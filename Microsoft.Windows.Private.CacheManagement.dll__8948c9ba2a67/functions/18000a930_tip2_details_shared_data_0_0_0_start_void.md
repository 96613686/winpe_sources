# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x18000a930`
- end: `0x18000ab0b`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `475`
- prototype: `_OWORD *__fastcall(__int64, _OWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800095d0`

## callees

- `0x18000a930`
- `0x18000aec0`
- `0x18000dfa0`
- `0x1800181b0`
- `0x18001cdf0`
- `0x18001d600`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000aa45`
- `KERNEL32!GetProcAddress` at `0x18000aa45`
- `KERNEL32!GetLastError` at `0x18000aa8b`
- `KERNEL32!GetLastError` at `0x18000aa8b`
- `KERNEL32!SetLastError` at `0x18000aa9d`
- `KERNEL32!SetLastError` at `0x18000aa9d`
- `KERNEL32!GetModuleHandleW` at `0x18000aa2e`
- `KERNEL32!GetModuleHandleW` at `0x18000aa2e`
- `KERNEL32!LeaveCriticalSection` at `0x18000aad7`
- `KERNEL32!LeaveCriticalSection` at `0x18000aad7`
- `KERNEL32!EnterCriticalSection` at `0x18000a969`
- `KERNEL32!EnterCriticalSection` at `0x18000a969`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000aac9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000aac9`

## string_xrefs

- `0x18000aa3b`: `TestCreate`
- `0x18000aa27`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_OWORD *__fastcall tip2::details::shared_data<0,0,0>::start(__int64 a1, _OWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  __int64 v5; // r15
  _OWORD *v6; // rsi
  __int64 v7; // r12
  unsigned int v8; // ebx
  unsigned __int8 v9; // r13
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v12; // rsi
  DWORD LastError; // ebx
  unsigned int v15; // [rsp+40h] [rbp-888h]
  LPVOID pv; // [rsp+50h] [rbp-878h] BYREF
  char v17; // [rsp+58h] [rbp-870h]
  int v18; // [rsp+59h] [rbp-86Fh] BYREF
  char v19; // [rsp+5Dh] [rbp-86Bh]
  _BYTE v20[2050]; // [rsp+5Eh] [rbp-86Ah] BYREF
  int *v21; // [rsp+860h] [rbp-68h]
  _BYTE *v22; // [rsp+868h] [rbp-60h]
  _BYTE *v23; // [rsp+870h] [rbp-58h]

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  memset(v20, 0, sizeof(v20));
  v5 = 0;
  pv = 0;
  v17 = 0;
  v21 = &v18;
  v23 = &v20[2043];
  v18 = -2143256512;
  v19 = 0;
  v22 = v20;
  if ( (*(_DWORD *)(a1 + 64) & 0x800) == 0 || (*(_DWORD *)(a1 + 20) & 0x8000) != 0 )
  {
    v6 = (_OWORD *)(a1 + 144);
    v7 = 0;
  }
  else
  {
    v6 = (_OWORD *)(a1 + 144);
    v7 = tip2::details::shared_data<0,0,0>::serialize_data((__int64 *)a1, (tson::write_buffer *)&pv, 1);
  }
  v8 = *(_DWORD *)(a1 + 20);
  v9 = *(_BYTE *)(a1 + 32);
  v15 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate )
    goto LABEL_10;
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "TestCreate");
  `TestCreate'::`2'::s_pfnTestCreate = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_10:
    v5 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, __int64, _OWORD *))ProcAddress)(
           v15,
           0,
           v9,
           v8,
           v7,
           v6);
  else
    *v6 = 0;
  v12 = *(_QWORD *)(a1 + 232);
  if ( v12 )
  {
    LastError = GetLastError();
    TestClose(v12);
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 232) = v5;
  *(_DWORD *)(a1 + 184) = 1;
  *a2 = *(_OWORD *)(a1 + 144);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v4 )
    LeaveCriticalSection(v4);
  return a2;
}

```

## disassembly

```asm
0x18000a930  mov     [rsp+arg_10], rbx
0x18000a935  push    rbp
0x18000a936  push    rsi
0x18000a937  push    rdi
0x18000a938  push    r12
0x18000a93a  push    r13
0x18000a93c  push    r14
0x18000a93e  push    r15
0x18000a940  sub     rsp, 890h
0x18000a947  mov     rax, cs:__security_cookie
0x18000a94e  xor     rax, rsp
0x18000a951  mov     [rsp+8C8h+var_48], rax
0x18000a959  mov     rbp, rdx
0x18000a95c  mov     rdi, rcx
0x18000a95f  lea     r14, [rcx+0C0h]
0x18000a966  mov     rcx, r14; lpCriticalSection
0x18000a969  call    cs:__imp_EnterCriticalSection
0x18000a96f  xor     edx, edx; Val
0x18000a971  mov     r8d, 802h; Size
0x18000a977  lea     rcx, [rsp+8C8h+var_86A]; void *
0x18000a97c  call    memset
0x18000a981  xor     r15d, r15d
0x18000a984  mov     [rsp+8C8h+pv], r15
0x18000a989  mov     [rsp+8C8h+var_870], r15b
0x18000a98e  lea     rax, [rsp+8C8h+var_86F]
0x18000a993  mov     [rsp+8C8h+var_68], rax
0x18000a99b  lea     rax, [rsp+8C8h+var_6F]
0x18000a9a3  mov     [rsp+8C8h+var_58], rax
0x18000a9ab  mov     [rsp+8C8h+var_86F], 80408040h
0x18000a9b3  mov     [rsp+8C8h+var_86B], r15b
0x18000a9b8  lea     rax, [rsp+8C8h+var_86A]
0x18000a9bd  mov     [rsp+8C8h+var_60], rax
0x18000a9c5  test    dword ptr [rdi+40h], 800h
0x18000a9cc  jz      short loc_18000A9F6
0x18000a9ce  test    dword ptr [rdi+14h], 8000h
0x18000a9d5  jnz     short loc_18000A9F6
0x18000a9d7  lea     rsi, [rdi+90h]
0x18000a9de  mov     r8d, 1
0x18000a9e4  lea     rdx, [rsp+8C8h+pv]
0x18000a9e9  mov     rcx, rdi
0x18000a9ec  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18000a9f1  mov     r12, rax
0x18000a9f4  jmp     short loc_18000AA00
0x18000a9f6  lea     rsi, [rdi+90h]
0x18000a9fd  mov     r12, r15
0x18000aa00  mov     ebx, [rdi+14h]
0x18000aa03  movzx   r13d, byte ptr [rdi+20h]
0x18000aa08  mov     eax, [rdi+10h]
0x18000aa0b  mov     [rsp+8C8h+var_888], eax
0x18000aa0f  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18000aa16  test    rax, rax
0x18000aa19  jnz     short loc_18000AA5F
0x18000aa1b  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18000aa22  test    rax, rax
0x18000aa25  jnz     short loc_18000AA3B
0x18000aa27  lea     rcx, ModuleName; "kernelbase.dll"
0x18000aa2e  call    cs:__imp_GetModuleHandleW
0x18000aa34  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18000aa3b  lea     rdx, aTestcreate; "TestCreate"
0x18000aa42  mov     rcx, rax; hModule
0x18000aa45  call    cs:__imp_GetProcAddress
0x18000aa4b  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18000aa52  test    rax, rax
0x18000aa55  jnz     short loc_18000AA5F
0x18000aa57  xorps   xmm0, xmm0
0x18000aa5a  movups  xmmword ptr [rsi], xmm0
0x18000aa5d  jmp     short loc_18000AA7F
0x18000aa5f  mov     [rsp+8C8h+var_8A0], rsi
0x18000aa64  mov     [rsp+8C8h+var_8A8], r12
0x18000aa69  mov     r9d, ebx
0x18000aa6c  movzx   r8d, r13b
0x18000aa70  xor     edx, edx
0x18000aa72  mov     ecx, [rsp+8C8h+var_888]
0x18000aa76  call    cs:__guard_dispatch_icall_fptr
0x18000aa7c  mov     r15, rax
0x18000aa7f  mov     rsi, [rdi+0E8h]
0x18000aa86  test    rsi, rsi
0x18000aa89  jz      short loc_18000AAA3
0x18000aa8b  call    cs:__imp_GetLastError
0x18000aa91  mov     ebx, eax
0x18000aa93  mov     rcx, rsi
0x18000aa96  call    TestClose
0x18000aa9b  mov     ecx, ebx; dwErrCode
0x18000aa9d  call    cs:__imp_SetLastError
0x18000aaa3  mov     [rdi+0E8h], r15
0x18000aaaa  mov     dword ptr [rdi+0B8h], 1
0x18000aab4  movups  xmm0, xmmword ptr [rdi+90h]
0x18000aabb  movups  xmmword ptr [rbp+0], xmm0
0x18000aabf  mov     rcx, [rsp+8C8h+pv]; pv
0x18000aac4  test    rcx, rcx
0x18000aac7  jz      short loc_18000AACF
0x18000aac9  call    cs:__imp_CoTaskMemFree
0x18000aacf  test    r14, r14
0x18000aad2  jz      short loc_18000AADD
0x18000aad4  mov     rcx, r14; lpCriticalSection
0x18000aad7  call    cs:__imp_LeaveCriticalSection
0x18000aadd  mov     rax, rbp
0x18000aae0  mov     rcx, [rsp+8C8h+var_48]
0x18000aae8  xor     rcx, rsp; StackCookie
0x18000aaeb  call    __security_check_cookie
0x18000aaf0  mov     rbx, [rsp+8C8h+arg_10]
0x18000aaf8  add     rsp, 890h
0x18000aaff  pop     r15
0x18000ab01  pop     r14
0x18000ab03  pop     r13
0x18000ab05  pop     r12
0x18000ab07  pop     rdi
0x18000ab08  pop     rsi
0x18000ab09  pop     rbp
0x18000ab0a  retn
```
