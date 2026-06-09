# BdeSvcApipRotateRecoveryPasswords

- ea: `0x18005c000`
- end: `0x18005c57b`
- name: `BdeSvcApipRotateRecoveryPasswords`
- size: `1403`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18000a010`
- `0x180023354`
- `0x180034070`
- `0x180044378`
- `0x18004a218`
- `0x18005aa80`
- `0x18005ab8c`
- `0x18005acf0`
- `0x18005ae00`
- `0x18005c000`
- `0x18005f660`
- `0x18006a26c`
- `0x18006a594`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005c13b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005c13b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c444`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c444`
- `RPCRT4!RpcImpersonateClient` at `0x18005c066`
- `RPCRT4!RpcImpersonateClient` at `0x18005c066`
- `RPCRT4!RpcRevertToSelf` at `0x18005c4f7`
- `RPCRT4!RpcRevertToSelf` at `0x18005c4f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BdeSvcApipRotateRecoveryPasswords(__int64 a1, const unsigned __int16 *a2)
{
  unsigned __int64 SystemTimeInULL; // r14
  RPC_STATUS v4; // eax
  unsigned int v5; // ebx
  char v6; // r12
  PVOID *v7; // rcx
  signed int v8; // ebx
  int v9; // eax
  int v10; // eax
  unsigned int v11; // ebx
  int started; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  unsigned int v16; // eax
  unsigned int v17; // eax
  int v18; // edi
  unsigned int v19; // eax
  int v20; // edi
  PVOID *v21; // rcx
  unsigned int v22; // eax
  __int64 v24; // [rsp+20h] [rbp-59h] BYREF
  __int64 v25; // [rsp+28h] [rbp-51h]
  __int64 v26; // [rsp+30h] [rbp-49h]
  __int64 v27; // [rsp+38h] [rbp-41h] BYREF
  __int64 *v28; // [rsp+40h] [rbp-39h]
  _QWORD *v29; // [rsp+48h] [rbp-31h] BYREF
  _QWORD *v30; // [rsp+50h] [rbp-29h]
  unsigned int v31; // [rsp+58h] [rbp-21h] BYREF
  _QWORD v32[6]; // [rsp+60h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v31 = 0;
  SystemTimeInULL = BdeSvcGetSystemTimeInULL();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_8a3f59d54824346350fe913136af4d55_Traceguids);
  v4 = RpcImpersonateClient(0);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( v4 )
      goto LABEL_7;
    v9 = CheckDeviceForServerKeyRotation();
    v8 = v9;
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2D8,
        (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\fverequesthandler.cpp",
        (const char *)(unsigned int)v9,
        v24);
    EnterCriticalSection(&gBdesvcServerRotationStatusCS);
    v6 = 1;
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          55,
          WPP_8a3f59d54824346350fe913136af4d55_Traceguids,
          (unsigned int)v8);
      FveSetRecoveryPasswordRotationStatus(0xFFFFFFFF);
      FveSetRecoveryPasswordRotationHresult(v8);
LABEL_60:
      LeaveCriticalSection(&gBdesvcServerRotationStatusCS);
      goto LABEL_61;
    }
    v8 = CheckIfRotationRequestSentTooSoon(SystemTimeInULL);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_8a3f59d54824346350fe913136af4d55_Traceguids);
      goto LABEL_60;
    }
    v10 = FveSetRecoveryPasswordRotationStatus(1u);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2F3,
        (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\fverequesthandler.cpp",
        (const char *)(unsigned int)v10,
        v24);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_8a3f59d54824346350fe913136af4d55_Traceguids, v11);
    }
    started = FveSetRecoveryPasswordRotationStartTime(SystemTimeInULL);
    v13 = started;
    if ( started < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2FA,
        (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\fverequesthandler.cpp",
        (const char *)(unsigned int)started,
        v24);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_8a3f59d54824346350fe913136af4d55_Traceguids, v13);
    }
    v14 = FveSetRecoveryPasswordRotationRequestID(a2);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x301,
        (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\fverequesthandler.cpp",
        (const char *)(unsigned int)v14,
        v24);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_8a3f59d54824346350fe913136af4d55_Traceguids, v15);
    }
    v16 = WorkerThreadLauncher((__int64)BdeSvRotateRecoveryPasswordsThread, 0, 7, &v31);
    v8 = v16;
    if ( v16 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_8a3f59d54824346350fe913136af4d55_Traceguids, v16);
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x31A,
          (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\fverequesthandler.cpp",
          (const char *)(unsigned int)v8,
          v24);
      v17 = FveSetRecoveryPasswordRotationStatus(0xFFFFFFFF);
      v18 = v17;
      if ( v17 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_8a3f59d54824346350fe913136af4d55_Traceguids, v17);
        if ( v18 < 0 )
          goto LABEL_60;
      }
      v19 = FveSetRecoveryPasswordRotationHresult(v8);
      v20 = v19;
      if ( v19 )
      {
        v21 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_8a3f59d54824346350fe913136af4d55_Traceguids, v19);
          v21 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v20 < 0 )
          goto LABEL_60;
        goto LABEL_57;
      }
    }
    else
    {
      v8 = 0;
      v27 = 0;
      v24 = 0;
      v25 = 0;
      v26 = 0;
      v30 = &v29;
      v29 = &v29;
      v28 = FVEAPI_OP_RECOVERY_PASSWORD_ROTATION_INITIATED;
      FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v24, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v27);
      FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v24);
    }
    v21 = (PVOID *)WPP_GLOBAL_Control;
LABEL_57:
    if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 8) != 0 )
      WPP_SF_d(v21[2], 63, WPP_8a3f59d54824346350fe913136af4d55_Traceguids, v31);
    goto LABEL_60;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x2D0,
    (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\fverequesthandler.cpp",
    (const char *)(unsigned int)v4,
    v24);
LABEL_7:
  v6 = 0;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_8a3f59d54824346350fe913136af4d55_Traceguids, v5);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  v8 = v5 != 0 ? v5 | 0x80010000 : 0;
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 )
  {
    WPP_SF_d(v7[2], 54, WPP_8a3f59d54824346350fe913136af4d55_Traceguids, (unsigned int)v8);
LABEL_61:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 < 0 )
  {
    v27 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v31 = v8;
    v32[2] = L"hr";
    v32[3] = L"HRESULT";
    v32[4] = &v31;
    v32[5] = 4;
    v32[0] = &v29;
    v32[1] = &v29;
    v29 = v32;
    v30 = v32;
    v28 = FVEAPI_OP_RECOVERY_PASSWORD_ROTATION_INIT_FAILED;
    FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v24, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v27);
    FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v24);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v6 )
    goto LABEL_70;
  v22 = RpcRevertToSelf();
  if ( !v22 )
    goto LABEL_69;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)v8;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_8a3f59d54824346350fe913136af4d55_Traceguids, v22);
LABEL_69:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_70:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
    WPP_SF_d(v7[2], 65, WPP_8a3f59d54824346350fe913136af4d55_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005c000  push    rbp
0x18005c002  push    rbx
0x18005c003  push    rdi
0x18005c004  push    r12
0x18005c006  push    r14
0x18005c008  push    r15
0x18005c00a  lea     rbp, [rsp-2Fh]
0x18005c00f  sub     rsp, 0A8h
0x18005c016  mov     rax, cs:__security_cookie
0x18005c01d  xor     rax, rsp
0x18005c020  mov     [rbp+57h+var_40], rax
0x18005c024  mov     r15, rdx
0x18005c027  mov     [rbp+57h+var_78], 0
0x18005c02e  call    ?BdeSvcGetSystemTimeInULL@@YA_KXZ; BdeSvcGetSystemTimeInULL(void)
0x18005c033  mov     r14, rax
0x18005c036  lea     rax, WPP_GLOBAL_Control
0x18005c03d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c044  cmp     rcx, rax
0x18005c047  jz      short loc_18005C064
0x18005c049  test    byte ptr [rcx+1Ch], 20h
0x18005c04d  jz      short loc_18005C064
0x18005c04f  mov     edx, 34h ; '4'
0x18005c054  lea     r8, WPP_8a3f59d54824346350fe913136af4d55_Traceguids
0x18005c05b  mov     rcx, [rcx+10h]
0x18005c05f  call    WPP_SF_
0x18005c064  xor     ecx, ecx; BindingHandle
0x18005c066  call    cs:__imp_RpcImpersonateClient
0x18005c06d  nop     dword ptr [rax+rax+00h]
0x18005c072  mov     ebx, eax
0x18005c074  mov     rcx, [rbp+5Fh]; this
0x18005c078  test    eax, eax
0x18005c07a  jns     short loc_18005C092
0x18005c07c  mov     r9d, eax; char *
0x18005c07f  lea     r8, aBaseNgscbCorne_0; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x18005c086  mov     edx, 2D0h; void *
0x18005c08b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005c090  jmp     short loc_18005C096
0x18005c092  test    ebx, ebx
0x18005c094  jz      short loc_18005C10E
0x18005c096  xor     r12b, r12b
0x18005c099  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c0a0  lea     r14, WPP_GLOBAL_Control
0x18005c0a7  cmp     rcx, r14
0x18005c0aa  jz      short loc_18005C0D1
0x18005c0ac  test    byte ptr [rcx+1Ch], 2
0x18005c0b0  jz      short loc_18005C0D1
0x18005c0b2  mov     edx, 35h ; '5'
0x18005c0b7  mov     r9d, ebx
0x18005c0ba  lea     r8, WPP_8a3f59d54824346350fe913136af4d55_Traceguids
0x18005c0c1  mov     rcx, [rcx+10h]
0x18005c0c5  call    WPP_SF_d
0x18005c0ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c0d1  mov     eax, ebx
0x18005c0d3  or      eax, 80010000h
0x18005c0d8  neg     ebx
0x18005c0da  sbb     ebx, ebx
0x18005c0dc  and     ebx, eax
0x18005c0de  cmp     rcx, r14
0x18005c0e1  jz      loc_18005C457
0x18005c0e7  test    byte ptr [rcx+1Ch], 40h
0x18005c0eb  jz      loc_18005C457
0x18005c0f1  mov     edx, 36h ; '6'
0x18005c0f6  mov     r9d, ebx
0x18005c0f9  lea     r8, WPP_8a3f59d54824346350fe913136af4d55_Traceguids
0x18005c100  mov     rcx, [rcx+10h]
0x18005c104  call    WPP_SF_d
0x18005c109  jmp     loc_18005C450
0x18005c10e  call    ?CheckDeviceForServerKeyRotation@@YAJXZ; CheckDeviceForServerKeyRotation(void)
0x18005c113  mov     ebx, eax
0x18005c115  mov     rcx, [rbp+5Fh]; this
0x18005c119  lea     rdi, aBaseNgscbCorne_0; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x18005c120  test    eax, eax
0x18005c122  jns     short loc_18005C134
0x18005c124  mov     r9d, eax; char *
0x18005c127  mov     r8, rdi; unsigned int
0x18005c12a  mov     edx, 2D8h; void *
0x18005c12f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005c134  lea     rcx, ?gBdesvcServerRotationStatusCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005c13b  call    cs:__imp_EnterCriticalSection
0x18005c142  nop     dword ptr [rax+rax+00h]
0x18005c147  mov     r12d, 1
0x18005c14d  test    ebx, ebx
0x18005c14f  jns     short loc_18005C196
0x18005c151  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c158  lea     r14, WPP_GLOBAL_Control
0x18005c15f  cmp     rcx, r14
0x18005c162  jz      short loc_18005C182
0x18005c164  test    byte ptr [rcx+1Ch], 2
0x18005c168  jz      short loc_18005C182
0x18005c16a  lea     edx, [r12+36h]
0x18005c16f  mov     r9d, ebx
0x18005c172  lea     r8, WPP_8a3f59d54824346350fe913136af4d55_Traceguids
0x18005c179  mov     rcx, [rcx+10h]
0x18005c17d  call    WPP_SF_d
0x18005c182  or      ecx, 0FFFFFFFFh; unsigned int
0x18005c185  call    ?FveSetRecoveryPasswordRotationStatus@@YAJK@Z; FveSetRecoveryPasswordRotationStatus(ulong)
0x18005c18a  mov     ecx, ebx; int
0x18005c18c  call    ?FveSetRecoveryPasswordRotationHresult@@YAJJ@Z; FveSetRecoveryPasswordRotationHresult(long)
0x18005c191  jmp     loc_18005C43D
0x18005c196  mov     rcx, r14; unsigned __int64
0x18005c199  call    ?CheckIfRotationRequestSentTooSoon@@YAJ_K@Z; CheckIfRotationRequestSentTooSoon(unsigned __int64)
0x18005c19e  mov     ebx, eax
0x18005c1a0  test    eax, eax
0x18005c1a2  jns     short loc_18005C1DF
0x18005c1a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c1ab  lea     r14, WPP_GLOBAL_Control
0x18005c1b2  cmp     rcx, r14
0x18005c1b5  jz      loc_18005C43D
0x18005c1bb  test    byte ptr [rcx+1Ch], 2
0x18005c1bf  jz      loc_18005C43D
0x18005c1c5  mov     edx, 38h ; '8'
0x18005c1ca  lea     r8, WPP_8a3f59d54824346350fe913136af4d55_Traceguids
0x18005c1d1  mov     rcx, [rcx+10h]
0x18005c1d5  call    WPP_SF_
0x18005c1da  jmp     loc_18005C43D
0x18005c1df  mov     ecx, r12d; unsigned int
0x18005c1e2  call    ?FveSetRecoveryPasswordRotationStatus@@YAJK@Z; FveSetRecoveryPasswordRotationStatus(ulong)
0x18005c1e7  mov     ebx, eax
0x18005c1e9  mov     rcx, [rbp+5Fh]; this
0x18005c1ed  test    eax, eax
0x18005c1ef  jns     short loc_18005C232
0x18005c1f1  mov     r9d, eax; char *
0x18005c1f4  mov     r8, rdi; unsigned int
0x18005c1f7  mov     edx, 2F3h; void *
0x18005c1fc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005c201  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c208  lea     rax, WPP_GLOBAL_Control
0x18005c20f  cmp     rcx, rax
0x18005c212  jz      short loc_18005C232
0x18005c214  test    byte ptr [rcx+1Ch], 2
0x18005c218  jz      short loc_18005C232
0x18005c21a  mov     edx, 39h ; '9'
0x18005c21f  mov     r9d, ebx
0x18005c222  lea     r8, WPP_8a3f59d54824346350fe913136af4d55_Traceguids
0x18005c229  mov     rcx, [rcx+10h]
0x18005c22d  call    WPP_SF_d
0x18005c232  mov     rcx, r14; unsigned __int64
0x18005c235  call    ?FveSetRecoveryPasswordRotationStartTime@@YAJ_K@Z; FveSetRecoveryPasswordRotationStartTime(unsigned __int64)
0x18005c23a  mov     ebx, eax
0x18005c23c  mov     rcx, [rbp+5Fh]; this
0x18005c240  test    eax, eax
0x18005c242  jns     short loc_18005C287
0x18005c244  mov     r9d, eax; char *
0x18005c247  mov     r8, rdi; unsigned int
0x18005c24a  mov     edx, 2FAh; void *
0x18005c24f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005c254  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c25b  lea     r14, WPP_GLOBAL_Control
0x18005c262  cmp     rcx, r14
0x18005c265  jz      short loc_18005C28E
0x18005c267  test    byte ptr [rcx+1Ch], 2
0x18005c26b  jz      short loc_18005C28E
0x18005c26d  mov     edx, 3Ah ; ':'
0x18005c272  mov     r9d, ebx
0x18005c275  lea     r8, WPP_8a3f59d54824346350fe913136af4d55_Traceguids
0x18005c27c  mov     rcx, [rcx+10h]
0x18005c280  call    WPP_SF_d
0x18005c285  jmp     short loc_18005C28E
0x18005c287  lea     r14, WPP_GLOBAL_Control
0x18005c28e  mov     rcx, r15; unsigned __int16 *
0x18005c291  call    ?FveSetRecoveryPasswordRotationRequestID@@YAJPEBG@Z; FveSetRecoveryPasswordRotationRequestID(ushort const *)
0x18005c296  mov     ebx, eax
0x18005c298  mov     rcx, [rbp+5Fh]; this
0x18005c29c  test    eax, eax
0x18005c29e  jns     short loc_18005C2DA
0x18005c2a0  mov     r9d, eax; char *
0x18005c2a3  mov     r8, rdi; unsigned int
0x18005c2a6  mov     edx, 301h; void *
0x18005c2ab  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005c2b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c2b7  cmp     rcx, r14
0x18005c2ba  jz      short loc_18005C2DA
0x18005c2bc  test    byte ptr [rcx+1Ch], 2
0x18005c2c0  jz      short loc_18005C2DA
0x18005c2c2  mov     edx, 3Bh ; ';'
0x18005c2c7  mov     r9d, ebx
0x18005c2ca  lea     r8, WPP_8a3f59d54824346350fe913136af4d55_Traceguids
0x18005c2d1  mov     rcx, [rcx+10h]
0x18005c2d5  call    WPP_SF_d
0x18005c2da  lea     r9, [rbp+57h+var_78]
0x18005c2de  xor     edx, edx
0x18005c2e0  lea     r8d, [rdx+7]
0x18005c2e4  lea     rcx, ?BdeSvRotateRecoveryPasswordsThread@@YAIPEAX@Z; BdeSvRotateRecoveryPasswordsThread(void *)
0x18005c2eb  call    ?WorkerThreadLauncher@@YAKP6AIPEAX@Z0W4WorkerThreadFlags@@PEAK@Z; WorkerThreadLauncher(uint (*)(void *),void *,WorkerThreadFlags,ulong *)
0x18005c2f0  mov     ebx, eax
0x18005c2f2  test    eax, eax
0x18005c2f4  jz      loc_18005C3CD
0x18005c2fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c301  cmp     rcx, r14
0x18005c304  jz      short loc_18005C324
0x18005c306  test    byte ptr [rcx+1Ch], 2
0x18005c30a  jz      short loc_18005C324
0x18005c30c  mov     edx, 3Ch ; '<'
0x18005c311  mov     r9d, eax
0x18005c314  lea     r8, WPP_8a3f59d54824346350fe913136af4d55_Traceguids
0x18005c31b  mov     rcx, [rcx+10h]
0x18005c31f  call    WPP_SF_d
0x18005c324  test    ebx, ebx
0x18005c326  jle     short loc_18005C331
0x18005c328  movzx   ebx, bx
0x18005c32b  or      ebx, 80070000h
0x18005c331  mov     rcx, [rbp+5Fh]; this
0x18005c335  test    ebx, ebx
0x18005c337  jns     short loc_18005C349
0x18005c339  mov     r9d, ebx; char *
0x18005c33c  mov     r8, rdi; unsigned int
0x18005c33f  mov     edx, 31Ah; void *
0x18005c344  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005c349  or      ecx, 0FFFFFFFFh; unsigned int
0x18005c34c  call    ?FveSetRecoveryPasswordRotationStatus@@YAJK@Z; FveSetRecoveryPasswordRotationStatus(ulong)
0x18005c351  mov     edi, eax
0x18005c353  test    eax, eax
0x18005c355  jz      short loc_18005C389
0x18005c357  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c35e  cmp     rcx, r14
0x18005c361  jz      short loc_18005C381
0x18005c363  test    byte ptr [rcx+1Ch], 40h
0x18005c367  jz      short loc_18005C381
0x18005c369  mov     edx, 3Dh ; '='
0x18005c36e  mov     r9d, eax
0x18005c371  lea     r8, WPP_8a3f59d54824346350fe913136af4d55_Traceguids
0x18005c378  mov     rcx, [rcx+10h]
0x18005c37c  call    WPP_SF_d
0x18005c381  test    edi, edi
0x18005c383  js      loc_18005C43D
0x18005c389  mov     ecx, ebx; int
0x18005c38b  call    ?FveSetRecoveryPasswordRotationHresult@@YAJJ@Z; FveSetRecoveryPasswordRotationHresult(long)
0x18005c390  mov     edi, eax
0x18005c392  test    eax, eax
0x18005c394  jz      short loc_18005C412
0x18005c396  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c39d  cmp     rcx, r14
0x18005c3a0  jz      short loc_18005C3C7
0x18005c3a2  test    byte ptr [rcx+1Ch], 40h
0x18005c3a6  jz      short loc_18005C3C7
0x18005c3a8  mov     edx, 3Eh ; '>'
0x18005c3ad  mov     r9d, eax
0x18005c3b0  lea     r8, WPP_8a3f59d54824346350fe913136af4d55_Traceguids
0x18005c3b7  mov     rcx, [rcx+10h]
0x18005c3bb  call    WPP_SF_d
0x18005c3c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c3c7  test    edi, edi
0x18005c3c9  js      short loc_18005C43D
0x18005c3cb  jmp     short loc_18005C419
0x18005c3cd  xor     ebx, ebx
0x18005c3cf  mov     [rbp+57h+var_98], rbx
0x18005c3d3  mov     [rbp+57h+var_B0], rbx
0x18005c3d7  mov     [rbp+57h+var_A8], rbx
0x18005c3db  mov     [rbp+57h+var_A0], rbx
0x18005c3df  lea     rax, [rbp+57h+var_88]
0x18005c3e3  mov     [rbp+57h+var_80], rax
0x18005c3e7  lea     rax, [rbp+57h+var_88]
0x18005c3eb  mov     [rbp+57h+var_88], rax
0x18005c3ef  lea     rax, FVEAPI_OP_RECOVERY_PASSWORD_ROTATION_INITIATED
0x18005c3f6  mov     [rbp+57h+var_90], rax
0x18005c3fa  lea     rdx, [rbp+57h+var_98]; struct _FVEAPI_EVENT_DATA_COLLECTION *
0x18005c3fe  lea     rcx, [rbp+57h+var_B0]; this
0x18005c402  call    ?LogFveApiEvent@FveEventLogHandle@@QEAAJPEAU_FVEAPI_EVENT_DATA_COLLECTION@@@Z; FveEventLogHandle::LogFveApiEvent(_FVEAPI_EVENT_DATA_COLLECTION *)
0x18005c407  nop
0x18005c408  lea     rcx, [rbp+57h+var_B0]; this
0x18005c40c  call    ?EventLogCleanup@FveEventLogHandle@@AEAAXXZ; FveEventLogHandle::EventLogCleanup(void)
0x18005c411  nop
0x18005c412  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c419  cmp     rcx, r14
0x18005c41c  jz      short loc_18005C43D
0x18005c41e  test    byte ptr [rcx+1Ch], 8
0x18005c422  jz      short loc_18005C43D
0x18005c424  mov     edx, 3Fh ; '?'
0x18005c429  mov     r9d, [rbp+57h+var_78]
0x18005c42d  lea     r8, WPP_8a3f59d54824346350fe913136af4d55_Traceguids
0x18005c434  mov     rcx, [rcx+10h]
0x18005c438  call    WPP_SF_d
0x18005c43d  lea     rcx, ?gBdesvcServerRotationStatusCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005c444  call    cs:__imp_LeaveCriticalSection
0x18005c44b  nop     dword ptr [rax+rax+00h]
0x18005c450  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c457  test    ebx, ebx
0x18005c459  jns     loc_18005C4F2
0x18005c45f  mov     [rbp+57h+var_98], 0
0x18005c467  mov     [rbp+57h+var_B0], 0
0x18005c46f  mov     [rbp+57h+var_A8], 0
0x18005c477  mov     [rbp+57h+var_A0], 0
0x18005c47f  mov     [rbp+57h+var_78], ebx
0x18005c482  lea     rax, aHr; "hr"
0x18005c489  lea     rcx, aHresult; "HRESULT"
0x18005c490  lea     rdx, [rbp+57h+var_78]
0x18005c494  mov     [rbp+57h+var_60], rax
0x18005c498  mov     [rbp+57h+var_58], rcx
0x18005c49c  mov     [rbp+57h+var_50], rdx
0x18005c4a0  mov     [rbp+57h+var_48], 4
0x18005c4a8  lea     rax, [rbp+57h+var_88]
0x18005c4ac  mov     [rbp+57h+var_70], rax
0x18005c4b0  lea     rax, [rbp+57h+var_88]
0x18005c4b4  mov     [rbp+57h+var_68], rax
0x18005c4b8  lea     rax, [rbp+57h+var_70]
0x18005c4bc  mov     [rbp+57h+var_88], rax
0x18005c4c0  lea     rax, [rbp+57h+var_70]
0x18005c4c4  mov     [rbp+57h+var_80], rax
0x18005c4c8  lea     rax, FVEAPI_OP_RECOVERY_PASSWORD_ROTATION_INIT_FAILED
0x18005c4cf  mov     [rbp+57h+var_90], rax
  ... truncated ...
```
