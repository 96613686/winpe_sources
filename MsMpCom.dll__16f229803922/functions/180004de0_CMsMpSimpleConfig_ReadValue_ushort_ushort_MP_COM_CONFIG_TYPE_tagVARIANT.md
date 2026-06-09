# CMsMpSimpleConfig::ReadValue(ushort *,ushort *,_MP_COM_CONFIG_TYPE *,tagVARIANT *)

- ea: `0x180004de0`
- end: `0x180004e14`
- name: `?ReadValue@CMsMpSimpleConfig@@UEAAJPEAG0PEAW4_MP_COM_CONFIG_TYPE@@PEAUtagVARIANT@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(CMsMpSimpleConfig *__hidden this, unsigned __int16 *, unsigned __int16 *, enum _MP_COM_CONFIG_TYPE *, VARIANTARG *pvarg)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004de0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180004dfd`
- `OLEAUT32!__imp_VariantInit` at `0x180004dfd`

## pseudocode

```c
__int64 __fastcall CMsMpSimpleConfig::ReadValue(
        CMsMpSimpleConfig *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        enum _MP_COM_CONFIG_TYPE *a4,
        VARIANTARG *pvarg)
{
  if ( !a2 || !a3 || !a4 || !pvarg )
    return 2147500035LL;
  VariantInit(pvarg);
  return 2147500033LL;
}

```

## disassembly

```asm
0x180004de0  sub     rsp, 28h
0x180004de4  test    rdx, rdx
0x180004de7  jz      short loc_180004E0A
0x180004de9  test    r8, r8
0x180004dec  jz      short loc_180004E0A
0x180004dee  test    r9, r9
0x180004df1  jz      short loc_180004E0A
0x180004df3  mov     rcx, [rsp+28h+pvarg]; pvarg
0x180004df8  test    rcx, rcx
0x180004dfb  jz      short loc_180004E0A
0x180004dfd  call    cs:__imp_VariantInit
0x180004e03  mov     eax, 80004001h
0x180004e08  jmp     short loc_180004E0F
0x180004e0a  mov     eax, 80004003h
0x180004e0f  add     rsp, 28h
0x180004e13  retn
```
