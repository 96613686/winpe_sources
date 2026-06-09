# SafeAllocaInitialize

- ea: `0x1800717a4`
- end: `0x180071860`
- name: `SafeAllocaInitialize`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003a5fc`

## callees

- `0x1800717a4`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x1800717b5`
- `ntdll!RtlImageNtHeader` at `0x1800717b5`

## pseudocode

```c
void (__stdcall *SafeAllocaInitialize())(void *)
{
  PIMAGE_NT_HEADERS v0; // rax
  PIMAGE_NT_HEADERS v1; // rdx
  __int64 SizeOfStackCommit; // rax
  __int64 GuaranteedStackBytes; // rax
  void (__stdcall *result)(void *); // rax

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
  g_pfnAllocate = (__int64)KdcAllocate;
  result = KdcFree;
  g_pfnFree = (__int64)KdcFree;
  return result;
}

```

## disassembly

```asm
0x1800717a4  sub     rsp, 28h
0x1800717a8  mov     rcx, gs:60h
0x1800717b1  mov     rcx, [rcx+10h]; BaseAddress
0x1800717b5  call    cs:__imp_RtlImageNtHeader
0x1800717bb  mov     rcx, gs:60h
0x1800717c4  mov     r8d, 3000h
0x1800717ca  mov     rdx, rax
0x1800717cd  cmp     byte ptr [rcx+2], 0
0x1800717d1  jnz     short loc_1800717F8
0x1800717d3  test    rax, rax
0x1800717d6  jz      short loc_1800717F8
0x1800717d8  mov     rax, [rax+60h]
0x1800717dc  sub     rax, [rdx+68h]
0x1800717e0  cmp     rax, r8
0x1800717e3  jnb     short loc_1800717F2
0x1800717e5  mov     cs:g_ulMaxStackAllocSize, 0
0x1800717f0  jmp     short loc_180071806
0x1800717f2  mov     rax, [rdx+68h]
0x1800717f6  jmp     short loc_1800717FA
0x1800717f8  xor     eax, eax
0x1800717fa  mov     cs:g_ulMaxStackAllocSize, rax
0x180071801  test    rdx, rdx
0x180071804  jz      short loc_180071834
0x180071806  mov     rax, gs:30h
0x18007180f  mov     eax, [rax+1748h]
0x180071815  mov     cs:g_ulAdditionalProbeSize, rax
0x18007181c  test    rax, rax
0x18007181f  jnz     short loc_18007182A
0x180071821  mov     cs:g_ulAdditionalProbeSize, r8
0x180071828  jmp     short loc_18007183F
0x18007182a  add     rax, 8
0x18007182e  cmp     rax, 8
0x180071832  jnb     short loc_18007183F
0x180071834  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x18007183f  lea     rax, ?KdcAllocate@@YAPEAX_K@Z; KdcAllocate(unsigned __int64)
0x180071846  mov     cs:g_pfnAllocate, rax
0x18007184d  lea     rax, ?KdcFree@@YAXPEAX@Z; KdcFree(void *)
0x180071854  mov     cs:g_pfnFree, rax
0x18007185b  add     rsp, 28h
0x18007185f  retn
```
