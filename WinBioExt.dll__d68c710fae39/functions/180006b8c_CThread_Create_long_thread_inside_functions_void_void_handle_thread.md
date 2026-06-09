# CThread::Create(long (*)(thread_inside_functions &,void *),void *,handle_thread *)

- ea: `0x180006b8c`
- end: `0x180006c35`
- name: `?Create@CThread@@SAJP6AJAEAVthread_inside_functions@@PEAX@Z1PEAVhandle_thread@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(int (*)(struct thread_inside_functions *, void *), void *, struct handle_thread *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006150`

## callees

- `0x180001610`
- `0x180006af0`
- `0x180006b40`
- `0x180006b8c`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CThread::Create(
        int (*a1)(struct thread_inside_functions *, void *),
        void *a2,
        struct handle_thread *a3)
{
  unsigned int v5; // ebx
  _QWORD *v6; // rdx
  char v8; // [rsp+20h] [rbp-68h]
  _QWORD v9[3]; // [rsp+30h] [rbp-58h] BYREF
  char v10; // [rsp+48h] [rbp-40h]
  _QWORD *v11; // [rsp+68h] [rbp-20h]

  handle_thread::Close(a3);
  v9[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (*&)(thread_inside_functions &,void *),std::_Ph<1> const &,void * &>,long,thread_inside_functions &>::`vftable';
  v9[1] = CAccountCleanupHandler::DeleteBiometricTemplates;
  v9[2] = a2;
  v10 = v8;
  v11 = v9;
  v5 = CThread::Create(v9, a3);
  if ( v11 )
  {
    v6 = v9;
    LOBYTE(v6) = v11 != v9;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v11 + 32LL))(v11, v6);
  }
  return v5;
}

```

## disassembly

```asm
0x180006b8c  mov     [rsp+arg_0], rbx
0x180006b91  push    rdi
0x180006b92  sub     rsp, 80h
0x180006b99  mov     rax, cs:__security_cookie
0x180006ba0  xor     rax, rsp
0x180006ba3  mov     [rsp+88h+var_18], rax
0x180006ba8  mov     rdi, r8
0x180006bab  mov     rbx, rdx
0x180006bae  mov     rcx, r8; this
0x180006bb1  call    ?Close@handle_thread@@QEAAXXZ; handle_thread::Close(void)
0x180006bb6  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@AEAP6AJAEAVthread_inside_functions@@PEAX@ZAEBU?$_Ph@$00@2@AEAPEAX@std@@JAEAVthread_inside_functions@@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (*&)(thread_inside_functions &,void *),std::_Ph<1> const &,void * &>,long,thread_inside_functions &>::`vftable'
0x180006bbd  mov     [rsp+88h+var_58], rax
0x180006bc2  lea     rax, ?DeleteBiometricTemplates@CAccountCleanupHandler@@CAJAEAVthread_inside_functions@@PEAX@Z; CAccountCleanupHandler::DeleteBiometricTemplates(thread_inside_functions &,void *)
0x180006bc9  mov     [rsp+88h+var_50], rax
0x180006bce  mov     [rsp+88h+var_48], rbx
0x180006bd3  mov     al, [rsp+88h+var_68]
0x180006bd7  mov     [rsp+88h+var_40], al
0x180006bdb  lea     rax, [rsp+88h+var_58]
0x180006be0  mov     [rsp+88h+var_20], rax
0x180006be5  mov     rdx, rdi
0x180006be8  lea     rcx, [rsp+88h+var_58]
0x180006bed  call    ?Create@CThread@@CAJAEBV?$function@$$A6AJAEAVthread_inside_functions@@@Z@std@@PEAPEAVthread_outside_functions@@@Z; CThread::Create(std::function<long (thread_inside_functions &)> const &,thread_outside_functions * *)
0x180006bf2  mov     ebx, eax
0x180006bf4  mov     rcx, [rsp+88h+var_20]
0x180006bf9  test    rcx, rcx
0x180006bfc  jz      short loc_180006C15
0x180006bfe  mov     rax, [rcx]
0x180006c01  lea     rdx, [rsp+88h+var_58]
0x180006c06  cmp     rcx, rdx
0x180006c09  setnz   dl
0x180006c0c  mov     rax, [rax+20h]
0x180006c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c15  mov     eax, ebx
0x180006c17  mov     rcx, [rsp+88h+var_18]
0x180006c1c  xor     rcx, rsp; StackCookie
0x180006c1f  call    __security_check_cookie
0x180006c24  mov     rbx, [rsp+88h+arg_0]
0x180006c2c  add     rsp, 80h
0x180006c33  pop     rdi
0x180006c34  retn
```
