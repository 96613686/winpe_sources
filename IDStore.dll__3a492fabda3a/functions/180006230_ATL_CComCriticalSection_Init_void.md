# ATL::CComCriticalSection::Init(void)

- ea: `0x180006230`
- end: `0x180006250`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `13`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003a70`
- `0x180004300`
- `0x180005ea0`
- `0x180005fe0`
- `0x180007a10`
- `0x180007b20`
- `0x180007eb0`
- `0x180007f54`
- `0x180008178`
- `0x18000e610`
- `0x18000e9fc`
- `0x180010d24`
- `0x180010e78`

## callees

- `0x180006230`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006234`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006234`

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
0x180006230  sub     rsp, 38h
0x180006234  call    cs:__imp_InitializeCriticalSection
0x18000623a  xor     eax, eax
0x18000623c  mov     [rsp+38h+var_18], eax
0x180006240  jmp     short loc_18000624B
0x180006242  mov     eax, 8007000Eh
0x180006247  mov     [rsp+38h+var_18], eax
0x18000624b  add     rsp, 38h
0x18000624f  retn
```
