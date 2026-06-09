# GetClientUserName(void)

- ea: `0x140048010`
- end: `0x14004827d`
- name: `?GetClientUserName@@YAPEAGXZ`
- size: `621`
- prototype: `unsigned __int16 *(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14001dbc0`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140048010`
- `0x140073854`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x1400480ee`
- `ADVAPI32!OpenThreadToken` at `0x1400480ee`
- `ADVAPI32!GetTokenInformation` at `0x14004816f`
- `ADVAPI32!GetTokenInformation` at `0x14004816f`
- `KERNEL32!GetLastError` at `0x1400480fe`
- `KERNEL32!GetLastError` at `0x14004817f`
- `KERNEL32!GetLastError` at `0x1400480fe`
- `KERNEL32!GetLastError` at `0x14004817f`
- `KERNEL32!SetLastError` at `0x1400480c0`
- `KERNEL32!SetLastError` at `0x140048245`
- `KERNEL32!SetLastError` at `0x1400480c0`
- `KERNEL32!SetLastError` at `0x140048245`
- `KERNEL32!CloseHandle` at `0x140048233`
- `KERNEL32!CloseHandle` at `0x140048233`
- `KERNEL32!GetCurrentThread` at `0x1400480d3`
- `KERNEL32!GetCurrentThread` at `0x1400480d3`
- `RPCRT4!RpcRevertToSelf` at `0x1400481ed`
- `RPCRT4!RpcRevertToSelf` at `0x1400481ed`
- `RPCRT4!RpcImpersonateClient` at `0x140048080`
- `RPCRT4!RpcImpersonateClient` at `0x140048080`

## pseudocode

```c
unsigned __int16 *GetClientUserName(void)
{
  unsigned int v0; // eax
  DWORD v1; // ebx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  DWORD v5; // ebx
  CMapDeviceId *v6; // rcx
  __int64 v7; // rdx
  DWORD v8; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-B8h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-B0h] BYREF
  __int64 v11; // [rsp+40h] [rbp-A8h]
  PSID TokenInformation[16]; // [rsp+50h] [rbp-98h] BYREF

  v11 = 0;
  TokenHandle = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
  }
  v0 = RpcImpersonateClient(0);
  v1 = v0;
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v0);
    }
    SetLastError(v1);
    return 0;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    v5 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_27;
    }
    v7 = 50;
    goto LABEL_16;
  }
  ReturnLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x80u, &ReturnLength) )
  {
    v8 = ConvertUserSidToName(TokenInformation[0]);
    v5 = v8;
    if ( v8
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v8);
    }
    goto LABEL_27;
  }
  LastError = GetLastError();
  v5 = LastError;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = 51;
LABEL_16:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, LastError);
  }
LABEL_27:
  if ( RpcRevertToSelf()
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v5);
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v5 )
    SetLastError(v5);
  return (unsigned __int16 *)v11;
}

```

## disassembly

```asm
0x140048010  mov     [rsp+arg_0], rbx
0x140048015  mov     [rsp+arg_8], r14
0x14004801a  push    r15
0x14004801c  sub     rsp, 0E0h
0x140048023  mov     rax, cs:__security_cookie
0x14004802a  xor     rax, rsp
0x14004802d  mov     [rsp+0E8h+var_18], rax
0x140048035  mov     [rsp+0E8h+var_A8], 0
0x14004803e  mov     [rsp+0E8h+TokenHandle], 0
0x140048047  mov     rcx, cs:WPP_GLOBAL_Control
0x14004804e  lea     r14, WPP_GLOBAL_Control
0x140048055  lea     r15, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x14004805c  cmp     rcx, r14
0x14004805f  jz      short loc_14004807E
0x140048061  test    byte ptr [rcx+1Ch], 4
0x140048065  jz      short loc_14004807E
0x140048067  cmp     byte ptr [rcx+19h], 5
0x14004806b  jb      short loc_14004807E
0x14004806d  mov     rcx, [rcx+10h]
0x140048071  mov     edx, 30h ; '0'
0x140048076  mov     r8, r15
0x140048079  call    WPP_SF_
0x14004807e  xor     ecx, ecx; BindingHandle
0x140048080  call    cs:__imp_RpcImpersonateClient
0x140048087  nop     dword ptr [rax+rax+00h]
0x14004808c  mov     ebx, eax
0x14004808e  test    eax, eax
0x140048090  jz      short loc_1400480D3
0x140048092  mov     rcx, cs:WPP_GLOBAL_Control
0x140048099  cmp     rcx, r14
0x14004809c  jz      short loc_1400480BE
0x14004809e  test    byte ptr [rcx+1Ch], 4
0x1400480a2  jz      short loc_1400480BE
0x1400480a4  cmp     byte ptr [rcx+19h], 2
0x1400480a8  jb      short loc_1400480BE
0x1400480aa  mov     rcx, [rcx+10h]
0x1400480ae  mov     edx, 31h ; '1'
0x1400480b3  mov     r9d, eax
0x1400480b6  mov     r8, r15
0x1400480b9  call    WPP_SF_d
0x1400480be  mov     ecx, ebx; dwErrCode
0x1400480c0  call    cs:__imp_SetLastError
0x1400480c7  nop     dword ptr [rax+rax+00h]
0x1400480cc  xor     eax, eax
0x1400480ce  jmp     loc_140048256
0x1400480d3  call    cs:__imp_GetCurrentThread
0x1400480da  nop     dword ptr [rax+rax+00h]
0x1400480df  xor     r8d, r8d; OpenAsSelf
0x1400480e2  lea     r9, [rsp+0E8h+TokenHandle]; TokenHandle
0x1400480e7  mov     rcx, rax; ThreadHandle
0x1400480ea  lea     edx, [r8+8]; DesiredAccess
0x1400480ee  call    cs:__imp_OpenThreadToken
0x1400480f5  nop     dword ptr [rax+rax+00h]
0x1400480fa  test    eax, eax
0x1400480fc  jnz     short loc_140048149
0x1400480fe  call    cs:__imp_GetLastError
0x140048105  nop     dword ptr [rax+rax+00h]
0x14004810a  mov     ebx, eax
0x14004810c  mov     rcx, cs:WPP_GLOBAL_Control
0x140048113  cmp     rcx, r14
0x140048116  jz      loc_1400481ED
0x14004811c  test    byte ptr [rcx+1Ch], 4
0x140048120  jz      loc_1400481ED
0x140048126  cmp     byte ptr [rcx+19h], 2
0x14004812a  jb      loc_1400481ED
0x140048130  mov     edx, 32h ; '2'
0x140048135  mov     rcx, [rcx+10h]
0x140048139  mov     r9d, eax
0x14004813c  mov     r8, r15
0x14004813f  call    WPP_SF_d
0x140048144  jmp     loc_1400481ED
0x140048149  mov     rcx, [rsp+0E8h+TokenHandle]; TokenHandle
0x14004814e  lea     rax, [rsp+0E8h+var_B8]
0x140048153  mov     r9d, 80h; TokenInformationLength
0x140048159  mov     [rsp+0E8h+var_B8], 0
0x140048161  lea     r8, [rsp+0E8h+TokenInformation]; TokenInformation
0x140048166  mov     [rsp+0E8h+ReturnLength], rax; ReturnLength
0x14004816b  lea     edx, [r9-7Fh]; TokenInformationClass
0x14004816f  call    cs:__imp_GetTokenInformation
0x140048176  nop     dword ptr [rax+rax+00h]
0x14004817b  test    eax, eax
0x14004817d  jnz     short loc_1400481AC
0x14004817f  call    cs:__imp_GetLastError
0x140048186  nop     dword ptr [rax+rax+00h]
0x14004818b  mov     ebx, eax
0x14004818d  mov     rcx, cs:WPP_GLOBAL_Control
0x140048194  cmp     rcx, r14
0x140048197  jz      short loc_1400481ED
0x140048199  test    byte ptr [rcx+1Ch], 4
0x14004819d  jz      short loc_1400481ED
0x14004819f  cmp     byte ptr [rcx+19h], 2
0x1400481a3  jb      short loc_1400481ED
0x1400481a5  mov     edx, 33h ; '3'
0x1400481aa  jmp     short loc_140048135
0x1400481ac  mov     rcx, [rsp+0E8h+TokenInformation]; Sid
0x1400481b1  lea     rdx, [rsp+0E8h+var_A8]
0x1400481b6  call    ConvertUserSidToName
0x1400481bb  mov     ebx, eax
0x1400481bd  test    eax, eax
0x1400481bf  jz      short loc_1400481ED
0x1400481c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400481c8  cmp     rcx, r14
0x1400481cb  jz      short loc_1400481ED
0x1400481cd  test    byte ptr [rcx+1Ch], 4
0x1400481d1  jz      short loc_1400481ED
0x1400481d3  cmp     byte ptr [rcx+19h], 2
0x1400481d7  jb      short loc_1400481ED
0x1400481d9  mov     rcx, [rcx+10h]
0x1400481dd  mov     edx, 34h ; '4'
0x1400481e2  mov     r9d, eax
0x1400481e5  mov     r8, r15
0x1400481e8  call    WPP_SF_d
0x1400481ed  call    cs:__imp_RpcRevertToSelf
0x1400481f4  nop     dword ptr [rax+rax+00h]
0x1400481f9  test    eax, eax
0x1400481fb  jz      short loc_140048229
0x1400481fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140048204  cmp     rcx, r14
0x140048207  jz      short loc_140048229
0x140048209  test    byte ptr [rcx+1Ch], 4
0x14004820d  jz      short loc_140048229
0x14004820f  cmp     byte ptr [rcx+19h], 2
0x140048213  jb      short loc_140048229
0x140048215  mov     rcx, [rcx+10h]
0x140048219  mov     edx, 35h ; '5'
0x14004821e  mov     r9d, ebx
0x140048221  mov     r8, r15
0x140048224  call    WPP_SF_d
0x140048229  mov     rcx, [rsp+0E8h+TokenHandle]; hObject
0x14004822e  test    rcx, rcx
0x140048231  jz      short loc_14004823F
0x140048233  call    cs:__imp_CloseHandle
0x14004823a  nop     dword ptr [rax+rax+00h]
0x14004823f  test    ebx, ebx
0x140048241  jz      short loc_140048251
0x140048243  mov     ecx, ebx; dwErrCode
0x140048245  call    cs:__imp_SetLastError
0x14004824c  nop     dword ptr [rax+rax+00h]
0x140048251  mov     rax, [rsp+0E8h+var_A8]
0x140048256  mov     rcx, [rsp+0E8h+var_18]
0x14004825e  xor     rcx, rsp; StackCookie
0x140048261  call    __security_check_cookie
0x140048266  lea     r11, [rsp+0E8h+var_8]
0x14004826e  mov     rbx, [r11+10h]
0x140048272  mov     r14, [r11+18h]
0x140048276  mov     rsp, r11
0x140048279  pop     r15
0x14004827b  retn
```
