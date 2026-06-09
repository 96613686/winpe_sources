# SystemSettings::PenSettings::DevicesPenSetActionBase::LaunchDesktopAppPicker(void)

- ea: `0x18002c690`
- end: `0x18002c9f0`
- name: `?LaunchDesktopAppPicker@DevicesPenSetActionBase@PenSettings@SystemSettings@@AEAAJXZ`
- size: `864`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::DevicesPenSetActionBase *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002faf0`

## callees

- `0x1800030e0`
- `0x180008128`
- `0x18000a2bc`
- `0x180011418`
- `0x1800146a8`
- `0x180016138`
- `0x18001b284`
- `0x18001b2d0`
- `0x18001b510`
- `0x18001cdd4`
- `0x18001fe00`
- `0x1800203bc`
- `0x18002c690`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c744`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c785`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c7ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c9b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c744`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c785`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c7ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c9b8`

## string_xrefs

- `0x18002c711`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x18002c76f`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x18002c7b5`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x18002c828`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x18002c8ce`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x18002c955`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SystemSettings::PenSettings::DevicesPenSetActionBase::LaunchDesktopAppPicker(
        SystemSettings::PenSettings::DevicesPenSetActionBase *this,
        const unsigned __int16 *a2)
{
  _QWORD *v3; // rax
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  HSTRING *v7; // r8
  int ResourceStringById; // eax
  HSTRING v9; // rbx
  int v10; // eax
  int v11; // edi
  __int64 v12; // rsi
  __int64 (__fastcall *v13)(__int64, int *); // rdi
  __int64 v14; // rdx
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, __int64 *); // rdi
  int v17; // eax
  int v18; // edi
  int v20[2]; // [rsp+20h] [rbp-89h] BYREF
  __int64 v21; // [rsp+28h] [rbp-81h] BYREF
  __int64 v22; // [rsp+30h] [rbp-79h] BYREF
  HSTRING string; // [rsp+38h] [rbp-71h] BYREF
  SystemSettings::PenSettings::DevicesPenSetActionBase *v24; // [rsp+40h] [rbp-69h] BYREF
  SystemSettings::PenSettings::DevicesPenSetActionBase *v25; // [rsp+48h] [rbp-61h] BYREF
  int v26; // [rsp+50h] [rbp-59h]
  _BYTE v27[40]; // [rsp+58h] [rbp-51h] BYREF
  HSTRING v28[5]; // [rsp+80h] [rbp-29h] BYREF
  HSTRING v29; // [rsp+A8h] [rbp-1h] BYREF
  HSTRING v30; // [rsp+C8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v21 = 0;
  v3 = (_QWORD *)Windows::Internal::StringReference::StringReference(v28, (const unsigned __int16 (*)[39])a2);
  v4 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Storage::Pickers::IFileOpenPicker>>(
         *v3,
         &v21);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 88LL))(v21, 1);
    v5 = v4;
    if ( v4 < 0 )
    {
      v6 = 1949;
      goto LABEL_5;
    }
    v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 56LL))(v21, 1);
    v5 = v4;
    if ( v4 < 0 )
    {
      v6 = 1950;
      goto LABEL_5;
    }
    WindowsDeleteString(0);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_Devices_Pen_DesktopAppPicker_ChooseApplication",
                           &string,
                           v7);
    v5 = ResourceStringById;
    if ( ResourceStringById < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A1,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
        (const char *)(unsigned int)ResourceStringById,
        v20[0]);
      WindowsDeleteString(string);
      goto LABEL_27;
    }
    v9 = string;
    v10 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v21 + 104LL))(v21, string);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A2,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
        (const char *)(unsigned int)v10,
        v20[0]);
LABEL_12:
      WindowsDeleteString(v9);
      v5 = v11;
      goto LABEL_27;
    }
    *(_QWORD *)v20 = 0;
    Windows::Internal::StringReference::StringReference(&v29, L".exe");
    v12 = v21;
    v13 = *(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 112LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v20);
    v11 = v13(v12, v20);
    if ( v11 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(**(_QWORD **)v20 + 104LL))(*(_QWORD *)v20, v29);
      if ( v11 >= 0 )
      {
        Windows::Internal::StringReference::StringReference(&v30, L".lnk");
        v11 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(**(_QWORD **)v20 + 104LL))(*(_QWORD *)v20, v30);
        if ( v11 >= 0 )
        {
          v22 = 0;
          v15 = v21;
          v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 120LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
          v17 = v16(v15, &v22);
          v11 = v17;
          if ( v17 >= 0 )
          {
            v24 = this;
            Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v24);
            v18 = *((_DWORD *)this + 68);
            wil::cloud_store::cloud_store(
              (wil::cloud_store *)v28,
              (SystemSettings::PenSettings::DevicesPenSetActionBase *)((char *)this + 312));
            v25 = this;
            Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v25);
            v26 = v18;
            wil::cloud_store::cloud_store((wil::cloud_store *)v27, (const struct wil::cloud_store *)v28);
            v11 = StartOperationAndThenAgileCallback_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Storage::StorageFile____Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile_____lambda_5815450939de8374e7ffc211cc22f5ba___(
                    v22,
                    &v25);
            lambda_5815450939de8374e7ffc211cc22f5ba_::__lambda_5815450939de8374e7ffc211cc22f5ba_(&v25);
            if ( v11 >= 0 )
            {
              wil::cloud_store::~cloud_store((wil::cloud_store *)v28);
              (*(void (__fastcall **)(SystemSettings::PenSettings::DevicesPenSetActionBase *))(*(_QWORD *)this + 16LL))(this);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v20);
              WindowsDeleteString(v9);
              v5 = 0;
              goto LABEL_27;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x7E1,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
              (const char *)(unsigned int)v11,
              v20[0]);
            wil::cloud_store::~cloud_store((wil::cloud_store *)v28);
            (*(void (__fastcall **)(SystemSettings::PenSettings::DevicesPenSetActionBase *))(*(_QWORD *)this + 16LL))(this);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x7AB,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
              (const char *)(unsigned int)v17,
              v20[0]);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
          goto LABEL_16;
        }
        v14 = 1960;
      }
      else
      {
        v14 = 1958;
      }
    }
    else
    {
      v14 = 1957;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
      (const char *)(unsigned int)v11,
      v20[0]);
LABEL_16:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v20);
    goto LABEL_12;
  }
  v6 = 1948;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
    (const char *)(unsigned int)v4,
    v20[0]);
LABEL_27:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  return v5;
}

```

## disassembly

```asm
0x18002c690  mov     [rsp-8+arg_8], rbx
0x18002c695  mov     [rsp-8+arg_10], rsi
0x18002c69a  push    rbp
0x18002c69b  push    rdi
0x18002c69c  push    r14
0x18002c69e  lea     rbp, [rsp-47h]
0x18002c6a3  sub     rsp, 0F0h
0x18002c6aa  mov     rax, cs:__security_cookie
0x18002c6b1  xor     rax, rsp
0x18002c6b4  mov     [rbp+57h+var_18], rax
0x18002c6b8  mov     r14, rcx
0x18002c6bb  mov     [rsp+100h+var_D8], 0
0x18002c6c4  lea     rcx, [rbp+57h+var_80]; string
0x18002c6c8  call    ??$?0$0CH@@StringReference@Internal@Windows@@QEAA@AEAY0CH@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[39])
0x18002c6cd  lea     rdx, [rsp+100h+var_D8]
0x18002c6d2  mov     rcx, [rax]
0x18002c6d5  call    ??$ActivateInstance@V?$ComPtr@UIFileOpenPicker@Pickers@Storage@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIFileOpenPicker@Pickers@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Storage::Pickers::IFileOpenPicker>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Pickers::IFileOpenPicker>>)
0x18002c6da  mov     ebx, eax
0x18002c6dc  test    eax, eax
0x18002c6de  jns     short loc_18002C6E7
0x18002c6e0  mov     edx, 79Ch
0x18002c6e5  jmp     short loc_18002C70A
0x18002c6e7  mov     rcx, [rsp+100h+var_D8]
0x18002c6ec  mov     rax, [rcx]
0x18002c6ef  mov     edi, 1
0x18002c6f4  mov     edx, edi
0x18002c6f6  mov     rax, [rax+58h]
0x18002c6fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6ff  mov     ebx, eax
0x18002c701  test    eax, eax
0x18002c703  jns     short loc_18002C722
0x18002c705  mov     edx, 79Dh; void *
0x18002c70a  mov     rcx, [rbp+5Fh]; this
0x18002c70e  mov     r9d, eax; char *
0x18002c711  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002c718  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c71d  jmp     loc_18002C9C0
0x18002c722  mov     rcx, [rsp+100h+var_D8]
0x18002c727  mov     rax, [rcx]
0x18002c72a  mov     edx, edi
0x18002c72c  mov     rax, [rax+38h]
0x18002c730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c735  mov     ebx, eax
0x18002c737  test    eax, eax
0x18002c739  jns     short loc_18002C742
0x18002c73b  mov     edx, 79Eh
0x18002c740  jmp     short loc_18002C70A
0x18002c742  xor     ecx, ecx; string
0x18002c744  call    cs:__imp_WindowsDeleteString
0x18002c74a  mov     [rbp+57h+string], 0
0x18002c752  lea     rdx, [rbp+57h+string]; HSTRING *
0x18002c756  lea     rcx, aSystemsettings_18; "SystemSettings_Devices_Pen_DesktopAppPi"...
0x18002c75d  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18002c762  mov     ebx, eax
0x18002c764  test    eax, eax
0x18002c766  jns     short loc_18002C790
0x18002c768  mov     rcx, [rbp+5Fh]; this
0x18002c76c  mov     r9d, eax; char *
0x18002c76f  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002c776  mov     edx, 7A1h; void *
0x18002c77b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c780  nop
0x18002c781  mov     rcx, [rbp+57h+string]; string
0x18002c785  call    cs:__imp_WindowsDeleteString
0x18002c78b  jmp     loc_18002C9C0
0x18002c790  mov     rcx, [rsp+100h+var_D8]
0x18002c795  mov     rax, [rcx]
0x18002c798  mov     rbx, [rbp+57h+string]
0x18002c79c  mov     rdx, rbx
0x18002c79f  mov     rax, [rax+68h]
0x18002c7a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7a8  mov     edi, eax
0x18002c7aa  test    eax, eax
0x18002c7ac  jns     short loc_18002C7D7
0x18002c7ae  mov     rcx, [rbp+5Fh]; this
0x18002c7b2  mov     r9d, eax; char *
0x18002c7b5  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002c7bc  mov     edx, 7A2h; void *
0x18002c7c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c7c6  nop
0x18002c7c7  mov     rcx, rbx; string
0x18002c7ca  call    cs:__imp_WindowsDeleteString
0x18002c7d0  mov     ebx, edi
0x18002c7d2  jmp     loc_18002C9C0
0x18002c7d7  mov     qword ptr [rsp+100h+var_E0], 0; int
0x18002c7e0  lea     rdx, aExe; ".exe"
0x18002c7e7  lea     rcx, [rbp+57h+var_58]; string
0x18002c7eb  call    ??$?0$04@StringReference@Internal@Windows@@QEAA@AEAY04$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[5])
0x18002c7f0  mov     rsi, [rsp+100h+var_D8]
0x18002c7f5  mov     rax, [rsi]
0x18002c7f8  mov     rdi, [rax+70h]
0x18002c7fc  lea     rcx, [rsp+100h+var_E0]
0x18002c801  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c806  lea     rdx, [rsp+100h+var_E0]
0x18002c80b  mov     rcx, rsi
0x18002c80e  mov     rax, rdi
0x18002c811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c816  mov     edi, eax
0x18002c818  test    eax, eax
0x18002c81a  jns     short loc_18002C841
0x18002c81c  mov     edx, 7A5h; void *
0x18002c821  mov     rcx, [rbp+5Fh]; this
0x18002c825  mov     r9d, edi; char *
0x18002c828  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002c82f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c834  nop
0x18002c835  lea     rcx, [rsp+100h+var_E0]
0x18002c83a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c83f  jmp     short loc_18002C7C7
0x18002c841  mov     rcx, qword ptr [rsp+100h+var_E0]
0x18002c846  mov     rax, [rcx]
0x18002c849  mov     rdx, [rbp+57h+var_58]
0x18002c84d  mov     rax, [rax+68h]
0x18002c851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c856  mov     edi, eax
0x18002c858  test    eax, eax
0x18002c85a  jns     short loc_18002C863
0x18002c85c  mov     edx, 7A6h
0x18002c861  jmp     short loc_18002C821
0x18002c863  lea     rdx, aLnk; ".lnk"
0x18002c86a  lea     rcx, [rbp+57h+var_38]; string
0x18002c86e  call    ??$?0$04@StringReference@Internal@Windows@@QEAA@AEAY04$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[5])
0x18002c873  mov     rcx, qword ptr [rsp+100h+var_E0]
0x18002c878  mov     rax, [rcx]
0x18002c87b  mov     rdx, [rbp+57h+var_38]
0x18002c87f  mov     rax, [rax+68h]
0x18002c883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c888  mov     edi, eax
0x18002c88a  test    eax, eax
0x18002c88c  jns     short loc_18002C895
0x18002c88e  mov     edx, 7A8h
0x18002c893  jmp     short loc_18002C821
0x18002c895  mov     [rbp+57h+var_D0], 0
0x18002c89d  mov     rsi, [rsp+100h+var_D8]
0x18002c8a2  mov     rax, [rsi]
0x18002c8a5  mov     rdi, [rax+78h]
0x18002c8a9  lea     rcx, [rbp+57h+var_D0]
0x18002c8ad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c8b2  lea     rdx, [rbp+57h+var_D0]
0x18002c8b6  mov     rcx, rsi
0x18002c8b9  mov     rax, rdi
0x18002c8bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8c1  mov     edi, eax
0x18002c8c3  test    eax, eax
0x18002c8c5  jns     short loc_18002C8EE
0x18002c8c7  mov     rcx, [rbp+5Fh]; this
0x18002c8cb  mov     r9d, eax; char *
0x18002c8ce  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002c8d5  mov     edx, 7ABh; void *
0x18002c8da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c8df  nop
0x18002c8e0  lea     rcx, [rbp+57h+var_D0]
0x18002c8e4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c8e9  jmp     loc_18002C835
0x18002c8ee  mov     [rbp+57h+var_C0], r14
0x18002c8f2  lea     rcx, [rbp+57h+var_C0]
0x18002c8f6  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18002c8fb  nop
0x18002c8fc  mov     edi, [r14+110h]
0x18002c903  lea     rdx, [r14+138h]; struct wil::cloud_store *
0x18002c90a  lea     rcx, [rbp+57h+var_80]; this
0x18002c90e  call    ??0cloud_store@wil@@QEAA@AEBV01@@Z; wil::cloud_store::cloud_store(wil::cloud_store const &)
0x18002c913  nop
0x18002c914  mov     [rbp+57h+var_B8], r14
0x18002c918  lea     rcx, [rbp+57h+var_B8]
0x18002c91c  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18002c921  mov     [rbp+57h+var_B0], edi
0x18002c924  lea     rdx, [rbp+57h+var_80]; struct wil::cloud_store *
0x18002c928  lea     rcx, [rbp+57h+var_A8]; this
0x18002c92c  call    ??0cloud_store@wil@@QEAA@AEBV01@@Z; wil::cloud_store::cloud_store(wil::cloud_store const &)
0x18002c931  nop
0x18002c932  lea     rdx, [rbp+57h+var_B8]
0x18002c936  mov     rcx, [rbp+57h+var_D0]
0x18002c93a  call    StartOperationAndThenAgileCallback_Windows__Foundation__IAsyncOperationCompletedHandler_Windows__Storage__StorageFile____Windows__Foundation__IAsyncOperation_Windows__Storage__StorageFile_____lambda_5815450939de8374e7ffc211cc22f5ba___
0x18002c93f  mov     edi, eax
0x18002c941  lea     rcx, [rbp+57h+var_B8]
0x18002c945  call    _lambda_5815450939de8374e7ffc211cc22f5ba_____lambda_5815450939de8374e7ffc211cc22f5ba_
0x18002c94a  test    edi, edi
0x18002c94c  jns     short loc_18002C986
0x18002c94e  mov     rcx, [rbp+5Fh]; this
0x18002c952  mov     r9d, edi; char *
0x18002c955  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002c95c  mov     edx, 7E1h; void *
0x18002c961  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c966  nop
0x18002c967  lea     rcx, [rbp+57h+var_80]; this
0x18002c96b  call    ??1cloud_store@wil@@QEAA@XZ; wil::cloud_store::~cloud_store(void)
0x18002c970  nop
0x18002c971  mov     rax, [r14]
0x18002c974  mov     rcx, r14
0x18002c977  mov     rax, [rax+10h]
0x18002c97b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c980  nop
0x18002c981  jmp     loc_18002C8E0
0x18002c986  lea     rcx, [rbp+57h+var_80]; this
0x18002c98a  call    ??1cloud_store@wil@@QEAA@XZ; wil::cloud_store::~cloud_store(void)
0x18002c98f  nop
0x18002c990  mov     rax, [r14]
0x18002c993  mov     rcx, r14
0x18002c996  mov     rax, [rax+10h]
0x18002c99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c99f  nop
0x18002c9a0  lea     rcx, [rbp+57h+var_D0]
0x18002c9a4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c9a9  nop
0x18002c9aa  lea     rcx, [rsp+100h+var_E0]
0x18002c9af  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c9b4  nop
0x18002c9b5  mov     rcx, rbx; string
0x18002c9b8  call    cs:__imp_WindowsDeleteString
0x18002c9be  xor     ebx, ebx
0x18002c9c0  lea     rcx, [rsp+100h+var_D8]
0x18002c9c5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c9ca  mov     eax, ebx
0x18002c9cc  mov     rcx, [rbp+57h+var_18]
0x18002c9d0  xor     rcx, rsp; StackCookie
0x18002c9d3  call    __security_check_cookie
0x18002c9d8  lea     r11, [rsp+100h+var_10]
0x18002c9e0  mov     rbx, [r11+28h]
0x18002c9e4  mov     rsi, [r11+30h]
0x18002c9e8  mov     rsp, r11
0x18002c9eb  pop     r14
0x18002c9ed  pop     rdi
0x18002c9ee  pop     rbp
0x18002c9ef  retn
```
