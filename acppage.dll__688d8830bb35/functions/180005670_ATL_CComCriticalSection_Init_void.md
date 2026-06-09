# ATL::CComCriticalSection::Init(void)

- ea: `0x180005670`
- end: `0x180005690`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001460`
- `0x180001750`
- `0x180008ec8`
- `0x180008fe0`

## callees

- `0x180005670`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180005674`
- `KERNEL32!InitializeCriticalSection` at `0x180005674`

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
0x180005670  sub     rsp, 38h
0x180005674  call    cs:__imp_InitializeCriticalSection
0x18000567a  xor     eax, eax
0x18000567c  mov     [rsp+38h+var_18], eax
0x180005680  jmp     short loc_18000568B
0x180005682  mov     eax, 8007000Eh
0x180005687  mov     [rsp+38h+var_18], eax
0x18000568b  add     rsp, 38h
0x18000568f  retn
0x180016666  push    rbp
0x180016668  sub     rsp, 20h
0x18001666c  mov     rbp, rdx
0x18001666f  mov     rax, [rcx]
0x180016672  xor     ecx, ecx
0x180016674  cmp     dword ptr [rax], 0C0000017h
0x18001667a  setz    cl
0x18001667d  mov     eax, ecx
0x18001667f  add     rsp, 20h
0x180016683  pop     rbp
0x180016684  retn
```
