# FontStyleAttributes::GetString(array_ref<FontStyleAttributes::MatchingAxisValueRecord const>,array_ref<wchar_t const>,FontNameList const &)

- ea: `0x1800076c4`
- end: `0x180007b22`
- name: `?GetString@FontStyleAttributes@@QEBA?AVRefString@DWrite@@V?$array_ref@$$CBUMatchingAxisValueRecord@FontStyleAttributes@@@@V?$array_ref@$$CB_W@@AEBVFontNameList@@@Z`
- size: `1118`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x180006528`

## callees

- `0x1800076c4`
- `0x180007b28`
- `0x180007b9c`
- `0x180007c80`
- `0x180007d30`
- `0x180007e08`
- `0x180007fd4`
- `0x180008074`
- `0x1800080d8`
- `0x18000811c`
- `0x180008448`
- `0x180028c50`
- `0x18002ce34`
- `0x18009e3b8`
- `0x18009e420`
- `0x1800ab0aa`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800078c1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800078c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FontStyleAttributes::GetString(__int64 a1, __int64 a2, __int64 *a3, __int64 a4, _QWORD *a5)
{
  _QWORD *v9; // rbx
  __int64 v10; // rbx
  unsigned __int64 v11; // rdx
  rsize_t v12; // rdi
  wchar_t *v13; // rax
  __int64 v14; // rdi
  __int64 v15; // r15
  int v16; // ebx
  __int64 v17; // rax
  __int64 v18; // r9
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  unsigned int *v21; // r8
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // r8
  int v25; // eax
  unsigned __int64 v26; // rsi
  wchar_t *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  wchar_t *v31; // rax
  __int64 v32; // rax
  unsigned __int64 v33; // rax
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // r8
  int v36; // eax
  const wchar_t *v37; // rdx
  char *v38; // r8
  struct DWrite::RefString::Data *v40; // [rsp+28h] [rbp-49h] BYREF
  int v41; // [rsp+30h] [rbp-41h]
  __int64 v42; // [rsp+40h] [rbp-31h] BYREF
  int v43; // [rsp+48h] [rbp-29h]
  int v44; // [rsp+4Ch] [rbp-25h]
  void *Source[2]; // [rsp+50h] [rbp-21h] BYREF
  __int64 v46; // [rsp+60h] [rbp-11h] BYREF
  int v47; // [rsp+68h] [rbp-9h]
  __int128 v48; // [rsp+70h] [rbp-1h]

  RefStringBuilder::RefStringBuilder((RefStringBuilder *)&v40, 0x40u);
  v9 = a5;
  if ( *a5 != a5[1] )
  {
    LODWORD(a5) = 0;
    *(_OWORD *)Source = *(_OWORD *)a4;
    if ( !(unsigned __int8)FontNameList::FindLanguage(v9, Source, &a5) )
    {
      *(_OWORD *)Source = *(_OWORD *)&off_1800E7020;
      FontNameList::FindLanguage(v9, Source, &a5);
    }
    v10 = *(_QWORD *)(FontNameList::operator[](v9, (unsigned int)a5) + 32);
    v11 = *(unsigned int *)(v10 + 4);
    v12 = 2 * v11;
    v13 = RefStringBuilder::UninitializedAppend((RefStringBuilder *)&v40, v11);
    memcpy_s(v13, v12, (const void *const)(v10 + 8), v12);
  }
  v14 = *a3;
  v15 = a3[1];
  if ( *a3 != v15 )
  {
    v16 = HIDWORD(Source[1]);
    do
    {
      if ( (*(_BYTE *)v14 & 3) == 0 )
      {
        v17 = *(_QWORD *)(v14 + 16);
        if ( !*(_DWORD *)(v17 + 4) )
          goto LABEL_50;
        v18 = *(_QWORD *)(a1 + 32);
        v19 = *(unsigned int *)(a1 + 40);
        v20 = *(unsigned int *)(v17 + 4);
        if ( v20 > v19
          || (unsigned int)v19 - v20 < 4
          || (v21 = (unsigned int *)(v18 + v20), (((_BYTE)v18 + (_BYTE)v20) & 3) != 0) )
        {
LABEL_53:
          FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(*(_QWORD *)(a1 + 32));
        }
        v22 = v20 + 4;
        if ( v20 + 4 < v20 )
          goto LABEL_49;
        if ( v22 > 0xFFFFFFFF )
          goto LABEL_49;
        v20 = (unsigned int)v22 + 3LL;
        if ( v20 < (unsigned int)v22 || v20 > 0xFFFFFFFF )
          goto LABEL_49;
        v23 = (unsigned int)v20 & 0xFFFFFFFC;
        if ( v23 > v19 )
          goto LABEL_53;
        v24 = *v21;
        if ( v19 - v23 < v24 )
          goto LABEL_53;
        if ( (_DWORD)v24 )
        {
          LODWORD(a5) = 0;
          v42 = v23 + v18;
          v43 = v24;
          v44 = v16;
          BasedArrayPtr<NameDictionaryRegion,NameDictionaryRegion::LocalizedName,unsigned int,unsigned int,4>::GetCheckedPtr(
            &a5,
            &v46,
            &v42);
          v25 = v47;
        }
        else
        {
LABEL_50:
          v46 = 0;
          v25 = 0;
          v47 = 0;
        }
        v48 = *(_OWORD *)(a1 + 48);
        if ( v25 )
        {
          LODWORD(a5) = 0;
          if ( !FontNameDictionary::FindLanguage(
                  (FontNameDictionary *)&v46,
                  *(const wchar_t **)a4,
                  (__int64)(*(_QWORD *)(a4 + 8) - *(_QWORD *)a4) >> 1,
                  (unsigned int *)&a5) )
            FontNameDictionary::FindLanguage((FontNameDictionary *)&v46, L"en-us", L"" - L"en-us", (unsigned int *)&a5);
          FontNameDictionary::GetNameCheckedPtr(&v46, Source, (unsigned int)a5);
          v26 = LODWORD(Source[1]);
          if ( 2LL * LODWORD(Source[1]) )
          {
            if ( v41 )
            {
              v27 = RefStringBuilder::UninitializedAppend((RefStringBuilder *)&v40, 1u);
              if ( v27 )
              {
                *v27 = 32;
              }
              else
              {
                *(_DWORD *)_o__errno(v29, v28, v30) = 22;
                invalid_parameter_noinfo();
              }
            }
            v31 = RefStringBuilder::UninitializedAppend((RefStringBuilder *)&v40, v26);
            memcpy_s(v31, 2 * v26, Source[0], 2 * v26);
          }
        }
      }
      v14 += 40;
    }
    while ( v14 != v15 );
  }
  if ( !v41 )
  {
    v32 = CheckedPtr<unsigned char const,FailAsExceptionPolicy<InvalidCacheDataException>,unsigned int>::ReadAt<FontStyleAttributesRegion::Header>((__int64 *)(a1 + 32));
    if ( !*(_DWORD *)(v32 + 8) )
      goto LABEL_51;
    v18 = *(_QWORD *)(a1 + 32);
    v19 = *(unsigned int *)(a1 + 40);
    v20 = *(unsigned int *)(v32 + 8);
    if ( v20 > v19 )
      goto LABEL_54;
    if ( (unsigned int)v19 - v20 < 4 )
      goto LABEL_54;
    v21 = (unsigned int *)(v18 + v20);
    if ( (((_BYTE)v18 + (_BYTE)v20) & 3) != 0 )
      goto LABEL_54;
    v33 = v20 + 4;
    if ( v20 + 4 < v20
      || v33 > 0xFFFFFFFF
      || (v20 = (unsigned int)v33 + 3LL, v20 < (unsigned int)v33)
      || v20 > 0xFFFFFFFF )
    {
LABEL_49:
      SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v20, v19, v21, v18);
    }
    v34 = (unsigned int)v20 & 0xFFFFFFFC;
    if ( v34 > v19 || (v35 = *v21, v19 - v34 < v35) )
LABEL_54:
      FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(*(_QWORD *)(a1 + 32));
    if ( (_DWORD)v35 )
    {
      LODWORD(a5) = 0;
      v42 = v34 + v18;
      v43 = v35;
      v44 = HIDWORD(Source[1]);
      BasedArrayPtr<NameDictionaryRegion,NameDictionaryRegion::LocalizedName,unsigned int,unsigned int,4>::GetCheckedPtr(
        &a5,
        &v46,
        &v42);
      v36 = v47;
    }
    else
    {
LABEL_51:
      v46 = 0;
      v36 = 0;
      v47 = 0;
    }
    v48 = *(_OWORD *)(a1 + 48);
    if ( v36 )
    {
      LODWORD(a5) = 0;
      if ( !FontNameDictionary::FindLanguage(
              (FontNameDictionary *)&v46,
              *(const wchar_t **)a4,
              (__int64)(*(_QWORD *)(a4 + 8) - *(_QWORD *)a4) >> 1,
              (unsigned int *)&a5) )
        FontNameDictionary::FindLanguage((FontNameDictionary *)&v46, L"en-us", L"" - L"en-us", (unsigned int *)&a5);
      FontNameDictionary::GetNameCheckedPtr(&v46, Source, (unsigned int)a5);
      v37 = (const wchar_t *)Source[0];
      v38 = (char *)Source[0] + 2 * LODWORD(Source[1]);
    }
    else
    {
      v38 = 0;
      v37 = 0;
    }
    RefStringBuilder::Append((RefStringBuilder *)&v40, v37, (v38 - (char *)v37) >> 1);
  }
  RefStringBuilder::GetString(&v40, a2);
  DWrite::RefString::DecrementRef(v40);
  return a2;
}

```

## disassembly

```asm
0x1800076c4  mov     [rsp-8+arg_8], rdx
0x1800076c9  push    rbp
0x1800076ca  push    rbx
0x1800076cb  push    rsi
0x1800076cc  push    rdi
0x1800076cd  push    r12
0x1800076cf  push    r13
0x1800076d1  push    r14
0x1800076d3  push    r15
0x1800076d5  lea     rbp, [rsp-17h]
0x1800076da  sub     rsp, 88h
0x1800076e1  mov     r12, r9
0x1800076e4  mov     rsi, r8
0x1800076e7  mov     r13, rdx
0x1800076ea  mov     r14, rcx
0x1800076ed  mov     [rbp+4Fh+var_A0], 0
0x1800076f4  mov     edx, 40h ; '@'; unsigned __int64
0x1800076f9  lea     rcx, [rbp+4Fh+var_98]; this
0x1800076fd  call    ??0RefStringBuilder@@QEAA@_K@Z; RefStringBuilder::RefStringBuilder(unsigned __int64)
0x180007702  nop
0x180007703  mov     rbx, [rbp+4Fh+arg_20]
0x180007707  mov     rax, [rbx+8]
0x18000770b  cmp     [rbx], rax
0x18000770e  jz      short loc_18000776A
0x180007710  mov     dword ptr [rbp+4Fh+arg_20], 0
0x180007717  movaps  xmm0, xmmword ptr [r12]
0x18000771c  movdqa  xmmword ptr [rbp+4Fh+Source], xmm0
0x180007721  lea     r8, [rbp+4Fh+arg_20]
0x180007725  lea     rdx, [rbp+4Fh+Source]
0x180007729  mov     rcx, rbx
0x18000772c  call    ?FindLanguage@FontNameList@@QEBA_NV?$array_ref@$$CB_W@@PEAI@Z; FontNameList::FindLanguage(array_ref<wchar_t const>,uint *)
0x180007731  test    al, al
0x180007733  jz      loc_180007AB4
0x180007739  mov     edx, dword ptr [rbp+4Fh+arg_20]
0x18000773c  mov     rcx, rbx
0x18000773f  call    ??AFontNameList@@QEBAAEBV?$KeyValuePair@V?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@VRefString@DWrite@@@@_K@Z; FontNameList::operator[](unsigned __int64)
0x180007744  mov     rbx, [rax+20h]
0x180007748  mov     edx, [rbx+4]; unsigned __int64
0x18000774b  lea     rdi, [rdx+rdx]
0x18000774f  lea     rcx, [rbp+4Fh+var_98]; this
0x180007753  call    ?UninitializedAppend@RefStringBuilder@@QEAAPEA_W_K@Z; RefStringBuilder::UninitializedAppend(unsigned __int64)
0x180007758  lea     r8, [rbx+8]; Source
0x18000775c  mov     r9, rdi; SourceSize
0x18000775f  mov     rdx, rdi; DestinationSize
0x180007762  mov     rcx, rax; Destination
0x180007765  call    memcpy_s
0x18000776a  mov     rdi, [rsi]
0x18000776d  mov     r15, [rsi+8]
0x180007771  mov     r10d, 0FFFFFFFFh
0x180007777  mov     r11d, 0FFFFFFFCh
0x18000777d  cmp     rdi, r15
0x180007780  jz      loc_18000790B
0x180007786  mov     ebx, dword ptr [rbp+4Fh+Source+0Ch]
0x180007789  test    byte ptr [rdi], 3
0x18000778c  jnz     loc_1800078F1
0x180007792  mov     rax, [rdi+10h]
0x180007796  xor     esi, esi
0x180007798  cmp     [rax+4], esi
0x18000779b  jz      loc_180007A7E
0x1800077a1  mov     r9, [r14+20h]
0x1800077a5  mov     edx, [r14+28h]
0x1800077a9  mov     ecx, [rax+4]
0x1800077ac  cmp     rcx, rdx
0x1800077af  ja      loc_180007AA2
0x1800077b5  mov     eax, edx
0x1800077b7  sub     rax, rcx
0x1800077ba  cmp     rax, 4
0x1800077be  jb      loc_180007AA2
0x1800077c4  lea     r8, [r9+rcx]
0x1800077c8  test    r8b, 3
0x1800077cc  jnz     loc_180007AA2
0x1800077d2  lea     rax, [rcx+4]
0x1800077d6  cmp     rax, rcx
0x1800077d9  jb      loc_180007A78
0x1800077df  cmp     rax, r10
0x1800077e2  ja      loc_180007A78
0x1800077e8  mov     eax, eax
0x1800077ea  lea     rcx, [rax+3]
0x1800077ee  cmp     rcx, rax
0x1800077f1  jb      loc_180007A78
0x1800077f7  cmp     rcx, r10
0x1800077fa  ja      loc_180007A78
0x180007800  and     rcx, r11
0x180007803  cmp     rcx, rdx
0x180007806  ja      loc_180007AA2
0x18000780c  mov     r8d, [r8]
0x18000780f  sub     rdx, rcx
0x180007812  cmp     rdx, r8
0x180007815  jb      loc_180007AA2
0x18000781b  test    r8d, r8d
0x18000781e  jz      loc_180007A7E
0x180007824  mov     dword ptr [rbp+4Fh+arg_20], esi
0x180007827  lea     rax, [rcx+r9]
0x18000782b  mov     [rbp+4Fh+var_80], rax
0x18000782f  mov     [rbp+4Fh+var_78], r8d
0x180007833  mov     [rbp+4Fh+var_74], ebx
0x180007836  lea     r8, [rbp+4Fh+var_80]
0x18000783a  lea     rdx, [rbp+4Fh+var_60]
0x18000783e  lea     rcx, [rbp+4Fh+arg_20]
0x180007842  call    ?GetCheckedPtr@?$BasedArrayPtr@VNameDictionaryRegion@@ULocalizedName@1@II$03@@QEBA?AV?$CheckedPtr@$$CBULocalizedName@NameDictionaryRegion@@V?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@I@@VNameDictionaryRegion@@@Z; BasedArrayPtr<NameDictionaryRegion,NameDictionaryRegion::LocalizedName,uint,uint,4>::GetCheckedPtr(NameDictionaryRegion)
0x180007847  mov     eax, [rbp+4Fh+var_58]
0x18000784a  movups  xmm0, xmmword ptr [r14+30h]
0x18000784f  movdqu  [rbp+4Fh+var_50], xmm0
0x180007854  test    eax, eax
0x180007856  jz      loc_1800078F1
0x18000785c  mov     dword ptr [rbp+4Fh+arg_20], esi
0x18000785f  mov     r8, [r12+8]
0x180007864  sub     r8, [r12]
0x180007868  sar     r8, 1; unsigned __int64
0x18000786b  lea     r9, [rbp+4Fh+arg_20]; unsigned int *
0x18000786f  mov     rdx, [r12]; wchar_t *
0x180007873  lea     rcx, [rbp+4Fh+var_60]; this
0x180007877  call    ?FindLanguage@FontNameDictionary@@QEBA_NPEB_W_KPEAI@Z; FontNameDictionary::FindLanguage(wchar_t const *,unsigned __int64,uint *)
0x18000787c  test    al, al
0x18000787e  jz      loc_180007AD5
0x180007884  mov     r8d, dword ptr [rbp+4Fh+arg_20]
0x180007888  lea     rdx, [rbp+4Fh+Source]
0x18000788c  lea     rcx, [rbp+4Fh+var_60]
0x180007890  call    ?GetNameCheckedPtr@FontNameDictionary@@QEBA?AVStringCheckedPtr@@_K@Z; FontNameDictionary::GetNameCheckedPtr(unsigned __int64)
0x180007895  mov     esi, dword ptr [rbp+4Fh+Source+8]
0x180007898  lea     rax, [rsi+rsi]
0x18000789c  test    rax, rax
0x18000789f  jz      short loc_1800078F1
0x1800078a1  cmp     [rbp+4Fh+var_90], 0
0x1800078a5  jz      short loc_1800078D2
0x1800078a7  mov     edx, 1; unsigned __int64
0x1800078ac  lea     rcx, [rbp+4Fh+var_98]; this
0x1800078b0  call    ?UninitializedAppend@RefStringBuilder@@QEAAPEA_W_K@Z; RefStringBuilder::UninitializedAppend(unsigned __int64)
0x1800078b5  test    rax, rax
0x1800078b8  jz      short loc_1800078C1
0x1800078ba  mov     word ptr [rax], 20h ; ' '
0x1800078bf  jmp     short loc_1800078D2
0x1800078c1  call    cs:__imp__o__errno
0x1800078c7  mov     dword ptr [rax], 16h
0x1800078cd  call    _invalid_parameter_noinfo
0x1800078d2  mov     rdx, rsi; unsigned __int64
0x1800078d5  lea     rcx, [rbp+4Fh+var_98]; this
0x1800078d9  call    ?UninitializedAppend@RefStringBuilder@@QEAAPEA_W_K@Z; RefStringBuilder::UninitializedAppend(unsigned __int64)
0x1800078de  lea     rdx, [rsi+rsi]; DestinationSize
0x1800078e2  mov     r9, rdx; SourceSize
0x1800078e5  mov     r8, [rbp+4Fh+Source]; Source
0x1800078e9  mov     rcx, rax; Destination
0x1800078ec  call    memcpy_s
0x1800078f1  add     rdi, 28h ; '('
0x1800078f5  cmp     rdi, r15
0x1800078f8  jz      short loc_18000790B
0x1800078fa  mov     r10d, 0FFFFFFFFh
0x180007900  mov     r11d, 0FFFFFFFCh
0x180007906  jmp     loc_180007789
0x18000790b  xor     edi, edi
0x18000790d  cmp     [rbp+4Fh+var_90], edi
0x180007910  jnz     loc_180007A44
0x180007916  lea     rcx, [r14+20h]
0x18000791a  call    ??$ReadAt@UHeader@FontStyleAttributesRegion@@@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@I@@QEBAAEBUHeader@FontStyleAttributesRegion@@_K0@Z; CheckedPtr<uchar const,FailAsExceptionPolicy<InvalidCacheDataException>,uint>::ReadAt<FontStyleAttributesRegion::Header>(unsigned __int64,unsigned __int64)
0x18000791f  cmp     [rax+8], edi
0x180007922  jz      loc_180007A8C
0x180007928  mov     r9, [r14+20h]
0x18000792c  mov     edx, [r14+28h]
0x180007930  mov     ecx, [rax+8]
0x180007933  cmp     rcx, rdx
0x180007936  ja      loc_180007AAB
0x18000793c  mov     eax, edx
0x18000793e  sub     rax, rcx
0x180007941  cmp     rax, 4
0x180007945  jb      loc_180007AAB
0x18000794b  lea     r8, [r9+rcx]
0x18000794f  test    r8b, 3
0x180007953  jnz     loc_180007AAB
0x180007959  lea     rax, [rcx+4]
0x18000795d  cmp     rax, rcx
0x180007960  jb      loc_180007A78
0x180007966  mov     r10d, 0FFFFFFFFh
0x18000796c  cmp     rax, r10
0x18000796f  ja      loc_180007A78
0x180007975  mov     eax, eax
0x180007977  lea     rcx, [rax+3]
0x18000797b  cmp     rcx, rax
0x18000797e  jb      loc_180007A78
0x180007984  cmp     rcx, r10
0x180007987  ja      loc_180007A78
0x18000798d  mov     eax, 0FFFFFFFCh
0x180007992  and     rcx, rax
0x180007995  cmp     rcx, rdx
0x180007998  ja      loc_180007AAB
0x18000799e  mov     r8d, [r8]
0x1800079a1  sub     rdx, rcx
0x1800079a4  cmp     rdx, r8
0x1800079a7  jb      loc_180007AAB
0x1800079ad  test    r8d, r8d
0x1800079b0  jz      loc_180007A8C
0x1800079b6  mov     dword ptr [rbp+4Fh+arg_20], edi
0x1800079b9  lea     rax, [rcx+r9]
0x1800079bd  mov     [rbp+4Fh+var_80], rax
0x1800079c1  mov     [rbp+4Fh+var_78], r8d
0x1800079c5  mov     eax, dword ptr [rbp+4Fh+Source+0Ch]
0x1800079c8  mov     [rbp+4Fh+var_74], eax
0x1800079cb  lea     r8, [rbp+4Fh+var_80]
0x1800079cf  lea     rdx, [rbp+4Fh+var_60]
0x1800079d3  lea     rcx, [rbp+4Fh+arg_20]
0x1800079d7  call    ?GetCheckedPtr@?$BasedArrayPtr@VNameDictionaryRegion@@ULocalizedName@1@II$03@@QEBA?AV?$CheckedPtr@$$CBULocalizedName@NameDictionaryRegion@@V?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@I@@VNameDictionaryRegion@@@Z; BasedArrayPtr<NameDictionaryRegion,NameDictionaryRegion::LocalizedName,uint,uint,4>::GetCheckedPtr(NameDictionaryRegion)
0x1800079dc  mov     eax, [rbp+4Fh+var_58]
0x1800079df  movups  xmm0, xmmword ptr [r14+30h]
0x1800079e4  movdqu  [rbp+4Fh+var_50], xmm0
0x1800079e9  test    eax, eax
0x1800079eb  jz      loc_180007A9A
0x1800079f1  mov     dword ptr [rbp+4Fh+arg_20], edi
0x1800079f4  mov     r8, [r12+8]
0x1800079f9  sub     r8, [r12]
0x1800079fd  sar     r8, 1; unsigned __int64
0x180007a00  lea     r9, [rbp+4Fh+arg_20]; unsigned int *
0x180007a04  mov     rdx, [r12]; wchar_t *
0x180007a08  lea     rcx, [rbp+4Fh+var_60]; this
0x180007a0c  call    ?FindLanguage@FontNameDictionary@@QEBA_NPEB_W_KPEAI@Z; FontNameDictionary::FindLanguage(wchar_t const *,unsigned __int64,uint *)
0x180007a11  test    al, al
0x180007a13  jz      loc_180007AFB
0x180007a19  mov     r8d, dword ptr [rbp+4Fh+arg_20]
0x180007a1d  lea     rdx, [rbp+4Fh+Source]
0x180007a21  lea     rcx, [rbp+4Fh+var_60]
0x180007a25  call    ?GetNameCheckedPtr@FontNameDictionary@@QEBA?AVStringCheckedPtr@@_K@Z; FontNameDictionary::GetNameCheckedPtr(unsigned __int64)
0x180007a2a  mov     eax, dword ptr [rbp+4Fh+Source+8]
0x180007a2d  mov     rdx, [rbp+4Fh+Source]; wchar_t *
0x180007a31  lea     r8, [rdx+rax*2]
0x180007a35  sub     r8, rdx
0x180007a38  sar     r8, 1; unsigned __int64
0x180007a3b  lea     rcx, [rbp+4Fh+var_98]; this
0x180007a3f  call    ?Append@RefStringBuilder@@QEAAPEA_WPEB_W_K@Z; RefStringBuilder::Append(wchar_t const *,unsigned __int64)
0x180007a44  mov     rdx, r13
0x180007a47  lea     rcx, [rbp+4Fh+var_98]
0x180007a4b  call    ?GetString@RefStringBuilder@@QEAA?AVRefString@DWrite@@XZ; RefStringBuilder::GetString(void)
0x180007a50  mov     [rbp+4Fh+var_A0], 1
0x180007a57  mov     rcx, [rbp+4Fh+var_98]; struct DWrite::RefString::Data *
0x180007a5b  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180007a60  nop
0x180007a61  mov     rax, r13
0x180007a64  add     rsp, 88h
0x180007a6b  pop     r15
0x180007a6d  pop     r14
0x180007a6f  pop     r13
0x180007a71  pop     r12
0x180007a73  pop     rdi
0x180007a74  pop     rsi
0x180007a75  pop     rbx
0x180007a76  pop     rbp
0x180007a77  retn
0x180007a78  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
0x180007a7e  mov     [rbp+4Fh+var_60], rsi
0x180007a82  mov     eax, esi
0x180007a84  mov     [rbp+4Fh+var_58], eax
0x180007a87  jmp     loc_18000784A
0x180007a8c  mov     [rbp+4Fh+var_60], rdi
0x180007a90  mov     eax, edi
0x180007a92  mov     [rbp+4Fh+var_58], eax
0x180007a95  jmp     loc_1800079DF
0x180007a9a  mov     r8, rdi
0x180007a9d  mov     rdx, rdi
0x180007aa0  jmp     short loc_180007A35
0x180007aa2  mov     rcx, r9
0x180007aa5  call    ?OnOutOfRange@?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@SAXPEBX@Z; FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(void const *)
0x180007aab  mov     rcx, r9
0x180007aae  call    ?OnOutOfRange@?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@SAXPEBX@Z; FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(void const *)
0x180007ab4  movups  xmm0, xmmword ptr cs:off_1800E7020; "en-us"
0x180007abb  movdqu  xmmword ptr [rbp+4Fh+Source], xmm0
0x180007ac0  lea     r8, [rbp+4Fh+arg_20]
0x180007ac4  lea     rdx, [rbp+4Fh+Source]
0x180007ac8  mov     rcx, rbx
0x180007acb  call    ?FindLanguage@FontNameList@@QEBA_NV?$array_ref@$$CB_W@@PEAI@Z; FontNameList::FindLanguage(array_ref<wchar_t const>,uint *)
0x180007ad0  jmp     loc_180007739
0x180007ad5  mov     r8, cs:off_1800E7028; ""
0x180007adc  mov     rdx, cs:off_1800E7020; wchar_t *
0x180007ae3  sub     r8, rdx
0x180007ae6  sar     r8, 1; unsigned __int64
0x180007ae9  lea     r9, [rbp+4Fh+arg_20]; unsigned int *
0x180007aed  lea     rcx, [rbp+4Fh+var_60]; this
0x180007af1  call    ?FindLanguage@FontNameDictionary@@QEBA_NPEB_W_KPEAI@Z; FontNameDictionary::FindLanguage(wchar_t const *,unsigned __int64,uint *)
0x180007af6  jmp     loc_180007884
0x180007afb  mov     r8, cs:off_1800E7028; ""
0x180007b02  mov     rdx, cs:off_1800E7020; wchar_t *
0x180007b09  sub     r8, rdx
0x180007b0c  sar     r8, 1; unsigned __int64
0x180007b0f  lea     r9, [rbp+4Fh+arg_20]; unsigned int *
0x180007b13  lea     rcx, [rbp+4Fh+var_60]; this
0x180007b17  call    ?FindLanguage@FontNameDictionary@@QEBA_NPEB_W_KPEAI@Z; FontNameDictionary::FindLanguage(wchar_t const *,unsigned __int64,uint *)
0x180007b1c  jmp     loc_180007A19
```
