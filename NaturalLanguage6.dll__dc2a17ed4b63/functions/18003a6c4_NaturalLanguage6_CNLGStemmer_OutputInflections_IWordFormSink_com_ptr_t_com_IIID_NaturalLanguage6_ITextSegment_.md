# NaturalLanguage6::CNLGStemmer::OutputInflections(IWordFormSink *,_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>)

- ea: `0x18003a6c4`
- end: `0x18003a84e`
- name: `?OutputInflections@CNLGStemmer@NaturalLanguage6@@AEAAJPEAUIWordFormSink@@V?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@@Z`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005d41c`

## callees

- `0x180005160`
- `0x180005190`
- `0x180008460`
- `0x18002b720`
- `0x18002bf50`
- `0x18003a6c4`
- `0x18003a854`
- `0x18005d3b8`
- `0x18009e300`
- `0x1800b0010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003a736`
- `OLEAUT32!__imp_VariantInit` at `0x18003a736`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NaturalLanguage6::CNLGStemmer::OutputInflections(__int64 a1, int a2, __int64 *a3)
{
  struct IUnknown *v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  int v9; // ebx
  signed __int64 v10; // r9
  int v12; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v14; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+78h] [rbp-88h]
  __int64 *v17; // [rsp+80h] [rbp-80h]
  _BYTE v18[8]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v19; // [rsp+90h] [rbp-70h] BYREF
  wchar_t pszDest[64]; // [rsp+A0h] [rbp-60h] BYREF

  v16 = -2;
  v17 = a3;
  v6 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(a3);
  NaturalLanguage6::ITextSegment::GetExpansions(v6);
  v7 = _com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(a3);
  NaturalLanguage6::ITextSegment::GetRange(v7, v18);
  if ( v13 )
  {
    VariantInit(&pvarg);
    v12 = 0;
    do
    {
      v8 = _com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(&v13);
      v9 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *, int *))(*(_QWORD *)v8 + 24LL))(
             v8,
             1,
             &pvarg,
             &v12);
      if ( v9 < 0 )
        break;
      if ( !v12 )
        break;
      v14 = 0;
      v9 = StringCchPrintfExW(pszDest, 0x40u, &v14, &v19, 0x800u, L"%s", pvarg.llVal);
      if ( v9 < 0 )
        break;
      v10 = v14 - pszDest;
      if ( (int)v10 > 0 && (unsigned int)v10 < *(_DWORD *)(a1 + 20) )
      {
        v9 = NaturalLanguage6::CNLGStemmer::PutCheckedWord(
               a1,
               a2,
               (unsigned int) IWordFormSink::`vcall'{24,{flat}},
               v10,
               (__int64)pszDest);
        if ( v9 < 0 )
          break;
      }
    }
    while ( v12 );
    _variant_t::~_variant_t(&pvarg);
  }
  else
  {
    v9 = 0;
  }
  _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v13);
  _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(a3);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003a6c4  push    rbp
0x18003a6c6  push    rbx
0x18003a6c7  push    rsi
0x18003a6c8  push    rdi
0x18003a6c9  push    r14
0x18003a6cb  lea     rbp, [rsp-30h]
0x18003a6d0  sub     rsp, 130h
0x18003a6d7  mov     [rsp+150h+var_D8], 0FFFFFFFFFFFFFFFEh
0x18003a6e0  mov     rax, cs:__security_cookie
0x18003a6e7  xor     rax, rsp
0x18003a6ea  mov     [rbp+50h+var_30], rax
0x18003a6ee  mov     rdi, r8
0x18003a6f1  mov     r14, rdx
0x18003a6f4  mov     rsi, rcx
0x18003a6f7  mov     [rbp+50h+var_D0], r8
0x18003a6fb  mov     rcx, r8
0x18003a6fe  call    ??C?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@QEBAPEAUITextSegment@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(void)
0x18003a703  lea     rdx, [rsp+150h+var_108]
0x18003a708  mov     rcx, rax; struct IUnknown *
0x18003a70b  call    ?GetExpansions@ITextSegment@NaturalLanguage6@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIEnumVARIANT@@$1?_GUID_00020404_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@XZ; NaturalLanguage6::ITextSegment::GetExpansions(void)
0x18003a710  nop
0x18003a711  mov     rcx, rdi
0x18003a714  call    ??C?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@QEBAPEAUITextSegment@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(void)
0x18003a719  lea     rdx, [rbp+50h+var_C8]
0x18003a71d  mov     rcx, rax
0x18003a720  call    ?GetRange@ITextSegment@NaturalLanguage6@@QEAA?AUSTextRange@2@XZ; NaturalLanguage6::ITextSegment::GetRange(void)
0x18003a725  cmp     [rsp+150h+var_108], 0
0x18003a72b  jz      loc_18003A81D
0x18003a731  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18003a736  call    cs:__imp_VariantInit
0x18003a73c  nop
0x18003a73d  mov     [rsp+150h+var_110], 0
0x18003a745  lea     rcx, [rsp+150h+var_108]
0x18003a74a  call    ??C?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@QEBAPEAUITextSegment@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(void)
0x18003a74f  mov     r10, rax
0x18003a752  mov     rcx, [rax]
0x18003a755  mov     rax, [rcx+18h]
0x18003a759  lea     r9, [rsp+150h+var_110]
0x18003a75e  lea     r8, [rsp+150h+pvarg]
0x18003a763  mov     edx, 1
0x18003a768  mov     rcx, r10
0x18003a76b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a770  mov     ebx, eax
0x18003a772  test    eax, eax
0x18003a774  js      loc_18003A811
0x18003a77a  mov     eax, [rsp+150h+var_110]
0x18003a77e  test    eax, eax
0x18003a780  jz      loc_18003A811
0x18003a786  mov     [rsp+150h+var_100], 0
0x18003a78f  mov     rax, qword ptr [rsp+150h+pvarg+8]
0x18003a794  mov     [rsp+150h+var_120], rax
0x18003a799  lea     rax, aS_0; "%s"
0x18003a7a0  mov     [rsp+150h+var_128], rax; unsigned __int16 *
0x18003a7a5  mov     [rsp+150h+var_130], 800h; unsigned int
0x18003a7ad  lea     r9, [rbp+50h+var_C0]; unsigned __int64 *
0x18003a7b1  lea     r8, [rsp+150h+var_100]; unsigned __int16 **
0x18003a7b6  mov     edx, 40h ; '@'; unsigned __int64
0x18003a7bb  lea     rcx, [rbp+50h+pszDest]; pszDest
0x18003a7bf  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18003a7c4  mov     ebx, eax
0x18003a7c6  test    eax, eax
0x18003a7c8  js      short loc_18003A811
0x18003a7ca  lea     rax, [rbp+50h+pszDest]
0x18003a7ce  mov     r9, [rsp+150h+var_100]
0x18003a7d3  sub     r9, rax
0x18003a7d6  sar     r9, 1
0x18003a7d9  test    r9d, r9d
0x18003a7dc  jle     short loc_18003A805
0x18003a7de  cmp     r9d, [rsi+14h]
0x18003a7e2  jnb     short loc_18003A805
0x18003a7e4  lea     rax, [rbp+50h+pszDest]
0x18003a7e8  mov     qword ptr [rsp+150h+var_130], rax
0x18003a7ed  lea     r8, ??_9IWordFormSink@@$BBI@AA; [thunk]: IWordFormSink::`vcall'{24,{flat}}
0x18003a7f4  mov     rdx, r14
0x18003a7f7  mov     rcx, rsi
0x18003a7fa  call    ?PutCheckedWord@CNLGStemmer@NaturalLanguage6@@AEBAJPEAUIWordFormSink@@P83@EAAJPEBGK@ZK1KK@Z; NaturalLanguage6::CNLGStemmer::PutCheckedWord(IWordFormSink *,long (IWordFormSink::*)(ushort const *,ulong),ulong,ushort const *,ulong,ulong)
0x18003a7ff  mov     ebx, eax
0x18003a801  test    eax, eax
0x18003a803  js      short loc_18003A811
0x18003a805  mov     eax, [rsp+150h+var_110]
0x18003a809  test    eax, eax
0x18003a80b  jnz     loc_18003A745
0x18003a811  lea     rcx, [rsp+150h+pvarg]; this
0x18003a816  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003a81b  jmp     short loc_18003A81F
0x18003a81d  xor     ebx, ebx
0x18003a81f  lea     rcx, [rsp+150h+var_108]
0x18003a824  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18003a829  nop
0x18003a82a  mov     rcx, rdi
0x18003a82d  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18003a832  mov     eax, ebx
0x18003a834  mov     rcx, [rbp+50h+var_30]
0x18003a838  xor     rcx, rsp; StackCookie
0x18003a83b  call    __security_check_cookie
0x18003a840  add     rsp, 130h
0x18003a847  pop     r14
0x18003a849  pop     rdi
0x18003a84a  pop     rsi
0x18003a84b  pop     rbx
0x18003a84c  pop     rbp
0x18003a84d  retn
```
