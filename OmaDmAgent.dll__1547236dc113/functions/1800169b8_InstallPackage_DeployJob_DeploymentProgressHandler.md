# InstallPackage(_DeployJob,DeploymentProgressHandler *)

- ea: `0x1800169b8`
- end: `0x180017340`
- name: `?InstallPackage@@YAJU_DeployJob@@PEAVDeploymentProgressHandler@@@Z`
- size: `2440`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180017b58`

## callees

- `0x1800062ac`
- `0x1800070e4`
- `0x18000a290`
- `0x18000a2c0`
- `0x18000a440`
- `0x18000bbf8`
- `0x180014e1c`
- `0x180014fc4`
- `0x18001507c`
- `0x1800150f8`
- `0x180015244`
- `0x180016734`
- `0x1800169b8`
- `0x180017348`
- `0x180017918`
- `0x18001f420`
- `0x180021010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18001723a`
- `KERNEL32!WaitForSingleObject` at `0x18001723a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180016b20`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180016b20`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180017301`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180017301`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180016a07`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180016a07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016cca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016d71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016e25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016f2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016f8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016fa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001703b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017050`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800170fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800171e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017286`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016cca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016d71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016e25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016f2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016f8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016fa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001703b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017050`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800170fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800171e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017286`

## string_xrefs

- `0x180016af4`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall InstallPackage(__int64 *a1, __int64 a2)
{
  int v4; // edi
  int v5; // eax
  int PackageManager; // eax
  __int64 v7; // rbx
  int ActivationFactory; // eax
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rdi
  int v11; // eax
  __int64 *v12; // r15
  __int64 v13; // rax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, HSTRING, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 (__fastcall ***v19)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v20)(_QWORD, GUID *, __int64 *); // rdi
  int v21; // eax
  _QWORD *v22; // rbx
  _QWORD *v23; // rax
  __int64 v24; // rsi
  __int64 (__fastcall *v25)(__int64, HSTRING, __int64 *); // rdi
  int v26; // eax
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // r9
  int v33; // eax
  __int64 v34; // rcx
  int v35; // r8d
  __int64 v36; // rcx
  __int64 v38; // [rsp+30h] [rbp-89h] BYREF
  HSTRING string; // [rsp+38h] [rbp-81h] BYREF
  __int64 (__fastcall ***v40)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-79h] BYREF
  __int64 v41; // [rsp+48h] [rbp-71h] BYREF
  __int64 v42; // [rsp+50h] [rbp-69h] BYREF
  __int64 v43; // [rsp+58h] [rbp-61h] BYREF
  __int64 (__fastcall ***v44)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-59h] BYREF
  __int64 v45; // [rsp+68h] [rbp-51h] BYREF
  HSTRING v46; // [rsp+70h] [rbp-49h] BYREF
  struct Windows::Management::Deployment::IPackageManager *v47; // [rsp+78h] [rbp-41h] BYREF
  _QWORD v48[2]; // [rsp+80h] [rbp-39h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-29h] BYREF
  __int64 v50; // [rsp+A8h] [rbp-11h]
  _QWORD v51[3]; // [rsp+B0h] [rbp-9h] BYREF
  unsigned __int64 v52; // [rsp+C8h] [rbp+Fh]

  v48[1] = a1;
  v47 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    goto LABEL_90;
  }
  v5 = RoInitialize(1);
  v4 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
        (unsigned int)v5);
    goto LABEL_88;
  }
  v44 = 0;
  v41 = 0;
  v43 = 0;
  v38 = 0;
  v40 = 0;
  v42 = 0;
  PackageManager = GetPackageManager(&v47);
  v4 = PackageManager;
  if ( PackageManager >= 0 )
  {
    v50 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
    v7 = v50;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v44);
    ActivationFactory = RoGetActivationFactory(v7, &GUID_00000035_0000_0000_c000_000000000046, &v44);
    v4 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v44;
      v10 = **v44;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v41);
      v11 = v10(v9, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v41);
      v4 = v11;
      if ( v11 >= 0 )
      {
        string = 0;
        v12 = a1 + 8;
        if ( (unsigned __int64)a1[11] < 8 )
          v13 = (__int64)(a1 + 8);
        else
          v13 = *v12;
        v45 = v13;
        Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string, &v45);
        v14 = v41;
        v15 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v41 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v43);
        v16 = v15(v14, string, &v43);
        v4 = v16;
        if ( v16 >= 0 )
        {
          if ( !a1[14] )
          {
LABEL_56:
            v4 = (*(__int64 (__fastcall **)(struct Windows::Management::Deployment::IPackageManager *, __int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v47 + 48LL))(
                   v47,
                   v43,
                   v42,
                   *((unsigned int *)a1 + 25),
                   &v38);
            if ( v4 >= 0 )
            {
              if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                if ( (unsigned __int64)a1[11] < 8 )
                  v31 = (__int64)(a1 + 8);
                else
                  v31 = *v12;
                if ( (unsigned __int64)a1[3] < 8 )
                  LODWORD(v32) = (_DWORD)a1;
                else
                  v32 = *a1;
                WPP_SF_SS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  70,
                  (unsigned int)&WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
                  v32,
                  v31);
              }
              _DeployJob::operator=(a2 + 80, a1);
              v33 = AddDeploymentCallbacks(v38, a2, a2 + 8);
              v4 = v33;
              if ( v33 >= 0 )
              {
                if ( WaitForSingleObject(*(HANDLE *)(a2 + 72), *((_DWORD *)a1 + 30)) == 258
                  && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
                  && (WPP_GLOBAL_Control[14] & 2) != 0 )
                {
                  if ( (unsigned __int64)a1[11] >= 8 )
                    v12 = (__int64 *)*v12;
                  WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, v35, *((_DWORD *)a1 + 30), (__int64)v12);
                }
                WindowsDeleteString(string);
                string = 0;
                v50 = 0;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v42);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v40);
                v36 = v38;
                if ( v38 )
                {
                  v38 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    71,
                    &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
                    (unsigned int)v33);
                WindowsDeleteString(string);
                string = 0;
                v50 = 0;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v42);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v40);
                v34 = v38;
                if ( v38 )
                {
                  v38 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                }
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_17887b334fcf349edf3df6ab34803119_Traceguids);
              WindowsDeleteString(string);
              string = 0;
              v50 = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v42);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v40);
              v30 = v38;
              if ( v38 )
              {
                v38 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
              }
            }
            goto LABEL_87;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v40);
          v18 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Foundation::Uri,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>>>(
                  v17,
                  &v40);
          v4 = v18;
          if ( v18 >= 0 )
          {
            v19 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v40;
            v20 = **v40;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v42);
            v21 = v20(v19, &GUID_b0d63b78_78ad_5e31_b6d8_e32a0e16c447, &v42);
            v4 = v21;
            if ( v21 >= 0 )
            {
              v22 = (_QWORD *)a1[13];
              while ( 1 )
              {
                v22 = (_QWORD *)*v22;
                if ( v22 == (_QWORD *)a1[13] )
                  goto LABEL_56;
                v46 = 0;
                v52 = 7;
                v51[2] = 0;
                LOWORD(v51[0]) = 0;
                std::wstring::operator=(v51, v22 + 2);
                v23 = v51;
                if ( v52 >= 8 )
                  v23 = (_QWORD *)v51[0];
                v48[0] = v23;
                Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v46, v48);
                v45 = 0;
                v24 = v41;
                v25 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v41 + 48LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v45);
                v26 = v25(v24, v46, &v45);
                v4 = v26;
                if ( v26 < 0 )
                  break;
                v27 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*v40)[13])(
                        v40,
                        v45);
                v4 = v27;
                if ( v27 < 0 )
                {
                  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      68,
                      &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
                      (unsigned int)v27);
LABEL_51:
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v45);
                  LOBYTE(v29) = 1;
                  std::wstring::_Tidy(v51, v29, 0);
                  WindowsDeleteString(v46);
                  v46 = 0;
                  WindowsDeleteString(string);
                  string = 0;
                  v50 = 0;
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v42);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v40);
                  goto LABEL_87;
                }
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v45);
                LOBYTE(v28) = 1;
                std::wstring::_Tidy(v51, v28, 0);
                WindowsDeleteString(v46);
              }
              if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  67,
                  &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
                  (unsigned int)v26);
              goto LABEL_51;
            }
            if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                66,
                &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
                (unsigned int)v21);
          }
          else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              65,
              &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
              (unsigned int)v18);
          }
        }
        else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            64,
            &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
            (unsigned int)v16);
        }
        WindowsDeleteString(string);
        string = 0;
        v50 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v40);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            63,
            &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
            (unsigned int)v11);
        v50 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v40);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          62,
          &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
          (unsigned int)ActivationFactory);
      v50 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v42);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v40);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        61,
        &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
        (unsigned int)PackageManager);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v42);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v40);
  }
LABEL_87:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v41);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v44);
LABEL_88:
  if ( v47 )
  {
    (*(void (__fastcall **)(struct Windows::Management::Deployment::IPackageManager *))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
  }
LABEL_90:
  RoUninitialize();
  _DeployJob::~_DeployJob((_DeployJob *)a1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800169b8  mov     [rsp-8+arg_10], rbx
0x1800169bd  push    rbp
0x1800169be  push    rsi
0x1800169bf  push    rdi
0x1800169c0  push    r12
0x1800169c2  push    r13
0x1800169c4  push    r14
0x1800169c6  push    r15
0x1800169c8  lea     rbp, [rsp-27h]
0x1800169cd  sub     rsp, 0E0h
0x1800169d4  mov     rax, cs:__security_cookie
0x1800169db  xor     rax, rsp
0x1800169de  mov     [rbp+57h+var_40], rax
0x1800169e2  mov     r13, rdx
0x1800169e5  mov     r14, rcx
0x1800169e8  mov     [rbp+57h+var_88], rcx
0x1800169ec  xor     r12d, r12d
0x1800169ef  mov     [rbp+57h+var_98], r12
0x1800169f3  test    rdx, rdx
0x1800169f6  jnz     short loc_180016A02
0x1800169f8  mov     edi, 80070057h
0x1800169fd  jmp     loc_180017301
0x180016a02  mov     ecx, 1
0x180016a07  call    cs:__imp_RoInitialize
0x180016a0e  nop     dword ptr [rax+rax+00h]
0x180016a13  mov     edi, eax
0x180016a15  test    eax, eax
0x180016a17  jns     short loc_180016A57
0x180016a19  lea     rbx, WPP_GLOBAL_Control
0x180016a20  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a27  cmp     rcx, rbx
0x180016a2a  jz      loc_1800172E8
0x180016a30  test    byte ptr [rcx+1Ch], 4
0x180016a34  jz      loc_1800172E8
0x180016a3a  mov     edx, 3Ch ; '<'
0x180016a3f  mov     r9d, eax
0x180016a42  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x180016a49  mov     rcx, [rcx+10h]
0x180016a4d  call    WPP_SF_d
0x180016a52  jmp     loc_1800172E8
0x180016a57  mov     [rbp+57h+var_B0], r12
0x180016a5b  mov     [rbp+57h+var_C8], r12
0x180016a5f  mov     [rbp+57h+var_B8], r12
0x180016a63  mov     [rsp+110h+var_E0], r12
0x180016a68  mov     [rbp+57h+var_D0], r12
0x180016a6c  mov     [rbp+57h+var_C0], r12
0x180016a70  lea     rcx, [rbp+57h+var_98]; struct Windows::Management::Deployment::IPackageManager **
0x180016a74  call    ?GetPackageManager@@YAJPEAPEAUIPackageManager@Deployment@Management@Windows@@@Z; GetPackageManager(Windows::Management::Deployment::IPackageManager * *)
0x180016a79  mov     edi, eax
0x180016a7b  test    eax, eax
0x180016a7d  jns     short loc_180016AE6
0x180016a7f  lea     rbx, WPP_GLOBAL_Control
0x180016a86  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a8d  cmp     rcx, rbx
0x180016a90  jz      short loc_180016AB1
0x180016a92  test    byte ptr [rcx+1Ch], 4
0x180016a96  jz      short loc_180016AB1
0x180016a98  mov     edx, 3Dh ; '='
0x180016a9d  mov     r9d, eax
0x180016aa0  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x180016aa7  mov     rcx, [rcx+10h]
0x180016aab  call    WPP_SF_d
0x180016ab0  nop
0x180016ab1  lea     rcx, [rbp+57h+var_C0]
0x180016ab5  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180016aba  nop
0x180016abb  lea     rcx, [rbp+57h+var_D0]
0x180016abf  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180016ac4  nop
0x180016ac5  mov     rcx, [rsp+110h+var_E0]
0x180016aca  test    rcx, rcx
0x180016acd  jz      short loc_180016AE1
0x180016acf  mov     [rsp+110h+var_E0], r12
0x180016ad4  mov     rax, [rcx]
0x180016ad7  mov     rax, [rax+10h]
0x180016adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ae0  nop
0x180016ae1  jmp     loc_1800172CB
0x180016ae6  mov     [rbp+57h+var_68], r12
0x180016aea  mov     r9d, 16h; unsigned int
0x180016af0  lea     r8d, [r9+1]; unsigned int
0x180016af4  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180016afb  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180016aff  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180016b04  nop
0x180016b05  mov     rbx, [rbp+57h+var_68]
0x180016b09  lea     rcx, [rbp+57h+var_B0]
0x180016b0d  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180016b12  lea     r8, [rbp+57h+var_B0]
0x180016b16  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x180016b1d  mov     rcx, rbx
0x180016b20  call    cs:__imp_RoGetActivationFactory
0x180016b27  nop     dword ptr [rax+rax+00h]
0x180016b2c  mov     edi, eax
0x180016b2e  test    eax, eax
0x180016b30  jns     short loc_180016B9D
0x180016b32  lea     rbx, WPP_GLOBAL_Control
0x180016b39  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b40  cmp     rcx, rbx
0x180016b43  jz      short loc_180016B64
0x180016b45  test    byte ptr [rcx+1Ch], 4
0x180016b49  jz      short loc_180016B64
0x180016b4b  mov     edx, 3Eh ; '>'
0x180016b50  mov     r9d, eax
0x180016b53  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x180016b5a  mov     rcx, [rcx+10h]
0x180016b5e  call    WPP_SF_d
0x180016b63  nop
0x180016b64  mov     [rbp+57h+var_68], r12
0x180016b68  lea     rcx, [rbp+57h+var_C0]
0x180016b6c  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180016b71  nop
0x180016b72  lea     rcx, [rbp+57h+var_D0]
0x180016b76  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180016b7b  nop
0x180016b7c  mov     rcx, [rsp+110h+var_E0]
0x180016b81  test    rcx, rcx
0x180016b84  jz      short loc_180016B98
0x180016b86  mov     [rsp+110h+var_E0], r12
0x180016b8b  mov     rax, [rcx]
0x180016b8e  mov     rax, [rax+10h]
0x180016b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b97  nop
0x180016b98  jmp     loc_1800172CB
0x180016b9d  mov     rbx, [rbp+57h+var_B0]
0x180016ba1  mov     rax, [rbx]
0x180016ba4  mov     rdi, [rax]
0x180016ba7  lea     rcx, [rbp+57h+var_C8]
0x180016bab  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180016bb0  lea     r8, [rbp+57h+var_C8]
0x180016bb4  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x180016bbb  mov     rcx, rbx
0x180016bbe  mov     rax, rdi
0x180016bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bc6  mov     edi, eax
0x180016bc8  test    eax, eax
0x180016bca  jns     short loc_180016C37
0x180016bcc  lea     rbx, WPP_GLOBAL_Control
0x180016bd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180016bda  cmp     rcx, rbx
0x180016bdd  jz      short loc_180016BFE
0x180016bdf  test    byte ptr [rcx+1Ch], 4
0x180016be3  jz      short loc_180016BFE
0x180016be5  mov     edx, 3Fh ; '?'
0x180016bea  mov     r9d, eax
0x180016bed  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x180016bf4  mov     rcx, [rcx+10h]
0x180016bf8  call    WPP_SF_d
0x180016bfd  nop
0x180016bfe  mov     [rbp+57h+var_68], r12
0x180016c02  lea     rcx, [rbp+57h+var_C0]
0x180016c06  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180016c0b  nop
0x180016c0c  lea     rcx, [rbp+57h+var_D0]
0x180016c10  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180016c15  nop
0x180016c16  mov     rcx, [rsp+110h+var_E0]
0x180016c1b  test    rcx, rcx
0x180016c1e  jz      short loc_180016C32
0x180016c20  mov     [rsp+110h+var_E0], r12
0x180016c25  mov     rax, [rcx]
0x180016c28  mov     rax, [rax+10h]
0x180016c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c31  nop
0x180016c32  jmp     loc_1800172CB
0x180016c37  mov     [rsp+110h+string], r12
0x180016c3c  lea     r15, [r14+40h]
0x180016c40  cmp     qword ptr [r15+18h], 8
0x180016c45  jb      short loc_180016C4C
0x180016c47  mov     rax, [r15]
0x180016c4a  jmp     short loc_180016C4F
0x180016c4c  mov     rax, r15
0x180016c4f  mov     [rbp+57h+var_A8], rax
0x180016c53  lea     rdx, [rbp+57h+var_A8]
0x180016c57  lea     rcx, [rsp+110h+string]
0x180016c5c  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180016c61  mov     rdi, [rbp+57h+var_C8]
0x180016c65  mov     rax, [rdi]
0x180016c68  mov     rbx, [rax+30h]
0x180016c6c  lea     rcx, [rbp+57h+var_B8]
0x180016c70  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180016c75  lea     r8, [rbp+57h+var_B8]
0x180016c79  mov     rdx, [rsp+110h+string]
0x180016c7e  mov     rcx, rdi
0x180016c81  mov     rax, rbx
0x180016c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c89  mov     edi, eax
0x180016c8b  test    eax, eax
0x180016c8d  jns     loc_180016D14
0x180016c93  lea     rbx, WPP_GLOBAL_Control
0x180016c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ca1  cmp     rcx, rbx
0x180016ca4  jz      short loc_180016CC5
0x180016ca6  test    byte ptr [rcx+1Ch], 4
0x180016caa  jz      short loc_180016CC5
0x180016cac  mov     edx, 40h ; '@'
0x180016cb1  mov     r9d, eax
0x180016cb4  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x180016cbb  mov     rcx, [rcx+10h]
0x180016cbf  call    WPP_SF_d
0x180016cc4  nop
0x180016cc5  mov     rcx, [rsp+110h+string]; string
0x180016cca  call    cs:__imp_WindowsDeleteString
0x180016cd1  nop     dword ptr [rax+rax+00h]
0x180016cd6  mov     [rsp+110h+string], r12
0x180016cdb  mov     [rbp+57h+var_68], r12
0x180016cdf  lea     rcx, [rbp+57h+var_C0]
0x180016ce3  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180016ce8  nop
0x180016ce9  lea     rcx, [rbp+57h+var_D0]
0x180016ced  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180016cf2  nop
0x180016cf3  mov     rcx, [rsp+110h+var_E0]
0x180016cf8  test    rcx, rcx
0x180016cfb  jz      short loc_180016D0F
0x180016cfd  mov     [rsp+110h+var_E0], r12
0x180016d02  mov     rax, [rcx]
0x180016d05  mov     rax, [rax+10h]
0x180016d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d0e  nop
0x180016d0f  jmp     loc_1800172CB
0x180016d14  cmp     [r14+70h], r12
0x180016d18  jbe     loc_18001709A
0x180016d1e  lea     rcx, [rbp+57h+var_D0]
0x180016d22  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180016d27  lea     rdx, [rbp+57h+var_D0]
0x180016d2b  call    ??$CreateExternalObjectVector@VUri@Foundation@Windows@@V?$Vector@PEAVUri@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAVUri@Foundation@Windows@@@Internal@Collections@23@U?$DefaultLifetimeTraits@PEAVUri@Foundation@Windows@@@5623@U?$DefaultVectorOptions@PEAVUri@Foundation@Windows@@@5623@@Internal@Collections@23@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVUri@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAVUri@Foundation@Windows@@@Internal@Collections@23@U?$DefaultLifetimeTraits@PEAVUri@Foundation@Windows@@@5623@U?$DefaultVectorOptions@PEAVUri@Foundation@Windows@@@5623@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Foundation::Uri,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>> * *)
0x180016d30  mov     edi, eax
0x180016d32  test    eax, eax
0x180016d34  jns     loc_180016DBB
0x180016d3a  lea     rbx, WPP_GLOBAL_Control
0x180016d41  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d48  cmp     rcx, rbx
0x180016d4b  jz      short loc_180016D6C
0x180016d4d  test    byte ptr [rcx+1Ch], 4
0x180016d51  jz      short loc_180016D6C
0x180016d53  mov     edx, 41h ; 'A'
0x180016d58  mov     r9d, eax
0x180016d5b  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x180016d62  mov     rcx, [rcx+10h]
0x180016d66  call    WPP_SF_d
0x180016d6b  nop
0x180016d6c  mov     rcx, [rsp+110h+string]; string
0x180016d71  call    cs:__imp_WindowsDeleteString
0x180016d78  nop     dword ptr [rax+rax+00h]
0x180016d7d  mov     [rsp+110h+string], r12
0x180016d82  mov     [rbp+57h+var_68], r12
0x180016d86  lea     rcx, [rbp+57h+var_C0]
0x180016d8a  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180016d8f  nop
0x180016d90  lea     rcx, [rbp+57h+var_D0]
0x180016d94  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180016d99  nop
0x180016d9a  mov     rcx, [rsp+110h+var_E0]
0x180016d9f  test    rcx, rcx
0x180016da2  jz      short loc_180016DB6
0x180016da4  mov     [rsp+110h+var_E0], r12
0x180016da9  mov     rax, [rcx]
0x180016dac  mov     rax, [rax+10h]
0x180016db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016db5  nop
0x180016db6  jmp     loc_1800172CB
0x180016dbb  mov     rbx, [rbp+57h+var_D0]
0x180016dbf  mov     rax, [rbx]
0x180016dc2  mov     rdi, [rax]
0x180016dc5  lea     rcx, [rbp+57h+var_C0]
0x180016dc9  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180016dce  lea     r8, [rbp+57h+var_C0]
0x180016dd2  lea     rdx, _GUID_b0d63b78_78ad_5e31_b6d8_e32a0e16c447
0x180016dd9  mov     rcx, rbx
0x180016ddc  mov     rax, rdi
0x180016ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016de4  mov     edi, eax
0x180016de6  test    eax, eax
0x180016de8  jns     loc_180016E6F
0x180016dee  lea     rbx, WPP_GLOBAL_Control
0x180016df5  mov     rcx, cs:WPP_GLOBAL_Control
0x180016dfc  cmp     rcx, rbx
0x180016dff  jz      short loc_180016E20
0x180016e01  test    byte ptr [rcx+1Ch], 4
0x180016e05  jz      short loc_180016E20
0x180016e07  mov     edx, 42h ; 'B'
0x180016e0c  mov     r9d, eax
0x180016e0f  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x180016e16  mov     rcx, [rcx+10h]
0x180016e1a  call    WPP_SF_d
0x180016e1f  nop
0x180016e20  mov     rcx, [rsp+110h+string]; string
0x180016e25  call    cs:__imp_WindowsDeleteString
0x180016e2c  nop     dword ptr [rax+rax+00h]
0x180016e31  mov     [rsp+110h+string], r12
0x180016e36  mov     [rbp+57h+var_68], r12
0x180016e3a  lea     rcx, [rbp+57h+var_C0]
0x180016e3e  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180016e43  nop
0x180016e44  lea     rcx, [rbp+57h+var_D0]
0x180016e48  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180016e4d  nop
0x180016e4e  mov     rcx, [rsp+110h+var_E0]
0x180016e53  test    rcx, rcx
  ... truncated ...
```
