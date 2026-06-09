# GetPackageSidAndCapabilities(_MONIKER_AND_CAPABILITIES *,void * *,_SID_AND_ATTRIBUTES * const,ulong *,void * *)

- ea: `0x180106728`
- end: `0x180106900`
- name: `?GetPackageSidAndCapabilities@@YAKPEAU_MONIKER_AND_CAPABILITIES@@PEAPEAXQEAU_SID_AND_ATTRIBUTES@@PEAK1@Z`
- size: `472`
- prototype: `__int64 __fastcall(struct _MONIKER_AND_CAPABILITIES *, void **, struct _SID_AND_ATTRIBUTES *const, unsigned int *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180106908`
- `0x180106b44`

## callees

- `0x180040790`
- `0x180040880`
- `0x18008e690`
- `0x1801066e0`
- `0x180106728`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1801067f1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1801067f1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801068cb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801068cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106801`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180106783`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180106783`
- `api-ms-win-security-base-private-l1-1-1!CreateAppContainerToken` at `0x1801068a8`
- `api-ms-win-security-base-private-l1-1-1!CreateAppContainerToken` at `0x1801068a8`
- `ext-ms-win-kernel32-package-l1-1-0!AppContainerDeriveSidFromMoniker` at `0x180106861`
- `ext-ms-win-kernel32-package-l1-1-0!AppContainerDeriveSidFromMoniker` at `0x180106861`
- `USERENV!CreateAppContainerProfile` at `0x180106832`
- `USERENV!CreateAppContainerProfile` at `0x180106832`

## pseudocode

```c
__int64 __fastcall GetPackageSidAndCapabilities(
        struct _MONIKER_AND_CAPABILITIES *a1,
        void **a2,
        struct _SID_AND_ATTRIBUTES *const a3,
        unsigned int *a4,
        void **a5)
{
  DWORD LastError; // ebx
  unsigned int i; // ebx
  unsigned __int16 v11; // ax
  unsigned __int16 v12; // ax
  struct _SID_AND_ATTRIBUTES *pSid; // [rsp+50h] [rbp-51h]
  PSID v15; // [rsp+60h] [rbp-41h] BYREF
  int v16; // [rsp+68h] [rbp-39h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-31h] BYREF
  char v18; // [rsp+78h] [rbp-29h]
  _QWORD v19[2]; // [rsp+80h] [rbp-21h] BYREF
  unsigned int v20; // [rsp+90h] [rbp-11h]
  int v21; // [rsp+94h] [rbp-Dh]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+98h] [rbp-9h] BYREF

  *a2 = 0;
  v15 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 3840;
  v16 = 0;
  *a4 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v16, 0);
  if ( !*((_DWORD *)a1 + 2) )
  {
    LastError = 0;
    goto LABEL_14;
  }
  if ( *((_DWORD *)a1 + 2) > 4u )
  {
    LastError = 87;
LABEL_22:
    if ( v15 )
      FreeSid(v15);
    FreePackageCapabilities(a3, *a4);
    *a4 = 0;
    return LastError;
  }
  for ( i = 0; i < *((_DWORD *)a1 + 2); ++i )
  {
    pSid = &a3[i];
    pSid->Attributes = 4;
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 3u, *((_DWORD *)a1 + i + 3), 0, 0, 0, 0, 0, 0, &pSid->Sid) )
    {
      LastError = GetLastError();
      goto LABEL_21;
    }
    ++*a4;
  }
  if ( *((_DWORD *)a1 + 2) )
  {
    v11 = CreateAppContainerProfile(*(_QWORD *)a1, *(_QWORD *)a1, *(_QWORD *)a1, a3, *a4, &v15);
    LastError = v11;
    if ( v11 && v11 != 183 )
      goto LABEL_22;
LABEL_14:
    if ( *((_DWORD *)a1 + 2) && LastError != 183 )
      goto LABEL_17;
  }
  v12 = AppContainerDeriveSidFromMoniker(*(_QWORD *)a1, &v15);
  LastError = v12;
  if ( v12 )
    goto LABEL_22;
LABEL_17:
  TokenHandle = 0;
  v18 = 0;
  if ( (int)Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::Suspend(&TokenHandle) >= 0
    || TokenHandle )
  {
    v19[0] = v15;
    v20 = *a4;
    v21 = 0;
    v19[1] = a3;
    CreateAppContainerToken(TokenHandle, v19, a5);
  }
  Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&TokenHandle);
  *a2 = v15;
LABEL_21:
  if ( LastError )
    goto LABEL_22;
  return LastError;
}

```

## disassembly

```asm
0x180106728  push    rbp
0x18010672a  push    rbx
0x18010672b  push    rsi
0x18010672c  push    rdi
0x18010672d  push    r12
0x18010672f  push    r13
0x180106731  push    r14
0x180106733  push    r15
0x180106735  lea     rbp, [rsp-17h]
0x18010673a  sub     rsp, 0B8h
0x180106741  mov     rax, cs:__security_cookie
0x180106748  xor     rax, rsp
0x18010674b  mov     [rbp+4Fh+var_50], rax
0x18010674f  mov     r12, [rbp+4Fh+arg_20]
0x180106753  xor     r13d, r13d
0x180106756  mov     [rdx], r13
0x180106759  mov     r14, r8
0x18010675c  mov     r15, rdx
0x18010675f  mov     [rbp+4Fh+var_90], r13
0x180106763  mov     rsi, rcx
0x180106766  mov     dword ptr [rbp+4Fh+pIdentifierAuthority.Value], r13d
0x18010676a  lea     rdx, [rbp+4Fh+var_88]
0x18010676e  mov     word ptr [rbp+4Fh+pIdentifierAuthority.Value+4], 0F00h
0x180106774  xor     r8d, r8d
0x180106777  mov     [rbp+4Fh+var_88], r13d
0x18010677b  xor     ecx, ecx
0x18010677d  mov     [r9], r13d
0x180106780  mov     rdi, r9
0x180106783  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180106789  cmp     [rsi+8], r13d
0x18010678d  jz      loc_180106849
0x180106793  cmp     dword ptr [rsi+8], 4
0x180106797  jbe     short loc_1801067A2
0x180106799  lea     ebx, [r13+57h]
0x18010679d  jmp     loc_1801068C2
0x1801067a2  mov     ebx, r13d
0x1801067a5  cmp     ebx, [rsi+8]
0x1801067a8  jnb     short loc_18010680E
0x1801067aa  mov     r9d, ebx
0x1801067ad  mov     r8d, 3; nSubAuthority0
0x1801067b3  mov     ecx, ebx
0x1801067b5  mov     dl, 2; nSubAuthorityCount
0x1801067b7  shl     rcx, 4
0x1801067bb  add     rcx, r14
0x1801067be  mov     [rsp+0F0h+pSid], rcx; pSid
0x1801067c3  mov     [rsp+0F0h+nSubAuthority7], r13d; nSubAuthority7
0x1801067c8  mov     [rsp+0F0h+nSubAuthority6], r13d; nSubAuthority6
0x1801067cd  mov     [rsp+0F0h+nSubAuthority5], r13d; nSubAuthority5
0x1801067d2  mov     dword ptr [rcx+8], 4
0x1801067d9  lea     rcx, [rbp+4Fh+pIdentifierAuthority]; pIdentifierAuthority
0x1801067dd  mov     r9d, [rsi+r9*4+0Ch]; nSubAuthority1
0x1801067e2  mov     [rsp+0F0h+nSubAuthority4], r13d; nSubAuthority4
0x1801067e7  mov     [rsp+0F0h+nSubAuthority3], r13d; nSubAuthority3
0x1801067ec  mov     [rsp+0F0h+nSubAuthority2], r13d; nSubAuthority2
0x1801067f1  call    cs:__imp_AllocateAndInitializeSid
0x1801067f7  test    eax, eax
0x1801067f9  jz      short loc_180106801
0x1801067fb  inc     dword ptr [rdi]
0x1801067fd  inc     ebx
0x1801067ff  jmp     short loc_1801067A5
0x180106801  call    cs:__imp_GetLastError
0x180106807  mov     ebx, eax
0x180106809  jmp     loc_1801068BE
0x18010680e  mov     ebx, r13d
0x180106811  cmp     [rsi+8], r13d
0x180106815  jz      short loc_18010685A
0x180106817  mov     r8, [rsi]
0x18010681a  lea     rax, [rbp+4Fh+var_90]
0x18010681e  mov     qword ptr [rsp+0F0h+nSubAuthority3], rax
0x180106823  mov     r9, r14
0x180106826  mov     eax, [rdi]
0x180106828  mov     rdx, r8
0x18010682b  mov     rcx, r8
0x18010682e  mov     [rsp+0F0h+nSubAuthority2], eax
0x180106832  call    cs:__imp_CreateAppContainerProfile
0x180106838  movzx   ebx, ax
0x18010683b  test    ebx, ebx
0x18010683d  jz      short loc_18010684C
0x18010683f  cmp     ebx, 0B7h
0x180106845  jnz     short loc_1801068C2
0x180106847  jmp     short loc_18010684C
0x180106849  mov     ebx, r13d
0x18010684c  cmp     [rsi+8], r13d
0x180106850  jz      short loc_18010685A
0x180106852  cmp     ebx, 0B7h
0x180106858  jnz     short loc_18010686E
0x18010685a  mov     rcx, [rsi]
0x18010685d  lea     rdx, [rbp+4Fh+var_90]
0x180106861  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x180106867  movzx   ebx, ax
0x18010686a  test    ebx, ebx
0x18010686c  jnz     short loc_1801068C2
0x18010686e  lea     rcx, [rbp+4Fh+TokenHandle]; TokenHandle
0x180106872  mov     [rbp+4Fh+TokenHandle], r13
0x180106876  mov     [rbp+4Fh+var_78], r13b
0x18010687a  call    ?Suspend@SuspendImpersonationScope@Web@Authentication@Security@Internal@Windows@@QEAAJXZ; Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::Suspend(void)
0x18010687f  mov     rcx, [rbp+4Fh+TokenHandle]
0x180106883  test    eax, eax
0x180106885  jns     short loc_18010688C
0x180106887  test    rcx, rcx
0x18010688a  jz      short loc_1801068AE
0x18010688c  mov     rax, [rbp+4Fh+var_90]
0x180106890  lea     rdx, [rbp+4Fh+var_70]
0x180106894  mov     [rbp+4Fh+var_70], rax
0x180106898  mov     r8, r12
0x18010689b  mov     eax, [rdi]
0x18010689d  mov     [rbp+4Fh+var_60], eax
0x1801068a0  mov     [rbp+4Fh+var_5C], r13d
0x1801068a4  mov     [rbp+4Fh+var_68], r14
0x1801068a8  call    cs:__imp_CreateAppContainerToken
0x1801068ae  lea     rcx, [rbp+4Fh+TokenHandle]; this
0x1801068b2  call    ??1SuspendImpersonationScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope(void)
0x1801068b7  mov     rax, [rbp+4Fh+var_90]
0x1801068bb  mov     [r15], rax
0x1801068be  test    ebx, ebx
0x1801068c0  jz      short loc_1801068DE
0x1801068c2  mov     rcx, [rbp+4Fh+var_90]; pSid
0x1801068c6  test    rcx, rcx
0x1801068c9  jz      short loc_1801068D1
0x1801068cb  call    cs:__imp_FreeSid
0x1801068d1  mov     edx, [rdi]; unsigned int
0x1801068d3  mov     rcx, r14; struct _SID_AND_ATTRIBUTES *
0x1801068d6  call    ?FreePackageCapabilities@@YAXQEAU_SID_AND_ATTRIBUTES@@K@Z; FreePackageCapabilities(_SID_AND_ATTRIBUTES * const,ulong)
0x1801068db  mov     [rdi], r13d
0x1801068de  mov     eax, ebx
0x1801068e0  mov     rcx, [rbp+4Fh+var_50]
0x1801068e4  xor     rcx, rsp; StackCookie
0x1801068e7  call    __security_check_cookie
0x1801068ec  add     rsp, 0B8h
0x1801068f3  pop     r15
0x1801068f5  pop     r14
0x1801068f7  pop     r13
0x1801068f9  pop     r12
0x1801068fb  pop     rdi
0x1801068fc  pop     rsi
0x1801068fd  pop     rbx
0x1801068fe  pop     rbp
0x1801068ff  retn
```
