# UiaManagerEndpointStateNotifierClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180006990`
- end: `0x180006b50`
- name: `?CreateInstance@UiaManagerEndpointStateNotifierClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `448`
- prototype: `__int64 __fastcall(UiaManagerEndpointStateNotifierClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180006990`
- `0x180006edc`
- `0x180007134`
- `0x1800188ac`
- `0x180091010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180006b01`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180006b0c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180006b01`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180006b0c`
- `msvcp_win!_Mtx_lock` at `0x180006a19`
- `msvcp_win!_Mtx_lock` at `0x180006a19`
- `msvcp_win!_Mtx_unlock` at `0x180006a42`
- `msvcp_win!_Mtx_unlock` at `0x180006a42`

## string_xrefs

- `0x1800069f0`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerendpointstatenotifierclassfactory.cpp`
- `0x180006abf`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerendpointstatenotifierclassfactory.cpp`
- `0x180006ae4`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerendpointstatenotifierclassfactory.cpp`
- `0x180006b2f`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerendpointstatenotifierclassfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UiaManagerEndpointStateNotifierClassFactory::CreateInstance(
        UiaManagerEndpointStateNotifierClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 (__fastcall ***v7)(_QWORD, const struct _GUID *, void **); // rcx
  int v8; // eax
  const char *v9; // r9
  unsigned int v10; // ebx
  __int64 result; // rax
  struct _Mtx_internal_imp_t *v12; // rdi
  char *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // [rsp+20h] [rbp-38h]
  char v18; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v20; // [rsp+78h] [rbp+20h] BYREF

  try
  {
    if ( !a4 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerendpointstatenotifierclassfactory.cpp",
        (const char *)0x80070057LL,
        v17);
      return 2147942487LL;
    }
    *a4 = 0;
    if ( a2 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerendpointstatenotifierclassfactory.cpp",
        (const char *)0x80040110LL,
        v17);
      return 2147746064LL;
    }
    if ( *((_BYTE *)this + 64) )
      goto LABEL_5;
    v12 = (UiaManagerEndpointStateNotifierClassFactory *)((char *)this + 72);
    v17 = (_DWORD)this + 72;
    if ( _Mtx_lock((UiaManagerEndpointStateNotifierClassFactory *)((char *)this + 72)) )
    {
      std::_Throw_Cpp_error(5);
    }
    else if ( std::_Mutex_base::_Verify_ownership_levels(v12) )
    {
      if ( *((_BYTE *)this + 64) )
      {
LABEL_11:
        _Mtx_unlock(v12);
LABEL_5:
        v7 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*((_QWORD *)this + 7);
        if ( v7 )
        {
          v8 = (**v7)(v7, a3, a4);
          v10 = v8;
          if ( v8 >= 0 )
          {
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x22,
              (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerendpointstatenotifierclassfactory.cpp",
              (const char *)(unsigned int)v8,
              v17);
            return v10;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x21,
            (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerendpointstatenotifierclassfactory.cpp",
            (const char *)0x8000FFFFLL,
            v17);
          return 2147549183LL;
        }
      }
      v13 = (char *)UiaManagerEndpointStateNotifier::New(&v20);
      v14 = 0;
      if ( &v18 == v13 )
      {
LABEL_14:
        v15 = *((_QWORD *)this + 7);
        *((_QWORD *)this + 7) = v14;
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        v16 = v20;
        if ( v20 )
        {
          v20 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
        *((_BYTE *)this + 64) = 1;
        goto LABEL_11;
      }
LABEL_23:
      v14 = *(_QWORD *)v13;
      *(_QWORD *)v13 = 0;
      goto LABEL_14;
    }
    std::_Throw_Cpp_error(6);
    goto LABEL_23;
  }
  catch ( ... )
  {
    LODWORD(v20) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x26,
                     (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerendpointstatenotifierclassfactory.cpp",
                     v9);
    return (unsigned int)v20;
  }
  return result;
}

```

## disassembly

```asm
0x180006990  push    rbx
0x180006992  push    rsi
0x180006993  push    rdi
0x180006994  push    r14
0x180006996  sub     rsp, 38h
0x18000699a  mov     rsi, r9
0x18000699d  mov     r14, r8
0x1800069a0  mov     rbx, rcx
0x1800069a3  test    r9, r9
0x1800069a6  jz      loc_180006AD7
0x1800069ac  mov     qword ptr [r9], 0
0x1800069b3  test    rdx, rdx
0x1800069b6  jnz     loc_180006AB2
0x1800069bc  mov     al, [rcx+40h]
0x1800069bf  nop
0x1800069c0  test    al, al
0x1800069c2  jz      short loc_180006A0D
0x1800069c4  mov     rcx, [rbx+38h]
0x1800069c8  test    rcx, rcx
0x1800069cb  jz      loc_180006B22
0x1800069d1  mov     rax, [rcx]
0x1800069d4  mov     r8, rsi
0x1800069d7  mov     rdx, r14
0x1800069da  mov     rax, [rax]
0x1800069dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069e2  mov     ebx, eax
0x1800069e4  test    eax, eax
0x1800069e6  jns     short loc_180006A4D
0x1800069e8  mov     rcx, [rsp+58h]; this
0x1800069ed  mov     r9d, eax; char *
0x1800069f0  lea     r8, aOnecoreWindows_12; "onecore\\windows\\accessibletech\\uiama"...
0x1800069f7  mov     edx, 22h ; '"'; void *
0x1800069fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006a01  mov     eax, ebx
0x180006a03  add     rsp, 38h
0x180006a07  pop     r14
0x180006a09  pop     rdi
0x180006a0a  pop     rsi
0x180006a0b  pop     rbx
0x180006a0c  retn
0x180006a0d  lea     rdi, [rcx+48h]
0x180006a11  mov     [rsp+58h+var_38], rdi
0x180006a16  mov     rcx, rdi; _Mtx_t
0x180006a19  call    cs:__imp__Mtx_lock
0x180006a1f  test    eax, eax
0x180006a21  jnz     loc_180006AFC
0x180006a27  mov     rcx, rdi; this
0x180006a2a  call    ?_Verify_ownership_levels@_Mutex_base@std@@IEAA_NXZ; std::_Mutex_base::_Verify_ownership_levels(void)
0x180006a2f  test    al, al
0x180006a31  jz      loc_180006B07
0x180006a37  mov     al, [rbx+40h]
0x180006a3a  nop
0x180006a3b  test    al, al
0x180006a3d  jz      short loc_180006A51
0x180006a3f  mov     rcx, rdi; _Mtx_t
0x180006a42  call    cs:__imp__Mtx_unlock
0x180006a48  jmp     loc_1800069C4
0x180006a4d  xor     eax, eax
0x180006a4f  jmp     short loc_180006A03
0x180006a51  lea     rcx, [rsp+58h+arg_18]
0x180006a56  call    ?New@UiaManagerEndpointStateNotifier@@SA?AV?$ComPtr@VUiaManagerEndpointStateNotifier@@@WRL@Microsoft@@XZ; UiaManagerEndpointStateNotifier::New(void)
0x180006a5b  xor     ecx, ecx
0x180006a5d  lea     rdx, [rsp+58h+var_30]
0x180006a62  cmp     rdx, rax
0x180006a65  jnz     loc_180006B13
0x180006a6b  mov     rdx, [rbx+38h]
0x180006a6f  mov     [rbx+38h], rcx
0x180006a73  test    rdx, rdx
0x180006a76  jz      short loc_180006A88
0x180006a78  mov     rax, [rdx]
0x180006a7b  mov     rcx, rdx
0x180006a7e  mov     rax, [rax+10h]
0x180006a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a87  nop
0x180006a88  mov     rcx, [rsp+58h+arg_18]
0x180006a8d  test    rcx, rcx
0x180006a90  jz      short loc_180006AA8
0x180006a92  mov     [rsp+58h+arg_18], 0
0x180006a9b  mov     rax, [rcx]
0x180006a9e  mov     rax, [rax+10h]
0x180006aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aa7  nop
0x180006aa8  mov     eax, 1
0x180006aad  xchg    al, [rbx+40h]
0x180006ab0  jmp     short loc_180006A3F
0x180006ab2  mov     rcx, [rsp+58h]; this
0x180006ab7  mov     ebx, 80040110h
0x180006abc  mov     r9d, ebx; char *
0x180006abf  lea     r8, aOnecoreWindows_12; "onecore\\windows\\accessibletech\\uiama"...
0x180006ac6  mov     edx, 11h; void *
0x180006acb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ad0  mov     eax, ebx
0x180006ad2  jmp     loc_180006A03
0x180006ad7  mov     rcx, [rsp+58h]; this
0x180006adc  mov     ebx, 80070057h
0x180006ae1  mov     r9d, ebx; char *
0x180006ae4  lea     r8, aOnecoreWindows_12; "onecore\\windows\\accessibletech\\uiama"...
0x180006aeb  mov     edx, 0Eh; void *
0x180006af0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006af5  mov     eax, ebx
0x180006af7  jmp     loc_180006A03
0x180006afc  mov     ecx, 5
0x180006b01  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180006b07  mov     ecx, 6
0x180006b0c  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180006b12  nop
0x180006b13  mov     rcx, [rax]
0x180006b16  mov     qword ptr [rax], 0
0x180006b1d  jmp     loc_180006A6B
0x180006b22  mov     rcx, [rsp+58h]; this
0x180006b27  mov     ebx, 8000FFFFh
0x180006b2c  mov     r9d, ebx; char *
0x180006b2f  lea     r8, aOnecoreWindows_12; "onecore\\windows\\accessibletech\\uiama"...
0x180006b36  mov     edx, 21h ; '!'; void *
0x180006b3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006b40  mov     eax, ebx
0x180006b42  jmp     loc_180006A03
0x180006b47  mov     eax, dword ptr [rsp+58h+arg_18]
0x180006b4b  jmp     loc_180006A03
```
