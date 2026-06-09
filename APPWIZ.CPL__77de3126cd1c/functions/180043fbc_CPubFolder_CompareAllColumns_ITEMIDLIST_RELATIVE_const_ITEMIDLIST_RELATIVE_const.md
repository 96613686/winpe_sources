# CPubFolder::_CompareAllColumns(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x180043fbc`
- end: `0x1800440d4`
- name: `?_CompareAllColumns@CPubFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@0@Z`
- size: `280`
- prototype: `__int64 __fastcall(CPubFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800427f0`

## callees

- `0x180043108`
- `0x180043fbc`

## import_xrefs

- `PROPSYS!PropVariantCompareEx` at `0x180044087`
- `PROPSYS!PropVariantCompareEx` at `0x180044087`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180044060`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180044073`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180044060`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180044073`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800440a3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800440ad`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800440a3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800440ad`

## pseudocode

```c
__int64 __fastcall CPubFolder::_CompareAllColumns(
        CPubFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        const struct _ITEMIDLIST_RELATIVE *a3)
{
  unsigned int v3; // ebx
  __int64 v4; // r8
  __int64 v5; // r9
  const SERIALIZEDPROPSTORAGE *PropertyStorage; // r14
  const SERIALIZEDPROPSTORAGE *v7; // rsi
  unsigned int v8; // edi
  const PROPERTYKEY *v9; // rbx
  int v10; // eax
  PROPVARIANT ppropvar[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v13; // [rsp+30h] [rbp-20h]
  PROPVARIANT propvar2[2]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v15; // [rsp+48h] [rbp-8h]
  DWORD cb; // [rsp+70h] [rbp+20h] BYREF
  int v17; // [rsp+74h] [rbp+24h]
  DWORD v18; // [rsp+88h] [rbp+38h] BYREF

  v17 = HIDWORD(this);
  cb = 0;
  v3 = -2147024809;
  PropertyStorage = (const SERIALIZEDPROPSTORAGE *)CItemIDFactory<tagPUBITEM,1279415632>::GetPropertyStorage(
                                                     a2,
                                                     &cb,
                                                     a3,
                                                     a3);
  if ( PropertyStorage )
  {
    v18 = 0;
    v7 = (const SERIALIZEDPROPSTORAGE *)CItemIDFactory<tagPUBITEM,1279415632>::GetPropertyStorage(v5, &v18, v4, v5);
    if ( v7 )
    {
      v3 = 0;
      v8 = 0;
      do
      {
        if ( v8 >= 5 )
          break;
        *(_OWORD *)ppropvar = 0;
        v9 = *(&off_18005F120 + 4 * (int)v8);
        v13 = 0;
        v15 = 0;
        *(_OWORD *)propvar2 = 0;
        PSGetPropertyFromPropertyStorage(PropertyStorage, cb, v9, ppropvar);
        PSGetPropertyFromPropertyStorage(v7, v18, v9, propvar2);
        v10 = PropVariantCompareEx(ppropvar, propvar2, PVCU_DEFAULT, 0);
        v3 = v10 >= 0 ? v10 > 0 : 0xFFFF;
        PropVariantClear(ppropvar);
        PropVariantClear(propvar2);
        ++v8;
      }
      while ( !v3 );
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180043fbc  mov     [rsp-18h+arg_8], rbx
0x180043fc1  mov     [rsp-18h+arg_10], rsi
0x180043fc6  mov     qword ptr [rsp-18h+cb], rcx
0x180043fcb  push    rbp
0x180043fcc  push    rdi
0x180043fcd  push    r14
0x180043fcf  mov     rbp, rsp
0x180043fd2  sub     rsp, 50h
0x180043fd6  mov     rcx, rdx
0x180043fd9  mov     [rbp+cb], 0
0x180043fe0  lea     rdx, [rbp+cb]
0x180043fe4  mov     r9, r8
0x180043fe7  mov     ebx, 80070057h
0x180043fec  call    ?GetPropertyStorage@?$CItemIDFactory@UtagPUBITEM@@$0EMECFFFA@@@SAPEFBUtagSERIALIZEDPROPSTORAGE@@PEFBU_ITEMIDLIST_RELATIVE@@PEAK@Z; CItemIDFactory<tagPUBITEM,1279415632>::GetPropertyStorage(_ITEMIDLIST_RELATIVE const *,ulong *)
0x180043ff1  mov     r14, rax
0x180043ff4  test    rax, rax
0x180043ff7  jz      loc_1800440BD
0x180043ffd  lea     rdx, [rbp+arg_18]
0x180044001  mov     [rbp+arg_18], 0
0x180044008  mov     rcx, r9
0x18004400b  call    ?GetPropertyStorage@?$CItemIDFactory@UtagPUBITEM@@$0EMECFFFA@@@SAPEFBUtagSERIALIZEDPROPSTORAGE@@PEFBU_ITEMIDLIST_RELATIVE@@PEAK@Z; CItemIDFactory<tagPUBITEM,1279415632>::GetPropertyStorage(_ITEMIDLIST_RELATIVE const *,ulong *)
0x180044010  mov     rsi, rax
0x180044013  test    rax, rax
0x180044016  jz      loc_1800440BD
0x18004401c  xor     ebx, ebx
0x18004401e  xor     edi, edi
0x180044020  cmp     edi, 5
0x180044023  jnb     loc_1800440BD
0x180044029  mov     edx, [rbp+cb]; cb
0x18004402c  lea     rbx, off_18005F120
0x180044033  xorps   xmm0, xmm0
0x180044036  movsxd  rax, edi
0x180044039  shl     rax, 5
0x18004403d  lea     r9, [rbp+ppropvar]; ppropvar
0x180044041  xorps   xmm1, xmm1
0x180044044  mov     rcx, r14; psps
0x180044047  movups  xmmword ptr [rbp+ppropvar], xmm0
0x18004404b  mov     rbx, [rax+rbx]
0x18004404f  xor     eax, eax
0x180044051  mov     r8, rbx; rpkey
0x180044054  mov     [rbp+var_20], rax
0x180044058  mov     [rbp+var_8], rax
0x18004405c  movups  xmmword ptr [rbp+propvar2], xmm1
0x180044060  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x180044066  mov     edx, [rbp+arg_18]; cb
0x180044069  lea     r9, [rbp+propvar2]; ppropvar
0x18004406d  mov     r8, rbx; rpkey
0x180044070  mov     rcx, rsi; psps
0x180044073  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x180044079  xor     r9d, r9d; flags
0x18004407c  lea     rdx, [rbp+propvar2]; propvar2
0x180044080  xor     r8d, r8d; unit
0x180044083  lea     rcx, [rbp+ppropvar]; propvar1
0x180044087  call    cs:__imp_PropVariantCompareEx
0x18004408d  test    eax, eax
0x18004408f  jns     short loc_180044098
0x180044091  mov     ebx, 0FFFFh
0x180044096  jmp     short loc_18004409F
0x180044098  xor     ebx, ebx
0x18004409a  test    eax, eax
0x18004409c  setnle  bl
0x18004409f  lea     rcx, [rbp+ppropvar]; pvar
0x1800440a3  call    cs:__imp_PropVariantClear
0x1800440a9  lea     rcx, [rbp+propvar2]; pvar
0x1800440ad  call    cs:__imp_PropVariantClear
0x1800440b3  inc     edi
0x1800440b5  test    ebx, ebx
0x1800440b7  jz      loc_180044020
0x1800440bd  lea     r11, [rsp+50h+var_s0]
0x1800440c2  mov     eax, ebx
0x1800440c4  mov     rbx, [r11+28h]
0x1800440c8  mov     rsi, [r11+30h]
0x1800440cc  mov     rsp, r11
0x1800440cf  pop     r14
0x1800440d1  pop     rdi
0x1800440d2  pop     rbp
0x1800440d3  retn
```
