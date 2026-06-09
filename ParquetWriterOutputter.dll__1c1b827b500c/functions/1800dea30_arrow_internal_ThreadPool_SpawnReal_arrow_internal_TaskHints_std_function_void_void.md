# arrow::internal::ThreadPool::SpawnReal(arrow::internal::TaskHints,std::function<void (void)>)

- ea: `0x1800dea30`
- end: `0x1800debba`
- name: `?SpawnReal@ThreadPool@internal@arrow@@MEAA?AVStatus@3@UTaskHints@23@V?$function@$$A6AXXZ@std@@@Z`
- size: `394`
- prototype: `__int64 __fastcall(arrow::internal::ThreadPool *this)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800997f0`
- `0x1800dd260`
- `0x1800dd910`
- `0x1800dea30`
- `0x1800df150`
- `0x1802f0fb0`
- `0x180307e68`
- `0x180307e8c`
- `0x180307f98`
- `0x18030a13c`
- `0x180358070`

## string_xrefs

- `0x1800dea81`: `operation forbidden during or after shutdown`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall arrow::internal::ThreadPool::SpawnReal(
        arrow::internal::ThreadPool *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  struct _Mtx_internal_imp_t *v7; // rbx
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rdi
  unsigned __int64 v13; // rcx
  __int64 v14; // r15
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax

  v7 = (struct _Mtx_internal_imp_t *)*((_QWORD *)this + 3);
  v8 = Mtx_lock(v7);
  if ( v8 )
    std::_Throw_C_error(v8);
  if ( *(_BYTE *)(*((_QWORD *)this + 3) + 308LL) )
  {
    arrow::Status::Invalid<char const (&)[65]>(a2, "operation forbidden during or after shutdown");
    v9 = Mtx_unlock(v7);
    if ( v9 )
      std::_Throw_C_error(v9);
    v11 = *(_QWORD *)(a4 + 56);
    if ( v11 )
    {
LABEL_17:
      LOBYTE(v10) = v11 != a4;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 32LL))(v11, v10);
      *(_QWORD *)(a4 + 56) = 0;
    }
  }
  else
  {
    arrow::internal::ThreadPool::CollectFinishedWorkersUnlocked(this);
    v12 = (_QWORD *)(*((_QWORD *)this + 3) + 264LL);
    v13 = *(_QWORD *)(*((_QWORD *)this + 3) + 280LL);
    if ( v13 <= *(_QWORD *)(*((_QWORD *)this + 3) + 296LL) + 1LL )
    {
      std::deque<std::function<void (void)>>::_Growmap(*((_QWORD *)this + 3) + 264LL, 1);
      v13 = v12[2];
    }
    v12[3] &= v13 - 1;
    v14 = 8 * ((v12[4] + v12[3]) & (v12[2] - 1LL));
    v15 = v12[1];
    if ( !*(_QWORD *)(v15 + v14) )
    {
      *(_QWORD *)(v14 + v12[1]) = operator new(0x40u);
      v15 = v12[1];
    }
    std::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)>::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)>(
      *(_QWORD *)(v14 + v15),
      a4);
    ++v12[4];
    v16 = Mtx_unlock(v7);
    if ( v16 )
      std::_Throw_C_error(v16);
    v17 = Cnd_signal((_Cnd_t)(*((_QWORD *)this + 3) + 80LL));
    if ( v17 )
      std::_Throw_C_error(v17);
    *(_QWORD *)(a2 + 8) = 0;
    v11 = *(_QWORD *)(a4 + 56);
    if ( v11 )
      goto LABEL_17;
  }
  return a2;
}

```

## disassembly

```asm
0x1800dea30  mov     [rsp+arg_18], r9
0x1800dea35  push    rbp
0x1800dea36  push    rsi
0x1800dea37  push    rdi
0x1800dea38  push    r14
0x1800dea3a  push    r15
0x1800dea3c  sub     rsp, 30h
0x1800dea40  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x1800dea49  mov     [rsp+58h+arg_8], rbx
0x1800dea4e  mov     rsi, r9
0x1800dea51  mov     rbp, rdx
0x1800dea54  mov     r14, rcx
0x1800dea57  mov     rbx, [rcx+18h]
0x1800dea5b  mov     [rsp+58h+arg_0], rbx
0x1800dea60  mov     rcx, rbx; _Mtx_t
0x1800dea63  call    _Mtx_lock
0x1800dea68  test    eax, eax
0x1800dea6a  jz      short loc_1800DEA74
0x1800dea6c  mov     ecx, eax; int
0x1800dea6e  call    ?_Throw_C_error@std@@YAXH@Z; std::_Throw_C_error(int)
0x1800dea73  nop
0x1800dea74  mov     rax, [r14+18h]
0x1800dea78  cmp     byte ptr [rax+134h], 0
0x1800dea7f  jz      short loc_1800DEACC
0x1800dea81  lea     rdx, aOperationForbi_0; "operation forbidden during or after shu"...
0x1800dea88  mov     rcx, rbp
0x1800dea8b  call    ??$Invalid@AEAY0EB@$$CBD@Status@arrow@@SA?AV01@AEAY0EB@$$CBD@Z; arrow::Status::Invalid<char const (&)[65]>(char const (&)[65])
0x1800dea90  nop
0x1800dea91  mov     rcx, rbx; _Mtx_t
0x1800dea94  call    _Mtx_unlock
0x1800dea99  test    eax, eax
0x1800dea9b  jz      short loc_1800DEAA5
0x1800dea9d  mov     ecx, eax; int
0x1800dea9f  call    ?_Throw_C_error@std@@YAXH@Z; std::_Throw_C_error(int)
0x1800deaa4  nop
0x1800deaa5  mov     rcx, [rsi+38h]
0x1800deaa9  test    rcx, rcx
0x1800deaac  jz      loc_1800DEBA6
0x1800deab2  mov     rax, [rcx]
0x1800deab5  cmp     rcx, rsi
0x1800deab8  setnz   dl
0x1800deabb  mov     rax, [rax+20h]
0x1800deabf  call    cs:__guard_dispatch_icall_fptr
0x1800deac5  xor     ebx, ebx
0x1800deac7  jmp     loc_1800DEBA2
0x1800deacc  mov     rcx, r14; this
0x1800deacf  call    ?CollectFinishedWorkersUnlocked@ThreadPool@internal@arrow@@IEAAXXZ; arrow::internal::ThreadPool::CollectFinishedWorkersUnlocked(void)
0x1800dead4  mov     rdi, [r14+18h]
0x1800dead8  add     rdi, 108h
0x1800deadf  mov     rcx, [rdi+10h]
0x1800deae3  mov     rax, [rdi+20h]
0x1800deae7  inc     rax
0x1800deaea  cmp     rcx, rax
0x1800deaed  ja      short loc_1800DEB00
0x1800deaef  mov     edx, 1
0x1800deaf4  mov     rcx, rdi
0x1800deaf7  call    ?_Growmap@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@IEAAX_K@Z; std::deque<std::function<void (void)>>::_Growmap(unsigned __int64)
0x1800deafc  mov     rcx, [rdi+10h]
0x1800deb00  lea     rax, [rcx-1]
0x1800deb04  and     [rdi+18h], rax
0x1800deb08  mov     rdx, [rdi+18h]
0x1800deb0c  add     rdx, [rdi+20h]
0x1800deb10  mov     rax, [rdi+10h]
0x1800deb14  dec     rax
0x1800deb17  and     rax, rdx
0x1800deb1a  lea     r15, ds:0[rax*8]
0x1800deb22  mov     rcx, [rdi+8]
0x1800deb26  cmp     qword ptr [rcx+r15], 0
0x1800deb2b  jnz     short loc_1800DEB43
0x1800deb2d  mov     ecx, 40h ; '@'; Size
0x1800deb32  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800deb37  mov     rcx, [rdi+8]
0x1800deb3b  mov     [r15+rcx], rax
0x1800deb3f  mov     rcx, [rdi+8]
0x1800deb43  mov     rdx, rsi
0x1800deb46  mov     rcx, [r15+rcx]
0x1800deb4a  call    ??0?$function@$$A6A?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@compute@arrow@@AEBUKernelInitArgs@45@@Z@std@@QEAA@$$QEAV01@@Z; std::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)>::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)>(std::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)> &&)
0x1800deb4f  inc     qword ptr [rdi+20h]
0x1800deb53  mov     rcx, rbx; _Mtx_t
0x1800deb56  call    _Mtx_unlock
0x1800deb5b  test    eax, eax
0x1800deb5d  jz      short loc_1800DEB67
0x1800deb5f  mov     ecx, eax; int
0x1800deb61  call    ?_Throw_C_error@std@@YAXH@Z; std::_Throw_C_error(int)
0x1800deb66  nop
0x1800deb67  mov     rcx, [r14+18h]
0x1800deb6b  add     rcx, 50h ; 'P'; _Cnd_t
0x1800deb6f  call    _Cnd_signal
0x1800deb74  test    eax, eax
0x1800deb76  jz      short loc_1800DEB80
0x1800deb78  mov     ecx, eax; int
0x1800deb7a  call    ?_Throw_C_error@std@@YAXH@Z; std::_Throw_C_error(int)
0x1800deb7f  nop
0x1800deb80  xor     ebx, ebx
0x1800deb82  mov     [rbp+8], rbx
0x1800deb86  mov     rcx, [rsi+38h]
0x1800deb8a  test    rcx, rcx
0x1800deb8d  jz      short loc_1800DEBA6
0x1800deb8f  mov     rax, [rcx]
0x1800deb92  cmp     rcx, rsi
0x1800deb95  setnz   dl
0x1800deb98  mov     rax, [rax+20h]
0x1800deb9c  call    cs:__guard_dispatch_icall_fptr
0x1800deba2  mov     [rsi+38h], rbx
0x1800deba6  mov     rax, rbp
0x1800deba9  mov     rbx, [rsp+58h+arg_8]
0x1800debae  add     rsp, 30h
0x1800debb2  pop     r15
0x1800debb4  pop     r14
0x1800debb6  pop     rdi
0x1800debb7  pop     rsi
0x1800debb8  pop     rbp
0x1800debb9  retn
```
