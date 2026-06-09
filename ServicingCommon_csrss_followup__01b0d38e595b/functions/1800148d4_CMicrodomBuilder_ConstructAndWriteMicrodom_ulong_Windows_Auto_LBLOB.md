# CMicrodomBuilder::ConstructAndWriteMicrodom(ulong,Windows::Auto<_LBLOB> *)

- ea: `0x1800148d4`
- end: `0x180014cc0`
- name: `?ConstructAndWriteMicrodom@CMicrodomBuilder@@QEAAJKPEAV?$Auto@U_LBLOB@@@Windows@@@Z`
- size: `1004`
- prototype: `__int64 __fastcall(CMicrodomBuilder *this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000dcd0`

## callees

- `0x180009820`
- `0x18000bd10`
- `0x1800148d4`
- `0x180014cc8`
- `0x180014df0`
- `0x180015b30`
- `0x1800162ac`
- `0x1800190b8`
- `0x180019328`
- `0x18001c998`
- `0x18001f840`
- `0x1800204e0`
- `0x18002152c`
- `0x18002d2b0`
- `0x180097e20`

## string_xrefs

- `0x18001499f`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x180014a6f`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x180014af0`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x180014b76`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x180014be4`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x180014c36`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x180014c72`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x180014986`: `onecore\base\xml\udom_builder.cpp`
- `0x180014a5c`: `onecore\base\xml\udom_builder.cpp`
- `0x180014add`: `onecore\base\xml\udom_builder.cpp`
- `0x180014b5c`: `onecore\base\xml\udom_builder.cpp`
- `0x180014bd1`: `onecore\base\xml\udom_builder.cpp`
- `0x180014c23`: `onecore\base\xml\udom_builder.cpp`
- `0x180014c58`: `onecore\base\xml\udom_builder.cpp`
- `0x180014b88`: `BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToDoctypeData)`
- `0x180014a7a`: `BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToStringPool)`
- `0x180014afb`: `BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToDomLayout)`
- `0x180014bef`: `BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToPositionData)`
- `0x180014c41`: `BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulTotalSize)`

## pseudocode

```c
__int64 __fastcall CMicrodomBuilder::ConstructAndWriteMicrodom(CMicrodomBuilder *this, __int64 a2, __int128 *a3)
{
  int v5; // r15d
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rdi
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
  size_t v18; // rdx
  size_t v19; // rdx
  size_t v20; // rdx
  int v21; // eax
  int v22; // eax
  const char *v23; // [rsp+30h] [rbp-50h] BYREF
  const char *v24; // [rsp+38h] [rbp-48h]
  __int64 v25; // [rsp+40h] [rbp-40h]
  const char *v26; // [rsp+48h] [rbp-38h]
  size_t Size[2]; // [rsp+50h] [rbp-30h] BYREF
  _DWORD *v28; // [rsp+60h] [rbp-20h]
  int v29; // [rsp+68h] [rbp-18h] BYREF

  v29 = 0;
  v5 = CMicrodomBuilder::DetermineStringTableSize(this);
  v6 = ((unsigned int)CMicrodomBuilder::GetXmlDomSize(this) + 3) & 0xFFFFFFFC;
  v7 = ((unsigned int)CMicrodomBuilder::GetDoctypeDataSize(this) + 3) & 0xFFFFFFFC;
  v8 = v6 + (((unsigned int)CMicrodomBuilder::GetLocationDataSize(this) + 3) & 0xFFFFFFFC);
  v9 = v8 + v7;
  v10 = v8 >= v6 && v9 >= v7;
  if ( v10 && (v11 = ((v5 + 3) & 0xFFFFFFFC) + 24LL, v12 = v9 + v11, v9 + v11 >= v9) )
  {
    if ( v12 > 0xFFFFFFFF )
    {
      v25 = 1026;
      v23 = "onecore\\base\\xml\\udom_builder.cpp";
      v13 = 3221226539LL;
      v24 = "CMicrodomBuilder::ConstructAndWriteMicrodom";
      v14 = "cbRequiredSize <= BUCL::CMaximumInteger<ULONG>::Value";
LABEL_9:
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
      v18 = (LODWORD(Size[0]) + 27) & 0xFFFFFFFC;
      Size[0] = v18;
      v17[2] = v18;
      result = CMicrodomBuilder::ProduceStringTable(this, (struct _LBLOB *)Size);
      if ( (int)result >= 0 )
      {
        v19 = (LODWORD(Size[0]) + 3) & 0xFFFFFFFC;
        Size[0] = v19;
        v17[3] = v19;
        result = CMicrodomBuilder::WriteXmlDom(this, (struct _LBLOB *)Size);
        if ( (int)result >= 0 )
        {
          v20 = (LODWORD(Size[0]) + 3) & 0xFFFFFFFC;
          Size[0] = v20;
          v17[5] = v20;
          result = CMicrodomBuilder::WriteDoctypeData(this, (struct _LBLOB *)Size);
          if ( (int)result >= 0 )
          {
            Size[0] = (LODWORD(Size[0]) + 3) & 0xFFFFFFFC;
            v21 = BUCL::Rtl::ConvertInteger<unsigned __int64,unsigned long>(Size[0], v17 + 4);
            v13 = (unsigned int)v21;
            if ( v21 < 0 )
            {
              v25 = 1082;
              v23 = "onecore\\base\\xml\\udom_builder.cpp";
              v24 = "CMicrodomBuilder::ConstructAndWriteMicrodom";
              v14 = "BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToPositionData)";
              goto LABEL_9;
            }
            result = CMicrodomBuilder::WriteLocationData(this, (struct _LBLOB *)Size);
            if ( (int)result >= 0 )
            {
              v22 = BUCL::Rtl::ConvertInteger<unsigned __int64,unsigned long>(Size[0], v17 + 1);
              v13 = (unsigned int)v22;
              if ( v22 < 0 )
              {
                v25 = 1089;
                v23 = "onecore\\base\\xml\\udom_builder.cpp";
                v24 = "CMicrodomBuilder::ConstructAndWriteMicrodom";
                v14 = "BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulTotalSize)";
                goto LABEL_9;
              }
              *(_QWORD *)a3 = Size[0];
              return 0;
            }
          }
        }
      }
    }
  }
  else
  {
    v25 = 1024;
    v23 = "onecore\\base\\xml\\udom_builder.cpp";
    v24 = "CMicrodomBuilder::ConstructAndWriteMicrodom";
    v26 = "BUCL::Rtl::Add<SIZE_T>( sizeof(MICRODOM_HEADER), cbStringPoolSize, cbDomLayoutSize, cbPositionDataSize, cbDoct"
          "ypeDataSize, cbRequiredSize)";
    RtlReportErrorOrigination(&v23, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225621LL);
    return 3221225621LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800148d4  mov     [rsp-28h+arg_8], rbx
0x1800148d9  push    rbp
0x1800148da  push    rsi
0x1800148db  push    rdi
0x1800148dc  push    r14
0x1800148de  push    r15
0x1800148e0  mov     rbp, rsp
0x1800148e3  sub     rsp, 80h
0x1800148ea  mov     rax, cs:__security_cookie
0x1800148f1  xor     rax, rsp
0x1800148f4  mov     [rbp+var_10], rax
0x1800148f8  mov     r14, r8
0x1800148fb  mov     [rbp+var_18], 0
0x180014902  mov     rsi, rcx
0x180014905  call    ?DetermineStringTableSize@CMicrodomBuilder@@AEBA_KXZ; CMicrodomBuilder::DetermineStringTableSize(void)
0x18001490a  mov     rcx, rsi; this
0x18001490d  mov     r15, rax
0x180014910  call    ?GetXmlDomSize@CMicrodomBuilder@@AEBA_KXZ; CMicrodomBuilder::GetXmlDomSize(void)
0x180014915  mov     rcx, rsi; this
0x180014918  lea     ebx, [rax+3]
0x18001491b  and     rbx, 0FFFFFFFFFFFFFFFCh
0x18001491f  call    ?GetDoctypeDataSize@CMicrodomBuilder@@AEBA_KXZ; CMicrodomBuilder::GetDoctypeDataSize(void)
0x180014924  mov     rcx, rsi; this
0x180014927  lea     edi, [rax+3]
0x18001492a  and     rdi, 0FFFFFFFFFFFFFFFCh
0x18001492e  call    ?GetLocationDataSize@CMicrodomBuilder@@AEBA_KXZ; CMicrodomBuilder::GetLocationDataSize(void)
0x180014933  add     eax, 3
0x180014936  and     rax, 0FFFFFFFFFFFFFFFCh
0x18001493a  add     rax, rbx
0x18001493d  lea     r8, [rax+rdi]
0x180014941  cmp     rax, rbx
0x180014944  jb      short loc_18001494F
0x180014946  cmp     r8, rdi
0x180014949  jb      short loc_18001494F
0x18001494b  mov     al, 1
0x18001494d  jmp     short loc_180014951
0x18001494f  xor     al, al
0x180014951  test    al, al
0x180014953  jz      loc_180014C58
0x180014959  lea     ecx, [r15+3]
0x18001495d  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180014961  add     rcx, 18h
0x180014965  cmp     rcx, 18h
0x180014969  jb      loc_180014C58
0x18001496f  lea     rdx, [r8+rcx]
0x180014973  cmp     rdx, r8
0x180014976  jb      loc_180014C58
0x18001497c  mov     eax, 0FFFFFFFFh
0x180014981  cmp     rdx, rax
0x180014984  jbe     short loc_1800149C7
0x180014986  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x18001498d  mov     [rbp+var_40], 402h
0x180014995  mov     [rbp+var_50], rax
0x180014999  mov     r8d, 0C000042Bh
0x18001499f  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x1800149a6  mov     [rbp+var_48], rax
0x1800149aa  lea     rax, aCbrequiredsize; "cbRequiredSize <= BUCL::CMaximumInteger"...
0x1800149b1  lea     rdx, [rbp+var_50]
0x1800149b5  mov     [rbp+var_38], rax
0x1800149b9  lea     rcx, [rbp+var_18]
0x1800149bd  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800149c2  jmp     loc_180014C9C
0x1800149c7  cmp     [r14+8], rdx
0x1800149cb  jnb     short loc_1800149DF
0x1800149cd  mov     r8, r14
0x1800149d0  xor     ecx, ecx
0x1800149d2  call    RtlReallocateLBlob
0x1800149d7  test    eax, eax
0x1800149d9  js      loc_180014C9C
0x1800149df  movsd   xmm1, qword ptr [r14+10h]
0x1800149e5  xor     edx, edx; Val
0x1800149e7  movups  xmm0, xmmword ptr [r14]
0x1800149eb  movq    rcx, xmm1; void *
0x1800149f0  movsd   [rbp+var_20], xmm1
0x1800149f5  movups  xmmword ptr [rbp+Size], xmm0
0x1800149f9  mov     r8, [rbp+Size+8]; Size
0x1800149fd  mov     [rbp+Size], 0
0x180014a05  call    memset
0x180014a0a  mov     rbx, [rbp+var_20]
0x180014a0e  mov     edi, 0C00000E5h
0x180014a13  mov     dword ptr [rbx], 6448644Dh
0x180014a19  mov     ecx, dword ptr [rbp+Size]
0x180014a1c  add     ecx, 1Bh
0x180014a1f  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180014a23  mov     edx, ecx
0x180014a25  mov     [rbp+Size], rcx
0x180014a29  cmp     rcx, rdx
0x180014a2c  jz      short loc_180014A37
0x180014a2e  mov     [rbp+var_54], edi
0x180014a31  mov     byte ptr [rbp+var_5C], 0E5h
0x180014a35  jmp     short loc_180014A42
0x180014a37  mov     [rbp+var_54], 0
0x180014a3e  mov     byte ptr [rbp+var_5C], 0
0x180014a42  movzx   eax, word ptr [rbp+var_54+1]
0x180014a46  mov     word ptr [rbp+var_5C+1], ax
0x180014a4a  mov     al, byte ptr [rbp+var_54+3]
0x180014a4d  mov     byte ptr [rbp+var_5C+3], al
0x180014a50  mov     r8d, [rbp+var_5C]
0x180014a54  mov     [rbx+8], edx
0x180014a57  test    r8d, r8d
0x180014a5a  jns     short loc_180014A86
0x180014a5c  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x180014a63  mov     [rbp+var_40], 41Fh
0x180014a6b  mov     [rbp+var_50], rax
0x180014a6f  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x180014a76  mov     [rbp+var_48], rax
0x180014a7a  lea     rax, aBuclRtlConvert_5; "BUCL::Rtl::ConvertInteger(WriteBlock.Le"...
0x180014a81  jmp     loc_1800149B1
0x180014a86  lea     rdx, [rbp+Size]; struct _LBLOB *
0x180014a8a  mov     rcx, rsi; this
0x180014a8d  call    ?ProduceStringTable@CMicrodomBuilder@@AEBAJPEAU_LBLOB@@@Z; CMicrodomBuilder::ProduceStringTable(_LBLOB *)
0x180014a92  test    eax, eax
0x180014a94  js      loc_180014C9C
0x180014a9a  mov     ecx, dword ptr [rbp+Size]
0x180014a9d  add     ecx, 3
0x180014aa0  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180014aa4  mov     edx, ecx
0x180014aa6  mov     [rbp+Size], rcx
0x180014aaa  cmp     rcx, rdx
0x180014aad  jz      short loc_180014AB8
0x180014aaf  mov     [rbp+var_54], edi
0x180014ab2  mov     byte ptr [rbp+var_5C], 0E5h
0x180014ab6  jmp     short loc_180014AC3
0x180014ab8  mov     [rbp+var_54], 0
0x180014abf  mov     byte ptr [rbp+var_5C], 0
0x180014ac3  movzx   eax, word ptr [rbp+var_54+1]
0x180014ac7  mov     word ptr [rbp+var_5C+1], ax
0x180014acb  mov     al, byte ptr [rbp+var_54+3]
0x180014ace  mov     byte ptr [rbp+var_5C+3], al
0x180014ad1  mov     r8d, [rbp+var_5C]
0x180014ad5  mov     [rbx+0Ch], edx
0x180014ad8  test    r8d, r8d
0x180014adb  jns     short loc_180014B07
0x180014add  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x180014ae4  mov     [rbp+var_40], 428h
0x180014aec  mov     [rbp+var_50], rax
0x180014af0  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x180014af7  mov     [rbp+var_48], rax
0x180014afb  lea     rax, aBuclRtlConvert_4; "BUCL::Rtl::ConvertInteger(WriteBlock.Le"...
0x180014b02  jmp     loc_1800149B1
0x180014b07  lea     rdx, [rbp+Size]; struct _LBLOB *
0x180014b0b  mov     rcx, rsi; this
0x180014b0e  call    ?WriteXmlDom@CMicrodomBuilder@@AEAAJPEAU_LBLOB@@@Z; CMicrodomBuilder::WriteXmlDom(_LBLOB *)
0x180014b13  test    eax, eax
0x180014b15  js      loc_180014C9C
0x180014b1b  mov     ecx, dword ptr [rbp+Size]
0x180014b1e  add     ecx, 3
0x180014b21  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180014b25  mov     edx, ecx
0x180014b27  mov     [rbp+Size], rcx
0x180014b2b  cmp     rcx, rdx
0x180014b2e  jz      short loc_180014B39
0x180014b30  mov     [rbp+var_54], edi
0x180014b33  mov     byte ptr [rbp+var_5C], 0E5h
0x180014b37  jmp     short loc_180014B44
0x180014b39  mov     [rbp+var_54], 0
0x180014b40  mov     byte ptr [rbp+var_5C], 0
0x180014b44  movzx   eax, word ptr [rbp+var_54+1]
0x180014b48  mov     word ptr [rbp+var_5C+1], ax
0x180014b4c  mov     al, byte ptr [rbp+var_54+3]
0x180014b4f  mov     byte ptr [rbp+var_5C+3], al
0x180014b52  mov     edi, [rbp+var_5C]
0x180014b55  mov     [rbx+14h], edx
0x180014b58  test    edi, edi
0x180014b5a  jns     short loc_180014B9F
0x180014b5c  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x180014b63  mov     [rbp+var_40], 431h
0x180014b6b  mov     [rbp+var_50], rax
0x180014b6f  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180014b76  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x180014b7d  mov     r8d, edi
0x180014b80  mov     [rbp+var_48], rax
0x180014b84  lea     rcx, [rbp+var_50]
0x180014b88  lea     rax, aBuclRtlConvert_9; "BUCL::Rtl::ConvertInteger(WriteBlock.Le"...
0x180014b8f  mov     [rbp+var_38], rax
0x180014b93  call    RtlReportErrorOrigination
0x180014b98  mov     eax, edi
0x180014b9a  jmp     loc_180014C9C
0x180014b9f  lea     rdx, [rbp+Size]; struct _LBLOB *
0x180014ba3  mov     rcx, rsi; this
0x180014ba6  call    ?WriteDoctypeData@CMicrodomBuilder@@AEAAJPEAU_LBLOB@@@Z; CMicrodomBuilder::WriteDoctypeData(_LBLOB *)
0x180014bab  test    eax, eax
0x180014bad  js      loc_180014C9C
0x180014bb3  mov     ecx, dword ptr [rbp+Size]
0x180014bb6  lea     rdx, [rbx+10h]
0x180014bba  add     ecx, 3
0x180014bbd  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180014bc1  mov     [rbp+Size], rcx
0x180014bc5  call    ??$ConvertInteger@_KK@Rtl@BUCL@@YAJ_KAEAK@Z; BUCL::Rtl::ConvertInteger<unsigned __int64,ulong>(unsigned __int64,ulong &)
0x180014bca  mov     r8d, eax
0x180014bcd  test    eax, eax
0x180014bcf  jns     short loc_180014BFB
0x180014bd1  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x180014bd8  mov     [rbp+var_40], 43Ah
0x180014be0  mov     [rbp+var_50], rax
0x180014be4  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x180014beb  mov     [rbp+var_48], rax
0x180014bef  lea     rax, aBuclRtlConvert_1; "BUCL::Rtl::ConvertInteger(WriteBlock.Le"...
0x180014bf6  jmp     loc_1800149B1
0x180014bfb  lea     rdx, [rbp+Size]; struct _LBLOB *
0x180014bff  mov     rcx, rsi; this
0x180014c02  call    ?WriteLocationData@CMicrodomBuilder@@AEAAJPEAU_LBLOB@@@Z; CMicrodomBuilder::WriteLocationData(_LBLOB *)
0x180014c07  test    eax, eax
0x180014c09  js      loc_180014C9C
0x180014c0f  mov     rcx, [rbp+Size]
0x180014c13  lea     rdx, [rbx+4]
0x180014c17  call    ??$ConvertInteger@_KK@Rtl@BUCL@@YAJ_KAEAK@Z; BUCL::Rtl::ConvertInteger<unsigned __int64,ulong>(unsigned __int64,ulong &)
0x180014c1c  mov     r8d, eax
0x180014c1f  test    eax, eax
0x180014c21  jns     short loc_180014C4D
0x180014c23  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x180014c2a  mov     [rbp+var_40], 441h
0x180014c32  mov     [rbp+var_50], rax
0x180014c36  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x180014c3d  mov     [rbp+var_48], rax
0x180014c41  lea     rax, aBuclRtlConvert_8; "BUCL::Rtl::ConvertInteger(WriteBlock.Le"...
0x180014c48  jmp     loc_1800149B1
0x180014c4d  mov     rax, [rbp+Size]
0x180014c51  mov     [r14], rax
0x180014c54  xor     eax, eax
0x180014c56  jmp     short loc_180014C9C
0x180014c58  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x180014c5f  mov     [rbp+var_40], 400h
0x180014c67  mov     [rbp+var_50], rax
0x180014c6b  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180014c72  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x180014c79  mov     r8d, 0C0000095h
0x180014c7f  mov     [rbp+var_48], rax
0x180014c83  lea     rcx, [rbp+var_50]
0x180014c87  lea     rax, aBuclRtlAddSize_2; "BUCL::Rtl::Add<SIZE_T>( sizeof(MICRODOM"...
0x180014c8e  mov     [rbp+var_38], rax
0x180014c92  call    RtlReportErrorOrigination
0x180014c97  mov     eax, 0C0000095h
0x180014c9c  mov     rcx, [rbp+var_10]
0x180014ca0  xor     rcx, rsp; StackCookie
0x180014ca3  call    __security_check_cookie
0x180014ca8  mov     rbx, [rsp+80h+arg_8]
0x180014cb0  add     rsp, 80h
0x180014cb7  pop     r15
0x180014cb9  pop     r14
0x180014cbb  pop     rdi
0x180014cbc  pop     rsi
0x180014cbd  pop     rbp
0x180014cbe  retn
```
