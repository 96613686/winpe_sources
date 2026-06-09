# UlCreateTokenForMachineAccount

- ea: `0x14012ffe0`
- end: `0x1401303f4`
- name: `UlCreateTokenForMachineAccount`
- size: `1044`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140149cc0`

## callees

- `0x1400af720`
- `0x14012ffe0`
- `0x140130c48`
- `0x140167810`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14013036f`
- `ntoskrnl!ZwClose` at `0x14013036f`
- `ksecdd!InitializeSecurityContextW` at `0x1401301b9`
- `ksecdd!InitializeSecurityContextW` at `0x1401301b9`
- `ksecdd!SspiFreeAuthIdentity` at `0x140130354`
- `ksecdd!SspiFreeAuthIdentity` at `0x140130354`
- `ksecdd!FreeCredentialsHandle` at `0x140130301`
- `ksecdd!FreeCredentialsHandle` at `0x140130325`
- `ksecdd!FreeCredentialsHandle` at `0x140130301`
- `ksecdd!FreeCredentialsHandle` at `0x140130325`
- `ksecdd!AcquireCredentialsHandleW` at `0x1401300dc`
- `ksecdd!AcquireCredentialsHandleW` at `0x140130124`
- `ksecdd!AcquireCredentialsHandleW` at `0x1401300dc`
- `ksecdd!AcquireCredentialsHandleW` at `0x140130124`
- `ksecdd!DeleteSecurityContext` at `0x1401302b9`
- `ksecdd!DeleteSecurityContext` at `0x1401302dd`
- `ksecdd!DeleteSecurityContext` at `0x1401302b9`
- `ksecdd!DeleteSecurityContext` at `0x1401302dd`
- `ksecdd!AcceptSecurityContext` at `0x14013022e`
- `ksecdd!AcceptSecurityContext` at `0x14013022e`
- `ksecdd!QuerySecurityContextToken` at `0x1401303cb`
- `ksecdd!QuerySecurityContextToken` at `0x1401303cb`
- `ksecdd!SspiZeroAuthIdentity` at `0x140130343`
- `ksecdd!SspiZeroAuthIdentity` at `0x140130343`
- `ksecdd!FreeContextBuffer` at `0x140130147`
- `ksecdd!FreeContextBuffer` at `0x1401301db`
- `ksecdd!FreeContextBuffer` at `0x140130280`
- `ksecdd!FreeContextBuffer` at `0x140130299`
- `ksecdd!FreeContextBuffer` at `0x140130147`
- `ksecdd!FreeContextBuffer` at `0x1401301db`
- `ksecdd!FreeContextBuffer` at `0x140130280`
- `ksecdd!FreeContextBuffer` at `0x140130299`

## pseudocode

```c
__int64 __fastcall UlCreateTokenForMachineAccount(const wchar_t *a1, __int64 a2, HANDLE *a3)
{
  int LocalMachineAuthIdentity; // ebx
  SECURITY_STATUS v5; // eax
  struct _SecHandle *p_phNewContext; // rbx
  struct _SecHandle *p_phContext; // rdi
  unsigned int pfContextAttr; // [rsp+60h] [rbp-A0h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData; // [rsp+68h] [rbp-98h]
  SECURITY_INTEGER ptsExpiry; // [rsp+70h] [rbp-90h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-88h] BYREF
  PVOID v13[2]; // [rsp+80h] [rbp-80h] BYREF
  PVOID pvContextBuffer[2]; // [rsp+90h] [rbp-70h] BYREF
  UNICODE_STRING pPackage; // [rsp+A0h] [rbp-60h] BYREF
  struct _SecBufferDesc v16; // [rsp+B0h] [rbp-50h] BYREF
  struct _SecBufferDesc pInput; // [rsp+C0h] [rbp-40h] BYREF
  struct _SecHandle phContext; // [rsp+D0h] [rbp-30h] BYREF
  struct _SecHandle phNewContext; // [rsp+E0h] [rbp-20h] BYREF
  struct _SecHandle v20; // [rsp+F0h] [rbp-10h] BYREF
  struct _SecHandle phCredential; // [rsp+100h] [rbp+0h] BYREF

  *(_QWORD *)&pPackage.Length = 655368;
  *a3 = 0;
  pfContextAttr = 0;
  pPackage.Buffer = L"NTLM";
  ptsExpiry.QuadPart = 0;
  pInput.pBuffers = (PSecBuffer)pvContextBuffer;
  AuthData = 0;
  Handle = 0;
  v16.pBuffers = (PSecBuffer)v13;
  phCredential.dwUpper = -1;
  *(_OWORD *)pvContextBuffer = 0;
  phCredential.dwLower = -1;
  *(_OWORD *)v13 = 0;
  v20.dwUpper = -1;
  v20.dwLower = -1;
  phNewContext.dwUpper = -1;
  phNewContext.dwLower = -1;
  phContext.dwUpper = -1;
  phContext.dwLower = -1;
  HIDWORD(pvContextBuffer[0]) = 2;
  HIDWORD(v13[0]) = 2;
  pInput.ulVersion = 0;
  pInput.cBuffers = 1;
  v16.ulVersion = 0;
  v16.cBuffers = 1;
  LocalMachineAuthIdentity = UlpGetLocalMachineAuthIdentity(a1);
  if ( LocalMachineAuthIdentity >= 0 )
  {
    v5 = AcquireCredentialsHandleW(0, &pPackage, 2u, 0, AuthData, 0, 0, &phCredential, &ptsExpiry);
    if ( v5
      || (p_phNewContext = 0,
          p_phContext = 0,
          (v5 = AcquireCredentialsHandleW(0, &pPackage, 1u, 0, 0, 0, 0, &v20, &ptsExpiry)) != 0) )
    {
LABEL_17:
      LocalMachineAuthIdentity = UxSslMapSecurityStatusToErrorNtStatus((unsigned int)v5);
    }
    else
    {
      while ( 1 )
      {
        if ( pvContextBuffer[1] )
        {
          FreeContextBuffer(pvContextBuffer[1]);
          LODWORD(pvContextBuffer[0]) = 0;
          pvContextBuffer[1] = 0;
        }
        v5 = InitializeSecurityContextW(
               &phCredential,
               p_phNewContext,
               0,
               0x100u,
               0,
               0x10u,
               (PSecBufferDesc)((unsigned __int64)&v16 & -(__int64)(v13[1] != 0)),
               0,
               &phNewContext,
               &pInput,
               &pfContextAttr,
               &ptsExpiry);
        if ( v5 && v5 != 590610 )
        {
          if ( v5 < 0 && !p_phNewContext )
          {
            phNewContext.dwUpper = -1;
            phNewContext.dwLower = -1;
          }
          goto LABEL_17;
        }
        if ( v13[1] )
        {
          FreeContextBuffer(v13[1]);
          LODWORD(v13[0]) = 0;
          v13[1] = 0;
        }
        v5 = AcceptSecurityContext(
               &v20,
               p_phContext,
               &pInput,
               0x100u,
               0x10u,
               &phContext,
               &v16,
               &pfContextAttr,
               &ptsExpiry);
        if ( v5 && v5 != 590610 )
        {
          if ( v5 < 0 && !p_phContext )
          {
            phContext.dwUpper = -1;
            phContext.dwLower = -1;
          }
          goto LABEL_17;
        }
        if ( v5 != 590610 )
          break;
        p_phNewContext = &phNewContext;
        p_phContext = &phContext;
      }
      v5 = QuerySecurityContextToken(&phContext, &Handle);
      if ( v5 )
        goto LABEL_17;
      LocalMachineAuthIdentity = 0;
      *a3 = Handle;
      Handle = 0;
    }
  }
  if ( v13[1] )
  {
    FreeContextBuffer(v13[1]);
    v13[1] = 0;
  }
  if ( pvContextBuffer[1] )
  {
    FreeContextBuffer(pvContextBuffer[1]);
    pvContextBuffer[1] = 0;
  }
  if ( phContext.dwLower != -1 && phContext.dwUpper != -1 )
  {
    DeleteSecurityContext(&phContext);
    phContext.dwUpper = -1;
    phContext.dwLower = -1;
  }
  if ( phNewContext.dwLower != -1 && phNewContext.dwUpper != -1 )
  {
    DeleteSecurityContext(&phNewContext);
    phNewContext.dwUpper = -1;
    phNewContext.dwLower = -1;
  }
  if ( v20.dwLower != -1 && v20.dwUpper != -1 )
  {
    FreeCredentialsHandle(&v20);
    v20.dwUpper = -1;
    v20.dwLower = -1;
  }
  if ( phCredential.dwLower != -1 && phCredential.dwUpper != -1 )
  {
    FreeCredentialsHandle(&phCredential);
    phCredential.dwUpper = -1;
    phCredential.dwLower = -1;
  }
  if ( AuthData )
  {
    SspiZeroAuthIdentity(AuthData);
    SspiFreeAuthIdentity(AuthData);
    AuthData = 0;
  }
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)LocalMachineAuthIdentity;
}

```

## disassembly

```asm
0x14012ffe0  push    rbp
0x14012ffe2  push    rbx
0x14012ffe3  push    rsi
0x14012ffe4  push    rdi
0x14012ffe5  push    r12
0x14012ffe7  push    r14
0x14012ffe9  push    r15
0x14012ffeb  lea     rbp, [rsp-20h]
0x14012fff0  sub     rsp, 120h
0x14012fff7  mov     rax, cs:__security_cookie
0x14012fffe  xor     rax, rsp
0x140130001  mov     [rbp+50h+var_40], rax
0x140130005  xor     r14d, r14d
0x140130008  mov     qword ptr [rbp+50h+pPackage.Length], 0A0008h
0x140130010  or      r15, 0FFFFFFFFFFFFFFFFh
0x140130014  mov     [r8], r14
0x140130017  lea     rax, aNtlm_0; "NTLM"
0x14013001e  mov     [rsp+150h+var_F0], r14d
0x140130023  mov     [rbp+50h+pPackage.Buffer], rax
0x140130027  xorps   xmm0, xmm0
0x14013002a  lea     rax, [rbp+50h+pvContextBuffer]
0x14013002e  mov     qword ptr [rsp+150h+var_E0], r14
0x140130033  mov     [rbp+50h+pInput.pBuffers], rax
0x140130037  lea     edi, [r14+2]
0x14013003b  xorps   xmm1, xmm1
0x14013003e  mov     [rsp+150h+AuthData], r14
0x140130043  lea     rax, [rbp+50h+var_D0]
0x140130047  mov     [rsp+150h+Handle], r14
0x14013004c  mov     rsi, r8
0x14013004f  mov     [rbp+50h+var_A0.pBuffers], rax
0x140130053  lea     r12d, [r14+1]
0x140130057  mov     [rbp+50h+var_50.dwUpper], r15
0x14013005b  movups  xmmword ptr [rbp+50h+pvContextBuffer], xmm0
0x14013005f  lea     r8, [rsp+150h+AuthData]
0x140130064  mov     [rbp+50h+var_50.dwLower], r15
0x140130068  movups  xmmword ptr [rbp+50h+var_D0], xmm1
0x14013006c  mov     [rbp+50h+var_60.dwUpper], r15
0x140130070  mov     [rbp+50h+var_60.dwLower], r15
0x140130074  mov     [rbp+50h+phNewContext.dwUpper], r15
0x140130078  mov     [rbp+50h+phNewContext.dwLower], r15
0x14013007c  mov     [rbp+50h+phContext.dwUpper], r15
0x140130080  mov     [rbp+50h+phContext.dwLower], r15
0x140130084  mov     dword ptr [rbp+50h+pvContextBuffer+4], edi
0x140130087  mov     dword ptr [rbp+50h+var_D0+4], edi
0x14013008a  mov     [rbp+50h+pInput.ulVersion], r14d
0x14013008e  mov     [rbp+50h+pInput.cBuffers], r12d
0x140130092  mov     [rbp+50h+var_A0.ulVersion], r14d
0x140130096  mov     [rbp+50h+var_A0.cBuffers], r12d
0x14013009a  call    UlpGetLocalMachineAuthIdentity
0x14013009f  mov     ebx, eax
0x1401300a1  test    eax, eax
0x1401300a3  js      loc_140130277
0x1401300a9  lea     rax, [rsp+150h+var_E0]
0x1401300ae  xor     r9d, r9d; pvLogonId
0x1401300b1  mov     [rsp+150h+ptsExpiry], rax; ptsExpiry
0x1401300b6  lea     rdx, [rbp+50h+pPackage]; pPackage
0x1401300ba  lea     rax, [rbp+50h+var_50]
0x1401300be  mov     r8d, edi; fCredentialUse
0x1401300c1  mov     [rsp+150h+phCredential], rax; phCredential
0x1401300c6  xor     ecx, ecx; pPrincipal
0x1401300c8  mov     rax, [rsp+150h+AuthData]
0x1401300cd  mov     [rsp+150h+pvGetKeyArgument], r14; pvGetKeyArgument
0x1401300d2  mov     [rsp+150h+pGetKeyFn], r14; pGetKeyFn
0x1401300d7  mov     [rsp+150h+pAuthData], rax; pAuthData
0x1401300dc  call    cs:__imp_AcquireCredentialsHandleW
0x1401300e3  nop     dword ptr [rax+rax+00h]
0x1401300e8  test    eax, eax
0x1401300ea  jnz     loc_14013026E
0x1401300f0  lea     rax, [rsp+150h+var_E0]
0x1401300f5  xor     r9d, r9d; pvLogonId
0x1401300f8  mov     [rsp+150h+ptsExpiry], rax; ptsExpiry
0x1401300fd  lea     rdx, [rbp+50h+pPackage]; pPackage
0x140130101  lea     rax, [rbp+50h+var_60]
0x140130105  mov     r8d, r12d; fCredentialUse
0x140130108  mov     [rsp+150h+phCredential], rax; phCredential
0x14013010d  xor     ecx, ecx; pPrincipal
0x14013010f  mov     [rsp+150h+pvGetKeyArgument], r14; pvGetKeyArgument
0x140130114  mov     ebx, r14d
0x140130117  mov     [rsp+150h+pGetKeyFn], r14; pGetKeyFn
0x14013011c  mov     edi, r14d
0x14013011f  mov     [rsp+150h+pAuthData], r14; pAuthData
0x140130124  call    cs:__imp_AcquireCredentialsHandleW
0x14013012b  nop     dword ptr [rax+rax+00h]
0x140130130  test    eax, eax
0x140130132  jnz     loc_14013026E
0x140130138  mov     r12d, 90312h
0x14013013e  mov     rcx, [rbp+50h+pvContextBuffer+8]; pvContextBuffer
0x140130142  test    rcx, rcx
0x140130145  jz      short loc_14013015B
0x140130147  call    cs:__imp_FreeContextBuffer
0x14013014e  nop     dword ptr [rax+rax+00h]
0x140130153  mov     dword ptr [rbp+50h+pvContextBuffer], r14d
0x140130157  mov     [rbp+50h+pvContextBuffer+8], r14
0x14013015b  mov     rax, [rbp+50h+var_D0+8]
0x14013015f  mov     r9d, 100h; fContextReq
0x140130165  neg     rax
0x140130168  mov     rdx, rbx; phContext
0x14013016b  lea     rax, [rbp+50h+var_A0]
0x14013016f  sbb     rcx, rcx
0x140130172  xor     r8d, r8d; pTargetName
0x140130175  and     rcx, rax
0x140130178  lea     rax, [rsp+150h+var_E0]
0x14013017d  mov     [rsp+150h+var_F8], rax; ptsExpiry
0x140130182  lea     rax, [rsp+150h+var_F0]
0x140130187  mov     [rsp+150h+pfContextAttr], rax; pfContextAttr
0x14013018c  lea     rax, [rbp+50h+pInput]
0x140130190  mov     [rsp+150h+pOutput], rax; pOutput
0x140130195  lea     rax, [rbp+50h+phNewContext]
0x140130199  mov     [rsp+150h+ptsExpiry], rax; phNewContext
0x14013019e  mov     dword ptr [rsp+150h+phCredential], r14d; Reserved2
0x1401301a3  mov     [rsp+150h+pvGetKeyArgument], rcx; pInput
0x1401301a8  lea     rcx, [rbp+50h+var_50]; phCredential
0x1401301ac  mov     dword ptr [rsp+150h+pGetKeyFn], 10h; TargetDataRep
0x1401301b4  mov     dword ptr [rsp+150h+pAuthData], r14d; Reserved1
0x1401301b9  call    cs:__imp_InitializeSecurityContextW
0x1401301c0  nop     dword ptr [rax+rax+00h]
0x1401301c5  test    eax, eax
0x1401301c7  jz      short loc_1401301D2
0x1401301c9  cmp     eax, r12d
0x1401301cc  jnz     loc_14013025D
0x1401301d2  mov     rcx, [rbp+50h+var_D0+8]; pvContextBuffer
0x1401301d6  test    rcx, rcx
0x1401301d9  jz      short loc_1401301EF
0x1401301db  call    cs:__imp_FreeContextBuffer
0x1401301e2  nop     dword ptr [rax+rax+00h]
0x1401301e7  mov     dword ptr [rbp+50h+var_D0], r14d
0x1401301eb  mov     [rbp+50h+var_D0+8], r14
0x1401301ef  lea     rax, [rsp+150h+var_E0]
0x1401301f4  mov     r9d, 100h; fContextReq
0x1401301fa  mov     [rsp+150h+ptsExpiry], rax; ptsExpiry
0x1401301ff  lea     r8, [rbp+50h+pInput]; pInput
0x140130203  lea     rax, [rsp+150h+var_F0]
0x140130208  mov     rdx, rdi; phContext
0x14013020b  mov     [rsp+150h+phCredential], rax; pfContextAttr
0x140130210  lea     rcx, [rbp+50h+var_60]; phCredential
0x140130214  lea     rax, [rbp+50h+var_A0]
0x140130218  mov     [rsp+150h+pvGetKeyArgument], rax; pOutput
0x14013021d  lea     rax, [rbp+50h+phContext]
0x140130221  mov     [rsp+150h+pGetKeyFn], rax; phNewContext
0x140130226  mov     dword ptr [rsp+150h+pAuthData], 10h; TargetDataRep
0x14013022e  call    cs:__imp_AcceptSecurityContext
0x140130235  nop     dword ptr [rax+rax+00h]
0x14013023a  test    eax, eax
0x14013023c  jz      short loc_140130247
0x14013023e  cmp     eax, r12d
0x140130241  jnz     loc_14013039C
0x140130247  cmp     eax, r12d
0x14013024a  jnz     loc_1401303BA
0x140130250  lea     rbx, [rbp+50h+phNewContext]
0x140130254  lea     rdi, [rbp+50h+phContext]
0x140130258  jmp     loc_14013013E
0x14013025d  test    eax, eax
0x14013025f  jns     short loc_14013026E
0x140130261  test    rbx, rbx
0x140130264  jnz     short loc_14013026E
0x140130266  mov     [rbp+50h+phNewContext.dwUpper], r15
0x14013026a  mov     [rbp+50h+phNewContext.dwLower], r15
0x14013026e  mov     ecx, eax
0x140130270  call    UxSslMapSecurityStatusToErrorNtStatus
0x140130275  mov     ebx, eax
0x140130277  mov     rcx, [rbp+50h+var_D0+8]; pvContextBuffer
0x14013027b  test    rcx, rcx
0x14013027e  jz      short loc_140130290
0x140130280  call    cs:__imp_FreeContextBuffer
0x140130287  nop     dword ptr [rax+rax+00h]
0x14013028c  mov     [rbp+50h+var_D0+8], r14
0x140130290  mov     rcx, [rbp+50h+pvContextBuffer+8]; pvContextBuffer
0x140130294  test    rcx, rcx
0x140130297  jz      short loc_1401302A9
0x140130299  call    cs:__imp_FreeContextBuffer
0x1401302a0  nop     dword ptr [rax+rax+00h]
0x1401302a5  mov     [rbp+50h+pvContextBuffer+8], r14
0x1401302a9  cmp     [rbp+50h+phContext.dwLower], r15
0x1401302ad  jz      short loc_1401302CD
0x1401302af  cmp     [rbp+50h+phContext.dwUpper], r15
0x1401302b3  jz      short loc_1401302CD
0x1401302b5  lea     rcx, [rbp+50h+phContext]; phContext
0x1401302b9  call    cs:__imp_DeleteSecurityContext
0x1401302c0  nop     dword ptr [rax+rax+00h]
0x1401302c5  mov     [rbp+50h+phContext.dwUpper], r15
0x1401302c9  mov     [rbp+50h+phContext.dwLower], r15
0x1401302cd  cmp     [rbp+50h+phNewContext.dwLower], r15
0x1401302d1  jz      short loc_1401302F1
0x1401302d3  cmp     [rbp+50h+phNewContext.dwUpper], r15
0x1401302d7  jz      short loc_1401302F1
0x1401302d9  lea     rcx, [rbp+50h+phNewContext]; phContext
0x1401302dd  call    cs:__imp_DeleteSecurityContext
0x1401302e4  nop     dword ptr [rax+rax+00h]
0x1401302e9  mov     [rbp+50h+phNewContext.dwUpper], r15
0x1401302ed  mov     [rbp+50h+phNewContext.dwLower], r15
0x1401302f1  cmp     [rbp+50h+var_60.dwLower], r15
0x1401302f5  jz      short loc_140130315
0x1401302f7  cmp     [rbp+50h+var_60.dwUpper], r15
0x1401302fb  jz      short loc_140130315
0x1401302fd  lea     rcx, [rbp+50h+var_60]; phCredential
0x140130301  call    cs:__imp_FreeCredentialsHandle
0x140130308  nop     dword ptr [rax+rax+00h]
0x14013030d  mov     [rbp+50h+var_60.dwUpper], r15
0x140130311  mov     [rbp+50h+var_60.dwLower], r15
0x140130315  cmp     [rbp+50h+var_50.dwLower], r15
0x140130319  jz      short loc_140130339
0x14013031b  cmp     [rbp+50h+var_50.dwUpper], r15
0x14013031f  jz      short loc_140130339
0x140130321  lea     rcx, [rbp+50h+var_50]; phCredential
0x140130325  call    cs:__imp_FreeCredentialsHandle
0x14013032c  nop     dword ptr [rax+rax+00h]
0x140130331  mov     [rbp+50h+var_50.dwUpper], r15
0x140130335  mov     [rbp+50h+var_50.dwLower], r15
0x140130339  mov     rcx, [rsp+150h+AuthData]; AuthData
0x14013033e  test    rcx, rcx
0x140130341  jz      short loc_140130365
0x140130343  call    cs:__imp_SspiZeroAuthIdentity
0x14013034a  nop     dword ptr [rax+rax+00h]
0x14013034f  mov     rcx, [rsp+150h+AuthData]; AuthData
0x140130354  call    cs:__imp_SspiFreeAuthIdentity
0x14013035b  nop     dword ptr [rax+rax+00h]
0x140130360  mov     [rsp+150h+AuthData], r14
0x140130365  mov     rcx, [rsp+150h+Handle]; Handle
0x14013036a  test    rcx, rcx
0x14013036d  jz      short loc_14013037B
0x14013036f  call    cs:__imp_ZwClose
0x140130376  nop     dword ptr [rax+rax+00h]
0x14013037b  mov     eax, ebx
0x14013037d  mov     rcx, [rbp+50h+var_40]
0x140130381  xor     rcx, rsp; StackCookie
0x140130384  call    __security_check_cookie
0x140130389  add     rsp, 120h
0x140130390  pop     r15
0x140130392  pop     r14
0x140130394  pop     r12
0x140130396  pop     rdi
0x140130397  pop     rsi
0x140130398  pop     rbx
0x140130399  pop     rbp
0x14013039a  retn
0x14013039c  test    eax, eax
0x14013039e  jns     loc_14013026E
0x1401303a4  test    rdi, rdi
0x1401303a7  jnz     loc_14013026E
0x1401303ad  mov     [rbp+50h+phContext.dwUpper], r15
0x1401303b1  mov     [rbp+50h+phContext.dwLower], r15
0x1401303b5  jmp     loc_14013026E
0x1401303ba  test    eax, eax
0x1401303bc  jnz     loc_14013026E
0x1401303c2  lea     rdx, [rsp+150h+Handle]; Token
0x1401303c7  lea     rcx, [rbp+50h+phContext]; phContext
0x1401303cb  call    cs:__imp_QuerySecurityContextToken
0x1401303d2  nop     dword ptr [rax+rax+00h]
0x1401303d7  test    eax, eax
0x1401303d9  jnz     loc_14013026E
0x1401303df  mov     rax, [rsp+150h+Handle]
0x1401303e4  mov     ebx, r14d
0x1401303e7  mov     [rsi], rax
0x1401303ea  mov     [rsp+150h+Handle], r14
0x1401303ef  jmp     loc_140130277
```
