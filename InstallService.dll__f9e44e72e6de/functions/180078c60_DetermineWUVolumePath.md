# _DetermineWUVolumePath

- ea: `0x180078c60`
- end: `0x1800790d8`
- name: `_DetermineWUVolumePath`
- size: `1144`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180073690`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x18001c414`
- `0x1800252e8`
- `0x18002c310`
- `0x18006f5f8`
- `0x180070488`
- `0x180078c60`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078e8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078fbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800790ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078e8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078fbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800790ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078d56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078dc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078d56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078dc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180078d13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180079074`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180078d13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180079074`

## string_xrefs

- `0x180078dfc`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180079022`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180078df5`: `_DetermineWUVolumePath`
- `0x180079015`: `_DetermineWUVolumePath`
- `0x180078dd6`: `Volume path "%s" is not a system volume, but system volume is required; install will be redirected to a system volume.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall DetermineWUVolumePath(HSTRING string, char a2, HSTRING *a3)
{
  int v5; // ebx
  __int64 (__fastcall ***v6)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING, __int64 *); // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v15)(_QWORD, GUID *, __int64 *); // rbx
  HSTRING v16; // rdi
  unsigned int i; // esi
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD, __int64 *); // rbx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rbx
  HSTRING v22; // rcx
  HSTRING v23; // rax
  PCWSTR v25; // [rsp+40h] [rbp-49h]
  PCWSTR StringRawBuffer; // [rsp+40h] [rbp-49h]
  _BYTE v27[8]; // [rsp+50h] [rbp-39h] BYREF
  HSTRING stringa; // [rsp+58h] [rbp-31h] BYREF
  __int64 v29; // [rsp+60h] [rbp-29h] BYREF
  HSTRING v30; // [rsp+68h] [rbp-21h] BYREF
  unsigned int v31; // [rsp+70h] [rbp-19h] BYREF
  __int64 v32; // [rsp+78h] [rbp-11h] BYREF
  __int64 v33; // [rsp+80h] [rbp-9h] BYREF
  __int64 v34; // [rsp+88h] [rbp-1h] BYREF
  __int64 (__fastcall ***v35)(_QWORD, GUID *, __int64 *); // [rsp+90h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v37; // [rsp+B0h] [rbp+27h]

  v30 = string;
  *a3 = 0;
  stringa = 0;
  if ( a2 )
  {
    v35 = 0;
    v34 = 0;
    v37 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Management.Deployment.PackageManager",
      0x2Du,
      0x2Cu);
    v5 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager4>>(
           v37,
           &v35);
    if ( v5 >= 0 )
    {
      v6 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
      v7 = **v35;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
      v5 = v7(v6, &GUID_daad9948_36f1_41a7_9188_bc263e0dcb72, &v34);
      if ( v5 >= 0 )
      {
        if ( WindowsIsStringEmpty(string) )
          goto LABEL_12;
        v29 = 0;
        v8 = v34;
        v9 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v34 + 80LL);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v29);
        v5 = v9(v8, string, &v29);
        if ( v5 >= 0 )
        {
          v27[0] = 0;
          v5 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v29 + 56LL))(v29, v27);
          if ( v5 >= 0 )
          {
            if ( v27[0] )
            {
              v5 = Microsoft::WRL::Wrappers::HString::Set(&stringa, &v30);
            }
            else
            {
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              LogMessage(
                2u,
                "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                0x1CFu,
                "_DetermineWUVolumePath",
                -1,
                L"Volume path \"%s\" is not a system volume, but system volume is required; install will be redirected to "
                 "a system volume.",
                0,
                0,
                StringRawBuffer);
            }
          }
        }
        else
        {
          v25 = WindowsGetStringRawBuffer(string, 0);
          LogMessage(
            1u,
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
            0x1C1u,
            "_DetermineWUVolumePath",
            v5,
            L"FindPackageVolumeByName FAILED for \"%s\"",
            0,
            0,
            v25);
        }
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v29);
        if ( v5 >= 0 )
        {
LABEL_12:
          if ( !stringa )
          {
            v29 = 0;
            v10 = v34;
            v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 96LL);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v29);
            v5 = v11(v10, &v29);
            if ( v5 >= 0 )
            {
              v27[0] = 0;
              v5 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v29 + 56LL))(v29, v27);
              if ( v5 >= 0 )
              {
                if ( !v27[0]
                  || (v12 = v29,
                      v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 72LL),
                      WindowsDeleteString(stringa),
                      stringa = 0,
                      v5 = v13(v12, &stringa),
                      v5 >= 0) )
                {
                  if ( !stringa )
                  {
                    v30 = 0;
                    v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
                    v15 = (*v35)[6];
                    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v30);
                    v5 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), HSTRING *))v15)(
                           v14,
                           &v30);
                    if ( v5 >= 0 )
                    {
                      v33 = 0;
                      v16 = v30;
                      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v33);
                      v5 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Management::Deployment::PackageVolume *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Management::Deployment::PackageVolume *> *>>(v16);
                      if ( v5 >= 0 )
                      {
                        v5 = (*(__int64 (__fastcall **)(HSTRING, __int64 *))(*(_QWORD *)v16 + 64LL))(v16, &v33);
                        if ( v5 >= 0 )
                        {
                          v32 = 0;
                          v31 = 0;
                          v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v33 + 56LL))(v33, &v31);
                          v27[0] = 0;
                          for ( i = 0; v5 >= 0 && i < v31; ++i )
                          {
                            v18 = v33;
                            v19 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v33 + 48LL);
                            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
                            v5 = v19(v18, i, &v32);
                            if ( v5 >= 0 )
                            {
                              v27[0] = 0;
                              v5 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v32 + 56LL))(v32, v27);
                              if ( v5 >= 0 )
                              {
                                if ( v27[0] )
                                {
                                  v20 = v32;
                                  v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 72LL);
                                  WindowsDeleteString(stringa);
                                  stringa = 0;
                                  v5 = v21(v20, &stringa);
                                  break;
                                }
                              }
                            }
                          }
                          if ( !v27[0] )
                            LogMessage(
                              1u,
                              "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                              0x204u,
                              "_DetermineWUVolumePath",
                              -1,
                              L"Assert (%s): %s",
                              0,
                              0,
                              L"isSystemVol != 0",
                              L"Failed");
                          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
                        }
                      }
                      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v33);
                    }
                    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v30);
                  }
                }
              }
            }
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v29);
          }
        }
      }
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
  }
  else
  {
    v5 = 0;
    if ( WindowsIsStringEmpty(string) )
      goto LABEL_40;
    v5 = Microsoft::WRL::Wrappers::HString::Set(&stringa, &v30);
  }
  if ( v5 < 0 )
  {
    v22 = stringa;
    goto LABEL_42;
  }
LABEL_40:
  v22 = stringa;
  if ( stringa )
  {
    v23 = stringa;
    v22 = 0;
    stringa = 0;
    *a3 = v23;
  }
LABEL_42:
  WindowsDeleteString(v22);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180078c60  mov     [rsp-8+arg_8], rbx
0x180078c65  push    rbp
0x180078c66  push    rsi
0x180078c67  push    rdi
0x180078c68  push    r14
0x180078c6a  push    r15
0x180078c6c  lea     rbp, [rsp-37h]
0x180078c71  sub     rsp, 0C0h
0x180078c78  mov     rax, cs:__security_cookie
0x180078c7f  xor     rax, rsp
0x180078c82  mov     [rbp+57h+var_28], rax
0x180078c86  mov     r14, r8
0x180078c89  mov     rsi, rcx
0x180078c8c  mov     [rbp+57h+var_78], rcx
0x180078c90  xor     r15d, r15d
0x180078c93  mov     [r8], r15
0x180078c96  mov     [rbp+57h+string], r15
0x180078c9a  test    dl, dl
0x180078c9c  jz      loc_180079071
0x180078ca2  mov     [rbp+57h+var_50], r15
0x180078ca6  mov     [rbp+57h+var_58], r15
0x180078caa  mov     [rbp+57h+var_30], r15
0x180078cae  lea     r9d, [r15+2Ch]; unsigned int
0x180078cb2  lea     r8d, [r15+2Dh]; unsigned int
0x180078cb6  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x180078cbd  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180078cc1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180078cc6  lea     rdx, [rbp+57h+var_50]
0x180078cca  mov     rcx, [rbp+57h+var_30]
0x180078cce  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager4@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager4@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager4>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager4>>)
0x180078cd3  mov     ebx, eax
0x180078cd5  test    eax, eax
0x180078cd7  js      loc_18007905C
0x180078cdd  mov     rbx, [rbp+57h+var_50]
0x180078ce1  mov     rax, [rbx]
0x180078ce4  mov     rdi, [rax]
0x180078ce7  lea     rcx, [rbp+57h+var_58]
0x180078ceb  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180078cf0  lea     r8, [rbp+57h+var_58]
0x180078cf4  lea     rdx, _GUID_daad9948_36f1_41a7_9188_bc263e0dcb72
0x180078cfb  mov     rcx, rbx
0x180078cfe  mov     rax, rdi
0x180078d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078d06  mov     ebx, eax
0x180078d08  test    eax, eax
0x180078d0a  js      loc_18007905C
0x180078d10  mov     rcx, rsi; string
0x180078d13  call    cs:__imp_WindowsIsStringEmpty
0x180078d19  test    eax, eax
0x180078d1b  jnz     loc_180078E1A
0x180078d21  mov     [rbp+57h+var_80], r15
0x180078d25  mov     rdi, [rbp+57h+var_58]
0x180078d29  mov     rax, [rdi]
0x180078d2c  mov     rbx, [rax+50h]
0x180078d30  lea     rcx, [rbp+57h+var_80]
0x180078d34  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180078d39  lea     r8, [rbp+57h+var_80]
0x180078d3d  mov     rdx, rsi
0x180078d40  mov     rcx, rdi
0x180078d43  mov     rax, rbx
0x180078d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078d4b  mov     ebx, eax
0x180078d4d  test    eax, eax
0x180078d4f  jns     short loc_180078D87
0x180078d51  xor     edx, edx; length
0x180078d53  mov     rcx, rsi; string
0x180078d56  call    cs:__imp_WindowsGetStringRawBuffer
0x180078d5c  mov     [rsp+0E0h+var_A0], rax
0x180078d61  mov     [rsp+0E0h+var_A8], r15
0x180078d66  mov     [rsp+0E0h+var_B0], r15
0x180078d6b  lea     rax, aFindpackagevol; "FindPackageVolumeByName FAILED for \"%s"...
0x180078d72  mov     [rsp+0E0h+var_B8], rax
0x180078d77  mov     [rsp+0E0h+var_C0], ebx
0x180078d7b  mov     r8d, 1C1h
0x180078d81  lea     ecx, [r15+1]
0x180078d85  jmp     short loc_180078DF5
0x180078d87  mov     [rbp+57h+var_90], r15b
0x180078d8b  mov     rcx, [rbp+57h+var_80]
0x180078d8f  mov     rax, [rcx]
0x180078d92  lea     rdx, [rbp+57h+var_90]
0x180078d96  mov     rax, [rax+38h]
0x180078d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078d9f  mov     ebx, eax
0x180078da1  test    eax, eax
0x180078da3  js      short loc_180078E09
0x180078da5  cmp     [rbp+57h+var_90], r15b
0x180078da9  jz      short loc_180078DBC
0x180078dab  lea     rdx, [rbp+57h+var_78]; HSTRING *
0x180078daf  lea     rcx, [rbp+57h+string]; newString
0x180078db3  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180078db8  mov     ebx, eax
0x180078dba  jmp     short loc_180078E09
0x180078dbc  xor     edx, edx; length
0x180078dbe  mov     rcx, rsi; string
0x180078dc1  call    cs:__imp_WindowsGetStringRawBuffer
0x180078dc7  mov     [rsp+0E0h+var_A0], rax
0x180078dcc  mov     [rsp+0E0h+var_A8], r15; unsigned __int16 *
0x180078dd1  mov     [rsp+0E0h+var_B0], r15; char *
0x180078dd6  lea     rax, aVolumePathSIsN; "Volume path \"%s\" is not a system volu"...
0x180078ddd  mov     [rsp+0E0h+var_B8], rax; unsigned __int16 *
0x180078de2  mov     [rsp+0E0h+var_C0], 0FFFFFFFFh; int
0x180078dea  mov     r8d, 1CFh; unsigned int
0x180078df0  mov     ecx, 2; unsigned int
0x180078df5  lea     r9, aDeterminewuvol; "_DetermineWUVolumePath"
0x180078dfc  lea     rdx, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x180078e03  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180078e08  nop
0x180078e09  lea     rcx, [rbp+57h+var_80]
0x180078e0d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180078e12  test    ebx, ebx
0x180078e14  js      loc_18007905C
0x180078e1a  cmp     [rbp+57h+string], r15
0x180078e1e  jnz     loc_18007905C
0x180078e24  mov     [rbp+57h+var_80], r15
0x180078e28  mov     rdi, [rbp+57h+var_58]
0x180078e2c  mov     rax, [rdi]
0x180078e2f  mov     rbx, [rax+60h]
0x180078e33  lea     rcx, [rbp+57h+var_80]
0x180078e37  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180078e3c  lea     rdx, [rbp+57h+var_80]
0x180078e40  mov     rcx, rdi
0x180078e43  mov     rax, rbx
0x180078e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078e4b  mov     ebx, eax
0x180078e4d  test    eax, eax
0x180078e4f  js      loc_180079052
0x180078e55  mov     [rbp+57h+var_90], r15b
0x180078e59  mov     rcx, [rbp+57h+var_80]
0x180078e5d  mov     rax, [rcx]
0x180078e60  lea     rdx, [rbp+57h+var_90]
0x180078e64  mov     rax, [rax+38h]
0x180078e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078e6d  mov     ebx, eax
0x180078e6f  test    eax, eax
0x180078e71  js      loc_180079052
0x180078e77  cmp     [rbp+57h+var_90], r15b
0x180078e7b  jz      short loc_180078EAF
0x180078e7d  mov     rdi, [rbp+57h+var_80]
0x180078e81  mov     rax, [rdi]
0x180078e84  mov     rbx, [rax+48h]
0x180078e88  mov     rcx, [rbp+57h+string]; string
0x180078e8c  call    cs:__imp_WindowsDeleteString
0x180078e92  mov     [rbp+57h+string], r15
0x180078e96  lea     rdx, [rbp+57h+string]
0x180078e9a  mov     rcx, rdi
0x180078e9d  mov     rax, rbx
0x180078ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078ea5  mov     ebx, eax
0x180078ea7  test    eax, eax
0x180078ea9  js      loc_180079052
0x180078eaf  cmp     [rbp+57h+string], r15
0x180078eb3  jnz     loc_180079052
0x180078eb9  mov     [rbp+57h+var_78], r15
0x180078ebd  mov     rdi, [rbp+57h+var_50]
0x180078ec1  mov     rax, [rdi]
0x180078ec4  mov     rbx, [rax+30h]
0x180078ec8  lea     rcx, [rbp+57h+var_78]
0x180078ecc  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180078ed1  lea     rdx, [rbp+57h+var_78]
0x180078ed5  mov     rcx, rdi
0x180078ed8  mov     rax, rbx
0x180078edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078ee0  mov     ebx, eax
0x180078ee2  test    eax, eax
0x180078ee4  js      loc_180079048
0x180078eea  mov     [rbp+57h+var_60], r15
0x180078eee  mov     rdi, [rbp+57h+var_78]
0x180078ef2  lea     rcx, [rbp+57h+var_60]
0x180078ef6  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180078efb  mov     rcx, rdi
0x180078efe  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVPackageVolume@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVPackageVolume@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVPackageVolume@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Management::Deployment::PackageVolume *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Management::Deployment::PackageVolume *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Management::Deployment::PackageVolume *> *> *,tagCOWAIT_FLAGS,void *)
0x180078f03  mov     ebx, eax
0x180078f05  test    eax, eax
0x180078f07  js      loc_18007903E
0x180078f0d  mov     rax, [rdi]
0x180078f10  lea     rdx, [rbp+57h+var_60]
0x180078f14  mov     rcx, rdi
0x180078f17  mov     rax, [rax+40h]
0x180078f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078f20  mov     ebx, eax
0x180078f22  test    eax, eax
0x180078f24  js      loc_18007903E
0x180078f2a  mov     [rbp+57h+var_68], r15
0x180078f2e  mov     [rbp+57h+var_70], r15d
0x180078f32  mov     rcx, [rbp+57h+var_60]
0x180078f36  mov     rax, [rcx]
0x180078f39  lea     rdx, [rbp+57h+var_70]
0x180078f3d  mov     rax, [rax+38h]
0x180078f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078f46  mov     ebx, eax
0x180078f48  mov     [rbp+57h+var_90], r15b
0x180078f4c  mov     esi, r15d
0x180078f4f  test    ebx, ebx
0x180078f51  js      loc_180078FD9
0x180078f57  cmp     esi, [rbp+57h+var_70]
0x180078f5a  jnb     short loc_180078FD9
0x180078f5c  mov     rdi, [rbp+57h+var_60]
0x180078f60  mov     rax, [rdi]
0x180078f63  mov     rbx, [rax+30h]
0x180078f67  lea     rcx, [rbp+57h+var_68]
0x180078f6b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180078f70  lea     r8, [rbp+57h+var_68]
0x180078f74  mov     edx, esi
0x180078f76  mov     rcx, rdi
0x180078f79  mov     rax, rbx
0x180078f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078f81  mov     ebx, eax
0x180078f83  test    eax, eax
0x180078f85  js      short loc_180078FAB
0x180078f87  mov     [rbp+57h+var_90], r15b
0x180078f8b  mov     rcx, [rbp+57h+var_68]
0x180078f8f  mov     rax, [rcx]
0x180078f92  lea     rdx, [rbp+57h+var_90]
0x180078f96  mov     rax, [rax+38h]
0x180078f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078f9f  mov     ebx, eax
0x180078fa1  test    eax, eax
0x180078fa3  js      short loc_180078FAB
0x180078fa5  cmp     [rbp+57h+var_90], r15b
0x180078fa9  jnz     short loc_180078FAF
0x180078fab  inc     esi
0x180078fad  jmp     short loc_180078F4F
0x180078faf  mov     rdi, [rbp+57h+var_68]
0x180078fb3  mov     rax, [rdi]
0x180078fb6  mov     rbx, [rax+48h]
0x180078fba  mov     rcx, [rbp+57h+string]; string
0x180078fbe  call    cs:__imp_WindowsDeleteString
0x180078fc4  mov     [rbp+57h+string], r15
0x180078fc8  lea     rdx, [rbp+57h+string]
0x180078fcc  mov     rcx, rdi
0x180078fcf  mov     rax, rbx
0x180078fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078fd7  mov     ebx, eax
0x180078fd9  cmp     [rbp+57h+var_90], r15b
0x180078fdd  jnz     short loc_180079034
0x180078fdf  lea     rax, aFailed_1; "Failed"
0x180078fe6  mov     [rsp+0E0h+var_98], rax
0x180078feb  lea     rax, aIssystemvol0; "isSystemVol != 0"
0x180078ff2  mov     [rsp+0E0h+var_A0], rax
0x180078ff7  mov     [rsp+0E0h+var_A8], r15; unsigned __int16 *
0x180078ffc  mov     [rsp+0E0h+var_B0], r15; char *
0x180079001  lea     rax, aAssertSS; "Assert (%s): %s"
0x180079008  mov     [rsp+0E0h+var_B8], rax; unsigned __int16 *
0x18007900d  mov     [rsp+0E0h+var_C0], 0FFFFFFFFh; int
0x180079015  lea     r9, aDeterminewuvol; "_DetermineWUVolumePath"
0x18007901c  mov     r8d, 204h; unsigned int
0x180079022  lea     rdx, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x180079029  mov     ecx, 1; unsigned int
0x18007902e  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180079033  nop
0x180079034  lea     rcx, [rbp+57h+var_68]
0x180079038  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007903d  nop
0x18007903e  lea     rcx, [rbp+57h+var_60]
0x180079042  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180079047  nop
0x180079048  lea     rcx, [rbp+57h+var_78]
0x18007904c  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180079051  nop
0x180079052  lea     rcx, [rbp+57h+var_80]
0x180079056  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007905b  nop
0x18007905c  lea     rcx, [rbp+57h+var_58]
0x180079060  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180079065  nop
0x180079066  lea     rcx, [rbp+57h+var_50]
0x18007906a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007906f  jmp     short loc_18007908D
0x180079071  mov     ebx, r15d
0x180079074  call    cs:__imp_WindowsIsStringEmpty
0x18007907a  test    eax, eax
0x18007907c  jnz     short loc_180079097
0x18007907e  lea     rdx, [rbp+57h+var_78]; HSTRING *
0x180079082  lea     rcx, [rbp+57h+string]; newString
0x180079086  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18007908b  mov     ebx, eax
0x18007908d  test    ebx, ebx
0x18007908f  jns     short loc_180079097
0x180079091  mov     rcx, [rbp+57h+string]
0x180079095  jmp     short loc_1800790AD
0x180079097  mov     rcx, [rbp+57h+string]
0x18007909b  test    rcx, rcx
0x18007909e  jz      short loc_1800790AD
0x1800790a0  mov     rax, rcx
0x1800790a3  mov     rcx, r15; string
0x1800790a6  mov     [rbp+57h+string], rcx
0x1800790aa  mov     [r14], rax
0x1800790ad  call    cs:__imp_WindowsDeleteString
0x1800790b3  mov     eax, ebx
0x1800790b5  mov     rcx, [rbp+57h+var_28]
0x1800790b9  xor     rcx, rsp; StackCookie
0x1800790bc  call    __security_check_cookie
0x1800790c1  mov     rbx, [rsp+0E0h+arg_8]
0x1800790c9  add     rsp, 0C0h
0x1800790d0  pop     r15
0x1800790d2  pop     r14
0x1800790d4  pop     rdi
0x1800790d5  pop     rsi
0x1800790d6  pop     rbp
0x1800790d7  retn
  ... truncated ...
```
