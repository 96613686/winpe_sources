# GetThreadAuthenticationId

- ea: `0x180006990`
- end: `0x180006ada`
- name: `GetThreadAuthenticationId`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006740`

## callees

- `0x180006990`
- `0x18000db40`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180006a38`
- `ntdll!RtlAllocateHeap` at `0x180006a38`
- `ntdll!RtlFreeHeap` at `0x180006aa9`
- `ntdll!RtlFreeHeap` at `0x180006aa9`
- `ntdll!RtlCopyLuid` at `0x180006a14`
- `ntdll!RtlCopyLuid` at `0x180006a14`
- `ntdll!NtQueryInformationToken` at `0x1800069f6`
- `ntdll!NtQueryInformationToken` at `0x180006a6b`
- `ntdll!NtQueryInformationToken` at `0x1800069f6`
- `ntdll!NtQueryInformationToken` at `0x180006a6b`
- `ntdll!RtlCopySid` at `0x180006a8b`
- `ntdll!RtlCopySid` at `0x180006a8b`

## pseudocode

```c
__int64 GetThreadAuthenticationId()
{
  char *v0; // rsi
  NTSTATUS v1; // edi
  PSID *Heap; // rbx
  ULONG DestinationSidLength; // [rsp+30h] [rbp-58h] BYREF
  _OWORD TokenInformation[3]; // [rsp+38h] [rbp-50h] BYREF
  __int64 v6; // [rsp+68h] [rbp-20h]

  v0 = (char *)pNlsRegUserInfo;
  v6 = 0;
  DestinationSidLength = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v1 = NtQueryInformationToken(
         (HANDLE)0xFFFFFFFFFFFFFFFBLL,
         TokenStatistics,
         TokenInformation,
         0x38u,
         &DestinationSidLength);
  if ( v1 >= 0 )
    RtlCopyLuid((PLUID)(v0 + 1580), (PLUID)TokenInformation + 1);
  Heap = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x54u);
  if ( Heap )
  {
    v1 = NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenUser, Heap, 0x54u, &DestinationSidLength);
    if ( v1 >= 0 )
      RtlCopySid(DestinationSidLength, v0 + 1588, *Heap);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180006990  mov     [rsp+arg_0], rbx
0x180006995  mov     [rsp+arg_8], rsi
0x18000699a  push    rdi
0x18000699b  sub     rsp, 80h
0x1800069a2  mov     rax, cs:__security_cookie
0x1800069a9  xor     rax, rsp
0x1800069ac  mov     [rsp+88h+var_18], rax
0x1800069b1  mov     rsi, cs:pNlsRegUserInfo
0x1800069b8  lea     r8, [rsp+88h+TokenInformation]; TokenInformation
0x1800069bd  xor     eax, eax
0x1800069bf  xorps   xmm0, xmm0
0x1800069c2  mov     [rsp+88h+var_20], rax
0x1800069c7  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800069cd  mov     [rsp+88h+DestinationSidLength], eax
0x1800069d1  mov     edx, 0Ah; TokenInformationClass
0x1800069d6  lea     rax, [rsp+88h+DestinationSidLength]
0x1800069db  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x1800069e2  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x1800069e7  movups  [rsp+88h+TokenInformation], xmm0
0x1800069ec  movups  [rsp+88h+var_40], xmm0
0x1800069f1  movups  [rsp+88h+var_30], xmm0
0x1800069f6  call    cs:__imp_NtQueryInformationToken
0x1800069fd  nop     dword ptr [rax+rax+00h]
0x180006a02  mov     edi, eax
0x180006a04  test    eax, eax
0x180006a06  js      short loc_180006A20
0x180006a08  lea     rcx, [rsi+62Ch]; DestinationLuid
0x180006a0f  lea     rdx, [rsp+88h+TokenInformation+8]; SourceLuid
0x180006a14  call    cs:__imp_RtlCopyLuid
0x180006a1b  nop     dword ptr [rax+rax+00h]
0x180006a20  mov     rcx, gs:60h
0x180006a29  mov     edx, 8; Flags
0x180006a2e  mov     r8d, 54h ; 'T'; Size
0x180006a34  mov     rcx, [rcx+30h]; HeapHandle
0x180006a38  call    cs:__imp_RtlAllocateHeap
0x180006a3f  nop     dword ptr [rax+rax+00h]
0x180006a44  mov     rbx, rax
0x180006a47  test    rax, rax
0x180006a4a  jz      short loc_180006AB5
0x180006a4c  lea     rax, [rsp+88h+DestinationSidLength]
0x180006a51  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180006a57  mov     r8, rbx; TokenInformation
0x180006a5a  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x180006a5f  mov     edx, 1; TokenInformationClass
0x180006a64  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x180006a6b  call    cs:__imp_NtQueryInformationToken
0x180006a72  nop     dword ptr [rax+rax+00h]
0x180006a77  mov     edi, eax
0x180006a79  test    eax, eax
0x180006a7b  js      short loc_180006A97
0x180006a7d  mov     r8, [rbx]; SourceSid
0x180006a80  lea     rdx, [rsi+634h]; DestinationSid
0x180006a87  mov     ecx, [rsp+88h+DestinationSidLength]; DestinationSidLength
0x180006a8b  call    cs:__imp_RtlCopySid
0x180006a92  nop     dword ptr [rax+rax+00h]
0x180006a97  mov     rcx, gs:60h
0x180006aa0  mov     r8, rbx; P
0x180006aa3  xor     edx, edx; Flags
0x180006aa5  mov     rcx, [rcx+30h]; HeapHandle
0x180006aa9  call    cs:__imp_RtlFreeHeap
0x180006ab0  nop     dword ptr [rax+rax+00h]
0x180006ab5  mov     eax, edi
0x180006ab7  mov     rcx, [rsp+88h+var_18]
0x180006abc  xor     rcx, rsp; StackCookie
0x180006abf  call    __security_check_cookie
0x180006ac4  lea     r11, [rsp+88h+var_8]
0x180006acc  mov     rbx, [r11+10h]
0x180006ad0  mov     rsi, [r11+18h]
0x180006ad4  mov     rsp, r11
0x180006ad7  pop     rdi
0x180006ad8  retn
```
