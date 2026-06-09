# CRegistry::SetValue(ushort const *,ushort const *,ulong)

- ea: `0x180032308`
- end: `0x180032391`
- name: `?SetValue@CRegistry@@QEBAXPEBG0K@Z`
- size: `137`
- prototype: `void __fastcall(CRegistry *this, const unsigned __int16 *, const unsigned __int16 *, ulong)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180031df0`

## callees

- `0x180032308`
- `0x18003261b`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032366`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032366`
- `KERNEL32!lstrlenW` at `0x18003233d`
- `KERNEL32!lstrlenW` at `0x18003233d`

## pseudocode

```c
void __fastcall CRegistry::SetValue(CRegistry *this, const unsigned __int16 *a2, const unsigned __int16 *a3, ulong a4)
{
  int v6; // eax
  LSTATUS v7; // eax
  ulong pExceptionObject; // [rsp+58h] [rbp+20h] BYREF

  pExceptionObject = a4;
  if ( *((_DWORD *)this + 10) )
  {
    pExceptionObject = *((_DWORD *)this + 10);
    throw &pExceptionObject;
  }
  v6 = lstrlenW(a3);
  v7 = RegSetValueExW(*(HKEY *)this, L"Device", 0, 1u, (const BYTE *)a3, 2 * v6 + 2);
  if ( v7 )
  {
    pExceptionObject = v7;
    throw &pExceptionObject;
  }
}

```

## disassembly

```asm
0x180032308  mov     [rsp+arg_0], rbx
0x18003230d  mov     [rsp+pExceptionObject], r9d
0x180032312  push    rdi
0x180032313  sub     rsp, 30h
0x180032317  mov     eax, [rcx+28h]
0x18003231a  mov     rdi, r8
0x18003231d  mov     rbx, rcx
0x180032320  test    eax, eax
0x180032322  jz      short loc_18003233A
0x180032324  lea     rdx, _TI1K; pThrowInfo
0x18003232b  mov     [rsp+38h+pExceptionObject], eax
0x18003232f  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180032334  call    _CxxThrowException_0
0x18003233a  mov     rcx, rdi; lpString
0x18003233d  call    cs:__imp_lstrlenW
0x180032343  mov     rcx, [rbx]; hKey
0x180032346  lea     rdx, aDevice_1; "Device"
0x18003234d  mov     r9d, 1; dwType
0x180032353  xor     r8d, r8d; Reserved
0x180032356  lea     eax, ds:2[rax*2]
0x18003235d  mov     [rsp+38h+cbData], eax; cbData
0x180032361  mov     [rsp+38h+lpData], rdi; lpData
0x180032366  call    cs:__imp_RegSetValueExW
0x18003236c  test    eax, eax
0x18003236e  jz      short loc_180032386
0x180032370  lea     rdx, _TI1K; pThrowInfo
0x180032377  mov     [rsp+38h+pExceptionObject], eax
0x18003237b  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180032380  call    _CxxThrowException_0
0x180032386  mov     rbx, [rsp+38h+arg_0]
0x18003238b  add     rsp, 30h
0x18003238f  pop     rdi
0x180032390  retn
```
