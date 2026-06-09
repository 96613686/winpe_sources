# CUserLogonProcessingList::ProcessUserLogon(ulong)

- ea: `0x180056bcc`
- end: `0x180057143`
- name: `?ProcessUserLogon@CUserLogonProcessingList@@QEAAJK@Z`
- size: `1399`
- prototype: `__int64 __fastcall(CUserLogonProcessingList *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180057150`

## callees

- `0x180001fe8`
- `0x180002a5c`
- `0x180009f30`
- `0x180009f60`
- `0x18001a508`
- `0x18001c6c8`
- `0x18001fd14`
- `0x180022008`
- `0x180023c1c`
- `0x180026094`
- `0x18002858c`
- `0x18002b6ac`
- `0x18002fb58`
- `0x180034070`
- `0x180054f20`
- `0x180055fb4`
- `0x180056bcc`
- `0x18005876c`
- `0x18006a26c`
- `0x18006a594`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ccf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18005710d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18005710d`
- `WTSAPI32!WTSQueryUserToken` at `0x180056cbf`
- `WTSAPI32!WTSQueryUserToken` at `0x180056cbf`

## string_xrefs

- `0x180056d1c`: `WTSQueryUserToken failed with session id: %d`
- `0x180056d86`: `CheckIsInteractiveUserToken`
- `0x180056dff`: `GetFullToken`
- `0x180056e49`: `CheckIsElevatedAdminToken`
- `0x180057016`: `ComInit.Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CUserLogonProcessingList::ProcessUserLogon(CUserLogonProcessingList *this, ULONG a2)
{
  signed int LastError; // eax
  signed int IsUserAADJoined; // ebx
  unsigned int v6; // eax
  PVOID *v7; // rcx
  const char *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  unsigned int FullToken; // eax
  unsigned int v12; // eax
  CUserLogonProcessingList *v13; // rcx
  int v14; // edi
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  char *v22; // [rsp+28h] [rbp-61h]
  bool v23; // [rsp+30h] [rbp-59h] BYREF
  bool v24; // [rsp+31h] [rbp-58h] BYREF
  _BYTE v25[2]; // [rsp+32h] [rbp-57h] BYREF
  char v26[4]; // [rsp+34h] [rbp-55h] BYREF
  __int64 v27; // [rsp+38h] [rbp-51h] BYREF
  __int64 v28; // [rsp+40h] [rbp-49h]
  __int64 v29; // [rsp+48h] [rbp-41h]
  int v30; // [rsp+50h] [rbp-39h] BYREF
  __int64 (__fastcall **v31)(); // [rsp+58h] [rbp-31h] BYREF
  __int64 *v32; // [rsp+60h] [rbp-29h]
  __int64 v33; // [rsp+68h] [rbp-21h] BYREF
  __int64 *v34; // [rsp+70h] [rbp-19h]
  __int64 (__fastcall ***v35)(); // [rsp+90h] [rbp+7h]
  void *phToken; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v37; // [rsp+A0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v25[0] = 0;
  v24 = 0;
  v23 = 0;
  v37 = 0;
  phToken = 0;
  *(_DWORD *)v26 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
  v31 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v34 = &v33;
  v33 = (__int64)&v33;
  v32 = FVETRACE_DE_USER_LOGON_PROCESSING_START;
  FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v27, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v31);
  FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v27);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, a2);
  SH<void *,SH_HANDLE>::Reset(&phToken);
  if ( !WTSQueryUserToken(a2, &phToken) )
  {
    LastError = GetLastError();
    IsUserAADJoined = LastError;
    if ( LastError > 0 )
      IsUserAADJoined = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        146,
        &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
        a2,
        IsUserAADJoined);
    LODWORD(v22) = a2;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x902,
      (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
      (const char *)(unsigned int)IsUserAADJoined,
      (int)"WTSQueryUserToken failed with session id: %d",
      v22);
    goto LABEL_70;
  }
  v6 = CNgscbToken::CheckIsTokenMember(&phToken, WinInteractiveSid, &v23);
  IsUserAADJoined = v6;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v6);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( IsUserAADJoined < 0 )
  {
    v8 = "CheckIsInteractiveUserToken";
    v9 = 2314;
LABEL_69:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v9,
      (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
      (const char *)(unsigned int)IsUserAADJoined,
      (int)v8,
      v22);
    goto LABEL_70;
  }
  if ( !v23 )
  {
    if ( v7 == &WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 8) == 0 )
      goto LABEL_70;
    v10 = 148;
    goto LABEL_23;
  }
  FullToken = CNgscbToken::GetFullToken(&phToken, (struct CNgscbToken *)&v37);
  IsUserAADJoined = FullToken;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, FullToken);
  if ( IsUserAADJoined < 0 )
  {
    v8 = "GetFullToken";
    v9 = 2326;
    goto LABEL_69;
  }
  v12 = CNgscbToken::CheckIsElevatedAdminToken((CNgscbToken *)&v37, &v24);
  IsUserAADJoined = v12;
  v13 = (CUserLogonProcessingList *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v12);
  if ( IsUserAADJoined < 0 )
  {
    v8 = "CheckIsElevatedAdminToken";
    v9 = 2328;
    goto LABEL_69;
  }
  if ( !v24 )
  {
    IsUserAADJoined = CUserLogonProcessingList::IsUserAADJoined(v13, (int *)v26);
    v14 = *(_DWORD *)v26;
    if ( (unsigned int)dword_18009A348 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
    {
      *(_DWORD *)v26 = IsUserAADJoined;
      v30 = v14;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v15,
        (int)byte_18008DD13,
        v16,
        v17,
        (__int64)&v30,
        (__int64)v26);
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        151,
        &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
        (unsigned int)IsUserAADJoined);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( IsUserAADJoined < 0 )
    {
      v8 = "IsUserAADJoined";
      v9 = 2341;
      goto LABEL_69;
    }
    if ( !v14 )
    {
      if ( v7 == &WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 8) == 0 )
        goto LABEL_70;
      v10 = 152;
LABEL_23:
      WPP_SF_(v7[2], v10, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
      goto LABEL_70;
    }
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
      WPP_SF_(v7[2], 153, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
  }
  if ( CUserLogonProcessingList::IsUserLogonProcessingActive(this, a2) )
  {
    v31 = off_180080660;
    v32 = &v37;
    v35 = &v31;
    v18 = CUserLogonProcessingList::WithSession(this, a2, &v31);
    IsUserAADJoined = v18;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v18);
    if ( IsUserAADJoined < 0 )
    {
      v8 = "WithSession";
      v9 = 2377;
      goto LABEL_69;
    }
    v19 = CInitializeCom::Initialize((CInitializeCom *)v25);
    IsUserAADJoined = v19;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v19);
    if ( IsUserAADJoined < 0 )
    {
      v8 = "ComInit.Initialize";
      v9 = 2384;
      goto LABEL_69;
    }
    v20 = CUserLogonProcessingList::ProcessAdminLogon(this, a2, (const struct CNgscbToken *)&v37);
    IsUserAADJoined = v20;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v20);
    if ( IsUserAADJoined < 0 )
    {
      v8 = "ProcessAdminLogon";
      v9 = 2385;
      goto LABEL_69;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, a2);
  }
LABEL_70:
  CUserLogonProcessingList::EndUserLogonProcessing(this, a2);
  v31 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v34 = &v33;
  v33 = (__int64)&v33;
  v32 = FVETRACE_DE_USER_LOGON_PROCESSING_STOP;
  FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v27, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v31);
  FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v27);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
  SH<void *,SH_HANDLE>::Reset(&phToken);
  SH<void *,SH_HANDLE>::Reset(&v37);
  if ( v25[0] )
    CoUninitialize();
  return (unsigned int)IsUserAADJoined;
}

```

## disassembly

```asm
0x180056bcc  mov     [rsp-8+arg_10], rbx
0x180056bd1  push    rbp
0x180056bd2  push    rsi
0x180056bd3  push    rdi
0x180056bd4  push    r12
0x180056bd6  push    r13
0x180056bd8  push    r14
0x180056bda  push    r15
0x180056bdc  lea     rbp, [rsp-27h]
0x180056be1  sub     rsp, 0B0h
0x180056be8  mov     rax, cs:__security_cookie
0x180056bef  xor     rax, rsp
0x180056bf2  mov     [rbp+57h+var_38], rax
0x180056bf6  mov     esi, edx
0x180056bf8  mov     r14, rcx
0x180056bfb  xor     r15d, r15d
0x180056bfe  mov     [rbp+57h+var_AE], r15b
0x180056c02  mov     [rbp+57h+var_AF], r15b
0x180056c06  mov     [rbp+57h+var_B0], r15b
0x180056c0a  mov     [rbp+57h+var_40], r15
0x180056c0e  mov     [rbp+57h+phToken], r15
0x180056c12  mov     dword ptr [rbp+57h+var_AC], r15d
0x180056c16  lea     r13, WPP_GLOBAL_Control
0x180056c1d  lea     r12, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x180056c24  mov     rcx, cs:WPP_GLOBAL_Control
0x180056c2b  cmp     rcx, r13
0x180056c2e  jz      short loc_180056C47
0x180056c30  test    byte ptr [rcx+1Ch], 20h
0x180056c34  jz      short loc_180056C47
0x180056c36  mov     edx, 90h
0x180056c3b  mov     r8, r12
0x180056c3e  mov     rcx, [rcx+10h]
0x180056c42  call    WPP_SF_
0x180056c47  mov     [rbp+57h+var_88], r15
0x180056c4b  mov     [rbp+57h+var_A8], r15
0x180056c4f  mov     [rbp+57h+var_A0], r15
0x180056c53  mov     [rbp+57h+var_98], r15
0x180056c57  lea     rax, [rbp+57h+var_78]
0x180056c5b  mov     [rbp+57h+var_70], rax
0x180056c5f  lea     rax, [rbp+57h+var_78]
0x180056c63  mov     [rbp+57h+var_78], rax
0x180056c67  lea     rax, FVETRACE_DE_USER_LOGON_PROCESSING_START
0x180056c6e  mov     [rbp+57h+var_80], rax
0x180056c72  lea     rdx, [rbp+57h+var_88]; struct _FVEAPI_EVENT_DATA_COLLECTION *
0x180056c76  lea     rcx, [rbp+57h+var_A8]; this
0x180056c7a  call    ?LogFveApiEvent@FveEventLogHandle@@QEAAJPEAU_FVEAPI_EVENT_DATA_COLLECTION@@@Z; FveEventLogHandle::LogFveApiEvent(_FVEAPI_EVENT_DATA_COLLECTION *)
0x180056c7f  nop
0x180056c80  lea     rcx, [rbp+57h+var_A8]; this
0x180056c84  call    ?EventLogCleanup@FveEventLogHandle@@AEAAXXZ; FveEventLogHandle::EventLogCleanup(void)
0x180056c89  nop
0x180056c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180056c91  cmp     rcx, r13
0x180056c94  jz      short loc_180056CB0
0x180056c96  test    byte ptr [rcx+1Ch], 8
0x180056c9a  jz      short loc_180056CB0
0x180056c9c  mov     edx, 91h
0x180056ca1  mov     r9d, esi
0x180056ca4  mov     r8, r12
0x180056ca7  mov     rcx, [rcx+10h]
0x180056cab  call    WPP_SF_d
0x180056cb0  lea     rcx, [rbp+57h+phToken]
0x180056cb4  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180056cb9  lea     rdx, [rbp+57h+phToken]; phToken
0x180056cbd  mov     ecx, esi; SessionId
0x180056cbf  call    cs:__imp_WTSQueryUserToken
0x180056cc6  nop     dword ptr [rax+rax+00h]
0x180056ccb  test    eax, eax
0x180056ccd  jnz     short loc_180056D41
0x180056ccf  call    cs:__imp_GetLastError
0x180056cd6  nop     dword ptr [rax+rax+00h]
0x180056cdb  mov     ebx, eax
0x180056cdd  test    eax, eax
0x180056cdf  jle     short loc_180056CEA
0x180056ce1  movzx   ebx, ax
0x180056ce4  or      ebx, 80070000h
0x180056cea  mov     rcx, cs:WPP_GLOBAL_Control
0x180056cf1  cmp     rcx, r13
0x180056cf4  jz      short loc_180056D14
0x180056cf6  test    byte ptr [rcx+1Ch], 2
0x180056cfa  jz      short loc_180056D14
0x180056cfc  mov     edx, 92h
0x180056d01  mov     [rsp+0E0h+var_C0], ebx
0x180056d05  mov     r9d, esi
0x180056d08  mov     r8, r12
0x180056d0b  mov     rcx, [rcx+10h]
0x180056d0f  call    WPP_SF_DD
0x180056d14  mov     rcx, [rbp+5Fh]; this
0x180056d18  mov     dword ptr [rsp+0E0h+var_B8], esi; char *
0x180056d1c  lea     rax, aWtsqueryuserto_0; "WTSQueryUserToken failed with session i"...
0x180056d23  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180056d28  mov     r9d, ebx; char *
0x180056d2b  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x180056d32  mov     edx, 902h; void *
0x180056d37  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180056d3c  jmp     loc_180057082
0x180056d41  lea     r8, [rbp+57h+var_B0]; bool *
0x180056d45  mov     edx, 0Bh; enum WELL_KNOWN_SID_TYPE
0x180056d4a  lea     rcx, [rbp+57h+phToken]; this
0x180056d4e  call    ?CheckIsTokenMember@CNgscbToken@@AEBAJW4WELL_KNOWN_SID_TYPE@@PEA_N@Z; CNgscbToken::CheckIsTokenMember(WELL_KNOWN_SID_TYPE,bool *)
0x180056d53  mov     ebx, eax
0x180056d55  mov     rcx, cs:WPP_GLOBAL_Control
0x180056d5c  cmp     rcx, r13
0x180056d5f  jz      short loc_180056D82
0x180056d61  test    byte ptr [rcx+1Ch], 40h
0x180056d65  jz      short loc_180056D82
0x180056d67  mov     edx, 93h
0x180056d6c  mov     r9d, eax
0x180056d6f  mov     r8, r12
0x180056d72  mov     rcx, [rcx+10h]
0x180056d76  call    WPP_SF_d
0x180056d7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180056d82  test    ebx, ebx
0x180056d84  jns     short loc_180056D97
0x180056d86  lea     rax, aCheckisinterac; "CheckIsInteractiveUserToken"
0x180056d8d  mov     edx, 90Ah
0x180056d92  jmp     loc_18005706A
0x180056d97  cmp     [rbp+57h+var_B0], r15b
0x180056d9b  jnz     short loc_180056DC6
0x180056d9d  cmp     rcx, r13
0x180056da0  jz      loc_180057082
0x180056da6  test    byte ptr [rcx+1Ch], 8
0x180056daa  jz      loc_180057082
0x180056db0  mov     edx, 94h
0x180056db5  mov     r8, r12
0x180056db8  mov     rcx, [rcx+10h]
0x180056dbc  call    WPP_SF_
0x180056dc1  jmp     loc_180057082
0x180056dc6  lea     rdx, [rbp+57h+var_40]; struct CNgscbToken *
0x180056dca  lea     rcx, [rbp+57h+phToken]; this
0x180056dce  call    ?GetFullToken@CNgscbToken@@QEBAJAEAV1@@Z; CNgscbToken::GetFullToken(CNgscbToken &)
0x180056dd3  mov     ebx, eax
0x180056dd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ddc  cmp     rcx, r13
0x180056ddf  jz      short loc_180056DFB
0x180056de1  test    byte ptr [rcx+1Ch], 40h
0x180056de5  jz      short loc_180056DFB
0x180056de7  mov     edx, 95h
0x180056dec  mov     r9d, eax
0x180056def  mov     r8, r12
0x180056df2  mov     rcx, [rcx+10h]
0x180056df6  call    WPP_SF_d
0x180056dfb  test    ebx, ebx
0x180056dfd  jns     short loc_180056E10
0x180056dff  lea     rax, aGetfulltoken; "GetFullToken"
0x180056e06  mov     edx, 916h
0x180056e0b  jmp     loc_18005706A
0x180056e10  lea     rdx, [rbp+57h+var_AF]; bool *
0x180056e14  lea     rcx, [rbp+57h+var_40]; this
0x180056e18  call    ?CheckIsElevatedAdminToken@CNgscbToken@@QEBAJPEA_N@Z; CNgscbToken::CheckIsElevatedAdminToken(bool *)
0x180056e1d  mov     ebx, eax
0x180056e1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180056e26  cmp     rcx, r13
0x180056e29  jz      short loc_180056E45
0x180056e2b  test    byte ptr [rcx+1Ch], 40h
0x180056e2f  jz      short loc_180056E45
0x180056e31  mov     edx, 96h
0x180056e36  mov     r9d, eax
0x180056e39  mov     r8, r12
0x180056e3c  mov     rcx, [rcx+10h]
0x180056e40  call    WPP_SF_d
0x180056e45  test    ebx, ebx
0x180056e47  jns     short loc_180056E5A
0x180056e49  lea     rax, aCheckiselevate; "CheckIsElevatedAdminToken"
0x180056e50  mov     edx, 918h
0x180056e55  jmp     loc_18005706A
0x180056e5a  cmp     [rbp+57h+var_AF], r15b
0x180056e5e  jnz     loc_180056F3A
0x180056e64  lea     rdx, [rbp+57h+var_AC]; int *
0x180056e68  call    ?IsUserAADJoined@CUserLogonProcessingList@@IEAAJPEAH@Z; CUserLogonProcessingList::IsUserAADJoined(int *)
0x180056e6d  mov     ebx, eax
0x180056e6f  mov     eax, cs:dword_18009A348
0x180056e75  mov     edi, dword ptr [rbp+57h+var_AC]
0x180056e78  cmp     eax, 5
0x180056e7b  jbe     short loc_180056EBB
0x180056e7d  mov     rdx, 400000000000h
0x180056e87  lea     rcx, dword_18009A348
0x180056e8e  call    _tlgKeywordOn
0x180056e93  test    al, al
0x180056e95  jz      short loc_180056EBB
0x180056e97  mov     dword ptr [rbp+57h+var_AC], ebx
0x180056e9a  mov     [rbp+57h+var_90], edi
0x180056e9d  lea     rax, [rbp+57h+var_AC]
0x180056ea1  mov     [rsp+0E0h+var_B8], rax; char *
0x180056ea6  lea     rax, [rbp+57h+var_90]
0x180056eaa  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180056eaf  lea     rdx, byte_18008DD13
0x180056eb6  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180056ebb  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ec2  cmp     rcx, r13
0x180056ec5  jz      short loc_180056EE8
0x180056ec7  test    byte ptr [rcx+1Ch], 40h
0x180056ecb  jz      short loc_180056EE8
0x180056ecd  mov     edx, 97h
0x180056ed2  mov     r9d, ebx
0x180056ed5  mov     r8, r12
0x180056ed8  mov     rcx, [rcx+10h]
0x180056edc  call    WPP_SF_d
0x180056ee1  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ee8  test    ebx, ebx
0x180056eea  jns     short loc_180056EFD
0x180056eec  lea     rax, aIsuseraadjoine; "IsUserAADJoined"
0x180056ef3  mov     edx, 925h
0x180056ef8  jmp     loc_18005706A
0x180056efd  test    edi, edi
0x180056eff  jnz     short loc_180056F1E
0x180056f01  cmp     rcx, r13
0x180056f04  jz      loc_180057082
0x180056f0a  test    byte ptr [rcx+1Ch], 8
0x180056f0e  jz      loc_180057082
0x180056f14  mov     edx, 98h
0x180056f19  jmp     loc_180056DB5
0x180056f1e  cmp     rcx, r13
0x180056f21  jz      short loc_180056F3A
0x180056f23  test    byte ptr [rcx+1Ch], 8
0x180056f27  jz      short loc_180056F3A
0x180056f29  mov     edx, 99h
0x180056f2e  mov     r8, r12
0x180056f31  mov     rcx, [rcx+10h]
0x180056f35  call    WPP_SF_
0x180056f3a  mov     edx, esi; unsigned int
0x180056f3c  mov     rcx, r14; this
0x180056f3f  call    ?IsUserLogonProcessingActive@CUserLogonProcessingList@@IEAA_NK@Z; CUserLogonProcessingList::IsUserLogonProcessingActive(ulong)
0x180056f44  test    al, al
0x180056f46  jnz     short loc_180056F7B
0x180056f48  mov     rcx, cs:WPP_GLOBAL_Control
0x180056f4f  cmp     rcx, r13
0x180056f52  jz      loc_180057082
0x180056f58  test    byte ptr [rcx+1Ch], 8
0x180056f5c  jz      loc_180057082
0x180056f62  mov     edx, 9Ah
0x180056f67  mov     r9d, esi
0x180056f6a  mov     r8, r12
0x180056f6d  mov     rcx, [rcx+10h]
0x180056f71  call    WPP_SF_d
0x180056f76  jmp     loc_180057082
0x180056f7b  lea     rax, off_180080660
0x180056f82  mov     [rbp+57h+var_88], rax
0x180056f86  lea     rax, [rbp+57h+var_40]
0x180056f8a  mov     [rbp+57h+var_80], rax
0x180056f8e  lea     rax, [rbp+57h+var_88]
0x180056f92  mov     [rbp+57h+var_50], rax
0x180056f96  lea     r8, [rbp+57h+var_88]
0x180056f9a  mov     edx, esi
0x180056f9c  mov     rcx, r14
0x180056f9f  call    ?WithSession@CUserLogonProcessingList@@IEAAJKV?$function@$$A6AJAEAVCSessionState@@@Z@std@@@Z; CUserLogonProcessingList::WithSession(ulong,std::function<long (CSessionState &)>)
0x180056fa4  mov     ebx, eax
0x180056fa6  mov     rcx, cs:WPP_GLOBAL_Control
0x180056fad  cmp     rcx, r13
0x180056fb0  jz      short loc_180056FCC
0x180056fb2  test    byte ptr [rcx+1Ch], 40h
0x180056fb6  jz      short loc_180056FCC
0x180056fb8  mov     edx, 9Bh
0x180056fbd  mov     r9d, eax
0x180056fc0  mov     r8, r12
0x180056fc3  mov     rcx, [rcx+10h]
0x180056fc7  call    WPP_SF_d
0x180056fcc  test    ebx, ebx
0x180056fce  jns     short loc_180056FE1
0x180056fd0  lea     rax, aWithsession; "WithSession"
0x180056fd7  mov     edx, 949h
0x180056fdc  jmp     loc_18005706A
0x180056fe1  lea     rcx, [rbp+57h+var_AE]; this
0x180056fe5  call    ?Initialize@CInitializeCom@@QEAAJXZ; CInitializeCom::Initialize(void)
0x180056fea  mov     ebx, eax
0x180056fec  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ff3  cmp     rcx, r13
0x180056ff6  jz      short loc_180057012
0x180056ff8  test    byte ptr [rcx+1Ch], 40h
0x180056ffc  jz      short loc_180057012
0x180056ffe  mov     edx, 9Ch
0x180057003  mov     r9d, eax
0x180057006  mov     r8, r12
0x180057009  mov     rcx, [rcx+10h]
0x18005700d  call    WPP_SF_d
0x180057012  test    ebx, ebx
0x180057014  jns     short loc_180057024
0x180057016  lea     rax, aCominitInitial; "ComInit.Initialize"
0x18005701d  mov     edx, 950h
0x180057022  jmp     short loc_18005706A
0x180057024  lea     r8, [rbp+57h+var_40]; struct CNgscbToken *
0x180057028  mov     edx, esi; unsigned int
0x18005702a  mov     rcx, r14; this
0x18005702d  call    ?ProcessAdminLogon@CUserLogonProcessingList@@IEAAJKAEBVCNgscbToken@@@Z; CUserLogonProcessingList::ProcessAdminLogon(ulong,CNgscbToken const &)
0x180057032  mov     ebx, eax
0x180057034  mov     rcx, cs:WPP_GLOBAL_Control
0x18005703b  cmp     rcx, r13
0x18005703e  jz      short loc_18005705A
0x180057040  test    byte ptr [rcx+1Ch], 40h
0x180057044  jz      short loc_18005705A
0x180057046  mov     edx, 9Dh
0x18005704b  mov     r9d, eax
0x18005704e  mov     r8, r12
0x180057051  mov     rcx, [rcx+10h]
0x180057055  call    WPP_SF_d
0x18005705a  test    ebx, ebx
0x18005705c  jns     short loc_180057082
0x18005705e  lea     rax, aProcessadminlo; "ProcessAdminLogon"
0x180057065  mov     edx, 951h; void *
0x18005706a  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18005706f  mov     r9d, ebx; char *
  ... truncated ...
```
