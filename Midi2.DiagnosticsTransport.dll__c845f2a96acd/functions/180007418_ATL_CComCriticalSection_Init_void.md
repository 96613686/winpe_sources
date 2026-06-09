# ATL::CComCriticalSection::Init(void)

- ea: `0x180007418`
- end: `0x180007438`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800019f0`
- `0x180001b20`
- `0x180001b60`
- `0x180001ba0`
- `0x180006344`
- `0x180006454`
- `0x180006590`

## callees

- `0x180007418`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000741c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000741c`

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
0x180007418  sub     rsp, 38h
0x18000741c  call    cs:__imp_InitializeCriticalSection
0x180007422  xor     eax, eax
0x180007424  mov     [rsp+38h+var_18], eax
0x180007428  jmp     short loc_180007433
0x18000742a  mov     eax, 8007000Eh
0x18000742f  mov     [rsp+38h+var_18], eax
0x180007433  add     rsp, 38h
0x180007437  retn
```
