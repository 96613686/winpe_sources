# ORStart

- ea: `0x180086ca8`
- end: `0x180086d02`
- name: `ORStart`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008552c`

## callees

- `0x180031082`
- `0x180086ca8`
- `0x1800881d8`

## import_xrefs

- `ntdll!RtlRunOnceComplete` at `0x180086ced`
- `ntdll!RtlRunOnceComplete` at `0x180086ced`
- `ntdll!RtlRunOnceBeginInitialize` at `0x180086cbc`
- `ntdll!RtlRunOnceBeginInitialize` at `0x180086cbc`

## pseudocode

```c
__int64 ORStart()
{
  ULONG v0; // ebx
  NTSTATUS v1; // eax

  v0 = 0;
  if ( (unsigned int)RtlRunOnceBeginInitialize(&HiveInitialize, 0, 0) == 259 )
  {
    v1 = HvInitializeHashLibrary();
    if ( v1 < 0 )
      v0 = RtlNtStatusToDosError_0(v1);
    RtlRunOnceComplete(&HiveInitialize, 0, 0);
  }
  return v0;
}

```

## disassembly

```asm
0x180086ca8  push    rbx
0x180086caa  sub     rsp, 20h
0x180086cae  xor     r8d, r8d
0x180086cb1  lea     rcx, HiveInitialize
0x180086cb8  xor     edx, edx
0x180086cba  xor     ebx, ebx
0x180086cbc  call    cs:__imp_RtlRunOnceBeginInitialize
0x180086cc3  nop     dword ptr [rax+rax+00h]
0x180086cc8  cmp     eax, 103h
0x180086ccd  jnz     short loc_180086CF9
0x180086ccf  call    HvInitializeHashLibrary
0x180086cd4  test    eax, eax
0x180086cd6  jns     short loc_180086CE1
0x180086cd8  mov     ecx, eax; Status
0x180086cda  call    RtlNtStatusToDosError_0
0x180086cdf  mov     ebx, eax
0x180086ce1  xor     r8d, r8d; PVOID
0x180086ce4  lea     rcx, HiveInitialize; PRTL_RUN_ONCE
0x180086ceb  xor     edx, edx; DWORD
0x180086ced  call    cs:__imp_RtlRunOnceComplete
0x180086cf4  nop     dword ptr [rax+rax+00h]
0x180086cf9  mov     eax, ebx
0x180086cfb  add     rsp, 20h
0x180086cff  pop     rbx
0x180086d00  retn
```
