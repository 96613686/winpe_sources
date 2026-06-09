# CSetImageFeedDialog::CreateAndShowMessageDialog(bool *)

- ea: `0x18004d208`
- end: `0x18004d6bc`
- name: `?CreateAndShowMessageDialog@CSetImageFeedDialog@@QEAAJPEA_N@Z`
- size: `1204`
- prototype: `__int64 __fastcall(CSetImageFeedDialog *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800ceecc`

## callees

- `0x18000a910`
- `0x18002a700`
- `0x18003217c`
- `0x180034db4`
- `0x18003aa84`
- `0x18003d858`
- `0x18003dfac`
- `0x18004d208`
- `0x18004d6c4`
- `0x18004d6f0`
- `0x180050ba0`
- `0x1800cd5bc`
- `0x1800cdb14`
- `0x1800cddec`
- `0x1800ce98c`
- `0x1800ce9f8`
- `0x1800cea60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004d32c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004d48f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004d32c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004d48f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004d571`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004d571`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18004d5b8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18004d5b8`
- `USER32!GetWindowThreadProcessId` at `0x18004d560`
- `USER32!GetWindowThreadProcessId` at `0x18004d560`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CSetImageFeedDialog::CreateAndShowMessageDialog(CSetImageFeedDialog *this, bool *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rbx
  int v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  __int64 *v10; // rcx
  int v11; // eax
  __int64 v12; // rdx
  __int64 *v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  HANDLE v16; // rbx
  PVOID v17; // rdi
  enum tagCOWAIT_FLAGS v18; // edx
  int Error; // eax
  __int64 v20; // rdx
  __int64 v21; // r9
  int v22; // ecx
  ULONG dwMilliseconds; // [rsp+20h] [rbp-E0h]
  ULONG dwMillisecondsa; // [rsp+20h] [rbp-E0h]
  char v26[8]; // [rsp+30h] [rbp-D0h] BYREF
  PVOID Context; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h]
  __int64 v30; // [rsp+50h] [rbp-B0h]
  void *phNewWaitObject; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v32; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+68h] [rbp-98h] BYREF
  __int64 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+78h] [rbp-88h]
  DWORD dwProcessId; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v37[3]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  if ( a2 )
    *a2 = 0;
  Context = 0;
  v26[0] = 1;
  LODWORD(v32) = 1;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&Context);
  v4 = Microsoft::WRL::Details::MakeAndInitialize<CMessageDialogHelper,CMessageDialogHelper,HWND__ * &,enum CMessageDialogHelper::ActivationType,bool>(
         &Context,
         (char *)this + 48,
         &v32,
         v26);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v28 = 0;
    v29 = 0;
    v30 = 0;
    v6 = *((_QWORD *)this + 7);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v28);
    v29 = -1;
    v30 = -1;
    v7 = ResourceStringCoAllocFormatMessage(&_ImageBase, *((unsigned int *)this + 8), &v28, v6);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC3,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\setimagefeeddialog.cpp",
        (const char *)(unsigned int)v7,
        dwMilliseconds);
    if ( *((_DWORD *)this + 8) == 38326 )
    {
      if ( LoadStringW(&_ImageBase, 0x95B7u, Buffer, 260) <= 0 )
      {
        v8 = 201;
LABEL_10:
        v5 = -2147467259;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\setimagefeeddialog.cpp",
          (const char *)0x80004005LL,
          dwMilliseconds);
LABEL_11:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v28);
        goto LABEL_50;
      }
      memset(v37, 0, sizeof(v37));
      v9 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
             v37,
             &_ImageBase,
             38329);
      v5 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCD,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\setimagefeeddialog.cpp",
          (const char *)(unsigned int)v9,
          dwMilliseconds);
LABEL_14:
        v10 = v37;
LABEL_15:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v10);
        goto LABEL_11;
      }
      v33 = 0;
      v34 = 0;
      v35 = 0;
      v11 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
              &v33,
              &_ImageBase,
              38330);
      v5 = v11;
      if ( v11 < 0 )
      {
        v12 = 207;
LABEL_18:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\setimagefeeddialog.cpp",
          (const char *)(unsigned int)v11,
          dwMilliseconds);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v33);
        goto LABEL_14;
      }
      v11 = CMessageDialogHelper::SetTitle((CMessageDialogHelper *)Context, v28);
      v5 = v11;
      if ( v11 < 0 )
      {
        v12 = 209;
        goto LABEL_18;
      }
      v11 = CMessageDialogHelper::SetContent((CMessageDialogHelper *)Context, Buffer);
      v5 = v11;
      if ( v11 < 0 )
      {
        v12 = 210;
        goto LABEL_18;
      }
      v11 = CMessageDialogHelper::AddButton(Context, 38329, v37[0], 0);
      v5 = v11;
      if ( v11 < 0 )
      {
        v12 = 213;
        goto LABEL_18;
      }
      v11 = CMessageDialogHelper::AddButton(Context, 38330, v33, 1);
      v5 = v11;
      if ( v11 < 0 )
      {
        v12 = 214;
        goto LABEL_18;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v33);
      v13 = v37;
LABEL_40:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v13);
      dwProcessId = 0;
      GetWindowThreadProcessId(*((HWND *)this + 6), &dwProcessId);
      v16 = OpenProcess(0x100000u, 0, dwProcessId);
      v32 = v16;
      phNewWaitObject = 0;
      v17 = Context;
      wil::details::unique_storage_wil::details::handle_null_resource_policy_void____cdecl___void______anonymous_namespace_::UnregisterProcessExitWait___::reset(
        &phNewWaitObject,
        0);
      if ( RegisterWaitForSingleObject(
             &phNewWaitObject,
             v16,
             lambda_64d41ede1ce24ee49d935c7f611bcae6_::_lambda_invoker_cdecl_,
             v17,
             0xFFFFFFFF,
             8u)
        || (Error = ResultFromKnownLastError(), v5 = Error, Error >= 0) )
      {
        Error = CMessageDialogHelper::ShowMessageDialogAndWait((CMessageDialogHelper *)Context, v18);
        v5 = Error;
        if ( Error >= 0 )
        {
          wil::details::unique_storage_wil::details::handle_null_resource_policy_void____cdecl___void______anonymous_namespace_::UnregisterProcessExitWait___::reset(
            &phNewWaitObject,
            0);
          v22 = *((_DWORD *)Context + 20);
          switch ( v22 )
          {
            case 38329:
              *a2 = 1;
              break;
            case 38330:
              *a2 = 0;
              break;
            case -1:
            case 38337:
              break;
            default:
              v5 = -2147418113;
              v21 = 2147549183LL;
              v20 = 265;
              goto LABEL_44;
          }
          wil::details::unique_storage_wil::details::handle_null_resource_policy_void____cdecl___void______anonymous_namespace_::UnregisterProcessExitWait___::_unique_storage_wil::details::handle_null_resource_policy_void____cdecl___void______anonymous_namespace_::UnregisterProcessExitWait___(&phNewWaitObject);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v32);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v28);
          v5 = 0;
          goto LABEL_50;
        }
        v20 = 247;
      }
      else
      {
        v20 = 245;
      }
      v21 = (unsigned int)Error;
LABEL_44:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\setimagefeeddialog.cpp",
        (const char *)v21,
        dwMillisecondsa);
      wil::details::unique_storage_wil::details::handle_null_resource_policy_void____cdecl___void______anonymous_namespace_::UnregisterProcessExitWait___::_unique_storage_wil::details::handle_null_resource_policy_void____cdecl___void______anonymous_namespace_::UnregisterProcessExitWait___(&phNewWaitObject);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v32);
      goto LABEL_11;
    }
    if ( LoadStringW(&_ImageBase, *((_DWORD *)this + 9), Buffer, 260) <= 0 )
    {
      v8 = 218;
      goto LABEL_10;
    }
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v14 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
            &v33,
            &_ImageBase,
            38337);
    v5 = v14;
    if ( v14 >= 0 )
    {
      v14 = CMessageDialogHelper::SetTitle((CMessageDialogHelper *)Context, v28);
      v5 = v14;
      if ( v14 >= 0 )
      {
        v14 = CMessageDialogHelper::SetContent((CMessageDialogHelper *)Context, Buffer);
        v5 = v14;
        if ( v14 >= 0 )
        {
          v14 = CMessageDialogHelper::AddButton(Context, 38337, v33, 1);
          v5 = v14;
          if ( v14 >= 0 )
          {
            v13 = &v33;
            goto LABEL_40;
          }
          v15 = 227;
        }
        else
        {
          v15 = 225;
        }
      }
      else
      {
        v15 = 224;
      }
    }
    else
    {
      v15 = 222;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\setimagefeeddialog.cpp",
      (const char *)(unsigned int)v14,
      dwMilliseconds);
    v10 = &v33;
    goto LABEL_15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC0,
    (unsigned int)"shell\\windowsuiimmersive\\userinfo\\setimagefeeddialog.cpp",
    (const char *)(unsigned int)v4,
    dwMilliseconds);
LABEL_50:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&Context);
  return v5;
}

```

## disassembly

```asm
0x18004d208  mov     [rsp-8+arg_10], rbx
0x18004d20d  push    rbp
0x18004d20e  push    rsi
0x18004d20f  push    rdi
0x18004d210  push    r12
0x18004d212  push    r13
0x18004d214  push    r14
0x18004d216  push    r15
0x18004d218  lea     rbp, [rsp-1C0h]
0x18004d220  sub     rsp, 2C0h
0x18004d227  mov     rax, cs:__security_cookie
0x18004d22e  xor     rax, rsp
0x18004d231  mov     [rbp+1F0h+var_40], rax
0x18004d238  mov     r14, rdx
0x18004d23b  mov     rdi, rcx
0x18004d23e  xor     r12d, r12d
0x18004d241  test    rdx, rdx
0x18004d244  jz      short loc_18004D249
0x18004d246  mov     [rdx], r12b
0x18004d249  mov     [rsp+2F0h+Context], r12
0x18004d24e  mov     [rsp+2F0h+var_2C0], 1
0x18004d253  mov     dword ptr [rsp+2F0h+var_290], 1
0x18004d25b  lea     rcx, [rsp+2F0h+Context]
0x18004d260  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d265  lea     r15, [rdi+30h]
0x18004d269  lea     r9, [rsp+2F0h+var_2C0]
0x18004d26e  lea     r8, [rsp+2F0h+var_290]
0x18004d273  mov     rdx, r15
0x18004d276  lea     rcx, [rsp+2F0h+Context]
0x18004d27b  call    ??$MakeAndInitialize@VCMessageDialogHelper@@V1@AEAPEAUHWND__@@W4ActivationType@1@_N@Details@WRL@Microsoft@@YAJPEAPEAVCMessageDialogHelper@@AEAPEAUHWND__@@$$QEAW4ActivationType@3@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<CMessageDialogHelper,CMessageDialogHelper,HWND__ * &,CMessageDialogHelper::ActivationType,bool>(CMessageDialogHelper * *,HWND__ * &,CMessageDialogHelper::ActivationType &&,bool &&)
0x18004d280  mov     ebx, eax
0x18004d282  test    eax, eax
0x18004d284  jns     short loc_18004D2A6
0x18004d286  mov     rcx, [rbp+1F8h]; this
0x18004d28d  mov     r9d, eax; char *
0x18004d290  lea     r8, aShellWindowsui_1; "shell\\windowsuiimmersive\\userinfo\\se"...
0x18004d297  mov     edx, 0C0h; void *
0x18004d29c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d2a1  jmp     loc_18004D659
0x18004d2a6  mov     [rsp+2F0h+var_2B0], r12
0x18004d2ab  mov     [rsp+2F0h+var_2A8], r12
0x18004d2b0  mov     [rsp+2F0h+var_2A0], r12
0x18004d2b5  mov     rbx, [rdi+38h]
0x18004d2b9  lea     rcx, [rsp+2F0h+var_2B0]
0x18004d2be  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004d2c3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004d2c7  mov     [rsp+2F0h+var_2A8], rax
0x18004d2cc  mov     [rsp+2F0h+var_2A0], rax
0x18004d2d1  mov     r9, rbx
0x18004d2d4  lea     r8, [rsp+2F0h+var_2B0]
0x18004d2d9  mov     edx, [rdi+20h]
0x18004d2dc  lea     r13, __ImageBase
0x18004d2e3  mov     rcx, r13
0x18004d2e6  call    ResourceStringCoAllocFormatMessage
0x18004d2eb  mov     rcx, [rbp+1F8h]; this
0x18004d2f2  lea     rsi, aShellWindowsui_1; "shell\\windowsuiimmersive\\userinfo\\se"...
0x18004d2f9  test    eax, eax
0x18004d2fb  jns     short loc_18004D30D
0x18004d2fd  mov     r9d, eax; char *
0x18004d300  mov     r8, rsi; unsigned int
0x18004d303  mov     edx, 0C3h; void *
0x18004d308  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004d30d  mov     r9d, 104h; cchBufferMax
0x18004d313  lea     r8, [rbp+1F0h+Buffer]; lpBuffer
0x18004d317  mov     rcx, r13; hInstance
0x18004d31a  cmp     dword ptr [rdi+20h], 95B6h
0x18004d321  jnz     loc_18004D48C
0x18004d327  mov     edx, 95B7h; uID
0x18004d32c  call    cs:__imp_LoadStringW
0x18004d332  test    eax, eax
0x18004d334  jg      short loc_18004D362
0x18004d336  mov     edx, 0C9h; void *
0x18004d33b  mov     ebx, 80004005h
0x18004d340  mov     r8, rsi; unsigned int
0x18004d343  mov     r9d, ebx; char *
0x18004d346  mov     rcx, [rbp+1F8h]; this
0x18004d34d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d352  nop
0x18004d353  lea     rcx, [rsp+2F0h+var_2B0]
0x18004d358  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004d35d  jmp     loc_18004D659
0x18004d362  mov     [rbp+1F0h+var_268], r12
0x18004d366  mov     [rbp+1F0h+var_260], r12
0x18004d36a  mov     [rbp+1F0h+var_258], r12
0x18004d36e  mov     r8d, 95B9h
0x18004d374  mov     rdx, r13
0x18004d377  lea     rcx, [rbp+1F0h+var_268]
0x18004d37b  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)
0x18004d380  mov     ebx, eax
0x18004d382  test    eax, eax
0x18004d384  jns     short loc_18004D3A9
0x18004d386  mov     rcx, [rbp+1F8h]; this
0x18004d38d  mov     r9d, eax; char *
0x18004d390  mov     r8, rsi; unsigned int
0x18004d393  mov     edx, 0CDh; void *
0x18004d398  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d39d  nop
0x18004d39e  lea     rcx, [rbp+1F0h+var_268]
0x18004d3a2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004d3a7  jmp     short loc_18004D353
0x18004d3a9  mov     [rsp+2F0h+var_288], r12
0x18004d3ae  mov     [rsp+2F0h+var_280], r12
0x18004d3b3  mov     [rsp+2F0h+var_278], r12
0x18004d3b8  mov     edi, 95BAh
0x18004d3bd  mov     r8d, edi
0x18004d3c0  mov     rdx, r13
0x18004d3c3  lea     rcx, [rsp+2F0h+var_288]
0x18004d3c8  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)
0x18004d3cd  mov     ebx, eax
0x18004d3cf  test    eax, eax
0x18004d3d1  jns     short loc_18004D3F7
0x18004d3d3  mov     edx, 0CFh; void *
0x18004d3d8  mov     rcx, [rbp+1F8h]; this
0x18004d3df  mov     r9d, eax; char *
0x18004d3e2  mov     r8, rsi; unsigned int
0x18004d3e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d3ea  nop
0x18004d3eb  lea     rcx, [rsp+2F0h+var_288]
0x18004d3f0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004d3f5  jmp     short loc_18004D39E
0x18004d3f7  mov     rdx, [rsp+2F0h+var_2B0]; unsigned __int16 *
0x18004d3fc  mov     rcx, [rsp+2F0h+Context]; this
0x18004d401  call    ?SetTitle@CMessageDialogHelper@@QEAAJPEBG@Z; CMessageDialogHelper::SetTitle(ushort const *)
0x18004d406  mov     ebx, eax
0x18004d408  test    eax, eax
0x18004d40a  jns     short loc_18004D413
0x18004d40c  mov     edx, 0D1h
0x18004d411  jmp     short loc_18004D3D8
0x18004d413  lea     rdx, [rbp+1F0h+Buffer]; unsigned __int16 *
0x18004d417  mov     rcx, [rsp+2F0h+Context]; this
0x18004d41c  call    ?SetContent@CMessageDialogHelper@@QEAAJPEBG@Z; CMessageDialogHelper::SetContent(ushort const *)
0x18004d421  mov     ebx, eax
0x18004d423  test    eax, eax
0x18004d425  jns     short loc_18004D42E
0x18004d427  mov     edx, 0D2h
0x18004d42c  jmp     short loc_18004D3D8
0x18004d42e  xor     r9d, r9d
0x18004d431  mov     r8, [rbp+1F0h+var_268]
0x18004d435  mov     edx, 95B9h
0x18004d43a  mov     rcx, [rsp+2F0h+Context]
0x18004d43f  call    ?AddButton@CMessageDialogHelper@@QEAAJIPEBGW4MessageDialogButtonOptions@@@Z; CMessageDialogHelper::AddButton(uint,ushort const *,MessageDialogButtonOptions)
0x18004d444  mov     ebx, eax
0x18004d446  test    eax, eax
0x18004d448  jns     short loc_18004D451
0x18004d44a  mov     edx, 0D5h
0x18004d44f  jmp     short loc_18004D3D8
0x18004d451  mov     r9d, 1
0x18004d457  mov     r8, [rsp+2F0h+var_288]
0x18004d45c  mov     edx, edi
0x18004d45e  mov     rcx, [rsp+2F0h+Context]
0x18004d463  call    ?AddButton@CMessageDialogHelper@@QEAAJIPEBGW4MessageDialogButtonOptions@@@Z; CMessageDialogHelper::AddButton(uint,ushort const *,MessageDialogButtonOptions)
0x18004d468  mov     ebx, eax
0x18004d46a  test    eax, eax
0x18004d46c  jns     short loc_18004D478
0x18004d46e  mov     edx, 0D6h
0x18004d473  jmp     loc_18004D3D8
0x18004d478  lea     rcx, [rsp+2F0h+var_288]
0x18004d47d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004d482  nop
0x18004d483  lea     rcx, [rbp+1F0h+var_268]
0x18004d487  jmp     loc_18004D550
0x18004d48c  mov     edx, [rdi+24h]; uID
0x18004d48f  call    cs:__imp_LoadStringW
0x18004d495  test    eax, eax
0x18004d497  jg      short loc_18004D4A3
0x18004d499  mov     edx, 0DAh
0x18004d49e  jmp     loc_18004D33B
0x18004d4a3  mov     [rsp+2F0h+var_288], r12
0x18004d4a8  mov     [rsp+2F0h+var_280], r12
0x18004d4ad  mov     [rsp+2F0h+var_278], r12
0x18004d4b2  mov     r8d, 95C1h
0x18004d4b8  mov     rdx, r13
0x18004d4bb  lea     rcx, [rsp+2F0h+var_288]
0x18004d4c0  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)
0x18004d4c5  mov     ebx, eax
0x18004d4c7  test    eax, eax
0x18004d4c9  jns     short loc_18004D4ED
0x18004d4cb  mov     edx, 0DEh; void *
0x18004d4d0  mov     r8, rsi; unsigned int
0x18004d4d3  mov     r9d, eax; char *
0x18004d4d6  mov     rcx, [rbp+1F8h]; this
0x18004d4dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d4e2  nop
0x18004d4e3  lea     rcx, [rsp+2F0h+var_288]
0x18004d4e8  jmp     loc_18004D3A2
0x18004d4ed  mov     rdx, [rsp+2F0h+var_2B0]; unsigned __int16 *
0x18004d4f2  mov     rcx, [rsp+2F0h+Context]; this
0x18004d4f7  call    ?SetTitle@CMessageDialogHelper@@QEAAJPEBG@Z; CMessageDialogHelper::SetTitle(ushort const *)
0x18004d4fc  mov     ebx, eax
0x18004d4fe  test    eax, eax
0x18004d500  jns     short loc_18004D509
0x18004d502  mov     edx, 0E0h
0x18004d507  jmp     short loc_18004D4D0
0x18004d509  lea     rdx, [rbp+1F0h+Buffer]; unsigned __int16 *
0x18004d50d  mov     rcx, [rsp+2F0h+Context]; this
0x18004d512  call    ?SetContent@CMessageDialogHelper@@QEAAJPEBG@Z; CMessageDialogHelper::SetContent(ushort const *)
0x18004d517  mov     ebx, eax
0x18004d519  test    eax, eax
0x18004d51b  jns     short loc_18004D524
0x18004d51d  mov     edx, 0E1h
0x18004d522  jmp     short loc_18004D4D0
0x18004d524  mov     r9d, 1
0x18004d52a  mov     r8, [rsp+2F0h+var_288]
0x18004d52f  mov     edx, 95C1h
0x18004d534  mov     rcx, [rsp+2F0h+Context]
0x18004d539  call    ?AddButton@CMessageDialogHelper@@QEAAJIPEBGW4MessageDialogButtonOptions@@@Z; CMessageDialogHelper::AddButton(uint,ushort const *,MessageDialogButtonOptions)
0x18004d53e  mov     ebx, eax
0x18004d540  test    eax, eax
0x18004d542  jns     short loc_18004D54B
0x18004d544  mov     edx, 0E3h
0x18004d549  jmp     short loc_18004D4D0
0x18004d54b  lea     rcx, [rsp+2F0h+var_288]
0x18004d550  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004d555  mov     [rbp+1F0h+dwProcessId], r12d
0x18004d559  lea     rdx, [rbp+1F0h+dwProcessId]; lpdwProcessId
0x18004d55d  mov     rcx, [r15]; hWnd
0x18004d560  call    cs:__imp_GetWindowThreadProcessId
0x18004d566  mov     r8d, [rbp+1F0h+dwProcessId]; dwProcessId
0x18004d56a  xor     edx, edx; bInheritHandle
0x18004d56c  mov     ecx, 100000h; dwDesiredAccess
0x18004d571  call    cs:__imp_OpenProcess
0x18004d577  mov     rbx, rax
0x18004d57a  mov     [rsp+2F0h+var_290], rax
0x18004d57f  mov     [rsp+2F0h+phNewWaitObject], r12
0x18004d584  mov     rdi, [rsp+2F0h+Context]
0x18004d589  xor     edx, edx
0x18004d58b  lea     rcx, [rsp+2F0h+phNewWaitObject]
0x18004d590  call    wil__details__unique_storage_wil__details__handle_null_resource_policy_void____cdecl___void______anonymous_namespace___UnregisterProcessExitWait_____reset
0x18004d595  mov     [rsp+2F0h+dwFlags], 8; dwFlags
0x18004d59d  or      r15d, 0FFFFFFFFh
0x18004d5a1  mov     [rsp+2F0h+dwMilliseconds], r15d; int
0x18004d5a6  mov     r9, rdi; Context
0x18004d5a9  lea     r8, _lambda_64d41ede1ce24ee49d935c7f611bcae6____lambda_invoker_cdecl_; Callback
0x18004d5b0  mov     rdx, rbx; hObject
0x18004d5b3  lea     rcx, [rsp+2F0h+phNewWaitObject]; phNewWaitObject
0x18004d5b8  call    cs:__imp_RegisterWaitForSingleObject
0x18004d5be  test    eax, eax
0x18004d5c0  jnz     short loc_18004D5FF
0x18004d5c2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004d5c7  mov     ebx, eax
0x18004d5c9  test    eax, eax
0x18004d5cb  jns     short loc_18004D5FF
0x18004d5cd  mov     edx, 0F5h; void *
0x18004d5d2  mov     r9d, eax; char *
0x18004d5d5  mov     rcx, [rbp+1F8h]; this
0x18004d5dc  mov     r8, rsi; unsigned int
0x18004d5df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d5e4  nop
0x18004d5e5  lea     rcx, [rsp+2F0h+phNewWaitObject]
0x18004d5ea  call    wil__details__unique_storage_wil__details__handle_null_resource_policy_void____cdecl___void______anonymous_namespace___UnregisterProcessExitWait______unique_storage_wil__details__handle_null_resource_policy_void____cdecl___void______anonymous_namespace___UnregisterProcessExitWait___
0x18004d5ef  nop
0x18004d5f0  lea     rcx, [rsp+2F0h+var_290]
0x18004d5f5  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004d5fa  jmp     loc_18004D353
0x18004d5ff  mov     rcx, [rsp+2F0h+Context]; this
0x18004d604  call    ?ShowMessageDialogAndWait@CMessageDialogHelper@@QEAAJW4tagCOWAIT_FLAGS@@@Z; CMessageDialogHelper::ShowMessageDialogAndWait(tagCOWAIT_FLAGS)
0x18004d609  mov     ebx, eax
0x18004d60b  test    eax, eax
0x18004d60d  jns     short loc_18004D616
0x18004d60f  mov     edx, 0F7h
0x18004d614  jmp     short loc_18004D5D2
0x18004d616  xor     edx, edx
0x18004d618  lea     rcx, [rsp+2F0h+phNewWaitObject]
0x18004d61d  call    wil__details__unique_storage_wil__details__handle_null_resource_policy_void____cdecl___void______anonymous_namespace___UnregisterProcessExitWait_____reset
0x18004d622  mov     rax, [rsp+2F0h+Context]
0x18004d627  mov     ecx, [rax+50h]
0x18004d62a  cmp     ecx, 95B9h
0x18004d630  jnz     short loc_18004D68F
0x18004d632  mov     byte ptr [r14], 1
0x18004d636  lea     rcx, [rsp+2F0h+phNewWaitObject]
0x18004d63b  call    wil__details__unique_storage_wil__details__handle_null_resource_policy_void____cdecl___void______anonymous_namespace___UnregisterProcessExitWait______unique_storage_wil__details__handle_null_resource_policy_void____cdecl___void______anonymous_namespace___UnregisterProcessExitWait___
0x18004d640  nop
0x18004d641  lea     rcx, [rsp+2F0h+var_290]
0x18004d646  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004d64b  nop
0x18004d64c  lea     rcx, [rsp+2F0h+var_2B0]
0x18004d651  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004d656  mov     ebx, r12d
0x18004d659  lea     rcx, [rsp+2F0h+Context]
0x18004d65e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d663  mov     eax, ebx
0x18004d665  mov     rcx, [rbp+1F0h+var_40]
0x18004d66c  xor     rcx, rsp; StackCookie
0x18004d66f  call    __security_check_cookie
0x18004d674  mov     rbx, [rsp+2F0h+arg_10]
0x18004d67c  add     rsp, 2C0h
0x18004d683  pop     r15
0x18004d685  pop     r14
0x18004d687  pop     r13
0x18004d689  pop     r12
0x18004d68b  pop     rdi
0x18004d68c  pop     rsi
0x18004d68d  pop     rbp
0x18004d68e  retn
0x18004d68f  cmp     ecx, 95BAh
0x18004d695  jnz     short loc_18004D69C
0x18004d697  mov     [r14], r12b
0x18004d69a  jmp     short loc_18004D636
0x18004d69c  cmp     ecx, r15d
0x18004d69f  jz      short loc_18004D636
  ... truncated ...
```
