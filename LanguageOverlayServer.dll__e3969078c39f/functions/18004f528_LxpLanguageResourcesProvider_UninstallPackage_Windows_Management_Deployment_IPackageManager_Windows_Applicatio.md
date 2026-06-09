# LxpLanguageResourcesProvider::_UninstallPackage(Windows::Management::Deployment::IPackageManager *,Windows::ApplicationModel::IPackage *)

- ea: `0x18004f528`
- end: `0x18004f70a`
- name: `?_UninstallPackage@LxpLanguageResourcesProvider@@AEBAXPEAUIPackageManager@Deployment@Management@Windows@@PEAUIPackage@ApplicationModel@5@@Z`
- size: `482`
- prototype: `void __fastcall(void **this, struct Windows::Management::Deployment::IPackageManager *, struct Windows::ApplicationModel::IPackage *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004e370`

## callees

- `0x180003a00`
- `0x180012a98`
- `0x180035ce4`
- `0x18004b2f8`
- `0x18004da80`
- `0x18004f528`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f586`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f65d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f586`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f65d`

## string_xrefs

- `0x18004f6a0`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004f6b5`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004f6ca`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004f6df`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004f6f8`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`

## pseudocode

```c
void __fastcall LxpLanguageResourcesProvider::_UninstallPackage(
        void **this,
        struct Windows::Management::Deployment::IPackageManager *a2,
        struct Windows::ApplicationModel::IPackage *a3)
{
  int v5; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rbx
  const char *v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rcx
  HSTRING string; // [rsp+20h] [rbp-30h] BYREF
  __int64 v16; // [rsp+28h] [rbp-28h] BYREF
  __int64 v17; // [rsp+30h] [rbp-20h] BYREF
  __int64 v18; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  v18 = 0;
  v5 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::IPackage *, __int64 *))(*(_QWORD *)a3 + 48LL))(
         a3,
         &v18);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x257,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v5,
      (int)string);
  string = 0;
  v6 = v18;
  v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v18 + 96LL);
  WindowsDeleteString(0);
  string = 0;
  v8 = v7(v6, &string);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x25A,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v8,
      (int)string);
  v17 = 0;
  v9 = (*(__int64 (__fastcall **)(struct Windows::Management::Deployment::IPackageManager *, HSTRING, __int64 *))(*(_QWORD *)a2 + 64LL))(
         a2,
         string,
         &v17);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x25F,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v9,
      (int)string);
  Microsoft::WRL::Details::Make<CompletionHandler,>(&v16);
  v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 64LL))(v17, v16);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x262,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v10,
      (int)string);
  v11 = v16;
  CancellableWait(*(void **)(v16 + 16), this[1], 0x1B7740u);
  v12 = (const char *)*(unsigned int *)(v11 + 24);
  if ( (int)v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE6,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
      v12,
      (int)string);
  if ( v16 )
  {
    v16 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::Release();
  }
  v13 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  WindowsDeleteString(string);
  string = 0;
  v14 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
}

```

## disassembly

```asm
0x18004f528  push    rbp
0x18004f52a  push    rbx
0x18004f52b  push    rsi
0x18004f52c  push    rdi
0x18004f52d  push    r14
0x18004f52f  mov     rbp, rsp
0x18004f532  sub     rsp, 50h
0x18004f536  mov     rax, cs:__security_cookie
0x18004f53d  xor     rax, rsp
0x18004f540  mov     [rbp+var_10], rax
0x18004f544  mov     rsi, rdx
0x18004f547  mov     r14, rcx
0x18004f54a  mov     [rbp+var_18], 0
0x18004f552  mov     rax, [r8]
0x18004f555  lea     rdx, [rbp+var_18]
0x18004f559  mov     rcx, r8
0x18004f55c  mov     rax, [rax+30h]
0x18004f560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f565  mov     rcx, [rbp+28h]; this
0x18004f569  test    eax, eax
0x18004f56b  js      loc_18004F6B2
0x18004f571  mov     [rbp+string], 0
0x18004f579  mov     rdi, [rbp+var_18]
0x18004f57d  mov     rax, [rdi]
0x18004f580  mov     rbx, [rax+60h]
0x18004f584  xor     ecx, ecx; string
0x18004f586  call    cs:__imp_WindowsDeleteString
0x18004f58c  mov     [rbp+string], 0
0x18004f594  lea     rdx, [rbp+string]
0x18004f598  mov     rcx, rdi
0x18004f59b  mov     rax, rbx
0x18004f59e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5a3  mov     rcx, [rbp+28h]; this
0x18004f5a7  test    eax, eax
0x18004f5a9  js      loc_18004F6C7
0x18004f5af  mov     [rbp+var_20], 0
0x18004f5b7  mov     rax, [rsi]
0x18004f5ba  lea     r8, [rbp+var_20]
0x18004f5be  mov     rdx, [rbp+string]
0x18004f5c2  mov     rcx, rsi
0x18004f5c5  mov     rax, [rax+40h]
0x18004f5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5ce  mov     rcx, [rbp+28h]; this
0x18004f5d2  test    eax, eax
0x18004f5d4  js      loc_18004F6DC
0x18004f5da  lea     rcx, [rbp+var_28]
0x18004f5de  call    ??$Make@VCompletionHandler@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCompletionHandler@@@12@XZ; Microsoft::WRL::Details::Make<CompletionHandler,>(void)
0x18004f5e3  nop
0x18004f5e4  mov     rcx, [rbp+var_20]
0x18004f5e8  mov     rax, [rcx]
0x18004f5eb  mov     rdx, [rbp+var_28]
0x18004f5ef  mov     rax, [rax+40h]
0x18004f5f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5f8  test    eax, eax
0x18004f5fa  js      loc_18004F6F1
0x18004f600  mov     rbx, [rbp+var_28]
0x18004f604  mov     r8d, 1B7740h; unsigned int
0x18004f60a  mov     rdx, [r14+8]; void *
0x18004f60e  mov     rcx, [rbx+10h]; void *
0x18004f612  call    ?CancellableWait@@YAXPEAX0K@Z; CancellableWait(void *,void *,ulong)
0x18004f617  mov     r9d, [rbx+18h]; char *
0x18004f61b  mov     rcx, [rbp+28h]; this
0x18004f61f  test    r9d, r9d
0x18004f622  js      short loc_18004F6A0
0x18004f624  mov     rcx, [rbp+var_28]
0x18004f628  test    rcx, rcx
0x18004f62b  jz      short loc_18004F63B
0x18004f62d  mov     [rbp+var_28], 0
0x18004f635  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::Release(void)
0x18004f63a  nop
0x18004f63b  mov     rcx, [rbp+var_20]
0x18004f63f  test    rcx, rcx
0x18004f642  jz      short loc_18004F659
0x18004f644  mov     [rbp+var_20], 0
0x18004f64c  mov     rax, [rcx]
0x18004f64f  mov     rax, [rax+10h]
0x18004f653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f658  nop
0x18004f659  mov     rcx, [rbp+string]; string
0x18004f65d  call    cs:__imp_WindowsDeleteString
0x18004f663  mov     [rbp+string], 0
0x18004f66b  mov     rcx, [rbp+var_18]
0x18004f66f  test    rcx, rcx
0x18004f672  jz      short loc_18004F689
0x18004f674  mov     [rbp+var_18], 0
0x18004f67c  mov     rax, [rcx]
0x18004f67f  mov     rax, [rax+10h]
0x18004f683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f688  nop
0x18004f689  mov     rcx, [rbp+var_10]
0x18004f68d  xor     rcx, rsp; StackCookie
0x18004f690  call    __security_check_cookie
0x18004f695  add     rsp, 50h
0x18004f699  pop     r14
0x18004f69b  pop     rdi
0x18004f69c  pop     rsi
0x18004f69d  pop     rbx
0x18004f69e  pop     rbp
0x18004f69f  retn
0x18004f6a0  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004f6a7  mov     edx, 0E6h; void *
0x18004f6ac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f6b2  mov     r9d, eax; char *
0x18004f6b5  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004f6bc  mov     edx, 257h; void *
0x18004f6c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f6c7  mov     r9d, eax; char *
0x18004f6ca  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004f6d1  mov     edx, 25Ah; void *
0x18004f6d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f6dc  mov     r9d, eax; char *
0x18004f6df  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004f6e6  mov     edx, 25Fh; void *
0x18004f6eb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f6f1  mov     rcx, [rbp+28h]; this
0x18004f6f5  mov     r9d, eax; char *
0x18004f6f8  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004f6ff  mov     edx, 262h; void *
0x18004f704  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
