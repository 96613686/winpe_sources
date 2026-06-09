# ATL::CComCriticalSection::Init(void)

- ea: `0x1400072dc`
- end: `0x1400072fc`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001240`
- `0x140001280`
- `0x140007304`
- `0x14000ca6c`
- `0x140015020`

## callees

- `0x1400072dc`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1400072e0`
- `KERNEL32!InitializeCriticalSection` at `0x1400072e0`

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
0x1400072dc  sub     rsp, 38h
0x1400072e0  call    cs:__imp_InitializeCriticalSection
0x1400072e6  xor     eax, eax
0x1400072e8  mov     [rsp+38h+var_18], eax
0x1400072ec  jmp     short loc_1400072F7
0x1400072ee  mov     eax, 8007000Eh
0x1400072f3  mov     [rsp+38h+var_18], eax
0x1400072f7  add     rsp, 38h
0x1400072fb  retn
```
