# NaturalLanguage6::Copy

- ea: `0x180050310`
- end: `0x1800506e5`
- name: `NaturalLanguage6::Copy`
- size: `981`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18003c460`

## callees

- `0x180003b40`
- `0x180003d38`
- `0x180005160`
- `0x180005190`
- `0x180009790`
- `0x18000f380`
- `0x1800240f0`
- `0x18002d8c4`
- `0x180035640`
- `0x18003ed6c`
- `0x180050310`
- `0x180053dc0`
- `0x180054478`
- `0x18005d5d8`
- `0x18009e300`
- `0x1800b0010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800503bb`
- `OLEAUT32!__imp_VariantInit` at `0x1800503bb`
- `OLEAUT32!__imp_VariantClear` at `0x180050538`
- `OLEAUT32!__imp_VariantClear` at `0x180050538`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct LSP::EnumVARIANTOnNameArray *__fastcall NaturalLanguage6::Copy(
        unsigned __int16 *a1,
        CSentence **a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  NaturalLanguage6::Sentence *v6; // rsi
  CZoneHeap *v8; // rbx
  struct LSP::EnumVARIANTOnNameArray *v9; // r13
  unsigned __int8 *v10; // rdi
  int v11; // eax
  LONGLONG llVal; // rbx
  __int64 i; // rsi
  LSP::CName *v14; // rax
  const unsigned __int16 *v15; // rax
  __int64 v16; // rax
  bool v17; // zf
  __int64 v18; // rax
  __int64 v19; // rax
  _OWORD *v20; // rbx
  __int64 v21; // r9
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rcx
  HRESULT v26; // eax
  NLG *v27; // rcx
  __int64 j; // rbx
  LSP::CName *v29; // rax
  const unsigned __int16 *v30; // rax
  __int64 v31; // rax
  _OWORD *v32; // rbx
  __int64 v33; // r9
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rcx
  bool v39[8]; // [rsp+30h] [rbp-D0h] BYREF
  NaturalLanguage6::Sentence *v40; // [rsp+38h] [rbp-C8h]
  struct LSP::EnumVARIANTOnNameArray *v41; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v43; // [rsp+60h] [rbp-A0h]
  _BYTE v44[16]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE pExceptionObject[72]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v46[63]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v47; // [rsp+2BEh] [rbp+1BEh]
  const void *retaddr; // [rsp+318h] [rbp+218h]

  v43 = -2;
  v6 = (NaturalLanguage6::Sentence *)a2;
  v40 = (NaturalLanguage6::Sentence *)a2;
  v8 = CSentence::ResultsZoneHeap(a2[3]);
  v9 = NaturalLanguage6::Sentence::NewNameArrayEnum(v6);
  v41 = v9;
  *((_BYTE *)v9 + 24) = *(_BYTE *)(*(_QWORD *)(*((_QWORD *)v6 + 3) + 216LL) + 8LL) == 0;
  v10 = CZoneHeap::Alloc(v8, 0x28u, 8u);
  *(_QWORD *)v10 = 0;
  *((_QWORD *)v10 + 1) = 0;
  *((_QWORD *)v10 + 2) = 0;
  v10[24] = 1;
  *((_QWORD *)v10 + 4) = v8;
  *(_DWORD *)v39 = 0;
  VariantInit(&pvarg);
  while ( 1 )
  {
    v11 = (*(__int64 (__fastcall **)(unsigned __int16 *, __int64, VARIANTARG *, bool *))(*(_QWORD *)a1 + 24LL))(
            a1,
            1,
            &pvarg,
            v39);
    if ( v11 < 0 )
    {
      CNLException::CNLException((CNLException *)pExceptionObject, (unsigned int)v11, retaddr);
      throw (CNLException *)pExceptionObject;
    }
    if ( *(_DWORD *)v39 != 1 )
      break;
    llVal = pvarg.llVal;
    if ( pvarg.llVal )
    {
      if ( *((_QWORD *)v10 + 1) )
      {
        for ( i = 0; i < *((_QWORD *)v10 + 1); ++i )
        {
          v14 = (LSP::CName *)CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ElementAt(v10, i);
          v15 = LSP::CName::ToString(v14);
          if ( !(unsigned int)CMN_CompareStringNoCaseW(v15, llVal) )
            goto LABEL_15;
          if ( a3 )
          {
            if ( !(unsigned int)CMN_CompareStringNoCaseNumW(llVal, a3, (unsigned int)a4) )
            {
              v16 = -1;
              do
                ++v16;
              while ( *(_WORD *)(llVal + 2 * v16) );
              if ( a4 == (const unsigned __int16 *)(int)v16 )
              {
LABEL_15:
                llVal = 0;
                break;
              }
            }
          }
        }
        v6 = v40;
        v17 = llVal == 0;
LABEL_22:
        if ( v17 )
          goto LABEL_31;
        goto LABEL_23;
      }
      if ( a3 && !(unsigned int)CMN_CompareStringNoCaseNumW(pvarg.llVal, a3, (unsigned int)a4) )
      {
        v18 = -1;
        do
          ++v18;
        while ( *(_WORD *)(llVal + 2 * v18) );
        v17 = a4 == (const unsigned __int16 *)(int)v18;
        goto LABEL_22;
      }
LABEL_23:
      v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)v6 + 2) + 16LL) + 272LL))(
              *(_QWORD *)(*((_QWORD *)v6 + 2) + 16LL),
              0);
      v20 = (_OWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *, LONGLONG, _QWORD))(*(_QWORD *)v19 + 24LL))(
                        v19,
                        v44,
                        llVal,
                        0);
      v21 = *((_QWORD *)v10 + 2);
      v22 = *((_QWORD *)v10 + 1);
      if ( v22 >= v21 )
      {
        v23 = v22 + 1;
        v24 = *((_QWORD *)v10 + 1);
        if ( v22 < 8 )
          v24 = 8;
        v25 = v21 + v24;
        if ( v23 < v25 )
          v23 = v25;
        if ( v23 > v21 )
        {
          CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ReallocWorker(v10);
          v22 = *((_QWORD *)v10 + 1);
        }
      }
      *(_OWORD *)(*(_QWORD *)v10 + 16 * v22) = *v20;
      ++*((_QWORD *)v10 + 1);
LABEL_31:
      if ( *((_BYTE *)v9 + 24) )
      {
        v26 = VariantClear(&pvarg);
        if ( v26 < 0 )
        {
          CNLException::CNLException((CNLException *)pExceptionObject, (unsigned int)v26, retaddr);
          throw (CNLException *)pExceptionObject;
        }
      }
    }
  }
  if ( a3 )
  {
    v27 = (NLG *)a1[440];
    if ( (_WORD)v27 )
    {
      if ( NLG::NormalizeString(v27, a3, a4, (unsigned __int64)v46, (unsigned __int16 *)0x100, 0, v39[0]) )
      {
        v47 = 0;
        for ( j = 0; j < *((_QWORD *)v10 + 1); ++j )
        {
          v29 = (LSP::CName *)CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ElementAt(v10, j);
          v30 = LSP::CName::ToString(v29);
          if ( !(unsigned int)CMN_CompareStringNoCaseW(v30, v46) )
            goto LABEL_50;
        }
        if ( LOWORD(v46[0]) )
        {
          v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)v6 + 2) + 16LL) + 272LL))(
                  *(_QWORD *)(*((_QWORD *)v6 + 2) + 16LL),
                  0);
          v32 = (_OWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *, unsigned __int64 *, _QWORD))(*(_QWORD *)v31 + 24LL))(
                            v31,
                            v44,
                            v46,
                            0);
          v33 = *((_QWORD *)v10 + 2);
          v34 = *((_QWORD *)v10 + 1);
          if ( v34 >= v33 )
          {
            v35 = v34 + 1;
            v36 = *((_QWORD *)v10 + 1);
            if ( v34 < 8 )
              v36 = 8;
            v37 = v33 + v36;
            if ( v35 < v37 )
              v35 = v37;
            if ( v35 > v33 )
            {
              CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ReallocWorker(v10);
              v34 = *((_QWORD *)v10 + 1);
            }
          }
          *(_OWORD *)(*(_QWORD *)v10 + 16 * v34) = *v32;
          ++*((_QWORD *)v10 + 1);
        }
      }
    }
  }
LABEL_50:
  *((_QWORD *)v9 + 2) = v10;
  v41 = 0;
  _variant_t::~_variant_t(&pvarg);
  _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v41);
  return v9;
}

```

## disassembly

```asm
0x180050310  push    rbp
0x180050312  push    rbx
0x180050313  push    rsi
0x180050314  push    rdi
0x180050315  push    r12
0x180050317  push    r13
0x180050319  push    r14
0x18005031b  push    r15
0x18005031d  lea     rbp, [rsp-1D8h]
0x180050325  sub     rsp, 2D8h
0x18005032c  mov     [rsp+310h+var_2B0], 0FFFFFFFFFFFFFFFEh
0x180050335  mov     rax, cs:__security_cookie
0x18005033c  xor     rax, rsp
0x18005033f  mov     [rbp+210h+var_50], rax
0x180050346  mov     r15, r9
0x180050349  mov     r14, r8
0x18005034c  mov     rsi, rdx
0x18005034f  mov     [rsp+310h+var_2D8], rdx
0x180050354  mov     r12, rcx
0x180050357  mov     rcx, [rdx+18h]; this
0x18005035b  call    ?ResultsZoneHeap@CSentence@@QEBAAEAVCZoneHeap@@XZ; CSentence::ResultsZoneHeap(void)
0x180050360  mov     rbx, rax
0x180050363  mov     rcx, rsi; this
0x180050366  call    ?NewNameArrayEnum@Sentence@NaturalLanguage6@@QEAAPEAVEnumVARIANTOnNameArray@LSP@@XZ; NaturalLanguage6::Sentence::NewNameArrayEnum(void)
0x18005036b  mov     r13, rax
0x18005036e  mov     [rsp+310h+var_2D0], rax
0x180050373  mov     rcx, [rsi+18h]
0x180050377  mov     rdx, [rcx+0D8h]
0x18005037e  xor     ecx, ecx
0x180050380  cmp     [rdx+8], cl
0x180050383  setz    cl
0x180050386  mov     [rax+18h], cl
0x180050389  mov     edx, 28h ; '('; unsigned __int64
0x18005038e  lea     r8d, [rdx-20h]; unsigned __int64
0x180050392  mov     rcx, rbx; this
0x180050395  call    ?Alloc@CZoneHeap@@QEAAPEAE_K0@Z; CZoneHeap::Alloc(unsigned __int64,unsigned __int64)
0x18005039a  mov     rdi, rax
0x18005039d  xor     eax, eax
0x18005039f  mov     [rdi], rax
0x1800503a2  mov     [rdi+8], rax
0x1800503a6  mov     [rdi+10h], rax
0x1800503aa  mov     byte ptr [rdi+18h], 1
0x1800503ae  mov     [rdi+20h], rbx
0x1800503b2  mov     dword ptr [rsp+310h+var_2E0], eax; bool
0x1800503b6  lea     rcx, [rsp+310h+pvarg]; pvarg
0x1800503bb  call    cs:__imp_VariantInit
0x1800503c1  nop
0x1800503c2  mov     rax, [r12]
0x1800503c6  lea     r9, [rsp+310h+var_2E0]
0x1800503cb  lea     r8, [rsp+310h+pvarg]
0x1800503d0  mov     edx, 1
0x1800503d5  mov     rcx, r12
0x1800503d8  mov     rax, [rax+18h]
0x1800503dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503e1  xor     edx, edx
0x1800503e3  test    eax, eax
0x1800503e5  js      loc_1800506C0
0x1800503eb  cmp     dword ptr [rsp+310h+var_2E0], 1
0x1800503f0  jnz     loc_18005056B
0x1800503f6  mov     rbx, qword ptr [rsp+310h+pvarg+8]
0x1800503fb  test    rbx, rbx
0x1800503fe  jz      short loc_1800503C2
0x180050400  cmp     [rdi+8], rdx
0x180050404  jz      short loc_180050471
0x180050406  mov     esi, edx
0x180050408  cmp     rsi, [rdi+8]
0x18005040c  jge     short loc_180050467
0x18005040e  mov     rdx, rsi
0x180050411  mov     rcx, rdi
0x180050414  call    ?ElementAt@?$CArray@VCName@LSP@@V?$CArrayAllocator_GC@VCZoneHeap@@@@@@QEBAAEAVCName@LSP@@_J@Z; CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ElementAt(__int64)
0x180050419  mov     rcx, rax; this
0x18005041c  call    ?ToString@CName@LSP@@QEBAPEBGXZ; LSP::CName::ToString(void)
0x180050421  mov     rdx, rbx
0x180050424  mov     rcx, rax
0x180050427  call    CMN_CompareStringNoCaseW
0x18005042c  xor     edx, edx
0x18005042e  test    eax, eax
0x180050430  jz      short loc_180050464
0x180050432  test    r14, r14
0x180050435  jz      short loc_18005045F
0x180050437  mov     r8d, r15d
0x18005043a  mov     rdx, r14
0x18005043d  mov     rcx, rbx
0x180050440  call    CMN_CompareStringNoCaseNumW
0x180050445  xor     edx, edx
0x180050447  test    eax, eax
0x180050449  jnz     short loc_18005045F
0x18005044b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005044f  inc     rax
0x180050452  cmp     [rbx+rax*2], dx
0x180050456  jnz     short loc_18005044F
0x180050458  cdqe
0x18005045a  cmp     r15, rax
0x18005045d  jz      short loc_180050464
0x18005045f  inc     rsi
0x180050462  jmp     short loc_180050408
0x180050464  mov     rbx, rdx
0x180050467  mov     rsi, [rsp+310h+var_2D8]
0x18005046c  test    rbx, rbx
0x18005046f  jmp     short loc_18005049C
0x180050471  test    r14, r14
0x180050474  jz      short loc_1800504A2
0x180050476  mov     r8d, r15d
0x180050479  mov     rdx, r14
0x18005047c  mov     rcx, rbx
0x18005047f  call    CMN_CompareStringNoCaseNumW
0x180050484  xor     edx, edx
0x180050486  test    eax, eax
0x180050488  jnz     short loc_1800504A2
0x18005048a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005048e  inc     rax
0x180050491  cmp     [rbx+rax*2], dx
0x180050495  jnz     short loc_18005048E
0x180050497  cdqe
0x180050499  cmp     r15, rax
0x18005049c  jz      loc_180050529
0x1800504a2  mov     rax, [rsi+10h]
0x1800504a6  mov     rcx, [rax+10h]
0x1800504aa  mov     rax, [rcx]
0x1800504ad  mov     rax, [rax+110h]
0x1800504b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504b9  mov     r10, rax
0x1800504bc  mov     rcx, [rax]
0x1800504bf  mov     rax, [rcx+18h]
0x1800504c3  xor     r9d, r9d
0x1800504c6  mov     r8, rbx
0x1800504c9  lea     rdx, [rsp+310h+var_2A8]
0x1800504ce  mov     rcx, r10
0x1800504d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504d6  mov     rbx, rax
0x1800504d9  mov     r9, [rdi+10h]
0x1800504dd  mov     r8, [rdi+8]
0x1800504e1  cmp     r8, r9
0x1800504e4  jl      short loc_180050514
0x1800504e6  lea     rdx, [r8+1]
0x1800504ea  mov     rcx, r8
0x1800504ed  mov     eax, 8
0x1800504f2  cmp     r8, rax
0x1800504f5  cmovl   rcx, rax
0x1800504f9  add     rcx, r9
0x1800504fc  cmp     rdx, rcx
0x1800504ff  cmovl   rdx, rcx
0x180050503  cmp     rdx, r9
0x180050506  jle     short loc_180050514
0x180050508  mov     rcx, rdi
0x18005050b  call    ?ReallocWorker@?$CArray@VCName@LSP@@V?$CArrayAllocator_GC@VCZoneHeap@@@@@@AEAAX_J@Z; CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ReallocWorker(__int64)
0x180050510  mov     r8, [rdi+8]
0x180050514  add     r8, r8
0x180050517  mov     rax, [rdi]
0x18005051a  movups  xmm0, xmmword ptr [rbx]
0x18005051d  movdqu  xmmword ptr [rax+r8*8], xmm0
0x180050523  inc     qword ptr [rdi+8]
0x180050527  xor     edx, edx
0x180050529  cmp     [r13+18h], dl
0x18005052d  jz      loc_1800503C2
0x180050533  lea     rcx, [rsp+310h+pvarg]; pvarg
0x180050538  call    cs:__imp_VariantClear
0x18005053e  test    eax, eax
0x180050540  jns     loc_1800503C2
0x180050546  mov     r8, [rbp+218h]; void *
0x18005054d  mov     edx, eax; int
0x18005054f  lea     rcx, [rsp+310h+pExceptionObject]; this
0x180050554  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180050559  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180050560  lea     rcx, [rsp+310h+pExceptionObject]; pExceptionObject
0x180050565  call    _CxxThrowException_0
0x18005056b  test    r14, r14
0x18005056e  jz      loc_18005067C
0x180050574  movzx   ecx, word ptr [r12+370h]; this
0x18005057d  test    cx, cx
0x180050580  jz      loc_18005067C
0x180050586  mov     [rsp+310h+var_2E8], dl; char
0x18005058a  mov     [rsp+310h+var_2F0], 100h; unsigned __int16 *
0x180050593  lea     r9, [rbp+210h+var_250]; unsigned __int64
0x180050597  mov     r8, r15; unsigned __int16 *
0x18005059a  mov     rdx, r14; unsigned __int16
0x18005059d  call    ?NormalizeString@NLG@@YAPEBGGPEBG_KPEAG1_N@Z; NLG::NormalizeString(ushort,ushort const *,unsigned __int64,ushort *,unsigned __int64,bool)
0x1800505a2  xor     edx, edx
0x1800505a4  test    rax, rax
0x1800505a7  jz      loc_18005067C
0x1800505ad  mov     [rbp+210h+var_52], dx
0x1800505b4  mov     ebx, edx
0x1800505b6  cmp     rbx, [rdi+8]
0x1800505ba  jge     short loc_1800505EA
0x1800505bc  mov     rdx, rbx
0x1800505bf  mov     rcx, rdi
0x1800505c2  call    ?ElementAt@?$CArray@VCName@LSP@@V?$CArrayAllocator_GC@VCZoneHeap@@@@@@QEBAAEAVCName@LSP@@_J@Z; CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ElementAt(__int64)
0x1800505c7  mov     rcx, rax; this
0x1800505ca  call    ?ToString@CName@LSP@@QEBAPEBGXZ; LSP::CName::ToString(void)
0x1800505cf  lea     rdx, [rbp+210h+var_250]
0x1800505d3  mov     rcx, rax
0x1800505d6  call    CMN_CompareStringNoCaseW
0x1800505db  xor     edx, edx
0x1800505dd  test    eax, eax
0x1800505df  jz      loc_18005067C
0x1800505e5  inc     rbx
0x1800505e8  jmp     short loc_1800505B6
0x1800505ea  cmp     word ptr [rbp+210h+var_250], dx
0x1800505ee  jz      loc_18005067C
0x1800505f4  mov     rax, [rsi+10h]
0x1800505f8  mov     rcx, [rax+10h]
0x1800505fc  mov     rax, [rcx]
0x1800505ff  mov     rax, [rax+110h]
0x180050606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005060b  mov     r10, rax
0x18005060e  mov     rcx, [rax]
0x180050611  mov     rax, [rcx+18h]
0x180050615  xor     r9d, r9d
0x180050618  lea     r8, [rbp+210h+var_250]
0x18005061c  lea     rdx, [rsp+310h+var_2A8]
0x180050621  mov     rcx, r10
0x180050624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050629  mov     rbx, rax
0x18005062c  mov     r9, [rdi+10h]
0x180050630  mov     r8, [rdi+8]
0x180050634  cmp     r8, r9
0x180050637  jl      short loc_180050667
0x180050639  lea     rdx, [r8+1]
0x18005063d  mov     rcx, r8
0x180050640  mov     eax, 8
0x180050645  cmp     r8, rax
0x180050648  cmovl   rcx, rax
0x18005064c  add     rcx, r9
0x18005064f  cmp     rdx, rcx
0x180050652  cmovl   rdx, rcx
0x180050656  cmp     rdx, r9
0x180050659  jle     short loc_180050667
0x18005065b  mov     rcx, rdi
0x18005065e  call    ?ReallocWorker@?$CArray@VCName@LSP@@V?$CArrayAllocator_GC@VCZoneHeap@@@@@@AEAAX_J@Z; CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ReallocWorker(__int64)
0x180050663  mov     r8, [rdi+8]
0x180050667  shl     r8, 4
0x18005066b  add     r8, [rdi]
0x18005066e  movups  xmm0, xmmword ptr [rbx]
0x180050671  movdqu  xmmword ptr [r8], xmm0
0x180050676  inc     qword ptr [rdi+8]
0x18005067a  xor     edx, edx
0x18005067c  mov     [r13+10h], rdi
0x180050680  mov     [rsp+310h+var_2D0], rdx
0x180050685  lea     rcx, [rsp+310h+pvarg]; this
0x18005068a  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005068f  nop
0x180050690  lea     rcx, [rsp+310h+var_2D0]
0x180050695  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005069a  mov     rax, r13
0x18005069d  mov     rcx, [rbp+210h+var_50]
0x1800506a4  xor     rcx, rsp; StackCookie
0x1800506a7  call    __security_check_cookie
0x1800506ac  add     rsp, 2D8h
0x1800506b3  pop     r15
0x1800506b5  pop     r14
0x1800506b7  pop     r13
0x1800506b9  pop     r12
0x1800506bb  pop     rdi
0x1800506bc  pop     rsi
0x1800506bd  pop     rbx
0x1800506be  pop     rbp
0x1800506bf  retn
0x1800506c0  mov     r8, [rbp+218h]; void *
0x1800506c7  mov     edx, eax; int
0x1800506c9  lea     rcx, [rsp+310h+pExceptionObject]; this
0x1800506ce  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x1800506d3  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x1800506da  lea     rcx, [rsp+310h+pExceptionObject]; pExceptionObject
0x1800506df  call    _CxxThrowException_0
```
