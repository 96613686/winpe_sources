# Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)

- ea: `0x180018ac4`
- end: `0x180018bf4`
- name: `?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z`
- size: `304`
- prototype: `char __fastcall(Concurrency::details::_Task_impl_base *this, const struct std::exception_ptr *)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18002ae4d`
- `0x18002b3ff`
- `0x18002b4eb`
- `0x18002b5c6`

## callees

- `0x1800021e4`
- `0x180015e28`
- `0x1800165e8`
- `0x180018ac4`
- `0x18002d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180018b50`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180018b50`

## pseudocode

```c
char __fastcall Concurrency::details::_Task_impl_base::_CancelWithException(
        Concurrency::details::_Task_impl_base *this,
        const struct std::exception_ptr *a2)
{
  __int64 (__fastcall *v4)(Concurrency::details::_Task_impl_base *, __int64, __int64, _QWORD, char **); // rbp
  __int64 v5; // r8
  __int64 v6; // rdx
  char v7; // di
  volatile signed __int32 *v8; // rbx
  char *v10; // [rsp+30h] [rbp-48h] BYREF
  volatile signed __int32 *v11; // [rsp+38h] [rbp-40h]
  _BYTE v12[8]; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v13[24]; // [rsp+48h] [rbp-30h] BYREF
  _DWORD *v14; // [rsp+80h] [rbp+8h]

  v4 = *(__int64 (__fastcall **)(Concurrency::details::_Task_impl_base *, __int64, __int64, _QWORD, char **))(*(_QWORD *)this + 8LL);
  Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(
    (Concurrency::details::_TaskCreationCallstack *)v12,
    (Concurrency::details::_Task_impl_base *)((char *)this + 320));
  v14 = operator new(0x48u);
  *(_OWORD *)v14 = 0;
  v14[2] = 1;
  v14[3] = 1;
  *(_QWORD *)v14 = &std::_Ref_count_obj2<Concurrency::details::_ExceptionHolder>::`vftable';
  v14[4] = 0;
  *((_QWORD *)v14 + 3) = 0;
  *((_QWORD *)v14 + 4) = 0;
  __ExceptionPtrCopy(v14 + 6, a2);
  Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(
    (Concurrency::details::_TaskCreationCallstack *)(v14 + 10),
    (const struct Concurrency::details::_TaskCreationCallstack *)v12);
  v10 = (char *)(v14 + 4);
  v11 = v14;
  LOBYTE(v5) = 1;
  LOBYTE(v6) = 1;
  v7 = v4(this, v6, v5, 0, &v10);
  v8 = v11;
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  std::vector<void *>::~vector<void *>(v13);
  return v7;
}

```

## disassembly

```asm
0x180018ac4  mov     [rsp+arg_8], rbx
0x180018ac9  mov     [rsp+arg_18], rbp
0x180018ace  push    rsi
0x180018acf  push    rdi
0x180018ad0  push    r14
0x180018ad2  sub     rsp, 60h
0x180018ad6  mov     rsi, rdx
0x180018ad9  mov     r14, rcx
0x180018adc  mov     rax, [rcx]
0x180018adf  mov     rbp, [rax+8]
0x180018ae3  lea     rdx, [rcx+140h]; struct Concurrency::details::_TaskCreationCallstack *
0x180018aea  lea     rcx, [rsp+78h+var_38]; this
0x180018aef  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x180018af4  nop
0x180018af5  mov     ecx, 48h ; 'H'; Size
0x180018afa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018aff  mov     rdi, rax
0x180018b02  mov     [rsp+78h+arg_0], rax
0x180018b0a  xorps   xmm0, xmm0
0x180018b0d  movups  xmmword ptr [rax], xmm0
0x180018b10  mov     dword ptr [rax+8], 1
0x180018b17  mov     dword ptr [rax+0Ch], 1
0x180018b1e  lea     rax, ??_7?$_Ref_count_obj2@U_ExceptionHolder@details@Concurrency@@@std@@6B@; const std::_Ref_count_obj2<Concurrency::details::_ExceptionHolder>::`vftable'
0x180018b25  mov     [rdi], rax
0x180018b28  lea     rbx, [rdi+10h]
0x180018b2c  mov     [rsp+78h+arg_10], rbx
0x180018b34  mov     dword ptr [rbx], 0
0x180018b3a  lea     rcx, [rbx+8]
0x180018b3e  mov     qword ptr [rcx], 0
0x180018b45  mov     qword ptr [rcx+8], 0
0x180018b4d  mov     rdx, rsi
0x180018b50  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180018b56  nop
0x180018b57  lea     rcx, [rbx+18h]; this
0x180018b5b  lea     rdx, [rsp+78h+var_38]; struct Concurrency::details::_TaskCreationCallstack *
0x180018b60  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x180018b65  nop
0x180018b66  mov     [rsp+78h+var_48], rbx
0x180018b6b  mov     [rsp+78h+var_40], rdi
0x180018b70  lea     rax, [rsp+78h+var_48]
0x180018b75  mov     [rsp+78h+var_58], rax
0x180018b7a  xor     r9d, r9d
0x180018b7d  mov     r8b, 1
0x180018b80  mov     dl, r8b
0x180018b83  mov     rcx, r14
0x180018b86  mov     rax, rbp
0x180018b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b8e  mov     dil, al
0x180018b91  mov     rbx, [rsp+78h+var_40]
0x180018b96  test    rbx, rbx
0x180018b99  jz      short loc_180018BD2
0x180018b9b  or      esi, 0FFFFFFFFh
0x180018b9e  mov     ecx, esi
0x180018ba0  lock xadd [rbx+8], ecx
0x180018ba5  add     ecx, esi
0x180018ba7  jnz     short loc_180018BD2
0x180018ba9  mov     rdx, [rbx]
0x180018bac  mov     rcx, rbx
0x180018baf  mov     rax, [rdx]
0x180018bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bb7  mov     eax, esi
0x180018bb9  lock xadd [rbx+0Ch], eax
0x180018bbe  add     eax, esi
0x180018bc0  jnz     short loc_180018BD2
0x180018bc2  mov     rax, [rbx]
0x180018bc5  mov     rcx, rbx
0x180018bc8  mov     rax, [rax+8]
0x180018bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bd1  nop
0x180018bd2  lea     rcx, [rsp+78h+var_30]
0x180018bd7  call    ??1?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@XZ; std::vector<void *>::~vector<void *>(void)
0x180018bdc  mov     al, dil
0x180018bdf  lea     r11, [rsp+78h+var_18]
0x180018be4  mov     rbx, [r11+28h]
0x180018be8  mov     rbp, [r11+38h]
0x180018bec  mov     rsp, r11
0x180018bef  pop     r14
0x180018bf1  pop     rdi
0x180018bf2  pop     rsi
0x180018bf3  retn
```
