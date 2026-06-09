# ATL::CComCriticalSection::Init(void)

- ea: `0x180004370`
- end: `0x180004390`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001070`
- `0x180001110`
- `0x180001150`
- `0x180001190`
- `0x180003800`
- `0x1800039f0`

## callees

- `0x180004370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004374`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004374`

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
0x180004370  sub     rsp, 38h
0x180004374  call    cs:__imp_InitializeCriticalSection
0x18000437a  xor     eax, eax
0x18000437c  mov     [rsp+38h+var_18], eax
0x180004380  jmp     short loc_18000438B
0x180004382  mov     eax, 8007000Eh
0x180004387  mov     [rsp+38h+var_18], eax
0x18000438b  add     rsp, 38h
0x18000438f  retn
```
