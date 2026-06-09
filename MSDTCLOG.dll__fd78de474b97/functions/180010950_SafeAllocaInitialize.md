# SafeAllocaInitialize

- ea: `0x180010950`
- end: `0x180010a0d`
- name: `SafeAllocaInitialize`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180008b68`

## callees

- `0x180010950`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x180010961`
- `ntdll!RtlImageNtHeader` at `0x180010961`

## pseudocode

```c
__int64 (__fastcall *SafeAllocaInitialize())()
{
  PIMAGE_NT_HEADERS v0; // rax
  PIMAGE_NT_HEADERS v1; // rdx
  __int64 v2; // rax
  __int64 GuaranteedStackBytes; // rax
  __int64 (__fastcall *result)(); // rax

  v0 = RtlImageNtHeader(NtCurrentPeb()->ImageBaseAddress);
  v1 = v0;
  if ( NtCurrentPeb()->BeingDebugged )
  {
    v2 = 0;
  }
  else
  {
    if ( v0 && v0->OptionalHeader.SizeOfStackReserve - v0->OptionalHeader.SizeOfStackCommit < 0x3000 )
    {
      g_ulMaxStackAllocSize = 0;
      goto LABEL_8;
    }
    v2 = 526;
  }
  g_ulMaxStackAllocSize = v2;
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
0x180010950  sub     rsp, 28h
0x180010954  mov     rcx, gs:60h
0x18001095d  mov     rcx, [rcx+10h]; BaseAddress
0x180010961  call    cs:__imp_RtlImageNtHeader
0x180010967  mov     rcx, gs:60h
0x180010970  mov     r8d, 3000h
0x180010976  mov     rdx, rax
0x180010979  cmp     byte ptr [rcx+2], 0
0x18001097d  jz      short loc_180010983
0x18001097f  xor     eax, eax
0x180010981  jmp     short loc_1800109A7
0x180010983  test    rdx, rdx
0x180010986  jz      short loc_1800109A2
0x180010988  mov     rax, [rax+60h]
0x18001098c  sub     rax, [rdx+68h]
0x180010990  cmp     rax, r8
0x180010993  jnb     short loc_1800109A2
0x180010995  mov     cs:g_ulMaxStackAllocSize, 0
0x1800109a0  jmp     short loc_1800109B3
0x1800109a2  mov     eax, 20Eh
0x1800109a7  mov     cs:g_ulMaxStackAllocSize, rax
0x1800109ae  test    rdx, rdx
0x1800109b1  jz      short loc_1800109E1
0x1800109b3  mov     rax, gs:30h
0x1800109bc  mov     eax, [rax+1748h]
0x1800109c2  mov     cs:g_ulAdditionalProbeSize, rax
0x1800109c9  test    rax, rax
0x1800109cc  jnz     short loc_1800109D7
0x1800109ce  mov     cs:g_ulAdditionalProbeSize, r8
0x1800109d5  jmp     short loc_1800109EC
0x1800109d7  add     rax, 8
0x1800109db  cmp     rax, 8
0x1800109df  jnb     short loc_1800109EC
0x1800109e1  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x1800109ec  lea     rax, SafeAllocaAllocateFromHeap
0x1800109f3  mov     cs:g_pfnAllocate, rax
0x1800109fa  lea     rax, SafeAllocaFreeToHeap
0x180010a01  mov     cs:g_pfnFree, rax
0x180010a08  add     rsp, 28h
0x180010a0c  retn
```
