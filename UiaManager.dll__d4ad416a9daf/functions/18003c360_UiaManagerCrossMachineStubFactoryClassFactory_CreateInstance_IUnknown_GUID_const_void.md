# UiaManagerCrossMachineStubFactoryClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18003c360`
- end: `0x18003c4c4`
- name: `?CreateInstance@UiaManagerCrossMachineStubFactoryClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `356`
- prototype: `int(UiaManagerCrossMachineStubFactoryClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800067f8`
- `0x180006edc`
- `0x180018868`
- `0x180023ce8`
- `0x180031540`
- `0x18003c360`
- `0x18003c4cc`
- `0x180091010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18003c464`
- `msvcp_win!_Mtx_unlock` at `0x18003c464`

## string_xrefs

- `0x18003c49d`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18003c41b`: `onecore\windows\accessibletech\Common\WrlUtils.h`
- `0x18003c391`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestubfactoryclassfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UiaManagerCrossMachineStubFactoryClassFactory::CreateInstance(
        UiaManagerCrossMachineStubFactoryClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 *v10; // rax
  const char *v11; // r9
  __int64 v12; // rdi
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 (__fastcall ***v15)(_QWORD, const struct _GUID *, void **); // rcx
  int v16; // eax
  int v17; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v19; // [rsp+58h] [rbp+20h] BYREF

  if ( !a4 )
  {
    v7 = -2147024809;
    v8 = 17;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestubfactoryclassfactory.cpp",
      (const char *)v7,
      v17);
    return v7;
  }
  *a4 = 0;
  if ( a2 )
  {
    v7 = -2147221232;
    v8 = 20;
    goto LABEL_3;
  }
  if ( !*((_BYTE *)this + 64) )
  {
    std::_Mutex_base::lock((UiaManagerCrossMachineStubFactoryClassFactory *)((char *)this + 72));
    if ( !*((_BYTE *)this + 64) )
    {
      v10 = (__int64 *)Microsoft::WRL::Details::Make<UiaManagerCrossMachineStubFactory,>(&v19);
      v12 = *v10;
      *v10 = 0;
      v13 = v19;
      if ( v19 )
      {
        v19 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      if ( !v12 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)9,
          (unsigned int)"onecore\\windows\\accessibletech\\Common\\WrlUtils.h",
          v11);
      v19 = 0;
      v14 = *((_QWORD *)this + 7);
      *((_QWORD *)this + 7) = v12;
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v19);
      *((_BYTE *)this + 64) = 1;
    }
    _Mtx_unlock((UiaManagerCrossMachineStubFactoryClassFactory *)((char *)this + 72));
  }
  v15 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*((_QWORD *)this + 7);
  if ( !v15 )
  {
    v7 = -2147418113;
    v8 = 37;
    goto LABEL_3;
  }
  v16 = (**v15)(v15, a3, a4);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v16,
      v17);
  return 0;
}

```

## disassembly

```asm
0x18003c360  mov     [rsp+arg_0], rbx
0x18003c365  mov     [rsp+arg_8], rbp
0x18003c36a  push    rsi
0x18003c36b  push    rdi
0x18003c36c  push    r14; int
0x18003c36e  sub     rsp, 20h
0x18003c372  mov     rsi, r9
0x18003c375  mov     r14, r8
0x18003c378  mov     rbx, rcx
0x18003c37b  test    r9, r9
0x18003c37e  jnz     short loc_18003C3A4
0x18003c380  mov     ebx, 80070057h
0x18003c385  lea     edx, [r9+11h]; void *
0x18003c389  mov     rcx, [rsp+38h]; this
0x18003c38e  mov     r9d, ebx; char *
0x18003c391  lea     r8, aOnecoreWindows_9; "onecore\\windows\\accessibletech\\uiama"...
0x18003c398  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c39d  mov     eax, ebx
0x18003c39f  jmp     loc_18003C4B1
0x18003c3a4  mov     qword ptr [r9], 0
0x18003c3ab  test    rdx, rdx
0x18003c3ae  jz      short loc_18003C3BC
0x18003c3b0  mov     ebx, 80040110h
0x18003c3b5  mov     edx, 14h
0x18003c3ba  jmp     short loc_18003C389
0x18003c3bc  mov     al, [rcx+40h]
0x18003c3bf  nop
0x18003c3c0  test    al, al
0x18003c3c2  jnz     loc_18003C46A
0x18003c3c8  add     rcx, 48h ; 'H'; this
0x18003c3cc  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18003c3d1  mov     al, [rbx+40h]
0x18003c3d4  nop
0x18003c3d5  test    al, al
0x18003c3d7  jnz     loc_18003C460
0x18003c3dd  lea     rcx, [rsp+38h+arg_18]
0x18003c3e2  call    ??$Make@VUiaManagerCrossMachineStubFactory@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VUiaManagerCrossMachineStubFactory@@@12@XZ; Microsoft::WRL::Details::Make<UiaManagerCrossMachineStubFactory,>(void)
0x18003c3e7  mov     rdi, [rax]
0x18003c3ea  mov     qword ptr [rax], 0
0x18003c3f1  mov     rcx, [rsp+38h+arg_18]
0x18003c3f6  test    rcx, rcx
0x18003c3f9  jz      short loc_18003C411
0x18003c3fb  mov     [rsp+38h+arg_18], 0
0x18003c404  mov     rax, [rcx]
0x18003c407  mov     rax, [rax+10h]
0x18003c40b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c410  nop
0x18003c411  mov     rcx, [rsp+38h]; this
0x18003c416  test    rdi, rdi
0x18003c419  jnz     short loc_18003C42B
0x18003c41b  lea     r8, aOnecoreWindows_30; "onecore\\windows\\accessibletech\\Commo"...
0x18003c422  lea     edx, [rdi+9]; void *
0x18003c425  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18003c42b  mov     [rsp+38h+arg_18], 0
0x18003c434  mov     rcx, [rbx+38h]
0x18003c438  mov     [rbx+38h], rdi
0x18003c43c  test    rcx, rcx
0x18003c43f  jz      short loc_18003C44E
0x18003c441  mov     rax, [rcx]
0x18003c444  mov     rax, [rax+10h]
0x18003c448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c44d  nop
0x18003c44e  lea     rcx, [rsp+38h+arg_18]
0x18003c453  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x18003c458  mov     eax, 1
0x18003c45d  xchg    al, [rbx+40h]
0x18003c460  lea     rcx, [rbx+48h]; _Mtx_t
0x18003c464  call    cs:__imp__Mtx_unlock
0x18003c46a  mov     rcx, [rbx+38h]
0x18003c46e  test    rcx, rcx
0x18003c471  jnz     short loc_18003C480
0x18003c473  mov     ebx, 8000FFFFh
0x18003c478  lea     edx, [rcx+25h]
0x18003c47b  jmp     loc_18003C389
0x18003c480  mov     rax, [rcx]
0x18003c483  mov     r8, rsi
0x18003c486  mov     rdx, r14
0x18003c489  mov     rax, [rax]
0x18003c48c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c491  test    eax, eax
0x18003c493  jns     short loc_18003C4AF
0x18003c495  mov     rcx, [rsp+38h]; this
0x18003c49a  mov     r9d, eax; char *
0x18003c49d  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003c4a4  mov     edx, 1CBEh; void *
0x18003c4a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c4af  xor     eax, eax
0x18003c4b1  mov     rbx, [rsp+38h+arg_0]
0x18003c4b6  mov     rbp, [rsp+38h+arg_8]
0x18003c4bb  add     rsp, 20h
0x18003c4bf  pop     r14
0x18003c4c1  pop     rdi
0x18003c4c2  pop     rsi
0x18003c4c3  retn
```
