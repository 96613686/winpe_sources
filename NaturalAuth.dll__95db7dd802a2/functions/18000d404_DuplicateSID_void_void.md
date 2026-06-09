# DuplicateSID(void *,void * *)

- ea: `0x18000d404`
- end: `0x18000d474`
- name: `?DuplicateSID@@YAJPEAXPEAPEAX@Z`
- size: `112`
- prototype: `__int64 __fastcall(PSID SourceSid, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000d47c`
- `0x180013d30`

## callees

- `0x18000d404`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000d43f`
- `ntdll!RtlAllocateHeap` at `0x18000d43f`
- `ntdll!RtlLengthSid` at `0x18000d425`
- `ntdll!RtlLengthSid` at `0x18000d425`
- `ntdll!RtlCopySid` at `0x18000d45c`
- `ntdll!RtlCopySid` at `0x18000d45c`

## pseudocode

```c
__int64 __fastcall DuplicateSID(PSID SourceSid, void **a2)
{
  ULONG v4; // esi
  PVOID Heap; // rax

  *a2 = 0;
  if ( SourceSid )
  {
    v4 = RtlLengthSid(SourceSid);
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    *a2 = Heap;
    if ( !Heap )
      return 2147942414LL;
    RtlCopySid(v4, Heap, SourceSid);
  }
  return 0;
}

```

## disassembly

```asm
0x18000d404  mov     [rsp+arg_0], rbx
0x18000d409  mov     [rsp+arg_8], rsi
0x18000d40e  push    rdi
0x18000d40f  sub     rsp, 20h
0x18000d413  mov     qword ptr [rdx], 0
0x18000d41a  mov     rdi, rdx
0x18000d41d  mov     rbx, rcx
0x18000d420  test    rcx, rcx
0x18000d423  jz      short loc_18000D462
0x18000d425  call    cs:__imp_RtlLengthSid
0x18000d42b  mov     rcx, gs:60h
0x18000d434  xor     edx, edx; Flags
0x18000d436  mov     r8d, eax; Size
0x18000d439  mov     esi, eax
0x18000d43b  mov     rcx, [rcx+30h]; HeapHandle
0x18000d43f  call    cs:__imp_RtlAllocateHeap
0x18000d445  mov     [rdi], rax
0x18000d448  test    rax, rax
0x18000d44b  jnz     short loc_18000D454
0x18000d44d  mov     eax, 8007000Eh
0x18000d452  jmp     short loc_18000D464
0x18000d454  mov     r8, rbx; SourceSid
0x18000d457  mov     rdx, rax; DestinationSid
0x18000d45a  mov     ecx, esi; DestinationSidLength
0x18000d45c  call    cs:__imp_RtlCopySid
0x18000d462  xor     eax, eax
0x18000d464  mov     rbx, [rsp+28h+arg_0]
0x18000d469  mov     rsi, [rsp+28h+arg_8]
0x18000d46e  add     rsp, 20h
0x18000d472  pop     rdi
0x18000d473  retn
```
