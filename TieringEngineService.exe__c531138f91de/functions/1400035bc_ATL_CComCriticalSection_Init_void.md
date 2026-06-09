# ATL::CComCriticalSection::Init(void)

- ea: `0x1400035bc`
- end: `0x1400035dc`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400017c0`
- `0x140001940`
- `0x140001980`
- `0x1400019c0`
- `0x140002e04`
- `0x140002f58`
- `0x1400030b4`
- `0x14000321c`
- `0x140003380`

## callees

- `0x1400035bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1400035c0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1400035c0`

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
0x1400035bc  sub     rsp, 38h
0x1400035c0  call    cs:__imp_InitializeCriticalSection
0x1400035c6  xor     eax, eax
0x1400035c8  mov     [rsp+38h+var_18], eax
0x1400035cc  jmp     short loc_1400035D7
0x1400035ce  mov     eax, 8007000Eh
0x1400035d3  mov     [rsp+38h+var_18], eax
0x1400035d7  add     rsp, 38h
0x1400035db  retn
```
