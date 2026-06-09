# ATL::CComCriticalSection::Init(void)

- ea: `0x180002f84`
- end: `0x180002fa4`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001170`
- `0x180001200`
- `0x180001400`
- `0x180001430`
- `0x180002b90`

## callees

- `0x180002f84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002f88`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002f88`

## pseudocode

```c
__int64 __fastcall ATL::CComCriticalSection::Init(struct _RTL_CRITICAL_SECTION *this)
{
  InitializeCriticalSection(this);
  return 0;
}

```

## disassembly

```asm
0x180002f84  sub     rsp, 38h
0x180002f88  call    cs:__imp_InitializeCriticalSection
0x180002f8e  xor     eax, eax
0x180002f90  mov     [rsp+38h+var_18], eax
0x180002f94  jmp     short loc_180002F9F
0x180002f96  mov     eax, 8007000Eh
0x180002f9b  mov     [rsp+38h+var_18], eax
0x180002f9f  add     rsp, 38h
0x180002fa3  retn
```
