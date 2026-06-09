# SafeAllocaInitialize

- ea: `0x18001a0c8`
- end: `0x18001a126`
- name: `SafeAllocaInitialize`
- size: `94`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x180010f50`

## callees

- `0x18001a0c8`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x18001a0d9`
- `ntdll!RtlImageNtHeader` at `0x18001a0d9`

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
0x18001a0c8  sub     rsp, 28h
0x18001a0cc  mov     rcx, gs:60h
0x18001a0d5  mov     rcx, [rcx+10h]; BaseAddress
0x18001a0d9  call    cs:__imp_RtlImageNtHeader
0x18001a0df  test    rax, rax
0x18001a0e2  jz      short loc_18001A116
0x18001a0e4  mov     rax, gs:30h
0x18001a0ed  mov     eax, [rax+1748h]
0x18001a0f3  mov     cs:g_ulAdditionalProbeSize, rax
0x18001a0fa  test    rax, rax
0x18001a0fd  jnz     short loc_18001A10C
0x18001a0ff  mov     cs:g_ulAdditionalProbeSize, 3000h
0x18001a10a  jmp     short loc_18001A121
0x18001a10c  add     rax, 8
0x18001a110  cmp     rax, 8
0x18001a114  jnb     short loc_18001A121
0x18001a116  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x18001a121  add     rsp, 28h
0x18001a125  retn
```
