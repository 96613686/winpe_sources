# WorkerModule::InitializeComSecurity(void)

- ea: `0x1400c3a80`
- end: `0x1400c3cd8`
- name: `?InitializeComSecurity@WorkerModule@@QEAAXXZ`
- size: `600`
- prototype: `void __fastcall(WorkerModule *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400c3720`

## callees

- `0x14005b628`
- `0x14006af38`
- `0x1400c3a80`
- `0x1400c3e2c`
- `0x1400c3eb8`
- `0x1400c3f44`
- `0x1400c40cc`
- `0x1400c419c`
- `0x1400c4290`
- `0x1400c4358`
- `0x1400c4394`
- `0x1400c5c6c`
- `0x140132940`
- `0x1401335fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400c3b2d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400c3b2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400c3b15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400c3b15`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400c3c51`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400c3c51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c3b87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c3c85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c3cae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c3b87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c3c85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c3cae`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400c3bf5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400c3bf5`

## string_xrefs

- `0x1400c3b41`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1400c3c09`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall WorkerModule::InitializeComSecurity(WorkerModule *this, __int64 a2, unsigned int a3)
{
  HANDLE CurrentProcess; // rax
  enum _TOKEN_INFORMATION_CLASS v4; // edx
  const char *v5; // r9
  struct _ACL *Information; // rbx
  const struct _ACL *Dacl; // rax
  const struct _ACL *v8; // rax
  unsigned int v9; // r8d
  unsigned int v10; // r9d
  PSECURITY_DESCRIPTOR v11; // rbx
  const char *v12; // r9
  HRESULT v13; // eax
  enum _ACCESS_MODE dwAuthnLevel; // [rsp+20h] [rbp-69h]
  DWORD dwAuthnLevela; // [rsp+20h] [rbp-69h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor[2]; // [rsp+50h] [rbp-39h] BYREF
  PACL pDacl[2]; // [rsp+60h] [rbp-29h] BYREF
  void *TokenHandle[2]; // [rsp+70h] [rbp-19h] BYREF
  void *v19; // [rsp+80h] [rbp-9h] BYREF
  int v20; // [rsp+88h] [rbp-1h]
  __int128 v21; // [rsp+90h] [rbp+7h]
  __m128i si128; // [rsp+A0h] [rbp+17h]
  __int128 v23; // [rsp+B0h] [rbp+27h]
  __m128i v24; // [rsp+C0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  *(_OWORD *)pSecurityDescriptor = 0;
  Vml::VmSecurityDescriptor::Assign(
    (Vml::VmSecurityDescriptor *)pSecurityDescriptor,
    L"O:BAG:BAD:(A;OICI;0x3;;;SY)(A;OICI;0x3;;;BA)(A;OICI;0x3;;;HA)",
    a3);
  Vml::VmSecurityDescriptor::MakeAbsolute((Vml::VmSecurityDescriptor *)pSecurityDescriptor);
  TokenHandle[0] = 0;
  memset_0(&v19, 0, 0x50u);
  v19 = 0;
  v20 = 7;
  v21 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v21) = 0;
  v23 = 0;
  v24 = si128;
  LOWORD(v23) = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CE7,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v5);
  *(_OWORD *)pDacl = 0;
  Information = (struct _ACL *)Vml::VmAccessToken::_GetInformation((Vml::VmAccessToken *)TokenHandle, v4);
  pDacl[0] = Information;
  Vml::VmSid::Assign((Vml::VmSid *)&v19, *(void **)Information);
  if ( Information )
    LocalFree(Information);
  *(_OWORD *)pDacl = 0;
  Dacl = Vml::VmSecurityDescriptor::GetDacl((Vml::VmSecurityDescriptor *)pSecurityDescriptor);
  pDacl[0] = 0;
  Vml::VmAcl::Assign((Vml::VmAcl *)pDacl, Dacl);
  v8 = Vml::VmSecurityDescriptor::GetDacl((Vml::VmSecurityDescriptor *)pSecurityDescriptor);
  Vml::VmAcl::Assign((Vml::VmAcl *)pDacl, v8);
  Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, v19, v9, v10, dwAuthnLevel);
  Vml::VmSecurityDescriptor::MakeAbsolute((Vml::VmSecurityDescriptor *)pSecurityDescriptor);
  v11 = pSecurityDescriptor[0];
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor[0], 1, pDacl[0], 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xDD6,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v12);
  v13 = CoInitializeSecurity(v11, -1, 0, 0, 5u, 2u, 0, 0x5002u, 0);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x477,
      (unsigned int)"onecore\\vm\\worker\\wpexe\\workermodule.cpp",
      (const char *)(unsigned int)v13,
      dwAuthnLevela);
  if ( pDacl[0] )
    LocalFree(pDacl[0]);
  Vml::VmSid::~VmSid((Vml::VmSid *)&v19);
  Vml::VmAccessToken::~VmAccessToken((Vml::VmAccessToken *)TokenHandle);
  if ( v11 )
    LocalFree(v11);
}

```

## disassembly

```asm
0x1400c3a80  mov     [rsp-8+arg_0], rbx
0x1400c3a85  push    rbp
0x1400c3a86  lea     rbp, [rsp-57h]
0x1400c3a8b  sub     rsp, 0E0h
0x1400c3a92  mov     rax, cs:__security_cookie
0x1400c3a99  xor     rax, rsp
0x1400c3a9c  mov     [rbp+57h+var_10], rax
0x1400c3aa0  xorps   xmm0, xmm0
0x1400c3aa3  movups  xmmword ptr [rbp+57h+pSecurityDescriptor], xmm0
0x1400c3aa7  mov     [rbp+57h+pSecurityDescriptor], 0
0x1400c3aaf  lea     rdx, aOBagBadAOici0x; "O:BAG:BAD:(A;OICI;0x3;;;SY)(A;OICI;0x3;"...
0x1400c3ab6  lea     rcx, [rbp+57h+pSecurityDescriptor]; this
0x1400c3aba  call    ?Assign@VmSecurityDescriptor@Vml@@QEAAXPEBGK@Z; Vml::VmSecurityDescriptor::Assign(ushort const *,ulong)
0x1400c3abf  lea     rcx, [rbp+57h+pSecurityDescriptor]; this
0x1400c3ac3  call    ?MakeAbsolute@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::MakeAbsolute(void)
0x1400c3ac8  mov     [rbp+57h+TokenHandle], 0
0x1400c3ad0  xor     edx, edx; Val
0x1400c3ad2  lea     r8d, [rdx+50h]; Size
0x1400c3ad6  lea     rcx, [rbp+57h+var_60]; void *
0x1400c3ada  call    memset_0
0x1400c3adf  mov     [rbp+57h+var_60], 0
0x1400c3ae7  mov     [rbp+57h+var_58], 7
0x1400c3aee  xorps   xmm0, xmm0
0x1400c3af1  movups  [rbp+57h+var_50], xmm0
0x1400c3af5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400c3afd  movdqa  [rbp+57h+var_40], xmm1
0x1400c3b02  xor     eax, eax
0x1400c3b04  mov     word ptr [rbp+57h+var_50], ax
0x1400c3b08  movups  [rbp+57h+var_30], xmm0
0x1400c3b0c  movdqa  [rbp+57h+var_20], xmm1
0x1400c3b11  mov     word ptr [rbp+57h+var_30], ax
0x1400c3b15  call    cs:__imp_GetCurrentProcess
0x1400c3b1c  nop     dword ptr [rax+rax+00h]
0x1400c3b21  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1400c3b25  mov     edx, 8; DesiredAccess
0x1400c3b2a  mov     rcx, rax; ProcessHandle
0x1400c3b2d  call    cs:__imp_OpenProcessToken
0x1400c3b34  nop     dword ptr [rax+rax+00h]
0x1400c3b39  mov     rcx, [rbp+5Fh]; this
0x1400c3b3d  test    eax, eax
0x1400c3b3f  jnz     short loc_1400C3B53
0x1400c3b41  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400c3b48  mov     edx, 1CE7h; void *
0x1400c3b4d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400c3b53  xorps   xmm0, xmm0
0x1400c3b56  movups  xmmword ptr [rbp+57h+pDacl], xmm0
0x1400c3b5a  mov     [rbp+57h+pDacl], 0
0x1400c3b62  lea     rcx, [rbp+57h+TokenHandle]; this
0x1400c3b66  call    ?_GetInformation@VmAccessToken@Vml@@AEBAPEAXW4_TOKEN_INFORMATION_CLASS@@@Z; Vml::VmAccessToken::_GetInformation(_TOKEN_INFORMATION_CLASS)
0x1400c3b6b  mov     rbx, rax
0x1400c3b6e  mov     [rbp+57h+pDacl], rax
0x1400c3b72  mov     rdx, [rax]; void *
0x1400c3b75  lea     rcx, [rbp+57h+var_60]; this
0x1400c3b79  call    ?Assign@VmSid@Vml@@QEAAXPEAX@Z; Vml::VmSid::Assign(void *)
0x1400c3b7e  nop
0x1400c3b7f  test    rbx, rbx
0x1400c3b82  jz      short loc_1400C3B93
0x1400c3b84  mov     rcx, rbx; hMem
0x1400c3b87  call    cs:__imp_LocalFree
0x1400c3b8e  nop     dword ptr [rax+rax+00h]
0x1400c3b93  xorps   xmm0, xmm0
0x1400c3b96  movups  xmmword ptr [rbp+57h+pDacl], xmm0
0x1400c3b9a  lea     rcx, [rbp+57h+pSecurityDescriptor]; this
0x1400c3b9e  call    ?GetDacl@VmSecurityDescriptor@Vml@@QEBAPEBU_ACL@@XZ; Vml::VmSecurityDescriptor::GetDacl(void)
0x1400c3ba3  mov     [rbp+57h+pDacl], 0
0x1400c3bab  mov     rdx, rax; struct _ACL *
0x1400c3bae  lea     rcx, [rbp+57h+pDacl]; this
0x1400c3bb2  call    ?Assign@VmAcl@Vml@@QEAAXPEBU_ACL@@@Z; Vml::VmAcl::Assign(_ACL const *)
0x1400c3bb7  nop
0x1400c3bb8  lea     rcx, [rbp+57h+pSecurityDescriptor]; this
0x1400c3bbc  call    ?GetDacl@VmSecurityDescriptor@Vml@@QEBAPEBU_ACL@@XZ; Vml::VmSecurityDescriptor::GetDacl(void)
0x1400c3bc1  mov     rdx, rax; struct _ACL *
0x1400c3bc4  lea     rcx, [rbp+57h+pDacl]; this
0x1400c3bc8  call    ?Assign@VmAcl@Vml@@QEAAXPEBU_ACL@@@Z; Vml::VmAcl::Assign(_ACL const *)
0x1400c3bcd  mov     rdx, [rbp+57h+var_60]; void *
0x1400c3bd1  lea     rcx, [rbp+57h+pDacl]; this
0x1400c3bd5  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x1400c3bda  lea     rcx, [rbp+57h+pSecurityDescriptor]; this
0x1400c3bde  call    ?MakeAbsolute@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::MakeAbsolute(void)
0x1400c3be3  xor     r9d, r9d; bDaclDefaulted
0x1400c3be6  mov     r8, [rbp+57h+pDacl]; pDacl
0x1400c3bea  lea     edx, [r9+1]; bDaclPresent
0x1400c3bee  mov     rbx, [rbp+57h+pSecurityDescriptor]
0x1400c3bf2  mov     rcx, rbx; pSecurityDescriptor
0x1400c3bf5  call    cs:__imp_SetSecurityDescriptorDacl
0x1400c3bfc  nop     dword ptr [rax+rax+00h]
0x1400c3c01  mov     rcx, [rbp+5Fh]; this
0x1400c3c05  test    eax, eax
0x1400c3c07  jnz     short loc_1400C3C1B
0x1400c3c09  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400c3c10  mov     edx, 0DD6h; void *
0x1400c3c15  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400c3c1b  mov     [rsp+0E0h+pReserved3], 0; pReserved3
0x1400c3c24  mov     [rsp+0E0h+dwCapabilities], 5002h; dwCapabilities
0x1400c3c2c  mov     [rsp+0E0h+pAuthList], 0; pAuthList
0x1400c3c35  mov     [rsp+0E0h+dwImpLevel], 2; dwImpLevel
0x1400c3c3d  mov     [rsp+0E0h+dwAuthnLevel], 5; int
0x1400c3c45  xor     r9d, r9d; pReserved1
0x1400c3c48  xor     r8d, r8d; asAuthSvc
0x1400c3c4b  or      edx, 0FFFFFFFFh; cAuthSvc
0x1400c3c4e  mov     rcx, rbx; pSecDesc
0x1400c3c51  call    cs:__imp_CoInitializeSecurity
0x1400c3c58  nop     dword ptr [rax+rax+00h]
0x1400c3c5d  mov     rcx, [rbp+5Fh]; this
0x1400c3c61  test    eax, eax
0x1400c3c63  jns     short loc_1400C3C7A
0x1400c3c65  mov     r9d, eax; char *
0x1400c3c68  lea     r8, aOnecoreVmWorke_1; "onecore\\vm\\worker\\wpexe\\workermodul"...
0x1400c3c6f  mov     edx, 477h; void *
0x1400c3c74  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400c3c7a  cmp     [rbp+57h+pDacl], 0
0x1400c3c7f  jz      short loc_1400C3C92
0x1400c3c81  mov     rcx, [rbp+57h+pDacl]; hMem
0x1400c3c85  call    cs:__imp_LocalFree
0x1400c3c8c  nop     dword ptr [rax+rax+00h]
0x1400c3c91  nop
0x1400c3c92  lea     rcx, [rbp+57h+var_60]; this
0x1400c3c96  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x1400c3c9b  nop
0x1400c3c9c  lea     rcx, [rbp+57h+TokenHandle]; this
0x1400c3ca0  call    ??1VmAccessToken@Vml@@QEAA@XZ; Vml::VmAccessToken::~VmAccessToken(void)
0x1400c3ca5  nop
0x1400c3ca6  test    rbx, rbx
0x1400c3ca9  jz      short loc_1400C3CBA
0x1400c3cab  mov     rcx, rbx; hMem
0x1400c3cae  call    cs:__imp_LocalFree
0x1400c3cb5  nop     dword ptr [rax+rax+00h]
0x1400c3cba  mov     rcx, [rbp+57h+var_10]
0x1400c3cbe  xor     rcx, rsp; StackCookie
0x1400c3cc1  call    __security_check_cookie
0x1400c3cc6  mov     rbx, [rsp+0E0h+arg_0]
0x1400c3cce  add     rsp, 0E0h
0x1400c3cd5  pop     rbp
0x1400c3cd6  retn
```
