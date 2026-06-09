# CreateSD(ulong,ulong &)

- ea: `0x140005140`
- end: `0x140005490`
- name: `?CreateSD@@YAPEAXKAEAK@Z`
- size: `848`
- prototype: `_DWORD *__fastcall(DWORD, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140005ad0`

## callees

- `0x1400027e1`
- `0x140004d30`
- `0x140005140`
- `0x140014ad0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140005189`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140005189`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140005179`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140005179`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005286`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005482`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005286`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005482`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400051a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140005304`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140005386`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400051a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140005304`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140005386`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000527c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005450`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005478`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000527c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005450`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005478`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400051d5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400051d5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14000521e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140005265`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14000521e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140005265`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400052c7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400052d4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400052e1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400052c7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400052d4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400052e1`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1400053b2`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1400053b2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1400053d7`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1400053f8`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1400053d7`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1400053f8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140005272`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140005315`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140005464`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000546e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140005272`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140005315`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140005464`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000546e`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x140005433`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x140005433`

## pseudocode

```c
_DWORD *__fastcall CreateSD(DWORD a1, unsigned int *a2)
{
  HANDLE CurrentProcess; // rax
  void *v3; // rbx
  _QWORD *v4; // rax
  _QWORD *v5; // r15
  PSID v6; // rdi
  PSID v8; // rsi
  DWORD LengthSid; // r14d
  DWORD v10; // r12d
  ULONG v11; // r13d
  _DWORD *v12; // rax
  _DWORD *v13; // r14
  struct _ACL *v14; // rax
  struct _ACL *v15; // r12
  DWORD TokenInformationLength; // [rsp+60h] [rbp-59h] BYREF
  DWORD AccessMask; // [rsp+64h] [rbp-55h]
  PSID pSid; // [rsp+68h] [rbp-51h] BYREF
  PSID v19; // [rsp+70h] [rbp-49h] BYREF
  void *Src; // [rsp+78h] [rbp-41h]
  DWORD nAclLength; // [rsp+80h] [rbp-39h]
  void *TokenHandle; // [rsp+88h] [rbp-31h] BYREF
  _DWORD *v23; // [rsp+90h] [rbp-29h] BYREF
  char v24; // [rsp+98h] [rbp-21h]
  unsigned int *v25; // [rsp+A0h] [rbp-19h]
  void *v26; // [rsp+A8h] [rbp-11h]
  _QWORD *v27; // [rsp+B0h] [rbp-9h]
  PSID v28; // [rsp+B8h] [rbp-1h]
  PSID v29; // [rsp+C0h] [rbp+7h]
  struct _ACL *v30; // [rsp+C8h] [rbp+Fh]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+D0h] [rbp+17h] BYREF

  v25 = a2;
  AccessMask = a1;
  *a2 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    return 0;
  v3 = TokenHandle;
  v26 = TokenHandle;
  TokenInformationLength = 88;
  v4 = LocalAlloc(0x40u, 0x58u);
  v5 = v4;
  if ( !v4 )
  {
LABEL_8:
    CloseHandle(v3);
    return 0;
  }
  v27 = v4;
  if ( !GetTokenInformation(TokenHandle, TokenUser, v4, TokenInformationLength, &TokenInformationLength)
    || (*(_DWORD *)pIdentifierAuthority.Value = 0,
        *(_WORD *)&pIdentifierAuthority.Value[4] = 1280,
        pSid = 0,
        !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid)) )
  {
LABEL_7:
    LocalFree(v5);
    goto LABEL_8;
  }
  v6 = pSid;
  v28 = pSid;
  v19 = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v19) )
  {
LABEL_6:
    FreeSid(v6);
    goto LABEL_7;
  }
  v8 = v19;
  v29 = v19;
  Src = (void *)*v5;
  TokenInformationLength = GetLengthSid(Src);
  LengthSid = GetLengthSid(v19);
  v10 = LengthSid + GetLengthSid(pSid) + 24;
  nAclLength = v10;
  v11 = v10 + 2 * (TokenInformationLength + 10);
  v12 = LocalAlloc(0x40u, v11);
  v13 = v12;
  if ( !v12 )
  {
LABEL_11:
    FreeSid(v8);
    goto LABEL_6;
  }
  v23 = v12;
  v24 = 0;
  *(_OWORD *)v12 = 0;
  v12[4] = 0;
  *(_BYTE *)v12 = 1;
  *((_WORD *)v12 + 1) = -32764;
  memcpy_0(v12 + 5, Src, TokenInformationLength);
  v13[1] = 20;
  memcpy_0((char *)v13 + TokenInformationLength + 20, Src, TokenInformationLength);
  v13[2] = TokenInformationLength + 20;
  Src = (void *)v10;
  v14 = (struct _ACL *)LocalAlloc(0x40u, v10);
  v15 = v14;
  if ( !v14 )
  {
    OnDeleteIf<void *,void * (*)(void *),&void * LocalFree(void *)>::~OnDeleteIf<void *,void * (*)(void *),&void * LocalFree(void *)>(&v23);
    goto LABEL_11;
  }
  v30 = v14;
  if ( InitializeAcl(v14, nAclLength, 2u)
    && AddAccessAllowedAceEx(v15, 2u, 0, AccessMask, pSid)
    && AddAccessAllowedAceEx(v15, 2u, 0, AccessMask, v19)
    && (memcpy_0((char *)v13 + 2 * TokenInformationLength + 20, v15, (size_t)Src),
        v13[4] = 2 * TokenInformationLength + 20,
        RtlValidRelativeSecurityDescriptor(v13, v11, 7u)) )
  {
    v24 = 1;
    *v25 = v11;
  }
  else
  {
    v13 = 0;
  }
  LocalFree(v15);
  OnDeleteIf<void *,void * (*)(void *),&void * LocalFree(void *)>::~OnDeleteIf<void *,void * (*)(void *),&void * LocalFree(void *)>(&v23);
  FreeSid(v8);
  FreeSid(v6);
  LocalFree(v5);
  CloseHandle(v3);
  return v13;
}

```

## disassembly

```asm
0x140005140  mov     [rsp-8+arg_10], rbx
0x140005145  push    rbp
0x140005146  push    rsi
0x140005147  push    rdi
0x140005148  push    r12
0x14000514a  push    r13
0x14000514c  push    r14
0x14000514e  push    r15
0x140005150  lea     rbp, [rsp-27h]
0x140005155  sub     rsp, 0E0h
0x14000515c  mov     rax, cs:__security_cookie
0x140005163  xor     rax, rsp
0x140005166  mov     [rbp+57h+var_38], rax
0x14000516a  mov     [rbp+57h+var_70], rdx
0x14000516e  mov     [rbp+57h+AccessMask], ecx
0x140005171  xor     esi, esi
0x140005173  mov     [rdx], esi
0x140005175  mov     [rbp+57h+TokenHandle], rsi
0x140005179  call    cs:__imp_GetCurrentProcess
0x14000517f  mov     rcx, rax; ProcessHandle
0x140005182  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x140005186  lea     edx, [rsi+8]; DesiredAccess
0x140005189  call    cs:__imp_OpenProcessToken
0x14000518f  test    eax, eax
0x140005191  jz      loc_14000528C
0x140005197  mov     rbx, [rbp+57h+TokenHandle]
0x14000519b  mov     [rbp+57h+var_68], rbx
0x14000519f  lea     edx, [rsi+58h]; uBytes
0x1400051a2  mov     [rbp+57h+TokenInformationLength], edx
0x1400051a5  lea     ecx, [rsi+40h]; uFlags
0x1400051a8  call    cs:__imp_LocalAlloc
0x1400051ae  mov     r15, rax
0x1400051b1  test    rax, rax
0x1400051b4  jz      loc_140005283
0x1400051ba  mov     [rbp+57h+var_60], rax
0x1400051be  lea     rax, [rbp+57h+TokenInformationLength]
0x1400051c2  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x1400051c7  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x1400051cb  mov     r8, r15; TokenInformation
0x1400051ce  lea     edx, [rsi+1]; TokenInformationClass
0x1400051d1  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1400051d5  call    cs:__imp_GetTokenInformation
0x1400051db  test    eax, eax
0x1400051dd  jz      loc_140005279
0x1400051e3  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x1400051e6  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1400051ec  mov     [rbp+57h+var_A8], rsi
0x1400051f0  lea     rax, [rbp+57h+var_A8]
0x1400051f4  mov     [rsp+110h+pSid], rax; pSid
0x1400051f9  mov     [rsp+110h+nSubAuthority7], esi; nSubAuthority7
0x1400051fd  mov     [rsp+110h+nSubAuthority6], esi; nSubAuthority6
0x140005201  mov     [rsp+110h+nSubAuthority5], esi; nSubAuthority5
0x140005205  mov     [rsp+110h+nSubAuthority4], esi; nSubAuthority4
0x140005209  mov     [rsp+110h+nSubAuthority3], esi; nSubAuthority3
0x14000520d  mov     dword ptr [rsp+110h+ReturnLength], esi; nSubAuthority2
0x140005211  xor     r9d, r9d; nSubAuthority1
0x140005214  lea     r8d, [rsi+12h]; nSubAuthority0
0x140005218  mov     dl, 1; nSubAuthorityCount
0x14000521a  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14000521e  call    cs:__imp_AllocateAndInitializeSid
0x140005224  test    eax, eax
0x140005226  jz      short loc_140005279
0x140005228  mov     rdi, [rbp+57h+var_A8]
0x14000522c  mov     [rbp+57h+var_58], rdi
0x140005230  mov     [rbp+57h+var_A0], rsi
0x140005234  lea     rax, [rbp+57h+var_A0]
0x140005238  mov     [rsp+110h+pSid], rax; pSid
0x14000523d  mov     [rsp+110h+nSubAuthority7], esi; nSubAuthority7
0x140005241  mov     [rsp+110h+nSubAuthority6], esi; nSubAuthority6
0x140005245  mov     [rsp+110h+nSubAuthority5], esi; nSubAuthority5
0x140005249  mov     [rsp+110h+nSubAuthority4], esi; nSubAuthority4
0x14000524d  mov     [rsp+110h+nSubAuthority3], esi; nSubAuthority3
0x140005251  mov     dword ptr [rsp+110h+ReturnLength], esi; nSubAuthority2
0x140005255  mov     r9d, 220h; nSubAuthority1
0x14000525b  lea     r8d, [rsi+20h]; nSubAuthority0
0x14000525f  mov     dl, 2; nSubAuthorityCount
0x140005261  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140005265  call    cs:__imp_AllocateAndInitializeSid
0x14000526b  test    eax, eax
0x14000526d  jnz     short loc_1400052B5
0x14000526f  mov     rcx, rdi; pSid
0x140005272  call    cs:__imp_FreeSid
0x140005278  nop
0x140005279  mov     rcx, r15; hMem
0x14000527c  call    cs:__imp_LocalFree
0x140005282  nop
0x140005283  mov     rcx, rbx; hObject
0x140005286  call    cs:__imp_CloseHandle
0x14000528c  xor     eax, eax
0x14000528e  mov     rcx, [rbp+57h+var_38]
0x140005292  xor     rcx, rsp; StackCookie
0x140005295  call    __security_check_cookie
0x14000529a  mov     rbx, [rsp+110h+arg_10]
0x1400052a2  add     rsp, 0E0h
0x1400052a9  pop     r15
0x1400052ab  pop     r14
0x1400052ad  pop     r13
0x1400052af  pop     r12
0x1400052b1  pop     rdi
0x1400052b2  pop     rsi
0x1400052b3  pop     rbp
0x1400052b4  retn
0x1400052b5  mov     rsi, [rbp+57h+var_A0]
0x1400052b9  mov     [rbp+57h+var_50], rsi
0x1400052bd  mov     rax, [r15]
0x1400052c0  mov     [rbp+57h+Src], rax
0x1400052c4  mov     rcx, rax; pSid
0x1400052c7  call    cs:__imp_GetLengthSid
0x1400052cd  mov     [rbp+57h+TokenInformationLength], eax
0x1400052d0  mov     rcx, [rbp+57h+var_A0]; pSid
0x1400052d4  call    cs:__imp_GetLengthSid
0x1400052da  mov     r14d, eax
0x1400052dd  mov     rcx, [rbp+57h+var_A8]; pSid
0x1400052e1  call    cs:__imp_GetLengthSid
0x1400052e7  lea     r12d, [rax+18h]
0x1400052eb  add     r12d, r14d
0x1400052ee  mov     [rbp+57h+nAclLength], r12d
0x1400052f2  mov     eax, [rbp+57h+TokenInformationLength]
0x1400052f5  add     eax, 0Ah
0x1400052f8  lea     r13d, [r12+rax*2]
0x1400052fc  mov     edx, r13d; uBytes
0x1400052ff  mov     ecx, 40h ; '@'; uFlags
0x140005304  call    cs:__imp_LocalAlloc
0x14000530a  mov     r14, rax
0x14000530d  test    rax, rax
0x140005310  jnz     short loc_140005320
0x140005312  mov     rcx, rsi; pSid
0x140005315  call    cs:__imp_FreeSid
0x14000531b  jmp     loc_14000526F
0x140005320  mov     [rbp+57h+var_80], r14
0x140005324  mov     [rbp+57h+var_78], 0
0x140005328  xorps   xmm0, xmm0
0x14000532b  xor     eax, eax
0x14000532d  movups  xmmword ptr [r14], xmm0
0x140005331  mov     [r14+10h], eax
0x140005335  mov     byte ptr [r14], 1
0x140005339  mov     word ptr [r14+2], 8004h
0x140005340  mov     r8d, [rbp+57h+TokenInformationLength]; Size
0x140005344  lea     rcx, [r14+14h]; void *
0x140005348  mov     rdx, [rbp+57h+Src]; Src
0x14000534c  call    memcpy_0
0x140005351  mov     dword ptr [r14+4], 14h
0x140005359  mov     r8d, [rbp+57h+TokenInformationLength]; Size
0x14000535d  lea     rcx, [r8+14h]
0x140005361  add     rcx, r14; void *
0x140005364  mov     rdx, [rbp+57h+Src]; Src
0x140005368  call    memcpy_0
0x14000536d  mov     eax, [rbp+57h+TokenInformationLength]
0x140005370  add     eax, 14h
0x140005373  mov     [r14+8], eax
0x140005377  mov     eax, r12d
0x14000537a  mov     [rbp+57h+Src], rax
0x14000537e  mov     edx, r12d; uBytes
0x140005381  mov     ecx, 40h ; '@'; uFlags
0x140005386  call    cs:__imp_LocalAlloc
0x14000538c  mov     r12, rax
0x14000538f  test    rax, rax
0x140005392  jnz     short loc_1400053A2
0x140005394  lea     rcx, [rbp+57h+var_80]
0x140005398  call    ??1?$OnDeleteIf@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@@QEAA@XZ; OnDeleteIf<void *,void * (*)(void *),&LocalFree(void *)>::~OnDeleteIf<void *,void * (*)(void *),&LocalFree(void *)>(void)
0x14000539d  jmp     loc_140005312
0x1400053a2  mov     [rbp+57h+var_48], r12
0x1400053a6  mov     r8d, 2; dwAclRevision
0x1400053ac  mov     edx, [rbp+57h+nAclLength]; nAclLength
0x1400053af  mov     rcx, r12; pAcl
0x1400053b2  call    cs:__imp_InitializeAcl
0x1400053b8  test    eax, eax
0x1400053ba  jz      loc_14000544A
0x1400053c0  mov     rax, [rbp+57h+var_A8]
0x1400053c4  mov     [rsp+110h+ReturnLength], rax; pSid
0x1400053c9  mov     r9d, [rbp+57h+AccessMask]; AccessMask
0x1400053cd  xor     r8d, r8d; AceFlags
0x1400053d0  lea     edx, [r8+2]; dwAceRevision
0x1400053d4  mov     rcx, r12; pAcl
0x1400053d7  call    cs:__imp_AddAccessAllowedAceEx
0x1400053dd  test    eax, eax
0x1400053df  jz      short loc_14000544A
0x1400053e1  mov     rax, [rbp+57h+var_A0]
0x1400053e5  mov     [rsp+110h+ReturnLength], rax; pSid
0x1400053ea  mov     r9d, [rbp+57h+AccessMask]; AccessMask
0x1400053ee  xor     r8d, r8d; AceFlags
0x1400053f1  lea     edx, [r8+2]; dwAceRevision
0x1400053f5  mov     rcx, r12; pAcl
0x1400053f8  call    cs:__imp_AddAccessAllowedAceEx
0x1400053fe  test    eax, eax
0x140005400  jz      short loc_14000544A
0x140005402  mov     eax, [rbp+57h+TokenInformationLength]
0x140005405  add     rax, 0Ah
0x140005409  lea     rcx, [r14+rax*2]; void *
0x14000540d  mov     r8, [rbp+57h+Src]; Size
0x140005411  mov     rdx, r12; Src
0x140005414  call    memcpy_0
0x140005419  mov     eax, [rbp+57h+TokenInformationLength]
0x14000541c  lea     eax, ds:14h[rax*2]
0x140005423  mov     [r14+10h], eax
0x140005427  mov     r8d, 7; RequiredInformation
0x14000542d  mov     edx, r13d; SecurityDescriptorLength
0x140005430  mov     rcx, r14; SecurityDescriptorInput
0x140005433  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x140005439  test    al, al
0x14000543b  jz      short loc_14000544A
0x14000543d  mov     [rbp+57h+var_78], 1
0x140005441  mov     rax, [rbp+57h+var_70]
0x140005445  mov     [rax], r13d
0x140005448  jmp     short loc_14000544D
0x14000544a  xor     r14d, r14d
0x14000544d  mov     rcx, r12; hMem
0x140005450  call    cs:__imp_LocalFree
0x140005456  nop
0x140005457  lea     rcx, [rbp+57h+var_80]
0x14000545b  call    ??1?$OnDeleteIf@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@@QEAA@XZ; OnDeleteIf<void *,void * (*)(void *),&LocalFree(void *)>::~OnDeleteIf<void *,void * (*)(void *),&LocalFree(void *)>(void)
0x140005460  nop
0x140005461  mov     rcx, rsi; pSid
0x140005464  call    cs:__imp_FreeSid
0x14000546a  nop
0x14000546b  mov     rcx, rdi; pSid
0x14000546e  call    cs:__imp_FreeSid
0x140005474  nop
0x140005475  mov     rcx, r15; hMem
0x140005478  call    cs:__imp_LocalFree
0x14000547e  nop
0x14000547f  mov     rcx, rbx; hObject
0x140005482  call    cs:__imp_CloseHandle
0x140005488  mov     rax, r14
0x14000548b  jmp     loc_14000528E
```
