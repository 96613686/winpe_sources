# ATL::CComCriticalSection::Init(void)

- ea: `0x1400059c0`
- end: `0x1400059e0`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007a78`

## callees

- `0x1400059c0`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1400059c4`
- `KERNEL32!InitializeCriticalSection` at `0x1400059c4`

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
0x1400059c0  sub     rsp, 38h
0x1400059c4  call    cs:__imp_InitializeCriticalSection
0x1400059ca  xor     eax, eax
0x1400059cc  mov     [rsp+38h+var_18], eax
0x1400059d0  jmp     short loc_1400059DB
0x1400059d2  mov     eax, 8007000Eh
0x1400059d7  mov     [rsp+38h+var_18], eax
0x1400059db  add     rsp, 38h
0x1400059df  retn
```
