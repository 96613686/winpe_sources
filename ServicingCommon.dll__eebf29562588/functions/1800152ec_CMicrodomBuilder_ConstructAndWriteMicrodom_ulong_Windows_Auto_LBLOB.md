# CMicrodomBuilder::ConstructAndWriteMicrodom(ulong,Windows::Auto<_LBLOB> *)

- ea: `0x1800152ec`
- end: `0x18001562a`
- name: `?ConstructAndWriteMicrodom@CMicrodomBuilder@@QEAAJKPEAV?$Auto@U_LBLOB@@@Windows@@@Z`
- size: `830`
- prototype: `__int64 __fastcall(CMicrodomBuilder *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180015630`

## callees

- `0x180002df0`
- `0x18000f088`
- `0x1800152ec`
- `0x180015c64`
- `0x180016090`
- `0x18001897c`
- `0x180018d80`
- `0x180019030`
- `0x18001f5d4`
- `0x1800293a0`
- `0x1800625e0`
- `0x180062790`
- `0x180062800`
- `0x180099cb0`

## string_xrefs

- `0x18001539c`: `onecore\base\xml\udom_builder.cpp`
- `0x180015435`: `onecore\base\xml\udom_builder.cpp`
- `0x180015491`: `onecore\base\xml\udom_builder.cpp`
- `0x1800154ed`: `onecore\base\xml\udom_builder.cpp`
- `0x180015549`: `onecore\base\xml\udom_builder.cpp`
- `0x18001559b`: `onecore\base\xml\udom_builder.cpp`
- `0x1800155cd`: `onecore\base\xml\udom_builder.cpp`
- `0x1800153b5`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x180015448`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x1800154a4`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x180015500`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x18001555c`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x1800155ae`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x1800155e6`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x180015453`: `BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToStringPool)`
- `0x1800154af`: `BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToDomLayout)`
- `0x18001550b`: `BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToDoctypeData)`
- `0x180015567`: `BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToPositionData)`
- `0x1800155b9`: `BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulTotalSize)`

## pseudocode

```c
__int64 __fastcall CMicrodomBuilder::ConstructAndWriteMicrodom(CMicrodomBuilder *this, __int64 a2, __int128 *a3)
{
  int v5; // r15d
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // r14
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // r8
  bool v10; // al
  __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  __int64 v13; // r8
  const char *v14; // rax
  __int64 result; // rax
  __int128 v16; // xmm0
  _DWORD *v17; // rbx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  const char *v23; // [rsp+20h] [rbp-50h] BYREF
  const char *v24; // [rsp+28h] [rbp-48h]
  __int64 v25; // [rsp+30h] [rbp-40h]
  const char *v26; // [rsp+38h] [rbp-38h]
  size_t Size[2]; // [rsp+40h] [rbp-30h] BYREF
  _DWORD *v28; // [rsp+50h] [rbp-20h]
  int v29; // [rsp+58h] [rbp-18h] BYREF

  v29 = 0;
  v5 = CMicrodomBuilder::DetermineStringTableSize(this);
  v6 = ((unsigned int)CMicrodomBuilder::GetXmlDomSize(this) + 3) & 0xFFFFFFFC;
  v7 = ((unsigned int)CMicrodomBuilder::GetDoctypeDataSize(this) + 3) & 0xFFFFFFFC;
  v8 = v6 + (((unsigned int)CMicrodomBuilder::GetLocationDataSize(this) + 3) & 0xFFFFFFFC);
  v9 = v7 + v8;
  v10 = v8 >= v6 && v9 >= v7;
  if ( !v10 || (v11 = ((v5 + 3) & 0xFFFFFFFC) + 24LL, v12 = v11 + v9, v11 + v9 < v9) )
  {
    v25 = 1024;
    v23 = "onecore\\base\\xml\\udom_builder.cpp";
    v13 = 3221225621LL;
    v24 = "CMicrodomBuilder::ConstructAndWriteMicrodom";
    v14 = "BUCL::Rtl::Add<SIZE_T>( sizeof(MICRODOM_HEADER), cbStringPoolSize, cbDomLayoutSize, cbPositionDataSize, cbDoct"
          "ypeDataSize, cbRequiredSize)";
    goto LABEL_28;
  }
  if ( v12 > 0xFFFFFFFF )
  {
    v25 = 1026;
    v23 = "onecore\\base\\xml\\udom_builder.cpp";
    v13 = 3221226539LL;
    v24 = "CMicrodomBuilder::ConstructAndWriteMicrodom";
    v14 = "cbRequiredSize <= BUCL::CMaximumInteger<ULONG>::Value";
LABEL_28:
    v26 = v14;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v29,
             &v23,
             v13);
  }
  if ( *((_QWORD *)a3 + 1) >= v12 || (result = RtlReallocateLBlob(0, v12, a3), (int)result >= 0) )
  {
    v16 = *a3;
    v28 = (_DWORD *)*((_QWORD *)a3 + 2);
    Size[1] = *((_QWORD *)&v16 + 1);
    LODWORD(Size[0]) = 0;
    memset(v28, 0, *((size_t *)&v16 + 1));
    v17 = v28;
    *v28 = 1682465869;
    Size[0] = (LODWORD(Size[0]) + 27) & 0xFFFFFFFC;
    v18 = BUCL::Rtl::ConvertInteger<unsigned __int64,unsigned long>(Size[0], v17 + 2);
    v13 = (unsigned int)v18;
    if ( v18 >= 0 )
    {
      result = CMicrodomBuilder::ProduceStringTable(this, (struct _LBLOB *)Size);
      if ( (int)result < 0 )
        return result;
      Size[0] = (LODWORD(Size[0]) + 3) & 0xFFFFFFFC;
      v19 = BUCL::Rtl::ConvertInteger<unsigned __int64,unsigned long>(Size[0], v17 + 3);
      v13 = (unsigned int)v19;
      if ( v19 >= 0 )
      {
        result = CMicrodomBuilder::WriteXmlDom(this, (struct _LBLOB *)Size);
        if ( (int)result < 0 )
          return result;
        Size[0] = (LODWORD(Size[0]) + 3) & 0xFFFFFFFC;
        v20 = BUCL::Rtl::ConvertInteger<unsigned __int64,unsigned long>(Size[0], v17 + 5);
        v13 = (unsigned int)v20;
        if ( v20 >= 0 )
        {
          result = CMicrodomBuilder::WriteDoctypeData(this, (struct _LBLOB *)Size);
          if ( (int)result < 0 )
            return result;
          Size[0] = (LODWORD(Size[0]) + 3) & 0xFFFFFFFC;
          v21 = BUCL::Rtl::ConvertInteger<unsigned __int64,unsigned long>(Size[0], v17 + 4);
          v13 = (unsigned int)v21;
          if ( v21 >= 0 )
          {
            result = CMicrodomBuilder::WriteLocationData(this, (struct _LBLOB *)Size);
            if ( (int)result < 0 )
              return result;
            v22 = BUCL::Rtl::ConvertInteger<unsigned __int64,unsigned long>(Size[0], v17 + 1);
            v13 = (unsigned int)v22;
            if ( v22 >= 0 )
            {
              *(_QWORD *)a3 = Size[0];
              return 0;
            }
            v25 = 1089;
            v23 = "onecore\\base\\xml\\udom_builder.cpp";
            v24 = "CMicrodomBuilder::ConstructAndWriteMicrodom";
            v14 = "BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulTotalSize)";
          }
          else
          {
            v25 = 1082;
            v23 = "onecore\\base\\xml\\udom_builder.cpp";
            v24 = "CMicrodomBuilder::ConstructAndWriteMicrodom";
            v14 = "BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToPositionData)";
          }
        }
        else
        {
          v25 = 1073;
          v23 = "onecore\\base\\xml\\udom_builder.cpp";
          v24 = "CMicrodomBuilder::ConstructAndWriteMicrodom";
          v14 = "BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToDoctypeData)";
        }
      }
      else
      {
        v25 = 1064;
        v23 = "onecore\\base\\xml\\udom_builder.cpp";
        v24 = "CMicrodomBuilder::ConstructAndWriteMicrodom";
        v14 = "BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToDomLayout)";
      }
    }
    else
    {
      v25 = 1055;
      v23 = "onecore\\base\\xml\\udom_builder.cpp";
      v24 = "CMicrodomBuilder::ConstructAndWriteMicrodom";
      v14 = "BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToStringPool)";
    }
    goto LABEL_28;
  }
  return result;
}

```

## disassembly

```asm
0x1800152ec  mov     [rsp-28h+arg_8], rbx
0x1800152f1  push    rbp
0x1800152f2  push    rsi
0x1800152f3  push    rdi
0x1800152f4  push    r14
0x1800152f6  push    r15
0x1800152f8  mov     rbp, rsp
0x1800152fb  sub     rsp, 70h
0x1800152ff  mov     rax, cs:__security_cookie
0x180015306  xor     rax, rsp
0x180015309  mov     [rbp+var_10], rax
0x18001530d  mov     rsi, r8
0x180015310  mov     [rbp+var_18], 0
0x180015317  mov     rdi, rcx
0x18001531a  call    ?DetermineStringTableSize@CMicrodomBuilder@@AEBA_KXZ; CMicrodomBuilder::DetermineStringTableSize(void)
0x18001531f  mov     rcx, rdi; this
0x180015322  mov     r15, rax
0x180015325  call    ?GetXmlDomSize@CMicrodomBuilder@@AEBA_KXZ; CMicrodomBuilder::GetXmlDomSize(void)
0x18001532a  mov     rcx, rdi; this
0x18001532d  lea     ebx, [rax+3]
0x180015330  and     rbx, 0FFFFFFFFFFFFFFFCh
0x180015334  call    ?GetDoctypeDataSize@CMicrodomBuilder@@AEBA_KXZ; CMicrodomBuilder::GetDoctypeDataSize(void)
0x180015339  mov     rcx, rdi; this
0x18001533c  lea     r14d, [rax+3]
0x180015340  and     r14, 0FFFFFFFFFFFFFFFCh
0x180015344  call    ?GetLocationDataSize@CMicrodomBuilder@@AEBA_KXZ; CMicrodomBuilder::GetLocationDataSize(void)
0x180015349  add     eax, 3
0x18001534c  and     rax, 0FFFFFFFFFFFFFFFCh
0x180015350  add     rax, rbx
0x180015353  lea     r8, [r14+rax]
0x180015357  cmp     rax, rbx
0x18001535a  jb      short loc_180015365
0x18001535c  cmp     r8, r14
0x18001535f  jb      short loc_180015365
0x180015361  mov     al, 1
0x180015363  jmp     short loc_180015367
0x180015365  xor     al, al
0x180015367  test    al, al
0x180015369  jz      loc_1800155CD
0x18001536f  lea     ecx, [r15+3]
0x180015373  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180015377  add     rcx, 18h
0x18001537b  cmp     rcx, 18h
0x18001537f  jb      loc_1800155CD
0x180015385  lea     rdx, [rcx+r8]
0x180015389  cmp     rdx, r8
0x18001538c  jb      loc_1800155CD
0x180015392  mov     eax, 0FFFFFFFFh
0x180015397  cmp     rdx, rax
0x18001539a  jbe     short loc_1800153CC
0x18001539c  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x1800153a3  mov     [rbp+var_40], 402h
0x1800153ab  mov     [rbp+var_50], rax
0x1800153af  mov     r8d, 0C000042Bh
0x1800153b5  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x1800153bc  mov     [rbp+var_48], rax
0x1800153c0  lea     rax, aCbrequiredsize; "cbRequiredSize <= BUCL::CMaximumInteger"...
0x1800153c7  jmp     loc_1800155F8
0x1800153cc  cmp     [rsi+8], rdx
0x1800153d0  jnb     short loc_1800153E4
0x1800153d2  mov     r8, rsi
0x1800153d5  xor     ecx, ecx
0x1800153d7  call    RtlReallocateLBlob
0x1800153dc  test    eax, eax
0x1800153de  js      loc_180015609
0x1800153e4  movsd   xmm1, qword ptr [rsi+10h]
0x1800153e9  xor     edx, edx; Val
0x1800153eb  movups  xmm0, xmmword ptr [rsi]
0x1800153ee  movq    rcx, xmm1; void *
0x1800153f3  movsd   [rbp+var_20], xmm1
0x1800153f8  movups  xmmword ptr [rbp+Size], xmm0
0x1800153fc  mov     r8, [rbp+Size+8]; Size
0x180015400  mov     [rbp+Size], 0
0x180015408  call    memset
0x18001540d  mov     rbx, [rbp+var_20]
0x180015411  mov     dword ptr [rbx], 6448644Dh
0x180015417  lea     rdx, [rbx+8]
0x18001541b  mov     ecx, dword ptr [rbp+Size]
0x18001541e  add     ecx, 1Bh
0x180015421  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180015425  mov     [rbp+Size], rcx
0x180015429  call    ??$ConvertInteger@_KK@Rtl@BUCL@@YAJ_KAEAK@Z; BUCL::Rtl::ConvertInteger<unsigned __int64,ulong>(unsigned __int64,ulong &)
0x18001542e  mov     r8d, eax
0x180015431  test    eax, eax
0x180015433  jns     short loc_18001545F
0x180015435  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x18001543c  mov     [rbp+var_40], 41Fh
0x180015444  mov     [rbp+var_50], rax
0x180015448  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x18001544f  mov     [rbp+var_48], rax
0x180015453  lea     rax, aBuclRtlConvert_5; "BUCL::Rtl::ConvertInteger(WriteBlock.Le"...
0x18001545a  jmp     loc_1800155F8
0x18001545f  lea     rdx, [rbp+Size]; struct _LBLOB *
0x180015463  mov     rcx, rdi; this
0x180015466  call    ?ProduceStringTable@CMicrodomBuilder@@AEBAJPEAU_LBLOB@@@Z; CMicrodomBuilder::ProduceStringTable(_LBLOB *)
0x18001546b  test    eax, eax
0x18001546d  js      loc_180015609
0x180015473  mov     ecx, dword ptr [rbp+Size]
0x180015476  lea     rdx, [rbx+0Ch]
0x18001547a  add     ecx, 3
0x18001547d  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180015481  mov     [rbp+Size], rcx
0x180015485  call    ??$ConvertInteger@_KK@Rtl@BUCL@@YAJ_KAEAK@Z; BUCL::Rtl::ConvertInteger<unsigned __int64,ulong>(unsigned __int64,ulong &)
0x18001548a  mov     r8d, eax
0x18001548d  test    eax, eax
0x18001548f  jns     short loc_1800154BB
0x180015491  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x180015498  mov     [rbp+var_40], 428h
0x1800154a0  mov     [rbp+var_50], rax
0x1800154a4  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x1800154ab  mov     [rbp+var_48], rax
0x1800154af  lea     rax, aBuclRtlConvert_4; "BUCL::Rtl::ConvertInteger(WriteBlock.Le"...
0x1800154b6  jmp     loc_1800155F8
0x1800154bb  lea     rdx, [rbp+Size]; struct _LBLOB *
0x1800154bf  mov     rcx, rdi; this
0x1800154c2  call    ?WriteXmlDom@CMicrodomBuilder@@AEAAJPEAU_LBLOB@@@Z; CMicrodomBuilder::WriteXmlDom(_LBLOB *)
0x1800154c7  test    eax, eax
0x1800154c9  js      loc_180015609
0x1800154cf  mov     ecx, dword ptr [rbp+Size]
0x1800154d2  lea     rdx, [rbx+14h]
0x1800154d6  add     ecx, 3
0x1800154d9  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800154dd  mov     [rbp+Size], rcx
0x1800154e1  call    ??$ConvertInteger@_KK@Rtl@BUCL@@YAJ_KAEAK@Z; BUCL::Rtl::ConvertInteger<unsigned __int64,ulong>(unsigned __int64,ulong &)
0x1800154e6  mov     r8d, eax
0x1800154e9  test    eax, eax
0x1800154eb  jns     short loc_180015517
0x1800154ed  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x1800154f4  mov     [rbp+var_40], 431h
0x1800154fc  mov     [rbp+var_50], rax
0x180015500  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x180015507  mov     [rbp+var_48], rax
0x18001550b  lea     rax, aBuclRtlConvert_9; "BUCL::Rtl::ConvertInteger(WriteBlock.Le"...
0x180015512  jmp     loc_1800155F8
0x180015517  lea     rdx, [rbp+Size]; struct _LBLOB *
0x18001551b  mov     rcx, rdi; this
0x18001551e  call    ?WriteDoctypeData@CMicrodomBuilder@@AEAAJPEAU_LBLOB@@@Z; CMicrodomBuilder::WriteDoctypeData(_LBLOB *)
0x180015523  test    eax, eax
0x180015525  js      loc_180015609
0x18001552b  mov     ecx, dword ptr [rbp+Size]
0x18001552e  lea     rdx, [rbx+10h]
0x180015532  add     ecx, 3
0x180015535  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180015539  mov     [rbp+Size], rcx
0x18001553d  call    ??$ConvertInteger@_KK@Rtl@BUCL@@YAJ_KAEAK@Z; BUCL::Rtl::ConvertInteger<unsigned __int64,ulong>(unsigned __int64,ulong &)
0x180015542  mov     r8d, eax
0x180015545  test    eax, eax
0x180015547  jns     short loc_180015573
0x180015549  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x180015550  mov     [rbp+var_40], 43Ah
0x180015558  mov     [rbp+var_50], rax
0x18001555c  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x180015563  mov     [rbp+var_48], rax
0x180015567  lea     rax, aBuclRtlConvert_1; "BUCL::Rtl::ConvertInteger(WriteBlock.Le"...
0x18001556e  jmp     loc_1800155F8
0x180015573  lea     rdx, [rbp+Size]; struct _LBLOB *
0x180015577  mov     rcx, rdi; this
0x18001557a  call    ?WriteLocationData@CMicrodomBuilder@@AEAAJPEAU_LBLOB@@@Z; CMicrodomBuilder::WriteLocationData(_LBLOB *)
0x18001557f  test    eax, eax
0x180015581  js      loc_180015609
0x180015587  mov     rcx, [rbp+Size]
0x18001558b  lea     rdx, [rbx+4]
0x18001558f  call    ??$ConvertInteger@_KK@Rtl@BUCL@@YAJ_KAEAK@Z; BUCL::Rtl::ConvertInteger<unsigned __int64,ulong>(unsigned __int64,ulong &)
0x180015594  mov     r8d, eax
0x180015597  test    eax, eax
0x180015599  jns     short loc_1800155C2
0x18001559b  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x1800155a2  mov     [rbp+var_40], 441h
0x1800155aa  mov     [rbp+var_50], rax
0x1800155ae  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x1800155b5  mov     [rbp+var_48], rax
0x1800155b9  lea     rax, aBuclRtlConvert_8; "BUCL::Rtl::ConvertInteger(WriteBlock.Le"...
0x1800155c0  jmp     short loc_1800155F8
0x1800155c2  mov     rax, [rbp+Size]
0x1800155c6  mov     [rsi], rax
0x1800155c9  xor     eax, eax
0x1800155cb  jmp     short loc_180015609
0x1800155cd  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x1800155d4  mov     [rbp+var_40], 400h
0x1800155dc  mov     [rbp+var_50], rax
0x1800155e0  mov     r8d, 0C0000095h
0x1800155e6  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x1800155ed  mov     [rbp+var_48], rax
0x1800155f1  lea     rax, aBuclRtlAddSize_2; "BUCL::Rtl::Add<SIZE_T>( sizeof(MICRODOM"...
0x1800155f8  lea     rdx, [rbp+var_50]
0x1800155fc  mov     [rbp+var_38], rax
0x180015600  lea     rcx, [rbp+var_18]
0x180015604  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180015609  mov     rcx, [rbp+var_10]
0x18001560d  xor     rcx, rsp; StackCookie
0x180015610  call    __security_check_cookie
0x180015615  mov     rbx, [rsp+70h+arg_8]
0x18001561d  add     rsp, 70h
0x180015621  pop     r15
0x180015623  pop     r14
0x180015625  pop     rdi
0x180015626  pop     rsi
0x180015627  pop     rbp
0x180015628  retn
```
