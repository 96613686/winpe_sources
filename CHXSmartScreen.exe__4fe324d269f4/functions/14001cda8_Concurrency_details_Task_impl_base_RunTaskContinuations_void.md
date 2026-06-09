# Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)

- ea: `0x14001cda8`
- end: `0x14001cee0`
- name: `?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ`
- size: `312`
- prototype: `void __fastcall(Concurrency::details::_Task_impl_base *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1400161c4`
- `0x14001ac88`
- `0x14001afc0`
- `0x14001be20`
- `0x14001c158`

## callees

- `0x14001cda8`
- `0x14001d0e0`
- `0x140031960`
- `0x140035010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::details::_Task_impl_base::_RunTaskContinuations(
        Concurrency::details::_Task_impl_base *this)
{
  struct Concurrency::details::_ContinuationTaskHandleBase *v2; // rbx
  struct Concurrency::details::_ContinuationTaskHandleBase *v3; // rsi
  __int64 v4; // r8
  char *v5; // rdx
  volatile signed __int32 *v6; // rbx
  Concurrency::details::_Task_impl_base *v7[2]; // [rsp+30h] [rbp-48h] BYREF

  v2 = (struct Concurrency::details::_ContinuationTaskHandleBase *)*((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = 0;
  if ( v2 )
  {
    while ( 1 )
    {
      v3 = (struct Concurrency::details::_ContinuationTaskHandleBase *)*((_QWORD *)v2 + 3);
      *(_OWORD *)v7 = 0;
      (*(void (__fastcall **)(struct Concurrency::details::_ContinuationTaskHandleBase *, Concurrency::details::_Task_impl_base **))(*(_QWORD *)v2 + 8LL))(
        v2,
        v7);
      if ( *((_DWORD *)this + 4) == 4 && !*((_BYTE *)v2 + 40) )
        break;
      if ( *((_DWORD *)v7[0] + 4) == 4 )
        goto LABEL_9;
      Concurrency::details::_Task_impl_base::_ScheduleContinuationTask(v7[0], v2);
LABEL_11:
      v6 = (volatile signed __int32 *)v7[1];
      if ( v7[1] && !_InterlockedDecrement((volatile signed __int32 *)v7[1] + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
        if ( !_InterlockedDecrement(v6 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      }
      v2 = v3;
      if ( !v3 )
        return;
    }
    v5 = (char *)this + 24;
    if ( *((_QWORD *)this + 3) )
    {
      LOBYTE(v4) = 1;
    }
    else
    {
      v5 = (char *)v7[0] + 24;
      v4 = 0;
    }
    LOBYTE(v5) = 1;
    (*(void (__fastcall **)(Concurrency::details::_Task_impl_base *, char *, __int64))(*(_QWORD *)v7[0] + 8LL))(
      v7[0],
      v5,
      v4);
LABEL_9:
    (**(void (__fastcall ***)(struct Concurrency::details::_ContinuationTaskHandleBase *, __int64))v2)(v2, 1);
    goto LABEL_11;
  }
}

```

## disassembly

```asm
0x14001cda8  push    rbx
0x14001cdaa  push    rsi
0x14001cdab  push    rdi
0x14001cdac  push    r14
0x14001cdae  sub     rsp, 58h
0x14001cdb2  mov     rax, cs:__security_cookie
0x14001cdb9  xor     rax, rsp
0x14001cdbc  mov     [rsp+78h+var_38], rax
0x14001cdc1  mov     rdi, rcx
0x14001cdc4  mov     rbx, [rcx+68h]
0x14001cdc8  mov     qword ptr [rcx+68h], 0
0x14001cdd0  test    rbx, rbx
0x14001cdd3  jz      loc_14001CEC9
0x14001cdd9  or      r14d, 0FFFFFFFFh
0x14001cddd  mov     rsi, [rbx+18h]
0x14001cde1  xorps   xmm0, xmm0
0x14001cde4  movups  xmmword ptr [rsp+78h+var_48], xmm0
0x14001cde9  mov     rax, [rbx]
0x14001cdec  lea     rdx, [rsp+78h+var_48]
0x14001cdf1  mov     rcx, rbx
0x14001cdf4  mov     rax, [rax+8]
0x14001cdf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cdfd  nop
0x14001cdfe  mov     eax, [rdi+10h]
0x14001ce01  cmp     eax, 4
0x14001ce04  jnz     short loc_14001CE4A
0x14001ce06  cmp     byte ptr [rbx+28h], 0
0x14001ce0a  jnz     short loc_14001CE4A
0x14001ce0c  lea     rdx, [rdi+18h]
0x14001ce10  mov     rcx, [rsp+78h+var_48]
0x14001ce15  mov     rax, [rcx]
0x14001ce18  mov     rax, [rax+8]
0x14001ce1c  cmp     qword ptr [rdx], 0
0x14001ce20  jz      short loc_14001CE32
0x14001ce22  mov     [rsp+78h+var_58], rdx
0x14001ce27  mov     r9b, 1
0x14001ce2a  mov     r8b, r9b
0x14001ce2d  mov     dl, r9b
0x14001ce30  jmp     short loc_14001CE43
0x14001ce32  lea     rdx, [rcx+18h]
0x14001ce36  mov     [rsp+78h+var_58], rdx
0x14001ce3b  xor     r9d, r9d
0x14001ce3e  xor     r8d, r8d
0x14001ce41  mov     dl, 1
0x14001ce43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ce48  jmp     short loc_14001CE57
0x14001ce4a  mov     rax, [rsp+78h+var_48]
0x14001ce4f  mov     edx, [rax+10h]
0x14001ce52  cmp     edx, 4
0x14001ce55  jnz     short loc_14001CE6D
0x14001ce57  mov     rax, [rbx]
0x14001ce5a  mov     edx, 1
0x14001ce5f  mov     rcx, rbx
0x14001ce62  mov     rax, [rax]
0x14001ce65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ce6a  nop
0x14001ce6b  jmp     short loc_14001CE7B
0x14001ce6d  mov     rdx, rbx; struct Concurrency::details::_ContinuationTaskHandleBase *
0x14001ce70  mov     rcx, [rsp+78h+var_48]; this
0x14001ce75  call    ?_ScheduleContinuationTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_ContinuationTaskHandleBase@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleContinuationTask(Concurrency::details::_ContinuationTaskHandleBase *)
0x14001ce7a  nop
0x14001ce7b  mov     rbx, [rsp+78h+var_48+8]
0x14001ce80  test    rbx, rbx
0x14001ce83  jz      short loc_14001CEBD
0x14001ce85  mov     eax, r14d
0x14001ce88  lock xadd [rbx+8], eax
0x14001ce8d  add     eax, r14d
0x14001ce90  jnz     short loc_14001CEBD
0x14001ce92  mov     rax, [rbx]
0x14001ce95  mov     rcx, rbx
0x14001ce98  mov     rax, [rax]
0x14001ce9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cea0  mov     eax, r14d
0x14001cea3  lock xadd [rbx+0Ch], eax
0x14001cea8  add     eax, r14d
0x14001ceab  jnz     short loc_14001CEBD
0x14001cead  mov     rax, [rbx]
0x14001ceb0  mov     rcx, rbx
0x14001ceb3  mov     rax, [rax+8]
0x14001ceb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cebc  nop
0x14001cebd  mov     rbx, rsi
0x14001cec0  test    rsi, rsi
0x14001cec3  jnz     loc_14001CDDD
0x14001cec9  mov     rcx, [rsp+78h+var_38]
0x14001cece  xor     rcx, rsp; StackCookie
0x14001ced1  call    __security_check_cookie
0x14001ced6  add     rsp, 58h
0x14001ceda  pop     r14
0x14001cedc  pop     rdi
0x14001cedd  pop     rsi
0x14001cede  pop     rbx
0x14001cedf  retn
```
