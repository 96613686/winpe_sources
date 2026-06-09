# SafeAllocaInitialize

- ea: `0x18002ce30`
- end: `0x18002ce8e`
- name: `SafeAllocaInitialize`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x1800112d0`

## callees

- `0x18002ce30`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x18002ce41`
- `ntdll!RtlImageNtHeader` at `0x18002ce41`

## pseudocode

```c
PIMAGE_NT_HEADERS SafeAllocaInitialize()
{
  PIMAGE_NT_HEADERS result; // rax

  result = RtlImageNtHeader(NtCurrentPeb()->ImageBaseAddress);
  if ( !result )
    goto LABEL_5;
  result = (PIMAGE_NT_HEADERS)NtCurrentTeb()->GuaranteedStackBytes;
  g_ulAdditionalProbeSize = (__int64)result;
  if ( !result )
  {
    g_ulAdditionalProbeSize = 12288;
    return result;
  }
  result = (PIMAGE_NT_HEADERS)((char *)result + 8);
  if ( (unsigned __int64)result < 8 )
LABEL_5:
    g_ulAdditionalProbeSize = -9;
  return result;
}

```

## disassembly

```asm
0x18002ce30  sub     rsp, 28h
0x18002ce34  mov     rcx, gs:60h
0x18002ce3d  mov     rcx, [rcx+10h]; BaseAddress
0x18002ce41  call    cs:__imp_RtlImageNtHeader
0x18002ce47  test    rax, rax
0x18002ce4a  jz      short loc_18002CE7E
0x18002ce4c  mov     rax, gs:30h
0x18002ce55  mov     eax, [rax+1748h]
0x18002ce5b  mov     cs:g_ulAdditionalProbeSize, rax
0x18002ce62  test    rax, rax
0x18002ce65  jnz     short loc_18002CE74
0x18002ce67  mov     cs:g_ulAdditionalProbeSize, 3000h
0x18002ce72  jmp     short loc_18002CE89
0x18002ce74  add     rax, 8
0x18002ce78  cmp     rax, 8
0x18002ce7c  jnb     short loc_18002CE89
0x18002ce7e  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x18002ce89  add     rsp, 28h
0x18002ce8d  retn
```
