# ATL::CComCriticalSection::Init(void)

- ea: `0x1800081d8`
- end: `0x1800081ff`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `39`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001830`

## callees

- `0x1800081d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800081e3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800081e3`

## pseudocode

```c
__int64 __fastcall ATL::CComCriticalSection::Init(ATL::CComCriticalSection *this)
{
  InitializeCriticalSection(&CriticalSection);
  return 0;
}

```

## disassembly

```asm
0x1800081d8  sub     rsp, 38h
0x1800081dc  lea     rcx, CriticalSection; lpCriticalSection
0x1800081e3  call    cs:__imp_InitializeCriticalSection
0x1800081e9  xor     eax, eax
0x1800081eb  mov     [rsp+38h+var_18], eax
0x1800081ef  jmp     short loc_1800081FA
0x1800081f1  mov     eax, 8007000Eh
0x1800081f6  mov     [rsp+38h+var_18], eax
0x1800081fa  add     rsp, 38h
0x1800081fe  retn
```
