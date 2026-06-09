# UiaManagerCrossMachineStub::EnsureCuiBrokerInitialized(void)

- ea: `0x180020b94`
- end: `0x180020cbc`
- name: `?EnsureCuiBrokerInitialized@UiaManagerCrossMachineStub@@AEAAJXZ`
- size: `296`
- prototype: `__int64 __fastcall(UiaManagerCrossMachineStub *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020ad0`
- `0x180021ba0`
- `0x180065dc0`

## callees

- `0x1800054f8`
- `0x180018868`
- `0x180020b94`
- `0x180031540`
- `0x180091010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180020c99`
- `msvcp_win!_Mtx_unlock` at `0x180020c99`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020c11`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020c11`

## string_xrefs

- `0x180020c23`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x180020c6e`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UiaManagerCrossMachineStub::EnsureCuiBrokerInitialized(
        UiaManagerCrossMachineStub *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  struct _Mtx_internal_imp_t *v5; // r15
  HRESULT v6; // eax
  LPVOID v7; // rsi
  __int64 (__fastcall *v8)(LPVOID, GUID *, GUID *, char *); // rdi
  int v9; // eax
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPVOID v13; // [rsp+50h] [rbp+8h] BYREF
  char *v14; // [rsp+58h] [rbp+10h]

  try
  {
    if ( !*((_BYTE *)this + 136) )
    {
      v5 = (UiaManagerCrossMachineStub *)((char *)this + 144);
      v14 = (char *)this + 144;
      std::_Mutex_base::lock((UiaManagerCrossMachineStub *)((char *)this + 144));
      if ( !*((_BYTE *)this + 136) )
      {
        v13 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
        v6 = CoCreateInstance(
               &CLSID_ShellServiceHostBrokerProvider,
               0,
               0x404u,
               &GUID_0f4accb1_d8f9_4011_ba37_2557925a78cf,
               &v13);
        if ( v6 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x331,
            (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
            (const char *)(unsigned int)v6,
            ppv);
        v7 = v13;
        v8 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, char *))(*(_QWORD *)v13 + 24LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 112);
        v9 = v8(
               v7,
               &GUID_1f79f7de_20bf_4591_930a_d490b78fb09f,
               &GUID_1f79f7de_20bf_4591_930a_d490b78fb09f,
               (char *)this + 112);
        if ( v9 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x332,
            (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
            (const char *)(unsigned int)v9,
            ppv);
        *((_BYTE *)this + 136) = 1;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
      }
      _Mtx_unlock(v5);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x339,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x180020b94  mov     [rsp+arg_10], rbx
0x180020b99  mov     [rsp+arg_18], rsi
0x180020b9e  push    rdi
0x180020b9f  push    r14
0x180020ba1  push    r15
0x180020ba3  sub     rsp, 30h
0x180020ba7  mov     r14, rcx
0x180020baa  mov     al, [rcx+88h]
0x180020bb0  nop
0x180020bb1  test    al, al
0x180020bb3  jnz     loc_180020C9F
0x180020bb9  lea     r15, [rcx+90h]
0x180020bc0  mov     [rsp+48h+arg_8], r15
0x180020bc5  mov     rcx, r15; this
0x180020bc8  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180020bcd  nop
0x180020bce  mov     al, [r14+88h]
0x180020bd5  nop
0x180020bd6  test    al, al
0x180020bd8  jnz     loc_180020C96
0x180020bde  mov     [rsp+48h+arg_0], 0
0x180020be7  lea     rcx, [rsp+48h+arg_0]
0x180020bec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020bf1  lea     rax, [rsp+48h+arg_0]
0x180020bf6  mov     qword ptr [rsp+48h+ppv], rax; int
0x180020bfb  lea     r9, _GUID_0f4accb1_d8f9_4011_ba37_2557925a78cf; riid
0x180020c02  xor     edx, edx; pUnkOuter
0x180020c04  mov     r8d, 404h; dwClsContext
0x180020c0a  lea     rcx, CLSID_ShellServiceHostBrokerProvider; rclsid
0x180020c11  call    cs:__imp_CoCreateInstance
0x180020c17  mov     rcx, [rsp+48h]; this
0x180020c1c  test    eax, eax
0x180020c1e  jns     short loc_180020C34
0x180020c20  mov     r9d, eax; char *
0x180020c23  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180020c2a  mov     edx, 331h; void *
0x180020c2f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180020c34  mov     rsi, [rsp+48h+arg_0]
0x180020c39  mov     rax, [rsi]
0x180020c3c  mov     rdi, [rax+18h]
0x180020c40  lea     rcx, [r14+70h]
0x180020c44  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020c49  lea     r9, [r14+70h]
0x180020c4d  lea     rdx, _GUID_1f79f7de_20bf_4591_930a_d490b78fb09f
0x180020c54  mov     r8, rdx
0x180020c57  mov     rcx, rsi
0x180020c5a  mov     rax, rdi
0x180020c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c62  mov     rcx, [rsp+48h]; this
0x180020c67  test    eax, eax
0x180020c69  jns     short loc_180020C7F
0x180020c6b  mov     r9d, eax; char *
0x180020c6e  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180020c75  mov     edx, 332h; void *
0x180020c7a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180020c7f  mov     eax, 1
0x180020c84  xchg    al, [r14+88h]
0x180020c8b  lea     rcx, [rsp+48h+arg_0]
0x180020c90  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020c95  nop
0x180020c96  mov     rcx, r15; _Mtx_t
0x180020c99  call    cs:__imp__Mtx_unlock
0x180020c9f  xor     eax, eax
0x180020ca1  jmp     short loc_180020CA7
0x180020ca3  mov     eax, dword ptr [rsp+48h+arg_0]
0x180020ca7  mov     rbx, [rsp+48h+arg_10]
0x180020cac  mov     rsi, [rsp+48h+arg_18]
0x180020cb1  add     rsp, 30h
0x180020cb5  pop     r15
0x180020cb7  pop     r14
0x180020cb9  pop     rdi
0x180020cba  retn
```
