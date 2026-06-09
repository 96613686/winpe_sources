# InvokeStoreAppUpdate(void)

- ea: `0x180036e08`
- end: `0x180036fce`
- name: `?InvokeStoreAppUpdate@@YAJXZ`
- size: `454`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180042460`

## callees

- `0x180003a00`
- `0x180009084`
- `0x180034d9c`
- `0x180036e08`
- `0x18003771c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180036e54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180036e54`

## string_xrefs

- `0x180036e4d`: `Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager`
- `0x180036e7c`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180036f19`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 InvokeStoreAppUpdate(void)
{
  HRESULT v0; // eax
  int v1; // edx
  unsigned int v2; // r8d
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, __int64 *); // rdi
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  __int64 v18; // [rsp+40h] [rbp-20h] BYREF
  __int64 v19; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v19 = 0;
  v18 = 0;
  string = 0;
  v0 = WindowsCreateStringReference(
         L"Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager",
         0x47u,
         &hstringHeader,
         &string);
  if ( v0 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v0, v1, v2);
    JUMPOUT(0x180036FCDLL);
  }
  v3 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>(
         (__int64)string,
         &v19);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35F,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
      (const char *)(unsigned int)v3,
      (int)hstringHeader.Reserved.Reserved1);
    v5 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    v6 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return v4;
  }
  v8 = v19;
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 176LL);
  v10 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = v9(v8, &v18);
  v4 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x361,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
      (const char *)(unsigned int)v11,
      (int)hstringHeader.Reserved.Reserved1);
    v12 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v13 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v4;
  }
  v14 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return 0;
}

```

## disassembly

```asm
0x180036e08  mov     [rsp-8+arg_0], rbx
0x180036e0d  mov     [rsp-8+arg_8], rdi
0x180036e12  push    rbp
0x180036e13  mov     rbp, rsp
0x180036e16  sub     rsp, 60h
0x180036e1a  mov     rax, cs:__security_cookie
0x180036e21  xor     rax, rsp
0x180036e24  mov     [rbp+var_10], rax
0x180036e28  mov     [rbp+var_18], 0
0x180036e30  mov     [rbp+var_20], 0
0x180036e38  mov     [rbp+string], 0
0x180036e40  lea     r9, [rbp+string]; string
0x180036e44  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180036e48  mov     edx, 47h ; 'G'; length
0x180036e4d  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Store_Preview_InstallControl_AppInstallManager@@3QBGB; "Windows.ApplicationModel.Store.Preview."...
0x180036e54  call    cs:__imp_WindowsCreateStringReference
0x180036e5a  test    eax, eax
0x180036e5c  js      loc_180036FC6
0x180036e62  lea     rdx, [rbp+var_18]
0x180036e66  mov     rcx, [rbp+string]
0x180036e6a  call    ??$ActivateInstance@V?$ComPtr@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>)
0x180036e6f  mov     ebx, eax
0x180036e71  test    eax, eax
0x180036e73  jns     short loc_180036ED1
0x180036e75  mov     rcx, [rbp+8]; this
0x180036e79  mov     r9d, eax; char *
0x180036e7c  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180036e83  mov     edx, 35Fh; void *
0x180036e88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036e8d  nop
0x180036e8e  mov     rcx, [rbp+var_20]
0x180036e92  test    rcx, rcx
0x180036e95  jz      short loc_180036EAC
0x180036e97  mov     [rbp+var_20], 0
0x180036e9f  mov     rax, [rcx]
0x180036ea2  mov     rax, [rax+10h]
0x180036ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036eab  nop
0x180036eac  mov     rcx, [rbp+var_18]
0x180036eb0  test    rcx, rcx
0x180036eb3  jz      short loc_180036ECA
0x180036eb5  mov     [rbp+var_18], 0
0x180036ebd  mov     rax, [rcx]
0x180036ec0  mov     rax, [rax+10h]
0x180036ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ec9  nop
0x180036eca  mov     eax, ebx
0x180036ecc  jmp     loc_180036FAA
0x180036ed1  mov     rbx, [rbp+var_18]
0x180036ed5  mov     rax, [rbx]
0x180036ed8  mov     rdi, [rax+0B0h]
0x180036edf  mov     rcx, [rbp+var_20]
0x180036ee3  test    rcx, rcx
0x180036ee6  jz      short loc_180036EFD
0x180036ee8  mov     [rbp+var_20], 0
0x180036ef0  mov     rdx, [rcx]
0x180036ef3  mov     rax, [rdx+10h]
0x180036ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036efc  nop
0x180036efd  lea     rdx, [rbp+var_20]
0x180036f01  mov     rcx, rbx
0x180036f04  mov     rax, rdi
0x180036f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f0c  mov     ebx, eax
0x180036f0e  test    eax, eax
0x180036f10  jns     short loc_180036F6C
0x180036f12  mov     rcx, [rbp+8]; this
0x180036f16  mov     r9d, eax; char *
0x180036f19  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180036f20  mov     edx, 361h; void *
0x180036f25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036f2a  nop
0x180036f2b  mov     rcx, [rbp+var_20]
0x180036f2f  test    rcx, rcx
0x180036f32  jz      short loc_180036F49
0x180036f34  mov     [rbp+var_20], 0
0x180036f3c  mov     rax, [rcx]
0x180036f3f  mov     rax, [rax+10h]
0x180036f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f48  nop
0x180036f49  mov     rcx, [rbp+var_18]
0x180036f4d  test    rcx, rcx
0x180036f50  jz      short loc_180036F67
0x180036f52  mov     [rbp+var_18], 0
0x180036f5a  mov     rax, [rcx]
0x180036f5d  mov     rax, [rax+10h]
0x180036f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f66  nop
0x180036f67  jmp     loc_180036ECA
0x180036f6c  mov     rcx, [rbp+var_20]
0x180036f70  test    rcx, rcx
0x180036f73  jz      short loc_180036F8A
0x180036f75  mov     [rbp+var_20], 0
0x180036f7d  mov     rax, [rcx]
0x180036f80  mov     rax, [rax+10h]
0x180036f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f89  nop
0x180036f8a  mov     rcx, [rbp+var_18]
0x180036f8e  test    rcx, rcx
0x180036f91  jz      short loc_180036FA8
0x180036f93  mov     [rbp+var_18], 0
0x180036f9b  mov     rax, [rcx]
0x180036f9e  mov     rax, [rax+10h]
0x180036fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fa7  nop
0x180036fa8  xor     eax, eax
0x180036faa  mov     rcx, [rbp+var_10]
0x180036fae  xor     rcx, rsp; StackCookie
0x180036fb1  call    __security_check_cookie
0x180036fb6  mov     rbx, [rsp+60h+arg_0]
0x180036fbb  mov     rdi, [rsp+60h+arg_8]
0x180036fc0  add     rsp, 60h
0x180036fc4  pop     rbp
0x180036fc5  retn
0x180036fc6  mov     ecx, eax; this
0x180036fc8  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
