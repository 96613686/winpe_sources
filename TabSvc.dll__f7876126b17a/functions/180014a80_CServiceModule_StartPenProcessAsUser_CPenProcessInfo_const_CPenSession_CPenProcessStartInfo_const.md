# CServiceModule::StartPenProcessAsUser(CPenProcessInfo const *,CPenSession *,CPenProcessStartInfo const *)

- ea: `0x180014a80`
- end: `0x180014d38`
- name: `?StartPenProcessAsUser@CServiceModule@@QEAAXPEBVCPenProcessInfo@@PEAVCPenSession@@PEBUCPenProcessStartInfo@@@Z`
- size: `696`
- prototype: `void __fastcall(PVOID Context, const struct CPenProcessInfo *, struct CPenSession *, const struct CPenProcessStartInfo *)`
- caller_count: `4`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18000f260`
- `0x18001506c`
- `0x1800245fc`
- `0x180024730`

## callees

- `0x180001008`
- `0x180001d08`
- `0x180012dc0`
- `0x180014a80`
- `0x180014d40`
- `0x180015630`
- `0x18002b3a8`
- `0x18002b404`
- `0x18002b574`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bc5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180014c5a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180014c5a`
- `WTSAPI32!WTSQueryUserToken` at `0x180014ba9`
- `WTSAPI32!WTSQueryUserToken` at `0x180014ba9`

## string_xrefs

- `0x180014ab4`: `PENSERVICE_CServiceModule::StartPenProcessAsUser`
- `0x180014c16`: `Failed to obtain user token.`

## pseudocode

```c
void __fastcall CServiceModule::StartPenProcessAsUser(
        PVOID Context,
        const struct CPenProcessInfo *a2,
        struct CPenSession *a3,
        const struct CPenProcessStartInfo *a4)
{
  struct _GUID *v8; // rcx
  int v9; // ecx
  int v10; // r9d
  ULONG v11; // ecx
  char LastError; // al
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  const char *v16; // rax
  char *v17; // rdx
  int v18; // [rsp+40h] [rbp-20h] BYREF
  int v19; // [rsp+44h] [rbp-1Ch] BYREF
  void *phToken; // [rsp+48h] [rbp-18h] BYREF
  __int64 v21; // [rsp+50h] [rbp-10h] BYREF
  const char *v22; // [rsp+98h] [rbp+38h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      20,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::StartPenProcessAsUser");
    v8 = WPP_GLOBAL_Control;
  }
  if ( a2 && a3 )
  {
    if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    {
      LOBYTE(v22) = *((_BYTE *)Context + 64);
      v18 = *((_DWORD *)Context + 17);
      v19 = *((_DWORD *)a3 + 1);
      v21 = *((_QWORD *)a2 + 68);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
        v9,
        (unsigned int)&byte_18003A2EF,
        (_DWORD)a3,
        v10,
        (__int64)&v21,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v22);
    }
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
      WPP_SF_sSl(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        22,
        (_DWORD)a3,
        (unsigned int)"PENSERVICE_CServiceModule::StartPenProcessAsUser",
        *((_QWORD *)a2 + 68),
        *((_DWORD *)a3 + 1));
    v11 = *((_DWORD *)a3 + 1);
    phToken = 0;
    if ( WTSQueryUserToken(v11, &phToken) )
    {
      if ( !byte_180041A40 )
        byte_180041A40 = RegisterWaitForSingleObject(
                           (PHANDLE)Context + 23,
                           *((HANDLE *)Context + 18),
                           CServiceModule::s_StartInputPersonalizationCallback,
                           Context,
                           0x23E38u,
                           8u);
      CServiceModule::StartPenProcessCore((CServiceModule *)Context, a2, a3, phToken, a4);
      SH<void *,SH_HANDLE>::Reset(&phToken);
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
        WPP_SF_s(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          24,
          WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          "PENSERVICE_CServiceModule::StartPenProcessAsUser");
    }
    else
    {
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_sd(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          23,
          (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          (unsigned int)"PENSERVICE_CServiceModule::StartPenProcessAsUser",
          LastError);
      }
      if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
      {
        v16 = "Failed to obtain user token.";
        v17 = byte_18003A103;
LABEL_30:
        v22 = v16;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v13,
          (_DWORD)v17,
          v14,
          v15,
          (__int64)&v22);
      }
    }
  }
  else
  {
    if ( v8 != (struct _GUID *)&WPP_GLOBAL_Control && (v8[1].Data4[4] & 4) != 0 )
      WPP_SF_s(
        *(_QWORD *)&v8[1].Data1,
        21,
        WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
        "PENSERVICE_CServiceModule::StartPenProcessAsUser");
    if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    {
      v16 = "NULL pInfo or pSession.";
      v17 = byte_180039A1B;
      goto LABEL_30;
    }
  }
}

```

## disassembly

```asm
0x180014a80  mov     [rsp-28h+arg_0], rsi
0x180014a85  mov     [rsp-28h+arg_10], rdi
0x180014a8a  push    rbp
0x180014a8b  push    r12
0x180014a8d  push    r13
0x180014a8f  push    r14
0x180014a91  push    r15
0x180014a93  mov     rbp, rsp
0x180014a96  sub     rsp, 60h
0x180014a9a  mov     r15, r9
0x180014a9d  mov     rdi, r8
0x180014aa0  mov     r14, rdx
0x180014aa3  mov     rsi, rcx
0x180014aa6  mov     rcx, cs:WPP_GLOBAL_Control
0x180014aad  lea     r12, WPP_GLOBAL_Control
0x180014ab4  lea     r13, aPenserviceCser_24; "PENSERVICE_CServiceModule::StartPenProc"...
0x180014abb  cmp     rcx, r12
0x180014abe  jz      short loc_180014AE5
0x180014ac0  test    byte ptr [rcx+1Ch], 10h
0x180014ac4  jz      short loc_180014AE5
0x180014ac6  mov     rcx, [rcx+10h]
0x180014aca  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180014ad1  mov     edx, 14h
0x180014ad6  mov     r9, r13
0x180014ad9  call    WPP_SF_s
0x180014ade  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ae5  test    r14, r14
0x180014ae8  jz      loc_180014CBB
0x180014aee  test    rdi, rdi
0x180014af1  jz      loc_180014CBB
0x180014af7  mov     eax, cs:dword_1800411A8
0x180014afd  cmp     eax, 5
0x180014b00  jbe     short loc_180014B64
0x180014b02  mov     edx, 4000000h
0x180014b07  lea     rcx, dword_1800411A8
0x180014b0e  call    _tlgKeywordOn
0x180014b13  test    al, al
0x180014b15  jz      short loc_180014B64
0x180014b17  mov     al, [rsi+40h]
0x180014b1a  lea     rdx, byte_18003A2EF
0x180014b21  mov     byte ptr [rbp+arg_8], al
0x180014b24  mov     eax, [rsi+44h]
0x180014b27  mov     [rbp+var_20], eax
0x180014b2a  mov     eax, [rdi+4]
0x180014b2d  mov     [rbp+var_1C], eax
0x180014b30  mov     rax, [r14+220h]
0x180014b37  mov     [rbp+var_10], rax
0x180014b3b  lea     rax, [rbp+arg_8]
0x180014b3f  mov     [rsp+60h+var_28], rax
0x180014b44  lea     rax, [rbp+var_20]
0x180014b48  mov     [rsp+60h+var_30], rax
0x180014b4d  lea     rax, [rbp+var_1C]
0x180014b51  mov     qword ptr [rsp+60h+dwFlags], rax
0x180014b56  lea     rax, [rbp+var_10]
0x180014b5a  mov     qword ptr [rsp+60h+dwMilliseconds], rax
0x180014b5f  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x180014b64  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b6b  cmp     rcx, r12
0x180014b6e  jz      short loc_180014B9A
0x180014b70  test    byte ptr [rcx+1Ch], 10h
0x180014b74  jz      short loc_180014B9A
0x180014b76  mov     eax, [rdi+4]
0x180014b79  mov     edx, 16h
0x180014b7e  mov     rcx, [rcx+10h]
0x180014b82  mov     r9, r13
0x180014b85  mov     [rsp+60h+dwFlags], eax
0x180014b89  mov     rax, [r14+220h]
0x180014b90  mov     qword ptr [rsp+60h+dwMilliseconds], rax
0x180014b95  call    WPP_SF_sSl
0x180014b9a  mov     ecx, [rdi+4]; SessionId
0x180014b9d  lea     rdx, [rbp+phToken]; phToken
0x180014ba1  mov     [rbp+phToken], 0
0x180014ba9  call    cs:__imp_WTSQueryUserToken
0x180014baf  test    eax, eax
0x180014bb1  jnz     short loc_180014C29
0x180014bb3  mov     rax, cs:WPP_GLOBAL_Control
0x180014bba  cmp     rax, r12
0x180014bbd  jz      short loc_180014BEE
0x180014bbf  test    byte ptr [rax+1Ch], 4
0x180014bc3  jz      short loc_180014BEE
0x180014bc5  call    cs:__imp_GetLastError
0x180014bcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180014bd2  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180014bd9  mov     edx, 17h
0x180014bde  mov     [rsp+60h+dwMilliseconds], eax
0x180014be2  mov     r9, r13
0x180014be5  mov     rcx, [rcx+10h]
0x180014be9  call    WPP_SF_sd
0x180014bee  mov     eax, cs:dword_1800411A8
0x180014bf4  cmp     eax, 5
0x180014bf7  jbe     loc_180014D1E
0x180014bfd  mov     edx, 4000000h
0x180014c02  lea     rcx, dword_1800411A8
0x180014c09  call    _tlgKeywordOn
0x180014c0e  test    al, al
0x180014c10  jz      loc_180014D1E
0x180014c16  lea     rax, aFailedToObtain; "Failed to obtain user token."
0x180014c1d  lea     rdx, byte_18003A103
0x180014c24  jmp     loc_180014D0C
0x180014c29  cmp     cs:byte_180041A40, 0
0x180014c30  jnz     short loc_180014C6B
0x180014c32  mov     rdx, [rsi+90h]; hObject
0x180014c39  lea     rcx, [rsi+0B8h]; phNewWaitObject
0x180014c40  mov     [rsp+60h+dwFlags], 8; dwFlags
0x180014c48  lea     r8, ?s_StartInputPersonalizationCallback@CServiceModule@@SAXPEAXE@Z; Callback
0x180014c4f  mov     r9, rsi; Context
0x180014c52  mov     [rsp+60h+dwMilliseconds], 23E38h; dwMilliseconds
0x180014c5a  call    cs:__imp_RegisterWaitForSingleObject
0x180014c60  test    eax, eax
0x180014c62  jz      short loc_180014C6B
0x180014c64  mov     cs:byte_180041A40, 1
0x180014c6b  mov     r9, [rbp+phToken]; void *
0x180014c6f  mov     r8, rdi; struct CPenSession *
0x180014c72  mov     rdx, r14; struct CPenProcessInfo *
0x180014c75  mov     qword ptr [rsp+60h+dwMilliseconds], r15; struct CPenProcessStartInfo *
0x180014c7a  mov     rcx, rsi; this
0x180014c7d  call    ?StartPenProcessCore@CServiceModule@@QEAAXPEBVCPenProcessInfo@@PEAVCPenSession@@PEAXPEBUCPenProcessStartInfo@@@Z; CServiceModule::StartPenProcessCore(CPenProcessInfo const *,CPenSession *,void *,CPenProcessStartInfo const *)
0x180014c82  lea     rcx, [rbp+phToken]
0x180014c86  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180014c8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c92  cmp     rcx, r12
0x180014c95  jz      loc_180014D1E
0x180014c9b  test    byte ptr [rcx+1Ch], 10h
0x180014c9f  jz      short loc_180014D1E
0x180014ca1  mov     rcx, [rcx+10h]
0x180014ca5  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180014cac  mov     edx, 18h
0x180014cb1  mov     r9, r13
0x180014cb4  call    WPP_SF_s
0x180014cb9  jmp     short loc_180014D1E
0x180014cbb  cmp     rcx, r12
0x180014cbe  jz      short loc_180014CDE
0x180014cc0  test    byte ptr [rcx+1Ch], 4
0x180014cc4  jz      short loc_180014CDE
0x180014cc6  mov     rcx, [rcx+10h]
0x180014cca  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180014cd1  mov     edx, 15h
0x180014cd6  mov     r9, r13
0x180014cd9  call    WPP_SF_s
0x180014cde  mov     eax, cs:dword_1800411A8
0x180014ce4  cmp     eax, 5
0x180014ce7  jbe     short loc_180014D1E
0x180014ce9  mov     edx, 4000000h
0x180014cee  lea     rcx, dword_1800411A8
0x180014cf5  call    _tlgKeywordOn
0x180014cfa  test    al, al
0x180014cfc  jz      short loc_180014D1E
0x180014cfe  lea     rax, aNullPinfoOrPse; "NULL pInfo or pSession."
0x180014d05  lea     rdx, byte_180039A1B
0x180014d0c  mov     [rbp+arg_8], rax
0x180014d10  lea     rax, [rbp+arg_8]
0x180014d14  mov     qword ptr [rsp+60h+dwMilliseconds], rax
0x180014d19  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180014d1e  lea     r11, [rsp+60h+var_s0]
0x180014d23  mov     rsi, [r11+30h]
0x180014d27  mov     rdi, [r11+40h]
0x180014d2b  mov     rsp, r11
0x180014d2e  pop     r15
0x180014d30  pop     r14
0x180014d32  pop     r13
0x180014d34  pop     r12
0x180014d36  pop     rbp
0x180014d37  retn
```
