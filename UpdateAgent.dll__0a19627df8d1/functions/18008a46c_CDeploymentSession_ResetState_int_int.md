# CDeploymentSession::ResetState(int,int)

- ea: `0x18008a46c`
- end: `0x18008ad61`
- name: `?ResetState@CDeploymentSession@@QEAAJHH@Z`
- size: `2293`
- prototype: `__int64 __fastcall(CDeploymentSession *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003a680`
- `0x18006b348`

## callees

- `0x1800059d0`
- `0x180039f90`
- `0x180077664`
- `0x180078b9c`
- `0x180079e18`
- `0x18008a46c`
- `0x1802b1010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18008a52e`
- `OLEAUT32!__imp_SysFreeString` at `0x18008a549`
- `OLEAUT32!__imp_SysFreeString` at `0x18008a5f5`
- `OLEAUT32!__imp_SysFreeString` at `0x18008a84b`
- `OLEAUT32!__imp_SysFreeString` at `0x18008aa8d`
- `OLEAUT32!__imp_SysFreeString` at `0x18008aaa8`
- `OLEAUT32!__imp_SysFreeString` at `0x18008ad0a`
- `OLEAUT32!__imp_SysFreeString` at `0x18008ad25`
- `OLEAUT32!__imp_SysFreeString` at `0x18008a52e`
- `OLEAUT32!__imp_SysFreeString` at `0x18008a549`
- `OLEAUT32!__imp_SysFreeString` at `0x18008a5f5`
- `OLEAUT32!__imp_SysFreeString` at `0x18008a84b`
- `OLEAUT32!__imp_SysFreeString` at `0x18008aa8d`
- `OLEAUT32!__imp_SysFreeString` at `0x18008aaa8`
- `OLEAUT32!__imp_SysFreeString` at `0x18008ad0a`
- `OLEAUT32!__imp_SysFreeString` at `0x18008ad25`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008a752`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008a994`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008abd7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008a752`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008a994`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008abd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008a655`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008a68c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008a8ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008a8e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008ab08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008ab3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008aca9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008acd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008a655`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008a68c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008a8ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008a8e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008ab08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008ab3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008aca9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008acd7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a66a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a6a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a8c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a8f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008ab1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008ab54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008acbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008acec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a66a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a6a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a8c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a8f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008ab1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008ab54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008acbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008acec`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDeploymentSession::ResetState(CDeploymentSession *this, int a2, int a3)
{
  __int64 *v5; // rcx
  __int64 v6; // rcx
  unsigned int v7; // edi
  __int64 updated; // rcx
  __int64 v9; // rax
  __int64 result; // rax
  const char *v11; // r9
  int v12; // eax
  unsigned int v13; // r15d
  int v14; // eax
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  int v18; // eax
  unsigned int v19; // r15d
  int v20; // eax
  int v21; // eax
  __int64 v22; // rcx
  int v23; // eax
  int v24; // eax
  unsigned int v25; // r15d
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  __int64 v30; // rcx
  PCNZWCH lpString2; // [rsp+20h] [rbp-78h]
  int cchCount2; // [rsp+28h] [rbp-70h]
  int cchCount2a; // [rsp+28h] [rbp-70h]
  BSTR v34; // [rsp+48h] [rbp-50h] BYREF
  unsigned int v35; // [rsp+50h] [rbp-48h] BYREF
  int v36; // [rsp+54h] [rbp-44h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-40h] BYREF
  __int64 v38; // [rsp+60h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  try
  {
    v34 = 0;
    bstrString = 0;
    v38 = 0;
    v35 = 0;
    v36 = 0;
    v5 = (__int64 *)*((_QWORD *)this + 76);
    if ( v5 )
    {
      v9 = *v5;
      if ( !a2 )
        return (*(unsigned int (**)(void))(v9 + 272))();
      v12 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v9 + 176))(v5, &v35);
      v7 = v12;
      if ( v12 >= 0 )
      {
        v13 = v35;
        while ( v13 )
        {
          --v13;
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          if ( v34 )
          {
            SysFreeString(v34);
            v34 = 0;
          }
          v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, BSTR *, int *))(**((_QWORD **)this + 76) + 168LL))(
                  *((_QWORD *)this + 76),
                  v13,
                  &v34,
                  &v36);
          v7 = v14;
          if ( v14 < 0 )
          {
            v6 = *((_QWORD *)this + 75);
            if ( !v6 )
              goto LABEL_66;
            cchCount2 = v14;
            LODWORD(lpString2) = 5573;
            goto LABEL_5;
          }
          v15 = CMiscHelpersT<CEmptyType>::ParseFileName(v34, 0);
          v7 = v15;
          if ( v15 < 0 )
          {
            v16 = *((_QWORD *)this + 75);
            if ( v16 )
            {
              LODWORD(lpString2) = 5577;
              updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                        v16,
                                        4,
                                        L"%s(%d): Result = 0x%X",
                                        L"CDeploymentSession::ResetState",
                                        lpString2,
                                        v15);
LABEL_22:
              if ( (int)updated < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated);
            }
            else
            {
LABEL_20:
              updated = 0;
            }
            goto LABEL_70;
          }
          v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 76) + 96LL))(
                  *((_QWORD *)this + 76),
                  v13);
          v7 = v17;
          if ( v17 < 0 )
          {
            v6 = *((_QWORD *)this + 75);
            if ( !v6 )
              goto LABEL_66;
            cchCount2 = v17;
            LODWORD(lpString2) = 5582;
            goto LABEL_5;
          }
        }
        v18 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 76) + 208LL))(
                *((_QWORD *)this + 76),
                &v35);
        v7 = v18;
        if ( v18 >= 0 )
        {
          v19 = v35;
          while ( v19 )
          {
            --v19;
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            if ( v34 )
            {
              SysFreeString(v34);
              v34 = 0;
            }
            v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, BSTR *, __int64 *))(**((_QWORD **)this + 76) + 200LL))(
                    *((_QWORD *)this + 76),
                    v19,
                    &v34,
                    &v38);
            v7 = v20;
            if ( v20 < 0 )
            {
              v6 = *((_QWORD *)this + 75);
              if ( !v6 )
                goto LABEL_66;
              cchCount2 = v20;
              LODWORD(lpString2) = 5593;
              goto LABEL_5;
            }
            v21 = CMiscHelpersT<CEmptyType>::ParseFileName(v34, 0);
            v7 = v21;
            if ( v21 < 0 )
            {
              v22 = *((_QWORD *)this + 75);
              if ( !v22 )
                goto LABEL_20;
              cchCount2a = v21;
              LODWORD(lpString2) = 5597;
LABEL_41:
              updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                        v22,
                                        4,
                                        L"%s(%d): Result = 0x%X",
                                        L"CDeploymentSession::ResetState",
                                        lpString2,
                                        cchCount2a);
              goto LABEL_22;
            }
            v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 76) + 112LL))(
                    *((_QWORD *)this + 76),
                    v19);
            v7 = v23;
            if ( v23 < 0 )
            {
              v6 = *((_QWORD *)this + 75);
              if ( !v6 )
                goto LABEL_66;
              cchCount2 = v23;
              LODWORD(lpString2) = 5602;
              goto LABEL_5;
            }
          }
          v24 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 76) + 224LL))(
                  *((_QWORD *)this + 76),
                  &v35);
          v7 = v24;
          if ( v24 >= 0 )
          {
            v25 = v35;
            while ( v25 )
            {
              --v25;
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              if ( v34 )
              {
                SysFreeString(v34);
                v34 = 0;
              }
              if ( bstrString )
              {
                SysFreeString(bstrString);
                bstrString = 0;
              }
              v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, BSTR *, BSTR *))(**((_QWORD **)this + 76) + 216LL))(
                      *((_QWORD *)this + 76),
                      v25,
                      &v34,
                      &bstrString);
              v7 = v26;
              if ( v26 < 0 )
              {
                v6 = *((_QWORD *)this + 75);
                if ( !v6 )
                  goto LABEL_66;
                cchCount2 = v26;
                LODWORD(lpString2) = 5614;
                goto LABEL_5;
              }
              v27 = CMiscHelpersT<CEmptyType>::ParseFileName(v34, 0);
              v7 = v27;
              if ( v27 < 0 )
              {
                v22 = *((_QWORD *)this + 75);
                if ( !v22 )
                  goto LABEL_20;
                cchCount2a = v27;
                LODWORD(lpString2) = 5618;
                goto LABEL_41;
              }
              v28 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 76) + 128LL))(
                      *((_QWORD *)this + 76),
                      v25);
              v7 = v28;
              if ( v28 < 0 )
              {
                v6 = *((_QWORD *)this + 75);
                if ( !v6 )
                  goto LABEL_66;
                cchCount2 = v28;
                LODWORD(lpString2) = 5623;
                goto LABEL_5;
              }
            }
            if ( !a3 )
              goto LABEL_71;
            v29 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 76) + 280LL))(
                    *((_QWORD *)this + 76),
                    1);
            v7 = v29;
            if ( v29 >= 0 )
              goto LABEL_71;
            v30 = *((_QWORD *)this + 75);
            if ( !v30 )
              goto LABEL_66;
            LODWORD(lpString2) = 5629;
            updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                      v30,
                                      4,
                                      L"%s(%d): Result = 0x%X",
                                      L"CDeploymentSession::ResetState",
                                      lpString2,
                                      v29);
            goto LABEL_68;
          }
          v6 = *((_QWORD *)this + 75);
          if ( !v6 )
            goto LABEL_66;
          cchCount2 = v24;
          LODWORD(lpString2) = 5606;
        }
        else
        {
          v6 = *((_QWORD *)this + 75);
          if ( !v6 )
            goto LABEL_66;
          cchCount2 = v18;
          LODWORD(lpString2) = 5586;
        }
        goto LABEL_5;
      }
      v6 = *((_QWORD *)this + 75);
      if ( v6 )
      {
        cchCount2 = v12;
        LODWORD(lpString2) = 5566;
LABEL_5:
        updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                  v6,
                                  4,
                                  L"%s(%d): Result = 0x%X",
                                  L"CDeploymentSession::ResetState",
                                  lpString2,
                                  cchCount2);
LABEL_68:
        if ( (int)updated < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated);
        goto LABEL_70;
      }
    }
    else
    {
      v6 = *((_QWORD *)this + 75);
      v7 = -2147483638;
      if ( v6 )
      {
        cchCount2 = -2147483638;
        LODWORD(lpString2) = 5559;
        goto LABEL_5;
      }
    }
LABEL_66:
    updated = 0;
LABEL_70:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(updated);
LABEL_71:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v34 )
      SysFreeString(v34);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1602,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x18008a46c  mov     r11, rsp
0x18008a46f  push    rdi
0x18008a470  push    r12
0x18008a472  push    r13
0x18008a474  push    r14
0x18008a476  push    r15
0x18008a478  sub     rsp, 70h
0x18008a47c  mov     qword ptr [r11-58h], 0FFFFFFFFFFFFFFFEh
0x18008a484  mov     [r11+10h], rbx
0x18008a488  mov     [r11+18h], rsi
0x18008a48c  mov     rax, cs:__security_cookie
0x18008a493  xor     rax, rsp
0x18008a496  mov     [rsp+98h+var_30], rax
0x18008a49b  mov     r12d, r8d
0x18008a49e  mov     rsi, rcx
0x18008a4a1  xor     r13d, r13d
0x18008a4a4  mov     [r11-50h], r13
0x18008a4a8  mov     [r11-40h], r13
0x18008a4ac  mov     r14d, r13d
0x18008a4af  mov     [r11-68h], r13
0x18008a4b3  mov     [r11-60h], r13
0x18008a4b7  mov     [r11-38h], r13
0x18008a4bb  mov     [r11-48h], r13d
0x18008a4bf  mov     [r11-44h], r13d
0x18008a4c3  mov     rcx, [rcx+260h]
0x18008a4ca  test    rcx, rcx
0x18008a4cd  jnz     short loc_18008A50F
0x18008a4cf  mov     rcx, [rsi+258h]
0x18008a4d6  mov     edi, 8000000Ah
0x18008a4db  test    rcx, rcx
0x18008a4de  jz      loc_18008AC5E
0x18008a4e4  mov     [rsp+98h+cchCount2], edi
0x18008a4e8  mov     dword ptr [rsp+98h+lpString2], 15B7h
0x18008a4f0  lea     r9, aCdeploymentses_14; "CDeploymentSession::ResetState"
0x18008a4f7  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18008a4fe  mov     edx, 4
0x18008a503  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18008a508  mov     ecx, eax
0x18008a50a  jmp     loc_18008AC89
0x18008a50f  mov     rax, [rcx]
0x18008a512  test    edx, edx
0x18008a514  jnz     short loc_18008A55C
0x18008a516  mov     rax, [rax+110h]
0x18008a51d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a522  mov     ebx, eax
0x18008a524  mov     rcx, [rsp+98h+bstrString]; bstrString
0x18008a529  test    rcx, rcx
0x18008a52c  jz      short loc_18008A53F
0x18008a52e  call    cs:__imp_SysFreeString
0x18008a535  nop     dword ptr [rax+rax+00h]
0x18008a53a  mov     [rsp+98h+bstrString], r13
0x18008a53f  mov     rcx, [rsp+98h+var_50]; bstrString
0x18008a544  test    rcx, rcx
0x18008a547  jz      short loc_18008A555
0x18008a549  call    cs:__imp_SysFreeString
0x18008a550  nop     dword ptr [rax+rax+00h]
0x18008a555  mov     eax, ebx
0x18008a557  jmp     loc_18008AD39
0x18008a55c  lea     rdx, [rsp+98h+var_48]
0x18008a561  mov     rax, [rax+0B0h]
0x18008a568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a56d  mov     edi, eax
0x18008a56f  test    eax, eax
0x18008a571  jns     short loc_18008A594
0x18008a573  mov     rcx, [rsi+258h]
0x18008a57a  test    rcx, rcx
0x18008a57d  jz      loc_18008AC5E
0x18008a583  mov     [rsp+98h+cchCount2], eax
0x18008a587  mov     dword ptr [rsp+98h+lpString2], 15BEh
0x18008a58f  jmp     loc_18008A4F0
0x18008a594  mov     r15d, [rsp+98h+var_48]
0x18008a599  test    r15d, r15d
0x18008a59c  jz      loc_18008A7A8
0x18008a5a2  lea     eax, [r15-1]
0x18008a5a6  cmp     eax, r15d
0x18008a5a9  ja      short loc_18008A5B3
0x18008a5ab  mov     r15d, eax
0x18008a5ae  mov     edi, r13d
0x18008a5b1  jmp     short loc_18008A5BF
0x18008a5b3  mov     edi, 80070216h
0x18008a5b8  mov     ecx, edi
0x18008a5ba  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18008a5bf  mov     ecx, edi
0x18008a5c1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18008a5c6  test    edi, edi
0x18008a5c8  jns     short loc_18008A5EB
0x18008a5ca  mov     rcx, [rsi+258h]
0x18008a5d1  test    rcx, rcx
0x18008a5d4  jz      loc_18008AC5E
0x18008a5da  mov     [rsp+98h+cchCount2], edi
0x18008a5de  mov     dword ptr [rsp+98h+lpString2], 15C2h
0x18008a5e6  jmp     loc_18008A4F0
0x18008a5eb  mov     rcx, [rsp+98h+var_50]; bstrString
0x18008a5f0  test    rcx, rcx
0x18008a5f3  jz      short loc_18008A606
0x18008a5f5  call    cs:__imp_SysFreeString
0x18008a5fc  nop     dword ptr [rax+rax+00h]
0x18008a601  mov     [rsp+98h+var_50], r13
0x18008a606  mov     rcx, [rsi+260h]
0x18008a60d  mov     rax, [rcx]
0x18008a610  lea     r9, [rsp+98h+var_44]
0x18008a615  lea     r8, [rsp+98h+var_50]
0x18008a61a  mov     edx, r15d
0x18008a61d  mov     rax, [rax+0A8h]
0x18008a624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a629  mov     edi, eax
0x18008a62b  test    eax, eax
0x18008a62d  jns     short loc_18008A650
0x18008a62f  mov     rcx, [rsi+258h]
0x18008a636  test    rcx, rcx
0x18008a639  jz      loc_18008AC5E
0x18008a63f  mov     [rsp+98h+cchCount2], eax
0x18008a643  mov     dword ptr [rsp+98h+lpString2], 15C5h
0x18008a64b  jmp     loc_18008A4F0
0x18008a650  test    r14, r14
0x18008a653  jz      short loc_18008A682
0x18008a655  call    cs:__imp_GetProcessHeap
0x18008a65c  nop     dword ptr [rax+rax+00h]
0x18008a661  mov     rcx, rax; hHeap
0x18008a664  lea     r8, [r14-4]; lpMem
0x18008a668  xor     edx, edx; dwFlags
0x18008a66a  call    cs:__imp_HeapFree
0x18008a671  nop     dword ptr [rax+rax+00h]
0x18008a676  xor     ecx, ecx
0x18008a678  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18008a67d  mov     [rsp+98h+lpString1], r13
0x18008a682  mov     rbx, [rsp+98h+var_60]
0x18008a687  test    rbx, rbx
0x18008a68a  jz      short loc_18008A6B9
0x18008a68c  call    cs:__imp_GetProcessHeap
0x18008a693  nop     dword ptr [rax+rax+00h]
0x18008a698  mov     rcx, rax; hHeap
0x18008a69b  lea     r8, [rbx-4]; lpMem
0x18008a69f  xor     edx, edx; dwFlags
0x18008a6a1  call    cs:__imp_HeapFree
0x18008a6a8  nop     dword ptr [rax+rax+00h]
0x18008a6ad  xor     ecx, ecx
0x18008a6af  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18008a6b4  mov     [rsp+98h+var_60], r13
0x18008a6b9  mov     [rsp+98h+lpString2], r13; __int64
0x18008a6be  lea     r9, [rsp+98h+var_60]
0x18008a6c3  lea     r8, [rsp+98h+lpString1]
0x18008a6c8  mov     rcx, [rsp+98h+var_50]; Src
0x18008a6cd  call    ?ParseFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_WPEAHPEAPEA_W22@Z; CMiscHelpersT<CEmptyType>::ParseFileName(wchar_t const *,int *,wchar_t * *,wchar_t * *,wchar_t * *)
0x18008a6d2  mov     edi, eax
0x18008a6d4  test    eax, eax
0x18008a6d6  jns     short loc_18008A727
0x18008a6d8  mov     rcx, [rsi+258h]
0x18008a6df  test    rcx, rcx
0x18008a6e2  jnz     short loc_18008A6E9
0x18008a6e4  mov     ecx, r13d
0x18008a6e7  jmp     short loc_18008A718
0x18008a6e9  mov     [rsp+98h+cchCount2], eax
0x18008a6ed  mov     dword ptr [rsp+98h+lpString2], 15C9h
0x18008a6f5  lea     r9, aCdeploymentses_14; "CDeploymentSession::ResetState"
0x18008a6fc  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18008a703  mov     edx, 4
0x18008a708  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18008a70d  mov     ecx, eax
0x18008a70f  test    ecx, ecx
0x18008a711  jns     short loc_18008A718
0x18008a713  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18008a718  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18008a71d  mov     r14, [rsp+98h+lpString1]
0x18008a722  jmp     loc_18008AC97
0x18008a727  mov     r14, [rsp+98h+lpString1]
0x18008a72c  test    r14, r14
0x18008a72f  jz      short loc_18008A767
0x18008a731  or      ebx, 0FFFFFFFFh
0x18008a734  mov     [rsp+98h+cchCount2], ebx; cchCount2
0x18008a738  lea     rax, aPersist; "Persist"
0x18008a73f  mov     [rsp+98h+lpString2], rax; lpString2
0x18008a744  mov     r9d, ebx; cchCount1
0x18008a747  mov     r8, r14; lpString1
0x18008a74a  lea     edx, [rbx+2]; dwCmpFlags
0x18008a74d  mov     ecx, 409h; Locale
0x18008a752  call    cs:__imp_CompareStringW
0x18008a759  nop     dword ptr [rax+rax+00h]
0x18008a75e  cmp     eax, 2
0x18008a761  jz      loc_18008A599
0x18008a767  mov     rcx, [rsi+260h]
0x18008a76e  mov     rax, [rcx]
0x18008a771  mov     edx, r15d
0x18008a774  mov     rax, [rax+60h]
0x18008a778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a77d  mov     edi, eax
0x18008a77f  test    eax, eax
0x18008a781  jns     loc_18008A599
0x18008a787  mov     rcx, [rsi+258h]
0x18008a78e  test    rcx, rcx
0x18008a791  jz      loc_18008AC5E
0x18008a797  mov     [rsp+98h+cchCount2], eax
0x18008a79b  mov     dword ptr [rsp+98h+lpString2], 15CEh
0x18008a7a3  jmp     loc_18008A4F0
0x18008a7a8  mov     rcx, [rsi+260h]
0x18008a7af  mov     rax, [rcx]
0x18008a7b2  lea     rdx, [rsp+98h+var_48]
0x18008a7b7  mov     rax, [rax+0D0h]
0x18008a7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a7c3  mov     edi, eax
0x18008a7c5  test    eax, eax
0x18008a7c7  jns     short loc_18008A7EA
0x18008a7c9  mov     rcx, [rsi+258h]
0x18008a7d0  test    rcx, rcx
0x18008a7d3  jz      loc_18008AC5E
0x18008a7d9  mov     [rsp+98h+cchCount2], eax
0x18008a7dd  mov     dword ptr [rsp+98h+lpString2], 15D2h
0x18008a7e5  jmp     loc_18008A4F0
0x18008a7ea  mov     r15d, [rsp+98h+var_48]
0x18008a7ef  test    r15d, r15d
0x18008a7f2  jz      loc_18008A9EA
0x18008a7f8  lea     eax, [r15-1]
0x18008a7fc  cmp     eax, r15d
0x18008a7ff  ja      short loc_18008A809
0x18008a801  mov     r15d, eax
0x18008a804  mov     edi, r13d
0x18008a807  jmp     short loc_18008A815
0x18008a809  mov     edi, 80070216h
0x18008a80e  mov     ecx, edi
0x18008a810  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18008a815  mov     ecx, edi
0x18008a817  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18008a81c  test    edi, edi
0x18008a81e  jns     short loc_18008A841
0x18008a820  mov     rcx, [rsi+258h]
0x18008a827  test    rcx, rcx
0x18008a82a  jz      loc_18008AC5E
0x18008a830  mov     [rsp+98h+cchCount2], edi
0x18008a834  mov     dword ptr [rsp+98h+lpString2], 15D6h
0x18008a83c  jmp     loc_18008A4F0
0x18008a841  mov     rcx, [rsp+98h+var_50]; bstrString
0x18008a846  test    rcx, rcx
0x18008a849  jz      short loc_18008A85C
0x18008a84b  call    cs:__imp_SysFreeString
0x18008a852  nop     dword ptr [rax+rax+00h]
0x18008a857  mov     [rsp+98h+var_50], r13
0x18008a85c  mov     rcx, [rsi+260h]
0x18008a863  mov     rax, [rcx]
0x18008a866  lea     r9, [rsp+98h+var_38]
0x18008a86b  lea     r8, [rsp+98h+var_50]
0x18008a870  mov     edx, r15d
0x18008a873  mov     rax, [rax+0C8h]
0x18008a87a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a87f  mov     edi, eax
0x18008a881  test    eax, eax
0x18008a883  jns     short loc_18008A8A6
0x18008a885  mov     rcx, [rsi+258h]
0x18008a88c  test    rcx, rcx
0x18008a88f  jz      loc_18008AC5E
0x18008a895  mov     [rsp+98h+cchCount2], eax
0x18008a899  mov     dword ptr [rsp+98h+lpString2], 15D9h
0x18008a8a1  jmp     loc_18008A4F0
0x18008a8a6  test    r14, r14
0x18008a8a9  jz      short loc_18008A8D8
0x18008a8ab  call    cs:__imp_GetProcessHeap
0x18008a8b2  nop     dword ptr [rax+rax+00h]
0x18008a8b7  mov     rcx, rax; hHeap
0x18008a8ba  lea     r8, [r14-4]; lpMem
0x18008a8be  xor     edx, edx; dwFlags
0x18008a8c0  call    cs:__imp_HeapFree
0x18008a8c7  nop     dword ptr [rax+rax+00h]
0x18008a8cc  xor     ecx, ecx
0x18008a8ce  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18008a8d3  mov     [rsp+98h+lpString1], r13
0x18008a8d8  mov     rbx, [rsp+98h+var_60]
0x18008a8dd  test    rbx, rbx
0x18008a8e0  jz      short loc_18008A90F
0x18008a8e2  call    cs:__imp_GetProcessHeap
0x18008a8e9  nop     dword ptr [rax+rax+00h]
0x18008a8ee  mov     rcx, rax; hHeap
0x18008a8f1  lea     r8, [rbx-4]; lpMem
0x18008a8f5  xor     edx, edx; dwFlags
0x18008a8f7  call    cs:__imp_HeapFree
0x18008a8fe  nop     dword ptr [rax+rax+00h]
0x18008a903  xor     ecx, ecx
0x18008a905  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18008a90a  mov     [rsp+98h+var_60], r13
0x18008a90f  mov     [rsp+98h+lpString2], r13; __int64
0x18008a914  lea     r9, [rsp+98h+var_60]
0x18008a919  lea     r8, [rsp+98h+lpString1]
0x18008a91e  mov     rcx, [rsp+98h+var_50]; Src
0x18008a923  call    ?ParseFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_WPEAHPEAPEA_W22@Z; CMiscHelpersT<CEmptyType>::ParseFileName(wchar_t const *,int *,wchar_t * *,wchar_t * *,wchar_t * *)
0x18008a928  mov     edi, eax
0x18008a92a  test    eax, eax
0x18008a92c  jns     short loc_18008A969
0x18008a92e  mov     rcx, [rsi+258h]
0x18008a935  test    rcx, rcx
0x18008a938  jz      loc_18008A6E4
0x18008a93e  mov     [rsp+98h+cchCount2], eax
0x18008a942  mov     dword ptr [rsp+98h+lpString2], 15DDh
0x18008a94a  lea     r9, aCdeploymentses_14; "CDeploymentSession::ResetState"
0x18008a951  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18008a958  mov     edx, 4
0x18008a95d  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18008a962  mov     ecx, eax
0x18008a964  jmp     loc_18008A70F
0x18008a969  mov     r14, [rsp+98h+lpString1]
0x18008a96e  test    r14, r14
0x18008a971  jz      short loc_18008A9A9
0x18008a973  or      eax, 0FFFFFFFFh
  ... truncated ...
```
