# ATL::CComCriticalSection::Init(void)

- ea: `0x180013b34`
- end: `0x180013b54`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001540`
- `0x180001660`
- `0x180001700`
- `0x180001730`

## callees

- `0x180013b34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180013b38`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180013b38`

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
0x180013b34  sub     rsp, 38h
0x180013b38  call    cs:__imp_InitializeCriticalSection
0x180013b3e  xor     eax, eax
0x180013b40  mov     [rsp+38h+var_18], eax
0x180013b44  jmp     short loc_180013B4F
0x180013b46  mov     eax, 8007000Eh
0x180013b4b  mov     [rsp+38h+var_18], eax
0x180013b4f  add     rsp, 38h
0x180013b53  retn
```
