# _lambda_b505ef1f8418cadf1b666e845785b169_::operator()_Windows::Internal::CMarshaledInterfaceResult_Windows::Graphics::Capture::Server::ICapturableItem___

- ea: `0x18000b9a4`
- end: `0x18000bba7`
- name: `_lambda_b505ef1f8418cadf1b666e845785b169_::operator()_Windows::Internal::CMarshaledInterfaceResult_Windows::Graphics::Capture::Server::ICapturableItem___`
- size: `515`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800148f0`

## callees

- `0x180002e60`
- `0x180007630`
- `0x18000907c`
- `0x18000b9a4`
- `0x18000c0ac`
- `0x18000cd90`
- `0x18000d4a4`
- `0x18000d4d4`
- `0x18000d7d8`
- `0x18000ddc4`
- `0x180022010`

## string_xrefs

- `0x18000b9e2`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x18000ba21`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x18000bb07`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall lambda_b505ef1f8418cadf1b666e845785b169_::operator()_Windows::Internal::CMarshaledInterfaceResult_Windows::Graphics::Capture::Server::ICapturableItem___(
        __int64 a1,
        __int64 a2,
        int a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // eax
  _QWORD *v11; // rdx
  _QWORD *v12; // rdx
  int v14; // [rsp+20h] [rbp-69h]
  __int64 v15; // [rsp+40h] [rbp-49h] BYREF
  _BYTE *v16; // [rsp+48h] [rbp-41h] BYREF
  __int64 v17; // [rsp+50h] [rbp-39h] BYREF
  __int64 v18; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v19[8]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v20[8]; // [rsp+68h] [rbp-21h] BYREF
  _QWORD v21[2]; // [rsp+70h] [rbp-19h] BYREF
  _QWORD v22[7]; // [rsp+80h] [rbp-9h] BYREF
  _QWORD *v23; // [rsp+B8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v5 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *>(
         *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(a1 + 8),
         a2,
         a3);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v15 = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 8) + 64LL))(*(_QWORD *)(a1 + 8), &v15);
    v6 = v7;
    if ( v7 >= 0 )
    {
      if ( v15 )
      {
        Windows::Internal::CResultBase::GetDeferral<Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem>>(
          a2,
          v19,
          a2);
        v16 = v19;
        wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_returncode_policy>::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_returncode_policy>(
          &v17,
          (__int64 *)a1);
        wil::com_ptr_t<Windows::Internal::PlatformExtensions::Capture::ICapturableItem,wil::err_returncode_policy>::com_ptr_t<Windows::Internal::PlatformExtensions::Capture::ICapturableItem,wil::err_returncode_policy>(
          &v18,
          v15);
        v22[0] = off_1800235B0;
        v22[1] = v16;
        v8 = v17;
        v17 = 0;
        v22[2] = v8;
        v9 = v18;
        v18 = 0;
        v22[3] = v9;
        v23 = v22;
        lambda_7ece5a4c252d6727f003b9501760a0a7_::__lambda_7ece5a4c252d6727f003b9501760a0a7_(&v16);
        v21[0] = 0;
        v21[1] = v22;
        v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(Windows::Graphics::Capture::Server *__hidden, struct tagComCallData *), _QWORD *, GUID *))(**(_QWORD **)(a1 + 16) + 24LL))(
                *(_QWORD *)(a1 + 16),
                Windows::Graphics::Capture::Server::CreateItemCallback,
                v21,
                &IID_IContextCallback);
        v6 = v10;
        if ( v10 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x313,
            (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
            (const char *)(unsigned int)v10,
            5);
          if ( v23 )
          {
            v11 = v22;
            LOBYTE(v11) = v23 != v22;
            (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v23 + 32LL))(v23, v11);
            v23 = 0;
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v20);
          goto LABEL_14;
        }
        if ( v23 )
        {
          v12 = v22;
          LOBYTE(v12) = v23 != v22;
          (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v23 + 32LL))(v23, v12);
          v23 = 0;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v20);
      }
      v6 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F9,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
        (const char *)(unsigned int)v7,
        v14);
    }
LABEL_14:
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v15);
    return v6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2F5,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
    (const char *)(unsigned int)v5,
    v14);
  return v6;
}

```

## disassembly

```asm
0x18000b9a4  mov     [rsp-8+arg_10], rbx
0x18000b9a9  push    rbp
0x18000b9aa  push    rsi
0x18000b9ab  push    rdi
0x18000b9ac  lea     rbp, [rsp-47h]
0x18000b9b1  sub     rsp, 0D0h
0x18000b9b8  mov     rax, cs:__security_cookie
0x18000b9bf  xor     rax, rsp
0x18000b9c2  mov     [rbp+57h+var_20], rax
0x18000b9c6  mov     rsi, rdx
0x18000b9c9  mov     rdi, rcx
0x18000b9cc  mov     rcx, [rcx+8]
0x18000b9d0  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18000b9d5  mov     ebx, eax
0x18000b9d7  test    eax, eax
0x18000b9d9  jns     short loc_18000B9F8
0x18000b9db  mov     rcx, [rbp+5Fh]; this
0x18000b9df  mov     r9d, eax; char *
0x18000b9e2  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18000b9e9  mov     edx, 2F5h; void *
0x18000b9ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b9f3  jmp     loc_18000BB86
0x18000b9f8  mov     [rbp+57h+var_A0], 0
0x18000ba00  mov     rcx, [rdi+8]
0x18000ba04  mov     rax, [rcx]
0x18000ba07  lea     rdx, [rbp+57h+var_A0]
0x18000ba0b  mov     rax, [rax+40h]
0x18000ba0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba14  mov     ebx, eax
0x18000ba16  test    eax, eax
0x18000ba18  jns     short loc_18000BA37
0x18000ba1a  mov     rcx, [rbp+5Fh]; this
0x18000ba1e  mov     r9d, eax; char *
0x18000ba21  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18000ba28  mov     edx, 2F9h; void *
0x18000ba2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba32  jmp     loc_18000BB7D
0x18000ba37  cmp     [rbp+57h+var_A0], 0
0x18000ba3c  jz      loc_18000BB7B
0x18000ba42  mov     r8, rsi
0x18000ba45  lea     rdx, [rbp+57h+var_80]
0x18000ba49  mov     rcx, rsi
0x18000ba4c  call    ??$GetDeferral@V?$CMarshaledInterfaceResult@UICapturableItem@Server@Capture@Graphics@Windows@@@Internal@Windows@@@CResultBase@Internal@Windows@@QEAA?AV?$AsyncDeferral@V?$CMarshaledInterfaceResult@UICapturableItem@Server@Capture@Graphics@Windows@@@Internal@Windows@@@12@AEAV?$CMarshaledInterfaceResult@UICapturableItem@Server@Capture@Graphics@Windows@@@12@@Z; Windows::Internal::CResultBase::GetDeferral<Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem>>(Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem> &)
0x18000ba51  nop
0x18000ba52  lea     rax, [rbp+57h+var_80]
0x18000ba56  mov     [rbp+57h+var_98], rax
0x18000ba5a  mov     rdx, rdi
0x18000ba5d  lea     rcx, [rbp+57h+var_90]
0x18000ba61  call    ??0?$com_ptr_t@U?$IVector@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_returncode_policy>::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_returncode_policy>(wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_returncode_policy> const &)
0x18000ba66  mov     rdx, [rbp+57h+var_A0]
0x18000ba6a  lea     rcx, [rbp+57h+var_88]
0x18000ba6e  call    ??0?$com_ptr_t@UICapturableItem@Capture@PlatformExtensions@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUICapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::PlatformExtensions::Capture::ICapturableItem,wil::err_returncode_policy>::com_ptr_t<Windows::Internal::PlatformExtensions::Capture::ICapturableItem,wil::err_returncode_policy>(Windows::Internal::PlatformExtensions::Capture::ICapturableItem *)
0x18000ba73  lea     rax, off_1800235B0
0x18000ba7a  mov     [rbp+57h+var_60], rax
0x18000ba7e  mov     rax, [rbp+57h+var_98]
0x18000ba82  mov     [rbp+57h+var_58], rax
0x18000ba86  mov     rax, [rbp+57h+var_90]
0x18000ba8a  mov     [rbp+57h+var_90], 0
0x18000ba92  mov     [rbp+57h+var_50], rax
0x18000ba96  mov     rax, [rbp+57h+var_88]
0x18000ba9a  mov     [rbp+57h+var_88], 0
0x18000baa2  mov     [rbp+57h+var_48], rax
0x18000baa6  lea     rax, [rbp+57h+var_60]
0x18000baaa  mov     [rbp+57h+var_28], rax
0x18000baae  lea     rcx, [rbp+57h+var_98]
0x18000bab2  call    _lambda_7ece5a4c252d6727f003b9501760a0a7_____lambda_7ece5a4c252d6727f003b9501760a0a7_
0x18000bab7  mov     [rbp+57h+var_70], 0
0x18000babf  lea     rax, [rbp+57h+var_60]
0x18000bac3  mov     [rbp+57h+var_68], rax
0x18000bac7  mov     rcx, [rdi+10h]
0x18000bacb  mov     rax, [rcx]
0x18000bace  mov     [rsp+0E0h+var_B8], 0
0x18000bad7  mov     [rsp+0E0h+var_C0], 5; int
0x18000badf  lea     r9, IID_IContextCallback
0x18000bae6  lea     r8, [rbp+57h+var_70]
0x18000baea  lea     rdx, ?CreateItemCallback@Server@Capture@Graphics@Windows@@YAJPEAUtagComCallData@@@Z; Windows::Graphics::Capture::Server::CreateItemCallback(tagComCallData *)
0x18000baf1  mov     rax, [rax+18h]
0x18000baf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bafa  mov     ebx, eax
0x18000bafc  test    eax, eax
0x18000bafe  jns     short loc_18000BB4B
0x18000bb00  mov     rcx, [rbp+5Fh]; this
0x18000bb04  mov     r9d, eax; char *
0x18000bb07  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18000bb0e  mov     edx, 313h; void *
0x18000bb13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bb18  nop
0x18000bb19  mov     rcx, [rbp+57h+var_28]
0x18000bb1d  test    rcx, rcx
0x18000bb20  jz      short loc_18000BB40
0x18000bb22  mov     rax, [rcx]
0x18000bb25  lea     rdx, [rbp+57h+var_60]
0x18000bb29  cmp     rcx, rdx
0x18000bb2c  setnz   dl
0x18000bb2f  mov     rax, [rax+20h]
0x18000bb33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb38  mov     [rbp+57h+var_28], 0
0x18000bb40  lea     rcx, [rbp+57h+var_78]
0x18000bb44  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000bb49  jmp     short loc_18000BB7D
0x18000bb4b  mov     rcx, [rbp+57h+var_28]
0x18000bb4f  test    rcx, rcx
0x18000bb52  jz      short loc_18000BB72
0x18000bb54  mov     rax, [rcx]
0x18000bb57  lea     rdx, [rbp+57h+var_60]
0x18000bb5b  cmp     rcx, rdx
0x18000bb5e  setnz   dl
0x18000bb61  mov     rax, [rax+20h]
0x18000bb65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb6a  mov     [rbp+57h+var_28], 0
0x18000bb72  lea     rcx, [rbp+57h+var_78]
0x18000bb76  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000bb7b  xor     ebx, ebx
0x18000bb7d  lea     rcx, [rbp+57h+var_A0]
0x18000bb81  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18000bb86  mov     eax, ebx
0x18000bb88  mov     rcx, [rbp+57h+var_20]
0x18000bb8c  xor     rcx, rsp; StackCookie
0x18000bb8f  call    __security_check_cookie
0x18000bb94  mov     rbx, [rsp+0E0h+arg_10]
0x18000bb9c  add     rsp, 0D0h
0x18000bba3  pop     rdi
0x18000bba4  pop     rsi
0x18000bba5  pop     rbp
0x18000bba6  retn
```
