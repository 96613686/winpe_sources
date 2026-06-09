# Broker::CreateSd(void *,ulong,void *,ulong)

- ea: `0x180013228`
- end: `0x1800133b4`
- name: `?CreateSd@Broker@@YAPEAXPEAXK0K@Z`
- size: `396`
- prototype: `void *__fastcall(PSID Owner, void *, __int64, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800131b0`

## callees

- `0x180013228`
- `0x18001cf50`

## import_xrefs

- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18001336f`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18001336f`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800132a0`
- `ntdll!RtlAddAccessAllowedAce` at `0x180013307`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800132a0`
- `ntdll!RtlAddAccessAllowedAce` at `0x180013307`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800132d5`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800132d5`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18001331b`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18001331b`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18001332c`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18001332c`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180013337`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180013337`
- `ntdll!RtlFreeHeap` at `0x180013390`
- `ntdll!RtlFreeHeap` at `0x180013390`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800132ed`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800132ed`
- `ntdll!RtlCreateAcl` at `0x180013285`
- `ntdll!RtlCreateAcl` at `0x180013285`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013354`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013354`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013343`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013343`

## pseudocode

```c
void *__fastcall Broker::CreateSd(PSID Owner, void *a2, __int64 a3, void *a4)
{
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  void *v7; // rax
  ULONG BufferLength; // [rsp+60h] [rbp-A0h] BYREF
  PSID P; // [rsp+68h] [rbp-98h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v12; // [rsp+90h] [rbp-70h]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+98h] [rbp-68h] BYREF
  _ACL Acl; // [rsp+A0h] [rbp-60h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  P = 0;
  BufferLength = 0;
  v12 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v5 = 0;
  RtlCreateAcl(&Acl, 0x400u, 2u);
  if ( Owner )
    RtlAddAccessAllowedAce(&Acl, 2u, 0x80000000, Owner);
  if ( RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &P) >= 0 )
  {
    RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
    RtlAddAccessAllowedAce(&Acl, 2u, 0x10000000u, P);
    RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, &Acl, 0);
    RtlSetOwnerSecurityDescriptor(SecurityDescriptor, Owner, 0);
    BufferLength = RtlLengthSecurityDescriptor(SecurityDescriptor);
    ProcessHeap = GetProcessHeap();
    v7 = HeapAlloc(ProcessHeap, 8u, BufferLength);
    v5 = v7;
    if ( v7 )
      RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v7, &BufferLength);
  }
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return v5;
}

```

## disassembly

```asm
0x180013228  push    rbp
0x18001322a  push    rbx
0x18001322b  push    rsi
0x18001322c  push    rdi
0x18001322d  lea     rbp, [rsp-3B8h]
0x180013235  sub     rsp, 4B8h
0x18001323c  mov     rax, cs:__security_cookie
0x180013243  xor     rax, rsp
0x180013246  mov     [rbp+3D0h+var_30], rax
0x18001324d  xor     esi, esi
0x18001324f  mov     word ptr [rbp+3D0h+IdentifierAuthority.Value+4], 500h
0x180013255  xorps   xmm0, xmm0
0x180013258  mov     dword ptr [rbp+3D0h+IdentifierAuthority.Value], esi
0x18001325b  mov     rdi, rcx
0x18001325e  mov     [rsp+4D0h+P], rsi
0x180013263  xor     eax, eax
0x180013265  mov     [rsp+4D0h+BufferLength], esi
0x180013269  lea     r8d, [rsi+2]; AclRevision
0x18001326d  mov     [rbp+3D0h+var_440], rax
0x180013271  mov     edx, 400h; AclSize
0x180013276  lea     rcx, [rbp+3D0h+Acl]; Acl
0x18001327a  movups  [rsp+4D0h+SecurityDescriptor], xmm0
0x18001327f  mov     ebx, esi
0x180013281  movups  [rbp+3D0h+var_450], xmm0
0x180013285  call    cs:__imp_RtlCreateAcl
0x18001328b  test    rdi, rdi
0x18001328e  jz      short loc_1800132A6
0x180013290  mov     r9, rdi; Sid
0x180013293  lea     edx, [rsi+2]; Revision
0x180013296  mov     r8d, 80000000h; AccessMask
0x18001329c  lea     rcx, [rbp+3D0h+Acl]; Acl
0x1800132a0  call    cs:__imp_RtlAddAccessAllowedAce
0x1800132a6  lea     rax, [rsp+4D0h+P]
0x1800132ab  xor     r9d, r9d; SubAuthority1
0x1800132ae  mov     [rsp+4D0h+Sid], rax; Sid
0x1800132b3  lea     rcx, [rbp+3D0h+IdentifierAuthority]; IdentifierAuthority
0x1800132b7  mov     [rsp+4D0h+SubAuthority7], esi; SubAuthority7
0x1800132bb  mov     dl, 1; SubAuthorityCount
0x1800132bd  mov     [rsp+4D0h+SubAuthority6], esi; SubAuthority6
0x1800132c1  mov     [rsp+4D0h+SubAuthority5], esi; SubAuthority5
0x1800132c5  lea     r8d, [r9+12h]; SubAuthority0
0x1800132c9  mov     [rsp+4D0h+SubAuthority4], esi; SubAuthority4
0x1800132cd  mov     [rsp+4D0h+SubAuthority3], esi; SubAuthority3
0x1800132d1  mov     [rsp+4D0h+SubAuthority2], esi; SubAuthority2
0x1800132d5  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800132db  test    eax, eax
0x1800132dd  js      loc_180013375
0x1800132e3  mov     edx, 1; Revision
0x1800132e8  lea     rcx, [rsp+4D0h+SecurityDescriptor]; SecurityDescriptor
0x1800132ed  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800132f3  mov     r9, [rsp+4D0h+P]; Sid
0x1800132f8  lea     rcx, [rbp+3D0h+Acl]; Acl
0x1800132fc  mov     edx, 2; Revision
0x180013301  mov     r8d, 10000000h; AccessMask
0x180013307  call    cs:__imp_RtlAddAccessAllowedAce
0x18001330d  xor     r9d, r9d; DaclDefaulted
0x180013310  lea     r8, [rbp+3D0h+Acl]; Dacl
0x180013314  mov     dl, 1; DaclPresent
0x180013316  lea     rcx, [rsp+4D0h+SecurityDescriptor]; SecurityDescriptor
0x18001331b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180013321  xor     r8d, r8d; OwnerDefaulted
0x180013324  lea     rcx, [rsp+4D0h+SecurityDescriptor]; SecurityDescriptor
0x180013329  mov     rdx, rdi; Owner
0x18001332c  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180013332  lea     rcx, [rsp+4D0h+SecurityDescriptor]; SecurityDescriptor
0x180013337  call    cs:__imp_RtlLengthSecurityDescriptor
0x18001333d  mov     ebx, eax
0x18001333f  mov     [rsp+4D0h+BufferLength], ebx
0x180013343  call    cs:__imp_GetProcessHeap
0x180013349  mov     r8d, ebx; dwBytes
0x18001334c  mov     edx, 8; dwFlags
0x180013351  mov     rcx, rax; hHeap
0x180013354  call    cs:__imp_HeapAlloc
0x18001335a  mov     rbx, rax
0x18001335d  test    rax, rax
0x180013360  jz      short loc_180013375
0x180013362  lea     r8, [rsp+4D0h+BufferLength]; BufferLength
0x180013367  mov     rdx, rax; SelfRelativeSecurityDescriptor
0x18001336a  lea     rcx, [rsp+4D0h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18001336f  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x180013375  cmp     [rsp+4D0h+P], rsi
0x18001337a  jz      short loc_180013396
0x18001337c  mov     rcx, gs:60h
0x180013385  xor     edx, edx; Flags
0x180013387  mov     r8, [rsp+4D0h+P]; P
0x18001338c  mov     rcx, [rcx+30h]; HeapHandle
0x180013390  call    cs:__imp_RtlFreeHeap
0x180013396  mov     rax, rbx
0x180013399  mov     rcx, [rbp+3D0h+var_30]
0x1800133a0  xor     rcx, rsp; StackCookie
0x1800133a3  call    __security_check_cookie
0x1800133a8  add     rsp, 4B8h
0x1800133af  pop     rdi
0x1800133b0  pop     rsi
0x1800133b1  pop     rbx
0x1800133b2  pop     rbp
0x1800133b3  retn
```
