# Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)

- ea: `0x14001a96c`
- end: `0x14001aa83`
- name: `?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z`
- size: `279`
- prototype: `bool __fastcall(Concurrency::details::_Task_impl_base *__hidden this, const struct std::exception_ptr *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1400330be`
- `0x14003334c`
- `0x140033435`

## callees

- `0x1400017a0`
- `0x14001a96c`
- `0x140035010`

## import_xrefs

- `msvcrt!__ExceptionPtrCopy` at `0x14001a9d5`
- `msvcrt!__ExceptionPtrCopy` at `0x14001a9d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall Concurrency::details::_Task_impl_base::_CancelWithException(
        Concurrency::details::_Task_impl_base *this,
        const struct std::exception_ptr *a2)
{
  __int64 (__fastcall *v4)(Concurrency::details::_Task_impl_base *, __int64, char *, _QWORD, char **); // r14
  __int64 v5; // rbp
  char *v6; // rax
  __int64 v7; // rdx
  char *v8; // rbx
  char *v9; // r8
  char v10; // di
  volatile signed __int32 *v11; // rbx
  char *v13; // [rsp+38h] [rbp-30h] BYREF
  volatile signed __int32 *v14; // [rsp+40h] [rbp-28h]
  char *v15; // [rsp+48h] [rbp-20h]

  v4 = *(__int64 (__fastcall **)(Concurrency::details::_Task_impl_base *, __int64, char *, _QWORD, char **))(*(_QWORD *)this + 8LL);
  v5 = *((_QWORD *)this + 19);
  v6 = (char *)operator new(0x38u);
  v8 = v6;
  v15 = v6;
  if ( v6 )
  {
    *((_DWORD *)v6 + 2) = 1;
    *((_DWORD *)v6 + 3) = 1;
    *(_QWORD *)v6 = &std::_Ref_count_obj<Concurrency::details::_ExceptionHolder>::`vftable';
    _InterlockedExchange((volatile __int32 *)v6 + 4, 0);
    __ExceptionPtrCopy(v6 + 24, a2);
    *((_QWORD *)v8 + 5) = 0;
    *((_QWORD *)v8 + 6) = v5;
  }
  else
  {
    v8 = 0;
  }
  v14 = (volatile signed __int32 *)v8;
  v9 = v8 + 16;
  v13 = v8 + 16;
  LOBYTE(v9) = 1;
  LOBYTE(v7) = 1;
  v10 = v4(this, v7, v9, 0, &v13);
  v11 = v14;
  if ( v14 )
  {
    if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( !_InterlockedDecrement(v11 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x14001a96c  mov     [rsp+arg_10], rbx
0x14001a971  mov     [rsp+arg_18], rbp
0x14001a976  push    rsi
0x14001a977  push    rdi
0x14001a978  push    r14
0x14001a97a  sub     rsp, 50h
0x14001a97e  mov     rsi, rdx
0x14001a981  mov     rdi, rcx
0x14001a984  mov     [rsp+68h+var_38], 0
0x14001a98c  mov     rax, [rcx]
0x14001a98f  mov     r14, [rax+8]
0x14001a993  mov     rbp, [rcx+98h]
0x14001a99a  mov     ecx, 38h ; '8'; Size
0x14001a99f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001a9a4  mov     rbx, rax
0x14001a9a7  mov     [rsp+68h+var_20], rax
0x14001a9ac  test    rax, rax
0x14001a9af  jz      short loc_14001A9E9
0x14001a9b1  mov     dword ptr [rax+8], 1
0x14001a9b8  mov     dword ptr [rax+0Ch], 1
0x14001a9bf  lea     rax, ??_7?$_Ref_count_obj@U_ExceptionHolder@details@Concurrency@@@std@@6B@; const std::_Ref_count_obj<Concurrency::details::_ExceptionHolder>::`vftable'
0x14001a9c6  mov     [rbx], rax
0x14001a9c9  xor     eax, eax
0x14001a9cb  xchg    eax, [rbx+10h]
0x14001a9ce  lea     rcx, [rbx+18h]
0x14001a9d2  mov     rdx, rsi
0x14001a9d5  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x14001a9db  mov     qword ptr [rbx+28h], 0
0x14001a9e3  mov     [rbx+30h], rbp
0x14001a9e7  jmp     short loc_14001A9EB
0x14001a9e9  xor     ebx, ebx
0x14001a9eb  xorps   xmm0, xmm0
0x14001a9ee  movups  [rsp+68h+var_30], xmm0
0x14001a9f3  mov     [rsp+68h+var_38], 1
0x14001a9fb  mov     qword ptr [rsp+68h+var_30+8], rbx
0x14001aa00  lea     r8, [rbx+10h]
0x14001aa04  mov     qword ptr [rsp+68h+var_30], r8
0x14001aa09  lea     rax, [rsp+68h+var_30]
0x14001aa0e  mov     [rsp+68h+var_48], rax
0x14001aa13  xor     r9d, r9d
0x14001aa16  mov     r8b, 1
0x14001aa19  mov     dl, r8b
0x14001aa1c  mov     rcx, rdi
0x14001aa1f  mov     rax, r14
0x14001aa22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aa27  mov     dil, al
0x14001aa2a  mov     rbx, qword ptr [rsp+68h+var_30+8]
0x14001aa2f  test    rbx, rbx
0x14001aa32  jz      short loc_14001AA6B
0x14001aa34  or      esi, 0FFFFFFFFh
0x14001aa37  mov     ecx, esi
0x14001aa39  lock xadd [rbx+8], ecx
0x14001aa3e  add     ecx, esi
0x14001aa40  jnz     short loc_14001AA6B
0x14001aa42  mov     rax, [rbx]
0x14001aa45  mov     rcx, rbx
0x14001aa48  mov     rax, [rax]
0x14001aa4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aa50  mov     eax, esi
0x14001aa52  lock xadd [rbx+0Ch], eax
0x14001aa57  add     eax, esi
0x14001aa59  jnz     short loc_14001AA6B
0x14001aa5b  mov     rax, [rbx]
0x14001aa5e  mov     rcx, rbx
0x14001aa61  mov     rax, [rax+8]
0x14001aa65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aa6a  nop
0x14001aa6b  mov     al, dil
0x14001aa6e  lea     r11, [rsp+68h+var_18]
0x14001aa73  mov     rbx, [r11+30h]
0x14001aa77  mov     rbp, [r11+38h]
0x14001aa7b  mov     rsp, r11
0x14001aa7e  pop     r14
0x14001aa80  pop     rdi
0x14001aa81  pop     rsi
0x14001aa82  retn
```
