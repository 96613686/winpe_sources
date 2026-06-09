# OOBEOneDriveOptin::AsyncClientInvoke(ushort *,ushort * *)

- ea: `0x180019840`
- end: `0x18001999d`
- name: `?AsyncClientInvoke@OOBEOneDriveOptin@@UEAAJPEAGPEAPEAG@Z`
- size: `349`
- prototype: `__int64 __fastcall(OOBEOneDriveOptin *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800067b0`
- `0x18000e2bc`
- `0x18001136c`
- `0x180017ad4`
- `0x180019840`
- `0x180019f58`
- `0x18001bc90`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019888`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019888`

## string_xrefs

- `0x180019975`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18001998a`: `shell\oobe\user\dll\oobesyncengineapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OOBEOneDriveOptin::AsyncClientInvoke(
        OOBEOneDriveOptin *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  HRESULT Instance; // eax
  OneDriveAsyncCallbackHandler **v7; // rax
  OneDriveAsyncCallbackHandler *v8; // rsi
  _QWORD *v9; // r14
  __int64 v10; // r15
  int v11; // eax
  int v12; // eax
  const char *v13; // r9
  __int64 result; // rax
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-38h]
  _BYTE v17[8]; // [rsp+30h] [rbp-28h] BYREF
  OneDriveAsyncCallbackHandler *v18; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  _QWORD *v20; // [rsp+70h] [rbp+18h] BYREF
  __int64 v21; // [rsp+78h] [rbp+20h] BYREF

  *a3 = 0;
  v20 = 0;
  Instance = CoCreateInstance(
               &GUID_94269c4e_071a_4116_90e6_52e557067e4e,
               0,
               4u,
               &GUID_a91efacb_8b83_4b84_b797_1c8cf3ab3dcb,
               (LPVOID *)&v20);
  try
  {
    if ( Instance < 0 )
    {
      v15 = OOBEOneDriveOptin::SyncClientInvoke(this, a2, a3);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v20);
      result = v15;
    }
    else
    {
      v7 = (OneDriveAsyncCallbackHandler **)wil::MakeAndInitializeOrThrow<OneDriveAsyncCallbackHandler,>(v17);
      v8 = *v7;
      *v7 = 0;
      v18 = v8;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v17);
      v9 = v20;
      v10 = *v20;
      v21 = 0;
      v11 = (**(__int64 (__fastcall ***)(OneDriveAsyncCallbackHandler *, GUID *, __int64 *))v8)(
              v8,
              &GUID_c47b67d4_ba96_44bc_ab9e_1cac8eea9e93,
              &v21);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v11,
          v16);
      v12 = (*(__int64 (__fastcall **)(_QWORD *, unsigned __int16 *, __int64))(v10 + 24))(v9, a2, v21);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB0,
          (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
          (const char *)(unsigned int)v12,
          v16);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v21);
      *a3 = OneDriveAsyncCallbackHandler::GetAsyncClientInvokeResponse(v8);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v18);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v20);
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xBA,
                           (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x180019840  mov     r11, rsp
0x180019843  mov     [r11+8], rbx
0x180019847  mov     [r11+10h], rsi
0x18001984b  push    rdi
0x18001984c  push    r14
0x18001984e  push    r15
0x180019850  sub     rsp, 40h
0x180019854  mov     rbx, r8
0x180019857  mov     rdi, rdx
0x18001985a  mov     rsi, rcx
0x18001985d  mov     qword ptr [r8], 0
0x180019864  mov     qword ptr [r11+18h], 0
0x18001986c  lea     rax, [r11+18h]
0x180019870  mov     [r11-38h], rax
0x180019874  lea     r9, _GUID_a91efacb_8b83_4b84_b797_1c8cf3ab3dcb; riid
0x18001987b  xor     edx, edx; pUnkOuter
0x18001987d  lea     r8d, [rdx+4]; dwClsContext
0x180019881  lea     rcx, _GUID_94269c4e_071a_4116_90e6_52e557067e4e; rclsid
0x180019888  call    cs:__imp_CoCreateInstance
0x18001988e  test    eax, eax
0x180019890  js      loc_18001993C
0x180019896  lea     rcx, [rsp+58h+var_28]
0x18001989b  call    ??$MakeAndInitializeOrThrow@VOneDriveAsyncCallbackHandler@@$$V@wil@@YA?AV?$ComPtr@VOneDriveAsyncCallbackHandler@@@WRL@Microsoft@@XZ; wil::MakeAndInitializeOrThrow<OneDriveAsyncCallbackHandler,>(void)
0x1800198a0  mov     rsi, [rax]
0x1800198a3  mov     qword ptr [rax], 0
0x1800198aa  mov     [rsp+58h+var_20], rsi
0x1800198af  lea     rcx, [rsp+58h+var_28]
0x1800198b4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800198b9  mov     r14, [rsp+58h+arg_10]
0x1800198be  mov     r15, [r14]
0x1800198c1  mov     [rsp+58h+arg_18], 0
0x1800198ca  mov     rax, [rsi]
0x1800198cd  lea     r8, [rsp+58h+arg_18]
0x1800198d2  lea     rdx, _GUID_c47b67d4_ba96_44bc_ab9e_1cac8eea9e93
0x1800198d9  mov     rcx, rsi
0x1800198dc  mov     rax, [rax]
0x1800198df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198e4  mov     rcx, [rsp+58h]; this
0x1800198e9  test    eax, eax
0x1800198eb  js      loc_180019972
0x1800198f1  mov     r8, [rsp+58h+arg_18]
0x1800198f6  mov     rdx, rdi
0x1800198f9  mov     rcx, r14
0x1800198fc  mov     rax, [r15+18h]
0x180019900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019905  mov     rcx, [rsp+58h]; this
0x18001990a  test    eax, eax
0x18001990c  js      short loc_180019987
0x18001990e  lea     rcx, [rsp+58h+arg_18]
0x180019913  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180019918  mov     rcx, rsi; this
0x18001991b  call    ?GetAsyncClientInvokeResponse@OneDriveAsyncCallbackHandler@@QEAAPEAGXZ; OneDriveAsyncCallbackHandler::GetAsyncClientInvokeResponse(void)
0x180019920  mov     [rbx], rax
0x180019923  lea     rcx, [rsp+58h+var_20]
0x180019928  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001992d  nop
0x18001992e  lea     rcx, [rsp+58h+arg_10]
0x180019933  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180019938  xor     eax, eax
0x18001993a  jmp     short loc_18001995E
0x18001993c  mov     r8, rbx; unsigned __int16 **
0x18001993f  mov     rdx, rdi; unsigned __int16 *
0x180019942  mov     rcx, rsi; this
0x180019945  call    ?SyncClientInvoke@OOBEOneDriveOptin@@UEAAJPEAGPEAPEAG@Z; OOBEOneDriveOptin::SyncClientInvoke(ushort *,ushort * *)
0x18001994a  mov     ebx, eax
0x18001994c  lea     rcx, [rsp+58h+arg_10]
0x180019951  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180019956  mov     eax, ebx
0x180019958  jmp     short loc_18001995E
0x18001995a  mov     eax, dword ptr [rsp+58h+arg_10]
0x18001995e  mov     rbx, [rsp+58h+arg_0]
0x180019963  mov     rsi, [rsp+58h+arg_8]
0x180019968  add     rsp, 40h
0x18001996c  pop     r15
0x18001996e  pop     r14
0x180019970  pop     rdi
0x180019971  retn
0x180019972  mov     r9d, eax; char *
0x180019975  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001997c  mov     edx, 1CBEh; void *
0x180019981  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019987  mov     r9d, eax; char *
0x18001998a  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x180019991  mov     edx, 0B0h; void *
0x180019996  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
