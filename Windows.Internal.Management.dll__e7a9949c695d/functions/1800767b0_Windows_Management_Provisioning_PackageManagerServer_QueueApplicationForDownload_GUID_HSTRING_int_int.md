# Windows::Management::Provisioning::PackageManagerServer::QueueApplicationForDownload(_GUID,HSTRING__ * *,int *,int *)

- ea: `0x1800767b0`
- end: `0x180076ef1`
- name: `?QueueApplicationForDownload@PackageManagerServer@Provisioning@Management@Windows@@UEAAJU_GUID@@PEAPEAUHSTRING__@@PEAH2@Z`
- size: `1857`
- prototype: `int(Windows::Management::Provisioning::PackageManagerServer *__hidden this, struct _GUID *__struct_ptr, HSTRING *, int *, int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004d50`
- `0x180005904`
- `0x18000992c`
- `0x18000a2a4`
- `0x18000a8e8`
- `0x1800176c4`
- `0x1800746ac`
- `0x180074720`
- `0x180074f74`
- `0x180075104`
- `0x1800767b0`
- `0x18007a7e4`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180076d00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180076d00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076ccc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076d35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076d9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076ccc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076d35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076d9f`

## string_xrefs

- `0x1800769bd`: `Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager`

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
  int (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // rdi
  HRESULT v26; // edx
  __int64 v27; // r8
  int v28; // ebx
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, _QWORD, __int64, _QWORD); // rbx
  __int64 v31; // rax
  int v32; // eax
  unsigned int v33; // ebx
  int (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // rdi
  HRESULT v35; // edx
  __int64 v36; // r8
  int v37; // ebx
  __int64 v38; // rdi
  int (__fastcall *v39)(__int64, HSTRING *); // rbx
  HRESULT v40; // eax
  unsigned int v41; // ebx
  int v42; // [rsp+20h] [rbp-148h]
  int Data2; // [rsp+20h] [rbp-148h]
  int *v44; // [rsp+20h] [rbp-148h]
  __int64 v45; // [rsp+70h] [rbp-F8h] BYREF
  __int64 (__fastcall ***v46)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp-F0h] BYREF
  int v47; // [rsp+80h] [rbp-E8h] BYREF
  int v48[2]; // [rsp+88h] [rbp-E0h] BYREF
  HSTRING string; // [rsp+90h] [rbp-D8h] BYREF
  int (__fastcall ***v50)(_QWORD, GUID *, __int64 *); // [rsp+98h] [rbp-D0h] BYREF
  __int64 v51; // [rsp+A0h] [rbp-C8h] BYREF
  __int64 v52; // [rsp+A8h] [rbp-C0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-B8h] BYREF
  __int64 v54; // [rsp+C8h] [rbp-A0h]
  WCHAR sourceString[40]; // [rsp+D0h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  if ( a3 )
  {
    if ( a4 )
    {
      if ( a5 )
      {
        v47 = 0;
        v9 = SecurityCheck(&v47);
        v10 = v9;
        if ( v9 >= 0 )
        {
          if ( v47 )
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
              v46 = 0;
              v54 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                &hstringHeader,
                L"Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager",
                0x48u,
                0x47u);
              v13 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>(
                      v54,
                      &v46);
              v14 = v13;
              if ( v13 >= 0 )
              {
                v45 = 0;
                v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v46;
                v16 = **v46;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                v17 = v16(v15, &GUID_57b15f7a_3367_48f6_bb71_bacba1331a6e, &v45);
                v18 = v17;
                if ( v17 >= 0 )
                {
                  *(_QWORD *)v48 = 0;
                  v19 = v45;
                  v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v45 + 56LL);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v48);
                  v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString);
                  v44 = v48;
                  LOBYTE(v22) = 1;
                  v23 = v20(v19, *(_QWORD *)(v21 + 24), 3, v22);
                  v24 = v23;
                  if ( v23 >= 0 )
                  {
                    v51 = 0;
                    v25 = *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))v48;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
                    v28 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>>(
                            v25,
                            v26,
                            v27);
                    if ( v28 < 0
                      || (v28 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v25)[8])(
                                  v25,
                                  &v51),
                          v28 < 0) )
                    {
                      if ( v28 == -2147024894 || v28 == -2147023728 )
                      {
                        *a4 = 0;
                      }
                      else if ( v28 == -2147024891 )
                      {
                        *a5 = 0;
                      }
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v48);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                      return (unsigned int)v28;
                    }
                    else
                    {
                      v50 = 0;
                      v29 = v45;
                      v30 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v45 + 72LL);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                      v31 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString);
                      LOBYTE(v44) = 0;
                      v32 = v30(v29, *(_QWORD *)(v31 + 24), 3, 0);
                      v33 = v32;
                      if ( v32 >= 0 )
                      {
                        v52 = 0;
                        v34 = v50;
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
                        v37 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>>(
                                v34,
                                v35,
                                v36);
                        if ( v37 < 0
                          || (v37 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v34)[8])(
                                      v34,
                                      &v52),
                              v37 < 0) )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x26A,
                            (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
                            (const char *)(unsigned int)v37,
                            (int)v44);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v48);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                          return (unsigned int)v37;
                        }
                        else
                        {
                          string = 0;
                          v38 = v52;
                          v39 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v52 + 48LL);
                          WindowsDeleteString(0);
                          string = 0;
                          if ( v39(v38, &string) < 0 || (v40 = WindowsDuplicateString(string, a3), v41 = v40, v40 >= 0) )
                          {
                            WindowsDeleteString(string);
                            string = 0;
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v48);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                            return 0;
                          }
                          else
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x279,
                              (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
                              (const char *)(unsigned int)v40,
                              (int)v44);
                            WindowsDeleteString(string);
                            string = 0;
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v48);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                            return v41;
                          }
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x263,
                          (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packagemanagerserver.cpp",
                          (const char *)(unsigned int)v32,
                          (int)v44);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v48);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                        return v33;
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
                      (int)v48);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v48);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
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
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
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
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
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
              v42);
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
            v42);
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
          v42);
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
        v42);
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
      v42);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800767b0  push    rbx
0x1800767b2  push    rsi
0x1800767b3  push    rdi
0x1800767b4  push    r12
0x1800767b6  push    r13
0x1800767b8  push    r14
0x1800767ba  push    r15
0x1800767bc  sub     rsp, 130h
0x1800767c3  mov     rax, cs:__security_cookie
0x1800767ca  xor     rax, rsp
0x1800767cd  mov     [rsp+168h+var_48], rax
0x1800767d5  mov     r15, r9
0x1800767d8  mov     r13, r8
0x1800767db  mov     r14, rdx
0x1800767de  mov     r12, [rsp+168h+arg_20]
0x1800767e6  xor     edi, edi
0x1800767e8  test    r8, r8
0x1800767eb  jnz     short loc_180076815
0x1800767ed  mov     rcx, [rsp+168h]; this
0x1800767f5  mov     ebx, 80004003h
0x1800767fa  mov     r9d, ebx; char *
0x1800767fd  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180076804  mov     edx, 21Ch; void *
0x180076809  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007680e  mov     eax, ebx
0x180076810  jmp     loc_180076ECD
0x180076815  test    r15, r15
0x180076818  jnz     short loc_180076842
0x18007681a  mov     rcx, [rsp+168h]; this
0x180076822  mov     ebx, 80004003h
0x180076827  mov     r9d, ebx; char *
0x18007682a  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180076831  mov     edx, 21Dh; void *
0x180076836  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007683b  mov     eax, ebx
0x18007683d  jmp     loc_180076ECD
0x180076842  test    r12, r12
0x180076845  jnz     short loc_18007686F
0x180076847  mov     rcx, [rsp+168h]; this
0x18007684f  mov     ebx, 80004003h
0x180076854  mov     r9d, ebx; char *
0x180076857  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007685e  mov     edx, 21Eh; void *
0x180076863  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076868  mov     eax, ebx
0x18007686a  jmp     loc_180076ECD
0x18007686f  mov     [rsp+168h+var_E8], edi
0x180076876  lea     rcx, [rsp+168h+var_E8]; int *
0x18007687e  call    ?SecurityCheck@@YAJPEAH@Z; SecurityCheck(int *)
0x180076883  mov     ebx, eax
0x180076885  test    eax, eax
0x180076887  jns     short loc_1800768AC
0x180076889  mov     rcx, [rsp+168h]; this
0x180076891  mov     r9d, eax; char *
0x180076894  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007689b  mov     edx, 221h; void *
0x1800768a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800768a5  mov     eax, ebx
0x1800768a7  jmp     loc_180076ECD
0x1800768ac  cmp     [rsp+168h+var_E8], edi
0x1800768b3  jnz     short loc_1800768DE
0x1800768b5  mov     rcx, [rsp+168h]; this
0x1800768bd  mov     r9d, 80070005h; char *
0x1800768c3  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x1800768ca  mov     edx, 222h; void *
0x1800768cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800768d4  mov     eax, 80070005h
0x1800768d9  jmp     loc_180076ECD
0x1800768de  mov     [r13+0], rdi
0x1800768e2  mov     eax, 1
0x1800768e7  mov     [r15], eax
0x1800768ea  mov     [r12], eax
0x1800768ee  xor     edx, edx; Val
0x1800768f0  lea     r8d, [rax+49h]; Size
0x1800768f4  lea     rcx, [rsp+168h+sourceString]; void *
0x1800768fc  call    memset_0
0x180076901  movzx   eax, byte ptr [r14+0Fh]
0x180076906  movzx   ecx, byte ptr [r14+0Eh]
0x18007690b  movzx   edx, byte ptr [r14+0Dh]
0x180076910  movzx   r8d, byte ptr [r14+0Ch]
0x180076915  movzx   r9d, byte ptr [r14+0Bh]
0x18007691a  movzx   r10d, byte ptr [r14+0Ah]
0x18007691f  movzx   r11d, byte ptr [r14+9]
0x180076924  movzx   ebx, byte ptr [r14+8]
0x180076929  movzx   edi, word ptr [r14+6]
0x18007692e  movzx   esi, word ptr [r14+4]
0x180076933  mov     [rsp+168h+var_100], eax
0x180076937  mov     [rsp+168h+var_108], ecx
0x18007693b  mov     [rsp+168h+var_110], edx
0x18007693f  mov     dword ptr [rsp+168h+var_118], r8d
0x180076944  mov     dword ptr [rsp+168h+var_120], r9d
0x180076949  mov     dword ptr [rsp+168h+var_128], r10d
0x18007694e  mov     dword ptr [rsp+168h+var_130], r11d
0x180076953  mov     dword ptr [rsp+168h+var_138], ebx
0x180076957  mov     [rsp+168h+var_140], edi
0x18007695b  mov     [rsp+168h+var_148], esi; int
0x18007695f  mov     r9d, [r14]
0x180076962  lea     r8, a08lx04x04x02x0; "%08lX-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x180076969  mov     edx, 25h ; '%'; unsigned __int64
0x18007696e  lea     rcx, [rsp+168h+sourceString]; unsigned __int16 *
0x180076976  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007697b  mov     ebx, eax
0x18007697d  xor     esi, esi
0x18007697f  test    eax, eax
0x180076981  jns     short loc_1800769A6
0x180076983  mov     rcx, [rsp+168h]; this
0x18007698b  mov     r9d, eax; char *
0x18007698e  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180076995  mov     edx, 22Bh; void *
0x18007699a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007699f  mov     eax, ebx
0x1800769a1  jmp     loc_180076ECD
0x1800769a6  mov     [rsp+168h+var_F0], rsi
0x1800769ab  mov     [rsp+168h+var_A0], rsi
0x1800769b3  mov     r9d, 47h ; 'G'; unsigned int
0x1800769b9  lea     r8d, [r9+1]; unsigned int
0x1800769bd  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Store_Preview_InstallControl_AppInstallManager@@3QBGB; "Windows.ApplicationModel.Store.Preview."...
0x1800769c4  lea     rcx, [rsp+168h+hstringHeader]; hstringHeader
0x1800769cc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800769d1  lea     rdx, [rsp+168h+var_F0]
0x1800769d6  mov     rcx, [rsp+168h+var_A0]
0x1800769de  call    ??$ActivateInstance@V?$ComPtr@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>)
0x1800769e3  mov     ebx, eax
0x1800769e5  test    eax, eax
0x1800769e7  jns     short loc_180076A17
0x1800769e9  mov     rcx, [rsp+168h]; this
0x1800769f1  mov     r9d, eax; char *
0x1800769f4  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x1800769fb  mov     edx, 231h; void *
0x180076a00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076a05  nop
0x180076a06  lea     rcx, [rsp+168h+var_F0]
0x180076a0b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076a10  mov     eax, ebx
0x180076a12  jmp     loc_180076ECD
0x180076a17  mov     [rsp+168h+var_F8], rsi
0x180076a1c  mov     rbx, [rsp+168h+var_F0]
0x180076a21  mov     rax, [rbx]
0x180076a24  mov     rdi, [rax]
0x180076a27  lea     rcx, [rsp+168h+var_F8]
0x180076a2c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076a31  lea     r8, [rsp+168h+var_F8]
0x180076a36  lea     rdx, _GUID_57b15f7a_3367_48f6_bb71_bacba1331a6e
0x180076a3d  mov     rcx, rbx
0x180076a40  mov     rax, rdi
0x180076a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076a48  mov     ebx, eax
0x180076a4a  test    eax, eax
0x180076a4c  jns     short loc_180076A87
0x180076a4e  mov     rcx, [rsp+168h]; this
0x180076a56  mov     r9d, eax; char *
0x180076a59  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180076a60  mov     edx, 234h; void *
0x180076a65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076a6a  nop
0x180076a6b  lea     rcx, [rsp+168h+var_F8]
0x180076a70  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076a75  nop
0x180076a76  lea     rcx, [rsp+168h+var_F0]
0x180076a7b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076a80  mov     eax, ebx
0x180076a82  jmp     loc_180076ECD
0x180076a87  mov     qword ptr [rsp+168h+var_E0], rsi
0x180076a8f  mov     rdi, [rsp+168h+var_F8]
0x180076a94  mov     rax, [rdi]
0x180076a97  mov     rbx, [rax+38h]
0x180076a9b  lea     rcx, [rsp+168h+var_E0]
0x180076aa3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076aa8  lea     rdx, [rsp+168h+sourceString]; sourceString
0x180076ab0  lea     rcx, [rsp+168h+hstringHeader]; hstringHeader
0x180076ab8  call    ??$?0$0CF@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0CF@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[37])
0x180076abd  nop
0x180076abe  lea     rcx, [rsp+168h+var_E0]
0x180076ac6  mov     qword ptr [rsp+168h+var_148], rcx; int
0x180076acb  mov     r9b, 1
0x180076ace  mov     r14d, 3
0x180076ad4  mov     r8d, r14d
0x180076ad7  mov     rdx, [rax+18h]
0x180076adb  mov     rcx, rdi
0x180076ade  mov     rax, rbx
0x180076ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076ae6  mov     ebx, eax
0x180076ae8  test    eax, eax
0x180076aea  jns     short loc_180076B33
0x180076aec  mov     rcx, [rsp+168h]; this
0x180076af4  mov     r9d, eax; char *
0x180076af7  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180076afe  mov     edx, 23Ch; void *
0x180076b03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076b08  nop
0x180076b09  lea     rcx, [rsp+168h+var_E0]
0x180076b11  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076b16  nop
0x180076b17  lea     rcx, [rsp+168h+var_F8]
0x180076b1c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076b21  nop
0x180076b22  lea     rcx, [rsp+168h+var_F0]
0x180076b27  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076b2c  mov     eax, ebx
0x180076b2e  jmp     loc_180076ECD
0x180076b33  mov     [rsp+168h+var_C8], rsi
0x180076b3b  mov     rdi, qword ptr [rsp+168h+var_E0]
0x180076b43  lea     rcx, [rsp+168h+var_C8]
0x180076b4b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076b50  mov     rcx, rdi
0x180076b53  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *,tagCOWAIT_FLAGS,void *)
0x180076b58  mov     ebx, eax
0x180076b5a  test    eax, eax
0x180076b5c  js      loc_180076E70
0x180076b62  mov     rax, [rdi]
0x180076b65  lea     rdx, [rsp+168h+var_C8]
0x180076b6d  mov     rcx, rdi
0x180076b70  mov     rax, [rax+40h]
0x180076b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076b79  mov     ebx, eax
0x180076b7b  test    eax, eax
0x180076b7d  js      loc_180076E70
0x180076b83  mov     [rsp+168h+var_D0], rsi
0x180076b8b  mov     rdi, [rsp+168h+var_F8]
0x180076b90  mov     rax, [rdi]
0x180076b93  mov     rbx, [rax+48h]
0x180076b97  lea     rcx, [rsp+168h+var_D0]
0x180076b9f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076ba4  lea     rdx, [rsp+168h+sourceString]; sourceString
0x180076bac  lea     rcx, [rsp+168h+hstringHeader]; hstringHeader
0x180076bb4  call    ??$?0$0CF@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0CF@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[37])
0x180076bb9  nop
0x180076bba  lea     rcx, [rsp+168h+var_D0]
0x180076bc2  mov     [rsp+168h+var_118], rcx
0x180076bc7  mov     [rsp+168h+var_120], rsi
0x180076bcc  mov     [rsp+168h+var_128], rsi
0x180076bd1  mov     [rsp+168h+var_130], rsi
0x180076bd6  mov     [rsp+168h+var_138], rsi
0x180076bdb  mov     byte ptr [rsp+168h+var_140], sil
0x180076be0  mov     byte ptr [rsp+168h+var_148], sil; int
0x180076be5  xor     r9d, r9d
0x180076be8  mov     r8d, r14d
0x180076beb  mov     rdx, [rax+18h]
0x180076bef  mov     rcx, rdi
0x180076bf2  mov     rax, rbx
0x180076bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076bfa  mov     ebx, eax
0x180076bfc  test    eax, eax
0x180076bfe  jns     short loc_180076C63
0x180076c00  mov     rcx, [rsp+168h]; this
0x180076c08  mov     r9d, eax; char *
0x180076c0b  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180076c12  mov     edx, 263h; void *
0x180076c17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076c1c  nop
0x180076c1d  lea     rcx, [rsp+168h+var_D0]
0x180076c25  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076c2a  nop
0x180076c2b  lea     rcx, [rsp+168h+var_C8]
0x180076c33  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076c38  nop
0x180076c39  lea     rcx, [rsp+168h+var_E0]
0x180076c41  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076c46  nop
0x180076c47  lea     rcx, [rsp+168h+var_F8]
0x180076c4c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076c51  nop
0x180076c52  lea     rcx, [rsp+168h+var_F0]
0x180076c57  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076c5c  mov     eax, ebx
0x180076c5e  jmp     loc_180076ECD
0x180076c63  mov     [rsp+168h+var_C0], rsi
0x180076c6b  mov     rdi, [rsp+168h+var_D0]
0x180076c73  lea     rcx, [rsp+168h+var_C0]
0x180076c7b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076c80  mov     rcx, rdi
0x180076c83  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *,tagCOWAIT_FLAGS,void *)
0x180076c88  mov     ebx, eax
0x180076c8a  test    eax, eax
0x180076c8c  js      loc_180076E02
0x180076c92  mov     rax, [rdi]
0x180076c95  lea     rdx, [rsp+168h+var_C0]
0x180076c9d  mov     rcx, rdi
0x180076ca0  mov     rax, [rax+40h]
0x180076ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076ca9  mov     ebx, eax
0x180076cab  test    eax, eax
0x180076cad  js      loc_180076E02
0x180076cb3  mov     [rsp+168h+string], rsi
0x180076cbb  mov     rdi, [rsp+168h+var_C0]
0x180076cc3  mov     rax, [rdi]
0x180076cc6  mov     rbx, [rax+30h]
0x180076cca  xor     ecx, ecx; string
0x180076ccc  call    cs:__imp_WindowsDeleteString
0x180076cd2  mov     [rsp+168h+string], rsi
0x180076cda  lea     rdx, [rsp+168h+string]
0x180076ce2  mov     rcx, rdi
0x180076ce5  mov     rax, rbx
0x180076ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076ced  test    eax, eax
0x180076cef  js      loc_180076D97
0x180076cf5  mov     rdx, r13; newString
0x180076cf8  mov     rcx, [rsp+168h+string]; string
0x180076d00  call    cs:__imp_WindowsDuplicateString
0x180076d06  mov     ebx, eax
  ... truncated ...
```
