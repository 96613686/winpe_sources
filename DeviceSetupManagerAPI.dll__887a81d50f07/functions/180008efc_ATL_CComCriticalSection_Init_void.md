# ATL::CComCriticalSection::Init(void)

- ea: `0x180008efc`
- end: `0x180008f1c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001210`
- `0x1800012b0`
- `0x1800012f0`
- `0x180001330`
- `0x180009498`
- `0x1800095f0`
- `0x18000cf58`

## callees

- `0x180008efc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180008f00`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180008f00`

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
0x180008efc  sub     rsp, 38h
0x180008f00  call    cs:__imp_InitializeCriticalSection
0x180008f06  xor     eax, eax
0x180008f08  mov     [rsp+38h+var_18], eax
0x180008f0c  jmp     short loc_180008F17
0x180008f0e  mov     eax, 8007000Eh
0x180008f13  mov     [rsp+38h+var_18], eax
0x180008f17  add     rsp, 38h
0x180008f1b  retn
```
