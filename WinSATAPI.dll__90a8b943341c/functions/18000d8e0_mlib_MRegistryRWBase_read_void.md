# mlib::MRegistryRWBase::read(void)

- ea: `0x18000d8e0`
- end: `0x18000d9ad`
- name: `?read@MRegistryRWBase@mlib@@UEAAHXZ`
- size: `205`
- prototype: `__int64 __fastcall(mlib::MRegistryRWBase *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001ecb8`

## callees

- `0x18000d8e0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d973`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d973`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d911`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d911`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d921`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d988`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d921`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d955`

## pseudocode

```c
__int64 __fastcall mlib::MRegistryRWBase::read(HKEY *this)
{
  HKEY *v1; // r14
  LSTATUS v3; // edi
  unsigned int v5; // edi
  DWORD LastError; // esi

  v1 = this + 1;
  v3 = RegOpenKeyExW(this[4], *((LPCWSTR *)this[3] + 3), 0, 0x20019u, this + 1);
  SetLastError(v3);
  if ( v3 )
  {
    *v1 = 0;
    return 1;
  }
  else
  {
    v5 = (*((__int64 (__fastcall **)(HKEY *))*this + 3))(this);
    LastError = GetLastError();
    *((_BYTE *)this + 64) = v5 == 0;
    if ( *v1 )
    {
      RegCloseKey(*v1);
      *v1 = 0;
    }
    SetLastError(LastError);
    return v5;
  }
}

```

## disassembly

```asm
0x18000d8e0  mov     [rsp+arg_8], rbx
0x18000d8e5  mov     [rsp+arg_10], rdi
0x18000d8ea  push    r14
0x18000d8ec  sub     rsp, 30h
0x18000d8f0  mov     rax, [rcx+18h]
0x18000d8f4  lea     r14, [rcx+8]
0x18000d8f8  mov     rbx, rcx
0x18000d8fb  mov     [rsp+38h+phkResult], r14; phkResult
0x18000d900  mov     rcx, [rcx+20h]; hKey
0x18000d904  mov     r9d, 20019h; samDesired
0x18000d90a  xor     r8d, r8d; ulOptions
0x18000d90d  mov     rdx, [rax+18h]; lpSubKey
0x18000d911  call    cs:__imp_RegOpenKeyExW
0x18000d918  nop     dword ptr [rax+rax+00h]
0x18000d91d  mov     ecx, eax; dwErrCode
0x18000d91f  mov     edi, eax
0x18000d921  call    cs:__imp_SetLastError
0x18000d928  nop     dword ptr [rax+rax+00h]
0x18000d92d  test    edi, edi
0x18000d92f  jz      short loc_18000D93F
0x18000d931  mov     qword ptr [r14], 0
0x18000d938  mov     eax, 1
0x18000d93d  jmp     short loc_18000D99B
0x18000d93f  mov     rax, [rbx]
0x18000d942  mov     rcx, rbx
0x18000d945  mov     [rsp+38h+arg_0], rsi
0x18000d94a  mov     rax, [rax+18h]
0x18000d94e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d953  mov     edi, eax
0x18000d955  call    cs:__imp_GetLastError
0x18000d95c  nop     dword ptr [rax+rax+00h]
0x18000d961  test    edi, edi
0x18000d963  mov     esi, eax
0x18000d965  setz    cl
0x18000d968  mov     [rbx+40h], cl
0x18000d96b  mov     rcx, [r14]; hKey
0x18000d96e  test    rcx, rcx
0x18000d971  jz      short loc_18000D986
0x18000d973  call    cs:__imp_RegCloseKey
0x18000d97a  nop     dword ptr [rax+rax+00h]
0x18000d97f  mov     qword ptr [r14], 0
0x18000d986  mov     ecx, esi; dwErrCode
0x18000d988  call    cs:__imp_SetLastError
0x18000d98f  nop     dword ptr [rax+rax+00h]
0x18000d994  mov     rsi, [rsp+38h+arg_0]
0x18000d999  mov     eax, edi
0x18000d99b  mov     rbx, [rsp+38h+arg_8]
0x18000d9a0  mov     rdi, [rsp+38h+arg_10]
0x18000d9a5  add     rsp, 30h
0x18000d9a9  pop     r14
0x18000d9ab  retn
```
