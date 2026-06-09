# ATL::CComCriticalSection::Init(void)

- ea: `0x18000f6fc`
- end: `0x18000f71c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001040`
- `0x1800010f0`
- `0x180001130`
- `0x180011a64`

## callees

- `0x18000f6fc`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000f700`
- `KERNEL32!InitializeCriticalSection` at `0x18000f700`

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
0x18000f6fc  sub     rsp, 38h
0x18000f700  call    cs:__imp_InitializeCriticalSection
0x18000f706  xor     eax, eax
0x18000f708  mov     [rsp+38h+var_18], eax
0x18000f70c  jmp     short loc_18000F717
0x18000f70e  mov     eax, 8007000Eh
0x18000f713  mov     [rsp+38h+var_18], eax
0x18000f717  add     rsp, 38h
0x18000f71b  retn
```
