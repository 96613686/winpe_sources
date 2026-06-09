# ATL::CComCriticalSection::Init(void)

- ea: `0x18000233c`
- end: `0x18000235c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010a0`
- `0x1800010e0`
- `0x180001120`
- `0x180003514`
- `0x180003668`
- `0x180003790`
- `0x1800038bc`
- `0x1800039bc`

## callees

- `0x18000233c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180002340`
- `KERNEL32!InitializeCriticalSection` at `0x180002340`

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
0x18000233c  sub     rsp, 38h
0x180002340  call    cs:__imp_InitializeCriticalSection
0x180002346  xor     eax, eax
0x180002348  mov     [rsp+38h+var_18], eax
0x18000234c  jmp     short loc_180002357
0x18000234e  mov     eax, 8007000Eh
0x180002353  mov     [rsp+38h+var_18], eax
0x180002357  add     rsp, 38h
0x18000235b  retn
```
