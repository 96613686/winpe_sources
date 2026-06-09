# AERTLockCurrentThread(void)

- ea: `0x140005d00`
- end: `0x140005d7c`
- name: `?AERTLockCurrentThread@@YAJXZ`
- size: `124`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140004310`
- `0x140005240`

## callees

- `0x140005d00`
- `0x14000faf8`
- `0x140012ed8`

## import_xrefs

- `ntdll!RtlLockCurrentThread` at `0x140005d06`
- `ntdll!RtlLockCurrentThread` at `0x140005d38`
- `ntdll!RtlLockCurrentThread` at `0x140005d06`
- `ntdll!RtlLockCurrentThread` at `0x140005d38`

## pseudocode

```c
__int64 AERTLockCurrentThread(void)
{
  int v0; // edx
  int v1; // ecx
  int v2; // ebx
  int v3; // r8d

  v2 = RtlLockCurrentThread();
  if ( v2 == -1073741663 && (int)IncreaseProcessWorkingSet(0x100000u) >= 0 )
    v2 = RtlLockCurrentThread();
  if ( (byte_1400E7E41 & 4) != 0 )
    McTemplateU0pqpqqqqqq_EventWriteTransfer(v1, v0, v3, 12, 0, 0, 0, 0);
  return v2 | 0x10000000u;
}

```

## disassembly

```asm
0x140005d00  push    rbx
0x140005d02  sub     rsp, 60h
0x140005d06  call    cs:__imp_RtlLockCurrentThread
0x140005d0c  mov     ebx, eax
0x140005d0e  cmp     eax, 0C00000A1h
0x140005d13  jz      short loc_140005D2A
0x140005d15  test    cs:byte_1400E7E41, 4
0x140005d1c  jnz     short loc_140005D42
0x140005d1e  bts     ebx, 1Ch
0x140005d22  mov     eax, ebx
0x140005d24  add     rsp, 60h
0x140005d28  pop     rbx
0x140005d29  retn
0x140005d2a  mov     ecx, 100000h; unsigned __int64
0x140005d2f  call    ?IncreaseProcessWorkingSet@@YAJ_K@Z; IncreaseProcessWorkingSet(unsigned __int64)
0x140005d34  test    eax, eax
0x140005d36  js      short loc_140005D15
0x140005d38  call    cs:__imp_RtlLockCurrentThread
0x140005d3e  mov     ebx, eax
0x140005d40  jmp     short loc_140005D15
0x140005d42  mov     [rsp+68h+var_18], ebx
0x140005d46  mov     r9d, 0Ch
0x140005d4c  mov     [rsp+68h+var_20], 0
0x140005d54  mov     [rsp+68h+var_30], 0
0x140005d5c  mov     [rsp+68h+var_38], 0
0x140005d64  mov     [rsp+68h+var_40], 0
0x140005d6c  mov     [rsp+68h+var_48], 0
0x140005d75  call    McTemplateU0pqpqqqqqq_EventWriteTransfer
0x140005d7a  jmp     short loc_140005D1E
```
