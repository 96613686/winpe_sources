# Common::StaticLock::StaticUninitialize(void)

- ea: `0x180012478`
- end: `0x1800124ba`
- name: `?StaticUninitialize@StaticLock@Common@@SAXXZ`
- size: `66`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012b64`

## callees

- `0x180012478`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180012485`
- `ntdll!RtlDeleteCriticalSection` at `0x18001249e`
- `ntdll!RtlDeleteCriticalSection` at `0x180012485`
- `ntdll!RtlDeleteCriticalSection` at `0x18001249e`

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
0x180012478  push    rbx
0x18001247a  sub     rsp, 20h
0x18001247e  lea     rcx, ?mainLock@Common@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180012485  call    cs:__imp_RtlDeleteCriticalSection
0x18001248b  mov     rbx, cs:?head@StaticLock@Common@@0PEAV12@EA; Common::StaticLock * Common::StaticLock::head
0x180012492  jmp     short loc_1800124A8
0x180012494  mov     eax, [rbx+28h]
0x180012497  test    eax, eax
0x180012499  jz      short loc_1800124A4
0x18001249b  mov     rcx, rbx; CriticalSection
0x18001249e  call    cs:__imp_RtlDeleteCriticalSection
0x1800124a4  mov     rbx, [rbx+30h]
0x1800124a8  test    rbx, rbx
0x1800124ab  jnz     short loc_180012494
0x1800124ad  mov     cs:?head@StaticLock@Common@@0PEAV12@EA, rbx; Common::StaticLock * Common::StaticLock::head
0x1800124b4  add     rsp, 20h
0x1800124b8  pop     rbx
0x1800124b9  retn
```
