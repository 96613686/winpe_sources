# CDBFolder::_GetListDescriptionForChild(_ITEMID_CHILD const *,_GUID const &,void * *)

- ea: `0x180018750`
- end: `0x180018a2c`
- name: `?_GetListDescriptionForChild@CDBFolder@@AEAAJPEBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z`
- size: `732`
- prototype: `int(CDBFolder *__hidden this, const struct _ITEMID_CHILD *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800184e0`

## callees

- `0x18000a730`
- `0x18000ccdc`
- `0x18000e450`
- `0x180017a7c`
- `0x180018750`
- `0x18001989c`
- `0x180035860`
- `0x180045e20`
- `0x18004ba88`
- `0x180071dc0`
- `0x180072cf4`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x1800189dc`
- `SHCORE!IUnknown_Set` at `0x1800189dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800189fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018a07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800189fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018a07`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001885d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001885d`
- `PROPSYS!PropVariantToVariant` at `0x1800187df`
- `PROPSYS!PropVariantToVariant` at `0x1800187df`
- `OLEAUT32!__imp_VariantClear` at `0x180018879`
- `OLEAUT32!__imp_VariantClear` at `0x180018879`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDBFolder::_GetListDescriptionForChild(
        CDBFolder *this,
        const struct _ITEMID_CHILD *a2,
        const struct _GUID *a3,
        void **a4)
{
  int PropertyForItem; // ebx
  const struct _GUID *v8; // r8
  struct IStream *v9; // [rsp+30h] [rbp-D0h] BYREF
  struct IFilterCondition *v10; // [rsp+38h] [rbp-C8h] BYREF
  IUnknown *punk; // [rsp+40h] [rbp-C0h] BYREF
  struct IScopeFactory *v12; // [rsp+48h] [rbp-B8h] BYREF
  VARIANT pVar; // [rsp+50h] [rbp-B0h] BYREF
  PROPVARIANT pPropVar[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v15; // [rsp+78h] [rbp-88h]
  _BYTE v16[88]; // [rsp+80h] [rbp-80h] BYREF
  LPVOID pv; // [rsp+D8h] [rbp-28h]
  LPVOID v18; // [rsp+E8h] [rbp-18h]
  IUnknown *ppunk; // [rsp+100h] [rbp+0h] BYREF

  *a4 = 0;
  v10 = 0;
  *(_OWORD *)pPropVar = 0;
  v15 = 0;
  PropertyForItem = CDBFolder::GetPropertyForItem((char *)this + 184, a2, PKEY_FilterInfo, 0, pPropVar);
  if ( PropertyForItem >= 0 )
  {
    memset(&pVar, 0, sizeof(pVar));
    pVar.vt = 0;
    PropertyForItem = PropVariantToVariant(pPropVar, &pVar);
    if ( PropertyForItem >= 0 )
    {
      if ( (v9 = 0, pVar.vt == 13) && pVar.llVal || (PropertyForItem = -2147467262, pVar.vt == 9) && pVar.llVal )
      {
        PropertyForItem = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, struct IStream **))pVar.llVal)(
                            pVar.llVal,
                            &GUID_0000000c_0000_0000_c000_000000000046,
                            &v9);
        if ( PropertyForItem >= 0 )
        {
          PropertyForItem = SHLoadFilterFromStream(v9, &GUID_fca2857d_1760_4ad3_8c63_c9b602fcbaea, (void **)&v10);
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v9 + 16LL))(v9);
        }
      }
    }
    PropVariantClear(pPropVar);
    if ( pVar.vt == 4095 )
      pVar.vt = 8;
    VariantClear(&pVar);
    if ( PropertyForItem >= 0 )
    {
      if ( (unsigned int)IsScopeFilter(v10) )
      {
        v12 = 0;
        PropertyForItem = CScopeFactory_CreateInstance(0, &GUID_54410b83_6787_4418_9735_5aaaabe83a9a, (void **)&v12);
        if ( PropertyForItem >= 0 )
        {
          punk = 0;
          PropertyForItem = GetScopeFromFilter(v10, v12, v8, (void **)&punk);
          if ( PropertyForItem >= 0 )
          {
            v9 = 0;
            PropertyForItem = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IStream **))this + 33))(
                                *((_QWORD *)this + 33),
                                &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
                                &v9);
            if ( PropertyForItem >= 0 )
            {
              memset_0(v16, 0, 0xB0u);
              PropertyForItem = GetAUTOLISTINITFromAutoListDescription((__int64)v9, 0, (__int64)v16);
              if ( PropertyForItem >= 0 )
              {
                IUnknown_Set(&ppunk, punk);
                PropertyForItem = CAutoList::s_CreateInstance(
                                    (const struct AUTOLISTINIT *)v16,
                                    0,
                                    &GUID_077386d3_344c_4e33_aa67_31408b2ee7a8,
                                    a4);
                CoTaskMemFree(pv);
                CoTaskMemFree(v18);
                ClearAutoListInit((struct AUTOLISTINIT *)v16);
              }
              (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v9 + 16LL))(v9);
            }
            ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
          }
          (*(void (__fastcall **)(struct IScopeFactory *))(*(_QWORD *)v12 + 16LL))(v12);
        }
      }
      else
      {
        PropertyForItem = (***((__int64 (__fastcall ****)(_QWORD, GUID *, void **))this + 33))(
                            *((_QWORD *)this + 33),
                            &GUID_077386d3_344c_4e33_aa67_31408b2ee7a8,
                            a4);
      }
      (*(void (__fastcall **)(struct IFilterCondition *))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  return (unsigned int)PropertyForItem;
}

```

## disassembly

```asm
0x180018750  mov     [rsp-8+arg_10], rbx
0x180018755  push    rbp
0x180018756  push    rsi
0x180018757  push    rdi
0x180018758  lea     rbp, [rsp-40h]
0x18001875d  sub     rsp, 140h
0x180018764  mov     rax, cs:__security_cookie
0x18001876b  xor     rax, rsp
0x18001876e  mov     [rbp+50h+var_20], rax
0x180018772  mov     rsi, r9
0x180018775  mov     rdi, rcx
0x180018778  mov     qword ptr [r9], 0
0x18001877f  mov     [rsp+150h+var_118], 0
0x180018788  xorps   xmm0, xmm0
0x18001878b  xor     eax, eax
0x18001878d  movups  xmmword ptr [rsp+150h+pPropVar], xmm0
0x180018792  mov     [rsp+150h+var_D8], rax
0x180018797  add     rcx, 0B8h
0x18001879e  lea     rax, [rsp+150h+pPropVar]
0x1800187a3  mov     [rsp+150h+var_130], rax
0x1800187a8  xor     r9d, r9d
0x1800187ab  lea     r8, PKEY_FilterInfo
0x1800187b2  call    ?GetPropertyForItem@CDBFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@W4PROPERTY_GET_TYPE@@PEAUtagPROPVARIANT@@@Z; CDBFolder::GetPropertyForItem(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,PROPERTY_GET_TYPE,tagPROPVARIANT *)
0x1800187b7  mov     ebx, eax
0x1800187b9  test    eax, eax
0x1800187bb  js      loc_1800188C0
0x1800187c1  xorps   xmm0, xmm0
0x1800187c4  xor     eax, eax
0x1800187c6  movups  xmmword ptr [rsp+150h+pVar], xmm0
0x1800187cb  mov     qword ptr [rsp+150h+pVar+10h], rax
0x1800187d0  mov     word ptr [rsp+150h+pVar], ax
0x1800187d5  lea     rdx, [rsp+150h+pVar]; pVar
0x1800187da  lea     rcx, [rsp+150h+pPropVar]; pPropVar
0x1800187df  call    cs:__imp_PropVariantToVariant
0x1800187e5  mov     ebx, eax
0x1800187e7  test    eax, eax
0x1800187e9  js      short loc_180018858
0x1800187eb  mov     [rsp+150h+var_120], 0
0x1800187f4  mov     eax, 0Dh
0x1800187f9  mov     rcx, qword ptr [rsp+150h+pVar+8]
0x1800187fe  cmp     ax, word ptr [rsp+150h+pVar]
0x180018803  jnz     loc_18001897A
0x180018809  test    rcx, rcx
0x18001880c  jz      loc_18001897A
0x180018812  mov     rax, [rcx]
0x180018815  lea     r8, [rsp+150h+var_120]
0x18001881a  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180018821  mov     rax, [rax]
0x180018824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018829  mov     ebx, eax
0x18001882b  test    eax, eax
0x18001882d  js      short loc_180018858
0x18001882f  lea     r8, [rsp+150h+var_118]; void **
0x180018834  lea     rdx, _GUID_fca2857d_1760_4ad3_8c63_c9b602fcbaea; struct _GUID *
0x18001883b  mov     rcx, [rsp+150h+var_120]; struct IStream *
0x180018840  call    ?SHLoadFilterFromStream@@YAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z; SHLoadFilterFromStream(IStream *,_GUID const &,void * *)
0x180018845  mov     ebx, eax
0x180018847  mov     rcx, [rsp+150h+var_120]
0x18001884c  mov     rax, [rcx]
0x18001884f  mov     rax, [rax+10h]
0x180018853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018858  lea     rcx, [rsp+150h+pPropVar]; pvar
0x18001885d  call    cs:__imp_PropVariantClear
0x180018863  nop
0x180018864  mov     eax, 0FFFh
0x180018869  cmp     word ptr [rsp+150h+pVar], ax
0x18001886e  jz      loc_18001899D
0x180018874  lea     rcx, [rsp+150h+pVar]; pvarg
0x180018879  call    cs:__imp_VariantClear
0x18001887f  test    ebx, ebx
0x180018881  js      short loc_1800188C0
0x180018883  mov     rcx, [rsp+150h+var_118]; struct IFilterCondition *
0x180018888  call    ?IsScopeFilter@@YAHPEAUIFilterCondition@@@Z; IsScopeFilter(IFilterCondition *)
0x18001888d  test    eax, eax
0x18001888f  jnz     short loc_1800188E1
0x180018891  mov     rcx, [rdi+108h]
0x180018898  mov     rax, [rcx]
0x18001889b  mov     r8, rsi
0x18001889e  lea     rdx, _GUID_077386d3_344c_4e33_aa67_31408b2ee7a8
0x1800188a5  mov     rax, [rax]
0x1800188a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188ad  mov     ebx, eax
0x1800188af  mov     rcx, [rsp+150h+var_118]
0x1800188b4  mov     rax, [rcx]
0x1800188b7  mov     rax, [rax+10h]
0x1800188bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188c0  mov     eax, ebx
0x1800188c2  mov     rcx, [rbp+50h+var_20]
0x1800188c6  xor     rcx, rsp; StackCookie
0x1800188c9  call    __security_check_cookie
0x1800188ce  mov     rbx, [rsp+150h+arg_10]
0x1800188d6  add     rsp, 140h
0x1800188dd  pop     rdi
0x1800188de  pop     rsi
0x1800188df  pop     rbp
0x1800188e0  retn
0x1800188e1  mov     [rsp+150h+var_108], 0
0x1800188ea  lea     r8, [rsp+150h+var_108]; void **
0x1800188ef  lea     rdx, _GUID_54410b83_6787_4418_9735_5aaaabe83a9a; struct _GUID *
0x1800188f6  xor     ecx, ecx; struct IUnknown *
0x1800188f8  call    ?CScopeFactory_CreateInstance@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CScopeFactory_CreateInstance(IUnknown *,_GUID const &,void * *)
0x1800188fd  mov     ebx, eax
0x1800188ff  test    eax, eax
0x180018901  js      short loc_1800188AF
0x180018903  mov     [rsp+150h+punk], 0
0x18001890c  lea     r9, [rsp+150h+punk]; void **
0x180018911  mov     rdx, [rsp+150h+var_108]; struct IScopeFactory *
0x180018916  mov     rcx, [rsp+150h+var_118]; struct IFilterCondition *
0x18001891b  call    ?GetScopeFromFilter@@YAJPEAUIFilterCondition@@PEAUIScopeFactory@@AEBU_GUID@@PEAPEAX@Z; GetScopeFromFilter(IFilterCondition *,IScopeFactory *,_GUID const &,void * *)
0x180018920  mov     ebx, eax
0x180018922  test    eax, eax
0x180018924  js      short loc_180018964
0x180018926  mov     [rsp+150h+var_120], 0
0x18001892f  mov     rcx, [rdi+108h]
0x180018936  mov     rax, [rcx]
0x180018939  lea     r8, [rsp+150h+var_120]
0x18001893e  lea     rdx, _GUID_607c87f7_0696_4558_a368_de5e59cfe456
0x180018945  mov     rax, [rax]
0x180018948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001894d  mov     ebx, eax
0x18001894f  test    eax, eax
0x180018951  jns     short loc_1800189AC
0x180018953  mov     rcx, [rsp+150h+punk]
0x180018958  mov     rax, [rcx]
0x18001895b  mov     rax, [rax+10h]
0x18001895f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018964  mov     rcx, [rsp+150h+var_108]
0x180018969  mov     rax, [rcx]
0x18001896c  mov     rax, [rax+10h]
0x180018970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018975  jmp     loc_1800188AF
0x18001897a  mov     ebx, 80004002h
0x18001897f  mov     eax, 9
0x180018984  cmp     ax, word ptr [rsp+150h+pVar]
0x180018989  jnz     loc_180018858
0x18001898f  test    rcx, rcx
0x180018992  jz      loc_180018858
0x180018998  jmp     loc_180018812
0x18001899d  mov     eax, 8
0x1800189a2  mov     word ptr [rsp+150h+pVar], ax
0x1800189a7  jmp     loc_180018874
0x1800189ac  xor     edx, edx; Val
0x1800189ae  mov     r8d, 0B0h; Size
0x1800189b4  lea     rcx, [rbp+50h+var_D0]; void *
0x1800189b8  call    memset_0
0x1800189bd  lea     r8, [rbp+50h+var_D0]
0x1800189c1  xor     edx, edx
0x1800189c3  mov     rcx, [rsp+150h+var_120]
0x1800189c8  call    ?GetAUTOLISTINITFromAutoListDescription@@YAJPEAUIAutoListDescription@@W4AUTOLISTINIT_FLAGS@@PEAUAUTOLISTINIT@@@Z; GetAUTOLISTINITFromAutoListDescription(IAutoListDescription *,AUTOLISTINIT_FLAGS,AUTOLISTINIT *)
0x1800189cd  mov     ebx, eax
0x1800189cf  test    eax, eax
0x1800189d1  js      short loc_180018A16
0x1800189d3  mov     rdx, [rsp+150h+punk]; punk
0x1800189d8  lea     rcx, [rbp+50h+ppunk]; ppunk
0x1800189dc  call    cs:__imp_IUnknown_Set
0x1800189e2  mov     r9, rsi; void **
0x1800189e5  lea     r8, _GUID_077386d3_344c_4e33_aa67_31408b2ee7a8; struct _GUID *
0x1800189ec  xor     edx, edx; struct ICompositionProcessor *
0x1800189ee  lea     rcx, [rbp+50h+var_D0]; struct AUTOLISTINIT *
0x1800189f2  call    ?s_CreateInstance@CAutoList@@SAJPEBUAUTOLISTINIT@@PEAUICompositionProcessor@@AEBU_GUID@@PEAPEAX@Z; CAutoList::s_CreateInstance(AUTOLISTINIT const *,ICompositionProcessor *,_GUID const &,void * *)
0x1800189f7  mov     ebx, eax
0x1800189f9  mov     rcx, [rbp+50h+pv]; pv
0x1800189fd  call    cs:__imp_CoTaskMemFree
0x180018a03  mov     rcx, [rbp+50h+var_68]; pv
0x180018a07  call    cs:__imp_CoTaskMemFree
0x180018a0d  lea     rcx, [rbp+50h+var_D0]; struct AUTOLISTINIT *
0x180018a11  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x180018a16  mov     rcx, [rsp+150h+var_120]
0x180018a1b  mov     rax, [rcx]
0x180018a1e  mov     rax, [rax+10h]
0x180018a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a27  jmp     loc_180018953
```
