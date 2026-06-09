# PerfRegSetValue

- ea: `0x180057560`
- end: `0x1800579e7`
- name: `PerfRegSetValue`
- size: `1159`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callees

- `0x180015d70`
- `0x180015e40`
- `0x180017100`
- `0x1800257d0`
- `0x180026a7c`
- `0x18002bbd8`
- `0x18002eb70`
- `0x180038490`
- `0x18003b2bc`
- `0x18003b57c`
- `0x180057560`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x18005759d`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18005759d`
- `ntdll!RtlInitUnicodeString` at `0x18005770f`
- `ntdll!RtlInitUnicodeString` at `0x18005770f`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18005769a`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x1800576e6`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18005769a`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x1800576e6`
- `KERNEL32!LocalFree` at `0x1800576f6`
- `KERNEL32!LocalFree` at `0x1800579a3`
- `KERNEL32!LocalFree` at `0x1800576f6`
- `KERNEL32!LocalFree` at `0x1800579a3`

## string_xrefs

- `0x180057605`: `Configuration Flags`

## pseudocode

```c
__int64 __fastcall PerfRegSetValue(
        __int64 a1,
        wchar_t *a2,
        __int64 a3,
        __int64 a4,
        unsigned __int8 *a5,
        unsigned int a6)
{
  unsigned int v6; // r13d
  unsigned int QueryType; // ebx
  HKEY KeyPerflib; // rax
  unsigned int *v11; // r8
  unsigned int v12; // esi
  int v13; // r12d
  _WORD *v14; // rbx
  int ThreadPreferredUILanguages; // eax
  int v16; // edi
  __int64 v17; // rax
  unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // rdi
  __int64 v20; // rcx
  __int16 v21; // r15
  int Names; // eax
  unsigned __int16 *v23; // rdi
  __int64 v24; // rax
  unsigned __int8 v26[4]; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v27; // [rsp+44h] [rbp-24h]
  unsigned int v28; // [rsp+48h] [rbp-20h] BYREF
  unsigned int LangIdFromSzLang; // [rsp+4Ch] [rbp-1Ch] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-18h] BYREF

  v6 = a6;
  v27 = a6;
  DestinationString = 0;
  RtlRunOnceExecuteOnce(qword_1800A3088, PerfpInitializeCallback, 0, 0);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, a2);
  QueryType = GetQueryType(a2);
  KeyPerflib = PerflibciGetKeyPerflib();
  if ( !KeyPerflib
    || (*(_DWORD *)v26 = 0,
        v28 = 0,
        LangIdFromSzLang = 4,
        PrivateRegQueryValueExT(KeyPerflib, L"Configuration Flags", v11, &v28, v26, &LangIdFromSzLang, 1))
    || v28 != 4
    || (*(_DWORD *)v26 & 0x10000) == 0 )
  {
    if ( !HIWORD(QueryType) )
      goto LABEL_9;
  }
  if ( (((_WORD)QueryType - 5) & 0xFFFD) != 0 )
  {
    if ( (((_WORD)QueryType - 6) & 0xFFFD) != 0 )
    {
LABEL_9:
      v12 = 1010;
      goto LABEL_56;
    }
    v13 = 65544;
  }
  else
  {
    v13 = 65543;
  }
  if ( ((a1 + 2147483568) & 0xFFFFFFFFFFFFFFEFuLL) != 0 )
  {
    v12 = 87;
    goto LABEL_56;
  }
  v28 = 0;
  *(_DWORD *)v26 = 0;
  v12 = 0;
  v14 = 0;
  ThreadPreferredUILanguages = RtlGetThreadPreferredUILanguages(36, v26, 0, &v28);
  v16 = ThreadPreferredUILanguages;
  if ( (!ThreadPreferredUILanguages || ThreadPreferredUILanguages == -1073741789) && v28 )
  {
    v14 = (_WORD *)operator new(saturated_mul(v28, 2u));
    if ( v14 )
    {
      v16 = RtlGetThreadPreferredUILanguages(36, v26, v14, &v28);
      if ( !*(_DWORD *)v26 )
      {
        LocalFree(v14);
        v14 = 0;
      }
    }
    else
    {
      *(_DWORD *)v26 = 0;
      v16 = -1073741801;
    }
  }
  RtlInitUnicodeString(&DestinationString, a2);
  if ( a1 != -2147483568 )
  {
    if ( a1 != -2147483552 )
      goto LABEL_49;
    if ( v14 && *v14 )
    {
      v23 = v14;
      while ( 1 )
      {
        LangIdFromSzLang = GetLangIdFromSzLang(v23);
        a6 = v27;
        if ( (int)PerfGetNames(v13, &stru_180067610, &DestinationString, a5, &a6, 0, v23) >= 0 )
          goto LABEL_54;
        *(_OWORD *)&NativeLangId = 0;
        PerfGetLangId(LangIdFromSzLang & 0x3FF, 1u, &NativeLangId, 8u);
        a6 = v27;
        if ( (int)PerfGetNames(v13, &stru_180067610, &DestinationString, a5, &a6, 0, &NativeLangId) >= 0 )
          goto LABEL_54;
        v24 = -1;
        do
          ++v24;
        while ( v23[v24] );
        v23 += v24 + 1;
        if ( !*v23 )
        {
          v6 = v27;
          break;
        }
      }
    }
    a6 = v6;
    Names = PerfGetNames(v13, &stru_180067610, &DestinationString, a5, &a6, 0, L"009");
LABEL_48:
    v16 = Names;
LABEL_49:
    if ( v16 < 0 )
    {
LABEL_50:
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids,
          (unsigned int)v16);
      v12 = PerfpDosError(v16);
      goto LABEL_54;
    }
    goto LABEL_54;
  }
  v16 = PerfGetNames(v13, &stru_180067610, &DestinationString, a5, &a6, 0, L"009");
  if ( v16 < 0 )
  {
    if ( !v14 || !*v14 )
      goto LABEL_50;
    v17 = -1;
    do
      ++v17;
    while ( v14[v17] );
    v18 = &v14[v17 + 1];
    if ( *v18 )
    {
      do
      {
        v19 = v18;
        v20 = -1;
        do
          ++v20;
        while ( v18[v20] );
        v18 += v20 + 1;
      }
      while ( *v18 );
    }
    else
    {
      v19 = v14;
    }
    v21 = GetLangIdFromSzLang(v19);
    a6 = v6;
    if ( (int)PerfGetNames(v13, &stru_180067610, &DestinationString, a5, &a6, 0, v19) < 0 )
    {
      *(_OWORD *)&NativeLangId = 0;
      PerfGetLangId(v21 & 0x3FF, 1u, &NativeLangId, 8u);
      a6 = v27;
      Names = PerfGetNames(v13, &stru_180067610, &DestinationString, a5, &a6, 0, &NativeLangId);
      goto LABEL_48;
    }
  }
LABEL_54:
  if ( *(_DWORD *)v26 )
    LocalFree(v14);
LABEL_56:
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x180057560  push    rbp
0x180057562  push    rbx
0x180057563  push    rsi
0x180057564  push    rdi
0x180057565  push    r12
0x180057567  push    r13
0x180057569  push    r14
0x18005756b  push    r15
0x18005756d  mov     rbp, rsp
0x180057570  sub     rsp, 68h
0x180057574  mov     r13d, [rbp+arg_28]
0x180057578  mov     r15, rdx
0x18005757b  mov     r14, rcx
0x18005757e  mov     [rbp+var_24], r13d
0x180057582  xorps   xmm0, xmm0
0x180057585  lea     rdx, PerfpInitializeCallback
0x18005758c  lea     rcx, qword_1800A3088
0x180057593  xor     r9d, r9d
0x180057596  xor     r8d, r8d
0x180057599  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18005759d  call    cs:__imp_RtlRunOnceExecuteOnce
0x1800575a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800575aa  test    byte ptr [rcx+1Ch], 1
0x1800575ae  jz      short loc_1800575CE
0x1800575b0  cmp     byte ptr [rcx+19h], 4
0x1800575b4  jb      short loc_1800575CE
0x1800575b6  mov     rcx, [rcx+10h]
0x1800575ba  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x1800575c1  mov     edx, 2Ah ; '*'
0x1800575c6  mov     r9, r15
0x1800575c9  call    WPP_SF_S
0x1800575ce  mov     rcx, r15; String1
0x1800575d1  call    ?GetQueryType@@YAKPEAG@Z; GetQueryType(ushort *)
0x1800575d6  mov     ebx, eax
0x1800575d8  call    ?PerflibciGetKeyPerflib@@YAPEAUHKEY__@@XZ; PerflibciGetKeyPerflib(void)
0x1800575dd  xor     edi, edi
0x1800575df  test    rax, rax
0x1800575e2  jz      short loc_180057631
0x1800575e4  lea     rcx, [rbp+var_1C]
0x1800575e8  mov     dword ptr [rsp+68h+var_38], 1; int
0x1800575f0  mov     [rsp+68h+var_40], rcx; unsigned int *
0x1800575f5  lea     r9, [rbp+var_20]; unsigned int *
0x1800575f9  lea     rcx, [rbp+var_28]
0x1800575fd  mov     dword ptr [rbp+var_28], edi
0x180057600  mov     [rsp+68h+var_48], rcx; unsigned __int8 *
0x180057605  lea     rdx, ?cszPerflibFlags@@3QBGB; "Configuration Flags"
0x18005760c  mov     rcx, rax; KeyHandle
0x18005760f  mov     [rbp+var_20], edi
0x180057612  mov     [rbp+var_1C], 4
0x180057619  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x18005761e  test    eax, eax
0x180057620  jnz     short loc_180057631
0x180057622  cmp     [rbp+var_20], 4
0x180057626  jnz     short loc_180057631
0x180057628  test    dword ptr [rbp+var_28], 10000h
0x18005762f  jnz     short loc_180057645
0x180057631  mov     eax, ebx
0x180057633  shr     eax, 10h
0x180057636  test    ax, ax
0x180057639  jnz     short loc_180057645
0x18005763b  mov     esi, 3F2h
0x180057640  jmp     loc_1800579A9
0x180057645  lea     eax, [rbx-5]
0x180057648  mov     ecx, 0FFFDh
0x18005764d  test    cx, ax
0x180057650  jz      short loc_180057661
0x180057652  sub     bx, 6
0x180057656  test    cx, bx
0x180057659  jnz     short loc_18005763B
0x18005765b  lea     r12d, [rcx+0Bh]
0x18005765f  jmp     short loc_180057667
0x180057661  mov     r12d, 10007h
0x180057667  lea     rax, [r14+7FFFFFB0h]
0x18005766e  test    rax, 0FFFFFFFFFFFFFFEFh
0x180057674  jz      short loc_180057680
0x180057676  mov     esi, 57h ; 'W'
0x18005767b  jmp     loc_1800579A9
0x180057680  xor     r8d, r8d
0x180057683  mov     [rbp+var_20], edi
0x180057686  lea     r9, [rbp+var_20]
0x18005768a  mov     dword ptr [rbp+var_28], edi
0x18005768d  lea     rdx, [rbp+var_28]
0x180057691  mov     esi, edi
0x180057693  mov     rbx, rdi
0x180057696  lea     ecx, [r8+24h]
0x18005769a  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x1800576a0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800576a4  mov     edi, eax
0x1800576a6  test    eax, eax
0x1800576a8  jz      short loc_1800576B1
0x1800576aa  cmp     eax, 0C0000023h
0x1800576af  jnz     short loc_180057708
0x1800576b1  mov     eax, [rbp+var_20]
0x1800576b4  test    eax, eax
0x1800576b6  jz      short loc_180057708
0x1800576b8  mov     edx, eax
0x1800576ba  mov     eax, 2
0x1800576bf  mul     rdx
0x1800576c2  cmovb   rax, r8
0x1800576c6  mov     rcx, rax
0x1800576c9  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x1800576ce  mov     rbx, rax
0x1800576d1  xor     eax, eax
0x1800576d3  test    rbx, rbx
0x1800576d6  jz      short loc_180057700
0x1800576d8  lea     r9, [rbp+var_20]
0x1800576dc  mov     r8, rbx
0x1800576df  lea     rdx, [rbp+var_28]
0x1800576e3  lea     ecx, [rax+24h]
0x1800576e6  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x1800576ec  mov     edi, eax
0x1800576ee  cmp     dword ptr [rbp+var_28], esi
0x1800576f1  jnz     short loc_180057708
0x1800576f3  mov     rcx, rbx; hMem
0x1800576f6  call    cs:__imp_LocalFree
0x1800576fc  xor     ebx, ebx
0x1800576fe  jmp     short loc_180057708
0x180057700  mov     dword ptr [rbp+var_28], eax
0x180057703  mov     edi, 0C0000017h
0x180057708  mov     rdx, r15; SourceString
0x18005770b  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005770f  call    cs:__imp_RtlInitUnicodeString
0x180057715  cmp     r14, 0FFFFFFFF80000050h
0x18005771c  jnz     loc_18005783B
0x180057722  mov     r9, [rbp+arg_20]; unsigned __int8 *
0x180057726  lea     rax, ?DefaultLangId@@3QBGB; "009"
0x18005772d  mov     [rsp+68h+var_38], rax; unsigned __int16 *
0x180057732  lea     r14, stru_180067610
0x180057739  lea     rax, [rbp+arg_28]
0x18005773d  xor     r15d, r15d
0x180057740  mov     [rsp+68h+var_40], r15; unsigned int *
0x180057745  lea     r8, [rbp+DestinationString]; struct _UNICODE_STRING *
0x180057749  mov     rdx, r14; struct _UNICODE_STRING *
0x18005774c  mov     [rsp+68h+var_48], rax; unsigned int *
0x180057751  mov     ecx, r12d; unsigned int
0x180057754  call    ?PerfGetNames@@YAJKPEBU_UNICODE_STRING@@0PEAEPEAK2PEBG@Z; PerfGetNames(ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar *,ulong *,ulong *,ushort const *)
0x180057759  mov     edi, eax
0x18005775b  test    eax, eax
0x18005775d  jns     loc_18005799A
0x180057763  test    rbx, rbx
0x180057766  jz      loc_180057966
0x18005776c  cmp     [rbx], r15w
0x180057770  jz      loc_180057966
0x180057776  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005777a  inc     rax
0x18005777d  cmp     [rbx+rax*2], r15w
0x180057782  jnz     short loc_18005777A
0x180057784  inc     rax
0x180057787  lea     rax, [rbx+rax*2]
0x18005778b  cmp     [rax], r15w
0x18005778f  jz      short loc_1800577B2
0x180057791  mov     rdi, rax
0x180057794  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180057798  inc     rcx
0x18005779b  cmp     [rax+rcx*2], r15w
0x1800577a0  jnz     short loc_180057798
0x1800577a2  lea     rax, [rax+rcx*2]
0x1800577a6  add     rax, 2
0x1800577aa  cmp     [rax], r15w
0x1800577ae  jnz     short loc_180057791
0x1800577b0  jmp     short loc_1800577B5
0x1800577b2  mov     rdi, rbx
0x1800577b5  mov     rcx, rdi; unsigned __int16 *
0x1800577b8  call    ?GetLangIdFromSzLang@@YAKPEBG@Z; GetLangIdFromSzLang(ushort const *)
0x1800577bd  mov     r9, [rbp+arg_20]; unsigned __int8 *
0x1800577c1  lea     r8, [rbp+DestinationString]; struct _UNICODE_STRING *
0x1800577c5  mov     [rsp+68h+var_38], rdi; unsigned __int16 *
0x1800577ca  mov     r15d, eax
0x1800577cd  lea     rax, [rbp+arg_28]
0x1800577d1  mov     [rbp+arg_28], r13d
0x1800577d5  xor     edi, edi
0x1800577d7  mov     rdx, r14; struct _UNICODE_STRING *
0x1800577da  mov     [rsp+68h+var_40], rdi; unsigned int *
0x1800577df  mov     ecx, r12d; unsigned int
0x1800577e2  mov     [rsp+68h+var_48], rax; unsigned int *
0x1800577e7  call    ?PerfGetNames@@YAJKPEBU_UNICODE_STRING@@0PEAEPEAK2PEBG@Z; PerfGetNames(ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar *,ulong *,ulong *,ushort const *)
0x1800577ec  test    eax, eax
0x1800577ee  jns     loc_18005799A
0x1800577f4  movzx   ecx, r15w
0x1800577f8  lea     r13, ?NativeLangId@@3PAGA; ushort near * NativeLangId
0x1800577ff  xorps   xmm0, xmm0
0x180057802  lea     r9d, [rdi+8]; unsigned int
0x180057806  and     ecx, 3FFh; unsigned int
0x18005780c  mov     r8, r13; unsigned __int16 *
0x18005780f  mov     dl, 1; unsigned __int8
0x180057811  movups  cs:?NativeLangId@@3PAGA, xmm0; ushort near * NativeLangId
0x180057818  call    ?PerfGetLangId@@YAXKEPEAGK@Z; PerfGetLangId(ulong,uchar,ushort *,ulong)
0x18005781d  mov     r8d, [rbp+var_24]
0x180057821  xor     r15d, r15d
0x180057824  mov     r9, [rbp+arg_20]
0x180057828  mov     [rsp+68h+var_38], r13
0x18005782d  mov     [rsp+68h+var_40], r15
0x180057832  mov     [rbp+arg_28], r8d
0x180057836  jmp     loc_180057948
0x18005783b  cmp     r14, 0FFFFFFFF80000060h
0x180057842  jnz     loc_180057962
0x180057848  mov     r15, [rbp+arg_20]
0x18005784c  lea     r14, stru_180067610
0x180057853  xor     eax, eax
0x180057855  test    rbx, rbx
0x180057858  jz      loc_18005792E
0x18005785e  cmp     [rbx], ax
0x180057861  jz      loc_18005792E
0x180057867  mov     rdi, rbx
0x18005786a  lea     r13, ?NativeLangId@@3PAGA; ushort near * NativeLangId
0x180057871  mov     rcx, rdi; unsigned __int16 *
0x180057874  call    ?GetLangIdFromSzLang@@YAKPEBG@Z; GetLangIdFromSzLang(ushort const *)
0x180057879  mov     r8d, [rbp+var_24]
0x18005787d  mov     r9, r15; unsigned __int8 *
0x180057880  mov     [rbp+var_1C], eax
0x180057883  mov     rdx, r14; struct _UNICODE_STRING *
0x180057886  mov     [rbp+arg_28], r8d
0x18005788a  lea     rax, [rbp+arg_28]
0x18005788e  mov     [rsp+68h+var_38], rdi; unsigned __int16 *
0x180057893  lea     r8, [rbp+DestinationString]; struct _UNICODE_STRING *
0x180057897  mov     [rsp+68h+var_40], rsi; unsigned int *
0x18005789c  mov     ecx, r12d; unsigned int
0x18005789f  mov     [rsp+68h+var_48], rax; unsigned int *
0x1800578a4  call    ?PerfGetNames@@YAJKPEBU_UNICODE_STRING@@0PEAEPEAK2PEBG@Z; PerfGetNames(ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar *,ulong *,ulong *,ushort const *)
0x1800578a9  test    eax, eax
0x1800578ab  jns     loc_18005799A
0x1800578b1  movzx   ecx, word ptr [rbp+var_1C]
0x1800578b5  xorps   xmm0, xmm0
0x1800578b8  and     ecx, 3FFh; unsigned int
0x1800578be  mov     r9d, 8; unsigned int
0x1800578c4  mov     r8, r13; unsigned __int16 *
0x1800578c7  mov     dl, 1; unsigned __int8
0x1800578c9  movups  cs:?NativeLangId@@3PAGA, xmm0; ushort near * NativeLangId
0x1800578d0  call    ?PerfGetLangId@@YAXKEPEAGK@Z; PerfGetLangId(ulong,uchar,ushort *,ulong)
0x1800578d5  mov     eax, [rbp+var_24]
0x1800578d8  lea     r8, [rbp+DestinationString]; struct _UNICODE_STRING *
0x1800578dc  mov     [rbp+arg_28], eax
0x1800578df  mov     r9, r15; unsigned __int8 *
0x1800578e2  lea     rax, [rbp+arg_28]
0x1800578e6  mov     [rsp+68h+var_38], r13; unsigned __int16 *
0x1800578eb  mov     [rsp+68h+var_40], rsi; unsigned int *
0x1800578f0  mov     rdx, r14; struct _UNICODE_STRING *
0x1800578f3  mov     ecx, r12d; unsigned int
0x1800578f6  mov     [rsp+68h+var_48], rax; unsigned int *
0x1800578fb  call    ?PerfGetNames@@YAJKPEBU_UNICODE_STRING@@0PEAEPEAK2PEBG@Z; PerfGetNames(ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar *,ulong *,ulong *,ushort const *)
0x180057900  xor     ecx, ecx
0x180057902  test    eax, eax
0x180057904  jns     loc_18005799A
0x18005790a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005790e  inc     rax
0x180057911  cmp     [rdi+rax*2], cx
0x180057915  jnz     short loc_18005790E
0x180057917  lea     rdi, [rdi+rax*2]
0x18005791b  add     rdi, 2
0x18005791f  cmp     [rdi], cx
0x180057922  jnz     loc_180057871
0x180057928  mov     r13d, [rbp+var_24]
0x18005792c  jmp     short loc_180057930
0x18005792e  xor     ecx, ecx
0x180057930  lea     rax, ?DefaultLangId@@3QBGB; "009"
0x180057937  mov     [rbp+arg_28], r13d
0x18005793b  mov     [rsp+68h+var_38], rax; unsigned __int16 *
0x180057940  mov     r9, r15; unsigned __int8 *
0x180057943  mov     [rsp+68h+var_40], rcx; unsigned int *
0x180057948  lea     rax, [rbp+arg_28]
0x18005794c  mov     rdx, r14; struct _UNICODE_STRING *
0x18005794f  lea     r8, [rbp+DestinationString]; struct _UNICODE_STRING *
0x180057953  mov     [rsp+68h+var_48], rax; unsigned int *
0x180057958  mov     ecx, r12d; unsigned int
0x18005795b  call    ?PerfGetNames@@YAJKPEBU_UNICODE_STRING@@0PEAEPEAK2PEBG@Z; PerfGetNames(ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar *,ulong *,ulong *,ushort const *)
0x180057960  mov     edi, eax
0x180057962  test    edi, edi
0x180057964  jns     short loc_18005799A
0x180057966  mov     rcx, cs:WPP_GLOBAL_Control
0x18005796d  test    byte ptr [rcx+1Ch], 2
0x180057971  jz      short loc_180057991
0x180057973  cmp     byte ptr [rcx+19h], 2
0x180057977  jb      short loc_180057991
0x180057979  mov     rcx, [rcx+10h]
0x18005797d  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180057984  mov     edx, 2Bh ; '+'
0x180057989  mov     r9d, edi
0x18005798c  call    WPP_SF_d
0x180057991  mov     ecx, edi; int
0x180057993  call    ?PerfpDosError@@YAKJ@Z; PerfpDosError(long)
0x180057998  mov     esi, eax
0x18005799a  cmp     dword ptr [rbp+var_28], 0
0x18005799e  jbe     short loc_1800579A9
0x1800579a0  mov     rcx, rbx; hMem
0x1800579a3  call    cs:__imp_LocalFree
0x1800579a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800579b0  test    byte ptr [rcx+1Ch], 1
0x1800579b4  jz      short loc_1800579D4
0x1800579b6  cmp     byte ptr [rcx+19h], 4
0x1800579ba  jb      short loc_1800579D4
0x1800579bc  mov     rcx, [rcx+10h]
0x1800579c0  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x1800579c7  mov     edx, 2Ch ; ','
0x1800579cc  mov     r9d, esi
0x1800579cf  call    WPP_SF_d
0x1800579d4  mov     eax, esi
0x1800579d6  add     rsp, 68h
0x1800579da  pop     r15
0x1800579dc  pop     r14
0x1800579de  pop     r13
  ... truncated ...
```
