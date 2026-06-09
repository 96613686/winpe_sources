# CRegistry::Close(void)

- ea: `0x180003958`
- end: `0x1800039bd`
- name: `?Close@CRegistry@@QEAAXXZ`
- size: `101`
- prototype: `void __fastcall(CRegistry *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002ea4`
- `0x1800039c4`
- `0x1800174ec`
- `0x18001d034`

## callees

- `0x180003958`
- `0x180003ef0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000398e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000399d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800039ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000398e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000399d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800039ad`

## pseudocode

```c
void __fastcall CRegistry::Close(CRegistry *this)
{
  HKEY v2; // rcx
  HKEY v3; // rcx

  v2 = (HKEY)*((_QWORD *)this + 2);
  if ( v2 )
  {
    RegCloseKey(v2);
    *((_QWORD *)this + 2) = 0;
  }
  v3 = (HKEY)*((_QWORD *)this + 1);
  if ( v3 )
  {
    RegCloseKey(v3);
    *((_QWORD *)this + 1) = 0;
  }
  if ( *(_QWORD *)this && *((_BYTE *)this + 36) )
  {
    RegCloseKey(*(HKEY *)this);
    *(_QWORD *)this = 0;
  }
  CRegistry::SetDefaultValues(this);
}

```

## disassembly

```asm
0x180003958  push    rbx
0x18000395a  sub     rsp, 20h
0x18000395e  mov     rbx, rcx
0x180003961  mov     rcx, [rcx+10h]; hKey
0x180003965  test    rcx, rcx
0x180003968  jnz     short loc_1800039AD
0x18000396a  mov     rcx, [rbx+8]; hKey
0x18000396e  test    rcx, rcx
0x180003971  jnz     short loc_18000399D
0x180003973  mov     rcx, [rbx]; hKey
0x180003976  test    rcx, rcx
0x180003979  jnz     short loc_180003988
0x18000397b  mov     rcx, rbx; this
0x18000397e  add     rsp, 20h
0x180003982  pop     rbx
0x180003983  jmp     ?SetDefaultValues@CRegistry@@AEAAXXZ; CRegistry::SetDefaultValues(void)
0x180003988  cmp     byte ptr [rbx+24h], 0
0x18000398c  jz      short loc_18000397B
0x18000398e  call    cs:__imp_RegCloseKey
0x180003994  mov     qword ptr [rbx], 0
0x18000399b  jmp     short loc_18000397B
0x18000399d  call    cs:__imp_RegCloseKey
0x1800039a3  mov     qword ptr [rbx+8], 0
0x1800039ab  jmp     short loc_180003973
0x1800039ad  call    cs:__imp_RegCloseKey
0x1800039b3  mov     qword ptr [rbx+10h], 0
0x1800039bb  jmp     short loc_18000396A
```
