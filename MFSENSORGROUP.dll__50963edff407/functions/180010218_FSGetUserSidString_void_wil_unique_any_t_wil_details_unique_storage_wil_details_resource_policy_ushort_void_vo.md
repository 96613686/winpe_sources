# FSGetUserSidString(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180010218`
- end: `0x18001036a`
- name: `?FSGetUserSidString@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `338`
- prototype: `__int64 __fastcall(__int64, LPWSTR *)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800049b0`
- `0x1800742f0`
- `0x180074d40`
- `0x1800751d0`

## callees

- `0x180005fa0`
- `0x180010218`
- `0x180010370`
- `0x18001061c`
- `0x180031920`
- `0x18003491c`
- `0x180044b28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001031f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001031f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800102a5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800102a5`

## pseudocode

```c
__int64 __fastcall FSGetUserSidString(__int64 a1, LPWSTR *a2)
{
  LPWSTR v2; // rbx
  int v4; // eax
  unsigned int v5; // ebx
  signed int LastError; // eax
  __int64 v8; // rdx
  char v9; // [rsp+50h] [rbp+18h] BYREF

  v2 = *a2;
  if ( *a2 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v9);
    LocalFree(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v9);
  }
  *a2 = 0;
  v4 = FSGetUserToken_Internal((HANDLE)0xFFFFFFFFFFFFFFFBLL);
  v5 = v4;
  if ( v4 == -2147023888 )
  {
    v4 = FSGetUserToken_Internal((HANDLE)0xFFFFFFFFFFFFFFFCLL);
    v5 = v4;
    if ( v4 >= 0 )
      goto LABEL_5;
    if ( !g_wppLevels )
      return v5;
    v8 = 36;
LABEL_14:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v4);
    return v5;
  }
  if ( v4 < 0 )
  {
    if ( !g_wppLevels )
      return v5;
    v8 = 37;
    goto LABEL_14;
  }
LABEL_5:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    a2,
    0);
  if ( !ConvertSidToStringSidW(MEMORY[0], a2) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (v5 & 0x80000000) != 0 && g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x180010218  mov     rax, rsp
0x18001021b  mov     [rax+20h], rbx
0x18001021f  mov     [rax+8], rcx
0x180010223  push    rdi
0x180010224  sub     rsp, 30h
0x180010228  mov     rbx, [rdx]
0x18001022b  mov     rdi, rdx
0x18001022e  mov     qword ptr [rax+10h], 0
0x180010236  mov     dword ptr [rax+8], 0
0x18001023d  test    rbx, rbx
0x180010240  jnz     loc_180010312
0x180010246  lea     r8, [rsp+38h+arg_0]
0x18001024b  mov     qword ptr [rdi], 0
0x180010252  lea     rdx, [rsp+38h+Block]
0x180010257  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x18001025e  call    ?FSGetUserToken_Internal@@YAJPEAXAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@AEAK@Z; FSGetUserToken_Internal(void *,wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &,ulong &)
0x180010263  mov     ebx, eax
0x180010265  cmp     eax, 800703F0h
0x18001026a  jnz     loc_180010353
0x180010270  lea     r8, [rsp+38h+arg_0]
0x180010275  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x18001027c  lea     rdx, [rsp+38h+Block]
0x180010281  call    ?FSGetUserToken_Internal@@YAJPEAXAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@AEAK@Z; FSGetUserToken_Internal(void *,wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &,ulong &)
0x180010286  mov     ebx, eax
0x180010288  test    eax, eax
0x18001028a  js      loc_180010334
0x180010290  xor     edx, edx
0x180010292  mov     rcx, rdi
0x180010295  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001029a  mov     rcx, [rsp+38h+Block]
0x18001029f  mov     rdx, rdi; StringSid
0x1800102a2  mov     rcx, [rcx]; Sid
0x1800102a5  call    cs:__imp_ConvertSidToStringSidW
0x1800102ab  test    eax, eax
0x1800102ad  jz      short loc_1800102CB
0x1800102af  mov     rcx, [rsp+38h+Block]; Block
0x1800102b4  test    rcx, rcx
0x1800102b7  jz      short loc_1800102BE
0x1800102b9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800102be  mov     eax, ebx
0x1800102c0  mov     rbx, [rsp+38h+arg_18]
0x1800102c5  add     rsp, 30h
0x1800102c9  pop     rdi
0x1800102ca  retn
0x1800102cb  call    cs:__imp_GetLastError
0x1800102d1  mov     ebx, eax
0x1800102d3  test    eax, eax
0x1800102d5  jle     short loc_1800102E0
0x1800102d7  movzx   ebx, ax
0x1800102da  or      ebx, 80070000h
0x1800102e0  test    ebx, ebx
0x1800102e2  jns     short loc_1800102AF
0x1800102e4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800102eb  jb      short loc_1800102AF
0x1800102ed  mov     edx, 27h ; '''
0x1800102f2  mov     [rsp+38h+var_18], ebx
0x1800102f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102fd  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180010304  xor     r9d, r9d
0x180010307  mov     rcx, [rcx+10h]
0x18001030b  call    WPP_SF_qD
0x180010310  jmp     short loc_1800102AF
0x180010312  lea     rcx, [rsp+38h+arg_10]; this
0x180010317  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001031c  mov     rcx, rbx; hMem
0x18001031f  call    cs:__imp_LocalFree
0x180010325  lea     rcx, [rsp+38h+arg_10]; this
0x18001032a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001032f  jmp     loc_180010246
0x180010334  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001033b  jb      loc_1800102AF
0x180010341  mov     edx, 24h ; '$'
0x180010346  jmp     short loc_18001034D
0x180010348  mov     edx, 25h ; '%'
0x18001034d  mov     [rsp+38h+var_18], eax
0x180010351  jmp     short loc_1800102F6
0x180010353  test    eax, eax
0x180010355  jns     loc_180010290
0x18001035b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180010362  jb      loc_1800102AF
0x180010368  jmp     short loc_180010348
```
