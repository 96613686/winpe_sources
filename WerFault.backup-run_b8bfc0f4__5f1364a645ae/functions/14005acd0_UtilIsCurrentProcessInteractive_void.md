# UtilIsCurrentProcessInteractive(void)

- ea: `0x14005acd0`
- end: `0x14005ae53`
- name: `?UtilIsCurrentProcessInteractive@@YAHXZ`
- size: `387`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004a768`
- `0x14004d690`
- `0x140052238`
- `0x140053bbc`

## callees

- `0x140002470`
- `0x140011ab8`
- `0x140011bf0`
- `0x140011d28`
- `0x140011e14`
- `0x14001444c`
- `0x14005acd0`
- `0x14005ae5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x14005add1`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x14005add1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005ade4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005ade4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14005ad33`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14005ad33`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14005ad75`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14005ad75`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14005ae2a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14005ae2a`

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
0x14005acd0  mov     [rsp-8+arg_0], rbx
0x14005acd5  mov     [rsp-8+arg_8], rdi
0x14005acda  push    rbp
0x14005acdb  mov     rbp, rsp
0x14005acde  sub     rsp, 80h
0x14005ace5  mov     rax, cs:__security_cookie
0x14005acec  xor     rax, rsp
0x14005acef  mov     [rbp+var_8], rax
0x14005acf3  xor     edi, edi
0x14005acf5  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x14005acfb  lea     rax, [rbp+SidToCheck]
0x14005acff  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x14005ad02  mov     [rsp+80h+pSid], rax; pSid
0x14005ad07  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x14005ad0b  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x14005ad0f  xor     r9d, r9d; nSubAuthority1
0x14005ad12  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x14005ad16  lea     r8d, [rdi+4]; nSubAuthority0
0x14005ad1a  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x14005ad1e  mov     dl, 1; nSubAuthorityCount
0x14005ad20  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x14005ad24  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x14005ad28  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x14005ad2c  mov     [rbp+IsMember], edi
0x14005ad2f  mov     [rbp+SidToCheck], rdi
0x14005ad33  call    cs:__imp_AllocateAndInitializeSid
0x14005ad39  test    eax, eax
0x14005ad3b  jnz     short loc_14005AD6B
0x14005ad3d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ad44  lea     rax, WPP_GLOBAL_Control
0x14005ad4b  cmp     rcx, rax
0x14005ad4e  jz      short loc_14005ADAC
0x14005ad50  test    byte ptr [rcx+1Ch], 1
0x14005ad54  jz      short loc_14005ADAC
0x14005ad56  lea     edx, [rdi+10h]
0x14005ad59  mov     rcx, [rcx+10h]
0x14005ad5d  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x14005ad64  call    WPP_SF_
0x14005ad69  jmp     short loc_14005ADAC
0x14005ad6b  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x14005ad6f  lea     r8, [rbp+IsMember]; IsMember
0x14005ad73  xor     ecx, ecx; TokenHandle
0x14005ad75  call    cs:__imp_CheckTokenMembership
0x14005ad7b  test    eax, eax
0x14005ad7d  jnz     short loc_14005AD9F
0x14005ad7f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ad86  lea     rax, WPP_GLOBAL_Control
0x14005ad8d  cmp     rcx, rax
0x14005ad90  jz      short loc_14005ADAC
0x14005ad92  test    byte ptr [rcx+1Ch], 1
0x14005ad96  jz      short loc_14005ADAC
0x14005ad98  mov     edx, 11h
0x14005ad9d  jmp     short loc_14005AD59
0x14005ad9f  cmp     [rbp+IsMember], edi
0x14005ada2  jz      short loc_14005ADB1
0x14005ada4  call    ?UtilIsInteractiveDesktop@@YAHXZ; UtilIsInteractiveDesktop(void)
0x14005ada9  mov     [rbp+IsMember], eax
0x14005adac  cmp     [rbp+IsMember], edi
0x14005adaf  jnz     short loc_14005AE05
0x14005adb1  call    ?UtilIsSystem@@YA_NXZ; UtilIsSystem(void)
0x14005adb6  test    al, al
0x14005adb8  jz      short loc_14005ADEC
0x14005adba  call    ?UtilIsInteractiveDesktop@@YAHXZ; UtilIsInteractiveDesktop(void)
0x14005adbf  test    eax, eax
0x14005adc1  jz      short loc_14005ADEC
0x14005adc3  lea     r8, aGlobalMicrosof; "Global\\Microsoft.Windows.Setup"
0x14005adca  xor     edx, edx; bInheritHandle
0x14005adcc  mov     ecx, 1F0001h; dwDesiredAccess
0x14005add1  call    cs:__imp_OpenMutexW
0x14005add7  lea     rcx, [rax+1]
0x14005addb  cmp     rcx, 1
0x14005addf  jbe     short loc_14005ADEC
0x14005ade1  mov     rcx, rax; hObject
0x14005ade4  call    cs:__imp_CloseHandle
0x14005adea  jmp     short loc_14005ADFE
0x14005adec  call    ?UtilIsWinPE@@YA_NXZ; UtilIsWinPE(void)
0x14005adf1  test    al, al
0x14005adf3  jz      short loc_14005AE1C
0x14005adf5  call    ?UtilIsInteractiveDesktop@@YAHXZ; UtilIsInteractiveDesktop(void)
0x14005adfa  test    eax, eax
0x14005adfc  jz      short loc_14005AE1C
0x14005adfe  mov     [rbp+IsMember], 1
0x14005ae05  call    ?UtilIsWindowManagerToken@@YAJPEAX@Z; UtilIsWindowManagerToken(void *)
0x14005ae0a  test    eax, eax
0x14005ae0c  jz      short loc_14005AE1C
0x14005ae0e  call    ?UtilIsVirtualServer@@YA_NXZ; UtilIsVirtualServer(void)
0x14005ae13  test    al, al
0x14005ae15  jnz     short loc_14005AE1C
0x14005ae17  mov     ebx, [rbp+IsMember]
0x14005ae1a  jmp     short loc_14005AE21
0x14005ae1c  mov     ebx, edi
0x14005ae1e  mov     [rbp+IsMember], ebx
0x14005ae21  mov     rcx, [rbp+SidToCheck]; pSid
0x14005ae25  test    rcx, rcx
0x14005ae28  jz      short loc_14005AE30
0x14005ae2a  call    cs:__imp_FreeSid
0x14005ae30  mov     eax, ebx
0x14005ae32  mov     rcx, [rbp+var_8]
0x14005ae36  xor     rcx, rsp; StackCookie
0x14005ae39  call    __security_check_cookie
0x14005ae3e  lea     r11, [rsp+80h+var_s0]
0x14005ae46  mov     rbx, [r11+10h]
0x14005ae4a  mov     rdi, [r11+18h]
0x14005ae4e  mov     rsp, r11
0x14005ae51  pop     rbp
0x14005ae52  retn
```
