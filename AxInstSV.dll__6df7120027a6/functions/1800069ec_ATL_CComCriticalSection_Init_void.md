# ATL::CComCriticalSection::Init(void)

- ea: `0x1800069ec`
- end: `0x180006a0c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800011d0`
- `0x180001210`
- `0x180005cec`
- `0x180007f0c`
- `0x18000bf48`
- `0x180013690`

## callees

- `0x1800069ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800069f0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800069f0`

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
0x1800069ec  sub     rsp, 38h
0x1800069f0  call    cs:__imp_InitializeCriticalSection
0x1800069f6  xor     eax, eax
0x1800069f8  mov     [rsp+38h+var_18], eax
0x1800069fc  jmp     short loc_180006A07
0x1800069fe  mov     eax, 8007000Eh
0x180006a03  mov     [rsp+38h+var_18], eax
0x180006a07  add     rsp, 38h
0x180006a0b  retn
```
