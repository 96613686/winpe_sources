# CDBFolder::GetContainerStackType(_ITEMID_CHILD const *,bool,ushort * *,ushort * *,ushort * *)

- ea: `0x1800191d0`
- end: `0x180019701`
- name: `?GetContainerStackType@CDBFolder@@UEAAXPEFBU_ITEMID_CHILD@@_NPEAPEAG22@Z`
- size: `1329`
- prototype: `void(CDBFolder *__hidden this, const struct _ITEMID_CHILD *, bool, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180017690`

## callees

- `0x18000a730`
- `0x1800182a0`
- `0x1800191d0`
- `0x180019708`
- `0x180019870`
- `0x180019b10`
- `0x180071dc0`
- `0x180072cd0`
- `0x18007a4e0`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!__imp_SHGetFolderTypeDescription` at `0x1800195fc`
- `Windows.Storage!__imp_SHGetFolderTypeDescription` at `0x1800195fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001951a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001951a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800194d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019651`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800194d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019651`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180019423`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180019423`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x180019374`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x180019374`
- `PROPSYS!PropVariantToVariant` at `0x1800192ab`
- `PROPSYS!PropVariantToVariant` at `0x1800192ab`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x180019491`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x180019491`
- `OLEAUT32!__imp_VariantClear` at `0x18001943f`
- `OLEAUT32!__imp_VariantClear` at `0x18001943f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CDBFolder::GetContainerStackType(
        CDBFolder *this,
        const struct _ITEMID_CHILD *a2,
        bool a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6)
{
  HRESULT v10; // ebx
  __int64 v11; // rsi
  CFilterCondition *v12; // rax
  CFilterCondition *v13; // rdi
  int v14; // ebx
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rdi
  unsigned __int64 v17; // rbx
  void *v18; // rcx
  unsigned __int64 v19; // rdx
  unsigned __int16 *v20; // r8
  unsigned __int16 *v21; // r9
  unsigned __int16 *v22; // rax
  __int64 v23; // rcx
  unsigned __int16 v24; // r10
  __int64 v25; // r9
  unsigned __int16 *v26; // rcx
  _WORD *v27; // rcx
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rcx
  unsigned __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rcx
  void *v34; // rcx
  __int64 v35; // rbx
  bool v36; // cf
  void *ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v38; // [rsp+38h] [rbp-C8h] BYREF
  CFilterCondition *v39; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v40; // [rsp+48h] [rbp-B8h] BYREF
  VARIANT pVar; // [rsp+50h] [rbp-B0h] BYREF
  PROPVARIANT pPropVar[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v43; // [rsp+78h] [rbp-88h]
  PROPERTYKEY propkey; // [rsp+80h] [rbp-80h] BYREF
  __int128 v45; // [rsp+98h] [rbp-68h] BYREF
  WCHAR v46[128]; // [rsp+B0h] [rbp-50h] BYREF

  *a6 = 0;
  *a5 = 0;
  *a4 = 0;
  v45 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 10) + 104LL))(*((_QWORD *)this + 10), &v45) >= 0 )
  {
    v38 = 0;
    if ( (int)SHGetFolderTypeDescription(&v45, &GUID_e2ba9629_b18f_4e3a_aba5_42d879e79c80, &v38) >= 0 )
    {
      ppv = 0;
      if ( (*(int (__fastcall **)(__int64, void **))(*(_QWORD *)v38 + 80LL))(v38, &ppv) >= 0
        && (int)CreateStackAssocationElement(v46, v31, (const unsigned __int16 *)ppv, a3) >= 0 )
      {
        _AllocString<CTCoAllocPolicy>(v33, v32, v46, a6);
      }
      v34 = ppv;
      ppv = 0;
      CoTaskMemFree(v34);
    }
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  memset(&propkey, 0, sizeof(propkey));
  v38 = 0;
  *(_OWORD *)pPropVar = 0;
  v43 = 0;
  if ( (int)CDBFolder::GetPropertyForItem(this, a2, PKEY_FilterInfo, 0, pPropVar) >= 0 )
  {
    memset(&pVar, 0, sizeof(pVar));
    pVar.vt = 0;
    v10 = PropVariantToVariant(pPropVar, &pVar);
    if ( v10 >= 0 )
    {
      if ( (v40 = 0, pVar.vt == 13) && pVar.llVal || (v10 = -2147467262, pVar.vt == 9) && pVar.llVal )
      {
        v10 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))pVar.llVal)(
                pVar.llVal,
                &GUID_0000000c_0000_0000_c000_000000000046,
                &v40);
        if ( v10 >= 0 )
        {
          v11 = v40;
          v38 = 0;
          ppv = 0;
          v10 = -2147024882;
          v12 = (CFilterCondition *)wil::details::heap_allocator::allocate(0x50u);
          v13 = v12;
          v39 = v12;
          if ( v12 )
          {
            *(_QWORD *)v12 = &CFilterCondition::`vftable'{for `IFilterCondition'};
            *((_QWORD *)v12 + 1) = &CFilterCondition::`vftable'{for `IObjectCollection'};
            *((_DWORD *)v12 + 4) = 1;
            *((_QWORD *)v12 + 9) = 0;
            _InterlockedIncrement(&g_cDllRef);
            v10 = QISearch(
                    v12,
                    &`CFilterCondition::QueryInterface'::`2'::qit,
                    &GUID_00000000_0000_0000_c000_000000000046,
                    &ppv);
            CFilterCondition::Release(v13);
            if ( v10 >= 0 )
            {
              v39 = 0;
              v10 = (**(__int64 (__fastcall ***)(void *, GUID *, CFilterCondition **))ppv)(
                      ppv,
                      &GUID_00000109_0000_0000_c000_000000000046,
                      &v39);
              if ( v10 >= 0 )
              {
                v10 = (*(__int64 (__fastcall **)(CFilterCondition *, __int64))(*(_QWORD *)v39 + 40LL))(v39, v11);
                (*(void (__fastcall **)(CFilterCondition *))(*(_QWORD *)v39 + 16LL))(v39);
                if ( v10 >= 0 )
                  v10 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))ppv)(
                          ppv,
                          &GUID_fca2857d_1760_4ad3_8c63_c9b602fcbaea,
                          &v38);
              }
              (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
            }
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        }
      }
    }
    PropVariantClear(pPropVar);
    if ( pVar.vt == 4095 )
      pVar.vt = 8;
    VariantClear(&pVar);
    if ( v10 >= 0 )
    {
      v14 = (*(__int64 (__fastcall **)(__int64, PROPERTYKEY *))(*(_QWORD *)v38 + 80LL))(v38, &propkey);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      if ( v14 >= 0 && (propkey.pid || memcmp_0(&propkey, &PKEY_Null, 0x10u)) )
      {
        ppv = 0;
        if ( PSGetNameFromPropertyKey(&propkey, (PWSTR *)&ppv) < 0 )
          goto LABEL_24;
        if ( (int)CreateStackAssocationElement(v46, v15, (const unsigned __int16 *)ppv, a3) < 0 )
          goto LABEL_24;
        v16 = -1;
        do
          ++v16;
        while ( v46[v16] );
        *a4 = 0;
        v17 = v16 + 1;
        if ( v16 + 1 < v16
          || !is_mul_ok(v17, 2u)
          || (v20 = (unsigned __int16 *)CoTaskMemAlloc(2 * v17), (*a4 = v20) == 0) )
        {
LABEL_24:
          v18 = ppv;
          ppv = 0;
          CoTaskMemFree(v18);
          return;
        }
        if ( v17 <= 0x7FFFFFFF )
        {
          if ( v16 < 0x7FFFFFFF )
          {
            v21 = v46;
            v19 = v16 + 1;
            v22 = v20;
            v23 = 0;
            do
            {
              if ( !v16 )
                break;
              v24 = *v21;
              if ( !*v21 )
                break;
              ++v21;
              *v22++ = v24;
              --v16;
              ++v23;
              --v19;
            }
            while ( v19 );
            v25 = v23 - 1;
            if ( v19 )
              v25 = v23;
            v26 = v22 - 1;
            if ( v19 )
              v26 = v22;
            *v26 = 0;
            if ( v19 )
            {
              v36 = v17 == v25;
              v35 = v17 - v25;
              if ( !v36 && v35 != 1 )
                StringExHandleFillBehindNullW(&v20[v25], 2 * v35, 0x300u);
            }
LABEL_39:
            v27 = ppv;
            v28 = 0;
            while ( *v27 )
            {
              if ( *v27 == 46 && ++v28 == 2 )
              {
                *v27 = 0;
                if ( (int)CreateStackAssocationElement(v46, v19, (const unsigned __int16 *)ppv, a3) >= 0 )
                  _AllocString<CTCoAllocPolicy>(v30, v29, v46, a5);
                goto LABEL_24;
              }
              ++v27;
            }
            goto LABEL_24;
          }
          if ( v16 == -1 )
            goto LABEL_39;
        }
        *v20 = 0;
        goto LABEL_39;
      }
    }
  }
}

```

## disassembly

```asm
0x1800191d0  mov     [rsp-8+arg_10], rbx
0x1800191d5  push    rbp
0x1800191d6  push    rsi
0x1800191d7  push    rdi
0x1800191d8  push    r12
0x1800191da  push    r13
0x1800191dc  push    r14
0x1800191de  push    r15
0x1800191e0  lea     rbp, [rsp-0C0h]
0x1800191e8  sub     rsp, 1C0h
0x1800191ef  mov     rax, cs:__security_cookie
0x1800191f6  xor     rax, rsp
0x1800191f9  mov     [rbp+0F0h+var_40], rax
0x180019200  mov     r14, r9
0x180019203  mov     r15b, r8b
0x180019206  mov     rsi, rdx
0x180019209  mov     rdi, rcx
0x18001920c  mov     r12, [rbp+0F0h+arg_20]
0x180019213  mov     rbx, [rbp+0F0h+arg_28]
0x18001921a  xor     r13d, r13d
0x18001921d  mov     [rbx], r13
0x180019220  mov     [r12], r13
0x180019224  mov     [r9], r13
0x180019227  xorps   xmm0, xmm0
0x18001922a  movups  [rbp+0F0h+var_158], xmm0
0x18001922e  mov     rcx, [rcx+50h]
0x180019232  mov     rax, [rcx]
0x180019235  lea     rdx, [rbp+0F0h+var_158]
0x180019239  mov     rax, [rax+68h]
0x18001923d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019242  test    eax, eax
0x180019244  jns     loc_1800195E7
0x18001924a  xorps   xmm0, xmm0
0x18001924d  xor     eax, eax
0x18001924f  movups  xmmword ptr [rbp+0F0h+propkey.fmtid.Data1], xmm0
0x180019253  mov     [rbp+0F0h+propkey.pid], eax
0x180019256  mov     [rsp+1F0h+var_1B8], r13
0x18001925b  movups  xmmword ptr [rsp+1F0h+pPropVar], xmm0
0x180019260  mov     [rsp+1F0h+var_178], rax
0x180019265  lea     rax, [rsp+1F0h+pPropVar]
0x18001926a  mov     [rsp+1F0h+var_1D0], rax
0x18001926f  xor     r9d, r9d
0x180019272  lea     r8, PKEY_FilterInfo
0x180019279  mov     rdx, rsi
0x18001927c  mov     rcx, rdi
0x18001927f  call    ?GetPropertyForItem@CDBFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@W4PROPERTY_GET_TYPE@@PEAUtagPROPVARIANT@@@Z; CDBFolder::GetPropertyForItem(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,PROPERTY_GET_TYPE,tagPROPVARIANT *)
0x180019284  test    eax, eax
0x180019286  js      loc_1800194DE
0x18001928c  xorps   xmm0, xmm0
0x18001928f  xor     eax, eax
0x180019291  movups  xmmword ptr [rsp+1F0h+pVar], xmm0
0x180019296  mov     qword ptr [rsp+1F0h+pVar+10h], rax
0x18001929b  mov     word ptr [rsp+1F0h+pVar], r13w
0x1800192a1  lea     rdx, [rsp+1F0h+pVar]; pVar
0x1800192a6  lea     rcx, [rsp+1F0h+pPropVar]; pPropVar
0x1800192ab  call    cs:__imp_PropVariantToVariant
0x1800192b1  mov     ebx, eax
0x1800192b3  test    eax, eax
0x1800192b5  js      loc_18001941E
0x1800192bb  mov     [rsp+1F0h+var_1A8], r13
0x1800192c0  mov     eax, 0Dh
0x1800192c5  mov     rcx, qword ptr [rsp+1F0h+pVar+8]
0x1800192ca  cmp     ax, word ptr [rsp+1F0h+pVar]
0x1800192cf  jnz     loc_1800196BC
0x1800192d5  test    rcx, rcx
0x1800192d8  jz      loc_1800196BC
0x1800192de  mov     rax, [rcx]
0x1800192e1  lea     r8, [rsp+1F0h+var_1A8]
0x1800192e6  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x1800192ed  mov     rax, [rax]
0x1800192f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192f5  mov     ebx, eax
0x1800192f7  test    eax, eax
0x1800192f9  js      loc_18001941E
0x1800192ff  mov     rsi, [rsp+1F0h+var_1A8]
0x180019304  mov     [rsp+1F0h+var_1B8], r13
0x180019309  mov     [rsp+1F0h+ppv], r13
0x18001930e  mov     ebx, 8007000Eh
0x180019313  mov     ecx, 50h ; 'P'; unsigned __int64
0x180019318  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x18001931d  mov     rdi, rax
0x180019320  mov     [rsp+1F0h+var_1B0], rax
0x180019325  test    rax, rax
0x180019328  jz      loc_18001940D
0x18001932e  lea     rax, ??_7CFilterCondition@@6BIFilterCondition@@@; const CFilterCondition::`vftable'{for `IFilterCondition'}
0x180019335  mov     [rdi], rax
0x180019338  lea     rax, ??_7CFilterCondition@@6BIObjectCollection@@@; const CFilterCondition::`vftable'{for `IObjectCollection'}
0x18001933f  mov     [rdi+8], rax
0x180019343  mov     dword ptr [rdi+10h], 1
0x18001934a  mov     [rdi+48h], r13
0x18001934e  lock inc cs:?g_cDllRef@@3JA; long g_cDllRef
0x180019355  test    rdi, rdi
0x180019358  jz      loc_18001940D
0x18001935e  lea     r9, [rsp+1F0h+ppv]; ppv
0x180019363  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18001936a  lea     rdx, ?qit@?1??QueryInterface@CFilterCondition@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x180019371  mov     rcx, rdi; that
0x180019374  call    cs:__imp_QISearch
0x18001937a  mov     ebx, eax
0x18001937c  mov     rcx, rdi; this
0x18001937f  call    ?Release@CFilterCondition@@UEAAKXZ; CFilterCondition::Release(void)
0x180019384  test    ebx, ebx
0x180019386  js      loc_18001940D
0x18001938c  mov     rcx, [rsp+1F0h+ppv]
0x180019391  mov     [rsp+1F0h+var_1B0], r13
0x180019396  mov     rax, [rcx]
0x180019399  lea     r8, [rsp+1F0h+var_1B0]
0x18001939e  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x1800193a5  mov     rax, [rax]
0x1800193a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193ad  mov     ebx, eax
0x1800193af  test    eax, eax
0x1800193b1  js      short loc_1800193FC
0x1800193b3  mov     rcx, [rsp+1F0h+var_1B0]
0x1800193b8  mov     rax, [rcx]
0x1800193bb  mov     rdx, rsi
0x1800193be  mov     rax, [rax+28h]
0x1800193c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193c7  mov     ebx, eax
0x1800193c9  mov     rcx, [rsp+1F0h+var_1B0]
0x1800193ce  mov     rax, [rcx]
0x1800193d1  mov     rax, [rax+10h]
0x1800193d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193da  test    ebx, ebx
0x1800193dc  js      short loc_1800193FC
0x1800193de  mov     rcx, [rsp+1F0h+ppv]
0x1800193e3  mov     rax, [rcx]
0x1800193e6  lea     r8, [rsp+1F0h+var_1B8]
0x1800193eb  lea     rdx, _GUID_fca2857d_1760_4ad3_8c63_c9b602fcbaea
0x1800193f2  mov     rax, [rax]
0x1800193f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193fa  mov     ebx, eax
0x1800193fc  mov     rcx, [rsp+1F0h+ppv]
0x180019401  mov     rax, [rcx]
0x180019404  mov     rax, [rax+10h]
0x180019408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001940d  mov     rcx, [rsp+1F0h+var_1A8]
0x180019412  mov     rax, [rcx]
0x180019415  mov     rax, [rax+10h]
0x180019419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001941e  lea     rcx, [rsp+1F0h+pPropVar]; pvar
0x180019423  call    cs:__imp_PropVariantClear
0x180019429  nop
0x18001942a  mov     eax, 0FFFh
0x18001942f  cmp     word ptr [rsp+1F0h+pVar], ax
0x180019434  jz      loc_1800196DF
0x18001943a  lea     rcx, [rsp+1F0h+pVar]; pvarg
0x18001943f  call    cs:__imp_VariantClear
0x180019445  test    ebx, ebx
0x180019447  js      loc_1800194DE
0x18001944d  mov     rcx, [rsp+1F0h+var_1B8]
0x180019452  mov     rax, [rcx]
0x180019455  lea     rdx, [rbp+0F0h+propkey]
0x180019459  mov     rax, [rax+50h]
0x18001945d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019462  mov     ebx, eax
0x180019464  mov     rcx, [rsp+1F0h+var_1B8]
0x180019469  mov     rdx, [rcx]
0x18001946c  mov     rax, [rdx+10h]
0x180019470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019475  test    ebx, ebx
0x180019477  js      short loc_1800194DE
0x180019479  cmp     [rbp+0F0h+propkey.pid], r13d
0x18001947d  jz      loc_180019674
0x180019483  mov     [rsp+1F0h+ppv], r13
0x180019488  lea     rdx, [rsp+1F0h+ppv]; ppszCanonicalName
0x18001948d  lea     rcx, [rbp+0F0h+propkey]; propkey
0x180019491  call    cs:__imp_PSGetNameFromPropertyKey
0x180019497  test    eax, eax
0x180019499  js      short loc_1800194CE
0x18001949b  mov     r9b, r15b; bool
0x18001949e  mov     r8, [rsp+1F0h+ppv]; unsigned __int16 *
0x1800194a3  lea     rcx, [rbp+0F0h+var_140]; unsigned __int16 *
0x1800194a7  call    ?CreateStackAssocationElement@@YAJPEAG_KPEBG_N@Z; CreateStackAssocationElement(ushort *,unsigned __int64,ushort const *,bool)
0x1800194ac  test    eax, eax
0x1800194ae  js      short loc_1800194CE
0x1800194b0  lea     rax, [rbp+0F0h+var_140]
0x1800194b4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800194b8  inc     rdi
0x1800194bb  cmp     [rax+rdi*2], r13w
0x1800194c0  jnz     short loc_1800194B8
0x1800194c2  mov     [r14], r13
0x1800194c5  lea     rbx, [rdi+1]
0x1800194c9  cmp     rbx, rdi
0x1800194cc  jnb     short loc_180019508
0x1800194ce  mov     rcx, [rsp+1F0h+ppv]; pv
0x1800194d3  mov     [rsp+1F0h+ppv], r13
0x1800194d8  call    cs:__imp_CoTaskMemFree
0x1800194de  mov     rcx, [rbp+0F0h+var_40]
0x1800194e5  xor     rcx, rsp; StackCookie
0x1800194e8  call    __security_check_cookie
0x1800194ed  mov     rbx, [rsp+1F0h+arg_10]
0x1800194f5  add     rsp, 1C0h
0x1800194fc  pop     r15
0x1800194fe  pop     r14
0x180019500  pop     r13
0x180019502  pop     r12
0x180019504  pop     rdi
0x180019505  pop     rsi
0x180019506  pop     rbp
0x180019507  retn
0x180019508  mov     esi, 2
0x18001950d  mov     eax, esi
0x18001950f  mul     rbx
0x180019512  test    rdx, rdx
0x180019515  jnz     short loc_1800194CE
0x180019517  mov     rcx, rax; cb
0x18001951a  call    cs:__imp_CoTaskMemAlloc
0x180019520  mov     r8, rax
0x180019523  mov     [r14], rax
0x180019526  test    rax, rax
0x180019529  jz      short loc_1800194CE
0x18001952b  mov     eax, 7FFFFFFFh
0x180019530  cmp     rbx, rax
0x180019533  ja      loc_1800196F7
0x180019539  cmp     rdi, rax
0x18001953c  jnb     loc_1800196EE
0x180019542  test    rbx, rbx
0x180019545  jz      short loc_180019596
0x180019547  lea     r9, [rbp+0F0h+var_140]
0x18001954b  mov     rdx, rbx
0x18001954e  mov     rax, r8
0x180019551  mov     rcx, r13
0x180019554  test    rdi, rdi
0x180019557  jz      short loc_180019579
0x180019559  movzx   r10d, word ptr [r9]
0x18001955d  test    r10w, r10w
0x180019561  jz      short loc_180019579
0x180019563  add     r9, rsi
0x180019566  mov     [rax], r10w
0x18001956a  add     rax, rsi
0x18001956d  dec     rdi
0x180019570  inc     rcx
0x180019573  sub     rdx, 1; unsigned __int64
0x180019577  jnz     short loc_180019554
0x180019579  lea     r9, [rcx-1]
0x18001957d  test    rdx, rdx
0x180019580  cmovnz  r9, rcx
0x180019584  lea     rcx, [rax-2]
0x180019588  cmovnz  rcx, rax
0x18001958c  mov     [rcx], r13w
0x180019590  jnz     loc_180019697
0x180019596  mov     rcx, [rsp+1F0h+ppv]
0x18001959b  mov     eax, r13d
0x18001959e  cmp     [rcx], r13w
0x1800195a2  jz      loc_1800194CE
0x1800195a8  cmp     word ptr [rcx], 2Eh ; '.'
0x1800195ac  jz      short loc_1800195B3
0x1800195ae  add     rcx, rsi
0x1800195b1  jmp     short loc_18001959E
0x1800195b3  inc     eax
0x1800195b5  cmp     eax, esi
0x1800195b7  jnz     short loc_1800195AE
0x1800195b9  mov     [rcx], r13w
0x1800195bd  mov     r9b, r15b; bool
0x1800195c0  mov     r8, [rsp+1F0h+ppv]; unsigned __int16 *
0x1800195c5  lea     rcx, [rbp+0F0h+var_140]; unsigned __int16 *
0x1800195c9  call    ?CreateStackAssocationElement@@YAJPEAG_KPEBG_N@Z; CreateStackAssocationElement(ushort *,unsigned __int64,ushort const *,bool)
0x1800195ce  test    eax, eax
0x1800195d0  js      loc_1800194CE
0x1800195d6  mov     r9, r12
0x1800195d9  lea     r8, [rbp+0F0h+var_140]
0x1800195dd  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800195e2  jmp     loc_1800194CE
0x1800195e7  mov     [rsp+1F0h+var_1B8], r13
0x1800195ec  lea     r8, [rsp+1F0h+var_1B8]
0x1800195f1  lea     rdx, _GUID_e2ba9629_b18f_4e3a_aba5_42d879e79c80
0x1800195f8  lea     rcx, [rbp+0F0h+var_158]
0x1800195fc  call    cs:__imp_SHGetFolderTypeDescription
0x180019602  test    eax, eax
0x180019604  js      short loc_180019658
0x180019606  mov     [rsp+1F0h+ppv], r13
0x18001960b  mov     rcx, [rsp+1F0h+var_1B8]
0x180019610  mov     rax, [rcx]
0x180019613  lea     rdx, [rsp+1F0h+ppv]
0x180019618  mov     rax, [rax+50h]
0x18001961c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019621  test    eax, eax
0x180019623  js      short loc_180019647
0x180019625  mov     r9b, r15b; bool
0x180019628  mov     r8, [rsp+1F0h+ppv]; unsigned __int16 *
0x18001962d  lea     rcx, [rbp+0F0h+var_140]; unsigned __int16 *
0x180019631  call    ?CreateStackAssocationElement@@YAJPEAG_KPEBG_N@Z; CreateStackAssocationElement(ushort *,unsigned __int64,ushort const *,bool)
0x180019636  test    eax, eax
0x180019638  js      short loc_180019647
0x18001963a  mov     r9, rbx
0x18001963d  lea     r8, [rbp+0F0h+var_140]
0x180019641  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180019646  nop
0x180019647  mov     rcx, [rsp+1F0h+ppv]; pv
0x18001964c  mov     [rsp+1F0h+ppv], r13
0x180019651  call    cs:__imp_CoTaskMemFree
0x180019657  nop
0x180019658  mov     rcx, [rsp+1F0h+var_1B8]
0x18001965d  test    rcx, rcx
0x180019660  jz      short loc_18001966F
0x180019662  mov     rax, [rcx]
0x180019665  mov     rax, [rax+10h]
0x180019669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001966e  nop
  ... truncated ...
```
