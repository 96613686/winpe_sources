# ATL::CComCriticalSection::Init(void)

- ea: `0x180008290`
- end: `0x1800082b0`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001a90`
- `0x180001b20`
- `0x180001b60`
- `0x180001ba0`
- `0x180007800`

## callees

- `0x180008290`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180008294`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180008294`

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
0x180008290  sub     rsp, 38h
0x180008294  call    cs:__imp_InitializeCriticalSection
0x18000829a  xor     eax, eax
0x18000829c  mov     [rsp+38h+var_18], eax
0x1800082a0  jmp     short loc_1800082AB
0x1800082a2  mov     eax, 8007000Eh
0x1800082a7  mov     [rsp+38h+var_18], eax
0x1800082ab  add     rsp, 38h
0x1800082af  retn
0x18000cd76  push    rbp
0x18000cd78  sub     rsp, 20h
0x18000cd7c  mov     rbp, rdx
0x18000cd7f  mov     rax, [rcx]
0x18000cd82  xor     ecx, ecx
0x18000cd84  cmp     dword ptr [rax], 0C0000017h
0x18000cd8a  setz    cl
0x18000cd8d  mov     eax, ecx
0x18000cd8f  add     rsp, 20h
0x18000cd93  pop     rbp
0x18000cd94  retn
```
