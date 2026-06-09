# Common::StaticLock::StaticUninitialize(void)

- ea: `0x180016d4c`
- end: `0x180016d8e`
- name: `?StaticUninitialize@StaticLock@Common@@SAXXZ`
- size: `66`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016b00`

## callees

- `0x180016d4c`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180016d59`
- `ntdll!RtlDeleteCriticalSection` at `0x180016d82`
- `ntdll!RtlDeleteCriticalSection` at `0x180016d59`
- `ntdll!RtlDeleteCriticalSection` at `0x180016d82`

## pseudocode

```c
void Common::StaticLock::StaticUninitialize(void)
{
  PRTL_CRITICAL_SECTION i; // rbx

  RtlDeleteCriticalSection(&Common::mainLock);
  for ( i = Common::StaticLock::head; i; i = *(PRTL_CRITICAL_SECTION *)&i[1].LockCount )
  {
    if ( LODWORD(i[1].DebugInfo) )
      RtlDeleteCriticalSection(i);
  }
  Common::StaticLock::head = 0;
}

```

## disassembly

```asm
0x180016d4c  push    rbx
0x180016d4e  sub     rsp, 20h
0x180016d52  lea     rcx, ?mainLock@Common@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180016d59  call    cs:__imp_RtlDeleteCriticalSection
0x180016d5f  mov     rbx, cs:?head@StaticLock@Common@@0PEAV12@EA; Common::StaticLock * Common::StaticLock::head
0x180016d66  test    rbx, rbx
0x180016d69  jnz     short loc_180016D78
0x180016d6b  mov     cs:?head@StaticLock@Common@@0PEAV12@EA, rbx; Common::StaticLock * Common::StaticLock::head
0x180016d72  add     rsp, 20h
0x180016d76  pop     rbx
0x180016d77  retn
0x180016d78  mov     eax, [rbx+28h]
0x180016d7b  test    eax, eax
0x180016d7d  jz      short loc_180016D88
0x180016d7f  mov     rcx, rbx; CriticalSection
0x180016d82  call    cs:__imp_RtlDeleteCriticalSection
0x180016d88  mov     rbx, [rbx+30h]
0x180016d8c  jmp     short loc_180016D66
```
