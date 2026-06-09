# CDBFolder::_CreateItemTypeAssocArray(_ITEMID_CHILD const *,_GUID const &,void * *)

- ea: `0x1800281f4`
- end: `0x180028397`
- name: `?_CreateItemTypeAssocArray@CDBFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z`
- size: `419`
- prototype: `__int64 __fastcall(struct IShellFolder *this, const struct _ITEMID_CHILD *, IID *riid, void **ppv)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800082a0`

## callees

- `0x18000a730`
- `0x1800281f4`
- `0x180028a68`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!AssocCreateForClasses` at `0x18002836f`
- `Windows.Storage!AssocCreateForClasses` at `0x18002836f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002826c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002826c`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocCreate` at `0x1800282ca`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocCreate` at `0x1800282ca`
- `PROPSYS!PropVariantToBSTR` at `0x180028260`
- `PROPSYS!PropVariantToBSTR` at `0x180028260`
- `OLEAUT32!__imp_SysFreeString` at `0x18002837b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002837b`

## pseudocode

```c
__int64 __fastcall CDBFolder::_CreateItemTypeAssocArray(
        struct IShellFolder *this,
        const struct _ITEMID_CHILD *a2,
        IID *riid,
        void **ppv)
{
  HRESULT PropertyForItem; // ebx
  struct IBindCtx *v9; // r8
  unsigned int v10; // ecx
  unsigned int v11; // edi
  ASSOCIATIONELEMENT propvar; // [rsp+30h] [rbp-30h] BYREF
  int v14; // [rsp+48h] [rbp-18h]
  __int128 v15; // [rsp+50h] [rbp-10h]
  void *ppva; // [rsp+90h] [rbp+30h] BYREF
  BSTR pbstrOut; // [rsp+A8h] [rbp+48h] BYREF

  *ppv = 0;
  pbstrOut = 0;
  memset(&propvar, 0, sizeof(propvar));
  PropertyForItem = CDBFolder::GetPropertyForItem(&this[23], a2, &PKEY_ItemType, 0, &propvar);
  if ( PropertyForItem >= 0 )
  {
    PropertyForItem = PropVariantToBSTR((const PROPVARIANT *const)&propvar, &pbstrOut);
    PropVariantClear((PROPVARIANT *)&propvar);
    if ( PropertyForItem >= 0 )
    {
      v10 = SHGetAttributesWithBindCtx(this, a2, v9, 0x60400001u);
      if ( v10 == 4194305 )
      {
        v11 = 0x40000000;
      }
      else
      {
        if ( (v10 & 0x40000000) == 0 )
        {
          propvar.ac = ASSOCCLASS_PROGID_STR;
          propvar.hkClass = 0;
          propvar.pszClass = pbstrOut;
          v14 = 8;
          v15 = 0;
          PropertyForItem = AssocCreateForClasses(&propvar, ((v10 & 0x20000000) != 0) + 1, riid, ppv);
LABEL_12:
          SysFreeString(pbstrOut);
          return (unsigned int)PropertyForItem;
        }
        v11 = v10;
      }
      ppva = 0;
      *(GUID *)&propvar.ac = CLSID_QueryAssociations;
      PropertyForItem = AssocCreate((CLSID *)&propvar, &GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57, &ppva);
      if ( PropertyForItem >= 0 )
      {
        PropertyForItem = (*(__int64 (__fastcall **)(void *, _QWORD, BSTR, _QWORD, _QWORD))(*(_QWORD *)ppva + 24LL))(
                            ppva,
                            (v11 >> 26) & 8,
                            pbstrOut,
                            0,
                            0);
        if ( PropertyForItem >= 0 )
          PropertyForItem = (**(__int64 (__fastcall ***)(void *, IID *, void **))ppva)(ppva, riid, ppv);
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppva + 16LL))(ppva);
      }
      goto LABEL_12;
    }
  }
  return (unsigned int)PropertyForItem;
}

```

## disassembly

```asm
0x1800281f4  mov     [rsp-28h+arg_8], rbx
0x1800281f9  push    rbp
0x1800281fa  push    rsi
0x1800281fb  push    rdi
0x1800281fc  push    r14
0x1800281fe  push    r15
0x180028200  mov     rbp, rsp
0x180028203  sub     rsp, 60h
0x180028207  xor     eax, eax
0x180028209  mov     qword ptr [r9], 0
0x180028210  mov     [rbp+var_20], rax
0x180028214  mov     r14, r9
0x180028217  lea     rax, [rbp+propvar]
0x18002821b  mov     [rbp+pbstrOut], 0
0x180028223  mov     r15, r8
0x180028226  mov     [rsp+60h+var_40], rax
0x18002822b  mov     rsi, rcx
0x18002822e  lea     r8, PKEY_ItemType
0x180028235  xorps   xmm0, xmm0
0x180028238  add     rcx, 0B8h
0x18002823f  xor     r9d, r9d
0x180028242  mov     rdi, rdx
0x180028245  movups  xmmword ptr [rbp+propvar], xmm0
0x180028249  call    ?GetPropertyForItem@CDBFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@W4PROPERTY_GET_TYPE@@PEAUtagPROPVARIANT@@@Z; CDBFolder::GetPropertyForItem(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,PROPERTY_GET_TYPE,tagPROPVARIANT *)
0x18002824e  mov     ebx, eax
0x180028250  test    eax, eax
0x180028252  js      loc_180028381
0x180028258  lea     rdx, [rbp+pbstrOut]; pbstrOut
0x18002825c  lea     rcx, [rbp+propvar]; propvar
0x180028260  call    cs:__imp_PropVariantToBSTR
0x180028266  lea     rcx, [rbp+propvar]; pvar
0x18002826a  mov     ebx, eax
0x18002826c  call    cs:__imp_PropVariantClear
0x180028272  test    ebx, ebx
0x180028274  js      loc_180028381
0x18002827a  mov     r9d, 60400001h; unsigned int
0x180028280  mov     rdx, rdi; struct _ITEMIDLIST_RELATIVE *
0x180028283  mov     rcx, rsi; struct IShellFolder *
0x180028286  call    ?SHGetAttributesWithBindCtx@@YAKPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@K@Z; SHGetAttributesWithBindCtx(IShellFolder *,_ITEMIDLIST_RELATIVE const *,IBindCtx *,ulong)
0x18002828b  mov     ecx, eax
0x18002828d  cmp     eax, 400001h
0x180028292  jnz     short loc_18002829B
0x180028294  mov     edi, 40000000h
0x180028299  jmp     short loc_1800282A7
0x18002829b  bt      ecx, 1Eh
0x18002829f  jnb     loc_180028331
0x1800282a5  mov     edi, ecx
0x1800282a7  movups  xmm0, xmmword ptr cs:CLSID_QueryAssociations.Data1
0x1800282ae  lea     r8, [rbp+ppv]; ppv
0x1800282b2  mov     [rbp+ppv], 0
0x1800282ba  lea     rdx, _GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57; riid
0x1800282c1  lea     rcx, [rbp+propvar]; clsid
0x1800282c5  movdqu  xmmword ptr [rbp+propvar], xmm0
0x1800282ca  call    cs:__imp_AssocCreate
0x1800282d0  mov     ebx, eax
0x1800282d2  test    eax, eax
0x1800282d4  js      loc_180028377
0x1800282da  mov     rcx, [rbp+ppv]
0x1800282de  xor     r9d, r9d
0x1800282e1  mov     r8, [rbp+pbstrOut]
0x1800282e5  shr     edi, 1Ah
0x1800282e8  and     edi, 8
0x1800282eb  mov     [rsp+60h+var_40], 0
0x1800282f4  mov     rax, [rcx]
0x1800282f7  mov     edx, edi
0x1800282f9  mov     rax, [rax+18h]
0x1800282fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028302  mov     ebx, eax
0x180028304  test    eax, eax
0x180028306  js      short loc_18002831F
0x180028308  mov     rcx, [rbp+ppv]
0x18002830c  mov     r8, r14
0x18002830f  mov     rdx, r15
0x180028312  mov     rax, [rcx]
0x180028315  mov     rax, [rax]
0x180028318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002831d  mov     ebx, eax
0x18002831f  mov     rcx, [rbp+ppv]
0x180028323  mov     rax, [rcx]
0x180028326  mov     rax, [rax+10h]
0x18002832a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002832f  jmp     short loc_180028377
0x180028331  mov     rax, [rbp+pbstrOut]
0x180028335  and     ecx, 20000000h
0x18002833b  neg     ecx
0x18002833d  mov     dword ptr [rbp+propvar], 2
0x180028344  xorps   xmm0, xmm0
0x180028347  mov     [rbp+propvar+8], 0
0x18002834f  sbb     edx, edx
0x180028351  mov     [rbp+var_20], rax
0x180028355  neg     edx
0x180028357  mov     [rbp+var_18], 8
0x18002835e  inc     edx; cClasses
0x180028360  lea     rcx, [rbp+propvar]; rgClasses
0x180028364  mov     r9, r14; ppv
0x180028367  mov     r8, r15; riid
0x18002836a  movdqu  [rbp+var_10], xmm0
0x18002836f  call    cs:__imp_AssocCreateForClasses
0x180028375  mov     ebx, eax
0x180028377  mov     rcx, [rbp+pbstrOut]; bstrString
0x18002837b  call    cs:__imp_SysFreeString
0x180028381  mov     eax, ebx
0x180028383  mov     rbx, [rsp+60h+arg_8]
0x18002838b  add     rsp, 60h
0x18002838f  pop     r15
0x180028391  pop     r14
0x180028393  pop     rdi
0x180028394  pop     rsi
0x180028395  pop     rbp
0x180028396  retn
```
