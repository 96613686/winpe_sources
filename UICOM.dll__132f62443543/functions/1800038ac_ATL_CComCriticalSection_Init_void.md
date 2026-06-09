# ATL::CComCriticalSection::Init(void)

- ea: `0x1800038ac`
- end: `0x1800038cc`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010b0`
- `0x1800010f0`
- `0x180001130`
- `0x180005440`

## callees

- `0x1800038ac`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800038b0`
- `KERNEL32!InitializeCriticalSection` at `0x1800038b0`

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
0x1800038ac  sub     rsp, 38h
0x1800038b0  call    cs:__imp_InitializeCriticalSection
0x1800038b6  xor     eax, eax
0x1800038b8  mov     [rsp+38h+var_18], eax
0x1800038bc  jmp     short loc_1800038C7
0x1800038be  mov     eax, 8007000Eh
0x1800038c3  mov     [rsp+38h+var_18], eax
0x1800038c7  add     rsp, 38h
0x1800038cb  retn
0x180006346  push    rbp
0x180006348  sub     rsp, 20h
0x18000634c  mov     rbp, rdx
0x18000634f  mov     rax, [rcx]
0x180006352  xor     ecx, ecx
0x180006354  cmp     dword ptr [rax], 0C0000017h
0x18000635a  setz    cl
0x18000635d  mov     eax, ecx
0x18000635f  add     rsp, 20h
0x180006363  pop     rbp
0x180006364  retn
```
