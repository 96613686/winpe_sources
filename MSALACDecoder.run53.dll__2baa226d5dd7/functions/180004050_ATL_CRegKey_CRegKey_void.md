# ATL::CRegKey::~CRegKey(void)

- ea: `0x180004050`
- end: `0x180004074`
- name: `??1CRegKey@ATL@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(ATL::CRegKey *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000a1fe`
- `0x18000a210`

## callees

- `0x180004050`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004061`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004061`

## pseudocode

```c
void __fastcall ATL::CRegKey::~CRegKey(HKEY *this)
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
0x180004050  push    rbx
0x180004052  sub     rsp, 20h
0x180004056  mov     rbx, rcx
0x180004059  mov     rcx, [rcx]; hKey
0x18000405c  test    rcx, rcx
0x18000405f  jz      short loc_18000406E
0x180004061  call    cs:__imp_RegCloseKey
0x180004067  mov     qword ptr [rbx], 0
0x18000406e  add     rsp, 20h
0x180004072  pop     rbx
0x180004073  retn
```
