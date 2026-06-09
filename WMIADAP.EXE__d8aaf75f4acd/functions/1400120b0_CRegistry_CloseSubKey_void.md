# CRegistry::CloseSubKey(void)

- ea: `0x1400120b0`
- end: `0x1400120d6`
- name: `?CloseSubKey@CRegistry@@AEAAXXZ`
- size: `38`
- prototype: `void __fastcall(CRegistry *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140013180`

## callees

- `0x1400120b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400120c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400120c2`

## pseudocode

```c
void __fastcall CRegistry::CloseSubKey(CRegistry *this)
{
  HKEY v2; // rcx

  v2 = (HKEY)*((_QWORD *)this + 2);
  if ( v2 )
    RegCloseKey(v2);
  *((_QWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x1400120b0  push    rbx
0x1400120b2  sub     rsp, 20h
0x1400120b6  mov     rbx, rcx
0x1400120b9  mov     rcx, [rcx+10h]; hKey
0x1400120bd  test    rcx, rcx
0x1400120c0  jz      short loc_1400120C8
0x1400120c2  call    cs:__imp_RegCloseKey
0x1400120c8  mov     qword ptr [rbx+10h], 0
0x1400120d0  add     rsp, 20h
0x1400120d4  pop     rbx
0x1400120d5  retn
```
