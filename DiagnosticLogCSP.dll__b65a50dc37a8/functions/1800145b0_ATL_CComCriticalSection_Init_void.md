# ATL::CComCriticalSection::Init(void)

- ea: `0x1800145b0`
- end: `0x1800145d7`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `39`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001560`
- `0x180001680`
- `0x180001730`
- `0x180001760`

## callees

- `0x1800145b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800145b4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800145b4`

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
0x1800145b0  sub     rsp, 38h
0x1800145b4  call    cs:__imp_InitializeCriticalSection
0x1800145bb  nop     dword ptr [rax+rax+00h]
0x1800145c0  xor     eax, eax
0x1800145c2  mov     [rsp+38h+var_18], eax
0x1800145c6  jmp     short loc_1800145D1
0x1800145c8  mov     eax, 8007000Eh
0x1800145cd  mov     [rsp+38h+var_18], eax
0x1800145d1  add     rsp, 38h
0x1800145d5  retn
```
