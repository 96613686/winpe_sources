# GetThreadAuthenticationId

- ea: `0x180006700`
- end: `0x180006846`
- name: `GetThreadAuthenticationId`
- size: `326`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800064c0`

## callees

- `0x180006700`
- `0x18000d730`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800067a5`
- `ntdll!RtlAllocateHeap` at `0x1800067a5`
- `ntdll!RtlFreeHeap` at `0x180006815`
- `ntdll!RtlFreeHeap` at `0x180006815`
- `ntdll!RtlCopyLuid` at `0x180006783`
- `ntdll!RtlCopyLuid` at `0x180006783`
- `ntdll!NtQueryInformationToken` at `0x180006765`
- `ntdll!NtQueryInformationToken` at `0x1800067d7`
- `ntdll!NtQueryInformationToken` at `0x180006765`
- `ntdll!NtQueryInformationToken` at `0x1800067d7`
- `ntdll!RtlCopySid` at `0x1800067f7`
- `ntdll!RtlCopySid` at `0x1800067f7`

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
0x180006700  mov     [rsp+arg_0], rbx
0x180006705  mov     [rsp+arg_8], rsi
0x18000670a  push    rdi
0x18000670b  sub     rsp, 80h
0x180006712  mov     rax, cs:__security_cookie
0x180006719  xor     rax, rsp
0x18000671c  mov     [rsp+88h+var_18], rax
0x180006721  mov     rsi, cs:pNlsRegUserInfo
0x180006728  lea     r8, [rsp+88h+TokenInformation]; TokenInformation
0x18000672d  xor     eax, eax
0x18000672f  xorps   xmm0, xmm0
0x180006732  mov     r9d, 38h ; '8'; TokenInformationLength
0x180006738  mov     [rsp+88h+var_20], rax
0x18000673d  mov     [rsp+88h+DestinationSidLength], eax
0x180006741  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x180006748  lea     rax, [rsp+88h+DestinationSidLength]
0x18000674d  movups  [rsp+88h+TokenInformation], xmm0
0x180006752  lea     edx, [r9-2Eh]; TokenInformationClass
0x180006756  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x18000675b  movups  [rsp+88h+var_40], xmm0
0x180006760  movups  [rsp+88h+var_30], xmm0
0x180006765  call    cs:__imp_NtQueryInformationToken
0x18000676c  nop     dword ptr [rax+rax+00h]
0x180006771  mov     edi, eax
0x180006773  test    eax, eax
0x180006775  js      short loc_18000678F
0x180006777  lea     rcx, [rsi+62Ch]; DestinationLuid
0x18000677e  lea     rdx, [rsp+88h+TokenInformation+8]; SourceLuid
0x180006783  call    cs:__imp_RtlCopyLuid
0x18000678a  nop     dword ptr [rax+rax+00h]
0x18000678f  mov     rcx, gs:60h
0x180006798  mov     edx, 8; Flags
0x18000679d  mov     rcx, [rcx+30h]; HeapHandle
0x1800067a1  lea     r8d, [rdx+4Ch]; Size
0x1800067a5  call    cs:__imp_RtlAllocateHeap
0x1800067ac  nop     dword ptr [rax+rax+00h]
0x1800067b1  mov     rbx, rax
0x1800067b4  test    rax, rax
0x1800067b7  jz      short loc_180006821
0x1800067b9  mov     r9d, 54h ; 'T'; TokenInformationLength
0x1800067bf  lea     rax, [rsp+88h+DestinationSidLength]
0x1800067c4  mov     r8, rbx; TokenInformation
0x1800067c7  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x1800067cc  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x1800067d3  lea     edx, [r9-53h]; TokenInformationClass
0x1800067d7  call    cs:__imp_NtQueryInformationToken
0x1800067de  nop     dword ptr [rax+rax+00h]
0x1800067e3  mov     edi, eax
0x1800067e5  test    eax, eax
0x1800067e7  js      short loc_180006803
0x1800067e9  mov     r8, [rbx]; SourceSid
0x1800067ec  lea     rdx, [rsi+634h]; DestinationSid
0x1800067f3  mov     ecx, [rsp+88h+DestinationSidLength]; DestinationSidLength
0x1800067f7  call    cs:__imp_RtlCopySid
0x1800067fe  nop     dword ptr [rax+rax+00h]
0x180006803  mov     rcx, gs:60h
0x18000680c  mov     r8, rbx; P
0x18000680f  xor     edx, edx; Flags
0x180006811  mov     rcx, [rcx+30h]; HeapHandle
0x180006815  call    cs:__imp_RtlFreeHeap
0x18000681c  nop     dword ptr [rax+rax+00h]
0x180006821  mov     eax, edi
0x180006823  mov     rcx, [rsp+88h+var_18]
0x180006828  xor     rcx, rsp; StackCookie
0x18000682b  call    __security_check_cookie
0x180006830  lea     r11, [rsp+88h+var_8]
0x180006838  mov     rbx, [r11+10h]
0x18000683c  mov     rsi, [r11+18h]
0x180006840  mov     rsp, r11
0x180006843  pop     rdi
0x180006844  retn
```
