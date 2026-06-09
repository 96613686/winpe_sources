# SafeAllocaInitialize

- ea: `0x18000a86c`
- end: `0x18000a92f`
- name: `SafeAllocaInitialize`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a4e0`

## callees

- `0x18000a86c`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x18000a87d`
- `ntdll!RtlImageNtHeader` at `0x18000a87d`

## pseudocode

```c
__int64 (__fastcall *SafeAllocaInitialize())(_QWORD)
{
  PIMAGE_NT_HEADERS v0; // rax
  PIMAGE_NT_HEADERS v1; // rdx
  __int64 GuaranteedStackBytes; // rax
  __int64 (__fastcall *result)(_QWORD); // rax
  __int64 SizeOfStackCommit; // rax

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
      goto LABEL_5;
    }
    SizeOfStackCommit = v0->OptionalHeader.SizeOfStackCommit;
  }
  g_ulMaxStackAllocSize = SizeOfStackCommit;
  if ( !v1 )
    goto LABEL_11;
LABEL_5:
  GuaranteedStackBytes = NtCurrentTeb()->GuaranteedStackBytes;
  g_ulAdditionalProbeSize = GuaranteedStackBytes;
  if ( GuaranteedStackBytes )
  {
    if ( (unsigned __int64)(GuaranteedStackBytes + 8) >= 8 )
      goto LABEL_8;
LABEL_11:
    g_ulAdditionalProbeSize = -9;
    goto LABEL_8;
  }
  g_ulAdditionalProbeSize = 12288;
LABEL_8:
  g_pfnAllocate = (__int64)SafeAllocaAllocateFromHeap;
  result = MSCryptFree;
  g_pfnFree = (__int64)MSCryptFree;
  return result;
}

```

## disassembly

```asm
0x18000a86c  sub     rsp, 28h
0x18000a870  mov     rcx, gs:60h
0x18000a879  mov     rcx, [rcx+10h]; BaseAddress
0x18000a87d  call    cs:__imp_RtlImageNtHeader
0x18000a884  nop     dword ptr [rax+rax+00h]
0x18000a889  mov     rcx, gs:60h
0x18000a892  mov     r8d, 3000h
0x18000a898  mov     rdx, rax
0x18000a89b  cmp     byte ptr [rcx+2], 0
0x18000a89f  jnz     short loc_18000A90E
0x18000a8a1  test    rax, rax
0x18000a8a4  jz      short loc_18000A90E
0x18000a8a6  mov     rax, [rax+60h]
0x18000a8aa  sub     rax, [rdx+68h]
0x18000a8ae  cmp     rax, r8
0x18000a8b1  jnb     short loc_18000A929
0x18000a8b3  mov     cs:g_ulMaxStackAllocSize, 0
0x18000a8be  mov     rax, gs:30h
0x18000a8c7  mov     eax, [rax+1748h]
0x18000a8cd  mov     cs:g_ulAdditionalProbeSize, rax
0x18000a8d4  test    rax, rax
0x18000a8d7  jnz     short loc_18000A8E2
0x18000a8d9  mov     cs:g_ulAdditionalProbeSize, r8
0x18000a8e0  jmp     short loc_18000A8EC
0x18000a8e2  add     rax, 8
0x18000a8e6  cmp     rax, 8
0x18000a8ea  jb      short loc_18000A91C
0x18000a8ec  lea     rax, SafeAllocaAllocateFromHeap
0x18000a8f3  mov     cs:g_pfnAllocate, rax
0x18000a8fa  lea     rax, MSCryptFree
0x18000a901  mov     cs:g_pfnFree, rax
0x18000a908  add     rsp, 28h
0x18000a90c  retn
0x18000a90e  xor     eax, eax
0x18000a910  mov     cs:g_ulMaxStackAllocSize, rax
0x18000a917  test    rdx, rdx
0x18000a91a  jnz     short loc_18000A8BE
0x18000a91c  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x18000a927  jmp     short loc_18000A8EC
0x18000a929  mov     rax, [rdx+68h]
0x18000a92d  jmp     short loc_18000A910
```
