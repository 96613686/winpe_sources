# CodeAuthzpGetTokenInformation

- ea: `0x18000a680`
- end: `0x18000a785`
- name: `CodeAuthzpGetTokenInformation`
- size: `261`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, TOKEN_INFORMATION_CLASS TokenInformationClass)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000a150`
- `0x18000a3b0`
- `0x18000a78c`

## callees

- `0x18000a680`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000a714`
- `ntdll!RtlFreeHeap` at `0x18000a76d`
- `ntdll!RtlFreeHeap` at `0x18000a714`
- `ntdll!RtlFreeHeap` at `0x18000a76d`
- `ntdll!NtQueryInformationToken` at `0x18000a6de`
- `ntdll!NtQueryInformationToken` at `0x18000a753`
- `ntdll!NtQueryInformationToken` at `0x18000a6de`
- `ntdll!NtQueryInformationToken` at `0x18000a753`
- `ntdll!RtlAllocateHeap` at `0x18000a6b0`
- `ntdll!RtlAllocateHeap` at `0x18000a72e`
- `ntdll!RtlAllocateHeap` at `0x18000a6b0`
- `ntdll!RtlAllocateHeap` at `0x18000a72e`

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
0x18000a680  mov     [rsp+arg_10], rsi
0x18000a685  push    rdi
0x18000a686  sub     rsp, 30h
0x18000a68a  xor     eax, eax
0x18000a68c  mov     esi, edx
0x18000a68e  mov     rdi, rcx
0x18000a691  test    rcx, rcx
0x18000a694  jz      short loc_18000A6F7
0x18000a696  mov     rcx, gs:60h
0x18000a69f  xor     edx, edx; Flags
0x18000a6a1  mov     r8d, 80h; Size
0x18000a6a7  mov     [rsp+38h+arg_8], rbx
0x18000a6ac  mov     rcx, [rcx+30h]; HeapHandle
0x18000a6b0  call    cs:__imp_RtlAllocateHeap
0x18000a6b6  mov     rbx, rax
0x18000a6b9  test    rax, rax
0x18000a6bc  jz      short loc_18000A6F2
0x18000a6be  lea     rax, [rsp+38h+TokenInformationLength]
0x18000a6c3  mov     [rsp+38h+TokenInformationLength], 0
0x18000a6cb  mov     r9d, 80h; TokenInformationLength
0x18000a6d1  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18000a6d6  mov     r8, rbx; TokenInformation
0x18000a6d9  mov     edx, esi; TokenInformationClass
0x18000a6db  mov     rcx, rdi; TokenHandle
0x18000a6de  call    cs:__imp_NtQueryInformationToken
0x18000a6e4  cmp     eax, 0C0000023h
0x18000a6e9  jz      short loc_18000A702
0x18000a6eb  test    eax, eax
0x18000a6ed  js      short loc_18000A75B
0x18000a6ef  mov     rax, rbx
0x18000a6f2  mov     rbx, [rsp+38h+arg_8]
0x18000a6f7  mov     rsi, [rsp+38h+arg_10]
0x18000a6fc  add     rsp, 30h
0x18000a700  pop     rdi
0x18000a701  retn
0x18000a702  mov     rcx, gs:60h
0x18000a70b  mov     r8, rbx; P
0x18000a70e  xor     edx, edx; Flags
0x18000a710  mov     rcx, [rcx+30h]; HeapHandle
0x18000a714  call    cs:__imp_RtlFreeHeap
0x18000a71a  mov     rcx, gs:60h
0x18000a723  xor     edx, edx; Flags
0x18000a725  mov     r8d, [rsp+38h+TokenInformationLength]; Size
0x18000a72a  mov     rcx, [rcx+30h]; HeapHandle
0x18000a72e  call    cs:__imp_RtlAllocateHeap
0x18000a734  mov     rbx, rax
0x18000a737  test    rax, rax
0x18000a73a  jz      short loc_18000A75B
0x18000a73c  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18000a741  lea     rax, [rsp+38h+TokenInformationLength]
0x18000a746  mov     r8, rbx; TokenInformation
0x18000a749  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18000a74e  mov     edx, esi; TokenInformationClass
0x18000a750  mov     rcx, rdi; TokenHandle
0x18000a753  call    cs:__imp_NtQueryInformationToken
0x18000a759  jmp     short loc_18000A6EB
0x18000a75b  mov     rcx, gs:60h
0x18000a764  mov     r8, rbx; P
0x18000a767  xor     edx, edx; Flags
0x18000a769  mov     rcx, [rcx+30h]; HeapHandle
0x18000a76d  call    cs:__imp_RtlFreeHeap
0x18000a773  mov     rbx, [rsp+38h+arg_8]
0x18000a778  xor     eax, eax
0x18000a77a  mov     rsi, [rsp+38h+arg_10]
0x18000a77f  add     rsp, 30h
0x18000a783  pop     rdi
0x18000a784  retn
```
