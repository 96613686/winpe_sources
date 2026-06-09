# ATL::CComCriticalSection::Init(void)

- ea: `0x180004afc`
- end: `0x180004b1c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001070`
- `0x1800010c0`
- `0x180001100`
- `0x180001130`
- `0x180004800`

## callees

- `0x180004afc`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180004b00`
- `KERNEL32!InitializeCriticalSection` at `0x180004b00`

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
0x180004afc  sub     rsp, 38h
0x180004b00  call    cs:__imp_InitializeCriticalSection
0x180004b06  xor     eax, eax
0x180004b08  mov     [rsp+38h+var_18], eax
0x180004b0c  jmp     short loc_180004B17
0x180004b0e  mov     eax, 8007000Eh
0x180004b13  mov     [rsp+38h+var_18], eax
0x180004b17  add     rsp, 38h
0x180004b1b  retn
```
