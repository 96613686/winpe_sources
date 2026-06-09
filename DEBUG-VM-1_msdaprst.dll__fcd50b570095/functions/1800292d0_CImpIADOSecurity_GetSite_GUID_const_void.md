# CImpIADOSecurity::GetSite(_GUID const &,void * *)

- ea: `0x1800292d0`
- end: `0x180029341`
- name: `?GetSite@CImpIADOSecurity@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `113`
- prototype: `__int64 __fastcall(CImpIADOSecurity *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014610`

## callees

- `0x180029218`
- `0x1800292a4`
- `0x1800292d0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall CImpIADOSecurity::GetSite(struct CCriticalSection **this, const struct _GUID *a2, void **a3)
{
  unsigned int v6; // ebx
  struct CCriticalSection *v7; // rcx
  char v9; // [rsp+30h] [rbp+8h] BYREF

  CMPCSAutoBlock::CMPCSAutoBlock((CMPCSAutoBlock *)&v9, this + 5);
  if ( a3 )
  {
    v7 = this[4];
    if ( v7 )
      v6 = (**(__int64 (__fastcall ***)(struct CCriticalSection *, const struct _GUID *, void **))v7)(v7, a2, a3);
    else
      v6 = -2147467259;
  }
  else
  {
    v6 = -2147024809;
  }
  CMPCSAutoBlock::~CMPCSAutoBlock((CMPCSAutoBlock *)&v9);
  return v6;
}

```

## disassembly

```asm
0x1800292d0  mov     [rsp+arg_8], rbx
0x1800292d5  mov     [rsp+arg_10], rsi
0x1800292da  push    rdi
0x1800292db  sub     rsp, 20h
0x1800292df  mov     rsi, rdx
0x1800292e2  mov     rbx, rcx
0x1800292e5  lea     rdx, [rcx+28h]; struct CCriticalSection **
0x1800292e9  mov     rdi, r8
0x1800292ec  lea     rcx, [rsp+28h+arg_0]; this
0x1800292f1  call    ??0CMPCSAutoBlock@@QEAA@PEAPEAVCCriticalSection@@@Z; CMPCSAutoBlock::CMPCSAutoBlock(CCriticalSection * *)
0x1800292f6  test    rdi, rdi
0x1800292f9  jnz     short loc_180029302
0x1800292fb  mov     ebx, 80070057h
0x180029300  jmp     short loc_180029325
0x180029302  mov     rcx, [rbx+20h]
0x180029306  test    rcx, rcx
0x180029309  jnz     short loc_180029312
0x18002930b  mov     ebx, 80004005h
0x180029310  jmp     short loc_180029325
0x180029312  mov     rax, [rcx]
0x180029315  mov     r8, rdi
0x180029318  mov     rdx, rsi
0x18002931b  mov     rax, [rax]
0x18002931e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029323  mov     ebx, eax
0x180029325  lea     rcx, [rsp+28h+arg_0]; this
0x18002932a  call    ??1CMPCSAutoBlock@@QEAA@XZ; CMPCSAutoBlock::~CMPCSAutoBlock(void)
0x18002932f  mov     rsi, [rsp+28h+arg_10]
0x180029334  mov     eax, ebx
0x180029336  mov     rbx, [rsp+28h+arg_8]
0x18002933b  add     rsp, 20h
0x18002933f  pop     rdi
0x180029340  retn
```
