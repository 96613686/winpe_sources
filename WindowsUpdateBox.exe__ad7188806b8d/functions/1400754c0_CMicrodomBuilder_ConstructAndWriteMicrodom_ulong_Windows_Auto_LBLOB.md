# CMicrodomBuilder::ConstructAndWriteMicrodom(ulong,Windows::Auto<_LBLOB> *)

- ea: `0x1400754c0`
- end: `0x14007593a`
- name: `?ConstructAndWriteMicrodom@CMicrodomBuilder@@QEAAJKPEAV?$Auto@U_LBLOB@@@Windows@@@Z`
- size: `1146`
- prototype: `__int64 __fastcall(CMicrodomBuilder *this, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140075e48`

## callees

- `0x140002116`
- `0x14006261c`
- `0x140071cbc`
- `0x140072764`
- `0x1400754c0`
- `0x1400763a4`
- `0x140076550`
- `0x1400767bc`
- `0x140077458`
- `0x140077edc`
- `0x140078258`
- `0x140078620`
- `0x140080d70`

## string_xrefs

- `0x1400755c0`: `onecore\base\xml\udom_builder.cpp`
- `0x14007568d`: `onecore\base\xml\udom_builder.cpp`
- `0x14007571c`: `onecore\base\xml\udom_builder.cpp`
- `0x140075799`: `onecore\base\xml\udom_builder.cpp`
- `0x140075816`: `onecore\base\xml\udom_builder.cpp`
- `0x1400758a3`: `onecore\base\xml\udom_builder.cpp`
- `0x1400758d8`: `onecore\base\xml\udom_builder.cpp`
- `0x1400755d7`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x1400756a0`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x14007572f`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x1400757ac`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x140075829`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x1400758b6`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x1400758ef`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x1400756ab`: `BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToStringPool)`
- `0x14007573a`: `BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToDomLayout)`
- `0x1400757b7`: `BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToDoctypeData)`
- `0x140075834`: `BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToPositionData)`
- `0x1400758c1`: `BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulTotalSize)`

## pseudocode

```c
__int64 __fastcall CMicrodomBuilder::ConstructAndWriteMicrodom(CMicrodomBuilder *this, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rbx
  __int64 v6; // r13
  unsigned __int64 v7; // r15
  __int64 v8; // rdi
  unsigned int v9; // eax
  unsigned __int64 v10; // rdi
  int v11; // ecx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rcx
  char v14; // al
  unsigned __int64 v15; // rdx
  __int64 result; // rax
  void *v17; // xmm1_8
  _DWORD *v18; // rdi
  size_t v19; // rdx
  size_t v20; // rdx
  size_t v21; // rdx
  size_t v22; // rdx
  __int64 v23; // rdx
  int v24; // ecx
  int v25; // ebx
  unsigned __int64 v26; // [rsp+20h] [rbp-50h] BYREF
  unsigned int v27; // [rsp+28h] [rbp-48h] BYREF
  int v28; // [rsp+2Ch] [rbp-44h]
  const char *v29; // [rsp+30h] [rbp-40h] BYREF
  const char *v30; // [rsp+38h] [rbp-38h]
  __int64 v31; // [rsp+40h] [rbp-30h]
  const char *v32; // [rsp+48h] [rbp-28h]
  size_t Size[2]; // [rsp+50h] [rbp-20h] BYREF
  void *v34; // [rsp+60h] [rbp-10h]

  v5 = 3;
  v6 = ((unsigned int)CMicrodomBuilder::DetermineStringTableSize(this) + 3) & 0xFFFFFFFC;
  v7 = ((unsigned int)CMicrodomBuilder::GetXmlDomSize(this) + 3) & 0xFFFFFFFC;
  v26 = 0;
  v8 = (unsigned int)CMicrodomBuilder::GetDoctypeDataSize(this) + 3;
  v9 = *((_DWORD *)this + 325);
  v10 = v8 & 0xFFFFFFFFFFFFFFFCuLL;
  if ( v9 > 0xFF )
  {
    v5 = 12;
    if ( v9 <= 0xFFFF )
      v5 = 6;
  }
  if ( (*BUCL::Implementation::Multiply<BUCL::Rtl::CCallDisposition,unsigned __int64>(
           &v27,
           (v5 + 3) & 0xFFFFFFFFFFFFFFFCuLL,
           *((_QWORD *)this + 161),
           &v26)
      & 0x80000000) == 0 )
  {
    v11 = v26 + 12;
    if ( v26 + 12 < v26 )
      v11 = 0;
  }
  else
  {
    v11 = 0;
  }
  v12 = v7 + ((v11 + 3) & 0xFFFFFFFC);
  v13 = v12 + v10;
  if ( v12 < v7 || (v14 = 1, v13 < v10) )
    v14 = 0;
  v15 = v6 + 24 + v13;
  if ( v14 && (unsigned __int64)(v6 + 24) >= 0x18 && v15 >= v13 )
  {
    if ( v15 <= 0xFFFFFFFF )
    {
      if ( a3[1] >= v15 || (result = RtlReallocateLBlob(v13, v15, a3), (int)result >= 0) )
      {
        v17 = (void *)a3[2];
        Size[1] = a3[1];
        v34 = v17;
        Size[0] = 0;
        memset_0(v17, 0, Size[1]);
        v18 = v34;
        *(_DWORD *)v34 = 1682465869;
        v19 = (LODWORD(Size[0]) + 27) & 0xFFFFFFFC;
        Size[0] = v19;
        v28 = 0;
        BYTE4(v26) = 0;
        *(_WORD *)((char *)&v26 + 5) = 0;
        HIBYTE(v26) = 0;
        v18[2] = v19;
        result = CMicrodomBuilder::ProduceStringTable(this, (struct _LBLOB *)Size);
        if ( (int)result >= 0 )
        {
          v20 = (LODWORD(Size[0]) + 3) & 0xFFFFFFFC;
          Size[0] = v20;
          v28 = 0;
          BYTE4(v26) = 0;
          *(_WORD *)((char *)&v26 + 5) = 0;
          HIBYTE(v26) = 0;
          v18[3] = v20;
          result = CMicrodomBuilder::WriteXmlDom(this, (struct _LBLOB *)Size);
          if ( (int)result >= 0 )
          {
            v21 = (LODWORD(Size[0]) + 3) & 0xFFFFFFFC;
            Size[0] = v21;
            v28 = 0;
            BYTE4(v26) = 0;
            *(_WORD *)((char *)&v26 + 5) = 0;
            HIBYTE(v26) = 0;
            v18[5] = v21;
            result = CMicrodomBuilder::WriteDoctypeData(this, (struct _LBLOB *)Size);
            if ( (int)result >= 0 )
            {
              v22 = (LODWORD(Size[0]) + 3) & 0xFFFFFFFC;
              Size[0] = v22;
              v28 = 0;
              BYTE4(v26) = 0;
              *(_WORD *)((char *)&v26 + 5) = 0;
              HIBYTE(v26) = 0;
              v18[4] = v22;
              result = CMicrodomBuilder::WriteLocationData(this, (struct _LBLOB *)Size);
              if ( (int)result >= 0 )
              {
                v24 = 0;
                v28 = 0;
                if ( Size[0] > 0xFFFFFFFF )
                {
                  v28 = -1073741675;
                  BYTE4(v26) = -107;
                }
                else
                {
                  v24 = Size[0];
                  if ( Size[0] == LODWORD(Size[0]) )
                  {
                    v28 = 0;
                    BYTE4(v26) = 0;
                  }
                  else
                  {
                    v28 = -1073741595;
                    BYTE4(v26) = -27;
                  }
                }
                *(_WORD *)((char *)&v26 + 5) = *(_WORD *)((char *)&v28 + 1);
                HIBYTE(v26) = HIBYTE(v28);
                v25 = HIDWORD(v26);
                v18[1] = v24;
                if ( v25 >= 0 )
                {
                  *a3 = Size[0];
                  return 0;
                }
                else
                {
                  v31 = 1089;
                  v29 = "onecore\\base\\xml\\udom_builder.cpp";
                  v30 = "CMicrodomBuilder::ConstructAndWriteMicrodom";
                  v32 = "BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulTotalSize)";
                  RtlReportErrorOrigination(&v29, v23, (unsigned int)v25);
                  return (unsigned int)v25;
                }
              }
            }
          }
        }
      }
    }
    else
    {
      v31 = 1026;
      v29 = "onecore\\base\\xml\\udom_builder.cpp";
      v30 = "CMicrodomBuilder::ConstructAndWriteMicrodom";
      v32 = "cbRequiredSize <= BUCL::CMaximumInteger<ULONG>::Value";
      RtlReportErrorOrigination(&v29, v15, 3221226539LL);
      return 3221226539LL;
    }
  }
  else
  {
    v31 = 1024;
    v29 = "onecore\\base\\xml\\udom_builder.cpp";
    v30 = "CMicrodomBuilder::ConstructAndWriteMicrodom";
    v32 = "BUCL::Rtl::Add<SIZE_T>( sizeof(MICRODOM_HEADER), cbStringPoolSize, cbDomLayoutSize, cbPositionDataSize, cbDoct"
          "ypeDataSize, cbRequiredSize)";
    RtlReportErrorOrigination(&v29, v15, 3221225621LL);
    return 3221225621LL;
  }
  return result;
}

```

## disassembly

```asm
0x1400754c0  mov     [rsp-38h+arg_8], rbx
0x1400754c5  push    rbp
0x1400754c6  push    rsi
0x1400754c7  push    rdi
0x1400754c8  push    r12
0x1400754ca  push    r13
0x1400754cc  push    r14
0x1400754ce  push    r15
0x1400754d0  mov     rbp, rsp
0x1400754d3  sub     rsp, 70h
0x1400754d7  mov     rax, cs:__security_cookie
0x1400754de  xor     rax, rsp
0x1400754e1  mov     [rbp+var_8], rax
0x1400754e5  mov     r14, r8
0x1400754e8  mov     rsi, rcx
0x1400754eb  call    ?DetermineStringTableSize@CMicrodomBuilder@@AEBA_KXZ; CMicrodomBuilder::DetermineStringTableSize(void)
0x1400754f0  mov     ebx, 3
0x1400754f5  mov     rcx, rsi; this
0x1400754f8  lea     r13d, [rbx+rax]
0x1400754fc  and     r13, 0FFFFFFFFFFFFFFFCh
0x140075500  call    ?GetXmlDomSize@CMicrodomBuilder@@AEBA_KXZ; CMicrodomBuilder::GetXmlDomSize(void)
0x140075505  mov     rcx, rsi; this
0x140075508  lea     r15d, [rbx+rax]
0x14007550c  and     r15, 0FFFFFFFFFFFFFFFCh
0x140075510  call    ?GetDoctypeDataSize@CMicrodomBuilder@@AEBA_KXZ; CMicrodomBuilder::GetDoctypeDataSize(void)
0x140075515  xor     r12d, r12d
0x140075518  mov     [rbp+var_50], r12
0x14007551c  lea     edi, [rbx+rax]
0x14007551f  mov     eax, [rsi+514h]
0x140075525  and     rdi, 0FFFFFFFFFFFFFFFCh
0x140075529  cmp     eax, 0FFh
0x14007552e  jbe     short loc_140075540
0x140075530  lea     ebx, [r12+0Ch]
0x140075535  cmp     eax, 0FFFFh
0x14007553a  lea     ecx, [rbx-6]
0x14007553d  cmovbe  ebx, ecx
0x140075540  mov     r8, [rsi+508h]
0x140075547  lea     rdx, [rbx+3]
0x14007554b  and     rdx, 0FFFFFFFFFFFFFFFCh
0x14007554f  lea     r9, [rbp+var_50]
0x140075553  lea     rcx, [rbp+var_48]
0x140075557  call    ??$Multiply@VCCallDisposition@Rtl@BUCL@@_K@Implementation@BUCL@@YA?A_P_K0AEA_K@Z
0x14007555c  cmp     [rax], r12d
0x14007555f  jge     short loc_140075566
0x140075561  mov     rcx, r12
0x140075564  jmp     short loc_140075575
0x140075566  mov     rax, [rbp+var_50]
0x14007556a  lea     rcx, [rax+0Ch]
0x14007556e  cmp     rcx, rax
0x140075571  cmovb   rcx, r12
0x140075575  lea     eax, [rcx+3]
0x140075578  and     rax, 0FFFFFFFFFFFFFFFCh
0x14007557c  add     rax, r15
0x14007557f  lea     rcx, [rax+rdi]
0x140075583  cmp     rax, r15
0x140075586  jb      short loc_14007558F
0x140075588  mov     al, 1
0x14007558a  cmp     rcx, rdi
0x14007558d  jnb     short loc_140075592
0x14007558f  mov     al, r12b
0x140075592  lea     r8, [r13+18h]
0x140075596  lea     rdx, [r8+rcx]
0x14007559a  test    al, al
0x14007559c  jz      loc_1400758D8
0x1400755a2  cmp     r8, 18h
0x1400755a6  jb      loc_1400758D8
0x1400755ac  cmp     rdx, rcx
0x1400755af  jb      loc_1400758D8
0x1400755b5  mov     r13d, 0FFFFFFFFh
0x1400755bb  cmp     rdx, r13
0x1400755be  jbe     short loc_140075602
0x1400755c0  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x1400755c7  mov     [rbp+var_30], 402h
0x1400755cf  mov     [rbp+var_40], rax
0x1400755d3  lea     rcx, [rbp+var_40]
0x1400755d7  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x1400755de  mov     r8d, 0C000042Bh
0x1400755e4  mov     [rbp+var_38], rax
0x1400755e8  lea     rax, aCbrequiredsize; "cbRequiredSize <= BUCL::CMaximumInteger"...
0x1400755ef  mov     [rbp+var_28], rax
0x1400755f3  call    RtlReportErrorOrigination
0x1400755f8  mov     eax, 0C000042Bh
0x1400755fd  jmp     loc_140075915
0x140075602  cmp     [r14+8], rdx
0x140075606  jnb     short loc_140075618
0x140075608  mov     r8, r14
0x14007560b  call    RtlReallocateLBlob
0x140075610  test    eax, eax
0x140075612  js      loc_140075915
0x140075618  movups  xmm0, xmmword ptr [r14]
0x14007561c  xor     edx, edx; Val
0x14007561e  movsd   xmm1, qword ptr [r14+10h]
0x140075624  movups  xmmword ptr [rbp+Size], xmm0
0x140075628  mov     r8, [rbp+Size+8]; Size
0x14007562c  movsd   [rbp+var_10], xmm1
0x140075631  mov     rcx, [rbp+var_10]; void *
0x140075635  mov     [rbp+Size], r12
0x140075639  call    memset_0
0x14007563e  mov     rdi, [rbp+var_10]
0x140075642  mov     r15d, 0C00000E5h
0x140075648  mov     dword ptr [rdi], 6448644Dh
0x14007564e  mov     ecx, dword ptr [rbp+Size]
0x140075651  add     ecx, 1Bh
0x140075654  and     rcx, 0FFFFFFFFFFFFFFFCh
0x140075658  mov     edx, ecx
0x14007565a  mov     [rbp+Size], rcx
0x14007565e  cmp     rcx, rdx
0x140075661  jz      short loc_14007566D
0x140075663  mov     [rbp+var_44], r15d
0x140075667  mov     byte ptr [rbp+var_50+4], 0E5h
0x14007566b  jmp     short loc_140075675
0x14007566d  mov     [rbp+var_44], r12d
0x140075671  mov     byte ptr [rbp+var_50+4], r12b
0x140075675  movzx   eax, word ptr [rbp+var_44+1]
0x140075679  mov     word ptr [rbp+var_50+5], ax
0x14007567d  mov     al, byte ptr [rbp+var_44+3]
0x140075680  mov     byte ptr [rbp+var_50+7], al
0x140075683  mov     ebx, dword ptr [rbp+var_50+4]
0x140075686  mov     [rdi+8], edx
0x140075689  test    ebx, ebx
0x14007568b  jns     short loc_1400756C9
0x14007568d  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x140075694  mov     [rbp+var_30], 41Fh
0x14007569c  mov     [rbp+var_40], rax
0x1400756a0  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x1400756a7  mov     [rbp+var_38], rax
0x1400756ab  lea     rax, aBuclRtlConvert_2; "BUCL::Rtl::ConvertInteger(WriteBlock.Le"...
0x1400756b2  mov     r8d, ebx
0x1400756b5  mov     [rbp+var_28], rax
0x1400756b9  lea     rcx, [rbp+var_40]
0x1400756bd  call    RtlReportErrorOrigination
0x1400756c2  mov     eax, ebx
0x1400756c4  jmp     loc_140075915
0x1400756c9  lea     rdx, [rbp+Size]; struct _LBLOB *
0x1400756cd  mov     rcx, rsi; this
0x1400756d0  call    ?ProduceStringTable@CMicrodomBuilder@@AEBAJPEAU_LBLOB@@@Z; CMicrodomBuilder::ProduceStringTable(_LBLOB *)
0x1400756d5  test    eax, eax
0x1400756d7  js      loc_140075915
0x1400756dd  mov     ecx, dword ptr [rbp+Size]
0x1400756e0  add     ecx, 3
0x1400756e3  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1400756e7  mov     edx, ecx
0x1400756e9  mov     [rbp+Size], rcx
0x1400756ed  cmp     rcx, rdx
0x1400756f0  jz      short loc_1400756FC
0x1400756f2  mov     [rbp+var_44], r15d
0x1400756f6  mov     byte ptr [rbp+var_50+4], 0E5h
0x1400756fa  jmp     short loc_140075704
0x1400756fc  mov     [rbp+var_44], r12d
0x140075700  mov     byte ptr [rbp+var_50+4], r12b
0x140075704  movzx   eax, word ptr [rbp+var_44+1]
0x140075708  mov     word ptr [rbp+var_50+5], ax
0x14007570c  mov     al, byte ptr [rbp+var_44+3]
0x14007570f  mov     byte ptr [rbp+var_50+7], al
0x140075712  mov     ebx, dword ptr [rbp+var_50+4]
0x140075715  mov     [rdi+0Ch], edx
0x140075718  test    ebx, ebx
0x14007571a  jns     short loc_140075746
0x14007571c  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x140075723  mov     [rbp+var_30], 428h
0x14007572b  mov     [rbp+var_40], rax
0x14007572f  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x140075736  mov     [rbp+var_38], rax
0x14007573a  lea     rax, aBuclRtlConvert_1; "BUCL::Rtl::ConvertInteger(WriteBlock.Le"...
0x140075741  jmp     loc_1400756B2
0x140075746  lea     rdx, [rbp+Size]; struct _LBLOB *
0x14007574a  mov     rcx, rsi; this
0x14007574d  call    ?WriteXmlDom@CMicrodomBuilder@@AEAAJPEAU_LBLOB@@@Z; CMicrodomBuilder::WriteXmlDom(_LBLOB *)
0x140075752  test    eax, eax
0x140075754  js      loc_140075915
0x14007575a  mov     ecx, dword ptr [rbp+Size]
0x14007575d  add     ecx, 3
0x140075760  and     rcx, 0FFFFFFFFFFFFFFFCh
0x140075764  mov     edx, ecx
0x140075766  mov     [rbp+Size], rcx
0x14007576a  cmp     rcx, rdx
0x14007576d  jz      short loc_140075779
0x14007576f  mov     [rbp+var_44], r15d
0x140075773  mov     byte ptr [rbp+var_50+4], 0E5h
0x140075777  jmp     short loc_140075781
0x140075779  mov     [rbp+var_44], r12d
0x14007577d  mov     byte ptr [rbp+var_50+4], r12b
0x140075781  movzx   eax, word ptr [rbp+var_44+1]
0x140075785  mov     word ptr [rbp+var_50+5], ax
0x140075789  mov     al, byte ptr [rbp+var_44+3]
0x14007578c  mov     byte ptr [rbp+var_50+7], al
0x14007578f  mov     ebx, dword ptr [rbp+var_50+4]
0x140075792  mov     [rdi+14h], edx
0x140075795  test    ebx, ebx
0x140075797  jns     short loc_1400757C3
0x140075799  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x1400757a0  mov     [rbp+var_30], 431h
0x1400757a8  mov     [rbp+var_40], rax
0x1400757ac  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x1400757b3  mov     [rbp+var_38], rax
0x1400757b7  lea     rax, aBuclRtlConvert_6; "BUCL::Rtl::ConvertInteger(WriteBlock.Le"...
0x1400757be  jmp     loc_1400756B2
0x1400757c3  lea     rdx, [rbp+Size]; struct _LBLOB *
0x1400757c7  mov     rcx, rsi; this
0x1400757ca  call    ?WriteDoctypeData@CMicrodomBuilder@@AEAAJPEAU_LBLOB@@@Z; CMicrodomBuilder::WriteDoctypeData(_LBLOB *)
0x1400757cf  test    eax, eax
0x1400757d1  js      loc_140075915
0x1400757d7  mov     ecx, dword ptr [rbp+Size]
0x1400757da  add     ecx, 3
0x1400757dd  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1400757e1  mov     edx, ecx
0x1400757e3  mov     [rbp+Size], rcx
0x1400757e7  cmp     rcx, rdx
0x1400757ea  jz      short loc_1400757F6
0x1400757ec  mov     [rbp+var_44], r15d
0x1400757f0  mov     byte ptr [rbp+var_50+4], 0E5h
0x1400757f4  jmp     short loc_1400757FE
0x1400757f6  mov     [rbp+var_44], r12d
0x1400757fa  mov     byte ptr [rbp+var_50+4], r12b
0x1400757fe  movzx   eax, word ptr [rbp+var_44+1]
0x140075802  mov     word ptr [rbp+var_50+5], ax
0x140075806  mov     al, byte ptr [rbp+var_44+3]
0x140075809  mov     byte ptr [rbp+var_50+7], al
0x14007580c  mov     ebx, dword ptr [rbp+var_50+4]
0x14007580f  mov     [rdi+10h], edx
0x140075812  test    ebx, ebx
0x140075814  jns     short loc_140075840
0x140075816  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x14007581d  mov     [rbp+var_30], 43Ah
0x140075825  mov     [rbp+var_40], rax
0x140075829  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x140075830  mov     [rbp+var_38], rax
0x140075834  lea     rax, aBuclRtlConvert_0; "BUCL::Rtl::ConvertInteger(WriteBlock.Le"...
0x14007583b  jmp     loc_1400756B2
0x140075840  lea     rdx, [rbp+Size]; struct _LBLOB *
0x140075844  mov     rcx, rsi; this
0x140075847  call    ?WriteLocationData@CMicrodomBuilder@@AEAAJPEAU_LBLOB@@@Z; CMicrodomBuilder::WriteLocationData(_LBLOB *)
0x14007584c  test    eax, eax
0x14007584e  js      loc_140075915
0x140075854  xor     eax, eax
0x140075856  mov     ecx, r12d
0x140075859  mov     [rbp+var_44], eax
0x14007585c  mov     rax, [rbp+Size]
0x140075860  cmp     rax, r13
0x140075863  ja      short loc_140075880
0x140075865  mov     ecx, eax
0x140075867  cmp     rax, rcx
0x14007586a  jz      short loc_140075876
0x14007586c  mov     [rbp+var_44], r15d
0x140075870  mov     byte ptr [rbp+var_50+4], 0E5h
0x140075874  jmp     short loc_14007588B
0x140075876  mov     [rbp+var_44], r12d
0x14007587a  mov     byte ptr [rbp+var_50+4], r12b
0x14007587e  jmp     short loc_14007588B
0x140075880  mov     [rbp+var_44], 0C0000095h
0x140075887  mov     byte ptr [rbp+var_50+4], 95h
0x14007588b  movzx   eax, word ptr [rbp+var_44+1]
0x14007588f  mov     word ptr [rbp+var_50+5], ax
0x140075893  mov     al, byte ptr [rbp+var_44+3]
0x140075896  mov     byte ptr [rbp+var_50+7], al
0x140075899  mov     ebx, dword ptr [rbp+var_50+4]
0x14007589c  mov     [rdi+4], ecx
0x14007589f  test    ebx, ebx
0x1400758a1  jns     short loc_1400758CD
0x1400758a3  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x1400758aa  mov     [rbp+var_30], 441h
0x1400758b2  mov     [rbp+var_40], rax
0x1400758b6  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x1400758bd  mov     [rbp+var_38], rax
0x1400758c1  lea     rax, aBuclRtlConvert_5; "BUCL::Rtl::ConvertInteger(WriteBlock.Le"...
0x1400758c8  jmp     loc_1400756B2
0x1400758cd  mov     rax, [rbp+Size]
0x1400758d1  mov     [r14], rax
0x1400758d4  xor     eax, eax
0x1400758d6  jmp     short loc_140075915
0x1400758d8  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x1400758df  mov     [rbp+var_30], 400h
0x1400758e7  mov     [rbp+var_40], rax
0x1400758eb  lea     rcx, [rbp+var_40]
0x1400758ef  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x1400758f6  mov     r8d, 0C0000095h
0x1400758fc  mov     [rbp+var_38], rax
0x140075900  lea     rax, aBuclRtlAddSize_2; "BUCL::Rtl::Add<SIZE_T>( sizeof(MICRODOM"...
0x140075907  mov     [rbp+var_28], rax
0x14007590b  call    RtlReportErrorOrigination
0x140075910  mov     eax, 0C0000095h
0x140075915  mov     rcx, [rbp+var_8]
0x140075919  xor     rcx, rsp; StackCookie
0x14007591c  call    __security_check_cookie
0x140075921  mov     rbx, [rsp+70h+arg_8]
0x140075929  add     rsp, 70h
0x14007592d  pop     r15
0x14007592f  pop     r14
0x140075931  pop     r13
0x140075933  pop     r12
0x140075935  pop     rdi
0x140075936  pop     rsi
0x140075937  pop     rbp
0x140075938  retn
```
