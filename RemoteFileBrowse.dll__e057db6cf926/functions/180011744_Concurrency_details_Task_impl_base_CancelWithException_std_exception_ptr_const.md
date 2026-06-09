# Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)

- ea: `0x180011744`
- end: `0x180011874`
- name: `?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z`
- size: `304`
- prototype: `char __fastcall(Concurrency::details::_Task_impl_base *this, const struct std::exception_ptr *)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180018039`
- `0x1800184e7`
- `0x18001854d`
- `0x1800185ec`

## callees

- `0x18000208c`
- `0x18000f5c8`
- `0x18000fd1c`
- `0x180011744`
- `0x180019010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800117d0`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800117d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
  char *v13; // [rsp+48h] [rbp-30h] BYREF
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
  std::vector<void *>::~vector<void *>(&v13);
  return v7;
}

```

## disassembly

```asm
0x180011744  mov     [rsp+arg_8], rbx
0x180011749  mov     [rsp+arg_18], rbp
0x18001174e  push    rsi
0x18001174f  push    rdi
0x180011750  push    r14
0x180011752  sub     rsp, 60h
0x180011756  mov     rsi, rdx
0x180011759  mov     r14, rcx
0x18001175c  mov     rax, [rcx]
0x18001175f  mov     rbp, [rax+8]
0x180011763  lea     rdx, [rcx+140h]; struct Concurrency::details::_TaskCreationCallstack *
0x18001176a  lea     rcx, [rsp+78h+var_38]; this
0x18001176f  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x180011774  nop
0x180011775  mov     ecx, 48h ; 'H'; Size
0x18001177a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001177f  mov     rdi, rax
0x180011782  mov     [rsp+78h+arg_0], rax
0x18001178a  xorps   xmm0, xmm0
0x18001178d  movups  xmmword ptr [rax], xmm0
0x180011790  mov     dword ptr [rax+8], 1
0x180011797  mov     dword ptr [rax+0Ch], 1
0x18001179e  lea     rax, ??_7?$_Ref_count_obj2@U_ExceptionHolder@details@Concurrency@@@std@@6B@; const std::_Ref_count_obj2<Concurrency::details::_ExceptionHolder>::`vftable'
0x1800117a5  mov     [rdi], rax
0x1800117a8  lea     rbx, [rdi+10h]
0x1800117ac  mov     [rsp+78h+arg_10], rbx
0x1800117b4  mov     dword ptr [rbx], 0
0x1800117ba  lea     rcx, [rbx+8]
0x1800117be  mov     qword ptr [rcx], 0
0x1800117c5  mov     qword ptr [rcx+8], 0
0x1800117cd  mov     rdx, rsi
0x1800117d0  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800117d6  nop
0x1800117d7  lea     rcx, [rbx+18h]; this
0x1800117db  lea     rdx, [rsp+78h+var_38]; struct Concurrency::details::_TaskCreationCallstack *
0x1800117e0  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x1800117e5  nop
0x1800117e6  mov     [rsp+78h+var_48], rbx
0x1800117eb  mov     [rsp+78h+var_40], rdi
0x1800117f0  lea     rax, [rsp+78h+var_48]
0x1800117f5  mov     [rsp+78h+var_58], rax
0x1800117fa  xor     r9d, r9d
0x1800117fd  mov     r8b, 1
0x180011800  mov     dl, r8b
0x180011803  mov     rcx, r14
0x180011806  mov     rax, rbp
0x180011809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001180e  mov     dil, al
0x180011811  mov     rbx, [rsp+78h+var_40]
0x180011816  test    rbx, rbx
0x180011819  jz      short loc_180011852
0x18001181b  or      esi, 0FFFFFFFFh
0x18001181e  mov     ecx, esi
0x180011820  lock xadd [rbx+8], ecx
0x180011825  add     ecx, esi
0x180011827  jnz     short loc_180011852
0x180011829  mov     rdx, [rbx]
0x18001182c  mov     rcx, rbx
0x18001182f  mov     rax, [rdx]
0x180011832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011837  mov     eax, esi
0x180011839  lock xadd [rbx+0Ch], eax
0x18001183e  add     eax, esi
0x180011840  jnz     short loc_180011852
0x180011842  mov     rax, [rbx]
0x180011845  mov     rcx, rbx
0x180011848  mov     rax, [rax+8]
0x18001184c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011851  nop
0x180011852  lea     rcx, [rsp+78h+var_30]
0x180011857  call    ??1?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@XZ; std::vector<void *>::~vector<void *>(void)
0x18001185c  mov     al, dil
0x18001185f  lea     r11, [rsp+78h+var_18]
0x180011864  mov     rbx, [r11+28h]
0x180011868  mov     rbp, [r11+38h]
0x18001186c  mov     rsp, r11
0x18001186f  pop     r14
0x180011871  pop     rdi
0x180011872  pop     rsi
0x180011873  retn
```
