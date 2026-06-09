# Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)

- ea: `0x18001c324`
- end: `0x18001c3f8`
- name: `?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z`
- size: `212`
- prototype: `char __fastcall(Concurrency::details::_Task_impl_base *this, const struct std::exception_ptr *)`
- caller_count: `5`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180023ad8`
- `0x1800241a0`
- `0x1800241f2`
- `0x180024293`
- `0x180024316`

## callees

- `0x18000288c`
- `0x18000c9e0`
- `0x1800102c4`
- `0x18001c324`
- `0x18001cc40`
- `0x18001dd48`
- `0x180025010`

## pseudocode

```c
char __fastcall Concurrency::details::_Task_impl_base::_CancelWithException(
        Concurrency::details::_Task_impl_base *this,
        const struct std::exception_ptr *a2)
{
  __int64 (__fastcall *v4)(Concurrency::details::_Task_impl_base *, __int64, __int64, _QWORD, _DWORD **); // rbp
  __int64 v5; // r8
  __int64 v6; // rdx
  char v7; // bl
  _DWORD *v9; // [rsp+30h] [rbp-48h] BYREF
  std::_Ref_count_base *v10; // [rsp+38h] [rbp-40h]
  _BYTE v11[8]; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v12[24]; // [rsp+48h] [rbp-30h] BYREF
  std::_Ref_count_base *v13; // [rsp+80h] [rbp+8h]

  v4 = *(__int64 (__fastcall **)(Concurrency::details::_Task_impl_base *, __int64, __int64, _QWORD, _DWORD **))(*(_QWORD *)this + 8LL);
  Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(
    (Concurrency::details::_TaskCreationCallstack *)v11,
    (Concurrency::details::_Task_impl_base *)((char *)this + 320));
  v13 = (std::_Ref_count_base *)operator new(0x48u);
  *(_OWORD *)v13 = 0;
  *((_DWORD *)v13 + 2) = 1;
  *((_DWORD *)v13 + 3) = 1;
  *(_QWORD *)v13 = &std::_Ref_count_obj2<Concurrency::details::_ExceptionHolder>::`vftable';
  std::_Construct_in_place<Concurrency::details::_ExceptionHolder,std::exception_ptr const &,Concurrency::details::_TaskCreationCallstack>(
    (_DWORD *)v13 + 4,
    a2,
    (const struct Concurrency::details::_TaskCreationCallstack *)v11);
  v9 = (_DWORD *)((char *)v13 + 16);
  v10 = v13;
  LOBYTE(v5) = 1;
  LOBYTE(v6) = 1;
  v7 = v4(this, v6, v5, 0, &v9);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  std::vector<void *>::_Tidy(v12);
  return v7;
}

```

## disassembly

```asm
0x18001c324  mov     [rsp+arg_8], rbx
0x18001c329  mov     [rsp+arg_10], rbp
0x18001c32e  push    rsi
0x18001c32f  push    rdi
0x18001c330  push    r14
0x18001c332  sub     rsp, 60h
0x18001c336  mov     rsi, rdx
0x18001c339  mov     r14, rcx
0x18001c33c  mov     rax, [rcx]
0x18001c33f  mov     rbp, [rax+8]
0x18001c343  lea     rdx, [rcx+140h]; struct Concurrency::details::_TaskCreationCallstack *
0x18001c34a  lea     rcx, [rsp+78h+var_38]; this
0x18001c34f  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x18001c354  nop
0x18001c355  mov     ecx, 48h ; 'H'; Size
0x18001c35a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c35f  mov     rdi, rax
0x18001c362  mov     [rsp+78h+arg_0], rax
0x18001c36a  xorps   xmm0, xmm0
0x18001c36d  movups  xmmword ptr [rax], xmm0
0x18001c370  mov     dword ptr [rax+8], 1
0x18001c377  mov     dword ptr [rax+0Ch], 1
0x18001c37e  lea     rax, ??_7?$_Ref_count_obj2@U_ExceptionHolder@details@Concurrency@@@std@@6B@; const std::_Ref_count_obj2<Concurrency::details::_ExceptionHolder>::`vftable'
0x18001c385  mov     [rdi], rax
0x18001c388  lea     rbx, [rdi+10h]
0x18001c38c  lea     r8, [rsp+78h+var_38]
0x18001c391  mov     rdx, rsi
0x18001c394  mov     rcx, rbx
0x18001c397  call    ??$_Construct_in_place@U_ExceptionHolder@details@Concurrency@@AEBVexception_ptr@std@@V_TaskCreationCallstack@23@@std@@YAXAEAU_ExceptionHolder@details@Concurrency@@AEBVexception_ptr@0@$$QEAV_TaskCreationCallstack@23@@Z; std::_Construct_in_place<Concurrency::details::_ExceptionHolder,std::exception_ptr const &,Concurrency::details::_TaskCreationCallstack>(Concurrency::details::_ExceptionHolder &,std::exception_ptr const &,Concurrency::details::_TaskCreationCallstack &&)
0x18001c39c  nop
0x18001c39d  mov     [rsp+78h+var_48], rbx
0x18001c3a2  mov     [rsp+78h+var_40], rdi
0x18001c3a7  lea     rax, [rsp+78h+var_48]
0x18001c3ac  mov     [rsp+78h+var_58], rax
0x18001c3b1  xor     r9d, r9d
0x18001c3b4  mov     r8b, 1
0x18001c3b7  mov     dl, r8b
0x18001c3ba  mov     rcx, r14
0x18001c3bd  mov     rax, rbp
0x18001c3c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3c5  mov     bl, al
0x18001c3c7  mov     rcx, [rsp+78h+var_40]; this
0x18001c3cc  test    rcx, rcx
0x18001c3cf  jz      short loc_18001C3D7
0x18001c3d1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001c3d6  nop
0x18001c3d7  lea     rcx, [rsp+78h+var_30]
0x18001c3dc  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18001c3e1  mov     al, bl
0x18001c3e3  lea     r11, [rsp+78h+var_18]
0x18001c3e8  mov     rbx, [r11+28h]
0x18001c3ec  mov     rbp, [r11+30h]
0x18001c3f0  mov     rsp, r11
0x18001c3f3  pop     r14
0x18001c3f5  pop     rdi
0x18001c3f6  pop     rsi
0x18001c3f7  retn
```
