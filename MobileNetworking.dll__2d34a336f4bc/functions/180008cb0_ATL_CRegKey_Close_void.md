# ATL::CRegKey::Close(void)

- ea: `0x180008cb0`
- end: `0x180008cd6`
- name: `?Close@CRegKey@ATL@@QEAAJXZ`
- size: `38`
- prototype: `LSTATUS __fastcall(HKEY *this)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180008ce0`
- `0x180009170`
- `0x18000d978`
- `0x18000eac4`
- `0x18000eda0`
- `0x18000f160`

## callees

- `0x180008cb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008cc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008cc3`

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
0x180008cb0  push    rbx
0x180008cb2  sub     rsp, 20h
0x180008cb6  mov     rbx, rcx
0x180008cb9  xor     eax, eax
0x180008cbb  mov     rcx, [rcx]; hKey
0x180008cbe  test    rcx, rcx
0x180008cc1  jz      short loc_180008CD0
0x180008cc3  call    cs:__imp_RegCloseKey
0x180008cc9  mov     qword ptr [rbx], 0
0x180008cd0  add     rsp, 20h
0x180008cd4  pop     rbx
0x180008cd5  retn
```
