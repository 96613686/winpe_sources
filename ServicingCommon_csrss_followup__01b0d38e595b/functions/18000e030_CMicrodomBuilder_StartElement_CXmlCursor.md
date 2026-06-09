# CMicrodomBuilder::StartElement(CXmlCursor *)

- ea: `0x18000e030`
- end: `0x18000e5e6`
- name: `?StartElement@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@@Z`
- size: `1462`
- prototype: `__int64 __fastcall(CMicrodomBuilder *__hidden this, struct CXmlCursor *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ece0`

## callees

- `0x180003bb8`
- `0x180009820`
- `0x18000d128`
- `0x18000d75c`
- `0x18000d7fc`
- `0x18000d8c0`
- `0x18000e030`
- `0x18000e5ec`
- `0x18000eae0`
- `0x1800217cc`
- `0x18002d2b0`
- `0x18005dd10`
- `0x18005de2c`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x18000e4dc`
- `ntdll!RtlRaiseStatus` at `0x18000e563`
- `ntdll!RtlRaiseStatus` at `0x18000e4dc`
- `ntdll!RtlRaiseStatus` at `0x18000e563`

## string_xrefs

- `0x18000e48e`: `onecore\base\xml\udom_builder.cpp`
- `0x18000e570`: `onecore\base\xml\udom_builder.cpp`
- `0x18000e5ab`: `onecore\base\xml\udom_builder.cpp`

## pseudocode

```c
__int64 __fastcall CMicrodomBuilder::StartElement(CMicrodomBuilder *this, struct CXmlCursor *a2)
{
  bool v3; // zf
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rdi
  __int64 v8; // rdi
  int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // eax
  __int64 result; // rax
  _QWORD *v13; // r8
  void *v14; // r9
  struct _RTL_GROWING_LIST_CHUNK *v15; // rax
  __int64 v16; // rdx
  unsigned int i; // r14d
  struct _RTL_GROWING_LIST *v18; // rdi
  unsigned int v19; // eax
  char *v20; // r12
  __int64 v21; // rax
  NTSTATUS ChunkForElementIndex; // eax
  __int64 v23; // rax
  __int64 v24; // rdi
  int v25; // edx
  unsigned int v26; // edx
  unsigned int v27; // ecx
  int v28; // eax
  struct _RTL_GROWING_LIST_CHUNK *v29; // [rsp+38h] [rbp-29h] BYREF
  __int64 v30; // [rsp+40h] [rbp-21h] BYREF
  int v31; // [rsp+48h] [rbp-19h]
  __int128 v32; // [rsp+50h] [rbp-11h] BYREF
  __int64 v33; // [rsp+60h] [rbp-1h]
  const char *v34; // [rsp+68h] [rbp+7h]
  unsigned __int64 v35; // [rsp+70h] [rbp+Fh] BYREF
  int v36; // [rsp+78h] [rbp+17h] BYREF

  v3 = *((_DWORD *)a2 + 2282) == 3;
  v36 = 0;
  if ( !v3 )
    RtlRaiseStatus(-1073741595);
  v5 = (_QWORD *)*((_QWORD *)this + 156);
  v30 = 0;
  v31 = 0;
  if ( (!v5 || *v5 == v5[1])
    && !Windows::Rtl::UniformObjectPool<CMicrodomBuilder::CXmlStreamObject>::AllocateNextCell((char *)this + 1248) )
  {
    goto LABEL_53;
  }
  v6 = *((_QWORD *)this + 156);
  v7 = 144LL * *(_QWORD *)(v6 + 8);
  v3 = *(_QWORD *)(v6 + 16) + v7 == 0;
  v8 = *(_QWORD *)(v6 + 16) + v7;
  v29 = (struct _RTL_GROWING_LIST_CHUNK *)(v8 + 16);
  if ( v3 )
  {
    v29 = (struct _RTL_GROWING_LIST_CHUNK *)(v8 + 16);
  }
  else
  {
    *(_QWORD *)(v8 + 16) = 0;
    *(_QWORD *)v8 = 0;
    *(_QWORD *)(v8 + 8) = 0;
    *(_QWORD *)(v8 + 40) = 0;
    *(_QWORD *)(v8 + 24) = 0;
    *(_QWORD *)(v8 + 32) = 0;
    *(_QWORD *)(v8 + 64) = 0;
    *(_QWORD *)(v8 + 72) = 0;
    *(_QWORD *)(v8 + 80) = 0;
    *(_QWORD *)(v8 + 104) = 0;
    *(_QWORD *)(v8 + 56) = v8 + 48;
    *(_QWORD *)(v8 + 48) = v8 + 48;
    *(_QWORD *)(v8 + 96) = v8 + 88;
    *(_QWORD *)(v8 + 88) = v8 + 88;
  }
  ++*(_QWORD *)(*((_QWORD *)this + 156) + 8LL);
  if ( !v8 )
  {
LABEL_53:
    v33 = 1290;
    *(_QWORD *)&v32 = "onecore\\base\\xml\\udom_builder.cpp";
    *((_QWORD *)&v32 + 1) = "CMicrodomBuilder::StartElement";
    v34 = "NewElement = this->AllocateStreamObject()";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
             &v36,
             &v32);
  }
  v9 = *((_DWORD *)this + 324);
  *((_DWORD *)this + 324) = v9 + 1;
  *(_DWORD *)(v8 + 72) = v9;
  v10 = *((_DWORD *)a2 + 2314);
  *(_DWORD *)(v8 + 80) = v10;
  v11 = *((_DWORD *)a2 + 2315);
  *(_DWORD *)(v8 + 84) = v11;
  if ( v10 <= v11 )
    v10 = v11;
  if ( *((_DWORD *)this + 325) > v10 )
    v10 = *((_DWORD *)this + 325);
  *((_DWORD *)this + 325) = v10;
  *(_DWORD *)(v8 + 112) = 16;
  result = CMicrodomBuilder::AddStringsForElement(
             this,
             a2,
             (struct CXmlCursor *)((char *)a2 + 9208),
             (struct CXmlCursor *)((char *)a2 + 9232),
             (struct CXmlCursor *)((char *)a2 + 9184),
             (struct CMicrodomBuilder::ThreeStringIdPair *)&v30);
  if ( (int)result >= 0 )
  {
    *(_DWORD *)(v8 + 120) = v30;
    *(_DWORD *)(v8 + 116) = HIDWORD(v30);
    *(_DWORD *)(v8 + 124) = v31;
    *(_QWORD *)(v8 + 64) = *((_QWORD *)this + 157);
    *(_QWORD *)(v8 + 8) = *((_QWORD *)this + 159);
    *(_QWORD *)v8 = (char *)this + 1264;
    **((_QWORD **)this + 159) = v8;
    v15 = v29;
    *((_QWORD *)this + 159) = v8;
    *(_QWORD *)v15 = (char *)this + 1264;
    ++*((_QWORD *)this + 161);
    v16 = *((_QWORD *)this + 157);
    if ( v16 )
    {
      v13 = *(_QWORD **)(v16 + 96);
      if ( *v13 != v16 + 88 )
LABEL_50:
        __fastfail(3u);
      *(_QWORD *)(v8 + 48) = v16 + 88;
      *(_QWORD *)(v8 + 56) = v13;
      *v13 = v8 + 48;
      *(_QWORD *)(v16 + 96) = v8 + 48;
      ++*(_QWORD *)(v16 + 104);
    }
    *((_QWORD *)this + 157) = v8;
    for ( i = 0; ; ++i )
    {
      if ( i == *((_DWORD *)a2 + 2316) )
      {
        result = CMicrodomBuilder::InsertDefaultAttributes(this);
        if ( (int)result < 0 )
          return result;
        if ( !*((_BYTE *)a2 + 9268) )
          return 0;
        v21 = Windows::Rtl::UniformObjectPool<CMicrodomBuilder::CXmlStreamObject>::Allocate((char *)this + 1248);
        if ( v21 )
        {
          *(_DWORD *)(v21 + 112) = 196612;
          *(_QWORD *)(v21 + 8) = *((_QWORD *)this + 159);
          *(_QWORD *)v21 = (char *)this + 1264;
          **((_QWORD **)this + 159) = v21;
          *((_QWORD *)this + 159) = v21;
          *(_QWORD *)(v21 + 16) = (char *)this + 1264;
          ++*((_QWORD *)this + 161);
          *((_QWORD *)this + 157) = *(_QWORD *)(*((_QWORD *)this + 157) + 64LL);
          return 0;
        }
        v33 = 1401;
        *(_QWORD *)&v32 = "onecore\\base\\xml\\udom_builder.cpp";
        *((_QWORD *)&v32 + 1) = "CMicrodomBuilder::StartElement";
        v34 = "CloserElement = this->AllocateStreamObject()";
        return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
                 &v36,
                 &v32);
      }
      v18 = (struct CXmlCursor *)((char *)a2 + 3456);
      if ( a2 == (struct CXmlCursor *)-3456LL )
      {
        v20 = 0;
        ChunkForElementIndex = RtlXmlReportErrorFunction(-1073741811, v16, (unsigned int)v13, v14);
        goto LABEL_29;
      }
      v19 = *((_DWORD *)a2 + 869);
      if ( i < v19 && v19 )
      {
        v20 = (char *)(*((_QWORD *)a2 + 435) + *((_QWORD *)a2 + 433) * i);
        goto LABEL_30;
      }
      v29 = 0;
      v35 = 0;
      ChunkForElementIndex = RtlpFindChunkForElementIndex(v18, i, &v29, &v35);
      if ( ChunkForElementIndex < 0 )
      {
        v20 = 0;
        if ( ChunkForElementIndex != -1073741275 )
          goto LABEL_29;
        ChunkForElementIndex = RtlpExpandGrowingList(v18, i);
        if ( ChunkForElementIndex < 0
          || (ChunkForElementIndex = RtlpFindChunkForElementIndex(v18, i, &v29, &v35), ChunkForElementIndex < 0) )
        {
LABEL_51:
          RtlRaiseStatus(ChunkForElementIndex);
        }
      }
      v20 = (char *)v29 + *((_QWORD *)a2 + 433) * v35 + 16;
LABEL_29:
      if ( ChunkForElementIndex < 0 )
        goto LABEL_51;
LABEL_30:
      v23 = Windows::Rtl::UniformObjectPool<CMicrodomBuilder::CXmlStreamObject>::Allocate((char *)this + 1248);
      v24 = v23;
      if ( !v23 )
      {
        v33 = 1339;
        *(_QWORD *)&v32 = "onecore\\base\\xml\\udom_builder.cpp";
        *((_QWORD *)&v32 + 1) = "CMicrodomBuilder::StartElement";
        v34 = "NewAttribute = this->AllocateStreamObject()";
        RtlReportErrorOrigination(&v32, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
        return 3221225495LL;
      }
      v25 = *((_DWORD *)this + 324);
      *((_DWORD *)this + 324) = v25 + 1;
      *(_DWORD *)(v23 + 72) = v25;
      v26 = *((_DWORD *)v20 + 24);
      *(_DWORD *)(v23 + 80) = v26;
      v27 = *((_DWORD *)v20 + 25);
      *(_DWORD *)(v23 + 84) = v27;
      if ( v26 <= v27 )
        v26 = v27;
      if ( *((_DWORD *)this + 325) > v26 )
        v26 = *((_DWORD *)this + 325);
      *((_DWORD *)this + 325) = v26;
      ++*(_DWORD *)(*((_QWORD *)this + 157) + 76LL);
      *(_DWORD *)(v23 + 112) = 65560;
      *(_BYTE *)(v23 + 132) = 1;
      result = CMicrodomBuilder::AddStringsForElement(
                 this,
                 a2,
                 (const struct _XML_EXTENT *)(v20 + 24),
                 (const struct _XML_EXTENT *)(v20 + 72),
                 (const struct _XML_EXTENT *)v20,
                 (struct CMicrodomBuilder::ThreeStringIdPair *)&v30);
      if ( (int)result < 0 )
        return result;
      *(_DWORD *)(v24 + 120) = v30;
      *(_DWORD *)(v24 + 116) = HIDWORD(v30);
      *(_DWORD *)(v24 + 124) = v31;
      v28 = *((_DWORD *)v20 + 17);
      *(_DWORD *)(v24 + 128) = -1;
      if ( v28 )
      {
        v33 = 0;
        v32 = 0;
        result = CXmlCursor::DecodeExtent((__int64)a2, (__int64 *)v20 + 6, (_QWORD *)this + 198, &v32);
        if ( (int)result < 0 )
          return result;
        result = CMicrodomBuilder::AddString(this, (const struct _LUTF8_STRING *)&v32, (unsigned int *)(v24 + 128));
        if ( (int)result < 0 )
          return result;
      }
      v16 = *((_QWORD *)this + 157);
      v13 = *(_QWORD **)(v16 + 96);
      if ( *v13 != v16 + 88 )
        goto LABEL_50;
      *(_QWORD *)(v24 + 48) = v16 + 88;
      *(_QWORD *)(v24 + 56) = v13;
      *v13 = v24 + 48;
      *(_QWORD *)(v16 + 96) = v24 + 48;
      ++*(_QWORD *)(v16 + 104);
      *(_QWORD *)(v24 + 8) = *((_QWORD *)this + 159);
      *(_QWORD *)v24 = (char *)this + 1264;
      **((_QWORD **)this + 159) = v24;
      *((_QWORD *)this + 159) = v24;
      *(_QWORD *)(v24 + 16) = (char *)this + 1264;
      ++*((_QWORD *)this + 161);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e030  mov     r11, rsp
0x18000e033  push    rbp
0x18000e034  push    rbx
0x18000e035  push    r13
0x18000e037  lea     rbp, [r11-5Fh]
0x18000e03b  sub     rsp, 0A0h
0x18000e042  mov     rax, cs:__security_cookie
0x18000e049  xor     rax, rsp
0x18000e04c  mov     [rbp+57h+var_38], rax
0x18000e050  xor     r10d, r10d
0x18000e053  mov     r13, rdx
0x18000e056  cmp     dword ptr [rdx+23A8h], 3
0x18000e05d  mov     rbx, rcx
0x18000e060  mov     [rbp+57h+var_40], r10d
0x18000e064  jnz     loc_18000E4D7
0x18000e06a  mov     rcx, [rcx+4E0h]
0x18000e071  xor     eax, eax
0x18000e073  mov     [r11+18h], rsi
0x18000e077  mov     [r11-20h], rdi
0x18000e07b  mov     [r11-28h], r12
0x18000e07f  mov     [r11-30h], r14
0x18000e083  mov     [rbp+57h+var_78], rax
0x18000e087  mov     [rbp+57h+var_70], eax
0x18000e08a  test    rcx, rcx
0x18000e08d  jz      short loc_18000E098
0x18000e08f  mov     rax, [rcx+8]
0x18000e093  cmp     [rcx], rax
0x18000e096  jnz     short loc_18000E0B0
0x18000e098  lea     rcx, [rbx+4E0h]
0x18000e09f  call    ?AllocateNextCell@?$UniformObjectPool@VCXmlStreamObject@CMicrodomBuilder@@@Rtl@Windows@@AEAAPEAXXZ; Windows::Rtl::UniformObjectPool<CMicrodomBuilder::CXmlStreamObject>::AllocateNextCell(void)
0x18000e0a4  test    rax, rax
0x18000e0a7  jz      loc_18000E5AB
0x18000e0ad  xor     r10d, r10d
0x18000e0b0  mov     rdx, [rbx+4E0h]
0x18000e0b7  mov     rax, [rdx+8]
0x18000e0bb  lea     rdi, [rax+rax*8]
0x18000e0bf  shl     rdi, 4
0x18000e0c3  add     rdi, [rdx+10h]
0x18000e0c7  lea     rax, [rdi+10h]
0x18000e0cb  mov     [rbp+57h+var_80], rax
0x18000e0cf  jz      loc_18000E485
0x18000e0d5  mov     [rax], r10
0x18000e0d8  lea     rax, [rdi+30h]
0x18000e0dc  mov     [rdi], r10
0x18000e0df  mov     [rdi+8], r10
0x18000e0e3  mov     [rdi+28h], r10
0x18000e0e7  mov     [rdi+18h], r10
0x18000e0eb  mov     [rdi+20h], r10
0x18000e0ef  mov     [rdi+40h], r10
0x18000e0f3  mov     qword ptr [rdi+48h], 0
0x18000e0fb  mov     qword ptr [rdi+50h], 0
0x18000e103  mov     [rdi+68h], r10
0x18000e107  mov     [rax+8], rax
0x18000e10b  mov     [rax], rax
0x18000e10e  lea     rax, [rdi+58h]
0x18000e112  mov     [rax+8], rax
0x18000e116  mov     [rax], rax
0x18000e119  mov     rax, [rbx+4E0h]
0x18000e120  inc     qword ptr [rax+8]
0x18000e124  test    rdi, rdi
0x18000e127  jz      loc_18000E5AB
0x18000e12d  mov     ecx, [rbx+510h]
0x18000e133  lea     rsi, [r13+23E0h]
0x18000e13a  lea     r9, [rsi+30h]; struct _XML_EXTENT *
0x18000e13e  mov     rdx, r13; struct CXmlCursor *
0x18000e141  lea     r8, [rsi+18h]; struct _XML_EXTENT *
0x18000e145  lea     eax, [rcx+1]
0x18000e148  mov     [rbx+510h], eax
0x18000e14e  mov     [rdi+48h], ecx
0x18000e151  mov     ecx, [rsi+48h]
0x18000e154  mov     [rdi+50h], ecx
0x18000e157  mov     eax, [rsi+4Ch]
0x18000e15a  cmp     ecx, eax
0x18000e15c  mov     [rdi+54h], eax
0x18000e15f  cmovbe  ecx, eax
0x18000e162  mov     eax, [rbx+514h]
0x18000e168  cmp     eax, ecx
0x18000e16a  cmova   ecx, eax
0x18000e16d  lea     rax, [rbp+57h+var_78]
0x18000e171  mov     [rbx+514h], ecx
0x18000e177  mov     rcx, rbx; this
0x18000e17a  mov     [rsp+28h], rax; struct CMicrodomBuilder::ThreeStringIdPair *
0x18000e17f  mov     [rsp+0B0h+var_90], rsi; struct _XML_EXTENT *
0x18000e184  mov     dword ptr [rdi+70h], 10h
0x18000e18b  call    ?AddStringsForElement@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@AEBU_XML_EXTENT@@11PEAUThreeStringIdPair@1@@Z; CMicrodomBuilder::AddStringsForElement(CXmlCursor *,_XML_EXTENT const &,_XML_EXTENT const &,_XML_EXTENT const &,CMicrodomBuilder::ThreeStringIdPair *)
0x18000e190  test    eax, eax
0x18000e192  js      loc_18000E244
0x18000e198  mov     eax, dword ptr [rbp+57h+var_78]
0x18000e19b  mov     [rdi+78h], eax
0x18000e19e  mov     eax, dword ptr [rbp+57h+var_78+4]
0x18000e1a1  mov     [rdi+74h], eax
0x18000e1a4  mov     eax, [rbp+57h+var_70]
0x18000e1a7  mov     [rdi+7Ch], eax
0x18000e1aa  mov     rax, [rbx+4E8h]
0x18000e1b1  mov     [rdi+40h], rax
0x18000e1b5  mov     [rsp+0B0h+var_30], r15
0x18000e1bd  lea     r15, [rbx+4F0h]
0x18000e1c4  mov     rax, [r15+8]
0x18000e1c8  mov     [rdi+8], rax
0x18000e1cc  mov     [rdi], r15
0x18000e1cf  mov     rax, [r15+8]
0x18000e1d3  mov     [rax], rdi
0x18000e1d6  mov     rax, [rbp+57h+var_80]
0x18000e1da  mov     [r15+8], rdi
0x18000e1de  mov     [rax], r15
0x18000e1e1  inc     qword ptr [r15+18h]
0x18000e1e5  mov     rdx, [rbx+4E8h]; unsigned int
0x18000e1ec  test    rdx, rdx
0x18000e1ef  jz      short loc_18000E218
0x18000e1f1  mov     r8, [rdx+60h]; unsigned int
0x18000e1f5  lea     rcx, [rdx+58h]
0x18000e1f9  cmp     [r8], rcx
0x18000e1fc  jnz     loc_18000E55A
0x18000e202  lea     rax, [rdi+30h]
0x18000e206  mov     [rax], rcx
0x18000e209  mov     [rax+8], r8
0x18000e20d  mov     [r8], rax
0x18000e210  mov     [rcx+8], rax
0x18000e214  inc     qword ptr [rdx+68h]
0x18000e218  mov     [rbx+4E8h], rdi
0x18000e21f  xor     r14d, r14d
0x18000e222  cmp     r14d, [rsi+50h]
0x18000e226  jnz     short loc_18000E27D
0x18000e228  mov     rcx, rbx; this
0x18000e22b  call    ?InsertDefaultAttributes@CMicrodomBuilder@@AEAAJXZ; CMicrodomBuilder::InsertDefaultAttributes(void)
0x18000e230  test    eax, eax
0x18000e232  js      short loc_18000E23C
0x18000e234  cmp     byte ptr [rsi+54h], 0
0x18000e238  jnz     short loc_18000E2AF
0x18000e23a  xor     eax, eax
0x18000e23c  mov     r15, [rsp+0B0h+var_30]
0x18000e244  mov     r12, [rsp+0B0h+var_20]
0x18000e24c  mov     rdi, [rsp+98h]
0x18000e254  mov     rsi, [rsp+0B0h+arg_10]
0x18000e25c  mov     r14, [rsp+0B0h+var_28]
0x18000e264  mov     rcx, [rbp+57h+var_38]
0x18000e268  xor     rcx, rsp; StackCookie
0x18000e26b  call    __security_check_cookie
0x18000e270  add     rsp, 0A0h
0x18000e277  pop     r13
0x18000e279  pop     rbx
0x18000e27a  pop     rbp
0x18000e27b  retn
0x18000e27d  lea     rdi, [r13+0D80h]
0x18000e284  test    rdi, rdi
0x18000e287  jz      loc_18000E311
0x18000e28d  mov     eax, [rdi+14h]
0x18000e290  cmp     r14d, eax
0x18000e293  jnb     loc_18000E4E9
0x18000e299  test    eax, eax
0x18000e29b  jz      loc_18000E4E9
0x18000e2a1  mov     r12d, r14d
0x18000e2a4  imul    r12, [rdi+8]
0x18000e2a9  add     r12, [rdi+18h]
0x18000e2ad  jmp     short loc_18000E326
0x18000e2af  lea     rcx, [rbx+4E0h]
0x18000e2b6  call    ?Allocate@?$UniformObjectPool@VCXmlStreamObject@CMicrodomBuilder@@@Rtl@Windows@@QEAAPEAVCXmlStreamObject@CMicrodomBuilder@@XZ; Windows::Rtl::UniformObjectPool<CMicrodomBuilder::CXmlStreamObject>::Allocate(void)
0x18000e2bb  mov     rdx, rax
0x18000e2be  test    rax, rax
0x18000e2c1  jz      loc_18000E570
0x18000e2c7  mov     dword ptr [rax+70h], 30004h
0x18000e2ce  lea     rcx, [rbx+4F0h]
0x18000e2d5  mov     rax, [rcx+8]
0x18000e2d9  mov     [rdx+8], rax
0x18000e2dd  mov     [rdx], rcx
0x18000e2e0  mov     rax, [rcx+8]
0x18000e2e4  mov     [rax], rdx
0x18000e2e7  mov     [rcx+8], rdx
0x18000e2eb  mov     [rdx+10h], rcx
0x18000e2ef  mov     rax, [rcx+18h]
0x18000e2f3  inc     rax
0x18000e2f6  mov     [r15+18h], rax
0x18000e2fa  mov     rax, [rbx+4E8h]
0x18000e301  mov     rcx, [rax+40h]
0x18000e305  mov     [rbx+4E8h], rcx
0x18000e30c  jmp     loc_18000E23A
0x18000e311  xor     r12d, r12d
0x18000e314  mov     ecx, 0C000000Dh; int
0x18000e319  call    ?RtlXmlReportErrorFunction@@YAJJKKPEAX@Z; RtlXmlReportErrorFunction(long,ulong,ulong,void *)
0x18000e31e  test    eax, eax
0x18000e320  js      loc_18000E561
0x18000e326  lea     rcx, [rbx+4E0h]
0x18000e32d  call    ?Allocate@?$UniformObjectPool@VCXmlStreamObject@CMicrodomBuilder@@@Rtl@Windows@@QEAAPEAVCXmlStreamObject@CMicrodomBuilder@@XZ; Windows::Rtl::UniformObjectPool<CMicrodomBuilder::CXmlStreamObject>::Allocate(void)
0x18000e332  mov     rdi, rax
0x18000e335  test    rax, rax
0x18000e338  jz      loc_18000E48E
0x18000e33e  mov     edx, [rbx+510h]
0x18000e344  lea     r9, [r12+48h]; struct _XML_EXTENT *
0x18000e349  lea     r8, [r12+18h]; struct _XML_EXTENT *
0x18000e34e  lea     ecx, [rdx+1]
0x18000e351  mov     [rbx+510h], ecx
0x18000e357  mov     [rax+48h], edx
0x18000e35a  mov     edx, [r12+60h]
0x18000e35f  mov     [rax+50h], edx
0x18000e362  mov     ecx, [r12+64h]
0x18000e367  cmp     edx, ecx
0x18000e369  mov     [rax+54h], ecx
0x18000e36c  mov     eax, [rbx+514h]
0x18000e372  cmovbe  edx, ecx
0x18000e375  cmp     eax, edx
0x18000e377  mov     rcx, rbx; this
0x18000e37a  cmova   edx, eax
0x18000e37d  mov     [rbx+514h], edx
0x18000e383  mov     rdx, r13; struct CXmlCursor *
0x18000e386  mov     rax, [rbx+4E8h]
0x18000e38d  inc     dword ptr [rax+4Ch]
0x18000e390  lea     rax, [rbp+57h+var_78]
0x18000e394  mov     [rsp+28h], rax; struct CMicrodomBuilder::ThreeStringIdPair *
0x18000e399  mov     [rsp+0B0h+var_90], r12; struct _XML_EXTENT *
0x18000e39e  mov     dword ptr [rdi+70h], 10018h
0x18000e3a5  mov     byte ptr [rdi+84h], 1
0x18000e3ac  call    ?AddStringsForElement@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@AEBU_XML_EXTENT@@11PEAUThreeStringIdPair@1@@Z; CMicrodomBuilder::AddStringsForElement(CXmlCursor *,_XML_EXTENT const &,_XML_EXTENT const &,_XML_EXTENT const &,CMicrodomBuilder::ThreeStringIdPair *)
0x18000e3b1  test    eax, eax
0x18000e3b3  js      loc_18000E23C
0x18000e3b9  mov     eax, dword ptr [rbp+57h+var_78]
0x18000e3bc  lea     rdx, [r12+30h]
0x18000e3c1  mov     [rdi+78h], eax
0x18000e3c4  mov     eax, dword ptr [rbp+57h+var_78+4]
0x18000e3c7  mov     [rdi+74h], eax
0x18000e3ca  mov     eax, [rbp+57h+var_70]
0x18000e3cd  mov     [rdi+7Ch], eax
0x18000e3d0  mov     eax, [rdx+14h]
0x18000e3d3  mov     dword ptr [rdi+80h], 0FFFFFFFFh
0x18000e3dd  test    eax, eax
0x18000e3df  jnz     short loc_18000E43D
0x18000e3e1  mov     rdx, [rbx+4E8h]
0x18000e3e8  mov     r8, [rdx+60h]
0x18000e3ec  lea     rcx, [rdx+58h]
0x18000e3f0  cmp     [r8], rcx
0x18000e3f3  jnz     loc_18000E55A
0x18000e3f9  mov     [rdi+30h], rcx
0x18000e3fd  lea     rax, [rdi+30h]
0x18000e401  mov     [rax+8], r8
0x18000e405  mov     [r8], rax
0x18000e408  mov     [rcx+8], rax
0x18000e40c  lea     rcx, [rbx+4F0h]
0x18000e413  inc     qword ptr [rdx+68h]
0x18000e417  mov     rax, [rcx+8]
0x18000e41b  mov     [rdi+8], rax
0x18000e41f  mov     [rdi], rcx
0x18000e422  mov     rax, [rcx+8]
0x18000e426  mov     [rax], rdi
0x18000e429  mov     [rcx+8], rdi
0x18000e42d  mov     [rdi+10h], rcx
0x18000e431  inc     qword ptr [rcx+18h]
0x18000e435  inc     r14d
0x18000e438  jmp     loc_18000E222
0x18000e43d  xorps   xmm0, xmm0
0x18000e440  lea     r8, [rbx+630h]
0x18000e447  xor     eax, eax
0x18000e449  lea     r9, [rbp+57h+var_68]
0x18000e44d  mov     rcx, r13
0x18000e450  mov     [rbp+57h+var_58], rax
0x18000e454  movups  [rbp+57h+var_68], xmm0
0x18000e458  call    ?DecodeExtent@CXmlCursor@@QEAAJAEBU_XML_EXTENT@@PEAV?$Auto@U_LUTF8_STRING@@@Windows@@PEAU_LUTF8_STRING@@@Z; CXmlCursor::DecodeExtent(_XML_EXTENT const &,Windows::Auto<_LUTF8_STRING> *,_LUTF8_STRING *)
0x18000e45d  test    eax, eax
0x18000e45f  js      loc_18000E23C
0x18000e465  lea     r8, [rdi+80h]; unsigned int *
0x18000e46c  mov     rcx, rbx; this
0x18000e46f  lea     rdx, [rbp+57h+var_68]; struct _LUTF8_STRING *
0x18000e473  call    ?AddString@CMicrodomBuilder@@AEAAJAEBU_LUTF8_STRING@@PEAK@Z; CMicrodomBuilder::AddString(_LUTF8_STRING const &,ulong *)
0x18000e478  test    eax, eax
0x18000e47a  jns     loc_18000E3E1
0x18000e480  jmp     loc_18000E23C
0x18000e485  mov     [rbp+57h+var_80], rax
0x18000e489  jmp     loc_18000E119
0x18000e48e  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x18000e495  mov     [rbp+57h+var_58], 53Bh
0x18000e49d  mov     qword ptr [rbp+57h+var_68], rax
0x18000e4a1  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18000e4a8  lea     rax, aCmicrodombuild_17; "CMicrodomBuilder::StartElement"
0x18000e4af  mov     r8d, 0C0000017h
0x18000e4b5  mov     qword ptr [rbp+57h+var_68+8], rax
0x18000e4b9  lea     rcx, [rbp+57h+var_68]
0x18000e4bd  lea     rax, aNewattributeTh; "NewAttribute = this->AllocateStreamObje"...
0x18000e4c4  mov     [rbp+57h+var_50], rax
0x18000e4c8  call    RtlReportErrorOrigination
0x18000e4cd  mov     eax, 0C0000017h
0x18000e4d2  jmp     loc_18000E23C
0x18000e4d7  mov     ecx, 0C00000E5h; Status
0x18000e4dc  call    cs:__imp_RtlRaiseStatus
0x18000e4e3  nop     dword ptr [rax+rax+00h]
0x18000e4e8  int     3; Trap to Debugger
0x18000e4e9  lea     r9, [rbp+57h+var_48]; unsigned __int64 *
0x18000e4ed  mov     [rbp+57h+var_80], 0
0x18000e4f5  lea     r8, [rbp+57h+var_80]; struct _RTL_GROWING_LIST_CHUNK **
0x18000e4f9  mov     [rbp+57h+var_48], 0
0x18000e501  mov     edx, r14d; unsigned int
0x18000e504  mov     rcx, rdi; struct _RTL_GROWING_LIST *
0x18000e507  call    ?RtlpFindChunkForElementIndex@@YAJPEAU_RTL_GROWING_LIST@@KPEAPEAU_RTL_GROWING_LIST_CHUNK@@PEA_K@Z; RtlpFindChunkForElementIndex(_RTL_GROWING_LIST *,ulong,_RTL_GROWING_LIST_CHUNK * *,unsigned __int64 *)
0x18000e50c  test    eax, eax
0x18000e50e  jns     short loc_18000E544
0x18000e510  xor     r12d, r12d
0x18000e513  cmp     eax, 0C0000225h
0x18000e518  jnz     loc_18000E31E
0x18000e51e  mov     edx, r14d; unsigned int
0x18000e521  mov     rcx, rdi; struct _RTL_GROWING_LIST *
0x18000e524  call    ?RtlpExpandGrowingList@@YAJPEAU_RTL_GROWING_LIST@@K@Z; RtlpExpandGrowingList(_RTL_GROWING_LIST *,ulong)
0x18000e529  test    eax, eax
0x18000e52b  js      short loc_18000E561
  ... truncated ...
```
