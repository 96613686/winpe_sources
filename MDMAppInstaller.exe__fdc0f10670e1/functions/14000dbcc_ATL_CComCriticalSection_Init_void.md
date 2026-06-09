# ATL::CComCriticalSection::Init(void)

- ea: `0x14000dbcc`
- end: `0x14000dbec`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140008ae0`

## callees

- `0x14000dbcc`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x14000dbd0`
- `KERNEL32!InitializeCriticalSection` at `0x14000dbd0`

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
0x14000dbcc  sub     rsp, 38h
0x14000dbd0  call    cs:__imp_InitializeCriticalSection
0x14000dbd6  xor     eax, eax
0x14000dbd8  mov     [rsp+38h+var_18], eax
0x14000dbdc  jmp     short loc_14000DBE7
0x14000dbde  mov     eax, 8007000Eh
0x14000dbe3  mov     [rsp+38h+var_18], eax
0x14000dbe7  add     rsp, 38h
0x14000dbeb  retn
```
