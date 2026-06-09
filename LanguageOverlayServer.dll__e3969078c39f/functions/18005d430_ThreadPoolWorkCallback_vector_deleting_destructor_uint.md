# ThreadPoolWorkCallback::`vector deleting destructor'(uint)

- ea: `0x18005d430`
- end: `0x18005d4b1`
- name: `??_EThreadPoolWorkCallback@@UEAAPEAXI@Z`
- size: `129`
- prototype: `ThreadPoolWorkCallback *__fastcall(ThreadPoolWorkCallback *this, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180003ea0`
- `0x18005d430`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18005d455`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18005d455`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005d45e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005d45e`

## pseudocode

```c
ThreadPoolWorkCallback *__fastcall ThreadPoolWorkCallback::`vector deleting destructor'(
        ThreadPoolWorkCallback *this,
        __int64 a2)
{
  struct _TP_WORK *v2; // rdi
  char v3; // si
  __int64 v5; // rcx

  v2 = (struct _TP_WORK *)*((_QWORD *)this + 9);
  v3 = a2;
  if ( v2 )
  {
    WaitForThreadpoolWorkCallbacks(v2, 1);
    CloseThreadpoolWork(v2);
  }
  v5 = *((_QWORD *)this + 8);
  if ( v5 )
  {
    LOBYTE(a2) = v5 != (_QWORD)this + 8;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 32LL))(v5, a2);
    *((_QWORD *)this + 8) = 0;
  }
  if ( (v3 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18005d430  mov     [rsp+arg_0], rbx
0x18005d435  mov     [rsp+arg_8], rsi
0x18005d43a  push    rdi
0x18005d43b  sub     rsp, 20h
0x18005d43f  mov     rdi, [rcx+48h]
0x18005d443  mov     esi, edx
0x18005d445  mov     rbx, rcx
0x18005d448  test    rdi, rdi
0x18005d44b  jz      short loc_18005D464
0x18005d44d  mov     edx, 1; fCancelPendingCallbacks
0x18005d452  mov     rcx, rdi; pwk
0x18005d455  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18005d45b  mov     rcx, rdi; pwk
0x18005d45e  call    cs:__imp_CloseThreadpoolWork
0x18005d464  lea     rdi, [rbx+8]
0x18005d468  mov     rcx, [rdi+38h]
0x18005d46c  test    rcx, rcx
0x18005d46f  jz      short loc_18005D48B
0x18005d471  mov     rax, [rcx]
0x18005d474  cmp     rcx, rdi
0x18005d477  setnz   dl
0x18005d47a  mov     rax, [rax+20h]
0x18005d47e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d483  mov     qword ptr [rdi+38h], 0
0x18005d48b  test    sil, 1
0x18005d48f  jz      short loc_18005D49E
0x18005d491  mov     edx, 58h ; 'X'; unsigned __int64
0x18005d496  mov     rcx, rbx; void *
0x18005d499  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005d49e  mov     rsi, [rsp+28h+arg_8]
0x18005d4a3  mov     rax, rbx
0x18005d4a6  mov     rbx, [rsp+28h+arg_0]
0x18005d4ab  add     rsp, 20h
0x18005d4af  pop     rdi
0x18005d4b0  retn
```
