# DllRegisterServer

- ea: `0x18000b5e0`
- end: `0x18000b841`
- name: `DllRegisterServer`
- size: `609`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b5e0`
- `0x180013c40`
- `0x18006ccc0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000b640`
- `ole32!CoCreateInstance` at `0x18000b640`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT v0; // ebx
  LPVOID ppv; // [rsp+70h] [rbp+28h] BYREF

  ppv = 0;
  v0 = sub_180013C40(1u);
  if ( v0 < 0 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v0;
  }
  v0 = CoCreateInstance(&rclsid, 0, 1u, &riid, &ppv);
  if ( v0 < 0 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v0;
  }
  v0 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64, wchar_t *))(*(_QWORD *)ppv + 24LL))(
         ppv,
         qword_180075C60,
         6291456,
         aPbdaCpFilters);
  if ( v0 < 0 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v0;
  }
  v0 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, const wchar_t *, _QWORD, __int64 *, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 40LL))(
         ppv,
         &xmmword_180075EA8,
         L"PBDA PTFilter",
         0,
         qword_180075C60,
         L"PBDA PTFilter",
         qword_180088658);
  if ( v0 < 0 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v0;
  }
  v0 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, const wchar_t *, _QWORD, __int64 *, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 40LL))(
         ppv,
         &xmmword_180075E28,
         L"PBDA ETFilter",
         0,
         qword_180075C60,
         L"PBDA ETFilter",
         qword_180088658);
  if ( v0 < 0 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v0;
  }
  v0 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, const wchar_t *, _QWORD, __int64 *, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 40LL))(
         ppv,
         &xmmword_1800759B0,
         L"PBDA DTFilter",
         0,
         qword_180075C60,
         L"PBDA DTFilter",
         qword_180088078);
  if ( v0 < 0 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v0;
  }
  (*(void (__fastcall **)(LPVOID, __int64 *, _QWORD, __int128 *))(*(_QWORD *)ppv + 32LL))(
    ppv,
    qword_180075C40,
    0,
    &xmmword_180075EA8);
  (*(void (__fastcall **)(LPVOID, __int64 *, _QWORD, __int128 *))(*(_QWORD *)ppv + 32LL))(
    ppv,
    qword_180075C40,
    0,
    &xmmword_180075E28);
  (*(void (__fastcall **)(LPVOID, __int64 *, _QWORD, __int128 *))(*(_QWORD *)ppv + 32LL))(
    ppv,
    qword_180075C40,
    0,
    &xmmword_1800759B0);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 0;
}

```

## disassembly

```asm
0x18000b5e0  push    rbp
0x18000b5e2  push    rbx
0x18000b5e3  push    rsi
0x18000b5e4  push    rdi
0x18000b5e5  mov     rbp, rsp
0x18000b5e8  sub     rsp, 48h
0x18000b5ec  mov     [rbp+arg_0], 0
0x18000b5f4  mov     edi, 1
0x18000b5f9  mov     ecx, edi
0x18000b5fb  call    sub_180013C40
0x18000b600  mov     ebx, eax
0x18000b602  test    eax, eax
0x18000b604  jns     short loc_18000B624
0x18000b606  mov     rcx, [rbp+arg_0]
0x18000b60a  test    rcx, rcx
0x18000b60d  jz      short loc_18000B61D
0x18000b60f  mov     rdx, [rcx]
0x18000b612  mov     rax, [rdx+10h]
0x18000b616  call    cs:__guard_dispatch_icall_fptr
0x18000b61c  nop
0x18000b61d  mov     eax, ebx
0x18000b61f  jmp     loc_18000B837
0x18000b624  lea     rax, [rbp+arg_0]
0x18000b628  mov     [rsp+48h+ppv], rax; ppv
0x18000b62d  lea     r9, riid; riid
0x18000b634  mov     r8d, edi; dwClsContext
0x18000b637  xor     edx, edx; pUnkOuter
0x18000b639  lea     rcx, rclsid; rclsid
0x18000b640  call    cs:CoCreateInstance
0x18000b647  nop     dword ptr [rax+rax+00h]
0x18000b64c  mov     ebx, eax
0x18000b64e  test    eax, eax
0x18000b650  jns     short loc_18000B66B
0x18000b652  mov     rcx, [rbp+arg_0]
0x18000b656  test    rcx, rcx
0x18000b659  jz      short loc_18000B669
0x18000b65b  mov     rdx, [rcx]
0x18000b65e  mov     rax, [rdx+10h]
0x18000b662  call    cs:__guard_dispatch_icall_fptr
0x18000b668  nop
0x18000b669  jmp     short loc_18000B61D
0x18000b66b  mov     rcx, [rbp+arg_0]
0x18000b66f  mov     rax, [rcx]
0x18000b672  lea     r9, aPbdaCpFilters; "PBDA CP Filters"
0x18000b679  mov     r8d, 600000h
0x18000b67f  lea     rdi, qword_180075C60
0x18000b686  mov     rdx, rdi
0x18000b689  mov     rax, [rax+18h]
0x18000b68d  call    cs:__guard_dispatch_icall_fptr
0x18000b693  mov     ebx, eax
0x18000b695  test    eax, eax
0x18000b697  jns     short loc_18000B6B5
0x18000b699  mov     rcx, [rbp+arg_0]
0x18000b69d  test    rcx, rcx
0x18000b6a0  jz      short loc_18000B6B0
0x18000b6a2  mov     rdx, [rcx]
0x18000b6a5  mov     rax, [rdx+10h]
0x18000b6a9  call    cs:__guard_dispatch_icall_fptr
0x18000b6af  nop
0x18000b6b0  jmp     loc_18000B61D
0x18000b6b5  mov     rcx, [rbp+arg_0]
0x18000b6b9  mov     rax, [rcx]
0x18000b6bc  lea     rsi, qword_180088658
0x18000b6c3  mov     [rsp+48h+var_18], rsi
0x18000b6c8  lea     r8, aPbdaPtfilter; "PBDA PTFilter"
0x18000b6cf  mov     [rsp+48h+var_20], r8
0x18000b6d4  mov     [rsp+48h+ppv], rdi
0x18000b6d9  xor     r9d, r9d
0x18000b6dc  lea     rdx, xmmword_180075EA8
0x18000b6e3  mov     rax, [rax+28h]
0x18000b6e7  call    cs:__guard_dispatch_icall_fptr
0x18000b6ed  mov     ebx, eax
0x18000b6ef  test    eax, eax
0x18000b6f1  jns     short loc_18000B70F
0x18000b6f3  mov     rcx, [rbp+arg_0]
0x18000b6f7  test    rcx, rcx
0x18000b6fa  jz      short loc_18000B70A
0x18000b6fc  mov     rdx, [rcx]
0x18000b6ff  mov     rax, [rdx+10h]
0x18000b703  call    cs:__guard_dispatch_icall_fptr
0x18000b709  nop
0x18000b70a  jmp     loc_18000B61D
0x18000b70f  mov     rcx, [rbp+arg_0]
0x18000b713  mov     rax, [rcx]
0x18000b716  mov     [rsp+48h+var_18], rsi
0x18000b71b  lea     r8, aPbdaEtfilter; "PBDA ETFilter"
0x18000b722  mov     [rsp+48h+var_20], r8
0x18000b727  mov     [rsp+48h+ppv], rdi
0x18000b72c  xor     r9d, r9d
0x18000b72f  lea     rdx, xmmword_180075E28
0x18000b736  mov     rax, [rax+28h]
0x18000b73a  call    cs:__guard_dispatch_icall_fptr
0x18000b740  mov     ebx, eax
0x18000b742  test    eax, eax
0x18000b744  jns     short loc_18000B762
0x18000b746  mov     rcx, [rbp+arg_0]
0x18000b74a  test    rcx, rcx
0x18000b74d  jz      short loc_18000B75D
0x18000b74f  mov     rdx, [rcx]
0x18000b752  mov     rax, [rdx+10h]
0x18000b756  call    cs:__guard_dispatch_icall_fptr
0x18000b75c  nop
0x18000b75d  jmp     loc_18000B61D
0x18000b762  mov     rcx, [rbp+arg_0]
0x18000b766  mov     rax, [rcx]
0x18000b769  lea     rdx, qword_180088078
0x18000b770  mov     [rsp+48h+var_18], rdx
0x18000b775  lea     r8, aPbdaDtfilter; "PBDA DTFilter"
0x18000b77c  mov     [rsp+48h+var_20], r8
0x18000b781  mov     [rsp+48h+ppv], rdi
0x18000b786  xor     r9d, r9d
0x18000b789  lea     rdx, xmmword_1800759B0
0x18000b790  mov     rax, [rax+28h]
0x18000b794  call    cs:__guard_dispatch_icall_fptr
0x18000b79a  mov     ebx, eax
0x18000b79c  test    eax, eax
0x18000b79e  jns     short loc_18000B7BC
0x18000b7a0  mov     rcx, [rbp+arg_0]
0x18000b7a4  test    rcx, rcx
0x18000b7a7  jz      short loc_18000B7B7
0x18000b7a9  mov     rdx, [rcx]
0x18000b7ac  mov     rax, [rdx+10h]
0x18000b7b0  call    cs:__guard_dispatch_icall_fptr
0x18000b7b6  nop
0x18000b7b7  jmp     loc_18000B61D
0x18000b7bc  mov     rcx, [rbp+arg_0]
0x18000b7c0  mov     rax, [rcx]
0x18000b7c3  lea     r9, xmmword_180075EA8
0x18000b7ca  xor     r8d, r8d
0x18000b7cd  lea     rbx, qword_180075C40
0x18000b7d4  mov     rdx, rbx
0x18000b7d7  mov     rax, [rax+20h]
0x18000b7db  call    cs:__guard_dispatch_icall_fptr
0x18000b7e1  mov     rcx, [rbp+arg_0]
0x18000b7e5  mov     rax, [rcx]
0x18000b7e8  lea     r9, xmmword_180075E28
0x18000b7ef  xor     r8d, r8d
0x18000b7f2  mov     rdx, rbx
0x18000b7f5  mov     rax, [rax+20h]
0x18000b7f9  call    cs:__guard_dispatch_icall_fptr
0x18000b7ff  mov     rcx, [rbp+arg_0]
0x18000b803  mov     rax, [rcx]
0x18000b806  lea     r9, xmmword_1800759B0
0x18000b80d  xor     r8d, r8d
0x18000b810  mov     rdx, rbx
0x18000b813  mov     rax, [rax+20h]
0x18000b817  call    cs:__guard_dispatch_icall_fptr
0x18000b81d  nop
0x18000b81e  mov     rcx, [rbp+arg_0]
0x18000b822  test    rcx, rcx
0x18000b825  jz      short loc_18000B835
0x18000b827  mov     rax, [rcx]
0x18000b82a  mov     rax, [rax+10h]
0x18000b82e  call    cs:__guard_dispatch_icall_fptr
0x18000b834  nop
0x18000b835  xor     eax, eax
0x18000b837  add     rsp, 48h
0x18000b83b  pop     rdi
0x18000b83c  pop     rsi
0x18000b83d  pop     rbx
0x18000b83e  pop     rbp
0x18000b83f  retn
```
