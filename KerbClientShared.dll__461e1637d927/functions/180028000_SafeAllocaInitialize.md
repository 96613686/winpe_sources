# SafeAllocaInitialize

- ea: `0x180028000`
- end: `0x1800280bc`
- name: `SafeAllocaInitialize`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180011dc0`

## callees

- `0x180028000`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x180028011`
- `ntdll!RtlImageNtHeader` at `0x180028011`

## pseudocode

```c
__int64 (__fastcall *SafeAllocaInitialize())()
{
  PIMAGE_NT_HEADERS v0; // rax
  PIMAGE_NT_HEADERS v1; // rdx
  __int64 SizeOfStackCommit; // rax
  __int64 GuaranteedStackBytes; // rax
  __int64 (__fastcall *result)(); // rax

  v0 = RtlImageNtHeader(NtCurrentPeb()->ImageBaseAddress);
  v1 = v0;
  if ( NtCurrentPeb()->BeingDebugged || !v0 )
  {
    SizeOfStackCommit = 0;
  }
  else
  {
    if ( v0->OptionalHeader.SizeOfStackReserve - v0->OptionalHeader.SizeOfStackCommit < 0x3000 )
    {
      g_ulMaxStackAllocSize = 0;
      goto LABEL_8;
    }
    SizeOfStackCommit = v0->OptionalHeader.SizeOfStackCommit;
  }
  g_ulMaxStackAllocSize = SizeOfStackCommit;
  if ( !v1 )
    goto LABEL_11;
LABEL_8:
  GuaranteedStackBytes = NtCurrentTeb()->GuaranteedStackBytes;
  g_ulAdditionalProbeSize = GuaranteedStackBytes;
  if ( GuaranteedStackBytes )
  {
    if ( (unsigned __int64)(GuaranteedStackBytes + 8) >= 8 )
      goto LABEL_12;
LABEL_11:
    g_ulAdditionalProbeSize = -9;
    goto LABEL_12;
  }
  g_ulAdditionalProbeSize = 12288;
LABEL_12:
  g_pfnAllocate = (__int64)SafeAllocaAllocateFromHeap;
  result = SafeAllocaFreeToHeap;
  g_pfnFree = (__int64)SafeAllocaFreeToHeap;
  return result;
}

```

## disassembly

```asm
0x180028000  sub     rsp, 28h
0x180028004  mov     rcx, gs:60h
0x18002800d  mov     rcx, [rcx+10h]; BaseAddress
0x180028011  call    cs:__imp_RtlImageNtHeader
0x180028017  mov     rcx, gs:60h
0x180028020  mov     r8d, 3000h
0x180028026  mov     rdx, rax
0x180028029  cmp     byte ptr [rcx+2], 0
0x18002802d  jnz     short loc_180028054
0x18002802f  test    rax, rax
0x180028032  jz      short loc_180028054
0x180028034  mov     rax, [rax+60h]
0x180028038  sub     rax, [rdx+68h]
0x18002803c  cmp     rax, r8
0x18002803f  jnb     short loc_18002804E
0x180028041  mov     cs:g_ulMaxStackAllocSize, 0
0x18002804c  jmp     short loc_180028062
0x18002804e  mov     rax, [rdx+68h]
0x180028052  jmp     short loc_180028056
0x180028054  xor     eax, eax
0x180028056  mov     cs:g_ulMaxStackAllocSize, rax
0x18002805d  test    rdx, rdx
0x180028060  jz      short loc_180028090
0x180028062  mov     rax, gs:30h
0x18002806b  mov     eax, [rax+1748h]
0x180028071  mov     cs:g_ulAdditionalProbeSize, rax
0x180028078  test    rax, rax
0x18002807b  jnz     short loc_180028086
0x18002807d  mov     cs:g_ulAdditionalProbeSize, r8
0x180028084  jmp     short loc_18002809B
0x180028086  add     rax, 8
0x18002808a  cmp     rax, 8
0x18002808e  jnb     short loc_18002809B
0x180028090  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x18002809b  lea     rax, SafeAllocaAllocateFromHeap
0x1800280a2  mov     cs:g_pfnAllocate, rax
0x1800280a9  lea     rax, SafeAllocaFreeToHeap
0x1800280b0  mov     cs:g_pfnFree, rax
0x1800280b7  add     rsp, 28h
0x1800280bb  retn
```
