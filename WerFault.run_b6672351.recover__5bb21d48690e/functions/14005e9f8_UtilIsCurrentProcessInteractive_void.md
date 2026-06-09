# UtilIsCurrentProcessInteractive(void)

- ea: `0x14005e9f8`
- end: `0x14005eb9a`
- name: `?UtilIsCurrentProcessInteractive@@YAHXZ`
- size: `418`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004dba8`
- `0x140050bf4`
- `0x140055b1c`
- `0x140057568`

## callees

- `0x140002490`
- `0x1400122ac`
- `0x1400123fc`
- `0x14001254c`
- `0x140012658`
- `0x140014ee4`
- `0x14005e9f8`
- `0x14005eba0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x14005eb05`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x14005eb05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005eb1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005eb1e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14005ea5b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14005ea5b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14005eaa3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14005eaa3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14005eb6a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14005eb6a`

## pseudocode

```c
__int64 UtilIsCurrentProcessInteractive(void)
{
  CUserModeHangReport *v0; // rcx
  __int64 v1; // rdx
  HANDLE v2; // rax
  unsigned int v3; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  IsMember = 0;
  SidToCheck = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    v0 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v1 = 16;
LABEL_5:
      WPP_SF_(*((_QWORD *)v0 + 2), v1, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids);
      goto LABEL_12;
    }
    goto LABEL_12;
  }
  if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v0 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v1 = 17;
      goto LABEL_5;
    }
LABEL_12:
    if ( IsMember )
      goto LABEL_20;
    goto LABEL_13;
  }
  if ( IsMember )
  {
    IsMember = UtilIsInteractiveDesktop();
    goto LABEL_12;
  }
LABEL_13:
  if ( UtilIsSystem()
    && (unsigned int)UtilIsInteractiveDesktop()
    && (v2 = OpenMutexW(0x1F0001u, 0, L"Global\\Microsoft.Windows.Setup"), (unsigned __int64)v2 + 1 > 1) )
  {
    CloseHandle(v2);
  }
  else if ( !UtilIsWinPE() || !(unsigned int)UtilIsInteractiveDesktop() )
  {
    goto LABEL_23;
  }
  IsMember = 1;
LABEL_20:
  if ( (unsigned int)UtilIsWindowManagerToken(v0) && !UtilIsVirtualServer() )
  {
    v3 = IsMember;
    goto LABEL_24;
  }
LABEL_23:
  v3 = 0;
  IsMember = 0;
LABEL_24:
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return v3;
}

```

## disassembly

```asm
0x14005e9f8  mov     [rsp-8+arg_0], rbx
0x14005e9fd  mov     [rsp-8+arg_8], rdi
0x14005ea02  push    rbp
0x14005ea03  mov     rbp, rsp
0x14005ea06  sub     rsp, 80h
0x14005ea0d  mov     rax, cs:__security_cookie
0x14005ea14  xor     rax, rsp
0x14005ea17  mov     [rbp+var_8], rax
0x14005ea1b  xor     edi, edi
0x14005ea1d  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x14005ea23  lea     rax, [rbp+SidToCheck]
0x14005ea27  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x14005ea2a  mov     [rsp+80h+pSid], rax; pSid
0x14005ea2f  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x14005ea33  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x14005ea37  xor     r9d, r9d; nSubAuthority1
0x14005ea3a  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x14005ea3e  lea     r8d, [rdi+4]; nSubAuthority0
0x14005ea42  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x14005ea46  mov     dl, 1; nSubAuthorityCount
0x14005ea48  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x14005ea4c  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x14005ea50  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x14005ea54  mov     [rbp+IsMember], edi
0x14005ea57  mov     [rbp+SidToCheck], rdi
0x14005ea5b  call    cs:__imp_AllocateAndInitializeSid
0x14005ea62  nop     dword ptr [rax+rax+00h]
0x14005ea67  test    eax, eax
0x14005ea69  jnz     short loc_14005EA99
0x14005ea6b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ea72  lea     rax, WPP_GLOBAL_Control
0x14005ea79  cmp     rcx, rax
0x14005ea7c  jz      short loc_14005EAE0
0x14005ea7e  test    byte ptr [rcx+1Ch], 1
0x14005ea82  jz      short loc_14005EAE0
0x14005ea84  lea     edx, [rdi+10h]
0x14005ea87  mov     rcx, [rcx+10h]
0x14005ea8b  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x14005ea92  call    WPP_SF_
0x14005ea97  jmp     short loc_14005EAE0
0x14005ea99  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x14005ea9d  lea     r8, [rbp+IsMember]; IsMember
0x14005eaa1  xor     ecx, ecx; TokenHandle
0x14005eaa3  call    cs:__imp_CheckTokenMembership
0x14005eaaa  nop     dword ptr [rax+rax+00h]
0x14005eaaf  test    eax, eax
0x14005eab1  jnz     short loc_14005EAD3
0x14005eab3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005eaba  lea     rax, WPP_GLOBAL_Control
0x14005eac1  cmp     rcx, rax
0x14005eac4  jz      short loc_14005EAE0
0x14005eac6  test    byte ptr [rcx+1Ch], 1
0x14005eaca  jz      short loc_14005EAE0
0x14005eacc  mov     edx, 11h
0x14005ead1  jmp     short loc_14005EA87
0x14005ead3  cmp     [rbp+IsMember], edi
0x14005ead6  jz      short loc_14005EAE5
0x14005ead8  call    ?UtilIsInteractiveDesktop@@YAHXZ; UtilIsInteractiveDesktop(void)
0x14005eadd  mov     [rbp+IsMember], eax
0x14005eae0  cmp     [rbp+IsMember], edi
0x14005eae3  jnz     short loc_14005EB45
0x14005eae5  call    ?UtilIsSystem@@YA_NXZ; UtilIsSystem(void)
0x14005eaea  test    al, al
0x14005eaec  jz      short loc_14005EB2C
0x14005eaee  call    ?UtilIsInteractiveDesktop@@YAHXZ; UtilIsInteractiveDesktop(void)
0x14005eaf3  test    eax, eax
0x14005eaf5  jz      short loc_14005EB2C
0x14005eaf7  lea     r8, aGlobalMicrosof; "Global\\Microsoft.Windows.Setup"
0x14005eafe  xor     edx, edx; bInheritHandle
0x14005eb00  mov     ecx, 1F0001h; dwDesiredAccess
0x14005eb05  call    cs:__imp_OpenMutexW
0x14005eb0c  nop     dword ptr [rax+rax+00h]
0x14005eb11  lea     rcx, [rax+1]
0x14005eb15  cmp     rcx, 1
0x14005eb19  jbe     short loc_14005EB2C
0x14005eb1b  mov     rcx, rax; hObject
0x14005eb1e  call    cs:__imp_CloseHandle
0x14005eb25  nop     dword ptr [rax+rax+00h]
0x14005eb2a  jmp     short loc_14005EB3E
0x14005eb2c  call    ?UtilIsWinPE@@YA_NXZ; UtilIsWinPE(void)
0x14005eb31  test    al, al
0x14005eb33  jz      short loc_14005EB5C
0x14005eb35  call    ?UtilIsInteractiveDesktop@@YAHXZ; UtilIsInteractiveDesktop(void)
0x14005eb3a  test    eax, eax
0x14005eb3c  jz      short loc_14005EB5C
0x14005eb3e  mov     [rbp+IsMember], 1
0x14005eb45  call    ?UtilIsWindowManagerToken@@YAJPEAX@Z; UtilIsWindowManagerToken(void *)
0x14005eb4a  test    eax, eax
0x14005eb4c  jz      short loc_14005EB5C
0x14005eb4e  call    ?UtilIsVirtualServer@@YA_NXZ; UtilIsVirtualServer(void)
0x14005eb53  test    al, al
0x14005eb55  jnz     short loc_14005EB5C
0x14005eb57  mov     ebx, [rbp+IsMember]
0x14005eb5a  jmp     short loc_14005EB61
0x14005eb5c  mov     ebx, edi
0x14005eb5e  mov     [rbp+IsMember], ebx
0x14005eb61  mov     rcx, [rbp+SidToCheck]; pSid
0x14005eb65  test    rcx, rcx
0x14005eb68  jz      short loc_14005EB76
0x14005eb6a  call    cs:__imp_FreeSid
0x14005eb71  nop     dword ptr [rax+rax+00h]
0x14005eb76  mov     eax, ebx
0x14005eb78  mov     rcx, [rbp+var_8]
0x14005eb7c  xor     rcx, rsp; StackCookie
0x14005eb7f  call    __security_check_cookie
0x14005eb84  lea     r11, [rsp+80h+var_s0]
0x14005eb8c  mov     rbx, [r11+10h]
0x14005eb90  mov     rdi, [r11+18h]
0x14005eb94  mov     rsp, r11
0x14005eb97  pop     rbp
0x14005eb98  retn
```
