# Concurrency::task_options::~task_options(void)

- ea: `0x180010138`
- end: `0x1800101c7`
- name: `??1task_options@Concurrency@@QEAA@XZ`
- size: `143`
- prototype: `void __fastcall(char **this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000f0a8`
- `0x180017efd`

## callees

- `0x18000fd1c`
- `0x180010138`
- `0x180019010`

## import_xrefs

- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18001014f`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18001014f`

## pseudocode

```c
void __fastcall Concurrency::task_options::~task_options(char **this)
{
  volatile signed __int32 *v2; // rcx
  volatile signed __int32 *v3; // rbx

  std::vector<void *>::~vector<void *>(this + 8);
  Concurrency::details::_ContextCallback::_Reset((Concurrency::details::_ContextCallback *)(this + 4));
  v2 = (volatile signed __int32 *)this[3];
  if ( v2 && _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
  this[3] = 0;
  v3 = (volatile signed __int32 *)this[1];
  if ( v3 && _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
    if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
  }
}

```

## disassembly

```asm
0x180010138  push    rbx
0x18001013a  sub     rsp, 20h
0x18001013e  mov     rbx, rcx
0x180010141  add     rcx, 40h ; '@'
0x180010145  call    ??1?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@XZ; std::vector<void *>::~vector<void *>(void)
0x18001014a  nop
0x18001014b  lea     rcx, [rbx+20h]
0x18001014f  call    cs:__imp_?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x180010155  nop
0x180010156  mov     rcx, [rbx+18h]
0x18001015a  test    rcx, rcx
0x18001015d  jz      short loc_180010178
0x18001015f  or      eax, 0FFFFFFFFh
0x180010162  lock xadd [rcx+8], eax
0x180010167  cmp     eax, 1
0x18001016a  jnz     short loc_180010178
0x18001016c  mov     rax, [rcx]
0x18001016f  mov     rax, [rax+8]
0x180010173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010178  mov     qword ptr [rbx+18h], 0
0x180010180  mov     rbx, [rbx+8]
0x180010184  test    rbx, rbx
0x180010187  jz      short loc_1800101C1
0x180010189  or      eax, 0FFFFFFFFh
0x18001018c  lock xadd [rbx+8], eax
0x180010191  cmp     eax, 1
0x180010194  jnz     short loc_1800101C1
0x180010196  mov     rax, [rbx]
0x180010199  mov     rcx, rbx
0x18001019c  mov     rax, [rax]
0x18001019f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101a4  or      eax, 0FFFFFFFFh
0x1800101a7  lock xadd [rbx+0Ch], eax
0x1800101ac  cmp     eax, 1
0x1800101af  jnz     short loc_1800101C1
0x1800101b1  mov     rax, [rbx]
0x1800101b4  mov     rcx, rbx
0x1800101b7  mov     rax, [rax+8]
0x1800101bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101c0  nop
0x1800101c1  add     rsp, 20h
0x1800101c5  pop     rbx
0x1800101c6  retn
```
