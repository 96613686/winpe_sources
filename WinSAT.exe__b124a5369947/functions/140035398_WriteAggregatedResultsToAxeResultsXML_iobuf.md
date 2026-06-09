# WriteAggregatedResultsToAxeResultsXML(_iobuf *)

- ea: `0x140035398`
- end: `0x140035a5d`
- name: `?WriteAggregatedResultsToAxeResultsXML@@YAJPEAU_iobuf@@@Z`
- size: `1733`
- prototype: `__int64 __fastcall(FILE *Stream)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400393cc`

## callees

- `0x14001f940`
- `0x14003527c`
- `0x140035398`
- `0x140039700`
- `0x1400397d0`
- `0x140113220`

## import_xrefs

- `msvcrt!wcsstr` at `0x1400357f6`
- `msvcrt!wcsstr` at `0x1400357f6`

## string_xrefs

- `0x1400355f9`: `CompressionMetric`
- `0x140035651`: `CPUCompression2Metric`
- `0x1400356a9`: `CompressionMetricUP`
- `0x140035701`: `CPUCompression2MetricUP`
- `0x14003599b`: `SequentialReadAveThroughput`
- `0x1400359b6`: `SequentialReadIOSize`
- `0x1400359ce`: `SequentialReadInterferencePercentage`
- `0x1400359e6`: `SequentialReadAllowedInterferencePercentage`
- `0x140035a08`: `SequentialReadScore`
- `0x14003590c`: `RandomReadAveThroughput`
- `0x14003592b`: `RandomReadIOSize`
- `0x140035947`: `RandomReadInterferencePercentage`
- `0x140035963`: `RandomReadAllowedInterferencePercentage`
- `0x14003598d`: `RandomReadScore`

## pseudocode

```c
__int64 __fastcall WriteAggregatedResultsToAxeResultsXML(FILE *Stream)
{
  int v1; // edx
  double *v3; // rcx
  double *v4; // rbx
  int v5; // edx
  const unsigned __int16 *v6; // r8
  double *v7; // rbx
  double v8; // xmm1_8
  const unsigned __int16 *v9; // r8
  unsigned __int16 v11[104]; // [rsp+20h] [rbp-118h] BYREF

  v1 = 0;
  if ( dbl_140168970 == 1.797693134862316e308
    || dbl_140168970 == 0.0
    || (v1 = WriteXMLMetric(Stream, dbl_140168970, L"SystemScore", 1u), v1 >= 0) )
  {
    if ( dbl_140168900 == 1.797693134862316e308
      || dbl_140168900 == 0.0
      || (v1 = WriteXMLMetric(Stream, dbl_140168900, L"CPUScore", 1u), v1 >= 0) )
    {
      if ( dbl_140168880 == 1.797693134862316e308
        || dbl_140168880 == 0.0
        || (v1 = WriteXMLMetric(Stream, dbl_140168880, L"MemScore", 1u), v1 >= 0) )
      {
        if ( dbl_1401688F0 == 1.797693134862316e308
          || dbl_1401688F0 == 0.0
          || (v1 = WriteXMLMetric(Stream, dbl_1401688F0, L"GraphicsScore", 1u), v1 >= 0) )
        {
          if ( dbl_1401688C0 == 1.797693134862316e308
            || dbl_1401688C0 == 0.0
            || (v1 = WriteXMLMetric(Stream, dbl_1401688C0, L"GamingScore", 1u), v1 >= 0) )
          {
            if ( dbl_140168930 == 1.797693134862316e308
              || dbl_140168930 == 0.0
              || (v1 = WriteXMLMetric(Stream, dbl_140168930, L"DiskScore", 1u), v1 >= 0) )
            {
              if ( dbl_140168898 == 1.797693134862316e308
                || dbl_140168898 == 0.0
                || (v1 = WriteXMLMetric(Stream, dbl_140168898, L"CPUSubAggScore", 1u), v1 >= 0) )
              {
                if ( dbl_1401688D0 == 1.797693134862316e308
                  || dbl_1401688D0 == 0.0
                  || (v1 = WriteXMLMetric(Stream, dbl_1401688D0, L"VideoEncodeScore", 1u), v1 >= 0) )
                {
                  if ( dbl_140168890 == 1.797693134862316e308
                    || dbl_140168890 == 0.0
                    || (v1 = WriteXMLMetric(Stream, dbl_140168890, L"Dx9SubScore", 1u), v1 >= 0) )
                  {
                    if ( dbl_140168948 == 1.797693134862316e308
                      || dbl_140168948 == 0.0
                      || (v1 = WriteXMLMetric(Stream, dbl_140168948, L"Dx10SubScore", 1u), v1 >= 0) )
                    {
                      if ( dbl_140168968 == 1.797693134862316e308
                        || (v1 = WriteXMLMetric(Stream, dbl_140168968, L"CompressionMetric", 5u), v1 >= 0) )
                      {
                        if ( dbl_140168920 == 1.797693134862316e308
                          || (v1 = WriteXMLMetric(Stream, dbl_140168920, L"EncryptionMetric", 5u), v1 >= 0) )
                        {
                          if ( dbl_140168918 == 1.797693134862316e308
                            || (v1 = WriteXMLMetric(Stream, dbl_140168918, L"CPUCompression2Metric", 5u), v1 >= 0) )
                          {
                            if ( dbl_140168928 == 1.797693134862316e308
                              || (v1 = WriteXMLMetric(Stream, dbl_140168928, L"Encryption2Metric", 5u), v1 >= 0) )
                            {
                              if ( dbl_140168990 == 1.797693134862316e308
                                || (v1 = WriteXMLMetric(Stream, dbl_140168990, L"CompressionMetricUP", 5u), v1 >= 0) )
                              {
                                if ( dbl_1401688B0 == 1.797693134862316e308
                                  || (v1 = WriteXMLMetric(Stream, dbl_1401688B0, L"EncryptionMetricUP", 5u), v1 >= 0) )
                                {
                                  if ( dbl_1401688B8 == 1.797693134862316e308
                                    || (v1 = WriteXMLMetric(Stream, dbl_1401688B8, L"CPUCompression2MetricUP", 5u),
                                        v1 >= 0) )
                                  {
                                    if ( dbl_140168988 == 1.797693134862316e308
                                      || (v1 = WriteXMLMetric(Stream, dbl_140168988, L"Encryption2MetricUP", 5u), v1 >= 0) )
                                    {
                                      if ( dbl_140168908 == 1.797693134862316e308
                                        || (v1 = WriteXMLMetric(Stream, dbl_140168908, L"DshowEncodeTime", 5u), v1 >= 0) )
                                      {
                                        if ( dbl_140168938 == 1.797693134862316e308
                                          || (v1 = WriteXMLMetric(Stream, dbl_140168938, L"Bandwidth", 5u), v1 >= 0) )
                                        {
                                          v3 = (double *)*(&Block + 1);
                                          v4 = (double *)Block;
                                          if ( *(&Block + 1) != Block )
                                          {
                                            while ( v4 != v3 )
                                            {
                                              v1 = StringCchPrintfW(
                                                     v11,
                                                     0x64u,
                                                     L"%ws",
                                                     *(_QWORD *)(*(_QWORD *)v4 + 8LL));
                                              if ( v1 < 0 )
                                                return (unsigned int)v1;
                                              if ( wcsstr(*(const wchar_t **)(*(_QWORD *)v4 + 8LL), L"Fps") )
                                              {
                                                v5 = *(_DWORD *)(*(_QWORD *)v4 + 4LL);
                                                if ( v5 )
                                                {
                                                  if ( v5 != 1 )
                                                    goto LABEL_60;
                                                  v6 = L"10";
                                                }
                                                else
                                                {
                                                  v6 = L"9";
                                                }
                                                v1 = StringCchCatW(v11, 0x64u, v6);
                                                if ( v1 < 0 )
                                                  return (unsigned int)v1;
                                              }
LABEL_60:
                                              v1 = WriteXMLMetric(Stream, v4[1], v11, 2u);
                                              if ( v1 < 0 )
                                                return (unsigned int)v1;
                                              v3 = (double *)*(&Block + 1);
                                              v4 += 3;
                                            }
                                          }
                                          if ( dbl_140168980 == 1.797693134862316e308
                                            || (v1 = WriteXMLMetric(Stream, dbl_140168980, L"VideoMemBandwidth", 5u),
                                                v1 >= 0) )
                                          {
                                            if ( dbl_1401688A0 == 1.797693134862316e308
                                              || (v1 = WriteXMLMetric(Stream, dbl_1401688A0, L"MFVideoDecodeDur", 5u),
                                                  v1 >= 0) )
                                            {
                                              v7 = (double *)xmmword_1401C63C0;
                                              if ( *(&xmmword_1401C63C0 + 1) != xmmword_1401C63C0 )
                                              {
                                                while ( 1 )
                                                {
                                                  if ( v7 == *(&xmmword_1401C63C0 + 1) )
                                                    return (unsigned int)v1;
                                                  if ( !*((_DWORD *)v7 + 9) )
                                                  {
                                                    if ( (*(_DWORD *)v7 & 0x1F00000F) == 0x1000001 )
                                                    {
                                                      v1 = WriteXMLMetric(
                                                             Stream,
                                                             v7[5],
                                                             L"SequentialReadAveThroughput",
                                                             5u);
                                                      if ( v1 < 0 )
                                                        return (unsigned int)v1;
                                                      v1 = WriteXMLMetric(
                                                             Stream,
                                                             *((unsigned int *)v7 + 6),
                                                             L"SequentialReadIOSize");
                                                      if ( v1 < 0 )
                                                        return (unsigned int)v1;
                                                      v1 = WriteXMLMetric(
                                                             Stream,
                                                             *((unsigned int *)v7 + 7),
                                                             L"SequentialReadInterferencePercentage");
                                                      if ( v1 < 0 )
                                                        return (unsigned int)v1;
                                                      v1 = WriteXMLMetric(
                                                             Stream,
                                                             *((unsigned int *)v7 + 8),
                                                             L"SequentialReadAllowedInterferencePercentage");
                                                      if ( v1 < 0 )
                                                        return (unsigned int)v1;
                                                      v8 = v7[1];
                                                      if ( v8 != 1.797693134862316e308 )
                                                      {
                                                        v9 = L"SequentialReadScore";
LABEL_83:
                                                        v1 = WriteXMLMetric(Stream, v8, v9, 1u);
                                                        if ( v1 < 0 )
                                                          return (unsigned int)v1;
                                                      }
                                                    }
                                                    else if ( (*(_DWORD *)v7 & 0x1F00000F) == 0x1000002 )
                                                    {
                                                      v1 = WriteXMLMetric(Stream, v7[5], L"RandomReadAveThroughput", 5u);
                                                      if ( v1 < 0 )
                                                        return (unsigned int)v1;
                                                      v1 = WriteXMLMetric(
                                                             Stream,
                                                             *((unsigned int *)v7 + 6),
                                                             L"RandomReadIOSize");
                                                      if ( v1 < 0 )
                                                        return (unsigned int)v1;
                                                      v1 = WriteXMLMetric(
                                                             Stream,
                                                             *((unsigned int *)v7 + 7),
                                                             L"RandomReadInterferencePercentage");
                                                      if ( v1 < 0 )
                                                        return (unsigned int)v1;
                                                      v1 = WriteXMLMetric(
                                                             Stream,
                                                             *((unsigned int *)v7 + 8),
                                                             L"RandomReadAllowedInterferencePercentage");
                                                      if ( v1 < 0 )
                                                        return (unsigned int)v1;
                                                      v8 = v7[1];
                                                      if ( v8 != 1.797693134862316e308 )
                                                      {
                                                        v9 = L"RandomReadScore";
                                                        goto LABEL_83;
                                                      }
                                                    }
                                                  }
                                                  v7 += 7;
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140035398  mov     rax, rsp
0x14003539b  mov     [rax+10h], rbx
0x14003539f  mov     [rax+18h], rbp
0x1400353a3  push    rsi
0x1400353a4  push    rdi
0x1400353a5  push    r14
0x1400353a7  sub     rsp, 120h
0x1400353ae  movaps  xmmword ptr [rax-28h], xmm6
0x1400353b2  movaps  xmmword ptr [rax-38h], xmm7
0x1400353b6  mov     rax, cs:__security_cookie
0x1400353bd  xor     rax, rsp
0x1400353c0  mov     [rsp+138h+var_48], rax
0x1400353c8  movsd   xmm1, cs:dbl_140168970; double
0x1400353d0  xor     edx, edx
0x1400353d2  movsd   xmm6, cs:__real@7fefffffffffffff
0x1400353da  mov     rdi, rcx
0x1400353dd  ucomisd xmm1, xmm6
0x1400353e1  lea     r14d, [rdx+1]
0x1400353e5  xorps   xmm7, xmm7
0x1400353e8  jp      short loc_1400353EC
0x1400353ea  jz      short loc_14003540D
0x1400353ec  ucomisd xmm1, xmm7
0x1400353f0  jp      short loc_1400353F4
0x1400353f2  jz      short loc_14003540D
0x1400353f4  mov     r9d, r14d; unsigned int
0x1400353f7  lea     r8, aSystemscore; "SystemScore"
0x1400353fe  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x140035403  mov     edx, eax
0x140035405  test    eax, eax
0x140035407  js      loc_140035A29
0x14003540d  movsd   xmm1, cs:dbl_140168900; double
0x140035415  ucomisd xmm1, xmm6
0x140035419  jp      short loc_14003541D
0x14003541b  jz      short loc_140035441
0x14003541d  ucomisd xmm1, xmm7
0x140035421  jp      short loc_140035425
0x140035423  jz      short loc_140035441
0x140035425  mov     r9d, r14d; unsigned int
0x140035428  lea     r8, aCpuscore; "CPUScore"
0x14003542f  mov     rcx, rdi; Stream
0x140035432  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x140035437  mov     edx, eax
0x140035439  test    eax, eax
0x14003543b  js      loc_140035A29
0x140035441  movsd   xmm1, cs:dbl_140168880; double
0x140035449  ucomisd xmm1, xmm6
0x14003544d  jp      short loc_140035451
0x14003544f  jz      short loc_140035475
0x140035451  ucomisd xmm1, xmm7
0x140035455  jp      short loc_140035459
0x140035457  jz      short loc_140035475
0x140035459  mov     r9d, r14d; unsigned int
0x14003545c  lea     r8, aMemscore; "MemScore"
0x140035463  mov     rcx, rdi; Stream
0x140035466  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x14003546b  mov     edx, eax
0x14003546d  test    eax, eax
0x14003546f  js      loc_140035A29
0x140035475  movsd   xmm1, cs:dbl_1401688F0; double
0x14003547d  ucomisd xmm1, xmm6
0x140035481  jp      short loc_140035485
0x140035483  jz      short loc_1400354A9
0x140035485  ucomisd xmm1, xmm7
0x140035489  jp      short loc_14003548D
0x14003548b  jz      short loc_1400354A9
0x14003548d  mov     r9d, r14d; unsigned int
0x140035490  lea     r8, aGraphicsscore; "GraphicsScore"
0x140035497  mov     rcx, rdi; Stream
0x14003549a  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x14003549f  mov     edx, eax
0x1400354a1  test    eax, eax
0x1400354a3  js      loc_140035A29
0x1400354a9  movsd   xmm1, cs:dbl_1401688C0; double
0x1400354b1  ucomisd xmm1, xmm6
0x1400354b5  jp      short loc_1400354B9
0x1400354b7  jz      short loc_1400354DD
0x1400354b9  ucomisd xmm1, xmm7
0x1400354bd  jp      short loc_1400354C1
0x1400354bf  jz      short loc_1400354DD
0x1400354c1  mov     r9d, r14d; unsigned int
0x1400354c4  lea     r8, aGamingscore; "GamingScore"
0x1400354cb  mov     rcx, rdi; Stream
0x1400354ce  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x1400354d3  mov     edx, eax
0x1400354d5  test    eax, eax
0x1400354d7  js      loc_140035A29
0x1400354dd  movsd   xmm1, cs:dbl_140168930; double
0x1400354e5  ucomisd xmm1, xmm6
0x1400354e9  jp      short loc_1400354ED
0x1400354eb  jz      short loc_140035511
0x1400354ed  ucomisd xmm1, xmm7
0x1400354f1  jp      short loc_1400354F5
0x1400354f3  jz      short loc_140035511
0x1400354f5  mov     r9d, r14d; unsigned int
0x1400354f8  lea     r8, aDiskscore; "DiskScore"
0x1400354ff  mov     rcx, rdi; Stream
0x140035502  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x140035507  mov     edx, eax
0x140035509  test    eax, eax
0x14003550b  js      loc_140035A29
0x140035511  movsd   xmm1, cs:dbl_140168898; double
0x140035519  ucomisd xmm1, xmm6
0x14003551d  jp      short loc_140035521
0x14003551f  jz      short loc_140035545
0x140035521  ucomisd xmm1, xmm7
0x140035525  jp      short loc_140035529
0x140035527  jz      short loc_140035545
0x140035529  mov     r9d, r14d; unsigned int
0x14003552c  lea     r8, aCpusubaggscore; "CPUSubAggScore"
0x140035533  mov     rcx, rdi; Stream
0x140035536  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x14003553b  mov     edx, eax
0x14003553d  test    eax, eax
0x14003553f  js      loc_140035A29
0x140035545  movsd   xmm1, cs:dbl_1401688D0; double
0x14003554d  ucomisd xmm1, xmm6
0x140035551  jp      short loc_140035555
0x140035553  jz      short loc_140035579
0x140035555  ucomisd xmm1, xmm7
0x140035559  jp      short loc_14003555D
0x14003555b  jz      short loc_140035579
0x14003555d  mov     r9d, r14d; unsigned int
0x140035560  lea     r8, aVideoencodesco; "VideoEncodeScore"
0x140035567  mov     rcx, rdi; Stream
0x14003556a  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x14003556f  mov     edx, eax
0x140035571  test    eax, eax
0x140035573  js      loc_140035A29
0x140035579  movsd   xmm1, cs:dbl_140168890; double
0x140035581  ucomisd xmm1, xmm6
0x140035585  jp      short loc_140035589
0x140035587  jz      short loc_1400355AD
0x140035589  ucomisd xmm1, xmm7
0x14003558d  jp      short loc_140035591
0x14003558f  jz      short loc_1400355AD
0x140035591  mov     r9d, r14d; unsigned int
0x140035594  lea     r8, aDx9subscore; "Dx9SubScore"
0x14003559b  mov     rcx, rdi; Stream
0x14003559e  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x1400355a3  mov     edx, eax
0x1400355a5  test    eax, eax
0x1400355a7  js      loc_140035A29
0x1400355ad  movsd   xmm1, cs:dbl_140168948; double
0x1400355b5  ucomisd xmm1, xmm6
0x1400355b9  jp      short loc_1400355BD
0x1400355bb  jz      short loc_1400355E1
0x1400355bd  ucomisd xmm1, xmm7
0x1400355c1  jp      short loc_1400355C5
0x1400355c3  jz      short loc_1400355E1
0x1400355c5  mov     r9d, r14d; unsigned int
0x1400355c8  lea     r8, aDx10subscore; "Dx10SubScore"
0x1400355cf  mov     rcx, rdi; Stream
0x1400355d2  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x1400355d7  mov     edx, eax
0x1400355d9  test    eax, eax
0x1400355db  js      loc_140035A29
0x1400355e1  movsd   xmm1, cs:dbl_140168968; double
0x1400355e9  mov     esi, 5
0x1400355ee  ucomisd xmm1, xmm6
0x1400355f2  jp      short loc_1400355F6
0x1400355f4  jz      short loc_140035612
0x1400355f6  mov     r9d, esi; unsigned int
0x1400355f9  lea     r8, aCompressionmet; "CompressionMetric"
0x140035600  mov     rcx, rdi; Stream
0x140035603  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x140035608  mov     edx, eax
0x14003560a  test    eax, eax
0x14003560c  js      loc_140035A29
0x140035612  movsd   xmm1, cs:dbl_140168920; double
0x14003561a  ucomisd xmm1, xmm6
0x14003561e  jp      short loc_140035622
0x140035620  jz      short loc_14003563E
0x140035622  mov     r9d, esi; unsigned int
0x140035625  lea     r8, aEncryptionmetr_0; "EncryptionMetric"
0x14003562c  mov     rcx, rdi; Stream
0x14003562f  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x140035634  mov     edx, eax
0x140035636  test    eax, eax
0x140035638  js      loc_140035A29
0x14003563e  movsd   xmm1, cs:dbl_140168918; double
0x140035646  ucomisd xmm1, xmm6
0x14003564a  jp      short loc_14003564E
0x14003564c  jz      short loc_14003566A
0x14003564e  mov     r9d, esi; unsigned int
0x140035651  lea     r8, aCpucompression_2; "CPUCompression2Metric"
0x140035658  mov     rcx, rdi; Stream
0x14003565b  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x140035660  mov     edx, eax
0x140035662  test    eax, eax
0x140035664  js      loc_140035A29
0x14003566a  movsd   xmm1, cs:dbl_140168928; double
0x140035672  ucomisd xmm1, xmm6
0x140035676  jp      short loc_14003567A
0x140035678  jz      short loc_140035696
0x14003567a  mov     r9d, esi; unsigned int
0x14003567d  lea     r8, aEncryption2met; "Encryption2Metric"
0x140035684  mov     rcx, rdi; Stream
0x140035687  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x14003568c  mov     edx, eax
0x14003568e  test    eax, eax
0x140035690  js      loc_140035A29
0x140035696  movsd   xmm1, cs:dbl_140168990; double
0x14003569e  ucomisd xmm1, xmm6
0x1400356a2  jp      short loc_1400356A6
0x1400356a4  jz      short loc_1400356C2
0x1400356a6  mov     r9d, esi; unsigned int
0x1400356a9  lea     r8, aCompressionmet_0; "CompressionMetricUP"
0x1400356b0  mov     rcx, rdi; Stream
0x1400356b3  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x1400356b8  mov     edx, eax
0x1400356ba  test    eax, eax
0x1400356bc  js      loc_140035A29
0x1400356c2  movsd   xmm1, cs:dbl_1401688B0; double
0x1400356ca  ucomisd xmm1, xmm6
0x1400356ce  jp      short loc_1400356D2
0x1400356d0  jz      short loc_1400356EE
0x1400356d2  mov     r9d, esi; unsigned int
0x1400356d5  lea     r8, aEncryptionmetr; "EncryptionMetricUP"
0x1400356dc  mov     rcx, rdi; Stream
0x1400356df  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x1400356e4  mov     edx, eax
0x1400356e6  test    eax, eax
0x1400356e8  js      loc_140035A29
0x1400356ee  movsd   xmm1, cs:dbl_1401688B8; double
0x1400356f6  ucomisd xmm1, xmm6
0x1400356fa  jp      short loc_1400356FE
0x1400356fc  jz      short loc_14003571A
0x1400356fe  mov     r9d, esi; unsigned int
0x140035701  lea     r8, aCpucompression_1; "CPUCompression2MetricUP"
0x140035708  mov     rcx, rdi; Stream
0x14003570b  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x140035710  mov     edx, eax
0x140035712  test    eax, eax
0x140035714  js      loc_140035A29
0x14003571a  movsd   xmm1, cs:dbl_140168988; double
0x140035722  ucomisd xmm1, xmm6
0x140035726  jp      short loc_14003572A
0x140035728  jz      short loc_140035746
0x14003572a  mov     r9d, esi; unsigned int
0x14003572d  lea     r8, aEncryption2met_0; "Encryption2MetricUP"
0x140035734  mov     rcx, rdi; Stream
0x140035737  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x14003573c  mov     edx, eax
0x14003573e  test    eax, eax
0x140035740  js      loc_140035A29
0x140035746  movsd   xmm1, cs:dbl_140168908; double
0x14003574e  ucomisd xmm1, xmm6
0x140035752  jp      short loc_140035756
0x140035754  jz      short loc_140035772
0x140035756  mov     r9d, esi; unsigned int
0x140035759  lea     r8, aDshowencodetim; "DshowEncodeTime"
0x140035760  mov     rcx, rdi; Stream
0x140035763  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x140035768  mov     edx, eax
0x14003576a  test    eax, eax
0x14003576c  js      loc_140035A29
0x140035772  movsd   xmm1, cs:dbl_140168938; double
0x14003577a  ucomisd xmm1, xmm6
0x14003577e  jp      short loc_140035782
0x140035780  jz      short loc_14003579E
0x140035782  mov     r9d, esi; unsigned int
0x140035785  lea     r8, aBandwidth; "Bandwidth"
0x14003578c  mov     rcx, rdi; Stream
0x14003578f  call    ?WriteXMLMetric@@YAJPEAU_iobuf@@NPEBGK@Z; WriteXMLMetric(_iobuf *,double,ushort const *,ulong)
0x140035794  mov     edx, eax
0x140035796  test    eax, eax
0x140035798  js      loc_140035A29
0x14003579e  mov     rcx, qword ptr cs:Block+8
0x1400357a5  mov     rbx, qword ptr cs:Block
0x1400357ac  cmp     rcx, rbx
0x1400357af  jz      loc_140035869
0x1400357b5  mov     ebp, 64h ; 'd'
0x1400357ba  cmp     rbx, rcx
0x1400357bd  jz      loc_140035869
0x1400357c3  mov     r9, [rbx]
0x1400357c6  lea     r8, aWs; "%ws"
0x1400357cd  mov     rdx, rbp; unsigned __int64
0x1400357d0  lea     rcx, [rsp+138h+var_118]; unsigned __int16 *
0x1400357d5  mov     r9, [r9+8]
0x1400357d9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400357de  mov     edx, eax
0x1400357e0  test    eax, eax
0x1400357e2  js      loc_140035A29
0x1400357e8  mov     rcx, [rbx]
0x1400357eb  lea     rdx, aFps_0; "Fps"
0x1400357f2  mov     rcx, [rcx+8]; Str
0x1400357f6  call    cs:__imp_wcsstr
0x1400357fc  test    rax, rax
0x1400357ff  jz      short loc_140035837
0x140035801  mov     rcx, [rbx]
0x140035804  mov     edx, [rcx+4]
0x140035807  test    edx, edx
0x140035809  jz      short loc_140035819
0x14003580b  cmp     edx, r14d
0x14003580e  jnz     short loc_140035837
0x140035810  lea     r8, a10; "10"
0x140035817  jmp     short loc_140035820
0x140035819  lea     r8, a9; "9"
0x140035820  mov     rdx, rbp; unsigned __int64
0x140035823  lea     rcx, [rsp+138h+var_118]; unsigned __int16 *
  ... truncated ...
```
