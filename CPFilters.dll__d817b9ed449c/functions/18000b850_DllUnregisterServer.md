# DllUnregisterServer

- ea: `0x18000b850`
- end: `0x18000b946`
- name: `DllUnregisterServer`
- size: `246`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b850`
- `0x180013c40`
- `0x18006ccc0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000b87d`
- `ole32!CoCreateInstance` at `0x18000b87d`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  HRESULT v0; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = 0;
  v0 = CoCreateInstance(&rclsid, 0, 1u, &riid, &ppv);
  if ( v0 >= 0 )
  {
    (*(void (__fastcall **)(LPVOID, __int64 *, const wchar_t *, __int128 *))(*(_QWORD *)ppv + 32LL))(
      ppv,
      qword_180075C60,
      L"PBDA PTFilter",
      &xmmword_180075EA8);
    (*(void (__fastcall **)(LPVOID, __int64 *, const wchar_t *, __int128 *))(*(_QWORD *)ppv + 32LL))(
      ppv,
      qword_180075C60,
      L"PBDA ETFilter",
      &xmmword_180075E28);
    (*(void (__fastcall **)(LPVOID, __int64 *, const wchar_t *, __int128 *))(*(_QWORD *)ppv + 32LL))(
      ppv,
      qword_180075C60,
      L"PBDA DTFilter",
      &xmmword_1800759B0);
    v0 = sub_180013C40(0);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  else if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return v0;
}

```

## disassembly

```asm
0x18000b850  push    rbx
0x18000b852  sub     rsp, 30h
0x18000b856  mov     [rsp+38h+arg_0], 0
0x18000b85f  lea     rax, [rsp+38h+arg_0]
0x18000b864  mov     [rsp+38h+ppv], rax; ppv
0x18000b869  lea     r9, riid; riid
0x18000b870  xor     edx, edx; pUnkOuter
0x18000b872  lea     r8d, [rdx+1]; dwClsContext
0x18000b876  lea     rcx, rclsid; rclsid
0x18000b87d  call    cs:CoCreateInstance
0x18000b884  nop     dword ptr [rax+rax+00h]
0x18000b889  mov     ebx, eax
0x18000b88b  test    eax, eax
0x18000b88d  jns     short loc_18000B8AC
0x18000b88f  mov     rcx, [rsp+38h+arg_0]
0x18000b894  test    rcx, rcx
0x18000b897  jz      short loc_18000B8A7
0x18000b899  mov     rdx, [rcx]
0x18000b89c  mov     rax, [rdx+10h]
0x18000b8a0  call    cs:__guard_dispatch_icall_fptr
0x18000b8a6  nop
0x18000b8a7  jmp     loc_18000B93D
0x18000b8ac  mov     rcx, [rsp+38h+arg_0]
0x18000b8b1  mov     rax, [rcx]
0x18000b8b4  lea     r9, xmmword_180075EA8
0x18000b8bb  lea     r8, aPbdaPtfilter; "PBDA PTFilter"
0x18000b8c2  lea     rbx, qword_180075C60
0x18000b8c9  mov     rdx, rbx
0x18000b8cc  mov     rax, [rax+20h]
0x18000b8d0  call    cs:__guard_dispatch_icall_fptr
0x18000b8d6  mov     rcx, [rsp+38h+arg_0]
0x18000b8db  mov     rax, [rcx]
0x18000b8de  lea     r9, xmmword_180075E28
0x18000b8e5  lea     r8, aPbdaEtfilter; "PBDA ETFilter"
0x18000b8ec  mov     rdx, rbx
0x18000b8ef  mov     rax, [rax+20h]
0x18000b8f3  call    cs:__guard_dispatch_icall_fptr
0x18000b8f9  mov     rcx, [rsp+38h+arg_0]
0x18000b8fe  mov     rax, [rcx]
0x18000b901  lea     r9, xmmword_1800759B0
0x18000b908  lea     r8, aPbdaDtfilter; "PBDA DTFilter"
0x18000b90f  mov     rdx, rbx
0x18000b912  mov     rax, [rax+20h]
0x18000b916  call    cs:__guard_dispatch_icall_fptr
0x18000b91c  xor     ecx, ecx
0x18000b91e  call    sub_180013C40
0x18000b923  mov     ebx, eax
0x18000b925  mov     rcx, [rsp+38h+arg_0]
0x18000b92a  test    rcx, rcx
0x18000b92d  jz      short loc_18000B93D
0x18000b92f  mov     rdx, [rcx]
0x18000b932  mov     rax, [rdx+10h]
0x18000b936  call    cs:__guard_dispatch_icall_fptr
0x18000b93c  nop
0x18000b93d  mov     eax, ebx
0x18000b93f  add     rsp, 30h
0x18000b943  pop     rbx
0x18000b944  retn
```
