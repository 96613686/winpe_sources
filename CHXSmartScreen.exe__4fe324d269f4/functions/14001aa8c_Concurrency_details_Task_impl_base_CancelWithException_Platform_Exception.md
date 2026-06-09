# Concurrency::details::_Task_impl_base::_CancelWithException(Platform::Exception *)

- ea: `0x14001aa8c`
- end: `0x14001ac04`
- name: `?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NPE$AAVException@Platform@@@Z`
- size: `376`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1400161c4`
- `0x14003308c`
- `0x140033316`
- `0x1400333ff`

## callees

- `0x1400017a0`
- `0x14001aa8c`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `msvcrt!__ExceptionPtrCreate` at `0x14001ab25`
- `msvcrt!__ExceptionPtrCreate` at `0x14001ab25`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall Concurrency::details::_Task_impl_base::_CancelWithException(_QWORD *a1, __int64 a2)
{
  __int64 (__fastcall *v4)(_QWORD *, __int64, char *, _QWORD, char **); // r15
  __int64 v5; // rbp
  char *v6; // rax
  __int64 v7; // rdx
  char *v8; // rdi
  char *v9; // r8
  char v10; // si
  volatile signed __int32 *v11; // rdi
  char *v13; // [rsp+38h] [rbp-60h] BYREF
  volatile signed __int32 *v14; // [rsp+40h] [rbp-58h]
  char *v15; // [rsp+48h] [rbp-50h]
  char *v16; // [rsp+50h] [rbp-48h]
  __int64 v17; // [rsp+58h] [rbp-40h]

  v17 = a2;
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  v17 = a2;
  v4 = *(__int64 (__fastcall **)(_QWORD *, __int64, char *, _QWORD, char **))(*a1 + 8LL);
  v5 = a1[19];
  v6 = (char *)operator new(0x38u);
  v8 = v6;
  v15 = v6;
  if ( v6 )
  {
    *((_DWORD *)v6 + 2) = 1;
    *((_DWORD *)v6 + 3) = 1;
    *(_QWORD *)v6 = &std::_Ref_count_obj<Concurrency::details::_ExceptionHolder>::`vftable';
    v16 = v6 + 16;
    _InterlockedExchange((volatile __int32 *)v6 + 4, 0);
    __ExceptionPtrCreate(v6 + 24);
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    *((_QWORD *)v8 + 5) = a2;
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
  v10 = v4(a1, v7, v9, 0, &v13);
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
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
  return v10;
}

```

## disassembly

```asm
0x14001aa8c  mov     [rsp+arg_10], rbx
0x14001aa91  push    rbp
0x14001aa92  push    rsi
0x14001aa93  push    rdi
0x14001aa94  push    r14
0x14001aa96  push    r15
0x14001aa98  sub     rsp, 70h
0x14001aa9c  mov     rax, cs:__security_cookie
0x14001aaa3  xor     rax, rsp
0x14001aaa6  mov     [rsp+98h+var_38], rax
0x14001aaab  mov     rbx, rdx
0x14001aaae  mov     r14, rcx
0x14001aab1  mov     [rsp+98h+var_40], rdx
0x14001aab6  mov     [rsp+98h+var_68], 0
0x14001aabe  test    rdx, rdx
0x14001aac1  jz      short loc_14001AAD2
0x14001aac3  mov     rax, [rdx]
0x14001aac6  mov     rcx, rdx
0x14001aac9  mov     rax, [rax+8]
0x14001aacd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aad2  mov     [rsp+98h+var_40], rbx
0x14001aad7  mov     rax, [r14]
0x14001aada  mov     r15, [rax+8]
0x14001aade  mov     rbp, [r14+98h]
0x14001aae5  mov     ecx, 38h ; '8'; Size
0x14001aaea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001aaef  mov     rdi, rax
0x14001aaf2  mov     [rsp+98h+var_50], rax
0x14001aaf7  test    rax, rax
0x14001aafa  jz      short loc_14001AB4A
0x14001aafc  mov     dword ptr [rax+8], 1
0x14001ab03  mov     dword ptr [rax+0Ch], 1
0x14001ab0a  lea     rax, ??_7?$_Ref_count_obj@U_ExceptionHolder@details@Concurrency@@@std@@6B@; const std::_Ref_count_obj<Concurrency::details::_ExceptionHolder>::`vftable'
0x14001ab11  mov     [rdi], rax
0x14001ab14  lea     rsi, [rdi+10h]
0x14001ab18  mov     [rsp+98h+var_48], rsi
0x14001ab1d  xor     eax, eax
0x14001ab1f  xchg    eax, [rsi]
0x14001ab21  lea     rcx, [rsi+8]
0x14001ab25  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x14001ab2b  nop
0x14001ab2c  test    rbx, rbx
0x14001ab2f  jz      short loc_14001AB40
0x14001ab31  mov     rax, [rbx]
0x14001ab34  mov     rcx, rbx
0x14001ab37  mov     rax, [rax+8]
0x14001ab3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ab40  mov     [rsi+18h], rbx
0x14001ab44  mov     [rsi+20h], rbp
0x14001ab48  jmp     short loc_14001AB4C
0x14001ab4a  xor     edi, edi
0x14001ab4c  xorps   xmm0, xmm0
0x14001ab4f  movups  [rsp+98h+var_60], xmm0
0x14001ab54  mov     [rsp+98h+var_68], 1
0x14001ab5c  mov     qword ptr [rsp+98h+var_60+8], rdi
0x14001ab61  lea     r8, [rdi+10h]
0x14001ab65  mov     qword ptr [rsp+98h+var_60], r8
0x14001ab6a  lea     rax, [rsp+98h+var_60]
0x14001ab6f  mov     [rsp+98h+var_78], rax
0x14001ab74  xor     r9d, r9d
0x14001ab77  mov     r8b, 1
0x14001ab7a  mov     dl, r8b
0x14001ab7d  mov     rcx, r14
0x14001ab80  mov     rax, r15
0x14001ab83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ab88  mov     sil, al
0x14001ab8b  mov     rdi, qword ptr [rsp+98h+var_60+8]
0x14001ab90  test    rdi, rdi
0x14001ab93  jz      short loc_14001ABCC
0x14001ab95  or      ebp, 0FFFFFFFFh
0x14001ab98  mov     ecx, ebp
0x14001ab9a  lock xadd [rdi+8], ecx
0x14001ab9f  add     ecx, ebp
0x14001aba1  jnz     short loc_14001ABCC
0x14001aba3  mov     rax, [rdi]
0x14001aba6  mov     rcx, rdi
0x14001aba9  mov     rax, [rax]
0x14001abac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001abb1  mov     eax, ebp
0x14001abb3  lock xadd [rdi+0Ch], eax
0x14001abb8  add     eax, ebp
0x14001abba  jnz     short loc_14001ABCC
0x14001abbc  mov     rax, [rdi]
0x14001abbf  mov     rcx, rdi
0x14001abc2  mov     rax, [rax+8]
0x14001abc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001abcb  nop
0x14001abcc  test    rbx, rbx
0x14001abcf  jz      short loc_14001ABE0
0x14001abd1  mov     rax, [rbx]
0x14001abd4  mov     rcx, rbx
0x14001abd7  mov     rax, [rax+10h]
0x14001abdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001abe0  mov     al, sil
0x14001abe3  mov     rcx, [rsp+98h+var_38]
0x14001abe8  xor     rcx, rsp; StackCookie
0x14001abeb  call    __security_check_cookie
0x14001abf0  mov     rbx, [rsp+98h+arg_10]
0x14001abf8  add     rsp, 70h
0x14001abfc  pop     r15
0x14001abfe  pop     r14
0x14001ac00  pop     rdi
0x14001ac01  pop     rsi
0x14001ac02  pop     rbp
0x14001ac03  retn
```
