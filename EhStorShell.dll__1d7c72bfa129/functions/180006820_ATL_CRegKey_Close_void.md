# ATL::CRegKey::Close(void)

- ea: `0x180006820`
- end: `0x180006846`
- name: `?Close@CRegKey@ATL@@QEAAJXZ`
- size: `38`
- prototype: `LSTATUS __fastcall(HKEY *this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180004fb8`
- `0x180006814`
- `0x180008660`
- `0x180008a68`
- `0x180008d88`

## callees

- `0x180006820`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180006833`
- `ADVAPI32!RegCloseKey` at `0x180006833`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::Close(HKEY *this)
{
  LSTATUS result; // eax
  HKEY v3; // rcx

  result = 0;
  v3 = *this;
  if ( v3 )
  {
    result = RegCloseKey(v3);
    *this = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180006820  push    rbx
0x180006822  sub     rsp, 20h
0x180006826  mov     rbx, rcx
0x180006829  xor     eax, eax
0x18000682b  mov     rcx, [rcx]; hKey
0x18000682e  test    rcx, rcx
0x180006831  jz      short loc_180006840
0x180006833  call    cs:__imp_RegCloseKey
0x180006839  mov     qword ptr [rbx], 0
0x180006840  add     rsp, 20h
0x180006844  pop     rbx
0x180006845  retn
```
