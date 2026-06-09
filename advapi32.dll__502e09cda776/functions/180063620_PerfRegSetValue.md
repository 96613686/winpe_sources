# PerfRegSetValue

- ea: `0x180063620`
- end: `0x180063acc`
- name: `PerfRegSetValue`
- size: `1196`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callees

- `0x180001978`
- `0x180002e40`
- `0x18000ec08`
- `0x18000ecf0`
- `0x180027f50`
- `0x180029698`
- `0x180032954`
- `0x18003c6c8`
- `0x18003e354`
- `0x18003fb18`
- `0x180063620`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x18006365d`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18006365d`
- `ntdll!RtlInitUnicodeString` at `0x1800637e7`
- `ntdll!RtlInitUnicodeString` at `0x1800637e7`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180063760`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x1800637b2`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180063760`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x1800637b2`
- `KERNEL32!LocalFree` at `0x1800637c8`
- `KERNEL32!LocalFree` at `0x180063a81`
- `KERNEL32!LocalFree` at `0x1800637c8`
- `KERNEL32!LocalFree` at `0x180063a81`

## string_xrefs

- `0x1800636cb`: `Configuration Flags`

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
  RtlRunOnceExecuteOnce(qword_1800B21D0, PerfpInitializeCallback, 0, 0);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, a2);
  QueryType = GetQueryType(a2);
  KeyPerflib = PerflibciGetKeyPerflib();
  if ( !KeyPerflib
    || (*(_DWORD *)v26 = 0,
        v28 = 0,
        LangIdFromSzLang = 4,
        (unsigned int)PrivateRegQueryValueExT(KeyPerflib, L"Configuration Flags", v11, &v28, v26, &LangIdFromSzLang, 1))
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
        if ( (int)PerfGetNames(v13, &stru_1800755F0, &DestinationString, a5, &a6, 0, v23) >= 0 )
          goto LABEL_54;
        *(_OWORD *)&NativeLangId = 0;
        PerfGetLangId(LangIdFromSzLang & 0x3FF, 1u, &NativeLangId, 8u);
        a6 = v27;
        if ( (int)PerfGetNames(v13, &stru_1800755F0, &DestinationString, a5, &a6, 0, &NativeLangId) >= 0 )
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
    Names = PerfGetNames(v13, &stru_1800755F0, &DestinationString, a5, &a6, 0, L"009");
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
  v16 = PerfGetNames(v13, &stru_1800755F0, &DestinationString, a5, &a6, 0, L"009");
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
    if ( (int)PerfGetNames(v13, &stru_1800755F0, &DestinationString, a5, &a6, 0, v19) < 0 )
    {
      *(_OWORD *)&NativeLangId = 0;
      PerfGetLangId(v21 & 0x3FF, 1u, &NativeLangId, 8u);
      a6 = v27;
      Names = PerfGetNames(v13, &stru_1800755F0, &DestinationString, a5, &a6, 0, &NativeLangId);
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
0x180063620  push    rbp
0x180063622  push    rbx
0x180063623  push    rsi
0x180063624  push    rdi
0x180063625  push    r12
0x180063627  push    r13
0x180063629  push    r14
0x18006362b  push    r15
0x18006362d  mov     rbp, rsp
0x180063630  sub     rsp, 68h
0x180063634  mov     r13d, [rbp+arg_28]
0x180063638  mov     r15, rdx
0x18006363b  mov     r14, rcx
0x18006363e  mov     [rbp+var_24], r13d
0x180063642  xorps   xmm0, xmm0
0x180063645  lea     rdx, PerfpInitializeCallback
0x18006364c  lea     rcx, qword_1800B21D0
0x180063653  xor     r9d, r9d
0x180063656  xor     r8d, r8d
0x180063659  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18006365d  call    cs:__imp_RtlRunOnceExecuteOnce
0x180063664  nop     dword ptr [rax+rax+00h]
0x180063669  mov     rcx, cs:WPP_GLOBAL_Control
0x180063670  test    byte ptr [rcx+1Ch], 1
0x180063674  jz      short loc_180063694
0x180063676  cmp     byte ptr [rcx+19h], 4
0x18006367a  jb      short loc_180063694
0x18006367c  mov     rcx, [rcx+10h]
0x180063680  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180063687  mov     edx, 2Ah ; '*'
0x18006368c  mov     r9, r15
0x18006368f  call    WPP_SF_S
0x180063694  mov     rcx, r15; String1
0x180063697  call    ?GetQueryType@@YAKPEAG@Z; GetQueryType(ushort *)
0x18006369c  mov     ebx, eax
0x18006369e  call    ?PerflibciGetKeyPerflib@@YAPEAUHKEY__@@XZ; PerflibciGetKeyPerflib(void)
0x1800636a3  xor     edi, edi
0x1800636a5  test    rax, rax
0x1800636a8  jz      short loc_1800636F7
0x1800636aa  lea     rcx, [rbp+var_1C]
0x1800636ae  mov     dword ptr [rsp+68h+var_38], 1; int
0x1800636b6  mov     [rsp+68h+var_40], rcx; unsigned int *
0x1800636bb  lea     r9, [rbp+var_20]; unsigned int *
0x1800636bf  lea     rcx, [rbp+var_28]
0x1800636c3  mov     dword ptr [rbp+var_28], edi
0x1800636c6  mov     [rsp+68h+var_48], rcx; unsigned __int8 *
0x1800636cb  lea     rdx, ?cszPerflibFlags@@3QBGB; "Configuration Flags"
0x1800636d2  mov     rcx, rax; KeyHandle
0x1800636d5  mov     [rbp+var_20], edi
0x1800636d8  mov     [rbp+var_1C], 4
0x1800636df  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x1800636e4  test    eax, eax
0x1800636e6  jnz     short loc_1800636F7
0x1800636e8  cmp     [rbp+var_20], 4
0x1800636ec  jnz     short loc_1800636F7
0x1800636ee  test    dword ptr [rbp+var_28], 10000h
0x1800636f5  jnz     short loc_18006370B
0x1800636f7  mov     eax, ebx
0x1800636f9  shr     eax, 10h
0x1800636fc  test    ax, ax
0x1800636ff  jnz     short loc_18006370B
0x180063701  mov     esi, 3F2h
0x180063706  jmp     loc_180063A8D
0x18006370b  lea     eax, [rbx-5]
0x18006370e  mov     ecx, 0FFFDh
0x180063713  test    cx, ax
0x180063716  jz      short loc_180063727
0x180063718  sub     bx, 6
0x18006371c  test    cx, bx
0x18006371f  jnz     short loc_180063701
0x180063721  lea     r12d, [rcx+0Bh]
0x180063725  jmp     short loc_18006372D
0x180063727  mov     r12d, 10007h
0x18006372d  lea     rax, [r14+7FFFFFB0h]
0x180063734  test    rax, 0FFFFFFFFFFFFFFEFh
0x18006373a  jz      short loc_180063746
0x18006373c  mov     esi, 57h ; 'W'
0x180063741  jmp     loc_180063A8D
0x180063746  xor     r8d, r8d
0x180063749  mov     [rbp+var_20], edi
0x18006374c  lea     r9, [rbp+var_20]
0x180063750  mov     dword ptr [rbp+var_28], edi
0x180063753  lea     rdx, [rbp+var_28]
0x180063757  mov     esi, edi
0x180063759  mov     rbx, rdi
0x18006375c  lea     ecx, [r8+24h]
0x180063760  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x180063767  nop     dword ptr [rax+rax+00h]
0x18006376c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180063770  mov     edi, eax
0x180063772  test    eax, eax
0x180063774  jz      short loc_18006377D
0x180063776  cmp     eax, 0C0000023h
0x18006377b  jnz     short loc_1800637E0
0x18006377d  mov     eax, [rbp+var_20]
0x180063780  test    eax, eax
0x180063782  jz      short loc_1800637E0
0x180063784  mov     edx, eax
0x180063786  mov     eax, 2
0x18006378b  mul     rdx
0x18006378e  cmovb   rax, r8
0x180063792  mov     rcx, rax
0x180063795  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18006379a  mov     rbx, rax
0x18006379d  xor     eax, eax
0x18006379f  test    rbx, rbx
0x1800637a2  jz      short loc_1800637D8
0x1800637a4  lea     r9, [rbp+var_20]
0x1800637a8  mov     r8, rbx
0x1800637ab  lea     rdx, [rbp+var_28]
0x1800637af  lea     ecx, [rax+24h]
0x1800637b2  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x1800637b9  nop     dword ptr [rax+rax+00h]
0x1800637be  mov     edi, eax
0x1800637c0  cmp     dword ptr [rbp+var_28], esi
0x1800637c3  jnz     short loc_1800637E0
0x1800637c5  mov     rcx, rbx; hMem
0x1800637c8  call    cs:__imp_LocalFree
0x1800637cf  nop     dword ptr [rax+rax+00h]
0x1800637d4  xor     ebx, ebx
0x1800637d6  jmp     short loc_1800637E0
0x1800637d8  mov     dword ptr [rbp+var_28], eax
0x1800637db  mov     edi, 0C0000017h
0x1800637e0  mov     rdx, r15; SourceString
0x1800637e3  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800637e7  call    cs:__imp_RtlInitUnicodeString
0x1800637ee  nop     dword ptr [rax+rax+00h]
0x1800637f3  cmp     r14, 0FFFFFFFF80000050h
0x1800637fa  jnz     loc_180063919
0x180063800  mov     r9, [rbp+arg_20]; unsigned __int8 *
0x180063804  lea     rax, ?DefaultLangId@@3QBGB; "009"
0x18006380b  mov     [rsp+68h+var_38], rax; unsigned __int16 *
0x180063810  lea     r14, stru_1800755F0
0x180063817  lea     rax, [rbp+arg_28]
0x18006381b  xor     r15d, r15d
0x18006381e  mov     [rsp+68h+var_40], r15; unsigned int *
0x180063823  lea     r8, [rbp+DestinationString]; struct _UNICODE_STRING *
0x180063827  mov     rdx, r14; struct _UNICODE_STRING *
0x18006382a  mov     [rsp+68h+var_48], rax; unsigned int *
0x18006382f  mov     ecx, r12d; unsigned int
0x180063832  call    ?PerfGetNames@@YAJKPEBU_UNICODE_STRING@@0PEAEPEAK2PEBG@Z; PerfGetNames(ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar *,ulong *,ulong *,ushort const *)
0x180063837  mov     edi, eax
0x180063839  test    eax, eax
0x18006383b  jns     loc_180063A78
0x180063841  test    rbx, rbx
0x180063844  jz      loc_180063A44
0x18006384a  cmp     [rbx], r15w
0x18006384e  jz      loc_180063A44
0x180063854  or      rax, 0FFFFFFFFFFFFFFFFh
0x180063858  inc     rax
0x18006385b  cmp     [rbx+rax*2], r15w
0x180063860  jnz     short loc_180063858
0x180063862  inc     rax
0x180063865  lea     rax, [rbx+rax*2]
0x180063869  cmp     [rax], r15w
0x18006386d  jz      short loc_180063890
0x18006386f  mov     rdi, rax
0x180063872  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180063876  inc     rcx
0x180063879  cmp     [rax+rcx*2], r15w
0x18006387e  jnz     short loc_180063876
0x180063880  lea     rax, [rax+rcx*2]
0x180063884  add     rax, 2
0x180063888  cmp     [rax], r15w
0x18006388c  jnz     short loc_18006386F
0x18006388e  jmp     short loc_180063893
0x180063890  mov     rdi, rbx
0x180063893  mov     rcx, rdi; unsigned __int16 *
0x180063896  call    ?GetLangIdFromSzLang@@YAKPEBG@Z; GetLangIdFromSzLang(ushort const *)
0x18006389b  mov     r9, [rbp+arg_20]; unsigned __int8 *
0x18006389f  lea     r8, [rbp+DestinationString]; struct _UNICODE_STRING *
0x1800638a3  mov     [rsp+68h+var_38], rdi; unsigned __int16 *
0x1800638a8  mov     r15d, eax
0x1800638ab  lea     rax, [rbp+arg_28]
0x1800638af  mov     [rbp+arg_28], r13d
0x1800638b3  xor     edi, edi
0x1800638b5  mov     rdx, r14; struct _UNICODE_STRING *
0x1800638b8  mov     [rsp+68h+var_40], rdi; unsigned int *
0x1800638bd  mov     ecx, r12d; unsigned int
0x1800638c0  mov     [rsp+68h+var_48], rax; unsigned int *
0x1800638c5  call    ?PerfGetNames@@YAJKPEBU_UNICODE_STRING@@0PEAEPEAK2PEBG@Z; PerfGetNames(ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar *,ulong *,ulong *,ushort const *)
0x1800638ca  test    eax, eax
0x1800638cc  jns     loc_180063A78
0x1800638d2  movzx   ecx, r15w
0x1800638d6  lea     r13, ?NativeLangId@@3PAGA; ushort near * NativeLangId
0x1800638dd  xorps   xmm0, xmm0
0x1800638e0  lea     r9d, [rdi+8]; unsigned int
0x1800638e4  and     ecx, 3FFh; unsigned int
0x1800638ea  mov     r8, r13; unsigned __int16 *
0x1800638ed  mov     dl, 1; unsigned __int8
0x1800638ef  movups  cs:?NativeLangId@@3PAGA, xmm0; ushort near * NativeLangId
0x1800638f6  call    ?PerfGetLangId@@YAXKEPEAGK@Z; PerfGetLangId(ulong,uchar,ushort *,ulong)
0x1800638fb  mov     r8d, [rbp+var_24]
0x1800638ff  xor     r15d, r15d
0x180063902  mov     r9, [rbp+arg_20]
0x180063906  mov     [rsp+68h+var_38], r13
0x18006390b  mov     [rsp+68h+var_40], r15
0x180063910  mov     [rbp+arg_28], r8d
0x180063914  jmp     loc_180063A26
0x180063919  cmp     r14, 0FFFFFFFF80000060h
0x180063920  jnz     loc_180063A40
0x180063926  mov     r15, [rbp+arg_20]
0x18006392a  lea     r14, stru_1800755F0
0x180063931  xor     eax, eax
0x180063933  test    rbx, rbx
0x180063936  jz      loc_180063A0C
0x18006393c  cmp     [rbx], ax
0x18006393f  jz      loc_180063A0C
0x180063945  mov     rdi, rbx
0x180063948  lea     r13, ?NativeLangId@@3PAGA; ushort near * NativeLangId
0x18006394f  mov     rcx, rdi; unsigned __int16 *
0x180063952  call    ?GetLangIdFromSzLang@@YAKPEBG@Z; GetLangIdFromSzLang(ushort const *)
0x180063957  mov     r8d, [rbp+var_24]
0x18006395b  mov     r9, r15; unsigned __int8 *
0x18006395e  mov     [rbp+var_1C], eax
0x180063961  mov     rdx, r14; struct _UNICODE_STRING *
0x180063964  mov     [rbp+arg_28], r8d
0x180063968  lea     rax, [rbp+arg_28]
0x18006396c  mov     [rsp+68h+var_38], rdi; unsigned __int16 *
0x180063971  lea     r8, [rbp+DestinationString]; struct _UNICODE_STRING *
0x180063975  mov     [rsp+68h+var_40], rsi; unsigned int *
0x18006397a  mov     ecx, r12d; unsigned int
0x18006397d  mov     [rsp+68h+var_48], rax; unsigned int *
0x180063982  call    ?PerfGetNames@@YAJKPEBU_UNICODE_STRING@@0PEAEPEAK2PEBG@Z; PerfGetNames(ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar *,ulong *,ulong *,ushort const *)
0x180063987  test    eax, eax
0x180063989  jns     loc_180063A78
0x18006398f  movzx   ecx, word ptr [rbp+var_1C]
0x180063993  xorps   xmm0, xmm0
0x180063996  and     ecx, 3FFh; unsigned int
0x18006399c  mov     r9d, 8; unsigned int
0x1800639a2  mov     r8, r13; unsigned __int16 *
0x1800639a5  mov     dl, 1; unsigned __int8
0x1800639a7  movups  cs:?NativeLangId@@3PAGA, xmm0; ushort near * NativeLangId
0x1800639ae  call    ?PerfGetLangId@@YAXKEPEAGK@Z; PerfGetLangId(ulong,uchar,ushort *,ulong)
0x1800639b3  mov     eax, [rbp+var_24]
0x1800639b6  lea     r8, [rbp+DestinationString]; struct _UNICODE_STRING *
0x1800639ba  mov     [rbp+arg_28], eax
0x1800639bd  mov     r9, r15; unsigned __int8 *
0x1800639c0  lea     rax, [rbp+arg_28]
0x1800639c4  mov     [rsp+68h+var_38], r13; unsigned __int16 *
0x1800639c9  mov     [rsp+68h+var_40], rsi; unsigned int *
0x1800639ce  mov     rdx, r14; struct _UNICODE_STRING *
0x1800639d1  mov     ecx, r12d; unsigned int
0x1800639d4  mov     [rsp+68h+var_48], rax; unsigned int *
0x1800639d9  call    ?PerfGetNames@@YAJKPEBU_UNICODE_STRING@@0PEAEPEAK2PEBG@Z; PerfGetNames(ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar *,ulong *,ulong *,ushort const *)
0x1800639de  xor     ecx, ecx
0x1800639e0  test    eax, eax
0x1800639e2  jns     loc_180063A78
0x1800639e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800639ec  inc     rax
0x1800639ef  cmp     [rdi+rax*2], cx
0x1800639f3  jnz     short loc_1800639EC
0x1800639f5  lea     rdi, [rdi+rax*2]
0x1800639f9  add     rdi, 2
0x1800639fd  cmp     [rdi], cx
0x180063a00  jnz     loc_18006394F
0x180063a06  mov     r13d, [rbp+var_24]
0x180063a0a  jmp     short loc_180063A0E
0x180063a0c  xor     ecx, ecx
0x180063a0e  lea     rax, ?DefaultLangId@@3QBGB; "009"
0x180063a15  mov     [rbp+arg_28], r13d
0x180063a19  mov     [rsp+68h+var_38], rax; unsigned __int16 *
0x180063a1e  mov     r9, r15; unsigned __int8 *
0x180063a21  mov     [rsp+68h+var_40], rcx; unsigned int *
0x180063a26  lea     rax, [rbp+arg_28]
0x180063a2a  mov     rdx, r14; struct _UNICODE_STRING *
0x180063a2d  lea     r8, [rbp+DestinationString]; struct _UNICODE_STRING *
0x180063a31  mov     [rsp+68h+var_48], rax; unsigned int *
0x180063a36  mov     ecx, r12d; unsigned int
0x180063a39  call    ?PerfGetNames@@YAJKPEBU_UNICODE_STRING@@0PEAEPEAK2PEBG@Z; PerfGetNames(ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar *,ulong *,ulong *,ushort const *)
0x180063a3e  mov     edi, eax
0x180063a40  test    edi, edi
0x180063a42  jns     short loc_180063A78
0x180063a44  mov     rcx, cs:WPP_GLOBAL_Control
0x180063a4b  test    byte ptr [rcx+1Ch], 2
0x180063a4f  jz      short loc_180063A6F
0x180063a51  cmp     byte ptr [rcx+19h], 2
0x180063a55  jb      short loc_180063A6F
0x180063a57  mov     rcx, [rcx+10h]
0x180063a5b  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180063a62  mov     edx, 2Bh ; '+'
0x180063a67  mov     r9d, edi
0x180063a6a  call    WPP_SF_d
0x180063a6f  mov     ecx, edi; int
0x180063a71  call    ?PerfpDosError@@YAKJ@Z; PerfpDosError(long)
0x180063a76  mov     esi, eax
0x180063a78  cmp     dword ptr [rbp+var_28], 0
0x180063a7c  jbe     short loc_180063A8D
0x180063a7e  mov     rcx, rbx; hMem
0x180063a81  call    cs:__imp_LocalFree
0x180063a88  nop     dword ptr [rax+rax+00h]
0x180063a8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180063a94  test    byte ptr [rcx+1Ch], 1
0x180063a98  jz      short loc_180063AB8
0x180063a9a  cmp     byte ptr [rcx+19h], 4
0x180063a9e  jb      short loc_180063AB8
0x180063aa0  mov     rcx, [rcx+10h]
0x180063aa4  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180063aab  mov     edx, 2Ch ; ','
0x180063ab0  mov     r9d, esi
  ... truncated ...
```
