# Concurrency::details::_Task_impl_base::~_Task_impl_base(void)

- ea: `0x140015c18`
- end: `0x140015cfc`
- name: `??1_Task_impl_base@details@Concurrency@@UEAA@XZ`
- size: `228`
- prototype: `void __fastcall(Concurrency::details::_Task_impl_base *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140015790`
- `0x140015820`
- `0x140017140`
- `0x140032ae2`

## callees

- `0x140015c18`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140015c9e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140015c9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015cf5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::_Task_impl_base::~_Task_impl_base(Concurrency::details::_Task_impl_base *this)
{
  volatile signed __int32 *v2; // rcx
  volatile signed __int32 *v3; // rbx
  volatile signed __int32 *v4; // rbx

  *(_QWORD *)this = &Concurrency::details::_Task_impl_base::`vftable';
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 14);
  if ( v2 != (volatile signed __int32 *)2 && _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 17);
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  v4 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  CloseHandle(*((HANDLE *)this + 1));
}

```

## disassembly

```asm
0x140015c18  mov     [rsp+arg_0], rbx
0x140015c1d  mov     [rsp+arg_8], rsi
0x140015c22  push    rdi
0x140015c23  sub     rsp, 20h
0x140015c27  mov     rdi, rcx
0x140015c2a  lea     rax, ??_7_Task_impl_base@details@Concurrency@@6B@; const Concurrency::details::_Task_impl_base::`vftable'
0x140015c31  mov     [rcx], rax
0x140015c34  mov     rcx, [rcx+70h]
0x140015c38  or      esi, 0FFFFFFFFh
0x140015c3b  cmp     rcx, 2
0x140015c3f  jz      short loc_140015C5A
0x140015c41  mov     eax, esi
0x140015c43  lock xadd [rcx+8], eax
0x140015c48  cmp     eax, 1
0x140015c4b  jnz     short loc_140015C5A
0x140015c4d  mov     rax, [rcx]
0x140015c50  mov     rax, [rax+8]
0x140015c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015c59  nop
0x140015c5a  mov     rbx, [rdi+88h]
0x140015c61  test    rbx, rbx
0x140015c64  jz      short loc_140015C9A
0x140015c66  mov     eax, esi
0x140015c68  lock xadd [rbx+8], eax
0x140015c6d  add     eax, esi
0x140015c6f  jnz     short loc_140015C9A
0x140015c71  mov     rax, [rbx]
0x140015c74  mov     rcx, rbx
0x140015c77  mov     rax, [rax]
0x140015c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015c7f  mov     eax, esi
0x140015c81  lock xadd [rbx+0Ch], eax
0x140015c86  add     eax, esi
0x140015c88  jnz     short loc_140015C9A
0x140015c8a  mov     rax, [rbx]
0x140015c8d  mov     rcx, rbx
0x140015c90  mov     rax, [rax+8]
0x140015c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015c99  nop
0x140015c9a  lea     rcx, [rdi+28h]; lpCriticalSection
0x140015c9e  call    cs:__imp_DeleteCriticalSection
0x140015ca4  nop
0x140015ca5  mov     rbx, [rdi+20h]
0x140015ca9  test    rbx, rbx
0x140015cac  jz      short loc_140015CE2
0x140015cae  mov     eax, esi
0x140015cb0  lock xadd [rbx+8], eax
0x140015cb5  add     eax, esi
0x140015cb7  jnz     short loc_140015CE2
0x140015cb9  mov     rax, [rbx]
0x140015cbc  mov     rcx, rbx
0x140015cbf  mov     rax, [rax]
0x140015cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015cc7  mov     eax, esi
0x140015cc9  lock xadd [rbx+0Ch], eax
0x140015cce  add     eax, esi
0x140015cd0  jnz     short loc_140015CE2
0x140015cd2  mov     rax, [rbx]
0x140015cd5  mov     rcx, rbx
0x140015cd8  mov     rax, [rax+8]
0x140015cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015ce1  nop
0x140015ce2  mov     rcx, [rdi+8]
0x140015ce6  mov     rbx, [rsp+28h+arg_0]
0x140015ceb  mov     rsi, [rsp+28h+arg_8]
0x140015cf0  add     rsp, 20h
0x140015cf4  pop     rdi
0x140015cf5  jmp     cs:__imp_CloseHandle
```
