# CARPFolder::_CompareAllColumns(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x180018c7c`
- end: `0x180018d8b`
- name: `?_CompareAllColumns@CARPFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@0@Z`
- size: `271`
- prototype: `__int64 __fastcall(CARPFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012170`

## callees

- `0x180013ecc`
- `0x180018c7c`

## import_xrefs

- `PROPSYS!PropVariantCompareEx` at `0x180018d46`
- `PROPSYS!PropVariantCompareEx` at `0x180018d46`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180018d1f`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180018d32`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180018d1f`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180018d32`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180018d62`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180018d6c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180018d62`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180018d6c`

## pseudocode

```c
__int64 __fastcall CARPFolder::_CompareAllColumns(
        CARPFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        const struct _ITEMIDLIST_RELATIVE *a3)
{
  unsigned int v4; // ebx
  __int64 v5; // r8
  __int64 v6; // r9
  const SERIALIZEDPROPSTORAGE *PropertyStorage; // r15
  const SERIALIZEDPROPSTORAGE *v8; // rsi
  unsigned int v9; // edi
  const PROPERTYKEY *v10; // rbx
  int v11; // eax
  DWORD v13; // [rsp+20h] [rbp-48h] BYREF
  PROPVARIANT ppropvar[2]; // [rsp+28h] [rbp-40h] BYREF
  __int64 v15; // [rsp+38h] [rbp-30h]
  PROPVARIANT propvar2[2]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v17; // [rsp+50h] [rbp-18h]
  DWORD cb; // [rsp+B8h] [rbp+50h] BYREF

  cb = 0;
  v4 = -2147024809;
  PropertyStorage = (const SERIALIZEDPROPSTORAGE *)CItemIDFactory<tagARPITEM,1230000705>::GetPropertyStorage(
                                                     a2,
                                                     &cb,
                                                     a3,
                                                     a3);
  if ( PropertyStorage )
  {
    v13 = 0;
    v8 = (const SERIALIZEDPROPSTORAGE *)CItemIDFactory<tagARPITEM,1230000705>::GetPropertyStorage(v6, &v13, v5, v6);
    if ( v8 )
    {
      v4 = 0;
      v9 = 0;
      do
      {
        if ( v9 >= *((_DWORD *)this + 36) )
          break;
        v10 = *(const PROPERTYKEY **)(32LL * v9 + *((_QWORD *)this + 17));
        v15 = 0;
        v17 = 0;
        *(_OWORD *)ppropvar = 0;
        *(_OWORD *)propvar2 = 0;
        PSGetPropertyFromPropertyStorage(PropertyStorage, cb, v10, ppropvar);
        PSGetPropertyFromPropertyStorage(v8, v13, v10, propvar2);
        v11 = PropVariantCompareEx(ppropvar, propvar2, PVCU_DEFAULT, 0);
        v4 = v11 >= 0 ? v11 > 0 : 0xFFFF;
        PropVariantClear(ppropvar);
        PropVariantClear(propvar2);
        ++v9;
      }
      while ( !v4 );
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180018c7c  push    rbp
0x180018c7e  push    rbx
0x180018c7f  push    rsi
0x180018c80  push    rdi
0x180018c81  push    r14
0x180018c83  push    r15
0x180018c85  mov     rbp, rsp
0x180018c88  sub     rsp, 68h
0x180018c8c  mov     rax, rdx
0x180018c8f  mov     [rbp+cb], 0
0x180018c96  mov     r14, rcx
0x180018c99  lea     rdx, [rbp+cb]
0x180018c9d  mov     rcx, rax
0x180018ca0  mov     r9, r8
0x180018ca3  mov     ebx, 80070057h
0x180018ca8  call    ?GetPropertyStorage@?$CItemIDFactory@UtagARPITEM@@$0EJFAFCEB@@@SAPEFBUtagSERIALIZEDPROPSTORAGE@@PEFBU_ITEMIDLIST_RELATIVE@@PEAK@Z; CItemIDFactory<tagARPITEM,1230000705>::GetPropertyStorage(_ITEMIDLIST_RELATIVE const *,ulong *)
0x180018cad  mov     r15, rax
0x180018cb0  test    rax, rax
0x180018cb3  jz      loc_180018D7C
0x180018cb9  lea     rdx, [rbp+var_48]
0x180018cbd  mov     [rbp+var_48], 0
0x180018cc4  mov     rcx, r9
0x180018cc7  call    ?GetPropertyStorage@?$CItemIDFactory@UtagARPITEM@@$0EJFAFCEB@@@SAPEFBUtagSERIALIZEDPROPSTORAGE@@PEFBU_ITEMIDLIST_RELATIVE@@PEAK@Z; CItemIDFactory<tagARPITEM,1230000705>::GetPropertyStorage(_ITEMIDLIST_RELATIVE const *,ulong *)
0x180018ccc  mov     rsi, rax
0x180018ccf  test    rax, rax
0x180018cd2  jz      loc_180018D7C
0x180018cd8  xor     ebx, ebx
0x180018cda  xor     edi, edi
0x180018cdc  cmp     edi, [r14+90h]
0x180018ce3  jnb     loc_180018D7C
0x180018ce9  mov     rax, [r14+88h]
0x180018cf0  lea     r9, [rbp+ppropvar]; ppropvar
0x180018cf4  mov     edx, [rbp+cb]; cb
0x180018cf7  xorps   xmm0, xmm0
0x180018cfa  xorps   xmm1, xmm1
0x180018cfd  mov     ecx, edi
0x180018cff  shl     rcx, 5
0x180018d03  mov     rbx, [rcx+rax]
0x180018d07  xor     eax, eax
0x180018d09  mov     r8, rbx; rpkey
0x180018d0c  mov     [rbp+var_30], rax
0x180018d10  mov     rcx, r15; psps
0x180018d13  mov     [rbp+var_18], rax
0x180018d17  movups  xmmword ptr [rbp+ppropvar], xmm0
0x180018d1b  movups  xmmword ptr [rbp+propvar2], xmm1
0x180018d1f  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x180018d25  mov     edx, [rbp+var_48]; cb
0x180018d28  lea     r9, [rbp+propvar2]; ppropvar
0x180018d2c  mov     r8, rbx; rpkey
0x180018d2f  mov     rcx, rsi; psps
0x180018d32  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x180018d38  xor     r9d, r9d; flags
0x180018d3b  lea     rdx, [rbp+propvar2]; propvar2
0x180018d3f  xor     r8d, r8d; unit
0x180018d42  lea     rcx, [rbp+ppropvar]; propvar1
0x180018d46  call    cs:__imp_PropVariantCompareEx
0x180018d4c  test    eax, eax
0x180018d4e  jns     short loc_180018D57
0x180018d50  mov     ebx, 0FFFFh
0x180018d55  jmp     short loc_180018D5E
0x180018d57  xor     ebx, ebx
0x180018d59  test    eax, eax
0x180018d5b  setnle  bl
0x180018d5e  lea     rcx, [rbp+ppropvar]; pvar
0x180018d62  call    cs:__imp_PropVariantClear
0x180018d68  lea     rcx, [rbp+propvar2]; pvar
0x180018d6c  call    cs:__imp_PropVariantClear
0x180018d72  inc     edi
0x180018d74  test    ebx, ebx
0x180018d76  jz      loc_180018CDC
0x180018d7c  mov     eax, ebx
0x180018d7e  add     rsp, 68h
0x180018d82  pop     r15
0x180018d84  pop     r14
0x180018d86  pop     rdi
0x180018d87  pop     rsi
0x180018d88  pop     rbx
0x180018d89  pop     rbp
0x180018d8a  retn
```
