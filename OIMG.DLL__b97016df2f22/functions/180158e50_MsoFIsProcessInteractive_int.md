# MsoFIsProcessInteractive(int *)

- ea: `0x180158e50`
- end: `0x180159090`
- name: `?MsoFIsProcessInteractive@@YAHPEAH@Z`
- size: `576`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180159090`

## callees

- `0x180013080`
- `0x18001373c`
- `0x180158e50`
- `0x18056bd00`
- `0x18056d14c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180158f40`
- `KERNEL32!GetLastError` at `0x180158f40`
- `KERNEL32!GetCurrentProcess` at `0x180158ef9`
- `KERNEL32!GetCurrentProcess` at `0x180158ef9`
- `KERNEL32!CloseHandle` at `0x180159011`
- `KERNEL32!CloseHandle` at `0x18015904e`
- `KERNEL32!CloseHandle` at `0x180159011`
- `KERNEL32!CloseHandle` at `0x18015904e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180158f52`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180158f52`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180158ffa`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180158ffa`
- `ADVAPI32!OpenProcessToken` at `0x180158f0b`
- `ADVAPI32!OpenProcessToken` at `0x180158f0b`
- `ADVAPI32!CreateWellKnownSid` at `0x180158f98`
- `ADVAPI32!CreateWellKnownSid` at `0x180158f98`
- `ADVAPI32!IsValidSid` at `0x180158fbe`
- `ADVAPI32!IsValidSid` at `0x180158fbe`
- `ADVAPI32!EqualSid` at `0x180158fd1`
- `ADVAPI32!EqualSid` at `0x180158fd1`
- `ADVAPI32!GetTokenInformation` at `0x180158f32`
- `ADVAPI32!GetTokenInformation` at `0x180158f7d`
- `ADVAPI32!GetTokenInformation` at `0x180158f32`
- `ADVAPI32!GetTokenInformation` at `0x180158f7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MsoFIsProcessInteractive(int *a1)
{
  HANDLE CurrentProcess; // rax
  unsigned int *v4; // rax
  unsigned int *v5; // rdi
  unsigned int v6; // r15d
  unsigned __int8 v7; // si
  HANDLE v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  DWORD TokenInformationLength; // [rsp+38h] [rbp-39h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-31h] BYREF
  DWORD cbSid[4]; // [rsp+48h] [rbp-29h] BYREF
  _BYTE pSid[80]; // [rsp+58h] [rbp-19h] BYREF

  TokenHandle = 0;
  TokenInformationLength = 0;
  memset_0(pSid, 0, 0x44u);
  cbSid[0] = 68;
  if ( !a1 )
  {
    MsoShipAssertTagProc(1422280);
    return 0;
  }
  if ( vfHaveCachedInteractiveValue )
  {
    *a1 = vfIsProcessInteractive;
    return 1;
  }
  *a1 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    if ( GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength) )
    {
      v10 = 1422282;
    }
    else
    {
      if ( GetLastError() == 122 )
      {
        v4 = (unsigned int *)malloc(TokenInformationLength);
        v5 = 0;
        if ( v4 )
        {
          v5 = v4;
          if ( GetTokenInformation(TokenHandle, TokenGroups, v4, TokenInformationLength, &TokenInformationLength) )
          {
            if ( CreateWellKnownSid(WinInteractiveSid, 0, pSid, cbSid) )
            {
              v6 = 0;
              v7 = 1;
              while ( v6 < *v5 )
              {
                if ( IsValidSid(*(PSID *)&v5[4 * v6 + 2]) && EqualSid(pSid, *(PSID *)&v5[4 * v6 + 2]) )
                {
                  *a1 = 1;
                  break;
                }
                ++v6;
              }
              vfHaveCachedInteractiveValue = 1;
              vfIsProcessInteractive = *a1;
              goto LABEL_17;
            }
            v9 = 1422286;
          }
          else
          {
            v9 = 1422285;
          }
        }
        else
        {
          v9 = 1422284;
        }
        MsoShipAssertTagProc(v9);
        v7 = 0;
LABEL_17:
        if ( v5 )
          free(v5);
        goto LABEL_19;
      }
      v10 = 1422283;
    }
  }
  else
  {
    v10 = 1422281;
  }
  MsoShipAssertTagProc(v10);
  v7 = 0;
LABEL_19:
  v8 = TokenHandle;
  if ( TokenHandle )
  {
    TokenHandle = 0;
    CloseHandle(v8);
  }
  return v7;
}

```

## disassembly

```asm
0x180158e50  mov     rax, rsp
0x180158e53  mov     [rax+10h], rsi
0x180158e57  mov     [rax+18h], rdi
0x180158e5b  mov     [rax+20h], r12
0x180158e5f  push    rbp
0x180158e60  push    r14
0x180158e62  push    r15
0x180158e64  lea     rbp, [rax-5Fh]
0x180158e68  sub     rsp, 0B0h
0x180158e6f  mov     rax, cs:__security_cookie
0x180158e76  xor     rax, rsp
0x180158e79  mov     [rbp+57h+var_20], rax
0x180158e7d  mov     r14, rcx
0x180158e80  mov     [rbp+57h+TokenHandle], 0
0x180158e88  mov     [rbp+57h+TokenInformationLength], 0
0x180158e8f  mov     edi, 44h ; 'D'
0x180158e94  mov     r8d, edi; Size
0x180158e97  xor     edx, edx; Val
0x180158e99  lea     rcx, [rbp+57h+pSid]; void *
0x180158e9d  call    memset_0
0x180158ea2  mov     [rbp+57h+cbSid], edi
0x180158ea5  test    r14, r14
0x180158ea8  jz      loc_180159037
0x180158eae  cmp     cs:?vfHaveCachedInteractiveValue@@3HA, 0; int vfHaveCachedInteractiveValue
0x180158eb5  jz      short loc_180158EF2
0x180158eb7  mov     eax, cs:?vfIsProcessInteractive@@3HA; int vfIsProcessInteractive
0x180158ebd  mov     [r14], eax
0x180158ec0  mov     eax, 1
0x180158ec5  jmp     short loc_180158EC9
0x180158ec7  xor     eax, eax
0x180158ec9  mov     rcx, [rbp+57h+var_20]
0x180158ecd  xor     rcx, rsp; StackCookie
0x180158ed0  call    __security_check_cookie
0x180158ed5  lea     r11, [rsp+0C0h+var_10]
0x180158edd  mov     rsi, [r11+28h]
0x180158ee1  mov     rdi, [r11+30h]
0x180158ee5  mov     r12, [r11+38h]
0x180158ee9  mov     rsp, r11
0x180158eec  pop     r15
0x180158eee  pop     r14
0x180158ef0  pop     rbp
0x180158ef1  retn
0x180158ef2  mov     dword ptr [r14], 0
0x180158ef9  call    cs:__imp_GetCurrentProcess
0x180158eff  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180158f03  mov     edx, 20008h; DesiredAccess
0x180158f08  mov     rcx, rax; ProcessHandle
0x180158f0b  call    cs:__imp_OpenProcessToken
0x180158f11  test    eax, eax
0x180158f13  jz      loc_180159059
0x180158f19  lea     rax, [rbp+57h+TokenInformationLength]
0x180158f1d  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180158f22  xor     r9d, r9d; TokenInformationLength
0x180158f25  xor     r8d, r8d; TokenInformation
0x180158f28  lea     esi, [r9+2]
0x180158f2c  mov     edx, esi; TokenInformationClass
0x180158f2e  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180158f32  call    cs:__imp_GetTokenInformation
0x180158f38  test    eax, eax
0x180158f3a  jnz     loc_180159068
0x180158f40  call    cs:__imp_GetLastError
0x180158f46  cmp     eax, 7Ah ; 'z'
0x180158f49  jnz     loc_18015906F
0x180158f4f  mov     ecx, [rbp+57h+TokenInformationLength]; Size
0x180158f52  call    cs:__imp_malloc
0x180158f58  xor     edi, edi
0x180158f5a  test    rax, rax
0x180158f5d  cmovnz  rdi, rax
0x180158f61  jz      loc_180159076
0x180158f67  lea     rax, [rbp+57h+TokenInformationLength]
0x180158f6b  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180158f70  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180158f74  mov     r8, rdi; TokenInformation
0x180158f77  mov     edx, esi; TokenInformationClass
0x180158f79  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180158f7d  call    cs:__imp_GetTokenInformation
0x180158f83  test    eax, eax
0x180158f85  jz      loc_180159088
0x180158f8b  lea     r9, [rbp+57h+cbSid]; cbSid
0x180158f8f  lea     r8, [rbp+57h+pSid]; pSid
0x180158f93  xor     edx, edx; DomainSid
0x180158f95  lea     ecx, [rsi+9]; WellKnownSidType
0x180158f98  call    cs:__imp_CreateWellKnownSid
0x180158f9e  test    eax, eax
0x180158fa0  jz      short loc_180159020
0x180158fa2  xor     r15d, r15d
0x180158fa5  test    rdi, rdi
0x180158fa8  jz      short loc_180159027
0x180158faa  lea     esi, [r15+1]
0x180158fae  cmp     r15d, [rdi]
0x180158fb1  jnb     short loc_180158FE3
0x180158fb3  mov     r12d, r15d
0x180158fb6  add     r12, r12
0x180158fb9  mov     rcx, [rdi+r12*8+8]; pSid
0x180158fbe  call    cs:__imp_IsValidSid
0x180158fc4  test    eax, eax
0x180158fc6  jz      short loc_180158FDB
0x180158fc8  mov     rdx, [rdi+r12*8+8]; pSid2
0x180158fcd  lea     rcx, [rbp+57h+pSid]; pSid1
0x180158fd1  call    cs:__imp_EqualSid
0x180158fd7  test    eax, eax
0x180158fd9  jnz     short loc_180158FE0
0x180158fdb  add     r15d, esi
0x180158fde  jmp     short loc_180158FAE
0x180158fe0  mov     [r14], esi
0x180158fe3  mov     cs:?vfHaveCachedInteractiveValue@@3HA, esi; int vfHaveCachedInteractiveValue
0x180158fe9  mov     eax, [r14]
0x180158fec  mov     cs:?vfIsProcessInteractive@@3HA, eax; int vfIsProcessInteractive
0x180158ff2  test    rdi, rdi
0x180158ff5  jz      short loc_180159000
0x180158ff7  mov     rcx, rdi; Block
0x180158ffa  call    cs:__imp_free
0x180159000  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180159004  test    rcx, rcx
0x180159007  jz      short loc_180159017
0x180159009  mov     [rbp+57h+TokenHandle], 0
0x180159011  call    cs:__imp_CloseHandle
0x180159017  movzx   eax, sil
0x18015901b  jmp     loc_180158EC9
0x180159020  mov     ecx, 15B3CEh
0x180159025  jmp     short loc_18015907B
0x180159027  xor     edx, edx; struct CrashContext *
0x180159029  mov     ecx, 1F31F70Ch; unsigned int
0x18015902e  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180159034  jmp     short $+2
0x180159036  nop
0x180159037  mov     ecx, 15B3C8h
0x18015903c  call    MsoShipAssertTagProc
0x180159041  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180159045  test    rcx, rcx
0x180159048  jz      loc_180158EC7
0x18015904e  call    cs:__imp_CloseHandle
0x180159054  jmp     loc_180158EC7
0x180159059  mov     ecx, 15B3C9h
0x18015905e  call    MsoShipAssertTagProc
0x180159063  xor     sil, sil
0x180159066  jmp     short loc_180159000
0x180159068  mov     ecx, 15B3CAh
0x18015906d  jmp     short loc_18015905E
0x18015906f  mov     ecx, 15B3CBh
0x180159074  jmp     short loc_18015905E
0x180159076  mov     ecx, 15B3CCh
0x18015907b  call    MsoShipAssertTagProc
0x180159080  xor     sil, sil
0x180159083  jmp     loc_180158FF2
0x180159088  mov     ecx, 15B3CDh
0x18015908d  jmp     short loc_18015907B
```
