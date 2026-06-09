# UiaManagerCrossMachineProxy::PreprocessCrossMachineWinEvent(uint,HWND__ *,bool,int,int)

- ea: `0x18000ad6c`
- end: `0x18000ae72`
- name: `?PreprocessCrossMachineWinEvent@UiaManagerCrossMachineProxy@@AEAAXIPEAUHWND__@@_NHH@Z`
- size: `262`
- prototype: `void __fastcall(UiaManagerCrossMachineProxy *__hidden this, unsigned int, HWND, bool, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180057efc`

## callees

- `0x1800067f8`
- `0x18000ad6c`
- `0x18000af78`
- `0x180018ecc`
- `0x180031540`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000adf1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000adf1`

## string_xrefs

- `0x18000ae03`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachineproxy.cpp`
- `0x18000ae46`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachineproxy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall UiaManagerCrossMachineProxy::PreprocessCrossMachineWinEvent(
        UiaManagerCrossMachineProxy *this,
        int a2,
        HWND a3,
        char a4,
        int a5,
        int a6)
{
  HRESULT Instance; // eax
  int v10; // eax
  int ppv; // [rsp+20h] [rbp-48h]
  LPVOID v12[2]; // [rsp+30h] [rbp-38h] BYREF
  HWND v13; // [rsp+40h] [rbp-28h] BYREF
  __int128 v14; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( a2 == 32769 && !a5 && !a6 )
  {
    v12[0] = a3;
    ThreadSafeMap<HWND__ *,HwndInfoCache::CachedHwndInfo>::RemoveValue((UiaManagerCrossMachineProxy *)((char *)this + 576));
    if ( a4 )
    {
      v12[0] = 0;
      Instance = CoCreateInstance(&CLSID_UiaManager, 0, 4u, &GUID_22bcd67a_1154_466f_972a_899e63847049, v12);
      if ( Instance < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x533,
          (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachineproxy.cpp",
          (const char *)(unsigned int)Instance,
          ppv);
      v13 = a3;
      v14 = *(_OWORD *)((char *)this + 72);
      v10 = (*(__int64 (__fastcall **)(LPVOID, HWND *))(*(_QWORD *)v12[0] + 40LL))(v12[0], &v13);
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x536,
          (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachineproxy.cpp",
          (const char *)(unsigned int)v10,
          ppv);
      wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(v12);
    }
  }
}

```

## disassembly

```asm
0x18000ad6c  cmp     edx, 8001h
0x18000ad72  jnz     locret_18000AE71
0x18000ad78  mov     rax, rsp
0x18000ad7b  mov     [rax+8], rbx
0x18000ad7f  mov     [rax+10h], rsi
0x18000ad83  push    rdi
0x18000ad84  sub     rsp, 60h
0x18000ad88  mov     sil, r9b
0x18000ad8b  mov     rbx, r8
0x18000ad8e  mov     rdi, rcx
0x18000ad91  cmp     [rsp+68h+arg_20], 0
0x18000ad99  jnz     loc_18000AE62
0x18000ad9f  cmp     [rsp+68h+arg_28], 0
0x18000ada7  jnz     loc_18000AE62
0x18000adad  mov     [rax-38h], rbx
0x18000adb1  add     rcx, 240h; _Mtx_t
0x18000adb8  lea     rdx, [rax-38h]
0x18000adbc  call    ?RemoveValue@?$ThreadSafeMap@PEAUHWND__@@UCachedHwndInfo@HwndInfoCache@@@@QEAAXAEBQEAUHWND__@@@Z; ThreadSafeMap<HWND__ *,HwndInfoCache::CachedHwndInfo>::RemoveValue(HWND__ * const &)
0x18000adc1  test    sil, sil
0x18000adc4  jz      loc_18000AE62
0x18000adca  mov     [rsp+68h+var_38], 0
0x18000add3  lea     rax, [rsp+68h+var_38]
0x18000add8  mov     qword ptr [rsp+68h+ppv], rax; int
0x18000addd  lea     r9, _GUID_22bcd67a_1154_466f_972a_899e63847049; riid
0x18000ade4  xor     edx, edx; pUnkOuter
0x18000ade6  lea     r8d, [rdx+4]; dwClsContext
0x18000adea  lea     rcx, CLSID_UiaManager; rclsid
0x18000adf1  call    cs:__imp_CoCreateInstance
0x18000adf7  mov     rcx, [rsp+68h]; this
0x18000adfc  test    eax, eax
0x18000adfe  jns     short loc_18000AE15
0x18000ae00  mov     r9d, eax; char *
0x18000ae03  lea     r8, aOnecoreWindows_16; "onecore\\windows\\accessibletech\\uiama"...
0x18000ae0a  mov     edx, 533h; void *
0x18000ae0f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000ae15  mov     rcx, [rsp+68h+var_38]
0x18000ae1a  mov     [rsp+68h+var_28], rbx
0x18000ae1f  movups  xmm0, xmmword ptr [rdi+48h]
0x18000ae23  movdqu  [rsp+68h+var_20], xmm0
0x18000ae29  mov     rax, [rcx]
0x18000ae2c  lea     rdx, [rsp+68h+var_28]
0x18000ae31  mov     rax, [rax+28h]
0x18000ae35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae3a  mov     rcx, [rsp+68h]; this
0x18000ae3f  test    eax, eax
0x18000ae41  jns     short loc_18000AE58
0x18000ae43  mov     r9d, eax; char *
0x18000ae46  lea     r8, aOnecoreWindows_16; "onecore\\windows\\accessibletech\\uiama"...
0x18000ae4d  mov     edx, 536h; void *
0x18000ae52  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ae57  nop
0x18000ae58  lea     rcx, [rsp+68h+var_38]
0x18000ae5d  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x18000ae62  mov     rbx, [rsp+68h+arg_0]
0x18000ae67  mov     rsi, [rsp+68h+arg_8]
0x18000ae6c  add     rsp, 60h
0x18000ae70  pop     rdi
0x18000ae71  retn
```
