# CConditionEvaluator::FilterConditionCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,int,int,IPropertyInfoProvider *,int,IPropertyChangeArray *,BITSSET,ushort *,ulong,int *,int *)

- ea: `0x180045360`
- end: `0x180045561`
- name: `?FilterConditionCompareValues@CConditionEvaluator@@QEAAJAEBUtagPROPVARIANT@@0AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@HHPEAUIPropertyInfoProvider@@HPEAUIPropertyChangeArray@@W4BITSSET@@PEAGKPEAH7@Z`
- size: `513`
- prototype: `int __high(const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct _tagpropertykey *, enum tagCONDITION_OPERATION, int, int, struct IPropertyInfoProvider *, int, struct IPropertyChangeArray *, enum BITSSET, unsigned __int16 *, unsigned int, int *, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004508c`
- `0x180049414`

## callees

- `0x1800444d8`
- `0x180045360`
- `0x180046068`
- `0x1800477e8`
- `0x1800485b8`
- `0x18004b350`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800453ff`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800453ff`
- `PROPSYS!PSCreateSimplePropertyChange` at `0x180045512`
- `PROPSYS!PSCreateSimplePropertyChange` at `0x180045512`

## pseudocode

```c
__int64 __fastcall CConditionEvaluator::FilterConditionCompareValues(
        CConditionEvaluator *a1,
        PROPVARIANT *a2,
        PROPVARIANT *a3,
        struct _tagpropertykey *a4,
        enum tagCONDITION_OPERATION a5,
        int a6,
        int a7,
        struct IPropertyInfoProvider *a8,
        unsigned int a9,
        __int64 a10,
        unsigned int a11,
        const WCHAR *pszStr1,
        LCID Locale,
        int *a14,
        _DWORD *a15)
{
  HRESULT v18; // ebx
  PKA_FLAGS v20; // edi
  void *ppv; // [rsp+60h] [rbp-48h] BYREF

  if ( a5 == COP_IMPLICIT )
    return 1;
  if ( (unsigned int)(a5 - 7) <= 6 )
    return (unsigned int)CConditionEvaluator::LikeOpCompareValues(a1, a2, a3, a5, a4, a6, a7, a8, a9, Locale, a14);
  if ( pszStr1 && !StrCmpICW(pszStr1, L"System.StructuredQueryType.SortKeyDescription") )
    return (unsigned int)SortKeyCompareValues(
                           (const struct tagPROPVARIANT *)a2,
                           (const struct tagPROPVARIANT *)a3,
                           a5,
                           a9,
                           a14);
  if ( a11 )
    return (unsigned int)BitwiseCompareValues(a2, a3, a11, a9, a14);
  v18 = _SimpleOpCompareValues(a2, a3, a5, a9, a14);
  if ( v18 >= 0 && !*a14 && a15 && a10 && (GetPropertyTypeFlags(a4, PDTF_ISINNATE) & 2) == 0 )
  {
    v20 = PKA_APPEND;
    if ( a9 )
    {
      if ( a5 != COP_NOTEQUAL )
        return (unsigned int)v18;
    }
    else if ( a5 != COP_EQUAL )
    {
      return (unsigned int)v18;
    }
    ppv = 0;
    if ( (GetPropertyTypeFlags(a4, PDTF_MULTIPLEVALUES) & 1) == 0 || !*(_WORD *)a2 )
      v20 = PKA_SET;
    v18 = PSCreateSimplePropertyChange(v20, a4, a2, &GUID_f917bc8a_1bba_4478_a245_1bde03eb9431, &ppv);
    if ( v18 >= 0 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)a10 + 48LL))(a10, ppv);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    *a15 = v18 >= 0;
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180045360  push    rbx
0x180045362  push    rbp
0x180045363  push    rsi
0x180045364  push    rdi
0x180045365  push    r12
0x180045367  push    r14
0x180045369  push    r15
0x18004536b  sub     rsp, 70h
0x18004536f  mov     esi, [rsp+0A8h+arg_20]
0x180045376  xor     r12d, r12d
0x180045379  mov     r15, r9
0x18004537c  mov     rbx, r8
0x18004537f  mov     rbp, rdx
0x180045382  test    esi, esi
0x180045384  jnz     short loc_18004538E
0x180045386  lea     ebx, [rsi+1]
0x180045389  jmp     loc_180045550
0x18004538e  lea     eax, [rsi-7]
0x180045391  cmp     eax, 6
0x180045394  ja      short loc_1800453EB
0x180045396  mov     rax, [rsp+0A8h+arg_68]
0x18004539e  mov     r9d, esi; enum tagCONDITION_OPERATION
0x1800453a1  mov     [rsp+0A8h+var_58], rax; int *
0x1800453a6  mov     eax, [rsp+0A8h+arg_60]
0x1800453ad  mov     [rsp+0A8h+Locale], eax; Locale
0x1800453b1  mov     eax, [rsp+0A8h+arg_40]
0x1800453b8  mov     [rsp+0A8h+var_68], eax; int
0x1800453bc  mov     rax, [rsp+0A8h+arg_38]
0x1800453c4  mov     [rsp+0A8h+var_70], rax; struct IPropertyInfoProvider *
0x1800453c9  mov     eax, [rsp+0A8h+arg_30]
0x1800453d0  mov     [rsp+0A8h+var_78], eax; int
0x1800453d4  mov     eax, [rsp+0A8h+arg_28]
0x1800453db  mov     [rsp+0A8h+var_80], eax; int
0x1800453df  mov     [rsp+0A8h+ppv], r15; propkey
0x1800453e4  call    ?LikeOpCompareValues@CConditionEvaluator@@QEAAJAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@AEBU_tagpropertykey@@HHPEAUIPropertyInfoProvider@@HKPEAH@Z; CConditionEvaluator::LikeOpCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,_tagpropertykey const &,int,int,IPropertyInfoProvider *,int,ulong,int *)
0x1800453e9  jmp     short loc_18004545B
0x1800453eb  mov     rcx, [rsp+0A8h+pszStr1]; pszStr1
0x1800453f3  test    rcx, rcx
0x1800453f6  jz      short loc_18004542E
0x1800453f8  lea     rdx, pszStr2; "System.StructuredQueryType.SortKeyDescr"...
0x1800453ff  call    cs:__imp_StrCmpICW
0x180045405  test    eax, eax
0x180045407  jnz     short loc_18004542E
0x180045409  mov     rax, [rsp+0A8h+arg_68]
0x180045411  mov     r8d, esi; enum tagCONDITION_OPERATION
0x180045414  mov     r9d, [rsp+0A8h+arg_40]; int
0x18004541c  mov     rdx, rbx; struct tagPROPVARIANT *
0x18004541f  mov     rcx, rbp; struct tagPROPVARIANT *
0x180045422  mov     [rsp+0A8h+ppv], rax; int *
0x180045427  call    ?SortKeyCompareValues@@YAJAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@HPEAH@Z; SortKeyCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,int,int *)
0x18004542c  jmp     short loc_18004545B
0x18004542e  mov     r8d, [rsp+0A8h+arg_50]
0x180045436  mov     rdx, rbx; propvar1
0x180045439  mov     r9d, [rsp+0A8h+arg_40]; int
0x180045441  mov     rcx, rbp; propvar2
0x180045444  test    r8d, r8d
0x180045447  jz      short loc_180045462
0x180045449  mov     rax, [rsp+0A8h+arg_68]
0x180045451  mov     [rsp+0A8h+ppv], rax
0x180045456  call    ?BitwiseCompareValues@@YAJAEBUtagPROPVARIANT@@0W4BITSSET@@HPEAH@Z; BitwiseCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,BITSSET,int,int *)
0x18004545b  mov     ebx, eax
0x18004545d  jmp     loc_180045550
0x180045462  mov     rdi, [rsp+0A8h+arg_68]
0x18004546a  mov     r8d, esi; enum tagCONDITION_OPERATION
0x18004546d  mov     [rsp+0A8h+ppv], rdi; int *
0x180045472  call    ?_SimpleOpCompareValues@@YAJAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@HPEAH@Z; _SimpleOpCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,int,int *)
0x180045477  mov     ebx, eax
0x180045479  test    eax, eax
0x18004547b  js      loc_180045550
0x180045481  cmp     [rdi], r12d
0x180045484  jnz     loc_180045550
0x18004548a  mov     r14, [rsp+0A8h+arg_70]
0x180045492  test    r14, r14
0x180045495  jz      loc_180045550
0x18004549b  mov     r12, [rsp+0A8h+arg_48]
0x1800454a3  test    r12, r12
0x1800454a6  jz      loc_180045550
0x1800454ac  mov     edx, 2; enum PROPDESC_TYPE_FLAGS
0x1800454b1  mov     rcx, r15; struct _tagpropertykey *
0x1800454b4  call    ?GetPropertyTypeFlags@@YA?AW4PROPDESC_TYPE_FLAGS@@AEBU_tagpropertykey@@W41@@Z; GetPropertyTypeFlags(_tagpropertykey const &,PROPDESC_TYPE_FLAGS)
0x1800454b9  test    al, 2
0x1800454bb  jnz     loc_180045550
0x1800454c1  cmp     [rsp+0A8h+arg_40], 0
0x1800454c9  mov     edi, 1
0x1800454ce  jz      short loc_1800454D7
0x1800454d0  cmp     esi, 2
0x1800454d3  jz      short loc_1800454DB
0x1800454d5  jmp     short loc_180045550
0x1800454d7  cmp     esi, edi
0x1800454d9  jnz     short loc_180045550
0x1800454db  xor     esi, esi
0x1800454dd  mov     edx, edi; enum PROPDESC_TYPE_FLAGS
0x1800454df  mov     rcx, r15; struct _tagpropertykey *
0x1800454e2  mov     [rsp+0A8h+var_48], rsi
0x1800454e7  call    ?GetPropertyTypeFlags@@YA?AW4PROPDESC_TYPE_FLAGS@@AEBU_tagpropertykey@@W41@@Z; GetPropertyTypeFlags(_tagpropertykey const &,PROPDESC_TYPE_FLAGS)
0x1800454ec  test    dil, al
0x1800454ef  jz      short loc_1800454F7
0x1800454f1  cmp     [rbp+0], si
0x1800454f5  jnz     short loc_1800454F9
0x1800454f7  mov     edi, esi
0x1800454f9  lea     rax, [rsp+0A8h+var_48]
0x1800454fe  mov     r8, rbp; propvar
0x180045501  lea     r9, _GUID_f917bc8a_1bba_4478_a245_1bde03eb9431; riid
0x180045508  mov     [rsp+0A8h+ppv], rax; ppv
0x18004550d  mov     rdx, r15; key
0x180045510  mov     ecx, edi; flags
0x180045512  call    cs:__imp_PSCreateSimplePropertyChange
0x180045518  mov     ebx, eax
0x18004551a  test    eax, eax
0x18004551c  js      short loc_180045546
0x18004551e  mov     rax, [r12]
0x180045522  mov     rcx, r12
0x180045525  mov     rdx, [rsp+0A8h+var_48]
0x18004552a  mov     rax, [rax+30h]
0x18004552e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045533  mov     rcx, [rsp+0A8h+var_48]
0x180045538  mov     ebx, eax
0x18004553a  mov     rax, [rcx]
0x18004553d  mov     rax, [rax+10h]
0x180045541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045546  mov     eax, ebx
0x180045548  not     eax
0x18004554a  shr     eax, 1Fh
0x18004554d  mov     [r14], eax
0x180045550  mov     eax, ebx
0x180045552  add     rsp, 70h
0x180045556  pop     r15
0x180045558  pop     r14
0x18004555a  pop     r12
0x18004555c  pop     rdi
0x18004555d  pop     rsi
0x18004555e  pop     rbp
0x18004555f  pop     rbx
0x180045560  retn
```
