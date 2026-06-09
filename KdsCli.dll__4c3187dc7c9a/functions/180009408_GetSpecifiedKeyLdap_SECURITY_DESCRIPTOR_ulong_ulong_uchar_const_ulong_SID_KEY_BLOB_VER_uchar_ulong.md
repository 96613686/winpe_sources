# GetSpecifiedKeyLdap(_SECURITY_DESCRIPTOR *,ulong,ulong,uchar * const,ulong,_SID_KEY_BLOB_VER,uchar *,ulong)

- ea: `0x180009408`
- end: `0x18000981f`
- name: `?GetSpecifiedKeyLdap@@YAJPEAU_SECURITY_DESCRIPTOR@@KKQEAEKW4_SID_KEY_BLOB_VER@@PEAEK@Z`
- size: `1047`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a034`

## callees

- `0x180003e08`
- `0x180003e30`
- `0x180009408`
- `0x180009828`
- `0x18000a154`
- `0x18000a26c`
- `0x180010950`
- `0x180010980`
- `0x180018c7c`
- `0x18001a450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009524`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009524`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009735`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000954a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009727`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000954a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009727`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009502`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009502`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000951a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000951a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097bc`

## string_xrefs

- `0x1800094b6`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x180009593`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x180009650`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x180009750`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x18000979b`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`

## pseudocode

```c
__int64 __fastcall GetSpecifiedKeyLdap(
        struct _SECURITY_DESCRIPTOR *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        int a6,
        _BYTE *a7,
        unsigned int a8)
{
  _BYTE *v8; // r12
  __int64 v12; // rdi
  __int64 v13; // r8
  unsigned __int8 *v14; // rsi
  unsigned int v15; // r14d
  _BYTE *v16; // rax
  int v17; // ebx
  signed int v18; // eax
  unsigned int v19; // edi
  HANDLE CurrentThread; // rax
  signed int v21; // eax
  unsigned int v22; // r9d
  unsigned int v23; // ecx
  signed int LastError; // eax
  int SIDKey; // eax
  unsigned int v26; // r9d
  unsigned int v27; // ecx
  struct _KEK_KEY_INFO *v28; // rsi
  signed int SpecifiedKeyLdapWorker; // eax
  _QWORD *v30; // rcx
  __int64 v31; // r8
  signed int v32; // eax
  __int64 v33; // rdx
  unsigned __int8 *v34; // rax
  int v36; // [rsp+50h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int8 *v38; // [rsp+60h] [rbp-10h] BYREF
  struct _KEK_KEY_INFO *v39; // [rsp+68h] [rbp-8h] BYREF
  unsigned int v41; // [rsp+C0h] [rbp+50h] BYREF

  v8 = a7;
  v36 = 0;
  v38 = 0;
  v41 = 0;
  v12 = 32;
  TokenHandle = 0;
  v13 = 32;
  a8 = 0;
  v14 = 0;
  v39 = 0;
  v15 = 0;
  v16 = a7;
  do
  {
    *v16++ = 0;
    --v13;
  }
  while ( v13 );
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_497df786d6153c614e507117de9dfe52_Traceguids, a3);
  if ( (a3 & 0x10000) == 0 )
  {
    v17 = -2146893815;
    goto LABEL_59;
  }
  v18 = QueryLdapRecoveryPort(&a8);
  v17 = v18;
  if ( v18 < 0 )
  {
    SidKeyDebugTraceError(v18, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", 0x865u);
    goto LABEL_59;
  }
  v19 = a8;
  if ( !a8 || a8 == 389 || a8 == 636 || a8 - 3268 <= 1 )
  {
    v17 = -2147024809;
    v22 = 2165;
    v23 = -2147024809;
    goto LABEL_57;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
  {
    if ( !SetThreadToken(0, 0) )
    {
      LastError = GetLastError();
      v17 = LastError;
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
      v22 = 2190;
      goto LABEL_18;
    }
    SIDKey = QueryLocalAdministrator(TokenHandle, &v36);
    v17 = SIDKey;
    if ( SIDKey >= 0 )
    {
      if ( !v36 )
      {
        v17 = -2147024891;
        v26 = 2207;
        v27 = -2147024891;
        goto LABEL_26;
      }
      SIDKey = ValidateClientKEKInfo(a4, a5, &v39);
      v17 = SIDKey;
      if ( SIDKey >= 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_497df786d6153c614e507117de9dfe52_Traceguids);
        v28 = v39;
        SpecifiedKeyLdapWorker = GetSpecifiedKeyLdapWorker(
                                   a1,
                                   a2,
                                   v19,
                                   (struct _GUID *)((char *)v39 + 24),
                                   *((_DWORD *)v39 + 3),
                                   *((_DWORD *)v39 + 4),
                                   *((_DWORD *)v39 + 5),
                                   &v38,
                                   &v41);
        v17 = SpecifiedKeyLdapWorker;
        if ( SpecifiedKeyLdapWorker < 0 )
        {
          SidKeyDebugTraceError(
            SpecifiedKeyLdapWorker,
            "hr",
            "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx",
            0x8BBu);
          v14 = v38;
          v15 = v41;
LABEL_47:
          if ( !SetThreadToken(0, TokenHandle) && v17 >= 0 )
          {
            v32 = GetLastError();
            v17 = v32;
            if ( v32 > 0 )
              v17 = (unsigned __int16)v32 | 0x80070000;
            SidKeyDebugTraceError(
              v17,
              "hr",
              "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx",
              0x8E0u);
          }
          if ( v14 )
          {
            v33 = v15;
            v34 = v14;
            if ( v15 )
            {
              do
              {
                *v34++ = 0;
                --v33;
              }
              while ( v33 );
            }
            SIDKeyProvFree(v14);
          }
          goto LABEL_58;
        }
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_497df786d6153c614e507117de9dfe52_Traceguids);
            v30 = WPP_GLOBAL_Control;
          }
          if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 4) != 0 )
            WPP_SF_(v30[2], 23, &WPP_497df786d6153c614e507117de9dfe52_Traceguids);
        }
        v31 = (__int64)v28;
        v14 = v38;
        v15 = v41;
        SIDKey = GenerateSIDKey((__int64)v38, v41, v31, a6, 0, 0, (__int64)v8);
        v17 = SIDKey;
        if ( SIDKey >= 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_497df786d6153c614e507117de9dfe52_Traceguids);
          goto LABEL_47;
        }
        v26 = 2253;
      }
      else
      {
        v26 = 2218;
      }
    }
    else
    {
      v26 = 2201;
    }
    v27 = SIDKey;
LABEL_26:
    SidKeyDebugTraceError(v27, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", v26);
    goto LABEL_47;
  }
  v21 = GetLastError();
  v17 = v21;
  if ( v21 > 0 )
    v17 = (unsigned __int16)v21 | 0x80070000;
  v22 = 2181;
LABEL_18:
  v23 = v17;
LABEL_57:
  SidKeyDebugTraceError(v23, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", v22);
LABEL_58:
  v12 = 32;
LABEL_59:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v17 < 0 )
  {
    do
    {
      *v8++ = 0;
      --v12;
    }
    while ( v12 );
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      &WPP_497df786d6153c614e507117de9dfe52_Traceguids,
      (unsigned int)v17);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180009408  mov     [rsp-38h+arg_8], rbx
0x18000940d  mov     [rsp-38h+arg_0], rcx
0x180009412  push    rbp
0x180009413  push    rsi
0x180009414  push    rdi
0x180009415  push    r12
0x180009417  push    r13
0x180009419  push    r14
0x18000941b  push    r15
0x18000941d  mov     rbp, rsp
0x180009420  sub     rsp, 70h
0x180009424  mov     r12, [rbp+arg_30]
0x180009428  xor     ecx, ecx
0x18000942a  mov     ebx, r8d
0x18000942d  mov     [rbp+var_20], ecx
0x180009430  mov     r15, r9
0x180009433  mov     [rbp+var_10], rcx
0x180009437  mov     r13d, edx
0x18000943a  mov     [rbp+arg_10], ecx
0x18000943d  lea     edi, [rcx+20h]
0x180009440  mov     [rbp+TokenHandle], rcx
0x180009444  mov     r8d, edi
0x180009447  mov     [rbp+arg_38], ecx
0x18000944a  mov     esi, ecx
0x18000944c  mov     [rbp+var_8], rcx
0x180009450  mov     r14d, ecx
0x180009453  mov     rax, r12
0x180009456  mov     [rax], cl
0x180009458  inc     rax
0x18000945b  sub     r8, 1
0x18000945f  jnz     short loc_180009456
0x180009461  mov     rcx, cs:WPP_GLOBAL_Control
0x180009468  lea     rax, WPP_GLOBAL_Control
0x18000946f  cmp     rcx, rax
0x180009472  jz      short loc_180009491
0x180009474  test    byte ptr [rcx+1Ch], 4
0x180009478  jz      short loc_180009491
0x18000947a  mov     rcx, [rcx+10h]
0x18000947e  lea     edx, [r8+14h]
0x180009482  lea     r8, WPP_497df786d6153c614e507117de9dfe52_Traceguids
0x180009489  mov     r9d, ebx
0x18000948c  call    WPP_SF_D
0x180009491  bt      ebx, 10h
0x180009495  jb      short loc_1800094A1
0x180009497  mov     ebx, 80090009h
0x18000949c  jmp     loc_1800097B3
0x1800094a1  lea     rcx, [rbp+arg_38]; unsigned int *
0x1800094a5  call    ?QueryLdapRecoveryPort@@YAJPEAK@Z; QueryLdapRecoveryPort(ulong *)
0x1800094aa  mov     ebx, eax
0x1800094ac  test    eax, eax
0x1800094ae  jns     short loc_1800094D0
0x1800094b0  mov     r9d, 865h; unsigned int
0x1800094b6  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800094bd  lea     rdx, aHr; "hr"
0x1800094c4  mov     ecx, eax; unsigned int
0x1800094c6  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800094cb  jmp     loc_1800097B3
0x1800094d0  mov     edi, [rbp+arg_38]
0x1800094d3  test    edi, edi
0x1800094d5  jz      loc_18000978B
0x1800094db  cmp     edi, 185h
0x1800094e1  jz      loc_18000978B
0x1800094e7  cmp     edi, 27Ch
0x1800094ed  jz      loc_18000978B
0x1800094f3  lea     eax, [rdi-0CC4h]
0x1800094f9  cmp     eax, 1
0x1800094fc  jbe     loc_18000978B
0x180009502  call    cs:__imp_GetCurrentThread
0x180009508  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18000950c  mov     edx, 2000Ch; DesiredAccess
0x180009511  mov     rcx, rax; ThreadHandle
0x180009514  mov     r8d, 1; OpenAsSelf
0x18000951a  call    cs:__imp_OpenThreadToken
0x180009520  test    eax, eax
0x180009522  jnz     short loc_180009546
0x180009524  call    cs:__imp_GetLastError
0x18000952a  mov     ebx, eax
0x18000952c  test    eax, eax
0x18000952e  jle     short loc_180009539
0x180009530  movzx   ebx, ax
0x180009533  or      ebx, 80070000h
0x180009539  mov     r9d, 885h
0x18000953f  mov     ecx, ebx
0x180009541  jmp     loc_18000979B
0x180009546  xor     edx, edx; Token
0x180009548  xor     ecx, ecx; Thread
0x18000954a  call    cs:__imp_SetThreadToken
0x180009550  test    eax, eax
0x180009552  jnz     short loc_180009571
0x180009554  call    cs:__imp_GetLastError
0x18000955a  mov     ebx, eax
0x18000955c  test    eax, eax
0x18000955e  jle     short loc_180009569
0x180009560  movzx   ebx, ax
0x180009563  or      ebx, 80070000h
0x180009569  mov     r9d, 88Eh
0x18000956f  jmp     short loc_18000953F
0x180009571  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180009575  lea     rdx, [rbp+var_20]; int *
0x180009579  call    ?QueryLocalAdministrator@@YAJPEAXPEAH@Z; QueryLocalAdministrator(void *,int *)
0x18000957e  mov     ebx, eax
0x180009580  test    eax, eax
0x180009582  jns     short loc_1800095A4
0x180009584  mov     r9d, 899h; unsigned int
0x18000958a  mov     ecx, eax; unsigned int
0x18000958c  lea     rdx, aHr; "hr"
0x180009593  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000959a  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000959f  jmp     loc_180009721
0x1800095a4  cmp     [rbp+var_20], esi
0x1800095a7  jnz     short loc_1800095BB
0x1800095a9  mov     ebx, 80070005h
0x1800095ae  mov     r9d, 89Fh
0x1800095b4  mov     ecx, 80070005h
0x1800095b9  jmp     short loc_18000958C
0x1800095bb  mov     edx, [rbp+arg_20]; unsigned int
0x1800095be  lea     r8, [rbp+var_8]; struct _KEK_KEY_INFO **
0x1800095c2  mov     rcx, r15; unsigned __int8 *
0x1800095c5  call    ?ValidateClientKEKInfo@@YAJQEAEKPEAPEAU_KEK_KEY_INFO@@@Z; ValidateClientKEKInfo(uchar * const,ulong,_KEK_KEY_INFO * *)
0x1800095ca  mov     ebx, eax
0x1800095cc  test    eax, eax
0x1800095ce  jns     short loc_1800095D8
0x1800095d0  mov     r9d, 8AAh
0x1800095d6  jmp     short loc_18000958A
0x1800095d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095df  lea     r15, WPP_GLOBAL_Control
0x1800095e6  cmp     rcx, r15
0x1800095e9  jz      short loc_180009606
0x1800095eb  test    byte ptr [rcx+1Ch], 4
0x1800095ef  jz      short loc_180009606
0x1800095f1  mov     rcx, [rcx+10h]
0x1800095f5  lea     r8, WPP_497df786d6153c614e507117de9dfe52_Traceguids
0x1800095fc  mov     edx, 15h
0x180009601  call    WPP_SF_
0x180009606  mov     rsi, [rbp+var_8]
0x18000960a  lea     rax, [rbp+arg_10]
0x18000960e  mov     rcx, [rbp+arg_0]; struct _SECURITY_DESCRIPTOR *
0x180009612  mov     r8d, edi; unsigned int
0x180009615  mov     [rsp+70h+var_30], rax; unsigned int *
0x18000961a  mov     edx, r13d; unsigned int
0x18000961d  lea     rax, [rbp+var_10]
0x180009621  mov     [rsp+70h+var_38], rax; unsigned __int8 **
0x180009626  lea     r9, [rsi+18h]; struct _GUID *
0x18000962a  mov     eax, [rsi+14h]
0x18000962d  mov     [rsp+70h+var_40], eax; int
0x180009631  mov     eax, [rsi+10h]
0x180009634  mov     [rsp+70h+var_48], eax; int
0x180009638  mov     eax, [rsi+0Ch]
0x18000963b  mov     [rsp+70h+var_50], eax; int
0x18000963f  call    ?GetSpecifiedKeyLdapWorker@@YAJPEAU_SECURITY_DESCRIPTOR@@KKPEAU_GUID@@JJJPEAPEAEPEAK@Z; GetSpecifiedKeyLdapWorker(_SECURITY_DESCRIPTOR *,ulong,ulong,_GUID *,long,long,long,uchar * *,ulong *)
0x180009644  mov     ebx, eax
0x180009646  test    eax, eax
0x180009648  jns     short loc_180009672
0x18000964a  mov     r9d, 8BBh; unsigned int
0x180009650  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180009657  lea     rdx, aHr; "hr"
0x18000965e  mov     ecx, eax; unsigned int
0x180009660  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180009665  mov     rsi, [rbp+var_10]
0x180009669  mov     r14d, [rbp+arg_10]
0x18000966d  jmp     loc_180009721
0x180009672  mov     rcx, cs:WPP_GLOBAL_Control
0x180009679  cmp     rcx, r15
0x18000967c  jz      short loc_1800096C0
0x18000967e  test    byte ptr [rcx+1Ch], 4
0x180009682  jz      short loc_1800096A0
0x180009684  mov     rcx, [rcx+10h]
0x180009688  lea     r8, WPP_497df786d6153c614e507117de9dfe52_Traceguids
0x18000968f  mov     edx, 16h
0x180009694  call    WPP_SF_
0x180009699  mov     rcx, cs:WPP_GLOBAL_Control
0x1800096a0  cmp     rcx, r15
0x1800096a3  jz      short loc_1800096C0
0x1800096a5  test    byte ptr [rcx+1Ch], 4
0x1800096a9  jz      short loc_1800096C0
0x1800096ab  mov     rcx, [rcx+10h]
0x1800096af  lea     r8, WPP_497df786d6153c614e507117de9dfe52_Traceguids
0x1800096b6  mov     edx, 17h
0x1800096bb  call    WPP_SF_
0x1800096c0  mov     r9d, [rbp+arg_28]
0x1800096c4  mov     r8, rsi
0x1800096c7  mov     rsi, [rbp+var_10]
0x1800096cb  mov     qword ptr [rsp+70h+var_40], r12
0x1800096d0  mov     rcx, rsi
0x1800096d3  mov     qword ptr [rsp+70h+var_48], r14
0x1800096d8  mov     qword ptr [rsp+70h+var_50], r14
0x1800096dd  mov     r14d, [rbp+arg_10]
0x1800096e1  mov     edx, r14d
0x1800096e4  call    ?GenerateSIDKey@@YAJQEAEKPEAU_KEK_KEY_INFO@@W4_SID_KEY_BLOB_VER@@PEAPEAEPEAKPEAEK@Z; GenerateSIDKey(uchar * const,ulong,_KEK_KEY_INFO *,_SID_KEY_BLOB_VER,uchar * *,ulong *,uchar *,ulong)
0x1800096e9  mov     ebx, eax
0x1800096eb  test    eax, eax
0x1800096ed  jns     short loc_1800096FA
0x1800096ef  mov     r9d, 8CDh
0x1800096f5  jmp     loc_18000958A
0x1800096fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180009701  cmp     rcx, r15
0x180009704  jz      short loc_180009721
0x180009706  test    byte ptr [rcx+1Ch], 4
0x18000970a  jz      short loc_180009721
0x18000970c  mov     rcx, [rcx+10h]
0x180009710  lea     r8, WPP_497df786d6153c614e507117de9dfe52_Traceguids
0x180009717  mov     edx, 18h
0x18000971c  call    WPP_SF_
0x180009721  mov     rdx, [rbp+TokenHandle]; Token
0x180009725  xor     ecx, ecx; Thread
0x180009727  call    cs:__imp_SetThreadToken
0x18000972d  test    eax, eax
0x18000972f  jnz     short loc_180009765
0x180009731  test    ebx, ebx
0x180009733  js      short loc_180009765
0x180009735  call    cs:__imp_GetLastError
0x18000973b  mov     ebx, eax
0x18000973d  test    eax, eax
0x18000973f  jle     short loc_18000974A
0x180009741  movzx   ebx, ax
0x180009744  or      ebx, 80070000h
0x18000974a  mov     r9d, 8E0h; unsigned int
0x180009750  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180009757  lea     rdx, aHr; "hr"
0x18000975e  mov     ecx, ebx; unsigned int
0x180009760  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180009765  test    rsi, rsi
0x180009768  jz      short loc_1800097AE
0x18000976a  mov     edx, r14d
0x18000976d  mov     rax, rsi
0x180009770  test    r14d, r14d
0x180009773  jz      short loc_180009781
0x180009775  mov     byte ptr [rax], 0
0x180009778  inc     rax
0x18000977b  sub     rdx, 1
0x18000977f  jnz     short loc_180009775
0x180009781  mov     rcx, rsi; lpMem
0x180009784  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180009789  jmp     short loc_1800097AE
0x18000978b  mov     ebx, 80070057h
0x180009790  mov     r9d, 875h; unsigned int
0x180009796  mov     ecx, 80070057h; unsigned int
0x18000979b  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800097a2  lea     rdx, aHr; "hr"
0x1800097a9  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800097ae  mov     edi, 20h ; ' '
0x1800097b3  mov     rcx, [rbp+TokenHandle]; hObject
0x1800097b7  test    rcx, rcx
0x1800097ba  jz      short loc_1800097C2
0x1800097bc  call    cs:__imp_CloseHandle
0x1800097c2  test    ebx, ebx
0x1800097c4  jns     short loc_1800097D4
0x1800097c6  mov     byte ptr [r12], 0
0x1800097cb  inc     r12
0x1800097ce  sub     rdi, 1
0x1800097d2  jnz     short loc_1800097C6
0x1800097d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097db  lea     rax, WPP_GLOBAL_Control
0x1800097e2  cmp     rcx, rax
0x1800097e5  jz      short loc_180009805
0x1800097e7  test    byte ptr [rcx+1Ch], 4
0x1800097eb  jz      short loc_180009805
0x1800097ed  mov     rcx, [rcx+10h]
0x1800097f1  lea     r8, WPP_497df786d6153c614e507117de9dfe52_Traceguids
0x1800097f8  mov     edx, 19h
0x1800097fd  mov     r9d, ebx
0x180009800  call    WPP_SF_D
0x180009805  mov     eax, ebx
0x180009807  mov     rbx, [rsp+70h+arg_8]
0x18000980f  add     rsp, 70h
0x180009813  pop     r15
0x180009815  pop     r14
0x180009817  pop     r13
0x180009819  pop     r12
0x18000981b  pop     rdi
0x18000981c  pop     rsi
0x18000981d  pop     rbp
0x18000981e  retn
```
