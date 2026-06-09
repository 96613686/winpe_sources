# CPersistErrorCache::~CPersistErrorCache(void)

- ea: `0x180015370`
- end: `0x1800153a1`
- name: `??1CPersistErrorCache@@QEAA@XZ`
- size: `49`
- prototype: `void __fastcall(CPersistErrorCache *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180015fb4`
- `0x180016014`
- `0x18001d3b4`
- `0x180021680`
- `0x180022d40`
- `0x18002eda8`
- `0x18002edba`
- `0x18002f105`

## callees

- `0x180015370`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x180015384`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180015384`

## pseudocode

```c
void __fastcall CPersistErrorCache::~CPersistErrorCache(CPersistErrorCache *this)
{
  IErrorInfo *v2; // rdx

  v2 = (IErrorInfo *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    SetErrorInfo(0, v2);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1));
  }
}

```

## disassembly

```asm
0x180015370  push    rbx
0x180015372  sub     rsp, 20h
0x180015376  mov     rbx, rcx
0x180015379  mov     rdx, [rcx+8]; perrinfo
0x18001537d  test    rdx, rdx
0x180015380  jz      short loc_18001539B
0x180015382  xor     ecx, ecx; dwReserved
0x180015384  call    cs:__imp_SetErrorInfo
0x18001538a  mov     rcx, [rbx+8]
0x18001538e  mov     rax, [rcx]
0x180015391  mov     rax, [rax+10h]
0x180015395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001539a  nop
0x18001539b  add     rsp, 20h
0x18001539f  pop     rbx
0x1800153a0  retn
```
