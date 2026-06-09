# RegKey::SetValue(ushort const *,ushort const *)

- ea: `0x18000e398`
- end: `0x18000e3ef`
- name: `?SetValue@RegKey@@QEBAJPEBG0@Z`
- size: `87`
- prototype: `int(RegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18000e3f8`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18000e3b3`
- `KERNEL32!lstrlenW` at `0x18000e3b3`
- `ADVAPI32!RegSetValueExW` at `0x18000e3d9`
- `ADVAPI32!RegSetValueExW` at `0x18000e3d9`

## pseudocode

```c
LSTATUS __fastcall RegKey::SetValue(HKEY *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int v6; // eax

  v6 = lstrlenW(a3);
  return RegSetValueExW(this[1], a2, 0, 1u, (const BYTE *)a3, 2 * v6 + 2);
}

```

## disassembly

```asm
0x18000e398  mov     [rsp+arg_0], rbx
0x18000e39d  mov     [rsp+arg_8], rsi
0x18000e3a2  push    rdi
0x18000e3a3  sub     rsp, 30h
0x18000e3a7  mov     rsi, rcx
0x18000e3aa  mov     rbx, r8
0x18000e3ad  mov     rcx, r8; lpString
0x18000e3b0  mov     rdi, rdx
0x18000e3b3  call    cs:__imp_lstrlenW
0x18000e3b9  mov     rcx, [rsi+8]; hKey
0x18000e3bd  mov     r9d, 1; dwType
0x18000e3c3  xor     r8d, r8d; Reserved
0x18000e3c6  mov     rdx, rdi; lpValueName
0x18000e3c9  lea     eax, ds:2[rax*2]
0x18000e3d0  mov     [rsp+38h+cbData], eax; cbData
0x18000e3d4  mov     [rsp+38h+lpData], rbx; lpData
0x18000e3d9  call    cs:__imp_RegSetValueExW
0x18000e3df  mov     rbx, [rsp+38h+arg_0]
0x18000e3e4  mov     rsi, [rsp+38h+arg_8]
0x18000e3e9  add     rsp, 30h
0x18000e3ed  pop     rdi
0x18000e3ee  retn
```
