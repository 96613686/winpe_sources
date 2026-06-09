# Windows::Management::Provisioning::PackageManagerServer::QueueApplicationForDownload(_GUID,HSTRING__ * *,int *,int *)

- ea: `0x180077f20`
- end: `0x180078679`
- name: `?QueueApplicationForDownload@PackageManagerServer@Provisioning@Management@Windows@@UEAAJU_GUID@@PEAPEAUHSTRING__@@PEAH2@Z`
- size: `1881`
- prototype: `int(Windows::Management::Provisioning::PackageManagerServer *__hidden this, struct _GUID *__struct_ptr, HSTRING *, int *, int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004eb0`
- `0x180005a74`
- `0x180009be4`
- `0x18000a5c4`
- `0x18000ac30`
- `0x180017ed0`
- `0x180075d60`
- `0x180075dd0`
- `0x180076644`
- `0x1800767dc`
- `0x180077f20`
- `0x18007c090`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180078476`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180078476`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007843c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800784b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078521`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007843c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800784b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078521`

## string_xrefs

- `0x18007812d`: `Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall Windows::Management::Provisioning::PackageManagerServer::QueueApplicationForDownload(
        Windows::Management::Provisioning::PackageManagerServer *this,
        struct _GUID *a2,
        HSTRING *a3,
        int *a4,
        int *a5)
{
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v16)(_QWORD, GUID *, __int64 *); // rdi
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64, __int64); // rbx
  __int64 v21; // rax
  __int64 v22; // r9
  int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // rdi
  int v26; // ebx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, _QWORD, __int64, _QWORD); // rbx
  __int64 v29; // rax
  int v30; // eax
  unsigned int v31; // ebx
  __int64 v32; // rdi
  int v33; // ebx
  __int64 v34; // rdi
  int (__fastcall *v35)(__int64, HSTRING *); // rbx
  HRESULT v36; // eax
  unsigned int v37; // ebx
  int v38; // [rsp+20h] [rbp-148h]
  int Data2; // [rsp+20h] [rbp-148h]
  int *v40; // [rsp+20h] [rbp-148h]
  __int64 v41; // [rsp+70h] [rbp-F8h] BYREF
  __int64 (__fastcall ***v42)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp-F0h] BYREF
  int v43; // [rsp+80h] [rbp-E8h] BYREF
  int v44[2]; // [rsp+88h] [rbp-E0h] BYREF
  HSTRING string; // [rsp+90h] [rbp-D8h] BYREF
  __int64 v46; // [rsp+98h] [rbp-D0h] BYREF
  __int64 v47; // [rsp+A0h] [rbp-C8h] BYREF
  __int64 v48; // [rsp+A8h] [rbp-C0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-B8h] BYREF
  __int64 v50; // [rsp+C8h] [rbp-A0h]
  WCHAR sourceString[40]; // [rsp+D0h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  if ( a3 )
  {
    if ( a4 )
    {
      if ( a5 )
      {
        v43 = 0;
        v9 = SecurityCheck(&v43);
        v10 = v9;
        if ( v9 >= 0 )
        {
          if ( v43 )
          {
            *a3 = 0;
            *a4 = 1;
            *a5 = 1;
            memset_0(sourceString, 0, 0x4Au);
            Data2 = a2->Data2;
            v11 = StringCchPrintfW(sourceString, 0x25u, L"%08lX-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X", a2->Data1);
            v12 = v11;
            if ( v11 >= 0 )
            {
              v42 = 0;
              v50 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                &hstringHeader,
                L"Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager",
                0x48u,
                0x47u);
              v13 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>(
                      v50,
                      &v42);
              v14 = v13;
              if ( v13 >= 0 )
              {
                v41 = 0;
                v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v42;
                v16 = **v42;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
                v17 = v16(v15, &GUID_57b15f7a_3367_48f6_bb71_bacba1331a6e, &v41);
                v18 = v17;
                if ( v17 >= 0 )
                {
                  *(_QWORD *)v44 = 0;
                  v19 = v41;
                  v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v41 + 56LL);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v44);
                  v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString);
                  v40 = v44;
                  LOBYTE(v22) = 1;
                  v23 = v20(v19, *(_QWORD *)(v21 + 24), 3, v22);
                  v24 = v23;
                  if ( v23 >= 0 )
                  {
                    v47 = 0;
                    v25 = *(_QWORD *)v44;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                    v26 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>>(v25);
                    if ( v26 < 0
                      || (v26 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 64LL))(v25, &v47),
                          v26 < 0) )
                    {
                      if ( v26 == -2147024894 || v26 == -2147023728 )
                      {
                        *a4 = 0;
                      }
                      else if ( v26 == -2147024891 )
                      {
                        *a5 = 0;
                      }
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v44);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
                      return (unsigned int)v26;
                    }
                    else
                    {
                      v46 = 0;
                      v27 = v41;
                      v28 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v41 + 72LL);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                      v29 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString);
                      LOBYTE(v40) = 0;
                      v30 = v28(v27, *(_QWORD *)(v29 + 24), 3, 0);
                      v31 = v30;
                      if ( v30 >= 0 )
                      {
                        v48 = 0;
                        v32 = v46;
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                        v33 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>>(v32);
                        if ( v33 < 0
                          || (v33 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 64LL))(v32, &v48),
                              v33 < 0) )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x26A,
                            (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
                            (const char *)(unsigned int)v33,
                            (int)v40);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v44);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
                          return (unsigned int)v33;
                        }
                        else
                        {
                          string = 0;
                          v34 = v48;
                          v35 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v48 + 48LL);
                          WindowsDeleteString(0);
                          string = 0;
                          if ( v35(v34, &string) < 0 || (v36 = WindowsDuplicateString(string, a3), v37 = v36, v36 >= 0) )
                          {
                            WindowsDeleteString(string);
                            string = 0;
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v44);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
                            return 0;
                          }
                          else
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x279,
                              (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
                              (const char *)(unsigned int)v36,
                              (int)v40);
                            WindowsDeleteString(string);
                            string = 0;
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v44);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
                            return v37;
                          }
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x263,
                          (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
                          (const char *)(unsigned int)v30,
                          (int)v40);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v44);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
                        return v31;
                      }
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x23C,
                      (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
                      (const char *)(unsigned int)v23,
                      (int)v44);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v44);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
                    return v24;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x234,
                    (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
                    (const char *)(unsigned int)v17,
                    Data2);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
                  return v18;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x231,
                  (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
                  (const char *)(unsigned int)v13,
                  Data2);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
                return v14;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x22B,
                (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
                (const char *)(unsigned int)v11,
                Data2);
              return v12;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x222,
              (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
              (const char *)0x80070005LL,
              v38);
            return 2147942405LL;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x221,
            (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
            (const char *)(unsigned int)v9,
            v38);
          return v10;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21E,
          (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
          (const char *)0x80004003LL,
          v38);
        return 2147500035LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21D,
        (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
        (const char *)0x80004003LL,
        v38);
      return 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21C,
      (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
      (const char *)0x80004003LL,
      v38);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180077f20  push    rbx
0x180077f22  push    rsi
0x180077f23  push    rdi
0x180077f24  push    r12
0x180077f26  push    r13
0x180077f28  push    r14
0x180077f2a  push    r15
0x180077f2c  sub     rsp, 130h
0x180077f33  mov     rax, cs:__security_cookie
0x180077f3a  xor     rax, rsp
0x180077f3d  mov     [rsp+168h+var_48], rax
0x180077f45  mov     r15, r9
0x180077f48  mov     r13, r8
0x180077f4b  mov     r14, rdx
0x180077f4e  mov     r12, [rsp+168h+arg_20]
0x180077f56  xor     edi, edi
0x180077f58  test    r8, r8
0x180077f5b  jnz     short loc_180077F85
0x180077f5d  mov     rcx, [rsp+168h]; this
0x180077f65  mov     ebx, 80004003h
0x180077f6a  mov     r9d, ebx; char *
0x180077f6d  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180077f74  mov     edx, 21Ch; void *
0x180077f79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077f7e  mov     eax, ebx
0x180077f80  jmp     loc_180078655
0x180077f85  test    r15, r15
0x180077f88  jnz     short loc_180077FB2
0x180077f8a  mov     rcx, [rsp+168h]; this
0x180077f92  mov     ebx, 80004003h
0x180077f97  mov     r9d, ebx; char *
0x180077f9a  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180077fa1  mov     edx, 21Dh; void *
0x180077fa6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077fab  mov     eax, ebx
0x180077fad  jmp     loc_180078655
0x180077fb2  test    r12, r12
0x180077fb5  jnz     short loc_180077FDF
0x180077fb7  mov     rcx, [rsp+168h]; this
0x180077fbf  mov     ebx, 80004003h
0x180077fc4  mov     r9d, ebx; char *
0x180077fc7  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180077fce  mov     edx, 21Eh; void *
0x180077fd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077fd8  mov     eax, ebx
0x180077fda  jmp     loc_180078655
0x180077fdf  mov     [rsp+168h+var_E8], edi
0x180077fe6  lea     rcx, [rsp+168h+var_E8]; int *
0x180077fee  call    ?SecurityCheck@@YAJPEAH@Z; SecurityCheck(int *)
0x180077ff3  mov     ebx, eax
0x180077ff5  test    eax, eax
0x180077ff7  jns     short loc_18007801C
0x180077ff9  mov     rcx, [rsp+168h]; this
0x180078001  mov     r9d, eax; char *
0x180078004  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007800b  mov     edx, 221h; void *
0x180078010  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078015  mov     eax, ebx
0x180078017  jmp     loc_180078655
0x18007801c  cmp     [rsp+168h+var_E8], edi
0x180078023  jnz     short loc_18007804E
0x180078025  mov     rcx, [rsp+168h]; this
0x18007802d  mov     r9d, 80070005h; char *
0x180078033  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007803a  mov     edx, 222h; void *
0x18007803f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078044  mov     eax, 80070005h
0x180078049  jmp     loc_180078655
0x18007804e  mov     [r13+0], rdi
0x180078052  mov     eax, 1
0x180078057  mov     [r15], eax
0x18007805a  mov     [r12], eax
0x18007805e  xor     edx, edx; Val
0x180078060  lea     r8d, [rax+49h]; Size
0x180078064  lea     rcx, [rsp+168h+sourceString]; void *
0x18007806c  call    memset_0
0x180078071  movzx   eax, byte ptr [r14+0Fh]
0x180078076  movzx   ecx, byte ptr [r14+0Eh]
0x18007807b  movzx   edx, byte ptr [r14+0Dh]
0x180078080  movzx   r8d, byte ptr [r14+0Ch]
0x180078085  movzx   r9d, byte ptr [r14+0Bh]
0x18007808a  movzx   r10d, byte ptr [r14+0Ah]
0x18007808f  movzx   r11d, byte ptr [r14+9]
0x180078094  movzx   ebx, byte ptr [r14+8]
0x180078099  movzx   edi, word ptr [r14+6]
0x18007809e  movzx   esi, word ptr [r14+4]
0x1800780a3  mov     [rsp+168h+var_100], eax
0x1800780a7  mov     [rsp+168h+var_108], ecx
0x1800780ab  mov     [rsp+168h+var_110], edx
0x1800780af  mov     dword ptr [rsp+168h+var_118], r8d
0x1800780b4  mov     dword ptr [rsp+168h+var_120], r9d
0x1800780b9  mov     dword ptr [rsp+168h+var_128], r10d
0x1800780be  mov     dword ptr [rsp+168h+var_130], r11d
0x1800780c3  mov     dword ptr [rsp+168h+var_138], ebx
0x1800780c7  mov     [rsp+168h+var_140], edi
0x1800780cb  mov     [rsp+168h+var_148], esi; int
0x1800780cf  mov     r9d, [r14]
0x1800780d2  lea     r8, a08lx04x04x02x0; "%08lX-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x1800780d9  mov     edx, 25h ; '%'; unsigned __int64
0x1800780de  lea     rcx, [rsp+168h+sourceString]; unsigned __int16 *
0x1800780e6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800780eb  mov     ebx, eax
0x1800780ed  xor     esi, esi
0x1800780ef  test    eax, eax
0x1800780f1  jns     short loc_180078116
0x1800780f3  mov     rcx, [rsp+168h]; this
0x1800780fb  mov     r9d, eax; char *
0x1800780fe  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180078105  mov     edx, 22Bh; void *
0x18007810a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007810f  mov     eax, ebx
0x180078111  jmp     loc_180078655
0x180078116  mov     [rsp+168h+var_F0], rsi
0x18007811b  mov     [rsp+168h+var_A0], rsi
0x180078123  mov     r9d, 47h ; 'G'; unsigned int
0x180078129  lea     r8d, [r9+1]; unsigned int
0x18007812d  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Store_Preview_InstallControl_AppInstallManager@@3QBGB; "Windows.ApplicationModel.Store.Preview."...
0x180078134  lea     rcx, [rsp+168h+hstringHeader]; hstringHeader
0x18007813c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180078141  lea     rdx, [rsp+168h+var_F0]
0x180078146  mov     rcx, [rsp+168h+var_A0]
0x18007814e  call    ??$ActivateInstance@V?$ComPtr@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>)
0x180078153  mov     ebx, eax
0x180078155  test    eax, eax
0x180078157  jns     short loc_180078187
0x180078159  mov     rcx, [rsp+168h]; this
0x180078161  mov     r9d, eax; char *
0x180078164  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007816b  mov     edx, 231h; void *
0x180078170  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078175  nop
0x180078176  lea     rcx, [rsp+168h+var_F0]
0x18007817b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180078180  mov     eax, ebx
0x180078182  jmp     loc_180078655
0x180078187  mov     [rsp+168h+var_F8], rsi
0x18007818c  mov     rbx, [rsp+168h+var_F0]
0x180078191  mov     rax, [rbx]
0x180078194  mov     rdi, [rax]
0x180078197  lea     rcx, [rsp+168h+var_F8]
0x18007819c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800781a1  lea     r8, [rsp+168h+var_F8]
0x1800781a6  lea     rdx, _GUID_57b15f7a_3367_48f6_bb71_bacba1331a6e
0x1800781ad  mov     rcx, rbx
0x1800781b0  mov     rax, rdi
0x1800781b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800781b8  mov     ebx, eax
0x1800781ba  test    eax, eax
0x1800781bc  jns     short loc_1800781F7
0x1800781be  mov     rcx, [rsp+168h]; this
0x1800781c6  mov     r9d, eax; char *
0x1800781c9  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x1800781d0  mov     edx, 234h; void *
0x1800781d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800781da  nop
0x1800781db  lea     rcx, [rsp+168h+var_F8]
0x1800781e0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800781e5  nop
0x1800781e6  lea     rcx, [rsp+168h+var_F0]
0x1800781eb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800781f0  mov     eax, ebx
0x1800781f2  jmp     loc_180078655
0x1800781f7  mov     qword ptr [rsp+168h+var_E0], rsi
0x1800781ff  mov     rdi, [rsp+168h+var_F8]
0x180078204  mov     rax, [rdi]
0x180078207  mov     rbx, [rax+38h]
0x18007820b  lea     rcx, [rsp+168h+var_E0]
0x180078213  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180078218  lea     rdx, [rsp+168h+sourceString]; sourceString
0x180078220  lea     rcx, [rsp+168h+hstringHeader]; hstringHeader
0x180078228  call    ??$?0$0CF@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0CF@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[37])
0x18007822d  nop
0x18007822e  lea     rcx, [rsp+168h+var_E0]
0x180078236  mov     qword ptr [rsp+168h+var_148], rcx; int
0x18007823b  mov     r9b, 1
0x18007823e  mov     r14d, 3
0x180078244  mov     r8d, r14d
0x180078247  mov     rdx, [rax+18h]
0x18007824b  mov     rcx, rdi
0x18007824e  mov     rax, rbx
0x180078251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078256  mov     ebx, eax
0x180078258  test    eax, eax
0x18007825a  jns     short loc_1800782A3
0x18007825c  mov     rcx, [rsp+168h]; this
0x180078264  mov     r9d, eax; char *
0x180078267  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007826e  mov     edx, 23Ch; void *
0x180078273  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078278  nop
0x180078279  lea     rcx, [rsp+168h+var_E0]
0x180078281  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180078286  nop
0x180078287  lea     rcx, [rsp+168h+var_F8]
0x18007828c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180078291  nop
0x180078292  lea     rcx, [rsp+168h+var_F0]
0x180078297  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007829c  mov     eax, ebx
0x18007829e  jmp     loc_180078655
0x1800782a3  mov     [rsp+168h+var_C8], rsi
0x1800782ab  mov     rdi, qword ptr [rsp+168h+var_E0]
0x1800782b3  lea     rcx, [rsp+168h+var_C8]
0x1800782bb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800782c0  mov     rcx, rdi
0x1800782c3  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *,tagCOWAIT_FLAGS,void *)
0x1800782c8  mov     ebx, eax
0x1800782ca  test    eax, eax
0x1800782cc  js      loc_1800785F8
0x1800782d2  mov     rax, [rdi]
0x1800782d5  lea     rdx, [rsp+168h+var_C8]
0x1800782dd  mov     rcx, rdi
0x1800782e0  mov     rax, [rax+40h]
0x1800782e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800782e9  mov     ebx, eax
0x1800782eb  test    eax, eax
0x1800782ed  js      loc_1800785F8
0x1800782f3  mov     [rsp+168h+var_D0], rsi
0x1800782fb  mov     rdi, [rsp+168h+var_F8]
0x180078300  mov     rax, [rdi]
0x180078303  mov     rbx, [rax+48h]
0x180078307  lea     rcx, [rsp+168h+var_D0]
0x18007830f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180078314  lea     rdx, [rsp+168h+sourceString]; sourceString
0x18007831c  lea     rcx, [rsp+168h+hstringHeader]; hstringHeader
0x180078324  call    ??$?0$0CF@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0CF@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[37])
0x180078329  nop
0x18007832a  lea     rcx, [rsp+168h+var_D0]
0x180078332  mov     [rsp+168h+var_118], rcx
0x180078337  mov     [rsp+168h+var_120], rsi
0x18007833c  mov     [rsp+168h+var_128], rsi
0x180078341  mov     [rsp+168h+var_130], rsi
0x180078346  mov     [rsp+168h+var_138], rsi
0x18007834b  mov     byte ptr [rsp+168h+var_140], sil
0x180078350  mov     byte ptr [rsp+168h+var_148], sil; int
0x180078355  xor     r9d, r9d
0x180078358  mov     r8d, r14d
0x18007835b  mov     rdx, [rax+18h]
0x18007835f  mov     rcx, rdi
0x180078362  mov     rax, rbx
0x180078365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007836a  mov     ebx, eax
0x18007836c  test    eax, eax
0x18007836e  jns     short loc_1800783D3
0x180078370  mov     rcx, [rsp+168h]; this
0x180078378  mov     r9d, eax; char *
0x18007837b  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180078382  mov     edx, 263h; void *
0x180078387  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007838c  nop
0x18007838d  lea     rcx, [rsp+168h+var_D0]
0x180078395  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007839a  nop
0x18007839b  lea     rcx, [rsp+168h+var_C8]
0x1800783a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800783a8  nop
0x1800783a9  lea     rcx, [rsp+168h+var_E0]
0x1800783b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800783b6  nop
0x1800783b7  lea     rcx, [rsp+168h+var_F8]
0x1800783bc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800783c1  nop
0x1800783c2  lea     rcx, [rsp+168h+var_F0]
0x1800783c7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800783cc  mov     eax, ebx
0x1800783ce  jmp     loc_180078655
0x1800783d3  mov     [rsp+168h+var_C0], rsi
0x1800783db  mov     rdi, [rsp+168h+var_D0]
0x1800783e3  lea     rcx, [rsp+168h+var_C0]
0x1800783eb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800783f0  mov     rcx, rdi
0x1800783f3  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *,tagCOWAIT_FLAGS,void *)
0x1800783f8  mov     ebx, eax
0x1800783fa  test    eax, eax
0x1800783fc  js      loc_18007858A
0x180078402  mov     rax, [rdi]
0x180078405  lea     rdx, [rsp+168h+var_C0]
0x18007840d  mov     rcx, rdi
0x180078410  mov     rax, [rax+40h]
0x180078414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078419  mov     ebx, eax
0x18007841b  test    eax, eax
0x18007841d  js      loc_18007858A
0x180078423  mov     [rsp+168h+string], rsi
0x18007842b  mov     rdi, [rsp+168h+var_C0]
0x180078433  mov     rax, [rdi]
0x180078436  mov     rbx, [rax+30h]
0x18007843a  xor     ecx, ecx; string
0x18007843c  call    cs:__imp_WindowsDeleteString
0x180078443  nop     dword ptr [rax+rax+00h]
0x180078448  mov     [rsp+168h+string], rsi
0x180078450  lea     rdx, [rsp+168h+string]
0x180078458  mov     rcx, rdi
0x18007845b  mov     rax, rbx
0x18007845e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078463  test    eax, eax
0x180078465  js      loc_180078519
0x18007846b  mov     rdx, r13; newString
0x18007846e  mov     rcx, [rsp+168h+string]; string
0x180078476  call    cs:__imp_WindowsDuplicateString
  ... truncated ...
```
