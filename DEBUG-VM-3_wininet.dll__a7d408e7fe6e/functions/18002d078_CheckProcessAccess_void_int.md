# CheckProcessAccess(void *,int *)

- ea: `0x18002d078`
- end: `0x18002d2e1`
- name: `?CheckProcessAccess@@YAJPEAXPEAH@Z`
- size: `617`
- prototype: `__int64 __fastcall(void *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002ba40`

## callees

- `0x18002d078`
- `0x1800701d0`
- `0x18014a7a0`
- `0x1801e1790`
- `0x1801e2f30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002d118`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002d118`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d106`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d106`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d1c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d1dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d1c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d1dd`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18002d1a8`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18002d1a8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002d156`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002d156`

## pseudocode

```c
__int64 __fastcall CheckProcessAccess(void *a1, int *a2)
{
  HANDLE CurrentProcess; // rax
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  signed int v7; // ebx
  int v9; // eax
  int v10; // eax
  int LastError; // eax
  HANDLE ClientToken; // [rsp+48h] [rbp-11h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-9h] BYREF
  WINBOOL AccessStatus; // [rsp+58h] [rbp-1h] BYREF
  DWORD GrantedAccess; // [rsp+5Ch] [rbp+3h] BYREF
  DWORD PrivilegeSetLength; // [rsp+60h] [rbp+7h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+68h] [rbp+Fh] BYREF

  TokenHandle = 0;
  ClientToken = 0;
  PrivilegeSetLength = 56;
  GrantedAccess = 0;
  AccessStatus = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
    WPP_SF_qq(
      1038,
      10,
      (unsigned int)&WPP_4b50d4119023394b229b3c7cf56764e6_Traceguids,
      (unsigned int)&unk_18021E540,
      (__int64)a2);
  if ( a2 )
  {
    *a2 = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x2000Au, &TokenHandle) )
    {
      if ( TokenHandle )
      {
        if ( DuplicateTokenEx(TokenHandle, 0x2000Cu, 0, SecurityIdentification, TokenImpersonation, &ClientToken) )
        {
          if ( ClientToken )
          {
            if ( AccessCheck(
                   &unk_18021E540,
                   ClientToken,
                   1u,
                   (PGENERIC_MAPPING)&GenericMapping,
                   &PrivilegeSet,
                   &PrivilegeSetLength,
                   &GrantedAccess,
                   &AccessStatus) )
            {
              v7 = 0;
              *a2 = AccessStatus;
            }
            else
            {
              LastError = WxGetLastError(v6);
              v7 = LastError;
              if ( LastError > 0 )
                v7 = (unsigned __int16)LastError | 0x80070000;
              if ( v7 >= 0 )
                v7 = -2147418113;
            }
          }
          else
          {
            v7 = -2147467259;
          }
        }
        else
        {
          v9 = WxGetLastError(v5);
          v7 = v9;
          if ( v9 > 0 )
            v7 = (unsigned __int16)v9 | 0x80070000;
          if ( v7 >= 0 )
            v7 = -2147418113;
        }
      }
      else
      {
        v7 = -2147467259;
      }
    }
    else
    {
      v10 = WxGetLastError(v4);
      v7 = v10;
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
      if ( v7 >= 0 )
        v7 = -2147418113;
    }
  }
  else
  {
    v7 = -2147024809;
  }
  if ( ClientToken )
  {
    CloseHandle(ClientToken);
    ClientToken = 0;
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
    WPP_SF_d(1038, 11, &WPP_4b50d4119023394b229b3c7cf56764e6_Traceguids, (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002d078  mov     [rsp-8+arg_0], rbx
0x18002d07d  mov     [rsp-8+arg_10], rdi
0x18002d082  push    rbp
0x18002d083  lea     rbp, [rsp-57h]
0x18002d088  sub     rsp, 0B0h
0x18002d08f  mov     rax, cs:__security_cookie
0x18002d096  xor     rax, rsp
0x18002d099  mov     [rbp+57h+var_10], rax
0x18002d09d  mov     rdi, rdx
0x18002d0a0  mov     [rbp+57h+var_6C], 0
0x18002d0a7  mov     [rbp+57h+TokenHandle], 0
0x18002d0af  mov     [rbp+57h+ClientToken], 0
0x18002d0b7  mov     [rbp+57h+PrivilegeSetLength], 38h ; '8'
0x18002d0be  mov     [rbp+57h+var_54], 0
0x18002d0c5  mov     [rbp+57h+var_58], 0
0x18002d0cc  test    byte ptr cs:xmmword_180266B60+1, 40h
0x18002d0d3  jz      short loc_18002D0F7
0x18002d0d5  mov     edx, 0Ah
0x18002d0da  mov     qword ptr [rsp+0B0h+TokenType], rdi
0x18002d0df  mov     ecx, 40Eh
0x18002d0e4  lea     r9, unk_18021E540
0x18002d0eb  lea     r8, WPP_4b50d4119023394b229b3c7cf56764e6_Traceguids
0x18002d0f2  call    WPP_SF_qq
0x18002d0f7  test    rdi, rdi
0x18002d0fa  jz      loc_18002D230
0x18002d100  mov     dword ptr [rdi], 0
0x18002d106  call    cs:__imp_GetCurrentProcess
0x18002d10c  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18002d110  mov     edx, 2000Ah; DesiredAccess
0x18002d115  mov     rcx, rax; ProcessHandle
0x18002d118  call    cs:__imp_OpenProcessToken
0x18002d11e  test    eax, eax
0x18002d120  jz      loc_18002D27C
0x18002d126  cmp     [rbp+57h+TokenHandle], 0
0x18002d12b  jz      loc_18002D26B
0x18002d131  mov     rcx, [rbp+57h+TokenHandle]; hExistingToken
0x18002d135  lea     rax, [rbp+57h+ClientToken]
0x18002d139  mov     [rsp+0B0h+phNewToken], rax; phNewToken
0x18002d13e  mov     ebx, 1
0x18002d143  mov     r9d, ebx; ImpersonationLevel
0x18002d146  mov     [rsp+0B0h+TokenType], 2; TokenType
0x18002d14e  xor     r8d, r8d; lpTokenAttributes
0x18002d151  mov     edx, 2000Ch; dwDesiredAccess
0x18002d156  call    cs:__imp_DuplicateTokenEx
0x18002d15c  test    eax, eax
0x18002d15e  jz      loc_18002D241
0x18002d164  cmp     [rbp+57h+ClientToken], 0
0x18002d169  jz      loc_18002D2D0
0x18002d16f  mov     rdx, [rbp+57h+ClientToken]; ClientToken
0x18002d173  lea     rax, [rbp+57h+var_58]
0x18002d177  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x18002d17c  lea     r9, GenericMapping; GenericMapping
0x18002d183  lea     rax, [rbp+57h+var_54]
0x18002d187  mov     r8d, ebx; DesiredAccess
0x18002d18a  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x18002d18f  lea     rcx, unk_18021E540; pSecurityDescriptor
0x18002d196  lea     rax, [rbp+57h+PrivilegeSetLength]
0x18002d19a  mov     [rsp+0B0h+phNewToken], rax; PrivilegeSetLength
0x18002d19f  lea     rax, [rbp+57h+PrivilegeSet]
0x18002d1a3  mov     qword ptr [rsp+0B0h+TokenType], rax; PrivilegeSet
0x18002d1a8  call    cs:__imp_AccessCheck
0x18002d1ae  test    eax, eax
0x18002d1b0  jz      loc_18002D2A6
0x18002d1b6  mov     eax, [rbp+57h+var_58]
0x18002d1b9  xor     ebx, ebx
0x18002d1bb  mov     [rdi], eax
0x18002d1bd  mov     rcx, [rbp+57h+ClientToken]; hObject
0x18002d1c1  test    rcx, rcx
0x18002d1c4  jz      short loc_18002D1D4
0x18002d1c6  call    cs:__imp_CloseHandle
0x18002d1cc  mov     [rbp+57h+ClientToken], 0
0x18002d1d4  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18002d1d8  test    rcx, rcx
0x18002d1db  jz      short loc_18002D1EB
0x18002d1dd  call    cs:__imp_CloseHandle
0x18002d1e3  mov     [rbp+57h+TokenHandle], 0
0x18002d1eb  test    byte ptr cs:xmmword_180266B60+1, 40h
0x18002d1f2  jz      short loc_18002D20D
0x18002d1f4  mov     edx, 0Bh
0x18002d1f9  lea     r8, WPP_4b50d4119023394b229b3c7cf56764e6_Traceguids
0x18002d200  mov     ecx, 40Eh
0x18002d205  mov     r9d, ebx
0x18002d208  call    WPP_SF_d
0x18002d20d  mov     eax, ebx
0x18002d20f  mov     rcx, [rbp+57h+var_10]
0x18002d213  xor     rcx, rsp; StackCookie
0x18002d216  call    __security_check_cookie
0x18002d21b  lea     r11, [rsp+0B0h+var_s0]
0x18002d223  mov     rbx, [r11+10h]
0x18002d227  mov     rdi, [r11+20h]
0x18002d22b  mov     rsp, r11
0x18002d22e  pop     rbp
0x18002d22f  retn
0x18002d230  mov     ebx, 80070057h
0x18002d235  mov     [rbp+57h+var_6C], 8Eh
0x18002d23c  jmp     loc_18002D1BD
0x18002d241  call    WxGetLastError
0x18002d246  mov     ebx, eax
0x18002d248  test    eax, eax
0x18002d24a  jle     short loc_18002D255
0x18002d24c  movzx   ebx, ax
0x18002d24f  or      ebx, 80070000h
0x18002d255  test    ebx, ebx
0x18002d257  mov     [rbp+57h+var_6C], 0A6h
0x18002d25e  mov     eax, 8000FFFFh
0x18002d263  cmovns  ebx, eax
0x18002d266  jmp     loc_18002D1BD
0x18002d26b  mov     ebx, 80004005h
0x18002d270  mov     [rbp+57h+var_6C], 9Ah
0x18002d277  jmp     loc_18002D1BD
0x18002d27c  call    WxGetLastError
0x18002d281  mov     ebx, eax
0x18002d283  test    eax, eax
0x18002d285  jle     short loc_18002D290
0x18002d287  movzx   ebx, ax
0x18002d28a  or      ebx, 80070000h
0x18002d290  test    ebx, ebx
0x18002d292  mov     [rbp+57h+var_6C], 98h
0x18002d299  mov     eax, 8000FFFFh
0x18002d29e  cmovns  ebx, eax
0x18002d2a1  jmp     loc_18002D1BD
0x18002d2a6  call    WxGetLastError
0x18002d2ab  mov     ebx, eax
0x18002d2ad  test    eax, eax
0x18002d2af  jle     short loc_18002D2BA
0x18002d2b1  movzx   ebx, ax
0x18002d2b4  or      ebx, 80070000h
0x18002d2ba  test    ebx, ebx
0x18002d2bc  mov     [rbp+57h+var_6C], 0B5h
0x18002d2c3  mov     eax, 8000FFFFh
0x18002d2c8  cmovns  ebx, eax
0x18002d2cb  jmp     loc_18002D1BD
0x18002d2d0  mov     ebx, 80004005h
0x18002d2d5  mov     [rbp+57h+var_6C], 0A8h
0x18002d2dc  jmp     loc_18002D1BD
```
