# FveEnableEAS::IsConnectedUser(bool *)

- ea: `0x180078eec`
- end: `0x1800791d6`
- name: `?IsConnectedUser@FveEnableEAS@@IEAAJPEA_N@Z`
- size: `746`
- prototype: `int(FveEnableEAS *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180078390`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18001a508`
- `0x180022008`
- `0x18002b6ac`
- `0x18006fa9c`
- `0x180070c48`
- `0x180078eec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079064`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079064`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007903f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007903f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180079054`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180079054`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180079022`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180079022`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180079005`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180079005`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180079181`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180079181`

## string_xrefs

- `0x1800790f3`: `GetFullToken`
- `0x180078fd3`: `InitializeCOM`
- `0x1800790a9`: `OpenProcessToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FveEnableEAS::IsConnectedUser(FveEnableEAS *this, bool *a2)
{
  PVOID *v3; // rcx
  signed int v4; // ebx
  unsigned int v5; // eax
  const char *v6; // rax
  __int64 v7; // rdx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int FullToken; // eax
  unsigned int v12; // eax
  PVOID *v13; // rcx
  const char *v15; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  FveEnableEAS *v17; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF
  __int64 v19; // [rsp+70h] [rbp+40h] BYREF

  v17 = this;
  TokenHandle = 0;
  v19 = 0;
  LOBYTE(v17) = 0;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    v4 = -2147467261;
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x40) != 0 )
      WPP_SF_d(v3[2], 98, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, 2147500035LL);
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x49D,
      (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
      (const char *)0x80004003LL,
      (int)"IsMSAUsernullptr",
      v15);
    goto LABEL_40;
  }
  v5 = FveBackupMonitor::InitializeCOM((bool *)&v17);
  v4 = v5;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v5);
  if ( v4 < 0 )
  {
    v6 = "InitializeCOM";
    v7 = 1184;
LABEL_14:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v7,
      (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
      (const char *)(unsigned int)v4,
      (int)v6,
      v15);
LABEL_37:
    v13 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_38;
  }
  SH<void *,SH_HANDLE>::Reset(&TokenHandle);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Au, 0, &TokenHandle) )
  {
    SH<void *,SH_HANDLE>::Reset(&TokenHandle);
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x2000Au, &TokenHandle) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          100,
          &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
          (unsigned int)v4);
      if ( v4 < 0 )
      {
        v6 = "OpenProcessToken";
        v7 = 1195;
        goto LABEL_14;
      }
    }
  }
  FullToken = CNgscbToken::GetFullToken((CNgscbToken *)&TokenHandle, (struct CNgscbToken *)&v19);
  v4 = FullToken;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, FullToken);
  if ( v4 < 0 )
  {
    v6 = "GetFullToken";
    v7 = 1199;
    goto LABEL_14;
  }
  v12 = FveBackupMonitor::CheckIsConnectedUser((const struct CNgscbToken *)&v19, a2);
  v4 = v12;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v12);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 < 0 )
  {
    v6 = "CheckIsConnectedUser";
    v7 = 1200;
    goto LABEL_14;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
  {
    WPP_SF_d(v13[2], 103, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, *a2);
    goto LABEL_37;
  }
LABEL_38:
  if ( (_BYTE)v17 )
  {
    CoUninitialize();
LABEL_40:
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x20) != 0 )
    WPP_SF_d(v13[2], 104, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, (unsigned int)v4);
  SH<void *,SH_HANDLE>::Reset(&v19);
  SH<void *,SH_HANDLE>::Reset(&TokenHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180078eec  mov     [rsp-28h+arg_0], rcx
0x180078ef1  push    rbp
0x180078ef2  push    rbx
0x180078ef3  push    rsi
0x180078ef4  push    r12
0x180078ef6  push    r15
0x180078ef8  mov     rbp, rsp
0x180078efb  sub     rsp, 30h
0x180078eff  mov     rsi, rdx
0x180078f02  mov     [rbp+TokenHandle], 0
0x180078f0a  mov     [rbp+arg_10], 0
0x180078f12  mov     byte ptr [rbp+arg_0], 0
0x180078f16  lea     r15, WPP_GLOBAL_Control
0x180078f1d  lea     r12, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180078f24  mov     rcx, cs:WPP_GLOBAL_Control
0x180078f2b  cmp     rcx, r15
0x180078f2e  jz      short loc_180078F4E
0x180078f30  test    byte ptr [rcx+1Ch], 20h
0x180078f34  jz      short loc_180078F4E
0x180078f36  mov     edx, 61h ; 'a'
0x180078f3b  mov     r8, r12
0x180078f3e  mov     rcx, [rcx+10h]
0x180078f42  call    WPP_SF_
0x180078f47  mov     rcx, cs:WPP_GLOBAL_Control
0x180078f4e  test    rsi, rsi
0x180078f51  jnz     short loc_180078F9E
0x180078f53  mov     ebx, 80004003h
0x180078f58  cmp     rcx, r15
0x180078f5b  jz      short loc_180078F75
0x180078f5d  test    byte ptr [rcx+1Ch], 40h
0x180078f61  jz      short loc_180078F75
0x180078f63  lea     edx, [rsi+62h]
0x180078f66  mov     r9d, ebx
0x180078f69  mov     r8, r12
0x180078f6c  mov     rcx, [rcx+10h]
0x180078f70  call    WPP_SF_d
0x180078f75  mov     rcx, [rbp+28h]; this
0x180078f79  lea     rax, aIsmsausernullp; "IsMSAUsernullptr"
0x180078f80  mov     qword ptr [rsp+30h+var_10], rax; int
0x180078f85  mov     r9d, ebx; char *
0x180078f88  lea     r8, aBaseNgscbCorne_2; "base\\ngscb\\cornerstone\\fveeas\\fveen"...
0x180078f8f  mov     edx, 49Dh; void *
0x180078f94  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180078f99  jmp     loc_18007918D
0x180078f9e  lea     rcx, [rbp+arg_0]; bool *
0x180078fa2  call    ?InitializeCOM@FveBackupMonitor@@SAJPEA_N@Z; FveBackupMonitor::InitializeCOM(bool *)
0x180078fa7  mov     ebx, eax
0x180078fa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180078fb0  cmp     rcx, r15
0x180078fb3  jz      short loc_180078FCF
0x180078fb5  test    byte ptr [rcx+1Ch], 40h
0x180078fb9  jz      short loc_180078FCF
0x180078fbb  mov     edx, 63h ; 'c'
0x180078fc0  mov     r9d, eax
0x180078fc3  mov     r8, r12
0x180078fc6  mov     rcx, [rcx+10h]
0x180078fca  call    WPP_SF_d
0x180078fcf  test    ebx, ebx
0x180078fd1  jns     short loc_180078FFC
0x180078fd3  lea     rax, aInitializecom; "InitializeCOM"
0x180078fda  mov     edx, 4A0h; void *
0x180078fdf  lea     r8, aBaseNgscbCorne_2; "base\\ngscb\\cornerstone\\fveeas\\fveen"...
0x180078fe6  mov     r9d, ebx; char *
0x180078fe9  mov     qword ptr [rsp+30h+var_10], rax; int
0x180078fee  mov     rcx, [rbp+28h]; this
0x180078ff2  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180078ff7  jmp     loc_180079174
0x180078ffc  lea     rcx, [rbp+TokenHandle]
0x180079000  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180079005  call    cs:__imp_GetCurrentThread
0x18007900c  nop     dword ptr [rax+rax+00h]
0x180079011  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180079015  xor     r8d, r8d; OpenAsSelf
0x180079018  mov     ebx, 2000Ah
0x18007901d  mov     edx, ebx; DesiredAccess
0x18007901f  mov     rcx, rax; ThreadHandle
0x180079022  call    cs:__imp_OpenThreadToken
0x180079029  nop     dword ptr [rax+rax+00h]
0x18007902e  test    eax, eax
0x180079030  jnz     loc_1800790BA
0x180079036  lea     rcx, [rbp+TokenHandle]
0x18007903a  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18007903f  call    cs:__imp_GetCurrentProcess
0x180079046  nop     dword ptr [rax+rax+00h]
0x18007904b  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18007904f  mov     edx, ebx; DesiredAccess
0x180079051  mov     rcx, rax; ProcessHandle
0x180079054  call    cs:__imp_OpenProcessToken
0x18007905b  nop     dword ptr [rax+rax+00h]
0x180079060  test    eax, eax
0x180079062  jnz     short loc_1800790BA
0x180079064  call    cs:__imp_GetLastError
0x18007906b  nop     dword ptr [rax+rax+00h]
0x180079070  mov     ebx, eax
0x180079072  test    eax, eax
0x180079074  jle     short loc_18007907F
0x180079076  movzx   ebx, ax
0x180079079  or      ebx, 80070000h
0x18007907f  mov     rcx, cs:WPP_GLOBAL_Control
0x180079086  cmp     rcx, r15
0x180079089  jz      short loc_1800790A5
0x18007908b  test    byte ptr [rcx+1Ch], 40h
0x18007908f  jz      short loc_1800790A5
0x180079091  mov     edx, 64h ; 'd'
0x180079096  mov     r9d, ebx
0x180079099  mov     r8, r12
0x18007909c  mov     rcx, [rcx+10h]
0x1800790a0  call    WPP_SF_d
0x1800790a5  test    ebx, ebx
0x1800790a7  jns     short loc_1800790BA
0x1800790a9  lea     rax, aOpenprocesstok; "OpenProcessToken"
0x1800790b0  mov     edx, 4ABh
0x1800790b5  jmp     loc_180078FDF
0x1800790ba  lea     rdx, [rbp+arg_10]; struct CNgscbToken *
0x1800790be  lea     rcx, [rbp+TokenHandle]; this
0x1800790c2  call    ?GetFullToken@CNgscbToken@@QEBAJAEAV1@@Z; CNgscbToken::GetFullToken(CNgscbToken &)
0x1800790c7  mov     ebx, eax
0x1800790c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800790d0  cmp     rcx, r15
0x1800790d3  jz      short loc_1800790EF
0x1800790d5  test    byte ptr [rcx+1Ch], 40h
0x1800790d9  jz      short loc_1800790EF
0x1800790db  mov     edx, 65h ; 'e'
0x1800790e0  mov     r9d, eax
0x1800790e3  mov     r8, r12
0x1800790e6  mov     rcx, [rcx+10h]
0x1800790ea  call    WPP_SF_d
0x1800790ef  test    ebx, ebx
0x1800790f1  jns     short loc_180079104
0x1800790f3  lea     rax, aGetfulltoken; "GetFullToken"
0x1800790fa  mov     edx, 4AFh
0x1800790ff  jmp     loc_180078FDF
0x180079104  mov     rdx, rsi; bool *
0x180079107  lea     rcx, [rbp+arg_10]; struct CNgscbToken *
0x18007910b  call    ?CheckIsConnectedUser@FveBackupMonitor@@SAJPEBVCNgscbToken@@PEA_N@Z; FveBackupMonitor::CheckIsConnectedUser(CNgscbToken const *,bool *)
0x180079110  mov     ebx, eax
0x180079112  mov     rcx, cs:WPP_GLOBAL_Control
0x180079119  cmp     rcx, r15
0x18007911c  jz      short loc_18007913F
0x18007911e  test    byte ptr [rcx+1Ch], 40h
0x180079122  jz      short loc_18007913F
0x180079124  mov     edx, 66h ; 'f'
0x180079129  mov     r9d, eax
0x18007912c  mov     r8, r12
0x18007912f  mov     rcx, [rcx+10h]
0x180079133  call    WPP_SF_d
0x180079138  mov     rcx, cs:WPP_GLOBAL_Control
0x18007913f  test    ebx, ebx
0x180079141  jns     short loc_180079154
0x180079143  lea     rax, aCheckisconnect; "CheckIsConnectedUser"
0x18007914a  mov     edx, 4B0h
0x18007914f  jmp     loc_180078FDF
0x180079154  cmp     rcx, r15
0x180079157  jz      short loc_18007917B
0x180079159  test    byte ptr [rcx+1Ch], 8
0x18007915d  jz      short loc_18007917B
0x18007915f  movzx   r9d, byte ptr [rsi]
0x180079163  mov     edx, 67h ; 'g'
0x180079168  mov     r8, r12
0x18007916b  mov     rcx, [rcx+10h]
0x18007916f  call    WPP_SF_d
0x180079174  mov     rcx, cs:WPP_GLOBAL_Control
0x18007917b  cmp     byte ptr [rbp+arg_0], 0
0x18007917f  jz      short loc_180079194
0x180079181  call    cs:__imp_CoUninitialize
0x180079188  nop     dword ptr [rax+rax+00h]
0x18007918d  mov     rcx, cs:WPP_GLOBAL_Control
0x180079194  cmp     rcx, r15
0x180079197  jz      short loc_1800791B4
0x180079199  test    byte ptr [rcx+1Ch], 20h
0x18007919d  jz      short loc_1800791B4
0x18007919f  mov     edx, 68h ; 'h'
0x1800791a4  mov     r9d, ebx
0x1800791a7  mov     r8, r12
0x1800791aa  mov     rcx, [rcx+10h]
0x1800791ae  call    WPP_SF_d
0x1800791b3  nop
0x1800791b4  lea     rcx, [rbp+arg_10]
0x1800791b8  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x1800791bd  nop
0x1800791be  lea     rcx, [rbp+TokenHandle]
0x1800791c2  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x1800791c7  mov     eax, ebx
0x1800791c9  add     rsp, 30h
0x1800791cd  pop     r15
0x1800791cf  pop     r12
0x1800791d1  pop     rsi
0x1800791d2  pop     rbx
0x1800791d3  pop     rbp
0x1800791d4  retn
```
