# SafeAllocaInitialize

- ea: `0x140036ed0`
- end: `0x140036f8c`
- name: `SafeAllocaInitialize`
- size: `188`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000685c`

## callees

- `0x140036ed0`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x140036ee1`
- `ntdll!RtlImageNtHeader` at `0x140036ee1`

## pseudocode

```c
void (*SafeAllocaInitialize())(void *)
{
  PIMAGE_NT_HEADERS v0; // rax
  PIMAGE_NT_HEADERS v1; // rdx
  __int64 SizeOfStackCommit; // rax
  __int64 GuaranteedStackBytes; // rax
  void (*result)(void *); // rax

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
0x140036ed0  sub     rsp, 28h
0x140036ed4  mov     rcx, gs:60h
0x140036edd  mov     rcx, [rcx+10h]; BaseAddress
0x140036ee1  call    cs:__imp_RtlImageNtHeader
0x140036ee7  mov     rcx, gs:60h
0x140036ef0  mov     r8d, 3000h
0x140036ef6  mov     rdx, rax
0x140036ef9  cmp     byte ptr [rcx+2], 0
0x140036efd  jnz     short loc_140036F24
0x140036eff  test    rax, rax
0x140036f02  jz      short loc_140036F24
0x140036f04  mov     rax, [rax+60h]
0x140036f08  sub     rax, [rdx+68h]
0x140036f0c  cmp     rax, r8
0x140036f0f  jnb     short loc_140036F1E
0x140036f11  mov     cs:g_ulMaxStackAllocSize, 0
0x140036f1c  jmp     short loc_140036F32
0x140036f1e  mov     rax, [rdx+68h]
0x140036f22  jmp     short loc_140036F26
0x140036f24  xor     eax, eax
0x140036f26  mov     cs:g_ulMaxStackAllocSize, rax
0x140036f2d  test    rdx, rdx
0x140036f30  jz      short loc_140036F60
0x140036f32  mov     rax, gs:30h
0x140036f3b  mov     eax, [rax+1748h]
0x140036f41  mov     cs:g_ulAdditionalProbeSize, rax
0x140036f48  test    rax, rax
0x140036f4b  jnz     short loc_140036F56
0x140036f4d  mov     cs:g_ulAdditionalProbeSize, r8
0x140036f54  jmp     short loc_140036F6B
0x140036f56  add     rax, 8
0x140036f5a  cmp     rax, 8
0x140036f5e  jnb     short loc_140036F6B
0x140036f60  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x140036f6b  lea     rax, SafeAllocaAllocateFromHeap
0x140036f72  mov     cs:g_pfnAllocate, rax
0x140036f79  lea     rax, SafeAllocaFreeToHeap
0x140036f80  mov     cs:g_pfnFree, rax
0x140036f87  add     rsp, 28h
0x140036f8b  retn
```
