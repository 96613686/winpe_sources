# NLG::RegistryKey::~RegistryKey(void)

- ea: `0x18004175c`
- end: `0x180041789`
- name: `??1RegistryKey@NLG@@QEAA@XZ`
- size: `45`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18009ff9d`
- `0x18009ffd3`
- `0x1800a0099`
- `0x1800a17d2`
- `0x1800a1886`
- `0x1800a18e0`
- `0x1800a78fb`
- `0x1800a790d`
- `0x1800a793c`
- `0x1800a797a`
- `0x1800a79a6`

## callees

- `0x18004175c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041776`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041776`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall NLG::RegistryKey::~RegistryKey(HKEY *this)
{
  HKEY v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    RegCloseKey(v2);
    *this = 0;
  }
}

```

## disassembly

```asm
0x18004175c  push    rbx
0x18004175e  sub     rsp, 30h
0x180041762  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18004176b  mov     rbx, rcx
0x18004176e  mov     rcx, [rcx]; hKey
0x180041771  test    rcx, rcx
0x180041774  jz      short loc_180041783
0x180041776  call    cs:__imp_RegCloseKey
0x18004177c  mov     qword ptr [rbx], 0
0x180041783  add     rsp, 30h
0x180041787  pop     rbx
0x180041788  retn
```
