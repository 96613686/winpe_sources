# ATL::CComCriticalSection::Init(void)

- ea: `0x1800058dc`
- end: `0x1800058fc`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001070`
- `0x180001110`
- `0x180001150`
- `0x1800011f0`
- `0x180004a88`
- `0x180004be0`
- `0x180008c84`

## callees

- `0x1800058dc`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800058e0`
- `KERNEL32!InitializeCriticalSection` at `0x1800058e0`

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
0x1800058dc  sub     rsp, 38h
0x1800058e0  call    cs:__imp_InitializeCriticalSection
0x1800058e6  xor     eax, eax
0x1800058e8  mov     [rsp+38h+var_18], eax
0x1800058ec  jmp     short loc_1800058F7
0x1800058ee  mov     eax, 8007000Eh
0x1800058f3  mov     [rsp+38h+var_18], eax
0x1800058f7  add     rsp, 38h
0x1800058fb  retn
```
