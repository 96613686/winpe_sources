# ATL::CComCriticalSection::Init(void)

- ea: `0x180007b98`
- end: `0x180007bb8`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001e50`
- `0x180001f10`
- `0x180001fd0`
- `0x180002090`
- `0x1800077bc`
- `0x180008d44`

## callees

- `0x180007b98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180007b9c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180007b9c`

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
0x180007b98  sub     rsp, 38h
0x180007b9c  call    cs:__imp_InitializeCriticalSection
0x180007ba2  xor     eax, eax
0x180007ba4  mov     [rsp+38h+var_18], eax
0x180007ba8  jmp     short loc_180007BB3
0x180007baa  mov     eax, 8007000Eh
0x180007baf  mov     [rsp+38h+var_18], eax
0x180007bb3  add     rsp, 38h
0x180007bb7  retn
```
