# ATL::CComCriticalSection::Init(void)

- ea: `0x18000b69c`
- end: `0x18000b6bc`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002100`
- `0x1800021b0`
- `0x1800021f0`
- `0x180002230`
- `0x18000d984`
- `0x18000dad4`
- `0x18000dc60`

## callees

- `0x18000b69c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000b6a0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000b6a0`

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
0x18000b69c  sub     rsp, 38h
0x18000b6a0  call    cs:__imp_InitializeCriticalSection
0x18000b6a6  xor     eax, eax
0x18000b6a8  mov     [rsp+38h+var_18], eax
0x18000b6ac  jmp     short loc_18000B6B7
0x18000b6ae  mov     eax, 8007000Eh
0x18000b6b3  mov     [rsp+38h+var_18], eax
0x18000b6b7  add     rsp, 38h
0x18000b6bb  retn
```
