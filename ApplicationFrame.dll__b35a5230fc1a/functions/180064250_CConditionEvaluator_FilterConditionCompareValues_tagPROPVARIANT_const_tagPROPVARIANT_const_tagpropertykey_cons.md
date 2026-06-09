# CConditionEvaluator::FilterConditionCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,int,int,IPropertyInfoProvider *,int,IPropertyChangeArray *,BITSSET,ushort *,ulong,int *,int *)

- ea: `0x180064250`
- end: `0x180064451`
- name: `?FilterConditionCompareValues@CConditionEvaluator@@QEAAJAEBUtagPROPVARIANT@@0AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@HHPEAUIPropertyInfoProvider@@HPEAUIPropertyChangeArray@@W4BITSSET@@PEAGKPEAH7@Z`
- size: `513`
- prototype: `int __high(const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct _tagpropertykey *, enum tagCONDITION_OPERATION, int, int, struct IPropertyInfoProvider *, int, struct IPropertyChangeArray *, enum BITSSET, unsigned __int16 *, unsigned int, int *, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180063f7c`
- `0x1800681f8`

## callees

- `0x1800632f8`
- `0x180064250`
- `0x180064db8`
- `0x1800663c8`
- `0x1800672b8`
- `0x180069e60`
- `0x180072010`

## import_xrefs

- `PROPSYS!PSCreateSimplePropertyChange` at `0x180064402`
- `PROPSYS!PSCreateSimplePropertyChange` at `0x180064402`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800642ef`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800642ef`

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
0x180064250  push    rbx
0x180064252  push    rbp
0x180064253  push    rsi
0x180064254  push    rdi
0x180064255  push    r12
0x180064257  push    r14
0x180064259  push    r15
0x18006425b  sub     rsp, 70h
0x18006425f  mov     esi, [rsp+0A8h+arg_20]
0x180064266  xor     r12d, r12d
0x180064269  mov     r15, r9
0x18006426c  mov     rbx, r8
0x18006426f  mov     rbp, rdx
0x180064272  test    esi, esi
0x180064274  jnz     short loc_18006427E
0x180064276  lea     ebx, [rsi+1]
0x180064279  jmp     loc_180064440
0x18006427e  lea     eax, [rsi-7]
0x180064281  cmp     eax, 6
0x180064284  ja      short loc_1800642DB
0x180064286  mov     rax, [rsp+0A8h+arg_68]
0x18006428e  mov     r9d, esi; enum tagCONDITION_OPERATION
0x180064291  mov     [rsp+0A8h+var_58], rax; int *
0x180064296  mov     eax, [rsp+0A8h+arg_60]
0x18006429d  mov     [rsp+0A8h+Locale], eax; Locale
0x1800642a1  mov     eax, [rsp+0A8h+arg_40]
0x1800642a8  mov     [rsp+0A8h+var_68], eax; int
0x1800642ac  mov     rax, [rsp+0A8h+arg_38]
0x1800642b4  mov     [rsp+0A8h+var_70], rax; struct IPropertyInfoProvider *
0x1800642b9  mov     eax, [rsp+0A8h+arg_30]
0x1800642c0  mov     [rsp+0A8h+var_78], eax; int
0x1800642c4  mov     eax, [rsp+0A8h+arg_28]
0x1800642cb  mov     [rsp+0A8h+var_80], eax; int
0x1800642cf  mov     [rsp+0A8h+ppv], r15; propkey
0x1800642d4  call    ?LikeOpCompareValues@CConditionEvaluator@@QEAAJAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@AEBU_tagpropertykey@@HHPEAUIPropertyInfoProvider@@HKPEAH@Z; CConditionEvaluator::LikeOpCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,_tagpropertykey const &,int,int,IPropertyInfoProvider *,int,ulong,int *)
0x1800642d9  jmp     short loc_18006434B
0x1800642db  mov     rcx, [rsp+0A8h+pszStr1]; pszStr1
0x1800642e3  test    rcx, rcx
0x1800642e6  jz      short loc_18006431E
0x1800642e8  lea     rdx, pszStr2; "System.StructuredQueryType.SortKeyDescr"...
0x1800642ef  call    cs:__imp_StrCmpICW
0x1800642f5  test    eax, eax
0x1800642f7  jnz     short loc_18006431E
0x1800642f9  mov     rax, [rsp+0A8h+arg_68]
0x180064301  mov     r8d, esi; enum tagCONDITION_OPERATION
0x180064304  mov     r9d, [rsp+0A8h+arg_40]; int
0x18006430c  mov     rdx, rbx; struct tagPROPVARIANT *
0x18006430f  mov     rcx, rbp; struct tagPROPVARIANT *
0x180064312  mov     [rsp+0A8h+ppv], rax; int *
0x180064317  call    ?SortKeyCompareValues@@YAJAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@HPEAH@Z; SortKeyCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,int,int *)
0x18006431c  jmp     short loc_18006434B
0x18006431e  mov     r8d, [rsp+0A8h+arg_50]
0x180064326  mov     rdx, rbx; propvar1
0x180064329  mov     r9d, [rsp+0A8h+arg_40]; int
0x180064331  mov     rcx, rbp; propvar2
0x180064334  test    r8d, r8d
0x180064337  jz      short loc_180064352
0x180064339  mov     rax, [rsp+0A8h+arg_68]
0x180064341  mov     [rsp+0A8h+ppv], rax
0x180064346  call    ?BitwiseCompareValues@@YAJAEBUtagPROPVARIANT@@0W4BITSSET@@HPEAH@Z; BitwiseCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,BITSSET,int,int *)
0x18006434b  mov     ebx, eax
0x18006434d  jmp     loc_180064440
0x180064352  mov     rdi, [rsp+0A8h+arg_68]
0x18006435a  mov     r8d, esi; enum tagCONDITION_OPERATION
0x18006435d  mov     [rsp+0A8h+ppv], rdi; int *
0x180064362  call    ?_SimpleOpCompareValues@@YAJAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@HPEAH@Z; _SimpleOpCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,int,int *)
0x180064367  mov     ebx, eax
0x180064369  test    eax, eax
0x18006436b  js      loc_180064440
0x180064371  cmp     [rdi], r12d
0x180064374  jnz     loc_180064440
0x18006437a  mov     r14, [rsp+0A8h+arg_70]
0x180064382  test    r14, r14
0x180064385  jz      loc_180064440
0x18006438b  mov     r12, [rsp+0A8h+arg_48]
0x180064393  test    r12, r12
0x180064396  jz      loc_180064440
0x18006439c  mov     edx, 2; enum PROPDESC_TYPE_FLAGS
0x1800643a1  mov     rcx, r15; struct _tagpropertykey *
0x1800643a4  call    ?GetPropertyTypeFlags@@YA?AW4PROPDESC_TYPE_FLAGS@@AEBU_tagpropertykey@@W41@@Z; GetPropertyTypeFlags(_tagpropertykey const &,PROPDESC_TYPE_FLAGS)
0x1800643a9  test    al, 2
0x1800643ab  jnz     loc_180064440
0x1800643b1  cmp     [rsp+0A8h+arg_40], 0
0x1800643b9  mov     edi, 1
0x1800643be  jz      short loc_1800643C7
0x1800643c0  cmp     esi, 2
0x1800643c3  jz      short loc_1800643CB
0x1800643c5  jmp     short loc_180064440
0x1800643c7  cmp     esi, edi
0x1800643c9  jnz     short loc_180064440
0x1800643cb  xor     esi, esi
0x1800643cd  mov     edx, edi; enum PROPDESC_TYPE_FLAGS
0x1800643cf  mov     rcx, r15; struct _tagpropertykey *
0x1800643d2  mov     [rsp+0A8h+var_48], rsi
0x1800643d7  call    ?GetPropertyTypeFlags@@YA?AW4PROPDESC_TYPE_FLAGS@@AEBU_tagpropertykey@@W41@@Z; GetPropertyTypeFlags(_tagpropertykey const &,PROPDESC_TYPE_FLAGS)
0x1800643dc  test    dil, al
0x1800643df  jz      short loc_1800643E7
0x1800643e1  cmp     [rbp+0], si
0x1800643e5  jnz     short loc_1800643E9
0x1800643e7  mov     edi, esi
0x1800643e9  lea     rax, [rsp+0A8h+var_48]
0x1800643ee  mov     r8, rbp; propvar
0x1800643f1  lea     r9, _GUID_f917bc8a_1bba_4478_a245_1bde03eb9431; riid
0x1800643f8  mov     [rsp+0A8h+ppv], rax; ppv
0x1800643fd  mov     rdx, r15; key
0x180064400  mov     ecx, edi; flags
0x180064402  call    cs:__imp_PSCreateSimplePropertyChange
0x180064408  mov     ebx, eax
0x18006440a  test    eax, eax
0x18006440c  js      short loc_180064436
0x18006440e  mov     rax, [r12]
0x180064412  mov     rcx, r12
0x180064415  mov     rdx, [rsp+0A8h+var_48]
0x18006441a  mov     rax, [rax+30h]
0x18006441e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064423  mov     rcx, [rsp+0A8h+var_48]
0x180064428  mov     ebx, eax
0x18006442a  mov     rax, [rcx]
0x18006442d  mov     rax, [rax+10h]
0x180064431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064436  mov     eax, ebx
0x180064438  not     eax
0x18006443a  shr     eax, 1Fh
0x18006443d  mov     [r14], eax
0x180064440  mov     eax, ebx
0x180064442  add     rsp, 70h
0x180064446  pop     r15
0x180064448  pop     r14
0x18006444a  pop     r12
0x18006444c  pop     rdi
0x18006444d  pop     rsi
0x18006444e  pop     rbp
0x18006444f  pop     rbx
0x180064450  retn
```
