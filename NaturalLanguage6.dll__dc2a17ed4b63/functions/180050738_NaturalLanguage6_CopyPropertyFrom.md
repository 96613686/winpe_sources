# NaturalLanguage6::CopyPropertyFrom

- ea: `0x180050738`
- end: `0x180050b61`
- name: `NaturalLanguage6::CopyPropertyFrom`
- size: `1065`
- prototype: `__int64 __fastcall(int, int, int, int, NaturalLanguage6::Sentence *)`
- caller_count: `5`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x180050738`
- `0x180057d00`
- `0x180058050`
- `0x1800581c0`
- `0x180058330`

## callees

- `0x1800036c4`
- `0x18000381c`
- `0x180005160`
- `0x180005190`
- `0x180024954`
- `0x1800268f0`
- `0x18002cea0`
- `0x180034ed4`
- `0x180038898`
- `0x18003dfcc`
- `0x180041974`
- `0x18004d828`
- `0x18004de00`
- `0x18004df50`
- `0x18004e3b8`
- `0x18004e40c`
- `0x180050738`
- `0x1800525b4`
- `0x180052900`
- `0x1800529e8`
- `0x180054f00`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180050762`
- `OLEAUT32!__imp_VariantInit` at `0x180050762`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
unsigned __int64 __fastcall NaturalLanguage6::CopyPropertyFrom(
        __int64 a1,
        VARIANTARG *a2,
        int a3,
        char a4,
        NaturalLanguage6::Sentence *a5)
{
  __int64 v9; // rdx
  int v10; // r9d
  unsigned __int64 result; // rax
  unsigned int v12; // r10d
  unsigned int v13; // r10d
  unsigned int v14; // r10d
  unsigned int v15; // r10d
  unsigned int v16; // r10d
  unsigned int v17; // r10d
  unsigned int v18; // r10d
  int v19; // eax
  void *v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r14
  struct NaturalLanguage6::ITextSegment *v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rdi
  LSP::SimpleDateTimeEnum *v26; // rax
  __int64 v27; // r15
  _QWORD *v28; // r14
  __int64 i; // r13
  struct NaturalLanguage6::ITextSegment *v30; // rbx
  __int64 v31; // rax
  bool v32; // r8
  VARIANTARG *v33; // r9
  __int64 v34; // r8
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // rdx
  unsigned int v39; // r10d
  unsigned int v40; // r10d
  unsigned int v41; // r10d
  unsigned int v42; // r10d
  unsigned int v43; // r10d
  __int64 v44; // rdx
  __int64 v45; // rcx
  LSP::SimpleDateTimeEnum *v46; // rax
  __int64 v47; // r8
  LSP::SimpleDateTimeEnum *v48; // rax
  unsigned int v49; // r8d
  __int64 v50; // rdx
  __int64 v51; // rax
  __int64 v52; // rax
  int v53; // [rsp+20h] [rbp-78h]
  _QWORD *v54; // [rsp+30h] [rbp-68h] BYREF
  VARIANTARG *v55; // [rsp+38h] [rbp-60h]
  _QWORD *v56; // [rsp+40h] [rbp-58h]
  __int64 v57; // [rsp+48h] [rbp-50h]
  VARIANTARG v58[3]; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  LSP::SimpleDateTimeEnum *v60; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v61; // [rsp+A8h] [rbp+10h] BYREF

  v57 = -2;
  VariantInit(a2);
  result = (unsigned __int64)*(unsigned int *)(a1 + 8) >> 24;
  v12 = (unsigned __int8)HIBYTE(*(_DWORD *)(a1 + 8));
  if ( v12 > 9 )
  {
    v39 = v12 - 10;
    if ( v39 )
    {
      v40 = v39 - 2;
      if ( !v40 )
      {
        v25 = 0;
        if ( !*(_QWORD *)(a1 + 16) )
          return result;
        v48 = (LSP::SimpleDateTimeEnum *)operator new(0x40u);
        v60 = v48;
        if ( v48 )
          v25 = LSP::SimpleDateTimeEnum::SimpleDateTimeEnum(
                  v48,
                  *(const struct SimpleTimeRepresentation **)(a1 + 16),
                  v49);
        goto LABEL_57;
      }
      v41 = v40 - 2;
      if ( !v41 )
      {
LABEL_54:
        v25 = 0;
        if ( !*(_QWORD *)(a1 + 16) )
          return result;
        v46 = (LSP::SimpleDateTimeEnum *)operator new(0x20u);
        v60 = v46;
        if ( v46 )
        {
          LOBYTE(v47) = a4 ^ 1;
          v25 = LSP::EnumVARIANTOnNameArray::EnumVARIANTOnNameArray(v46, *(_QWORD *)(a1 + 16), v47);
        }
LABEL_57:
        v44 = v25;
        return _variant_t::operator=(a2, v44);
      }
      v42 = v41 - 1;
      if ( v42 )
      {
        v43 = v42 - 1;
        if ( v43 )
        {
          if ( v43 != 1 )
            return result;
          v44 = *(_QWORD *)(a1 + 16);
          if ( !v44 )
            return result;
          return _variant_t::operator=(a2, v44);
        }
      }
      v45 = *(_QWORD *)(a1 + 16);
      if ( v45 )
      {
        LOBYTE(v10) = a4;
        return NaturalLanguage6::CopyPropertyFrom(*(_QWORD *)(v45 + 8), (int)a2, a3, v10, a5);
      }
    }
    else
    {
      v50 = *(_QWORD *)(a1 + 16);
      if ( v50 )
      {
        if ( a4 )
        {
          a2->vt = 16402;
          result = *(_QWORD *)(a1 + 16);
          a2->llVal = result;
        }
        else
        {
          return _variant_t::operator=(a2, v50);
        }
      }
    }
  }
  else
  {
    if ( v12 == 9 )
    {
      LOBYTE(v9) = *(_QWORD *)(a1 + 16) != 0;
      return _variant_t::operator=(a2, v9);
    }
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( v16 )
          {
            v17 = v16 - 2;
            if ( v17 )
            {
              v18 = v17 - 1;
              if ( v18 )
              {
                if ( v18 == 1 )
                  return _variant_t::operator=(a2);
              }
              else
              {
                LOWORD(v60) = 0;
                v19 = LongLongToShort(*(_QWORD *)(a1 + 16), (__int16 *)&v60);
                if ( v19 < 0 )
                  wil::details::in1diag3::_FailFast_Hr(retaddr, v20, v21, (const char *)(unsigned int)v19, v53);
                return _variant_t::operator=(a2, (unsigned __int16)v60);
              }
            }
            else
            {
              return _variant_t::operator=(a2, *(unsigned int *)(a1 + 16));
            }
          }
          else if ( a5 )
          {
            v22 = *(_QWORD *)(a1 + 16);
            if ( v22 )
            {
              LOBYTE(v60) = 0;
              v23 = NaturalLanguage6::Sentence::NewSegment(a5, (bool *)&v60);
              v24 = (__int64)v23;
              v61 = (__int64)v23;
              try
              {
                _variant_t::operator=(a2, v23);
                *(_QWORD *)(v24 + 24) = 0;
                *(_QWORD *)(v24 + 40) = v22;
                *(_DWORD *)(v24 + 48) = 2;
              }
              catch ( ... )
              {
                ImxTraceCatch(3, 3134570718LL, retaddr);
                v51 = v61;
                if ( (_BYTE)v60 )
                  v51 = 0;
                v61 = v51;
                throw;
              }
              if ( (_BYTE)v60 )
                v24 = 0;
              v61 = v24;
              return _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v61);
            }
          }
          return result;
        }
        v25 = 0;
        if ( !*(_QWORD *)(a1 + 16) )
          return result;
        v26 = (LSP::SimpleDateTimeEnum *)operator new(0x40u);
        v60 = v26;
        if ( v26 )
          v25 = NLG::EnumVARIANT<int,CArrayAllocator_GC<CZoneHeap>>::EnumVARIANT<int,CArrayAllocator_GC<CZoneHeap>>(
                  v26,
                  *(_QWORD *)(a1 + 16));
        goto LABEL_57;
      }
      goto LABEL_54;
    }
    if ( a5 )
    {
      v27 = *(_QWORD *)(a1 + 16);
      if ( v27 )
      {
        v28 = (_QWORD *)NaturalLanguage6::Sentence::NewRepresentationEnum(a5);
        v56 = v28;
        v54 = v28;
        for ( i = 0; i < *(_QWORD *)(v27 + 8); ++i )
        {
          LOBYTE(v60) = 0;
          v30 = NaturalLanguage6::Sentence::NewSegment(a5, (bool *)&v60);
          v61 = (__int64)v30;
          try
          {
            v31 = *(_QWORD *)CArray<NLG::CTrieWalker *,CArrayAllocator_malloc>::ElementAt(v27, i);
            *((_QWORD *)v30 + 3) = 0;
            *((_QWORD *)v30 + 5) = v31;
            *((_DWORD *)v30 + 12) = 2;
            v33 = (VARIANTARG *)_variant_t::_variant_t((_variant_t *)v58, (struct IUnknown *)v30, v32);
            v55 = v33;
            v34 = v28[4];
            v35 = v28[3];
            if ( v35 >= v34 )
            {
              if ( v35 >= 8 )
                v36 = v28[3];
              else
                v36 = 8;
              v37 = v35 + 1;
              v38 = v34 + v36;
              if ( v37 >= v38 )
                v38 = v37;
              if ( v38 > v34 )
              {
                CArray<_variant_t,CArrayAllocator_malloc>::ReallocWorker(v28 + 2, v38, v34, v33);
                v33 = v55;
              }
            }
            _variant_t::_variant_t((VARIANTARG *)(v28[2] + 24LL * v28[3]++), v33);
            _variant_t::~_variant_t(v58);
          }
          catch ( ... )
          {
            ImxTraceCatch(3, 3134570718LL, retaddr);
            v52 = v61;
            if ( (_BYTE)v60 )
              v52 = 0;
            v61 = v52;
            throw;
          }
          if ( (_BYTE)v60 )
            v30 = 0;
          v61 = (__int64)v30;
          _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v61);
          v28 = v56;
        }
        v54 = 0;
        _variant_t::operator=(a2, v28);
        return _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v54);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180050738  mov     rax, rsp
0x18005073b  push    rsi
0x18005073c  push    rdi
0x18005073d  push    r13
0x18005073f  push    r14
0x180050741  push    r15
0x180050743  sub     rsp, 70h
0x180050747  mov     qword ptr [rax-50h], 0FFFFFFFFFFFFFFFEh
0x18005074f  mov     [rax+18h], rbx
0x180050753  mov     r14b, r9b
0x180050756  mov     r15, r8
0x180050759  mov     rsi, rdx
0x18005075c  mov     rbx, rcx
0x18005075f  mov     rcx, rdx; pvarg
0x180050762  call    cs:__imp_VariantInit
0x180050768  mov     eax, [rbx+8]
0x18005076b  shr     rax, 18h
0x18005076f  movzx   r10d, al
0x180050773  cmp     r10d, 9
0x180050777  ja      loc_180050A42
0x18005077d  jz      loc_180050A2C
0x180050783  sub     r10d, 1
0x180050787  jz      loc_1800508D9
0x18005078d  sub     r10d, 1
0x180050791  jz      loc_180050ABD
0x180050797  sub     r10d, 1
0x18005079b  jz      loc_1800508A4
0x1800507a1  sub     r10d, 1
0x1800507a5  jz      short loc_180050824
0x1800507a7  sub     r10d, 2
0x1800507ab  jz      short loc_180050814
0x1800507ad  sub     r10d, 1
0x1800507b1  jz      short loc_1800507CF
0x1800507b3  cmp     r10d, 1
0x1800507b7  jnz     loc_180050B4C
0x1800507bd  movss   xmm1, dword ptr [rbx+10h]
0x1800507c2  mov     rcx, rsi
0x1800507c5  call    ??4_variant_t@@QEAAAEAV0@M@Z; _variant_t::operator=(float)
0x1800507ca  jmp     loc_180050B4C
0x1800507cf  xor     edi, edi
0x1800507d1  mov     word ptr [rsp+98h+arg_0], di
0x1800507d9  lea     rdx, [rsp+98h+arg_0]; __int16 *
0x1800507e1  mov     rcx, [rbx+10h]; __int64
0x1800507e5  call    ?LongLongToShort@@YAJ_JPEAF@Z; LongLongToShort(__int64,short *)
0x1800507ea  test    eax, eax
0x1800507ec  jns     short loc_1800507FF
0x1800507ee  mov     rcx, [rsp+98h]; this
0x1800507f6  mov     r9d, eax; char *
0x1800507f9  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800507ff  movzx   edx, word ptr [rsp+98h+arg_0]
0x180050807  mov     rcx, rsi
0x18005080a  call    ??4_variant_t@@QEAAAEAV0@F@Z; _variant_t::operator=(short)
0x18005080f  jmp     loc_180050B4C
0x180050814  mov     edx, [rbx+10h]
0x180050817  mov     rcx, rsi
0x18005081a  call    ??4_variant_t@@QEAAAEAV0@J@Z; _variant_t::operator=(long)
0x18005081f  jmp     loc_180050B4C
0x180050824  mov     rcx, [rsp+98h+arg_20]; this
0x18005082c  xor     edi, edi
0x18005082e  test    rcx, rcx
0x180050831  jz      loc_180050B4C
0x180050837  mov     r14, [rbx+10h]
0x18005083b  test    r14, r14
0x18005083e  jz      loc_180050B4C
0x180050844  mov     byte ptr [rsp+98h+arg_0], dil
0x18005084c  lea     rdx, [rsp+98h+arg_0]; bool *
0x180050854  call    ?NewSegment@Sentence@NaturalLanguage6@@QEAAPEAUITextSegment@2@AEA_N@Z; NaturalLanguage6::Sentence::NewSegment(bool &)
0x180050859  mov     rbx, rax
0x18005085c  mov     [rsp+98h+arg_8], rax
0x180050864  mov     rdx, rax
0x180050867  mov     rcx, rsi
0x18005086a  call    ??4_variant_t@@QEAAAEAV0@PEAUIUnknown@@@Z; _variant_t::operator=(IUnknown *)
0x18005086f  mov     [rbx+18h], rdi
0x180050873  mov     [rbx+28h], r14
0x180050877  mov     dword ptr [rbx+30h], 2
0x18005087e  cmp     byte ptr [rsp+98h+arg_0], dil
0x180050886  cmovnz  rbx, rdi
0x18005088a  mov     [rsp+98h+arg_8], rbx
0x180050892  lea     rcx, [rsp+98h+arg_8]
0x18005089a  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005089f  jmp     loc_180050B4C
0x1800508a4  xor     edi, edi
0x1800508a6  cmp     [rbx+10h], rdi
0x1800508aa  jz      loc_180050B4C
0x1800508b0  lea     ecx, [rdi+40h]; Size
0x1800508b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800508b8  mov     [rsp+98h+arg_0], rax
0x1800508c0  test    rax, rax
0x1800508c3  jz      short loc_1800508D4
0x1800508c5  mov     rdx, [rbx+10h]
0x1800508c9  mov     rcx, rax
0x1800508cc  call    ??0?$EnumVARIANT@HV?$CArrayAllocator_GC@VCZoneHeap@@@@@NLG@@QEAA@AEAV?$CArray@HV?$CArrayAllocator_GC@VCZoneHeap@@@@@@K_N@Z; NLG::EnumVARIANT<int,CArrayAllocator_GC<CZoneHeap>>::EnumVARIANT<int,CArrayAllocator_GC<CZoneHeap>>(CArray<int,CArrayAllocator_GC<CZoneHeap>> &,ulong,bool)
0x1800508d1  mov     rdi, rax
0x1800508d4  jmp     loc_180050AF4
0x1800508d9  xor     edi, edi
0x1800508db  cmp     [rsp+98h+arg_20], rdi
0x1800508e3  jz      loc_180050B4C
0x1800508e9  mov     r15, [rbx+10h]
0x1800508ed  test    r15, r15
0x1800508f0  jz      loc_180050B4C
0x1800508f6  mov     rcx, [rsp+98h+arg_20]
0x1800508fe  call    ?NewRepresentationEnum@Sentence@NaturalLanguage6@@QEAAPEAV?$EnumVARIANT@V_variant_t@@VCArrayAllocator_malloc@@@NLG@@XZ; NaturalLanguage6::Sentence::NewRepresentationEnum(void)
0x180050903  mov     r14, rax
0x180050906  mov     [rsp+98h+var_58], rax
0x18005090b  mov     [rsp+98h+var_68], rax
0x180050910  mov     r13d, edi
0x180050913  cmp     r13, [r15+8]
0x180050917  jge     loc_180050A0C
0x18005091d  mov     byte ptr [rsp+98h+arg_0], dil
0x180050925  lea     rdx, [rsp+98h+arg_0]; bool *
0x18005092d  mov     rcx, [rsp+98h+arg_20]; this
0x180050935  call    ?NewSegment@Sentence@NaturalLanguage6@@QEAAPEAUITextSegment@2@AEA_N@Z; NaturalLanguage6::Sentence::NewSegment(bool &)
0x18005093a  mov     rbx, rax
0x18005093d  mov     [rsp+98h+arg_8], rax
0x180050945  mov     rdx, r13
0x180050948  mov     rcx, r15
0x18005094b  call    ?ElementAt@?$CArray@PEAVCTrieWalker@NLG@@VCArrayAllocator_malloc@@@@QEBAAEAPEAVCTrieWalker@NLG@@_J@Z; CArray<NLG::CTrieWalker *,CArrayAllocator_malloc>::ElementAt(__int64)
0x180050950  mov     rax, [rax]
0x180050953  mov     [rbx+18h], rdi
0x180050957  mov     [rbx+28h], rax
0x18005095b  mov     dword ptr [rbx+30h], 2
0x180050962  mov     rdx, rbx; struct IUnknown *
0x180050965  lea     rcx, [rsp+98h+var_48]; this
0x18005096a  call    ??0_variant_t@@QEAA@PEAUIUnknown@@_N@Z; _variant_t::_variant_t(IUnknown *,bool)
0x18005096f  mov     r9, rax
0x180050972  mov     [rsp+98h+var_60], rax
0x180050977  mov     r8, [r14+20h]
0x18005097b  mov     rcx, [r14+18h]
0x18005097f  cmp     rcx, r8
0x180050982  jl      short loc_1800509B7
0x180050984  cmp     rcx, 8
0x180050988  jge     short loc_180050991
0x18005098a  mov     edx, 8
0x18005098f  jmp     short loc_180050994
0x180050991  mov     rdx, rcx
0x180050994  inc     rcx
0x180050997  add     rdx, r8
0x18005099a  cmp     rcx, rdx
0x18005099d  jge     short loc_1800509A1
0x18005099f  jmp     short loc_1800509A4
0x1800509a1  mov     rdx, rcx
0x1800509a4  cmp     rdx, r8
0x1800509a7  jle     short loc_1800509B7
0x1800509a9  lea     rcx, [r14+10h]
0x1800509ad  call    ?ReallocWorker@?$CArray@V_variant_t@@VCArrayAllocator_malloc@@@@AEAAX_J@Z; CArray<_variant_t,CArrayAllocator_malloc>::ReallocWorker(__int64)
0x1800509b2  mov     r9, [rsp+98h+var_60]
0x1800509b7  mov     rax, [r14+18h]
0x1800509bb  lea     rcx, [rax+rax*2]
0x1800509bf  mov     rax, [r14+10h]
0x1800509c3  lea     rcx, [rax+rcx*8]; pvargDest
0x1800509c7  mov     rdx, r9; pvargSrc
0x1800509ca  call    ??0_variant_t@@QEAA@AEBV0@@Z; _variant_t::_variant_t(_variant_t const &)
0x1800509cf  inc     qword ptr [r14+18h]
0x1800509d3  lea     rcx, [rsp+98h+var_48]; this
0x1800509d8  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800509dd  nop
0x1800509de  cmp     byte ptr [rsp+98h+arg_0], dil
0x1800509e6  cmovnz  rbx, rdi
0x1800509ea  mov     [rsp+98h+arg_8], rbx
0x1800509f2  lea     rcx, [rsp+98h+arg_8]
0x1800509fa  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x1800509ff  inc     r13
0x180050a02  mov     r14, [rsp+98h+var_58]
0x180050a07  jmp     loc_180050913
0x180050a0c  mov     [rsp+98h+var_68], rdi
0x180050a11  mov     rdx, r14
0x180050a14  mov     rcx, rsi
0x180050a17  call    ??4_variant_t@@QEAAAEAV0@PEAUIUnknown@@@Z; _variant_t::operator=(IUnknown *)
0x180050a1c  nop
0x180050a1d  lea     rcx, [rsp+98h+var_68]
0x180050a22  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x180050a27  jmp     loc_180050B4C
0x180050a2c  xor     edi, edi
0x180050a2e  cmp     [rbx+10h], rdi
0x180050a32  setnz   dl
0x180050a35  mov     rcx, rsi
0x180050a38  call    ??4_variant_t@@QEAAAEAV0@_N@Z; _variant_t::operator=(bool)
0x180050a3d  jmp     loc_180050B4C
0x180050a42  sub     r10d, 0Ah
0x180050a46  jz      loc_180050B27
0x180050a4c  sub     r10d, 2
0x180050a50  jz      loc_180050AF9
0x180050a56  sub     r10d, 2
0x180050a5a  jz      short loc_180050ABD
0x180050a5c  sub     r10d, 1
0x180050a60  jz      short loc_180050A8C
0x180050a62  sub     r10d, 1
0x180050a66  jz      short loc_180050A8C
0x180050a68  cmp     r10d, 1
0x180050a6c  jnz     loc_180050B4C
0x180050a72  mov     rdx, [rbx+10h]
0x180050a76  test    rdx, rdx
0x180050a79  jz      loc_180050B4C
0x180050a7f  mov     rcx, rsi
0x180050a82  call    ??4_variant_t@@QEAAAEAV0@PEAUIUnknown@@@Z; _variant_t::operator=(IUnknown *)
0x180050a87  jmp     loc_180050B4C
0x180050a8c  mov     rcx, [rbx+10h]
0x180050a90  test    rcx, rcx
0x180050a93  jz      loc_180050B4C
0x180050a99  mov     rax, [rsp+98h+arg_20]
0x180050aa1  mov     qword ptr [rsp+98h+var_78], rax; NaturalLanguage6::Sentence *
0x180050aa6  mov     r9b, r14b; int
0x180050aa9  mov     r8, r15; int
0x180050aac  mov     rdx, rsi; int
0x180050aaf  mov     rcx, [rcx+8]; int
0x180050ab3  call    NaturalLanguage6__CopyPropertyFrom
0x180050ab8  jmp     loc_180050B4C
0x180050abd  xor     edi, edi
0x180050abf  cmp     [rbx+10h], rdi
0x180050ac3  jz      loc_180050B4C
0x180050ac9  lea     ecx, [rdi+20h]; Size
0x180050acc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180050ad1  mov     [rsp+98h+arg_0], rax
0x180050ad9  test    rax, rax
0x180050adc  jz      short loc_180050AF4
0x180050ade  xor     r14b, 1
0x180050ae2  mov     r8b, r14b
0x180050ae5  mov     rdx, [rbx+10h]
0x180050ae9  mov     rcx, rax
0x180050aec  call    ??0EnumVARIANTOnNameArray@LSP@@QEAA@PEBV?$CArray@VCName@LSP@@V?$CArrayAllocator_GC@VCZoneHeap@@@@@@_NK@Z; LSP::EnumVARIANTOnNameArray::EnumVARIANTOnNameArray(CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>> const *,bool,ulong)
0x180050af1  mov     rdi, rax
0x180050af4  mov     rdx, rdi
0x180050af7  jmp     short loc_180050A7F
0x180050af9  xor     edi, edi
0x180050afb  cmp     [rbx+10h], rdi
0x180050aff  jz      short loc_180050B4C
0x180050b01  lea     ecx, [rdi+40h]; Size
0x180050b04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180050b09  mov     [rsp+98h+arg_0], rax
0x180050b11  test    rax, rax
0x180050b14  jz      short loc_180050B25
0x180050b16  mov     rdx, [rbx+10h]; struct SimpleTimeRepresentation *
0x180050b1a  mov     rcx, rax; this
0x180050b1d  call    ??0SimpleDateTimeEnum@LSP@@QEAA@PEBUSimpleTimeRepresentation@@K@Z; LSP::SimpleDateTimeEnum::SimpleDateTimeEnum(SimpleTimeRepresentation const *,ulong)
0x180050b22  mov     rdi, rax
0x180050b25  jmp     short loc_180050AF4
0x180050b27  mov     rdx, [rbx+10h]
0x180050b2b  test    rdx, rdx
0x180050b2e  jz      short loc_180050B4C
0x180050b30  test    r14b, r14b
0x180050b33  jz      short loc_180050B44
0x180050b35  mov     word ptr [rsi], 4012h
0x180050b3a  mov     rax, [rbx+10h]
0x180050b3e  mov     [rsi+8], rax
0x180050b42  jmp     short loc_180050B4C
0x180050b44  mov     rcx, rsi
0x180050b47  call    ??4_variant_t@@QEAAAEAV0@PEBG@Z; _variant_t::operator=(ushort const *)
0x180050b4c  mov     rbx, [rsp+98h+arg_10]
0x180050b54  add     rsp, 70h
0x180050b58  pop     r15
0x180050b5a  pop     r14
0x180050b5c  pop     r13
0x180050b5e  pop     rdi
0x180050b5f  pop     rsi
0x180050b60  retn
```
