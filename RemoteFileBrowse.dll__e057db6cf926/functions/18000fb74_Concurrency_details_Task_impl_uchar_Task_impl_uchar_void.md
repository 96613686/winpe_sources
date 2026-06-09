# Concurrency::details::_Task_impl<uchar>::~_Task_impl<uchar>(void)

- ea: `0x18000fb74`
- end: `0x18000fc07`
- name: `??1?$_Task_impl@E@details@Concurrency@@UEAA@XZ`
- size: `147`
- prototype: `void __fastcall(Concurrency::details::_Task_impl_base *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800106c0`

## callees

- `0x18000fb74`
- `0x180010008`
- `0x180011c30`
- `0x180019010`

## pseudocode

```c
void __fastcall Concurrency::details::_Task_impl<unsigned char>::~_Task_impl<unsigned char>(
        Concurrency::details::_Task_impl_base *this)
{
  struct Concurrency::details::_CancellationTokenRegistration *v2; // rdx
  volatile signed __int32 *v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &Concurrency::details::_Task_impl<unsigned char>::`vftable';
  v2 = (struct Concurrency::details::_CancellationTokenRegistration *)*((_QWORD *)this + 16);
  if ( v2 )
  {
    Concurrency::details::_CancellationTokenState::_DeregisterCallback(
      *((Concurrency::details::_CancellationTokenState **)this + 15),
      v2);
    v3 = (volatile signed __int32 *)*((_QWORD *)this + 16);
    if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    *((_QWORD *)this + 16) = 0;
  }
  v4 = *((_QWORD *)this + 54);
  if ( v4 )
  {
    LOBYTE(v2) = v4 != (_QWORD)this + 376;
    (*(void (__fastcall **)(__int64, struct Concurrency::details::_CancellationTokenRegistration *))(*(_QWORD *)v4 + 32LL))(
      v4,
      v2);
    *((_QWORD *)this + 54) = 0;
  }
  Concurrency::details::_Task_impl_base::~_Task_impl_base(this);
}

```

## disassembly

```asm
0x18000fb74  mov     [rsp+arg_8], rbx
0x18000fb79  push    rdi
0x18000fb7a  sub     rsp, 20h
0x18000fb7e  mov     rbx, rcx
0x18000fb81  lea     rax, ??_7?$_Task_impl@E@details@Concurrency@@6B@; const Concurrency::details::_Task_impl<uchar>::`vftable'
0x18000fb88  mov     [rcx], rax
0x18000fb8b  mov     rdx, [rcx+80h]; struct Concurrency::details::_CancellationTokenRegistration *
0x18000fb92  test    rdx, rdx
0x18000fb95  jz      short loc_18000FBCB
0x18000fb97  mov     rcx, [rcx+78h]; this
0x18000fb9b  call    ?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z; Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)
0x18000fba0  mov     rcx, [rbx+80h]
0x18000fba7  or      eax, 0FFFFFFFFh
0x18000fbaa  lock xadd [rcx+8], eax
0x18000fbaf  cmp     eax, 1
0x18000fbb2  jnz     short loc_18000FBC0
0x18000fbb4  mov     rax, [rcx]
0x18000fbb7  mov     rax, [rax+8]
0x18000fbbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbc0  mov     qword ptr [rbx+80h], 0
0x18000fbcb  lea     rdi, [rbx+178h]
0x18000fbd2  mov     rcx, [rdi+38h]
0x18000fbd6  test    rcx, rcx
0x18000fbd9  jz      short loc_18000FBF5
0x18000fbdb  mov     rax, [rcx]
0x18000fbde  cmp     rcx, rdi
0x18000fbe1  setnz   dl
0x18000fbe4  mov     rax, [rax+20h]
0x18000fbe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbed  mov     qword ptr [rdi+38h], 0
0x18000fbf5  mov     rcx, rbx; this
0x18000fbf8  mov     rbx, [rsp+28h+arg_8]
0x18000fbfd  add     rsp, 20h
0x18000fc01  pop     rdi
0x18000fc02  jmp     ??1_Task_impl_base@details@Concurrency@@UEAA@XZ; Concurrency::details::_Task_impl_base::~_Task_impl_base(void)
```
