# ATL::CComCriticalSection::Init(void)

- ea: `0x1800119c0`
- end: `0x1800119e0`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800013f0`
- `0x1800014e0`
- `0x180011540`
- `0x18001162c`
- `0x180011730`

## callees

- `0x1800119c0`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800119c4`
- `KERNEL32!InitializeCriticalSection` at `0x1800119c4`

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
0x1800119c0  sub     rsp, 38h
0x1800119c4  call    cs:__imp_InitializeCriticalSection
0x1800119ca  xor     eax, eax
0x1800119cc  mov     [rsp+38h+var_18], eax
0x1800119d0  jmp     short loc_1800119DB
0x1800119d2  mov     eax, 8007000Eh
0x1800119d7  mov     [rsp+38h+var_18], eax
0x1800119db  add     rsp, 38h
0x1800119df  retn
0x180013ab6  push    rbp
0x180013ab8  sub     rsp, 20h
0x180013abc  mov     rbp, rdx
0x180013abf  mov     rax, [rcx]
0x180013ac2  xor     ecx, ecx
0x180013ac4  cmp     dword ptr [rax], 0C0000017h
0x180013aca  setz    cl
0x180013acd  mov     eax, ecx
0x180013acf  add     rsp, 20h
0x180013ad3  pop     rbp
0x180013ad4  retn
```
