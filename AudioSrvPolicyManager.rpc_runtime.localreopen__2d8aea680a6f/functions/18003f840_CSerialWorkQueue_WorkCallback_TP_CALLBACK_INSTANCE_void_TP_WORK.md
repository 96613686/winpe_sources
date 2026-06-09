# CSerialWorkQueue::WorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18003f840`
- end: `0x18003f8c5`
- name: `?WorkCallback@CSerialWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `133`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1800203b0`
- `0x18003ed14`
- `0x18003f840`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18003f8a5`
- `msvcp_win!_Mtx_unlock` at `0x18003f8a5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003f86e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003f88a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003f86e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003f88a`
- `msvcp_win!_Mtx_lock` at `0x18003f85f`
- `msvcp_win!_Mtx_lock` at `0x18003f85f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18003f8be`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSerialWorkQueue::WorkCallback(PTP_CALLBACK_INSTANCE Instance, _WorkTask *Context, PTP_WORK Work)
{
  __int64 v5; // rsi
  unsigned int v6; // edx

  v5 = *((_QWORD *)Context + 2);
  if ( _Mtx_lock((_Mtx_t)(v5 + 88)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v5 + 164) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v5 + 164) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( !*(_BYTE *)(v5 + 80) )
    std::_Func_class<void,>::operator()(*(_QWORD *)Context);
  _Mtx_unlock((_Mtx_t)(v5 + 88));
  _WorkTask::`scalar deleting destructor'(Context, v6);
  CloseThreadpoolWork(Work);
}

```

## disassembly

```asm
0x18003f840  push    rbx
0x18003f842  push    rbp
0x18003f843  push    rsi
0x18003f844  push    rdi
0x18003f845  sub     rsp, 28h
0x18003f849  mov     rbp, r8
0x18003f84c  mov     rdi, rdx
0x18003f84f  mov     rsi, [rdx+10h]
0x18003f853  lea     rbx, [rsi+58h]
0x18003f857  mov     [rsp+48h+arg_8], rbx
0x18003f85c  mov     rcx, rbx; _Mtx_t
0x18003f85f  call    cs:__imp__Mtx_lock
0x18003f865  test    eax, eax
0x18003f867  jz      short loc_18003F875
0x18003f869  mov     ecx, 5
0x18003f86e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003f874  int     3; Trap to Debugger
0x18003f875  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18003f87c  jnz     short loc_18003F891
0x18003f87e  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18003f885  mov     ecx, 6
0x18003f88a  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003f890  nop
0x18003f891  mov     al, [rsi+50h]
0x18003f894  nop
0x18003f895  test    al, al
0x18003f897  jnz     short loc_18003F8A2
0x18003f899  mov     rcx, [rdi]
0x18003f89c  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x18003f8a1  nop
0x18003f8a2  mov     rcx, rbx; _Mtx_t
0x18003f8a5  call    cs:__imp__Mtx_unlock
0x18003f8ab  mov     rcx, rdi; this
0x18003f8ae  call    ??_G_WorkTask@@QEAAPEAXI@Z; _WorkTask::`scalar deleting destructor'(uint)
0x18003f8b3  mov     rcx, rbp
0x18003f8b6  add     rsp, 28h
0x18003f8ba  pop     rdi
0x18003f8bb  pop     rsi
0x18003f8bc  pop     rbp
0x18003f8bd  pop     rbx
0x18003f8be  jmp     cs:__imp_CloseThreadpoolWork
```
