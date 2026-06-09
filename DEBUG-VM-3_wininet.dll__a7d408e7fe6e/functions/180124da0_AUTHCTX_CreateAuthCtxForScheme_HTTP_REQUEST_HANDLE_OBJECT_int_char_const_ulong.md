# AUTHCTX::CreateAuthCtxForScheme(HTTP_REQUEST_HANDLE_OBJECT *,int,char const *,ulong)

- ea: `0x180124da0`
- end: `0x180125218`
- name: `?CreateAuthCtxForScheme@AUTHCTX@@SAPEAV1@PEAVHTTP_REQUEST_HANDLE_OBJECT@@HPEBDK@Z`
- size: `1144`
- prototype: `struct AUTHCTX *__fastcall(struct HTTP_REQUEST_HANDLE_OBJECT *, int, struct PWC *, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180120ad8`

## callees

- `0x18003e350`
- `0x1800ce534`
- `0x1800d2e04`
- `0x1800e70f4`
- `0x180124da0`
- `0x180149e88`
- `0x18014b3b4`
- `0x18015766c`
- `0x180158664`
- `0x180159aec`
- `0x18015a920`
- `0x1801b5bfc`
- `0x1801e3c24`
- `0x1801ec32c`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801250a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801250a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180124de2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180124de2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801250c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801250c8`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180124e16`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180124e53`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180124ead`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180124efa`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180124f65`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180124e16`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180124e53`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180124ead`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180124efa`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180124f65`

## pseudocode

```c
struct AUTHCTX *__fastcall AUTHCTX::CreateAuthCtxForScheme(
        struct HTTP_REQUEST_HANDLE_OBJECT *a1,
        int a2,
        const CHAR *a3,
        unsigned int a4)
{
  PASSPORT_CTX *v8; // rbx
  void *v9; // r14
  unsigned int v10; // r12d
  int v11; // eax
  int v12; // eax
  const CHAR *v13; // r13
  BOOL v14; // r15d
  int v15; // eax
  int v16; // ecx
  int v17; // eax
  AUTHCTX::SPMData *i; // rdi
  SECURITY_CACHE_LIST_ENTRY *v19; // rcx
  __int64 v20; // rdx
  PLUG_CTX *v21; // rax
  PLUG_CTX *v22; // rsi
  DIGEST_CTX *v23; // rax
  PASSPORT_CTX *v24; // rax
  PASSPORT_CTX *v25; // rbx
  __int64 ThreadInfo; // rax
  bool v28; // zf
  PLUG_CTX *v29; // rax
  PLUG_CTX *v30; // r15
  DIGEST_CTX *v31; // rax
  DIGEST_CTX *v32; // rbx
  PASSPORT_CTX *v33; // rax
  struct PWC *lpString2; // [rsp+20h] [rbp-78h]
  unsigned int v35; // [rsp+40h] [rbp-58h] BYREF
  BOOL v36; // [rsp+44h] [rbp-54h]
  void *v37; // [rsp+48h] [rbp-50h] BYREF

  if ( (BYTE1(xmmword_180266B60) & 4) != 0 )
    WPP_SF_qlsdD((_DWORD)a1, a2, (_DWORD)a3, (_DWORD)a1, a2, (__int64)a3, a4);
  EnterCriticalSection(&g_csAuth);
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v37 = 0;
  v35 = 0;
  v11 = CompareStringA(0x7Fu, 1u, "Nego2", -1, a3, -1);
  v28 = v11 == 2;
  v12 = v11 - 2;
  v13 = "Negotiate";
  if ( !v28 )
    v13 = a3;
  v14 = v12 == 0;
  v36 = v14;
  v15 = CompareStringA(0x7Fu, 1u, "Passport1.4", -1, v13, -1);
  v16 = *((_DWORD *)a1 + 1224);
  if ( v15 == 2 )
  {
    if ( v16 == 401 || AUTHCTX::UpgradeToNegotiate2Supported(a1, a4) )
      goto LABEL_45;
  }
  else if ( v16 == 302 )
  {
    goto LABEL_45;
  }
  if ( (CompareStringA(0x7Fu, 1u, "Basic", -1, v13, -1) != 2
     || (*((_DWORD *)a1 + 317) & 0x800000) != 0
     || !GlobalDisableBasicOverClearChannel && (*((_BYTE *)a1 + 1000) & 4) == 0)
    && (CompareStringA(0x7Fu, 1u, "Negotiate", -1, v13, -1) != 2
     || (*((_DWORD *)a1 + 250) & 2) != 0
     || (*((_DWORD *)a1 + 250) & 1) == 0 && GlobalEnableNegotiate) )
  {
    v17 = AUTHCTX::g_eState;
    if ( !AUTHCTX::g_eState )
    {
      AUTHCTX::Enumerate();
      v17 = AUTHCTX::g_eState;
    }
    if ( v17 == 1 )
    {
      for ( i = AUTHCTX::g_pSPMList; ; i = (AUTHCTX::SPMData *)*((_QWORD *)i + 4) )
      {
        if ( !i )
          goto LABEL_45;
        if ( CompareStringA(0x7Fu, 1u, *(PCNZCH *)i, -1, v13, -1) == 2 )
          break;
      }
      if ( *((_DWORD *)i + 6) )
      {
        if ( *((_DWORD *)i + 6) != 5 )
        {
          v19 = (SECURITY_CACHE_LIST_ENTRY *)*((_QWORD *)a1 + 666);
          if ( v19 )
          {
            SECURITY_CACHE_LIST_ENTRY::GetChannelBindingToken(v19, &v37, &v35);
            v9 = v37;
            v10 = v35;
          }
        }
      }
      v20 = *((unsigned int *)i + 6);
      if ( !(_DWORD)v20 )
      {
        if ( a2 && (GlobalDisableProxyAuthenticationSchemes & 1) != 0 )
          goto LABEL_45;
        v33 = (PASSPORT_CTX *)operator new(0x58u);
        v8 = v33;
        if ( v33 )
        {
          memset_0(v33, 0, 0x58u);
          AUTHCTX::AUTHCTX(v8, a1, a2, i, 0);
          *(_QWORD *)v8 = &BASIC_CTX::`vftable';
          goto LABEL_45;
        }
        goto LABEL_44;
      }
      if ( (_DWORD)v20 == 1 )
      {
        if ( a2 && (GlobalDisableProxyAuthenticationSchemes & 2) != 0 )
          goto LABEL_45;
        v31 = (DIGEST_CTX *)operator new(0x80u);
        v32 = v31;
        if ( v31 )
        {
          memset_0(v31, 0, 0x80u);
          v23 = DIGEST_CTX::DIGEST_CTX(v32, a1, a2, i, 0, v9, v10);
          goto LABEL_38;
        }
        goto LABEL_44;
      }
      if ( (_DWORD)v20 == 2 )
      {
        if ( !a2 )
          goto LABEL_55;
        v28 = (GlobalDisableProxyAuthenticationSchemes & 4) == 0;
      }
      else
      {
        if ( (_DWORD)v20 != 4 )
        {
          if ( (_DWORD)v20 == 5 )
          {
            if ( a2 )
              goto LABEL_45;
            v24 = (PASSPORT_CTX *)operator new(0x3B8u);
            v25 = v24;
            if ( v24 )
            {
              memset_0(v24, 0, 0x3B8u);
              v8 = PASSPORT_CTX::PASSPORT_CTX(v25, a1, 0, i, lpString2);
              if ( !v8 )
                goto LABEL_45;
              ThreadInfo = InternetCreateThreadInfo(0);
              *((_QWORD *)v8 + 13) = ThreadInfo;
              if ( ThreadInfo )
                goto LABEL_45;
              (**(void (__fastcall ***)(PASSPORT_CTX *, __int64))v8)(v8, 1);
            }
          }
          else
          {
            MicrosoftTelemetryAssertTriggeredArgs((unsigned int)(v20 - 4), v20, (unsigned int)v20);
            if ( a2 )
              goto LABEL_45;
            v21 = (PLUG_CTX *)operator new(0x90u);
            v22 = v21;
            if ( v21 )
            {
              memset_0(v21, 0, 0x90u);
              v23 = PLUG_CTX::PLUG_CTX(v22, a1, 0, i, 0, v9, v10, v14);
LABEL_38:
              v8 = v23;
              goto LABEL_45;
            }
          }
          goto LABEL_44;
        }
        if ( !a2 )
        {
LABEL_55:
          v29 = (PLUG_CTX *)operator new(0x90u);
          v30 = v29;
          if ( v29 )
          {
            memset_0(v29, 0, 0x90u);
            v23 = PLUG_CTX::PLUG_CTX(v30, a1, a2, i, 0, v9, v10, v36);
            goto LABEL_38;
          }
LABEL_44:
          v8 = 0;
          goto LABEL_45;
        }
        v28 = (GlobalDisableProxyAuthenticationSchemes & 0x10) == 0;
      }
      if ( !v28 )
        goto LABEL_45;
      goto LABEL_55;
    }
  }
LABEL_45:
  LeaveCriticalSection(&g_csAuth);
  if ( v8 )
    v9 = 0;
  if ( v9 )
    HeapFree(g_hWxProcessHeap, 0, v9);
  if ( (BYTE1(xmmword_180266B60) & 4) != 0 )
    WPP_SF_q(1034, 41, &WPP_238eb0d6eeb4389ab911b3c40e414073_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180124da0  push    rbx
0x180124da2  push    rbp
0x180124da3  push    rsi
0x180124da4  push    rdi
0x180124da5  push    r12
0x180124da7  push    r13
0x180124da9  push    r14
0x180124dab  push    r15
0x180124dad  sub     rsp, 58h
0x180124db1  mov     edi, r9d
0x180124db4  mov     r15, r8
0x180124db7  mov     esi, edx
0x180124db9  mov     rbp, rcx
0x180124dbc  test    byte ptr cs:xmmword_180266B60+1, 4
0x180124dc3  jz      short loc_180124DDB
0x180124dc5  mov     [rsp+98h+var_68], r9d
0x180124dca  mov     r9, rcx
0x180124dcd  mov     qword ptr [rsp+98h+cchCount2], r8
0x180124dd2  mov     dword ptr [rsp+98h+lpString2], edx
0x180124dd6  call    WPP_SF_qlsdD
0x180124ddb  lea     rcx, ?g_csAuth@@3VWxCriticalSection@@A; lpCriticalSection
0x180124de2  call    cs:__imp_EnterCriticalSection
0x180124de8  or      eax, 0FFFFFFFFh
0x180124deb  lea     r8, aNego2; "Nego2"
0x180124df2  xor     ebx, ebx
0x180124df4  mov     [rsp+98h+cchCount2], eax; cchCount2
0x180124df8  xor     r14d, r14d
0x180124dfb  mov     [rsp+98h+lpString2], r15; lpString2
0x180124e00  xor     r12d, r12d
0x180124e03  mov     [rsp+98h+var_50], r14
0x180124e08  mov     r9d, eax; cchCount1
0x180124e0b  mov     [rsp+98h+var_58], r12d
0x180124e10  lea     edx, [rbx+1]; dwCmpFlags
0x180124e13  lea     ecx, [rbx+7Fh]; Locale
0x180124e16  call    cs:__imp_CompareStringA
0x180124e1c  add     eax, 0FFFFFFFEh
0x180124e1f  lea     r13, aNegotiate_1; "Negotiate"
0x180124e26  lea     r8, aPassport14; "Passport1.4"
0x180124e2d  cmovnz  r13, r15
0x180124e31  lea     edx, [rbx+1]; dwCmpFlags
0x180124e34  xor     r15d, r15d
0x180124e37  lea     ecx, [rbx+7Fh]; Locale
0x180124e3a  test    eax, eax
0x180124e3c  setz    r15b
0x180124e40  or      r9d, 0FFFFFFFFh; cchCount1
0x180124e44  mov     [rsp+98h+cchCount2], r9d; cchCount2
0x180124e49  mov     [rsp+98h+lpString2], r13; lpString2
0x180124e4e  mov     [rsp+98h+var_54], r15d
0x180124e53  call    cs:__imp_CompareStringA
0x180124e59  mov     ecx, [rbp+1320h]
0x180124e5f  add     eax, 0FFFFFFFEh
0x180124e62  jnz     short loc_180124E83
0x180124e64  cmp     ecx, 191h
0x180124e6a  jz      loc_1801250A1
0x180124e70  mov     edx, edi; unsigned int
0x180124e72  mov     rcx, rbp; struct HTTP_REQUEST_HANDLE_OBJECT *
0x180124e75  call    ?UpgradeToNegotiate2Supported@AUTHCTX@@CAHPEAVHTTP_REQUEST_HANDLE_OBJECT@@K@Z; AUTHCTX::UpgradeToNegotiate2Supported(HTTP_REQUEST_HANDLE_OBJECT *,ulong)
0x180124e7a  test    eax, eax
0x180124e7c  jz      short loc_180124E8F
0x180124e7e  jmp     loc_1801250A1
0x180124e83  cmp     ecx, 12Eh
0x180124e89  jz      loc_1801250A1
0x180124e8f  or      eax, 0FFFFFFFFh
0x180124e92  lea     r8, aBasic_0; "Basic"
0x180124e99  mov     [rsp+98h+cchCount2], eax; cchCount2
0x180124e9d  mov     r9d, eax; cchCount1
0x180124ea0  mov     [rsp+98h+lpString2], r13; lpString2
0x180124ea5  lea     edi, [rax+2]
0x180124ea8  mov     edx, edi; dwCmpFlags
0x180124eaa  lea     ecx, [rdi+7Eh]; Locale
0x180124ead  call    cs:__imp_CompareStringA
0x180124eb3  cmp     eax, 2
0x180124eb6  jnz     short loc_180124EDD
0x180124eb8  test    dword ptr [rbp+4F4h], 800000h
0x180124ec2  jnz     short loc_180124EDD
0x180124ec4  cmp     cs:?GlobalDisableBasicOverClearChannel@@3HA, ebx; int GlobalDisableBasicOverClearChannel
0x180124eca  jnz     loc_1801250A1
0x180124ed0  test    byte ptr [rbp+3E8h], 4
0x180124ed7  jnz     loc_1801250A1
0x180124edd  or      eax, 0FFFFFFFFh
0x180124ee0  lea     r8, aNegotiate_1; "Negotiate"
0x180124ee7  mov     [rsp+98h+cchCount2], eax; cchCount2
0x180124eeb  mov     r9d, eax; cchCount1
0x180124eee  mov     edx, edi; dwCmpFlags
0x180124ef0  mov     [rsp+98h+lpString2], r13; lpString2
0x180124ef5  mov     ecx, 7Fh; Locale
0x180124efa  call    cs:__imp_CompareStringA
0x180124f00  cmp     eax, 2
0x180124f03  jnz     short loc_180124F27
0x180124f05  mov     eax, [rbp+3E8h]
0x180124f0b  mov     ecx, eax
0x180124f0d  and     ecx, edi
0x180124f0f  test    al, 2
0x180124f11  jnz     short loc_180124F27
0x180124f13  test    ecx, ecx
0x180124f15  jnz     loc_1801250A1
0x180124f1b  cmp     cs:?GlobalEnableNegotiate@@3HA, ebx; int GlobalEnableNegotiate
0x180124f21  jz      loc_1801250A1
0x180124f27  mov     eax, cs:?g_eState@AUTHCTX@@2W4SPMState@1@A; AUTHCTX::SPMState AUTHCTX::g_eState
0x180124f2d  test    eax, eax
0x180124f2f  jnz     short loc_180124F3C
0x180124f31  call    ?Enumerate@AUTHCTX@@SAXXZ; AUTHCTX::Enumerate(void)
0x180124f36  mov     eax, cs:?g_eState@AUTHCTX@@2W4SPMState@1@A; AUTHCTX::SPMState AUTHCTX::g_eState
0x180124f3c  cmp     eax, edi
0x180124f3e  jnz     loc_1801250A1
0x180124f44  mov     rdi, cs:?g_pSPMList@AUTHCTX@@2PEAVSPMData@1@EA; AUTHCTX::SPMData * AUTHCTX::g_pSPMList
0x180124f4b  jmp     short loc_180124F74
0x180124f4d  mov     r8, [rdi]; lpString1
0x180124f50  or      eax, 0FFFFFFFFh
0x180124f53  mov     [rsp+98h+cchCount2], eax; cchCount2
0x180124f57  mov     r9d, eax; cchCount1
0x180124f5a  mov     [rsp+98h+lpString2], r13; struct PWC *
0x180124f5f  lea     edx, [rax+2]; dwCmpFlags
0x180124f62  lea     ecx, [rdx+7Eh]; Locale
0x180124f65  call    cs:__imp_CompareStringA
0x180124f6b  cmp     eax, 2
0x180124f6e  jz      short loc_180124F7E
0x180124f70  mov     rdi, [rdi+20h]
0x180124f74  test    rdi, rdi
0x180124f77  jnz     short loc_180124F4D
0x180124f79  jmp     loc_1801250A1
0x180124f7e  cmp     [rdi+18h], ebx
0x180124f81  jz      short loc_180124FAE
0x180124f83  cmp     dword ptr [rdi+18h], 5
0x180124f87  jz      short loc_180124FAE
0x180124f89  mov     rcx, [rbp+14D0h]; this
0x180124f90  test    rcx, rcx
0x180124f93  jz      short loc_180124FAE
0x180124f95  lea     r8, [rsp+98h+var_58]; unsigned int *
0x180124f9a  lea     rdx, [rsp+98h+var_50]; void **
0x180124f9f  call    ?GetChannelBindingToken@SECURITY_CACHE_LIST_ENTRY@@QEAAXPEAPEAXPEAK@Z; SECURITY_CACHE_LIST_ENTRY::GetChannelBindingToken(void * *,ulong *)
0x180124fa4  mov     r14, [rsp+98h+var_50]
0x180124fa9  mov     r12d, [rsp+98h+var_58]
0x180124fae  mov     edx, [rdi+18h]
0x180124fb1  mov     ecx, edx
0x180124fb3  test    edx, edx
0x180124fb5  jz      loc_1801251B7
0x180124fbb  sub     ecx, 1
0x180124fbe  jz      loc_180125156
0x180124fc4  sub     ecx, 1
0x180124fc7  jz      loc_180125149
0x180124fcd  sub     ecx, 2
0x180124fd0  jz      loc_180125104
0x180124fd6  cmp     ecx, 1
0x180124fd9  jz      short loc_18012503E
0x180124fdb  mov     r8d, edx
0x180124fde  call    MicrosoftTelemetryAssertTriggeredArgs
0x180124fe3  test    esi, esi
0x180124fe5  jnz     loc_1801250A1
0x180124feb  mov     ebx, 90h
0x180124ff0  mov     ecx, ebx; unsigned __int64
0x180124ff2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180124ff7  mov     rsi, rax
0x180124ffa  test    rax, rax
0x180124ffd  jz      loc_18012509F
0x180125003  mov     r8d, ebx; Size
0x180125006  xor     edx, edx; Val
0x180125008  mov     rcx, rax; void *
0x18012500b  call    memset_0
0x180125010  xor     r8d, r8d; int
0x180125013  mov     [rsp+98h+var_60], r15d; int
0x180125018  mov     rcx, rsi; this
0x18012501b  mov     [rsp+98h+var_68], r12d; unsigned int
0x180125020  mov     rdx, rbp; struct HTTP_REQUEST_HANDLE_OBJECT *
0x180125023  mov     qword ptr [rsp+98h+cchCount2], r14; void *
0x180125028  mov     r9, rdi; struct AUTHCTX::SPMData *
0x18012502b  mov     [rsp+98h+lpString2], 0; struct PWC *
0x180125034  call    ??0PLUG_CTX@@QEAA@PEAVHTTP_REQUEST_HANDLE_OBJECT@@HPEAVSPMData@AUTHCTX@@PEAVPWC@@PEAXKH@Z; PLUG_CTX::PLUG_CTX(HTTP_REQUEST_HANDLE_OBJECT *,int,AUTHCTX::SPMData *,PWC *,void *,ulong,int)
0x180125039  mov     rbx, rax
0x18012503c  jmp     short loc_1801250A1
0x18012503e  test    esi, esi
0x180125040  jnz     short loc_1801250A1
0x180125042  mov     esi, 3B8h
0x180125047  mov     ecx, esi; unsigned __int64
0x180125049  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012504e  mov     rbx, rax
0x180125051  test    rax, rax
0x180125054  jz      short loc_18012509F
0x180125056  mov     r8d, esi; Size
0x180125059  xor     edx, edx; Val
0x18012505b  mov     rcx, rax; void *
0x18012505e  call    memset_0
0x180125063  mov     r9, rdi; struct AUTHCTX::SPMData *
0x180125066  xor     r8d, r8d; int
0x180125069  mov     rdx, rbp; struct HTTP_REQUEST_HANDLE_OBJECT *
0x18012506c  mov     rcx, rbx; this
0x18012506f  call    ??0PASSPORT_CTX@@QEAA@PEAVHTTP_REQUEST_HANDLE_OBJECT@@HPEAVSPMData@AUTHCTX@@PEAVPWC@@@Z; PASSPORT_CTX::PASSPORT_CTX(HTTP_REQUEST_HANDLE_OBJECT *,int,AUTHCTX::SPMData *,PWC *)
0x180125074  mov     rbx, rax
0x180125077  test    rax, rax
0x18012507a  jz      short loc_1801250A1
0x18012507c  xor     ecx, ecx
0x18012507e  call    InternetCreateThreadInfo
0x180125083  mov     [rbx+68h], rax
0x180125087  test    rax, rax
0x18012508a  jnz     short loc_1801250A1
0x18012508c  mov     rax, [rbx]
0x18012508f  mov     edx, 1
0x180125094  mov     rcx, rbx
0x180125097  mov     rax, [rax]
0x18012509a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012509f  xor     ebx, ebx
0x1801250a1  lea     rcx, ?g_csAuth@@3VWxCriticalSection@@A; lpCriticalSection
0x1801250a8  call    cs:__imp_LeaveCriticalSection
0x1801250ae  xor     eax, eax
0x1801250b0  test    rbx, rbx
0x1801250b3  cmovnz  r14, rax
0x1801250b7  test    r14, r14
0x1801250ba  jz      short loc_1801250CE
0x1801250bc  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1801250c3  mov     r8, r14; lpMem
0x1801250c6  xor     edx, edx; dwFlags
0x1801250c8  call    cs:__imp_HeapFree
0x1801250ce  test    byte ptr cs:xmmword_180266B60+1, 4
0x1801250d5  jz      short loc_1801250F0
0x1801250d7  mov     edx, 29h ; ')'
0x1801250dc  lea     r8, WPP_238eb0d6eeb4389ab911b3c40e414073_Traceguids
0x1801250e3  mov     ecx, 40Ah
0x1801250e8  mov     r9, rbx
0x1801250eb  call    WPP_SF_q
0x1801250f0  mov     rax, rbx
0x1801250f3  add     rsp, 58h
0x1801250f7  pop     r15
0x1801250f9  pop     r14
0x1801250fb  pop     r13
0x1801250fd  pop     r12
0x1801250ff  pop     rdi
0x180125100  pop     rsi
0x180125101  pop     rbp
0x180125102  pop     rbx
0x180125103  retn
0x180125104  test    esi, esi
0x180125106  jz      short loc_180125111
0x180125108  test    byte ptr cs:GlobalDisableProxyAuthenticationSchemes, 10h
0x18012510f  jnz     short loc_1801250A1
0x180125111  mov     ebx, 90h
0x180125116  mov     ecx, ebx; unsigned __int64
0x180125118  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012511d  mov     r15, rax
0x180125120  test    rax, rax
0x180125123  jz      loc_18012509F
0x180125129  mov     r8d, ebx; Size
0x18012512c  xor     edx, edx; Val
0x18012512e  mov     rcx, rax; void *
0x180125131  call    memset_0
0x180125136  mov     eax, [rsp+98h+var_54]
0x18012513a  mov     r8d, esi
0x18012513d  mov     [rsp+98h+var_60], eax
0x180125141  mov     rcx, r15
0x180125144  jmp     loc_18012501B
0x180125149  test    esi, esi
0x18012514b  jz      short loc_180125111
0x18012514d  test    byte ptr cs:GlobalDisableProxyAuthenticationSchemes, 4
0x180125154  jmp     short loc_18012510F
0x180125156  test    esi, esi
0x180125158  jz      short loc_180125167
0x18012515a  test    byte ptr cs:GlobalDisableProxyAuthenticationSchemes, 2
0x180125161  jnz     loc_1801250A1
0x180125167  mov     r15d, 80h
0x18012516d  mov     ecx, r15d; unsigned __int64
0x180125170  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180125175  mov     rbx, rax
0x180125178  test    rax, rax
0x18012517b  jz      loc_18012509F
0x180125181  mov     r8d, r15d; Size
0x180125184  xor     edx, edx; Val
0x180125186  mov     rcx, rax; void *
0x180125189  call    memset_0
0x18012518e  mov     [rsp+98h+var_68], r12d; unsigned int
0x180125193  mov     r9, rdi; struct AUTHCTX::SPMData *
0x180125196  mov     qword ptr [rsp+98h+cchCount2], r14; void *
0x18012519b  mov     r8d, esi; int
0x18012519e  mov     rdx, rbp; struct HTTP_REQUEST_HANDLE_OBJECT *
0x1801251a1  mov     [rsp+98h+lpString2], 0; struct PWC *
0x1801251aa  mov     rcx, rbx; this
0x1801251ad  call    ??0DIGEST_CTX@@QEAA@PEAVHTTP_REQUEST_HANDLE_OBJECT@@HPEAVSPMData@AUTHCTX@@PEAVPWC@@PEAXK@Z; DIGEST_CTX::DIGEST_CTX(HTTP_REQUEST_HANDLE_OBJECT *,int,AUTHCTX::SPMData *,PWC *,void *,ulong)
0x1801251b2  jmp     loc_180125039
0x1801251b7  test    esi, esi
0x1801251b9  jz      short loc_1801251C8
0x1801251bb  test    byte ptr cs:GlobalDisableProxyAuthenticationSchemes, 1
0x1801251c2  jnz     loc_1801250A1
0x1801251c8  mov     r15d, 58h ; 'X'
0x1801251ce  mov     ecx, r15d; unsigned __int64
0x1801251d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801251d6  mov     rbx, rax
0x1801251d9  test    rax, rax
0x1801251dc  jz      loc_18012509F
0x1801251e2  mov     r8d, r15d; Size
0x1801251e5  xor     edx, edx; Val
0x1801251e7  mov     rcx, rax; void *
0x1801251ea  call    memset_0
0x1801251ef  mov     r9, rdi; struct AUTHCTX::SPMData *
0x1801251f2  mov     [rsp+98h+lpString2], 0; struct PWC *
0x1801251fb  mov     r8d, esi; int
0x1801251fe  mov     rdx, rbp; struct HTTP_REQUEST_HANDLE_OBJECT *
0x180125201  mov     rcx, rbx; this
0x180125204  call    ??0AUTHCTX@@QEAA@PEAVHTTP_REQUEST_HANDLE_OBJECT@@HPEAVSPMData@0@PEAVPWC@@@Z; AUTHCTX::AUTHCTX(HTTP_REQUEST_HANDLE_OBJECT *,int,AUTHCTX::SPMData *,PWC *)
0x180125209  lea     rax, ??_7BASIC_CTX@@6B@; const BASIC_CTX::`vftable'
0x180125210  mov     [rbx], rax
0x180125213  jmp     loc_1801250A1
```
