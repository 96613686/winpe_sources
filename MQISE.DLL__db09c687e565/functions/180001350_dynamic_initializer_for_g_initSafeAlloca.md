# _dynamic_initializer_for__g_initSafeAlloca__

- ea: `0x180001350`
- end: `0x1800013ca`
- name: `_dynamic_initializer_for__g_initSafeAlloca__`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001350`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x180001361`
- `ntdll!RtlImageNtHeader` at `0x180001361`

## pseudocode

```c
void (__fastcall *dynamic_initializer_for__g_initSafeAlloca__())(void *)
{
  PIMAGE_NT_HEADERS v0; // rax
  __int64 v1; // rax
  void (__fastcall *result)(void *); // rax

  v0 = RtlImageNtHeader(NtCurrentPeb()->ImageBaseAddress);
  if ( NtCurrentPeb()->BeingDebugged
    || v0 && v0->OptionalHeader.SizeOfStackReserve - v0->OptionalHeader.SizeOfStackCommit < 0x3000 )
  {
    v1 = 0;
  }
  else
  {
    v1 = 0x4000;
  }
  g_ulMaxStackAllocSize = v1;
  g_pfnAllocate = (__int64)AllocaHeapAllocate;
  result = AllocaHeapFree;
  g_pfnFree = (__int64)AllocaHeapFree;
  g_ulAdditionalProbeSize = 0x4000;
  return result;
}

```

## disassembly

```asm
0x180001350  sub     rsp, 28h
0x180001354  mov     rcx, gs:60h
0x18000135d  mov     rcx, [rcx+10h]; BaseAddress
0x180001361  call    cs:__imp_RtlImageNtHeader
0x180001367  mov     rcx, gs:60h
0x180001370  mov     r8d, 4000h
0x180001376  mov     rdx, rax
0x180001379  cmp     byte ptr [rcx+2], 0
0x18000137d  jnz     short loc_180001399
0x18000137f  test    rax, rax
0x180001382  jz      short loc_180001394
0x180001384  mov     rax, [rax+60h]
0x180001388  sub     rax, [rdx+68h]
0x18000138c  cmp     rax, 3000h
0x180001392  jb      short loc_180001399
0x180001394  mov     rax, r8
0x180001397  jmp     short loc_18000139B
0x180001399  xor     eax, eax
0x18000139b  mov     cs:g_ulMaxStackAllocSize, rax
0x1800013a2  lea     rax, ?AllocaHeapAllocate@@YAPEAX_K@Z; AllocaHeapAllocate(unsigned __int64)
0x1800013a9  mov     cs:g_pfnAllocate, rax
0x1800013b0  lea     rax, ?AllocaHeapFree@@YAXPEAX@Z; AllocaHeapFree(void *)
0x1800013b7  mov     cs:g_pfnFree, rax
0x1800013be  mov     cs:g_ulAdditionalProbeSize, r8
0x1800013c5  add     rsp, 28h
0x1800013c9  retn
```
