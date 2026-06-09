# UiaManagerCrossMachineProxyFactoryClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180070f90`
- end: `0x1800710d3`
- name: `?CreateInstance@UiaManagerCrossMachineProxyFactoryClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `323`
- prototype: `__int64 __fastcall(UiaManagerCrossMachineProxyFactoryClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800067f8`
- `0x180006edc`
- `0x180018868`
- `0x18002fdd8`
- `0x180031540`
- `0x180070f90`
- `0x180091010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180071061`
- `msvcp_win!_Mtx_unlock` at `0x180071061`

## string_xrefs

- `0x1800710af`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180070fb5`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachineproxyfactoryclassfactory.cpp`
- `0x180070fe4`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachineproxyfactoryclassfactory.cpp`
- `0x18007107d`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachineproxyfactoryclassfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UiaManagerCrossMachineProxyFactoryClassFactory::CreateInstance(
        UiaManagerCrossMachineProxyFactoryClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 result; // rax
  struct _Mtx_internal_imp_t *v8; // rdi
  __int64 *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 (__fastcall ***v12)(_QWORD, const struct _GUID *, void **); // rcx
  const char *v13; // r9
  int v14; // eax
  int v15; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v17; // [rsp+78h] [rbp+20h] BYREF

  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachineproxyfactoryclassfactory.cpp",
        (const char *)0x80040110LL,
        v15);
      return 2147746064LL;
    }
    else
    {
      try
      {
        if ( !*((_BYTE *)this + 64) )
        {
          v8 = (UiaManagerCrossMachineProxyFactoryClassFactory *)((char *)this + 72);
          v15 = (_DWORD)this + 72;
          std::_Mutex_base::lock((UiaManagerCrossMachineProxyFactoryClassFactory *)((char *)this + 72));
          if ( !*((_BYTE *)this + 64) )
          {
            v9 = (__int64 *)MakeCom<UiaManagerCrossMachineProxyFactory,>(&v17);
            v10 = *v9;
            *v9 = 0;
            v11 = *((_QWORD *)this + 7);
            *((_QWORD *)this + 7) = v10;
            if ( v11 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
            wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v17);
            *((_BYTE *)this + 64) = 1;
          }
          _Mtx_unlock(v8);
        }
        v12 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*((_QWORD *)this + 7);
        if ( v12 )
        {
          v14 = (**v12)(v12, a3, a4);
          if ( v14 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1CBE,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
              (const char *)(unsigned int)v14,
              v15);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x23,
            (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachineproxyfactoryclassfactory.cpp",
            (const char *)0x8000FFFFLL,
            v15);
          result = 2147549183LL;
        }
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x28,
                               (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinepr"
                                             "oxyfactoryclassfactory.cpp",
                               v13);
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachineproxyfactoryclassfactory.cpp",
      (const char *)0x80070057LL,
      v15);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180070f90  push    rbx
0x180070f92  push    rsi
0x180070f93  push    rdi
0x180070f94  push    r14
0x180070f96  sub     rsp, 38h
0x180070f9a  mov     rsi, r9
0x180070f9d  mov     r14, r8
0x180070fa0  mov     rbx, rcx
0x180070fa3  test    r9, r9
0x180070fa6  jnz     short loc_180070FCB
0x180070fa8  mov     rcx, [rsp+58h]; this
0x180070fad  mov     ebx, 80070057h
0x180070fb2  mov     r9d, ebx; char *
0x180070fb5  lea     r8, aOnecoreWindows_2; "onecore\\windows\\accessibletech\\uiama"...
0x180070fbc  lea     edx, [rsi+0Fh]; void *
0x180070fbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070fc4  mov     eax, ebx
0x180070fc6  jmp     loc_1800710C8
0x180070fcb  mov     qword ptr [r9], 0
0x180070fd2  test    rdx, rdx
0x180070fd5  jz      short loc_180070FFC
0x180070fd7  mov     rcx, [rsp+58h]; this
0x180070fdc  mov     ebx, 80040110h
0x180070fe1  mov     r9d, ebx; char *
0x180070fe4  lea     r8, aOnecoreWindows_2; "onecore\\windows\\accessibletech\\uiama"...
0x180070feb  mov     edx, 12h; void *
0x180070ff0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070ff5  mov     eax, ebx
0x180070ff7  jmp     loc_1800710C8
0x180070ffc  mov     al, [rcx+40h]
0x180070fff  nop
0x180071000  test    al, al
0x180071002  jnz     short loc_180071067
0x180071004  lea     rdi, [rcx+48h]
0x180071008  mov     qword ptr [rsp+58h+var_38], rdi; int
0x18007100d  mov     rcx, rdi; this
0x180071010  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180071015  nop
0x180071016  mov     al, [rbx+40h]
0x180071019  nop
0x18007101a  test    al, al
0x18007101c  jnz     short loc_18007105E
0x18007101e  lea     rcx, [rsp+58h+arg_18]
0x180071023  call    ??$MakeCom@VUiaManagerCrossMachineProxyFactory@@$$V@@YA?AV?$com_ptr_t@VUiaManagerCrossMachineProxyFactory@@Uerr_exception_policy@wil@@@wil@@XZ; MakeCom<UiaManagerCrossMachineProxyFactory,>(void)
0x180071028  mov     rdx, [rax]
0x18007102b  mov     qword ptr [rax], 0
0x180071032  mov     rcx, [rbx+38h]
0x180071036  mov     [rbx+38h], rdx
0x18007103a  test    rcx, rcx
0x18007103d  jz      short loc_18007104C
0x18007103f  mov     rax, [rcx]
0x180071042  mov     rax, [rax+10h]
0x180071046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007104b  nop
0x18007104c  lea     rcx, [rsp+58h+arg_18]
0x180071051  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x180071056  mov     eax, 1
0x18007105b  xchg    al, [rbx+40h]
0x18007105e  mov     rcx, rdi; _Mtx_t
0x180071061  call    cs:__imp__Mtx_unlock
0x180071067  mov     rcx, [rbx+38h]
0x18007106b  test    rcx, rcx
0x18007106e  jnz     short loc_180071092
0x180071070  mov     rcx, [rsp+58h]; this
0x180071075  mov     ebx, 8000FFFFh
0x18007107a  mov     r9d, ebx; char *
0x18007107d  lea     r8, aOnecoreWindows_2; "onecore\\windows\\accessibletech\\uiama"...
0x180071084  mov     edx, 23h ; '#'; void *
0x180071089  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007108e  mov     eax, ebx
0x180071090  jmp     short loc_1800710C8
0x180071092  mov     rax, [rcx]
0x180071095  mov     r8, rsi
0x180071098  mov     rdx, r14
0x18007109b  mov     rax, [rax]
0x18007109e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800710a3  mov     rcx, [rsp+58h]; this
0x1800710a8  test    eax, eax
0x1800710aa  jns     short loc_1800710C0
0x1800710ac  mov     r9d, eax; char *
0x1800710af  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800710b6  mov     edx, 1CBEh; void *
0x1800710bb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800710c0  xor     eax, eax
0x1800710c2  jmp     short loc_1800710C8
0x1800710c4  mov     eax, [rsp+58h+arg_18]
0x1800710c8  add     rsp, 38h
0x1800710cc  pop     r14
0x1800710ce  pop     rdi
0x1800710cf  pop     rsi
0x1800710d0  pop     rbx
0x1800710d1  retn
```
