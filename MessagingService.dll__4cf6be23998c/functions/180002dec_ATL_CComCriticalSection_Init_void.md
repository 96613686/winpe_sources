# ATL::CComCriticalSection::Init(void)

- ea: `0x180002dec`
- end: `0x180002e0c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001470`
- `0x180001590`

## callees

- `0x180002dec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002df0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002df0`

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
0x180002dec  sub     rsp, 38h
0x180002df0  call    cs:__imp_InitializeCriticalSection
0x180002df6  xor     eax, eax
0x180002df8  mov     [rsp+38h+var_18], eax
0x180002dfc  jmp     short loc_180002E07
0x180002dfe  mov     eax, 8007000Eh
0x180002e03  mov     [rsp+38h+var_18], eax
0x180002e07  add     rsp, 38h
0x180002e0b  retn
```
