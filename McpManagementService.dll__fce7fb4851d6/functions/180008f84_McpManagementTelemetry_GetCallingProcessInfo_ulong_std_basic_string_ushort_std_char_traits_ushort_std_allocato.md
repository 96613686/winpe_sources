# McpManagementTelemetry::GetCallingProcessInfo(ulong *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180008f84`
- end: `0x1800090df`
- name: `?GetCallingProcessInfo@McpManagementTelemetry@@SAXPEAKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `347`
- prototype: `void *__fastcall(DWORD *, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x18000a338`
- `0x18000a41c`

## callees

- `0x180003a60`
- `0x1800045cc`
- `0x1800067a4`
- `0x180006a04`
- `0x180008f84`
- `0x18000e0a4`
- `0x18000e164`
- `0x18000e5e8`
- `0x180027324`
- `0x1800273d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180008fcc`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180008fcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008fec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008fec`

## pseudocode

```c
void *__fastcall McpManagementTelemetry::GetCallingProcessInfo(DWORD *a1, __int64 a2)
{
  int CallingProcessHandle; // esi
  char *v5; // rcx
  unsigned int *v6; // r8
  void *result; // rax
  unsigned __int64 v8; // rax
  __int64 v9; // rax
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rbx
  char *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rbx
  HANDLE Process; // [rsp+30h] [rbp-238h] BYREF
  DWORD dwSize; // [rsp+38h] [rbp-230h] BYREF
  WCHAR ExeName[264]; // [rsp+40h] [rbp-228h] BYREF

  Process = 0;
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle((__int64)a1, a2, &Process);
  if ( CallingProcessHandle >= 0 )
    *a1 = GetProcessId(Process);
  v5 = (char *)Process;
  Process = 0;
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  if ( CallingProcessHandle < 0 )
    *a1 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr() = 0;
  dwSize = 260;
  result = (void *)CallerIdentity::GetCallerProcessImageName(ExeName, &dwSize, v6);
  if ( (int)result >= 0 )
  {
    v8 = std::_WChar_traits<unsigned short>::length(ExeName);
    std::wstring::_Assign<unsigned short>(a2, (__int64)ExeName, v8);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    v9 = std::_WChar_traits<unsigned short>::length(L"\\");
    result = (void *)std::_Traits_rfind<std::char_traits<unsigned short>>(v10, *(_QWORD *)(a2 + 16), v10, v11, v9);
    if ( result != (void *)-1LL )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Check_offset(a2, 0);
      v12 = *(_QWORD *)(a2 + 16);
      v13 = (char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      v15 = v12 - v14;
      result = memmove_0(v13, &v13[2 * v14], 2 * v15 + 2);
      *(_QWORD *)(a2 + 16) = v15;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008f84  mov     [rsp+arg_10], rbx
0x180008f89  mov     [rsp+arg_18], rsi
0x180008f8e  push    rdi
0x180008f8f  sub     rsp, 260h
0x180008f96  mov     rax, cs:__security_cookie
0x180008f9d  xor     rax, rsp
0x180008fa0  mov     [rsp+268h+var_18], rax
0x180008fa8  lea     r8, [rsp+268h+Process]
0x180008fad  mov     [rsp+268h+Process], 0
0x180008fb6  mov     rdi, rdx
0x180008fb9  mov     rbx, rcx
0x180008fbc  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x180008fc1  mov     esi, eax
0x180008fc3  test    eax, eax
0x180008fc5  js      short loc_180008FD4
0x180008fc7  mov     rcx, [rsp+268h+Process]; Process
0x180008fcc  call    cs:__imp_GetProcessId
0x180008fd2  mov     [rbx], eax
0x180008fd4  mov     rcx, [rsp+268h+Process]; hObject
0x180008fd9  mov     [rsp+268h+Process], 0
0x180008fe2  lea     rdx, [rcx-1]
0x180008fe6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180008fea  ja      short loc_180008FF2
0x180008fec  call    cs:__imp_CloseHandle
0x180008ff2  test    esi, esi
0x180008ff4  jns     short loc_180008FFC
0x180008ff6  mov     dword ptr [rbx], 0
0x180008ffc  mov     rcx, rdi
0x180008fff  mov     qword ptr [rdi+10h], 0
0x180009007  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000900c  xor     ecx, ecx
0x18000900e  lea     rdx, [rsp+268h+dwSize]; lpdwSize
0x180009013  mov     [rax], cx
0x180009016  lea     rcx, [rsp+268h+ExeName]; lpExeName
0x18000901b  mov     [rsp+268h+dwSize], 104h
0x180009023  call    ?GetCallerProcessImageName@CallerIdentity@@YAJPEAGPEAK@Z; CallerIdentity::GetCallerProcessImageName(ushort *,ulong *)
0x180009028  test    eax, eax
0x18000902a  js      loc_1800090BA
0x180009030  lea     rcx, [rsp+268h+ExeName]
0x180009035  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000903a  mov     r8, rax
0x18000903d  lea     rdx, [rsp+268h+ExeName]
0x180009042  mov     rcx, rdi
0x180009045  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000904a  mov     rcx, rdi
0x18000904d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180009052  lea     rcx, asc_18002DEF8; "\\"
0x180009059  mov     r8, rax
0x18000905c  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180009061  mov     rdx, [rdi+10h]
0x180009065  mov     rcx, r8
0x180009068  mov     [rsp+268h+var_248], rax
0x18000906d  call    ??$_Traits_rfind@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_rfind<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x180009072  mov     rbx, rax
0x180009075  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009079  jz      short loc_1800090BA
0x18000907b  xor     edx, edx
0x18000907d  mov     rcx, rdi
0x180009080  call    ?_Check_offset@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAX_K@Z; std::_String_val<std::_Simple_types<ushort>>::_Check_offset(unsigned __int64)
0x180009085  lea     rax, [rbx+1]
0x180009089  mov     rcx, rdi
0x18000908c  mov     rbx, [rdi+10h]
0x180009090  cmp     rbx, rax
0x180009093  mov     rdx, rbx
0x180009096  cmovnb  rdx, rax
0x18000909a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000909f  sub     rbx, rdx
0x1800090a2  mov     rcx, rax; void *
0x1800090a5  lea     rdx, [rax+rdx*2]; Src
0x1800090a9  lea     r8, ds:2[rbx*2]; Size
0x1800090b1  call    memmove_0
0x1800090b6  mov     [rdi+10h], rbx
0x1800090ba  mov     rcx, [rsp+268h+var_18]
0x1800090c2  xor     rcx, rsp; StackCookie
0x1800090c5  call    __security_check_cookie
0x1800090ca  lea     r11, [rsp+268h+var_8]
0x1800090d2  mov     rbx, [r11+20h]
0x1800090d6  mov     rsi, [r11+28h]
0x1800090da  mov     rsp, r11
0x1800090dd  pop     rdi
0x1800090de  retn
```
