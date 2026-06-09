# ATL::CComCriticalSection::Init(void)

- ea: `0x180002a80`
- end: `0x180002aa7`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `39`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001f34`
- `0x180001fb0`
- `0x18000201c`
- `0x1800020a8`
- `0x180002800`
- `0x180002920`
- `0x180002950`

## callees

- `0x180002a80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002a84`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002a84`

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
0x180002a80  sub     rsp, 38h
0x180002a84  call    cs:__imp_InitializeCriticalSection
0x180002a8b  nop     dword ptr [rax+rax+00h]
0x180002a90  xor     eax, eax
0x180002a92  mov     [rsp+38h+var_18], eax
0x180002a96  jmp     short loc_180002AA1
0x180002a98  mov     eax, 8007000Eh
0x180002a9d  mov     [rsp+38h+var_18], eax
0x180002aa1  add     rsp, 38h
0x180002aa5  retn
```
