# WindowsPerformanceRecorder::CETWProperties::WriteSystemProvider(WindowsPerformanceRecorder::CXmlWriter &,WindowsPerformanceRecorder::CETWProperties::CEventSession const *,bool)

- ea: `0x1800442c8`
- end: `0x18004499a`
- name: `?WriteSystemProvider@CETWProperties@WindowsPerformanceRecorder@@CAJAEAVCXmlWriter@2@PEBUCEventSession@12@_N@Z`
- size: `1746`
- prototype: `__int64 __fastcall(struct WindowsPerformanceRecorder::CXmlWriter *this, const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *, bool)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config`

## callers

- `0x18003e33c`

## callees

- `0x180008330`
- `0x18000eeb0`
- `0x1800102d8`
- `0x1800128f8`
- `0x180013038`
- `0x180013094`
- `0x18001e6b8`
- `0x1800234f0`
- `0x180025580`
- `0x18002c3b0`
- `0x180031dc0`
- `0x180035250`
- `0x1800442c8`
- `0x1800449a0`
- `0x180044ac4`
- `0x18004942c`
- `0x18004f970`
- `0x1800576c8`
- `0x18005c5f4`
- `0x1800656e4`
- `0x18006573c`
- `0x1800657d4`
- `0x18006592c`
- `0x1800659b4`

## string_xrefs

- `0x1800443b6`: `SystemProvider`
- `0x180044921`: `SystemProvider`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WindowsPerformanceRecorder::CETWProperties::WriteSystemProvider(
        struct WindowsPerformanceRecorder::CXmlWriter *this,
        const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *a2,
        char a3)
{
  __int64 v5; // rax
  unsigned __int64 v6; // r14
  __int64 v7; // r13
  unsigned __int16 *v8; // rcx
  int i; // edx
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  char *SessionName; // rax
  unsigned __int64 j; // rax
  unsigned __int64 k; // r15
  unsigned __int64 v15; // r13
  unsigned __int64 m; // rax
  unsigned int v17; // ecx
  int v18; // ecx
  unsigned int v19; // r15d
  char HasSystemKeywordType; // r15
  char v21; // r12
  char v22; // r11
  __int64 v23; // r14
  __int64 v24; // r14
  __int64 v25; // rsi
  unsigned __int16 *v26; // r12
  unsigned __int16 *v27; // rsi
  int n; // ecx
  unsigned __int64 v29; // r15
  unsigned __int64 ii; // rcx
  __int64 v31; // r13
  const char *v32; // rdx
  int jj; // ecx
  unsigned __int64 v34; // rax
  unsigned __int64 kk; // r15
  __int64 v36; // rsi
  unsigned int v37; // r13d
  unsigned int v39; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+38h] [rbp-A0h] BYREF
  unsigned __int16 *v41; // [rsp+40h] [rbp-98h] BYREF
  _DWORD v42[2]; // [rsp+48h] [rbp-90h]
  unsigned __int16 *v43; // [rsp+50h] [rbp-88h] BYREF
  __int128 v44; // [rsp+58h] [rbp-80h]
  __int128 v45; // [rsp+68h] [rbp-70h]
  unsigned __int64 v46; // [rsp+78h] [rbp-60h]
  __int64 v47; // [rsp+80h] [rbp-58h]
  ATL::CAtlException *v48; // [rsp+88h] [rbp-50h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+90h] [rbp-48h] BYREF

  v47 = -2;
  v5 = *((_QWORD *)a2 + 1);
  v6 = 0;
  if ( *(_DWORD *)(v5 + 72) )
  {
    v7 = v5 + *(unsigned __int16 *)(v5 + 72);
    v40 = v7;
    if ( *(_WORD *)(v7 + 2) )
    {
      v44 = 0;
      v45 = 0;
      if ( a3 )
      {
        v8 = (unsigned __int16 *)(v7 + 4);
        for ( i = 0; i < *(unsigned __int16 *)(v7 + 2); ++i )
        {
          if ( v8[1] == 1 )
          {
            v10 = *(_OWORD *)(v8 + 2);
            v11 = *(_OWORD *)(v8 + 10);
            goto LABEL_10;
          }
          v8 += 2 * *v8;
        }
      }
      else
      {
        v10 = *(_OWORD *)((char *)a2 + 120);
        v11 = *(_OWORD *)((char *)a2 + 136);
LABEL_10:
        v45 = v11;
        v44 = v10;
      }
      SessionName = (char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(a2);
      try
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64 *)&v43,
          SessionName);
        ATL::CSimpleStringT<unsigned short,0>::Append(&v43, L"_Provider");
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
          &v43,
          58);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
          &v43,
          32);
        WindowsPerformanceRecorder::CXmlWriter::Start(this, L"SystemProvider");
        WindowsPerformanceRecorder::CXmlWriter::Attr(this, L"Id", v43);
        if ( !*((_BYTE *)a2 + 207) )
          WindowsPerformanceRecorder::CXmlWriter::AttrTrueFalse(this, L"SuppressHighVolume", 0);
        for ( j = 0; j < 8; ++j )
        {
          if ( *((_DWORD *)&v44 + j) )
          {
            WindowsPerformanceRecorder::CXmlWriter::Start(this, L"Keywords");
            for ( k = 0; k < 0x49; ++k )
            {
              v39 = qword_18008D048[4 * k];
              v15 = (unsigned __int64)v39 >> 29;
              if ( (v39 & *((_DWORD *)&v44 + v15) & 0x1FFFFFFF) == (v39 & 0x1FFFFFFF) )
              {
                WindowsPerformanceRecorder::CXmlWriter::Start(this, L"Keyword");
                WindowsPerformanceRecorder::CXmlWriter::Attr(
                  this,
                  L"Value",
                  *((const unsigned __int16 **)&WindowsPerformanceRecorder::CSystemProviderElement::sc_Keywords + 4 * k));
                WindowsPerformanceRecorder::CXmlWriter::End(this, 0);
                *((_DWORD *)&v44 + v15) &= ~(v39 & 0x1FFFFFFF);
                LODWORD(v6) = 0;
                for ( m = 0; m < 8; ++m )
                {
                  if ( v39 == dword_18009C5D4[2 * m] )
                  {
                    v17 = dword_18009C5D0[2 * m];
                    *((_DWORD *)&v44 + ((unsigned __int64)v17 >> 29)) &= ~(v17 & 0x1FFFFFFF);
                    break;
                  }
                }
              }
              else
              {
                LODWORD(v6) = 0;
              }
            }
            while ( (unsigned int)v6 < 8 )
            {
              v18 = *((_DWORD *)&v44 + (unsigned int)v6);
              if ( v18 )
              {
                v19 = v18 | ((_DWORD)v6 << 29);
                WindowsPerformanceRecorder::CXmlWriter::Start(this, L"CustomKeyword");
                WindowsPerformanceRecorder::CXmlWriter::AttrHex(this, L"Value", v19);
                WindowsPerformanceRecorder::CXmlWriter::End(this, 0);
              }
              LODWORD(v6) = v6 + 1;
            }
            WindowsPerformanceRecorder::CXmlWriter::End(this, L"Keywords");
            v7 = v40;
            v6 = 0;
            break;
          }
        }
        WindowsPerformanceRecorder::CETWProperties::CEventSession::HasSystemKeywordType(a2, 1);
        HasSystemKeywordType = WindowsPerformanceRecorder::CETWProperties::CEventSession::HasSystemKeywordType(a2, 2);
        v21 = WindowsPerformanceRecorder::CETWProperties::CEventSession::HasSystemKeywordType(a2, 3);
        v41 = (unsigned __int16 *)this;
        if ( v22 )
        {
          v39 = 1;
          v23 = std::map<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>::at(
                  (char *)a2 + 96,
                  &v39);
          WindowsPerformanceRecorder::CXmlWriter::Start(this, L"CaptureStateOnStart");
          lambda_6fa3425b4c07c34abf7b329463000c6f_::operator()(&v41, v23);
          WindowsPerformanceRecorder::CXmlWriter::End(this, L"CaptureStateOnStart");
          v6 = 0;
        }
        if ( HasSystemKeywordType )
        {
          v39 = 2;
          v24 = std::map<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>::at(
                  (char *)a2 + 96,
                  &v39);
          WindowsPerformanceRecorder::CXmlWriter::Start(this, L"CaptureStateOnSave");
          lambda_6fa3425b4c07c34abf7b329463000c6f_::operator()(&v41, v24);
          WindowsPerformanceRecorder::CXmlWriter::End(this, L"CaptureStateOnSave");
          v6 = 0;
        }
        if ( v21 )
        {
          v39 = 3;
          v25 = std::map<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>::at(
                  (char *)a2 + 96,
                  &v39);
          WindowsPerformanceRecorder::CXmlWriter::Start(this, L"CaptureStateOnDemand");
          lambda_6fa3425b4c07c34abf7b329463000c6f_::operator()(&v41, v25);
          WindowsPerformanceRecorder::CXmlWriter::End(this, L"CaptureStateOnDemand");
        }
        v26 = (unsigned __int16 *)(v7 + 4);
        v27 = (unsigned __int16 *)(v7 + 4);
        for ( n = 0; n < *(unsigned __int16 *)(v7 + 2); ++n )
        {
          if ( v27[1] == 3 )
          {
            WindowsPerformanceRecorder::CXmlWriter::Start(this, L"Stacks");
            v29 = *v27 - 1LL;
            while ( v6 < v29 )
            {
              for ( ii = 0; ; ++ii )
              {
                if ( ii >= 0xBC )
                {
                  WindowsPerformanceRecorder::CXmlWriter::Start(this, L"CustomStack");
                  WindowsPerformanceRecorder::CXmlWriter::AttrHex(this, L"Value", *(_DWORD *)&v27[2 * v6 + 2]);
                  WindowsPerformanceRecorder::CXmlWriter::End(this, 0);
                  goto LABEL_52;
                }
                v31 = 3 * ii;
                if ( *(_DWORD *)&v27[2 * v6 + 2] == (unsigned __int16)word_18008D968[12 * ii] )
                  break;
              }
              WindowsPerformanceRecorder::CXmlWriter::Start(this, L"Stack");
              WindowsPerformanceRecorder::CXmlWriter::Attr(
                this,
                L"Value",
                *((const unsigned __int16 **)&WindowsPerformanceRecorder::CSystemProviderElement::sc_Stacks + v31));
              *((_DWORD *)this + 5) -= 2;
              if ( !*((_BYTE *)this + 16) )
              {
                std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, v32);
                throw (std::invalid_argument *)pExceptionObject;
              }
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
                this,
                L" />\n");
              *((_BYTE *)this + 16) = 0;
LABEL_52:
              ++v6;
            }
            *((_DWORD *)this + 5) -= 2;
            LOBYTE(v6) = 0;
            if ( *((_BYTE *)this + 16) )
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
                this,
                L" />\n");
            else
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
                this,
                L"%*ws</%ws>\n",
                *((unsigned int *)this + 5),
                &LocaleName,
                L"Stacks");
            *((_BYTE *)this + 16) = 0;
            v7 = v40;
            break;
          }
          v27 += 2 * *v27;
        }
        for ( jj = 0; jj < *(unsigned __int16 *)(v7 + 2); ++jj )
        {
          if ( v26[1] == 4 )
          {
            WindowsPerformanceRecorder::CXmlWriter::Start(this, L"PoolTags");
            v34 = *v26 - 1LL;
            v46 = v34;
            for ( kk = 0; kk < v34; ++kk )
            {
              v42[0] = *(_DWORD *)&v26[2 * kk + 2];
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v40);
              v36 = v40;
              while ( (unsigned __int8)v6 < 4u )
              {
                v39 = *(_DWORD *)(v36 - 16);
                v37 = v39 + 1;
                if ( (((*(_DWORD *)(v36 - 12) - (v39 + 1)) | (1 - *(_DWORD *)(v36 - 8))) & 0x80000000) != 0 )
                {
                  ATL::CSimpleStringT<char,0>::PrepareWrite2(&v40, v37);
                  v36 = v40;
                }
                *(_BYTE *)(v39 + v36) = *((_BYTE *)v42 + (unsigned __int8)v6);
                ATL::CSimpleStringT<char,0>::SetLength(&v40, v37);
                LOBYTE(v6) = v6 + 1;
              }
              WindowsPerformanceRecorder::CXmlWriter::Start(this, L"PoolTag");
              ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&v41, &ATL::g_strmgr);
              LOBYTE(v6) = 0;
              if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                                       &v41,
                                       v36) )
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
                  &v41,
                  v36);
              WindowsPerformanceRecorder::CXmlWriter::Attr(this, L"Value", v41);
              WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v41);
              WindowsPerformanceRecorder::CXmlWriter::End(this, 0);
              WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v40);
              v34 = v46;
            }
            WindowsPerformanceRecorder::CXmlWriter::End(this, L"PoolTags");
            break;
          }
          v26 += 2 * *v26;
        }
        *((_DWORD *)this + 5) -= 2;
        if ( *((_BYTE *)this + 16) )
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            this,
            L" />\n");
        else
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            this,
            L"%*ws</%ws>\n",
            *((unsigned int *)this + 5),
            &LocaleName,
            L"SystemProvider");
        *((_BYTE *)this + 16) = 0;
        ATL::CStringData::Release((ATL::CStringData *)(v43 - 12));
      }
      catch ( ATL::CAtlException *v48 )
      {
        return *(unsigned int *)v48;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800442c8  mov     rax, rsp
0x1800442cb  push    rdi
0x1800442cc  push    r12
0x1800442ce  push    r13
0x1800442d0  push    r14
0x1800442d2  push    r15
0x1800442d4  sub     rsp, 0B0h
0x1800442db  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x1800442e3  mov     [rax+18h], rbx
0x1800442e7  mov     [rax+20h], rsi
0x1800442eb  mov     rsi, rdx
0x1800442ee  mov     rbx, rcx
0x1800442f1  mov     rax, [rdx+8]
0x1800442f5  xor     r14d, r14d
0x1800442f8  cmp     [rax+48h], r14d
0x1800442fc  jz      loc_180044975
0x180044302  movzx   r13d, word ptr [rax+48h]
0x180044307  add     r13, rax
0x18004430a  mov     [rsp+0D8h+var_A0], r13
0x18004430f  cmp     [r13+2], r14w
0x180044314  jz      loc_180044975
0x18004431a  xorps   xmm0, xmm0
0x18004431d  movups  [rsp+0D8h+var_80], xmm0
0x180044322  movups  [rsp+0D8h+var_70], xmm0
0x180044327  lea     edi, [r14+1]
0x18004432b  test    r8b, r8b
0x18004432e  jz      short loc_18004435C
0x180044330  lea     rcx, [r13+4]
0x180044334  mov     edx, r14d
0x180044337  movzx   r8d, word ptr [r13+2]
0x18004433c  cmp     edx, r8d
0x18004433f  jge     short loc_180044371
0x180044341  cmp     [rcx+2], di
0x180044345  jz      short loc_180044352
0x180044347  movzx   eax, word ptr [rcx]
0x18004434a  lea     rcx, [rcx+rax*4]
0x18004434e  add     edx, edi
0x180044350  jmp     short loc_18004433C
0x180044352  movups  xmm0, xmmword ptr [rcx+4]
0x180044356  movups  xmm1, xmmword ptr [rcx+14h]
0x18004435a  jmp     short loc_180044367
0x18004435c  movups  xmm0, xmmword ptr [rdx+78h]
0x180044360  movups  xmm1, xmmword ptr [rdx+88h]
0x180044367  movups  [rsp+0D8h+var_70], xmm1
0x18004436c  movups  [rsp+0D8h+var_80], xmm0
0x180044371  mov     rcx, rsi; this
0x180044374  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x180044379  mov     rdx, rax
0x18004437c  lea     rcx, [rsp+0D8h+var_88]
0x180044381  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180044386  nop
0x180044387  lea     rdx, aProvider; "_Provider"
0x18004438e  lea     rcx, [rsp+0D8h+var_88]
0x180044393  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x180044398  mov     edx, 3Ah ; ':'
0x18004439d  lea     rcx, [rsp+0D8h+var_88]
0x1800443a2  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHGG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort,ushort)
0x1800443a7  mov     edx, 20h ; ' '
0x1800443ac  lea     rcx, [rsp+0D8h+var_88]
0x1800443b1  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHGG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort,ushort)
0x1800443b6  lea     rdx, aSystemprovider_0; "SystemProvider"
0x1800443bd  mov     rcx, rbx; this
0x1800443c0  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x1800443c5  mov     r8, [rsp+0D8h+var_88]; unsigned __int16 *
0x1800443ca  lea     rdx, aId; "Id"
0x1800443d1  mov     rcx, rbx; this
0x1800443d4  call    ?Attr@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG0@Z; WindowsPerformanceRecorder::CXmlWriter::Attr(ushort const *,ushort const *)
0x1800443d9  cmp     [rsi+0CFh], r14b
0x1800443e0  jnz     short loc_1800443F4
0x1800443e2  xor     r8d, r8d; int
0x1800443e5  lea     rdx, aSuppresshighvo; "SuppressHighVolume"
0x1800443ec  mov     rcx, rbx; this
0x1800443ef  call    ?AttrTrueFalse@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBGH@Z; WindowsPerformanceRecorder::CXmlWriter::AttrTrueFalse(ushort const *,int)
0x1800443f4  mov     rax, r14
0x1800443f7  cmp     rax, 8
0x1800443fb  jnb     loc_180044551
0x180044401  cmp     dword ptr [rsp+rax*4+0D8h+var_80], r14d
0x180044406  jnz     short loc_18004440D
0x180044408  add     rax, rdi
0x18004440b  jmp     short loc_1800443F7
0x18004440d  lea     rdx, aKeywords; "Keywords"
0x180044414  mov     rcx, rbx; this
0x180044417  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x18004441c  mov     r15, r14
0x18004441f  lea     rdx, __ImageBase
0x180044426  cmp     r15, 49h ; 'I'
0x18004442a  jnb     loc_1800444EF
0x180044430  mov     r12, r15
0x180044433  shl     r12, 5
0x180044437  mov     ecx, [r12+rdx+8D048h]
0x18004443f  mov     [rsp+0D8h+var_A8], ecx
0x180044443  mov     r14d, ecx
0x180044446  and     r14d, 1FFFFFFFh
0x18004444d  mov     r13d, ecx
0x180044450  shr     r13, 1Dh
0x180044454  mov     eax, dword ptr [rsp+r13*4+0D8h+var_80]
0x180044459  and     eax, ecx
0x18004445b  and     eax, 1FFFFFFFh
0x180044460  cmp     eax, r14d
0x180044463  jnz     short loc_1800444E4
0x180044465  lea     rdx, aKeyword; "Keyword"
0x18004446c  mov     rcx, rbx; this
0x18004446f  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x180044474  lea     r8, __ImageBase
0x18004447b  mov     r8, [r12+r8+8D040h]; unsigned __int16 *
0x180044483  lea     rdx, aValue; "Value"
0x18004448a  mov     rcx, rbx; this
0x18004448d  call    ?Attr@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG0@Z; WindowsPerformanceRecorder::CXmlWriter::Attr(ushort const *,ushort const *)
0x180044492  xor     edx, edx; unsigned __int16 *
0x180044494  mov     rcx, rbx; this
0x180044497  call    ?End@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::End(ushort const *)
0x18004449c  not     r14d
0x18004449f  and     dword ptr [rsp+r13*4+0D8h+var_80], r14d
0x1800444a4  xor     r14d, r14d
0x1800444a7  mov     eax, r14d
0x1800444aa  mov     ecx, [rsp+0D8h+var_A8]
0x1800444ae  lea     rdx, __ImageBase
0x1800444b5  cmp     rax, 8
0x1800444b9  jnb     short loc_1800444E7
0x1800444bb  cmp     ecx, ds:rva dword_18009C5D4[rdx+rax*8]
0x1800444c2  jz      short loc_1800444C9
0x1800444c4  add     rax, rdi
0x1800444c7  jmp     short loc_1800444B5
0x1800444c9  mov     ecx, ds:rva dword_18009C5D0[rdx+rax*8]
0x1800444d0  mov     eax, ecx
0x1800444d2  shr     rax, 1Dh
0x1800444d6  and     ecx, 1FFFFFFFh
0x1800444dc  not     ecx
0x1800444de  and     dword ptr [rsp+rax*4+0D8h+var_80], ecx
0x1800444e2  jmp     short loc_1800444E7
0x1800444e4  xor     r14d, r14d
0x1800444e7  add     r15, rdi
0x1800444ea  jmp     loc_180044426
0x1800444ef  cmp     r14d, 8
0x1800444f3  jnb     short loc_18004453A
0x1800444f5  mov     eax, r14d
0x1800444f8  mov     ecx, dword ptr [rsp+rax*4+0D8h+var_80]
0x1800444fc  test    ecx, ecx
0x1800444fe  jz      short loc_180044535
0x180044500  mov     r15d, r14d
0x180044503  shl     r15d, 1Dh
0x180044507  or      r15d, ecx
0x18004450a  lea     rdx, aCustomkeyword; "CustomKeyword"
0x180044511  mov     rcx, rbx; this
0x180044514  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x180044519  mov     r8d, r15d; unsigned int
0x18004451c  lea     rdx, aValue; "Value"
0x180044523  mov     rcx, rbx; this
0x180044526  call    ?AttrHex@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBGK@Z; WindowsPerformanceRecorder::CXmlWriter::AttrHex(ushort const *,ulong)
0x18004452b  xor     edx, edx; unsigned __int16 *
0x18004452d  mov     rcx, rbx; this
0x180044530  call    ?End@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::End(ushort const *)
0x180044535  add     r14d, edi
0x180044538  jmp     short loc_1800444EF
0x18004453a  lea     rdx, aKeywords; "Keywords"
0x180044541  mov     rcx, rbx; this
0x180044544  call    ?End@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::End(ushort const *)
0x180044549  mov     r13, [rsp+0D8h+var_A0]
0x18004454e  xor     r14d, r14d
0x180044551  mov     edx, edi
0x180044553  mov     rcx, rsi
0x180044556  call    ?HasSystemKeywordType@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBA_NW4SystemKeywordType@3@@Z; WindowsPerformanceRecorder::CETWProperties::CEventSession::HasSystemKeywordType(WindowsPerformanceRecorder::SystemKeywordType)
0x18004455b  mov     r11b, al
0x18004455e  mov     edx, 2
0x180044563  mov     rcx, rsi
0x180044566  call    ?HasSystemKeywordType@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBA_NW4SystemKeywordType@3@@Z; WindowsPerformanceRecorder::CETWProperties::CEventSession::HasSystemKeywordType(WindowsPerformanceRecorder::SystemKeywordType)
0x18004456b  mov     r15b, al
0x18004456e  mov     edx, 3
0x180044573  mov     rcx, rsi
0x180044576  call    ?HasSystemKeywordType@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBA_NW4SystemKeywordType@3@@Z; WindowsPerformanceRecorder::CETWProperties::CEventSession::HasSystemKeywordType(WindowsPerformanceRecorder::SystemKeywordType)
0x18004457b  mov     r12b, al
0x18004457e  mov     [rsp+0D8h+var_98], rbx
0x180044583  test    r11b, r11b
0x180044586  jz      short loc_1800445CB
0x180044588  mov     [rsp+0D8h+var_A8], edi
0x18004458c  lea     rcx, [rsi+60h]
0x180044590  lea     rdx, [rsp+0D8h+var_A8]
0x180044595  call    ?at@?$map@W4SystemKeywordType@WindowsPerformanceRecorder@@V?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@U?$less@W4SystemKeywordType@WindowsPerformanceRecorder@@@4@V?$allocator@U?$pair@$$CBW4SystemKeywordType@WindowsPerformanceRecorder@@V?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@@std@@@4@@std@@QEBAAEBV?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@2@AEBW4SystemKeywordType@WindowsPerformanceRecorder@@@Z; std::map<WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>::at(WindowsPerformanceRecorder::SystemKeywordType const &)
0x18004459a  mov     r14, rax
0x18004459d  lea     rdx, aCapturestateon_1; "CaptureStateOnStart"
0x1800445a4  mov     rcx, rbx; this
0x1800445a7  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x1800445ac  mov     rdx, r14
0x1800445af  lea     rcx, [rsp+0D8h+var_98]
0x1800445b4  call    _lambda_6fa3425b4c07c34abf7b329463000c6f___operator__
0x1800445b9  lea     rdx, aCapturestateon_1; "CaptureStateOnStart"
0x1800445c0  mov     rcx, rbx; this
0x1800445c3  call    ?End@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::End(ushort const *)
0x1800445c8  xor     r14d, r14d
0x1800445cb  test    r15b, r15b
0x1800445ce  jz      short loc_180044617
0x1800445d0  mov     [rsp+0D8h+var_A8], 2
0x1800445d8  lea     rcx, [rsi+60h]
0x1800445dc  lea     rdx, [rsp+0D8h+var_A8]
0x1800445e1  call    ?at@?$map@W4SystemKeywordType@WindowsPerformanceRecorder@@V?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@U?$less@W4SystemKeywordType@WindowsPerformanceRecorder@@@4@V?$allocator@U?$pair@$$CBW4SystemKeywordType@WindowsPerformanceRecorder@@V?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@@std@@@4@@std@@QEBAAEBV?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@2@AEBW4SystemKeywordType@WindowsPerformanceRecorder@@@Z; std::map<WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>::at(WindowsPerformanceRecorder::SystemKeywordType const &)
0x1800445e6  mov     r14, rax
0x1800445e9  lea     rdx, aCapturestateon_0; "CaptureStateOnSave"
0x1800445f0  mov     rcx, rbx; this
0x1800445f3  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x1800445f8  mov     rdx, r14
0x1800445fb  lea     rcx, [rsp+0D8h+var_98]
0x180044600  call    _lambda_6fa3425b4c07c34abf7b329463000c6f___operator__
0x180044605  lea     rdx, aCapturestateon_0; "CaptureStateOnSave"
0x18004460c  mov     rcx, rbx; this
0x18004460f  call    ?End@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::End(ushort const *)
0x180044614  xor     r14d, r14d
0x180044617  mov     r15d, 3
0x18004461d  test    r12b, r12b
0x180044620  jz      short loc_180044663
0x180044622  mov     [rsp+0D8h+var_A8], r15d
0x180044627  lea     rcx, [rsi+60h]
0x18004462b  lea     rdx, [rsp+0D8h+var_A8]
0x180044630  call    ?at@?$map@W4SystemKeywordType@WindowsPerformanceRecorder@@V?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@U?$less@W4SystemKeywordType@WindowsPerformanceRecorder@@@4@V?$allocator@U?$pair@$$CBW4SystemKeywordType@WindowsPerformanceRecorder@@V?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@@std@@@4@@std@@QEBAAEBV?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@2@AEBW4SystemKeywordType@WindowsPerformanceRecorder@@@Z; std::map<WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>::at(WindowsPerformanceRecorder::SystemKeywordType const &)
0x180044635  mov     rsi, rax
0x180044638  lea     rdx, aCapturestateon_2; "CaptureStateOnDemand"
0x18004463f  mov     rcx, rbx; this
0x180044642  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x180044647  mov     rdx, rsi
0x18004464a  lea     rcx, [rsp+0D8h+var_98]
0x18004464f  call    _lambda_6fa3425b4c07c34abf7b329463000c6f___operator__
0x180044654  lea     rdx, aCapturestateon_2; "CaptureStateOnDemand"
0x18004465b  mov     rcx, rbx; this
0x18004465e  call    ?End@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::End(ushort const *)
0x180044663  lea     r12, [r13+4]
0x180044667  mov     rsi, r12
0x18004466a  mov     ecx, r14d
0x18004466d  movzx   eax, word ptr [r13+2]
0x180044672  cmp     ecx, eax
0x180044674  jge     loc_1800447C2
0x18004467a  cmp     [rsi+2], r15w
0x18004467f  jnz     loc_180044873
0x180044685  lea     rdx, aStacks; "Stacks"
0x18004468c  mov     rcx, rbx; this
0x18004468f  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x180044694  movzx   r15d, word ptr [rsi]
0x180044698  sub     r15, rdi
0x18004469b  cmp     r14, r15
0x18004469e  jnb     loc_180044778
0x1800446a4  xor     ecx, ecx
0x1800446a6  cmp     rcx, 0BCh
0x1800446ad  jnb     loc_180044743
0x1800446b3  lea     r13, [rcx+rcx*2]
0x1800446b7  lea     rax, __ImageBase
0x1800446be  movzx   eax, ds:rva word_18008D968[rax+r13*8]
0x1800446c7  cmp     [rsi+r14*4+4], eax
0x1800446cc  jnz     short loc_18004473B
0x1800446ce  lea     rdx, aStack; "Stack"
0x1800446d5  mov     rcx, rbx; this
0x1800446d8  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x1800446dd  lea     rax, __ImageBase
0x1800446e4  mov     r8, ds:rva ?sc_Stacks@CSystemProviderElement@WindowsPerformanceRecorder@@2QBUCStack@CBaseProfileElement@2@B[rax+r13*8]; unsigned __int16 *
0x1800446ec  lea     rdx, aValue; "Value"
0x1800446f3  mov     rcx, rbx; this
0x1800446f6  call    ?Attr@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG0@Z; WindowsPerformanceRecorder::CXmlWriter::Attr(ushort const *,ushort const *)
0x1800446fb  add     dword ptr [rbx+14h], 0FFFFFFFEh
0x1800446ff  cmp     byte ptr [rbx+10h], 0
0x180044703  jnz     short loc_180044726
0x180044705  lea     rcx, [rsp+0D8h+pExceptionObject]; this
0x18004470d  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x180044712  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x180044719  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180044721  call    _CxxThrowException_0
0x180044726  lea     rdx, asc_180094A18; " />\n"
0x18004472d  mov     rcx, rbx
0x180044730  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180044735  mov     byte ptr [rbx+10h], 0
0x180044739  jmp     short loc_180044770
0x18004473b  add     rcx, rdi
0x18004473e  jmp     loc_1800446A6
0x180044743  lea     rdx, aCustomstack; "CustomStack"
0x18004474a  mov     rcx, rbx; this
0x18004474d  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x180044752  mov     r8d, [rsi+r14*4+4]; unsigned int
0x180044757  lea     rdx, aValue; "Value"
0x18004475e  mov     rcx, rbx; this
0x180044761  call    ?AttrHex@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBGK@Z; WindowsPerformanceRecorder::CXmlWriter::AttrHex(ushort const *,ulong)
0x180044766  xor     edx, edx; unsigned __int16 *
0x180044768  mov     rcx, rbx; this
0x18004476b  call    ?End@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::End(ushort const *)
0x180044770  add     r14, rdi
0x180044773  jmp     loc_18004469B
0x180044778  add     dword ptr [rbx+14h], 0FFFFFFFEh
0x18004477c  xor     r14d, r14d
0x18004477f  mov     rcx, rbx
0x180044782  cmp     [rbx+10h], r14b
0x180044786  jnz     short loc_1800447AD
0x180044788  lea     rax, aStacks; "Stacks"
0x18004478f  mov     [rsp+0D8h+var_B8], rax
0x180044794  lea     r9, LocaleName
0x18004479b  mov     r8d, [rbx+14h]
0x18004479f  lea     rdx, aWsWs_3; "%*ws</%ws>\n"
0x1800447a6  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800447ab  jmp     short loc_1800447B9
0x1800447ad  lea     rdx, asc_180094A18; " />\n"
0x1800447b4  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800447b9  mov     [rbx+10h], r14b
0x1800447bd  mov     r13, [rsp+0D8h+var_A0]
0x1800447c2  mov     ecx, r14d
0x1800447c5  movzx   eax, word ptr [r13+2]
0x1800447ca  cmp     ecx, eax
  ... truncated ...
```
