# ATL::CComCriticalSection::Init(void)

- ea: `0x180010280`
- end: `0x1800102b1`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `49`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b388`

## callees

- `0x180010280`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180010288`
- `KERNEL32!InitializeCriticalSection` at `0x180010288`

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
0x180010280  push    rbx
0x180010282  sub     rsp, 20h
0x180010286  xor     ebx, ebx
0x180010288  call    cs:__imp_InitializeCriticalSection
0x18001028f  nop     dword ptr [rax+rax+00h]
0x180010294  jmp     short loc_1800102A8
0x180010296  mov     ebx, 80004005h
0x18001029b  mov     ecx, 8007000Eh
0x1800102a0  cmp     eax, 0C0000017h
0x1800102a5  cmovz   ebx, ecx
0x1800102a8  mov     eax, ebx
0x1800102aa  add     rsp, 20h
0x1800102ae  pop     rbx
0x1800102af  retn
```
