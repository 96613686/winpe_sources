# CImpIADOSecurity::SetSite(IUnknown *)

- ea: `0x180029930`
- end: `0x180029992`
- name: `?SetSite@CImpIADOSecurity@@UEAAJPEAUIUnknown@@@Z`
- size: `98`
- prototype: `__int64 __fastcall(CImpIADOSecurity *__hidden this, struct IUnknown *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800151f0`
- `0x180029248`

## callees

- `0x180029218`
- `0x1800292a4`
- `0x180029930`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall CImpIADOSecurity::SetSite(struct CCriticalSection **this, struct IUnknown *a2)
{
  struct CCriticalSection *v4; // rcx
  char v6; // [rsp+30h] [rbp+8h] BYREF

  CMPCSAutoBlock::CMPCSAutoBlock((CMPCSAutoBlock *)&v6, this + 5);
  if ( a2 )
    ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
  v4 = this[4];
  if ( v4 )
    (*(void (__fastcall **)(struct CCriticalSection *))(*(_QWORD *)v4 + 16LL))(v4);
  this[4] = (struct CCriticalSection *)a2;
  CMPCSAutoBlock::~CMPCSAutoBlock((CMPCSAutoBlock *)&v6);
  return 0;
}

```

## disassembly

```asm
0x180029930  mov     [rsp+arg_8], rbx
0x180029935  push    rdi
0x180029936  sub     rsp, 20h
0x18002993a  mov     rbx, rdx
0x18002993d  mov     rdi, rcx
0x180029940  lea     rdx, [rcx+28h]; struct CCriticalSection **
0x180029944  lea     rcx, [rsp+28h+arg_0]; this
0x180029949  call    ??0CMPCSAutoBlock@@QEAA@PEAPEAVCCriticalSection@@@Z; CMPCSAutoBlock::CMPCSAutoBlock(CCriticalSection * *)
0x18002994e  test    rbx, rbx
0x180029951  jz      short loc_180029962
0x180029953  mov     rax, [rbx]
0x180029956  mov     rcx, rbx
0x180029959  mov     rax, [rax+8]
0x18002995d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029962  mov     rcx, [rdi+20h]
0x180029966  test    rcx, rcx
0x180029969  jz      short loc_180029977
0x18002996b  mov     rax, [rcx]
0x18002996e  mov     rax, [rax+10h]
0x180029972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029977  lea     rcx, [rsp+28h+arg_0]; this
0x18002997c  mov     [rdi+20h], rbx
0x180029980  call    ??1CMPCSAutoBlock@@QEAA@XZ; CMPCSAutoBlock::~CMPCSAutoBlock(void)
0x180029985  mov     rbx, [rsp+28h+arg_8]
0x18002998a  xor     eax, eax
0x18002998c  add     rsp, 20h
0x180029990  pop     rdi
0x180029991  retn
```
