# CodeAuthzpGetTokenInformation

- ea: `0x18000fb50`
- end: `0x18000fc88`
- name: `CodeAuthzpGetTokenInformation`
- size: `312`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, TOKEN_INFORMATION_CLASS TokenInformationClass)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000f5ac`
- `0x18000f840`
- `0x18000fc88`

## callees

- `0x18000fb50`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000fbf5`
- `ntdll!RtlFreeHeap` at `0x18000fc63`
- `ntdll!RtlFreeHeap` at `0x18000fbf5`
- `ntdll!RtlFreeHeap` at `0x18000fc63`
- `ntdll!NtQueryInformationToken` at `0x18000fbb4`
- `ntdll!NtQueryInformationToken` at `0x18000fc40`
- `ntdll!NtQueryInformationToken` at `0x18000fbb4`
- `ntdll!NtQueryInformationToken` at `0x18000fc40`
- `ntdll!RtlAllocateHeap` at `0x18000fb80`
- `ntdll!RtlAllocateHeap` at `0x18000fc15`
- `ntdll!RtlAllocateHeap` at `0x18000fb80`
- `ntdll!RtlAllocateHeap` at `0x18000fc15`

## pseudocode

```c
PVOID __fastcall CodeAuthzpGetTokenInformation(HANDLE TokenHandle, TOKEN_INFORMATION_CLASS TokenInformationClass)
{
  PVOID result; // rax
  PVOID Heap; // rbx
  NTSTATUS v6; // eax
  ULONG TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF

  result = 0;
  if ( TokenHandle )
  {
    result = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x80u);
    Heap = result;
    if ( result )
    {
      TokenInformationLength = 0;
      v6 = NtQueryInformationToken(TokenHandle, TokenInformationClass, result, 0x80u, &TokenInformationLength);
      if ( v6 == -1073741789 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, TokenInformationLength);
        if ( !Heap )
          goto LABEL_9;
        v6 = NtQueryInformationToken(
               TokenHandle,
               TokenInformationClass,
               Heap,
               TokenInformationLength,
               &TokenInformationLength);
      }
      if ( v6 >= 0 )
        return Heap;
LABEL_9:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000fb50  mov     [rsp+arg_10], rsi
0x18000fb55  push    rdi
0x18000fb56  sub     rsp, 30h
0x18000fb5a  xor     eax, eax
0x18000fb5c  mov     esi, edx
0x18000fb5e  mov     rdi, rcx
0x18000fb61  test    rcx, rcx
0x18000fb64  jz      short loc_18000FBD7
0x18000fb66  mov     rcx, gs:60h
0x18000fb6f  xor     edx, edx; Flags
0x18000fb71  mov     r8d, 80h; Size
0x18000fb77  mov     [rsp+38h+arg_8], rbx
0x18000fb7c  mov     rcx, [rcx+30h]; HeapHandle
0x18000fb80  call    cs:__imp_RtlAllocateHeap
0x18000fb87  nop     dword ptr [rax+rax+00h]
0x18000fb8c  mov     rbx, rax
0x18000fb8f  test    rax, rax
0x18000fb92  jz      short loc_18000FBD2
0x18000fb94  lea     rax, [rsp+38h+TokenInformationLength]
0x18000fb99  mov     [rsp+38h+TokenInformationLength], 0
0x18000fba1  mov     r9d, 80h; TokenInformationLength
0x18000fba7  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18000fbac  mov     r8, rbx; TokenInformation
0x18000fbaf  mov     edx, esi; TokenInformationClass
0x18000fbb1  mov     rcx, rdi; TokenHandle
0x18000fbb4  call    cs:__imp_NtQueryInformationToken
0x18000fbbb  nop     dword ptr [rax+rax+00h]
0x18000fbc0  cmp     eax, 0C0000023h
0x18000fbc5  jz      short loc_18000FBE3
0x18000fbc7  test    eax, eax
0x18000fbc9  js      loc_18000FC51
0x18000fbcf  mov     rax, rbx
0x18000fbd2  mov     rbx, [rsp+38h+arg_8]
0x18000fbd7  mov     rsi, [rsp+38h+arg_10]
0x18000fbdc  add     rsp, 30h
0x18000fbe0  pop     rdi
0x18000fbe1  retn
0x18000fbe3  mov     rcx, gs:60h
0x18000fbec  mov     r8, rbx; P
0x18000fbef  xor     edx, edx; Flags
0x18000fbf1  mov     rcx, [rcx+30h]; HeapHandle
0x18000fbf5  call    cs:__imp_RtlFreeHeap
0x18000fbfc  nop     dword ptr [rax+rax+00h]
0x18000fc01  mov     rcx, gs:60h
0x18000fc0a  xor     edx, edx; Flags
0x18000fc0c  mov     r8d, [rsp+38h+TokenInformationLength]; Size
0x18000fc11  mov     rcx, [rcx+30h]; HeapHandle
0x18000fc15  call    cs:__imp_RtlAllocateHeap
0x18000fc1c  nop     dword ptr [rax+rax+00h]
0x18000fc21  mov     rbx, rax
0x18000fc24  test    rax, rax
0x18000fc27  jz      short loc_18000FC51
0x18000fc29  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18000fc2e  lea     rax, [rsp+38h+TokenInformationLength]
0x18000fc33  mov     r8, rbx; TokenInformation
0x18000fc36  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18000fc3b  mov     edx, esi; TokenInformationClass
0x18000fc3d  mov     rcx, rdi; TokenHandle
0x18000fc40  call    cs:__imp_NtQueryInformationToken
0x18000fc47  nop     dword ptr [rax+rax+00h]
0x18000fc4c  jmp     loc_18000FBC7
0x18000fc51  mov     rcx, gs:60h
0x18000fc5a  mov     r8, rbx; P
0x18000fc5d  xor     edx, edx; Flags
0x18000fc5f  mov     rcx, [rcx+30h]; HeapHandle
0x18000fc63  call    cs:__imp_RtlFreeHeap
0x18000fc6a  nop     dword ptr [rax+rax+00h]
0x18000fc6f  mov     rbx, [rsp+38h+arg_8]
0x18000fc74  xor     eax, eax
0x18000fc76  mov     rsi, [rsp+38h+arg_10]
0x18000fc7b  add     rsp, 30h
0x18000fc7f  pop     rdi
0x18000fc80  retn
```
