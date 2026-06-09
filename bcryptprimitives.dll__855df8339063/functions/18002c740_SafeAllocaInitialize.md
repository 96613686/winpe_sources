# SafeAllocaInitialize

- ea: `0x18002c740`
- end: `0x18002c803`
- name: `SafeAllocaInitialize`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002c090`

## callees

- `0x18002c740`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x18002c751`
- `ntdll!RtlImageNtHeader` at `0x18002c751`

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
0x18002c740  sub     rsp, 28h
0x18002c744  mov     rcx, gs:60h
0x18002c74d  mov     rcx, [rcx+10h]; BaseAddress
0x18002c751  call    cs:__imp_RtlImageNtHeader
0x18002c758  nop     dword ptr [rax+rax+00h]
0x18002c75d  mov     rcx, gs:60h
0x18002c766  mov     r8d, 3000h
0x18002c76c  mov     rdx, rax
0x18002c76f  cmp     byte ptr [rcx+2], 0
0x18002c773  jnz     short loc_18002C7E2
0x18002c775  test    rax, rax
0x18002c778  jz      short loc_18002C7E2
0x18002c77a  mov     rax, [rax+60h]
0x18002c77e  sub     rax, [rdx+68h]
0x18002c782  cmp     rax, r8
0x18002c785  jnb     short loc_18002C7FD
0x18002c787  mov     cs:g_ulMaxStackAllocSize, 0
0x18002c792  mov     rax, gs:30h
0x18002c79b  mov     eax, [rax+1748h]
0x18002c7a1  mov     cs:g_ulAdditionalProbeSize, rax
0x18002c7a8  test    rax, rax
0x18002c7ab  jnz     short loc_18002C7B6
0x18002c7ad  mov     cs:g_ulAdditionalProbeSize, r8
0x18002c7b4  jmp     short loc_18002C7C0
0x18002c7b6  add     rax, 8
0x18002c7ba  cmp     rax, 8
0x18002c7be  jb      short loc_18002C7F0
0x18002c7c0  lea     rax, SafeAllocaAllocateFromHeap
0x18002c7c7  mov     cs:g_pfnAllocate, rax
0x18002c7ce  lea     rax, MSCryptFree
0x18002c7d5  mov     cs:g_pfnFree, rax
0x18002c7dc  add     rsp, 28h
0x18002c7e0  retn
0x18002c7e2  xor     eax, eax
0x18002c7e4  mov     cs:g_ulMaxStackAllocSize, rax
0x18002c7eb  test    rdx, rdx
0x18002c7ee  jnz     short loc_18002C792
0x18002c7f0  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x18002c7fb  jmp     short loc_18002C7C0
0x18002c7fd  mov     rax, [rdx+68h]
0x18002c801  jmp     short loc_18002C7E4
```
