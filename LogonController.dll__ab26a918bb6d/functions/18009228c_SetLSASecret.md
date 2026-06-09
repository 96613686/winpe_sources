# _SetLSASecret

- ea: `0x18009228c`
- end: `0x180092338`
- name: `_SetLSASecret`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180065c38`

## callees

- `0x180064e40`
- `0x18009228c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800922f1`
- `ntdll!RtlInitUnicodeString` at `0x1800922fd`
- `ntdll!RtlInitUnicodeString` at `0x1800922f1`
- `ntdll!RtlInitUnicodeString` at `0x1800922fd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180092322`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180092322`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800922c5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800922c5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x18009230f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x18009230f`

## pseudocode

```c
__int64 SetLSASecret()
{
  NTSTATUS v0; // eax
  int v1; // ebx
  NTSTATUS v2; // eax
  struct _UNICODE_STRING v4; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  PVOID PolicyHandle; // [rsp+88h] [rbp+18h] BYREF

  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v0 = LsaOpenPolicy(0, &ObjectAttributes, 0x20u, &PolicyHandle);
  v1 = ResultFromWin32FromStatus(v0);
  if ( v1 >= 0 )
  {
    DestinationString = 0;
    v4 = 0;
    RtlInitUnicodeString(&DestinationString, L"DefaultPassword");
    RtlInitUnicodeString(&v4, 0);
    v2 = LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, (PLSA_UNICODE_STRING)&v4);
    v1 = ResultFromWin32FromStatus(v2);
    LsaClose(PolicyHandle);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18009228c  mov     [rsp-8+arg_0], rbx
0x180092291  mov     [rsp-8+PolicyHandle], rdx
0x180092296  push    rbp
0x180092297  mov     rbp, rsp
0x18009229a  sub     rsp, 70h
0x18009229e  xorps   xmm0, xmm0
0x1800922a1  mov     [rbp+PolicyHandle], 0
0x1800922a9  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1800922ad  mov     r8d, 20h ; ' '; DesiredAccess
0x1800922b3  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800922b7  xor     ecx, ecx; SystemName
0x1800922b9  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800922bd  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800922c1  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800922c5  call    cs:__imp_LsaOpenPolicy
0x1800922cb  mov     ecx, eax; int
0x1800922cd  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x1800922d2  mov     ebx, eax
0x1800922d4  test    eax, eax
0x1800922d6  js      short loc_180092328
0x1800922d8  xorps   xmm0, xmm0
0x1800922db  lea     rdx, SourceString; "DefaultPassword"
0x1800922e2  xorps   xmm1, xmm1
0x1800922e5  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800922e9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800922ed  movups  xmmword ptr [rbp+var_50.Length], xmm1
0x1800922f1  call    cs:__imp_RtlInitUnicodeString
0x1800922f7  xor     edx, edx; SourceString
0x1800922f9  lea     rcx, [rbp+var_50]; DestinationString
0x1800922fd  call    cs:__imp_RtlInitUnicodeString
0x180092303  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180092307  lea     r8, [rbp+var_50]; PrivateData
0x18009230b  lea     rdx, [rbp+DestinationString]; KeyName
0x18009230f  call    cs:__imp_LsaStorePrivateData
0x180092315  mov     ecx, eax; int
0x180092317  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18009231c  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180092320  mov     ebx, eax
0x180092322  call    cs:__imp_LsaClose
0x180092328  mov     eax, ebx
0x18009232a  mov     rbx, [rsp+70h+arg_0]
0x180092332  add     rsp, 70h
0x180092336  pop     rbp
0x180092337  retn
```
