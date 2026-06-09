# ATL::CRegKey::~CRegKey(void)

- ea: `0x140003944`
- end: `0x140003968`
- name: `??1CRegKey@ATL@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140015cac`
- `0x140015d4e`
- `0x140015dcc`
- `0x140015e02`
- `0x140015e5c`
- `0x140015e80`
- `0x140015fe4`
- `0x1400160b1`

## callees

- `0x140003944`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140003955`
- `ADVAPI32!RegCloseKey` at `0x140003955`

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
0x140003944  push    rbx
0x140003946  sub     rsp, 20h
0x14000394a  mov     rbx, rcx
0x14000394d  mov     rcx, [rcx]; hKey
0x140003950  test    rcx, rcx
0x140003953  jz      short loc_140003962
0x140003955  call    cs:__imp_RegCloseKey
0x14000395b  mov     qword ptr [rbx], 0
0x140003962  add     rsp, 20h
0x140003966  pop     rbx
0x140003967  retn
```
