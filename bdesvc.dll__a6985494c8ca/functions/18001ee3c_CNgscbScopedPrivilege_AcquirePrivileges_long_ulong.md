# CNgscbScopedPrivilege::AcquirePrivileges(long *,ulong)

- ea: `0x18001ee3c`
- end: `0x18001f22e`
- name: `?AcquirePrivileges@CNgscbScopedPrivilege@@QEAAJPEAJK@Z`
- size: `1010`
- prototype: `__int64 __fastcall(CNgscbScopedPrivilege *this, int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000dde0`
- `0x18001e900`
- `0x180040fac`

## callees

- `0x180009f60`
- `0x18001ee3c`
- `0x18002e628`
- `0x180030c74`
- `0x180030db0`
- `0x180030f60`
- `0x1800310b8`
- `0x180034070`
- `0x180034d28`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f038`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f038`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f024`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f154`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ef9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ef9b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001efb1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001efb1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ef6e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ef6e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f1e1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f1e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ef53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ef53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001effe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f013`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001effe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f013`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001f124`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001f124`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001f0c8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001f0c8`

## string_xrefs

- `0x18001f19f`: `ngscb_common_um`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNgscbScopedPrivilege::AcquirePrivileges(CNgscbScopedPrivilege *this, int *a2)
{
  PTOKEN_PRIVILEGES v4; // r12
  int v5; // edi
  void *v6; // rax
  unsigned int v7; // eax
  int v8; // ebx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  unsigned int KnownLastErrorHR; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  HANDLE ProcessHeap; // rax
  void *v16; // rcx
  unsigned int v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  DWORD LastError; // eax
  DWORD v21; // ebx
  __int64 v22; // rax
  void *v23; // [rsp+30h] [rbp-49h]
  PTOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-41h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-39h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-29h] BYREF

  TokenHandle = 0;
  v4 = 0;
  hObject = 0;
  v23 = 0;
  NewState = 0;
  if ( !*((_BYTE *)this + 8) )
  {
    NgscbTryOpenEventLog();
    v7 = HeapAllocateByByteCount<_TOKEN_PRIVILEGES>(&NewState);
    v5 = v7;
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 341, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v7);
      if ( v5 < 0 )
      {
        v4 = NewState;
        goto LABEL_36;
      }
    }
    v4 = NewState;
    NewState->PrivilegeCount = 1;
    v4->Privileges[0].Attributes = 2;
    LODWORD(NewState) = *a2;
    NewState = (PTOKEN_PRIVILEGES)(int)NewState;
    v4->Privileges[0].Luid = (LUID)(int)NewState;
    v8 = *((_DWORD *)this + 3);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 6u, v8, &TokenHandle) )
    {
      v16 = TokenHandle;
      v23 = TokenHandle;
    }
    else
    {
      if ( GetLastError() != 1008 )
      {
        KnownLastErrorHR = NgscbGetKnownLastErrorHR();
        v5 = KnownLastErrorHR;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_18;
        v13 = 343;
        goto LABEL_17;
      }
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 2u, &TokenHandle) )
      {
        KnownLastErrorHR = NgscbGetKnownLastErrorHR();
        v5 = KnownLastErrorHR;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_18;
        v13 = 342;
LABEL_17:
        WPP_SF_d(v12[2], v13, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, KnownLastErrorHR);
LABEL_18:
        v6 = 0;
        goto LABEL_19;
      }
      v16 = TokenHandle;
    }
    if ( DuplicateTokenEx(v16, 0x2Cu, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
    {
      if ( AdjustTokenPrivileges(hObject, 0, v4, 0, 0, 0) )
      {
        LastError = GetLastError();
        v21 = LastError;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 346, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, LastError);
        if ( v21 == 1300 )
        {
          memset_0(&UserData.Size, 0, 0x48u);
          v22 = -1;
          UserData.Ptr = (ULONGLONG)aNgscbCommonUm;
          do
            ++v22;
          while ( aNgscbCommonUm[v22] );
          UserData.Reserved = 0;
          UserData.Size = 2 * v22 + 2;
          NgscbTryWriteEventLog(&FVE_NOT_ALL_TOKEN_PRIVILEGES_ASSIGNED, 1u, &UserData);
        }
        if ( SetThreadToken(0, hObject) )
        {
          v6 = v23;
          *(_QWORD *)this = v23;
          *((_BYTE *)this + 8) = 1;
          goto LABEL_19;
        }
        v17 = NgscbGetKnownLastErrorHR();
        v5 = v17;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_36;
        v19 = 347;
      }
      else
      {
        v17 = NgscbGetKnownLastErrorHR();
        v5 = v17;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_36;
        v19 = 345;
      }
    }
    else
    {
      v17 = NgscbGetKnownLastErrorHR();
      v5 = v17;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_36;
      v19 = 344;
    }
    WPP_SF_d(v18[2], v19, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v17);
LABEL_36:
    v6 = v23;
    goto LABEL_19;
  }
  v5 = -2147024809;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
    goto LABEL_25;
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 340, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, 2147942487LL);
  v6 = 0;
LABEL_19:
  if ( TokenHandle != v6 )
    CloseHandle(TokenHandle);
  if ( hObject )
    CloseHandle(hObject);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
LABEL_25:
  NgscbTryCloseEventLog();
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001ee3c  mov     [rsp-8+arg_8], rbx
0x18001ee41  mov     [rsp-8+arg_10], rsi
0x18001ee46  push    rbp
0x18001ee47  push    rdi
0x18001ee48  push    r12
0x18001ee4a  push    r13
0x18001ee4c  push    r15
0x18001ee4e  lea     rbp, [rsp-37h]
0x18001ee53  sub     rsp, 0B0h
0x18001ee5a  mov     rax, cs:__security_cookie
0x18001ee61  xor     rax, rsp
0x18001ee64  mov     [rbp+57h+var_30], rax
0x18001ee68  xor     esi, esi
0x18001ee6a  mov     rbx, rdx
0x18001ee6d  mov     r13, rcx
0x18001ee70  mov     [rbp+57h+TokenHandle], rsi
0x18001ee74  mov     r12d, esi
0x18001ee77  mov     [rbp+57h+hObject], rsi
0x18001ee7b  mov     [rbp+57h+var_A0], rsi
0x18001ee7f  mov     [rbp+57h+NewState], rsi
0x18001ee83  cmp     [rcx+8], sil
0x18001ee87  jz      short loc_18001EECF
0x18001ee89  mov     edi, 80070057h
0x18001ee8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee95  lea     rsi, WPP_GLOBAL_Control
0x18001ee9c  cmp     rcx, rsi
0x18001ee9f  jz      loc_18001F044
0x18001eea5  test    byte ptr [rcx+1Ch], 40h
0x18001eea9  jz      loc_18001F044
0x18001eeaf  mov     rcx, [rcx+10h]
0x18001eeb3  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x18001eeba  mov     edx, 154h
0x18001eebf  mov     r9d, edi
0x18001eec2  call    WPP_SF_d
0x18001eec7  mov     eax, r12d
0x18001eeca  jmp     loc_18001EFF5
0x18001eecf  call    ?NgscbTryOpenEventLog@@YAXXZ; NgscbTryOpenEventLog(void)
0x18001eed4  lea     rcx, [rbp+57h+NewState]
0x18001eed8  call    ??$HeapAllocateByByteCount@U_TOKEN_PRIVILEGES@@@@YAJPEAPEAU_TOKEN_PRIVILEGES@@_K@Z; HeapAllocateByByteCount<_TOKEN_PRIVILEGES>(_TOKEN_PRIVILEGES * *,unsigned __int64)
0x18001eedd  lea     rsi, WPP_GLOBAL_Control
0x18001eee4  mov     edi, eax
0x18001eee6  lea     r15, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x18001eeed  test    eax, eax
0x18001eeef  jz      short loc_18001EF24
0x18001eef1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eef8  cmp     rcx, rsi
0x18001eefb  jz      short loc_18001EF17
0x18001eefd  test    byte ptr [rcx+1Ch], 40h
0x18001ef01  jz      short loc_18001EF17
0x18001ef03  mov     rcx, [rcx+10h]
0x18001ef07  mov     edx, 155h
0x18001ef0c  mov     r9d, eax
0x18001ef0f  mov     r8, r15
0x18001ef12  call    WPP_SF_d
0x18001ef17  test    edi, edi
0x18001ef19  jns     short loc_18001EF24
0x18001ef1b  mov     r12, [rbp+57h+NewState]
0x18001ef1f  jmp     loc_18001F105
0x18001ef24  mov     r12, [rbp+57h+NewState]
0x18001ef28  mov     dword ptr [r12], 1
0x18001ef30  mov     dword ptr [r12+0Ch], 2
0x18001ef39  movsxd  rax, dword ptr [rbx]
0x18001ef3c  mov     dword ptr [rbp+57h+NewState], eax
0x18001ef3f  shr     rax, 20h
0x18001ef43  mov     dword ptr [rbp+57h+NewState+4], eax
0x18001ef46  mov     rax, [rbp+57h+NewState]
0x18001ef4a  mov     [r12+4], rax
0x18001ef4f  mov     ebx, [r13+0Ch]
0x18001ef53  call    cs:__imp_GetCurrentThread
0x18001ef5a  nop     dword ptr [rax+rax+00h]
0x18001ef5f  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001ef63  mov     r8d, ebx; OpenAsSelf
0x18001ef66  mov     rcx, rax; ThreadHandle
0x18001ef69  mov     edx, 6; DesiredAccess
0x18001ef6e  call    cs:__imp_OpenThreadToken
0x18001ef75  nop     dword ptr [rax+rax+00h]
0x18001ef7a  xor     ebx, ebx
0x18001ef7c  test    eax, eax
0x18001ef7e  jnz     loc_18001F0A5
0x18001ef84  call    cs:__imp_GetLastError
0x18001ef8b  nop     dword ptr [rax+rax+00h]
0x18001ef90  cmp     eax, 3F0h
0x18001ef95  jnz     loc_18001F07A
0x18001ef9b  call    cs:__imp_GetCurrentProcess
0x18001efa2  nop     dword ptr [rax+rax+00h]
0x18001efa7  mov     rcx, rax; ProcessHandle
0x18001efaa  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18001efae  lea     edx, [rbx+2]; DesiredAccess
0x18001efb1  call    cs:__imp_OpenProcessToken
0x18001efb8  nop     dword ptr [rax+rax+00h]
0x18001efbd  test    eax, eax
0x18001efbf  jnz     loc_18001F074
0x18001efc5  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x18001efca  mov     edi, eax
0x18001efcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001efd3  cmp     rcx, rsi
0x18001efd6  jz      short loc_18001EFF2
0x18001efd8  test    byte ptr [rcx+1Ch], 40h
0x18001efdc  jz      short loc_18001EFF2
0x18001efde  mov     edx, 156h
0x18001efe3  mov     rcx, [rcx+10h]
0x18001efe7  mov     r9d, eax
0x18001efea  mov     r8, r15
0x18001efed  call    WPP_SF_d
0x18001eff2  mov     rax, rbx
0x18001eff5  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18001eff9  cmp     rcx, rax
0x18001effc  jz      short loc_18001F00A
0x18001effe  call    cs:__imp_CloseHandle
0x18001f005  nop     dword ptr [rax+rax+00h]
0x18001f00a  mov     rcx, [rbp+57h+hObject]; hObject
0x18001f00e  test    rcx, rcx
0x18001f011  jz      short loc_18001F01F
0x18001f013  call    cs:__imp_CloseHandle
0x18001f01a  nop     dword ptr [rax+rax+00h]
0x18001f01f  test    r12, r12
0x18001f022  jz      short loc_18001F044
0x18001f024  call    cs:__imp_GetProcessHeap
0x18001f02b  nop     dword ptr [rax+rax+00h]
0x18001f030  mov     r8, r12; lpMem
0x18001f033  xor     edx, edx; dwFlags
0x18001f035  mov     rcx, rax; hHeap
0x18001f038  call    cs:__imp_HeapFree
0x18001f03f  nop     dword ptr [rax+rax+00h]
0x18001f044  call    ?NgscbTryCloseEventLog@@YAXXZ; NgscbTryCloseEventLog(void)
0x18001f049  mov     eax, edi
0x18001f04b  mov     rcx, [rbp+57h+var_30]
0x18001f04f  xor     rcx, rsp; StackCookie
0x18001f052  call    __security_check_cookie
0x18001f057  lea     r11, [rsp+0D0h+var_20]
0x18001f05f  mov     rbx, [r11+38h]
0x18001f063  mov     rsi, [r11+40h]
0x18001f067  mov     rsp, r11
0x18001f06a  pop     r15
0x18001f06c  pop     r13
0x18001f06e  pop     r12
0x18001f070  pop     rdi
0x18001f071  pop     rbp
0x18001f072  retn
0x18001f074  mov     rcx, [rbp+57h+TokenHandle]
0x18001f078  jmp     short loc_18001F0AD
0x18001f07a  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x18001f07f  mov     edi, eax
0x18001f081  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f088  cmp     rcx, rsi
0x18001f08b  jz      loc_18001EFF2
0x18001f091  test    byte ptr [rcx+1Ch], 40h
0x18001f095  jz      loc_18001EFF2
0x18001f09b  mov     edx, 157h
0x18001f0a0  jmp     loc_18001EFE3
0x18001f0a5  mov     rcx, [rbp+57h+TokenHandle]; hExistingToken
0x18001f0a9  mov     [rbp+57h+var_A0], rcx
0x18001f0ad  lea     rax, [rbp+57h+hObject]
0x18001f0b1  xor     r8d, r8d; lpTokenAttributes
0x18001f0b4  mov     [rsp+0D0h+phNewToken], rax; phNewToken
0x18001f0b9  mov     eax, 2
0x18001f0be  mov     r9d, eax; ImpersonationLevel
0x18001f0c1  mov     [rsp+0D0h+TokenType], eax; TokenType
0x18001f0c5  lea     edx, [rax+2Ah]; dwDesiredAccess
0x18001f0c8  call    cs:__imp_DuplicateTokenEx
0x18001f0cf  nop     dword ptr [rax+rax+00h]
0x18001f0d4  test    eax, eax
0x18001f0d6  jnz     short loc_18001F10E
0x18001f0d8  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x18001f0dd  mov     edi, eax
0x18001f0df  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f0e6  cmp     rcx, rsi
0x18001f0e9  jz      short loc_18001F105
0x18001f0eb  test    byte ptr [rcx+1Ch], 40h
0x18001f0ef  jz      short loc_18001F105
0x18001f0f1  mov     edx, 158h
0x18001f0f6  mov     rcx, [rcx+10h]
0x18001f0fa  mov     r9d, eax
0x18001f0fd  mov     r8, r15
0x18001f100  call    WPP_SF_d
0x18001f105  mov     rax, [rbp+57h+var_A0]
0x18001f109  jmp     loc_18001EFF5
0x18001f10e  mov     rcx, [rbp+57h+hObject]; TokenHandle
0x18001f112  xor     r9d, r9d; BufferLength
0x18001f115  mov     [rsp+0D0h+phNewToken], rbx; ReturnLength
0x18001f11a  mov     r8, r12; NewState
0x18001f11d  xor     edx, edx; DisableAllPrivileges
0x18001f11f  mov     qword ptr [rsp+0D0h+TokenType], rbx; PreviousState
0x18001f124  call    cs:__imp_AdjustTokenPrivileges
0x18001f12b  nop     dword ptr [rax+rax+00h]
0x18001f130  test    eax, eax
0x18001f132  jnz     short loc_18001F154
0x18001f134  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x18001f139  mov     edi, eax
0x18001f13b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f142  cmp     rcx, rsi
0x18001f145  jz      short loc_18001F105
0x18001f147  test    byte ptr [rcx+1Ch], 40h
0x18001f14b  jz      short loc_18001F105
0x18001f14d  mov     edx, 159h
0x18001f152  jmp     short loc_18001F0F6
0x18001f154  call    cs:__imp_GetLastError
0x18001f15b  nop     dword ptr [rax+rax+00h]
0x18001f160  mov     ebx, eax
0x18001f162  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f169  cmp     rcx, rsi
0x18001f16c  jz      short loc_18001F188
0x18001f16e  test    byte ptr [rcx+1Ch], 8
0x18001f172  jz      short loc_18001F188
0x18001f174  mov     rcx, [rcx+10h]
0x18001f178  mov     edx, 15Ah
0x18001f17d  mov     r9d, eax
0x18001f180  mov     r8, r15
0x18001f183  call    WPP_SF_d
0x18001f188  cmp     ebx, 514h
0x18001f18e  jnz     short loc_18001F1DB
0x18001f190  xor     edx, edx; Val
0x18001f192  lea     rcx, [rbp+57h+UserData.Size]; void *
0x18001f196  lea     r8d, [rdx+48h]; Size
0x18001f19a  call    memset_0
0x18001f19f  lea     rcx, aNgscbCommonUm; "ngscb_common_um"
0x18001f1a6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f1aa  mov     [rbp+57h+UserData.Ptr], rcx
0x18001f1ae  xor     ebx, ebx
0x18001f1b0  inc     rax
0x18001f1b3  cmp     [rcx+rax*2], bx
0x18001f1b7  jnz     short loc_18001F1B0
0x18001f1b9  lea     eax, ds:2[rax*2]
0x18001f1c0  mov     dword ptr [rbp+57h+UserData.0Ch], ebx
0x18001f1c3  lea     r8, [rbp+57h+UserData]; UserData
0x18001f1c7  mov     [rbp+57h+UserData.Size], eax
0x18001f1ca  mov     edx, 1; UserDataCount
0x18001f1cf  lea     rcx, FVE_NOT_ALL_TOKEN_PRIVILEGES_ASSIGNED; EventDescriptor
0x18001f1d6  call    ?NgscbTryWriteEventLog@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; NgscbTryWriteEventLog(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x18001f1db  mov     rdx, [rbp+57h+hObject]; Token
0x18001f1df  xor     ecx, ecx; Thread
0x18001f1e1  call    cs:__imp_SetThreadToken
0x18001f1e8  nop     dword ptr [rax+rax+00h]
0x18001f1ed  test    eax, eax
0x18001f1ef  jnz     short loc_18001F21C
0x18001f1f1  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x18001f1f6  mov     edi, eax
0x18001f1f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1ff  cmp     rcx, rsi
0x18001f202  jz      loc_18001F105
0x18001f208  test    byte ptr [rcx+1Ch], 40h
0x18001f20c  jz      loc_18001F105
0x18001f212  mov     edx, 15Bh
0x18001f217  jmp     loc_18001F0F6
0x18001f21c  mov     rax, [rbp+57h+var_A0]
0x18001f220  mov     [r13+0], rax
0x18001f224  mov     byte ptr [r13+8], 1
0x18001f229  jmp     loc_18001EFF5
```
