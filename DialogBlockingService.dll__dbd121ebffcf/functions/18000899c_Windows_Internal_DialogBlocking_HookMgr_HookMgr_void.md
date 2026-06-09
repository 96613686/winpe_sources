# Windows::Internal::DialogBlocking::HookMgr::~HookMgr(void)

- ea: `0x18000899c`
- end: `0x180008a51`
- name: `??1HookMgr@DialogBlocking@Internal@Windows@@QEAA@XZ`
- size: `181`
- prototype: `void __fastcall(Windows::Internal::DialogBlocking::HookProcess **this)`
- caller_count: `6`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000396c`
- `0x180003e18`
- `0x180003f84`
- `0x18000a328`
- `0x18000a538`
- `0x18000a65c`

## callees

- `0x180001644`
- `0x18000899c`
- `0x180008a58`
- `0x180009010`
- `0x18000e010`

## pseudocode

```c
void __fastcall Windows::Internal::DialogBlocking::HookMgr::~HookMgr(
        Windows::Internal::DialogBlocking::HookProcess **this)
{
  Windows::Internal::DialogBlocking::HookProcess *v2; // rsi
  Windows::Internal::DialogBlocking::HookProcess *v3; // rdi
  volatile signed __int32 *v4; // rbx

  if ( *((_BYTE *)this + 4) )
    Windows::Internal::DialogBlocking::HookProcess::ResetHookProcess(this[3]);
  Windows::Internal::DialogBlocking::HookProcess::ResetHookProcess(this[4]);
  v2 = this[4];
  if ( v2 )
  {
    Windows::Internal::DialogBlocking::HookProcess::~HookProcess(this[4]);
    operator delete(v2, 0x28u);
  }
  v3 = this[3];
  if ( v3 )
  {
    Windows::Internal::DialogBlocking::HookProcess::~HookProcess(this[3]);
    operator delete(v3, 0x28u);
  }
  v4 = (volatile signed __int32 *)this[2];
  if ( v4 && _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
    if ( !_InterlockedDecrement(v4 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
  }
}

```

## disassembly

```asm
0x18000899c  mov     [rsp+arg_0], rbx
0x1800089a1  mov     [rsp+arg_8], rsi
0x1800089a6  push    rdi
0x1800089a7  sub     rsp, 20h
0x1800089ab  cmp     byte ptr [rcx+4], 0
0x1800089af  mov     rbx, rcx
0x1800089b2  jz      short loc_1800089BD
0x1800089b4  mov     rcx, [rcx+18h]; this
0x1800089b8  call    ?ResetHookProcess@HookProcess@DialogBlocking@Internal@Windows@@QEAAXXZ; Windows::Internal::DialogBlocking::HookProcess::ResetHookProcess(void)
0x1800089bd  mov     rcx, [rbx+20h]; this
0x1800089c1  call    ?ResetHookProcess@HookProcess@DialogBlocking@Internal@Windows@@QEAAXXZ; Windows::Internal::DialogBlocking::HookProcess::ResetHookProcess(void)
0x1800089c6  mov     rsi, [rbx+20h]
0x1800089ca  test    rsi, rsi
0x1800089cd  jz      short loc_1800089E4
0x1800089cf  mov     rcx, rsi; this
0x1800089d2  call    ??1HookProcess@DialogBlocking@Internal@Windows@@QEAA@XZ; Windows::Internal::DialogBlocking::HookProcess::~HookProcess(void)
0x1800089d7  mov     edx, 28h ; '('; unsigned __int64
0x1800089dc  mov     rcx, rsi; void *
0x1800089df  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800089e4  mov     rdi, [rbx+18h]
0x1800089e8  test    rdi, rdi
0x1800089eb  jz      short loc_180008A02
0x1800089ed  mov     rcx, rdi; this
0x1800089f0  call    ??1HookProcess@DialogBlocking@Internal@Windows@@QEAA@XZ; Windows::Internal::DialogBlocking::HookProcess::~HookProcess(void)
0x1800089f5  mov     edx, 28h ; '('; unsigned __int64
0x1800089fa  mov     rcx, rdi; void *
0x1800089fd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008a02  mov     rbx, [rbx+10h]
0x180008a06  test    rbx, rbx
0x180008a09  jz      short loc_180008A41
0x180008a0b  or      edi, 0FFFFFFFFh
0x180008a0e  mov     eax, edi
0x180008a10  lock xadd [rbx+8], eax
0x180008a15  add     eax, edi
0x180008a17  jnz     short loc_180008A41
0x180008a19  mov     rax, [rbx]
0x180008a1c  mov     rcx, rbx
0x180008a1f  mov     rax, [rax]
0x180008a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a27  mov     eax, edi
0x180008a29  lock xadd [rbx+0Ch], eax
0x180008a2e  add     eax, edi
0x180008a30  jnz     short loc_180008A41
0x180008a32  mov     rax, [rbx]
0x180008a35  mov     rcx, rbx
0x180008a38  mov     rax, [rax+8]
0x180008a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a41  mov     rbx, [rsp+28h+arg_0]
0x180008a46  mov     rsi, [rsp+28h+arg_8]
0x180008a4b  add     rsp, 20h
0x180008a4f  pop     rdi
0x180008a50  retn
```
