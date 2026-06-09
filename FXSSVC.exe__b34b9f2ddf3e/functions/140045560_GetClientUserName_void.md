# GetClientUserName(void)

- ea: `0x140045560`
- end: `0x140045790`
- name: `?GetClientUserName@@YAPEAGXZ`
- size: `560`
- prototype: `unsigned __int16 *(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14001cf70`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140045560`
- `0x14006f350`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x14004562c`
- `ADVAPI32!OpenThreadToken` at `0x14004562c`
- `ADVAPI32!GetTokenInformation` at `0x1400456a1`
- `ADVAPI32!GetTokenInformation` at `0x1400456a1`
- `KERNEL32!GetLastError` at `0x140045636`
- `KERNEL32!GetLastError` at `0x1400456ab`
- `KERNEL32!GetLastError` at `0x140045636`
- `KERNEL32!GetLastError` at `0x1400456ab`
- `KERNEL32!SetLastError` at `0x14004560a`
- `KERNEL32!SetLastError` at `0x14004575f`
- `KERNEL32!SetLastError` at `0x14004560a`
- `KERNEL32!SetLastError` at `0x14004575f`
- `KERNEL32!CloseHandle` at `0x140045753`
- `KERNEL32!CloseHandle` at `0x140045753`
- `KERNEL32!GetCurrentThread` at `0x140045617`
- `KERNEL32!GetCurrentThread` at `0x140045617`
- `RPCRT4!RpcRevertToSelf` at `0x140045713`
- `RPCRT4!RpcRevertToSelf` at `0x140045713`
- `RPCRT4!RpcImpersonateClient` at `0x1400455d0`
- `RPCRT4!RpcImpersonateClient` at `0x1400455d0`

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
0x140045560  mov     [rsp+arg_0], rbx
0x140045565  mov     [rsp+arg_8], r14
0x14004556a  push    r15
0x14004556c  sub     rsp, 0E0h
0x140045573  mov     rax, cs:__security_cookie
0x14004557a  xor     rax, rsp
0x14004557d  mov     [rsp+0E8h+var_18], rax
0x140045585  mov     [rsp+0E8h+var_A8], 0
0x14004558e  mov     [rsp+0E8h+TokenHandle], 0
0x140045597  mov     rcx, cs:WPP_GLOBAL_Control
0x14004559e  lea     r14, WPP_GLOBAL_Control
0x1400455a5  lea     r15, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x1400455ac  cmp     rcx, r14
0x1400455af  jz      short loc_1400455CE
0x1400455b1  test    byte ptr [rcx+1Ch], 4
0x1400455b5  jz      short loc_1400455CE
0x1400455b7  cmp     byte ptr [rcx+19h], 5
0x1400455bb  jb      short loc_1400455CE
0x1400455bd  mov     rcx, [rcx+10h]
0x1400455c1  mov     edx, 30h ; '0'
0x1400455c6  mov     r8, r15
0x1400455c9  call    WPP_SF_
0x1400455ce  xor     ecx, ecx; BindingHandle
0x1400455d0  call    cs:__imp_RpcImpersonateClient
0x1400455d6  mov     ebx, eax
0x1400455d8  test    eax, eax
0x1400455da  jz      short loc_140045617
0x1400455dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400455e3  cmp     rcx, r14
0x1400455e6  jz      short loc_140045608
0x1400455e8  test    byte ptr [rcx+1Ch], 4
0x1400455ec  jz      short loc_140045608
0x1400455ee  cmp     byte ptr [rcx+19h], 2
0x1400455f2  jb      short loc_140045608
0x1400455f4  mov     rcx, [rcx+10h]
0x1400455f8  mov     edx, 31h ; '1'
0x1400455fd  mov     r9d, eax
0x140045600  mov     r8, r15
0x140045603  call    WPP_SF_d
0x140045608  mov     ecx, ebx; dwErrCode
0x14004560a  call    cs:__imp_SetLastError
0x140045610  xor     eax, eax
0x140045612  jmp     loc_14004576A
0x140045617  call    cs:__imp_GetCurrentThread
0x14004561d  xor     r8d, r8d; OpenAsSelf
0x140045620  lea     r9, [rsp+0E8h+TokenHandle]; TokenHandle
0x140045625  mov     rcx, rax; ThreadHandle
0x140045628  lea     edx, [r8+8]; DesiredAccess
0x14004562c  call    cs:__imp_OpenThreadToken
0x140045632  test    eax, eax
0x140045634  jnz     short loc_14004567B
0x140045636  call    cs:__imp_GetLastError
0x14004563c  mov     ebx, eax
0x14004563e  mov     rcx, cs:WPP_GLOBAL_Control
0x140045645  cmp     rcx, r14
0x140045648  jz      loc_140045713
0x14004564e  test    byte ptr [rcx+1Ch], 4
0x140045652  jz      loc_140045713
0x140045658  cmp     byte ptr [rcx+19h], 2
0x14004565c  jb      loc_140045713
0x140045662  mov     edx, 32h ; '2'
0x140045667  mov     rcx, [rcx+10h]
0x14004566b  mov     r9d, eax
0x14004566e  mov     r8, r15
0x140045671  call    WPP_SF_d
0x140045676  jmp     loc_140045713
0x14004567b  mov     rcx, [rsp+0E8h+TokenHandle]; TokenHandle
0x140045680  lea     rax, [rsp+0E8h+var_B8]
0x140045685  mov     r9d, 80h; TokenInformationLength
0x14004568b  mov     [rsp+0E8h+var_B8], 0
0x140045693  lea     r8, [rsp+0E8h+TokenInformation]; TokenInformation
0x140045698  mov     [rsp+0E8h+ReturnLength], rax; ReturnLength
0x14004569d  lea     edx, [r9-7Fh]; TokenInformationClass
0x1400456a1  call    cs:__imp_GetTokenInformation
0x1400456a7  test    eax, eax
0x1400456a9  jnz     short loc_1400456D2
0x1400456ab  call    cs:__imp_GetLastError
0x1400456b1  mov     ebx, eax
0x1400456b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400456ba  cmp     rcx, r14
0x1400456bd  jz      short loc_140045713
0x1400456bf  test    byte ptr [rcx+1Ch], 4
0x1400456c3  jz      short loc_140045713
0x1400456c5  cmp     byte ptr [rcx+19h], 2
0x1400456c9  jb      short loc_140045713
0x1400456cb  mov     edx, 33h ; '3'
0x1400456d0  jmp     short loc_140045667
0x1400456d2  mov     rcx, [rsp+0E8h+TokenInformation]; Sid
0x1400456d7  lea     rdx, [rsp+0E8h+var_A8]
0x1400456dc  call    ConvertUserSidToName
0x1400456e1  mov     ebx, eax
0x1400456e3  test    eax, eax
0x1400456e5  jz      short loc_140045713
0x1400456e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400456ee  cmp     rcx, r14
0x1400456f1  jz      short loc_140045713
0x1400456f3  test    byte ptr [rcx+1Ch], 4
0x1400456f7  jz      short loc_140045713
0x1400456f9  cmp     byte ptr [rcx+19h], 2
0x1400456fd  jb      short loc_140045713
0x1400456ff  mov     rcx, [rcx+10h]
0x140045703  mov     edx, 34h ; '4'
0x140045708  mov     r9d, eax
0x14004570b  mov     r8, r15
0x14004570e  call    WPP_SF_d
0x140045713  call    cs:__imp_RpcRevertToSelf
0x140045719  test    eax, eax
0x14004571b  jz      short loc_140045749
0x14004571d  mov     rcx, cs:WPP_GLOBAL_Control
0x140045724  cmp     rcx, r14
0x140045727  jz      short loc_140045749
0x140045729  test    byte ptr [rcx+1Ch], 4
0x14004572d  jz      short loc_140045749
0x14004572f  cmp     byte ptr [rcx+19h], 2
0x140045733  jb      short loc_140045749
0x140045735  mov     rcx, [rcx+10h]
0x140045739  mov     edx, 35h ; '5'
0x14004573e  mov     r9d, ebx
0x140045741  mov     r8, r15
0x140045744  call    WPP_SF_d
0x140045749  mov     rcx, [rsp+0E8h+TokenHandle]; hObject
0x14004574e  test    rcx, rcx
0x140045751  jz      short loc_140045759
0x140045753  call    cs:__imp_CloseHandle
0x140045759  test    ebx, ebx
0x14004575b  jz      short loc_140045765
0x14004575d  mov     ecx, ebx; dwErrCode
0x14004575f  call    cs:__imp_SetLastError
0x140045765  mov     rax, [rsp+0E8h+var_A8]
0x14004576a  mov     rcx, [rsp+0E8h+var_18]
0x140045772  xor     rcx, rsp; StackCookie
0x140045775  call    __security_check_cookie
0x14004577a  lea     r11, [rsp+0E8h+var_8]
0x140045782  mov     rbx, [r11+10h]
0x140045786  mov     r14, [r11+18h]
0x14004578a  mov     rsp, r11
0x14004578d  pop     r15
0x14004578f  retn
```
