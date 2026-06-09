# GetPackageInfo(Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage>,PackageInfo &)

- ea: `0x180015c2c`
- end: `0x18001672c`
- name: `?GetPackageInfo@@YAJV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@AEAUPackageInfo@@@Z`
- size: `2816`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180015298`

## callees

- `0x1800062ac`
- `0x1800065f8`
- `0x1800070a4`
- `0x1800070e4`
- `0x180009e20`
- `0x18000a2c0`
- `0x1800155e4`
- `0x180015c2c`
- `0x180017348`
- `0x18001f3da`
- `0x18001f420`
- `0x180021010`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x180016665`
- `msvcrt!_snwprintf_s` at `0x180016665`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015ec7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015f98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001606a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001642a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001652c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015ec7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015f98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001606a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001642a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001652c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015e1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015eef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015fc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016501`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800166dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015e1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015eef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015fc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016501`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800166dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall GetPackageInfo(_QWORD *a1, _BYTE *a2)
{
  void (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // rdi
  void (__fastcall *v5)(_QWORD, GUID *, __int64 *); // rbx
  void (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v7)(void (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *); // rbx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  PCWSTR v24; // rax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, HSTRING *); // rbx
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rcx
  PCWSTR v30; // rax
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rcx
  int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 ArchString; // rax
  __int64 v44; // rdx
  int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // rcx
  unsigned int i; // esi
  __int64 v49; // rdi
  void (__fastcall *v50)(__int64, _QWORD *); // rbx
  PCWSTR v51; // rax
  __int64 v52; // rcx
  void (__fastcall ***v53)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v54)(void (__fastcall ***)(_QWORD, GUID *, __int64 *), void (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v55; // eax
  void (__fastcall ***v56)(_QWORD, _QWORD, _QWORD); // rbx
  void (__fastcall *v57)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v58; // rdi
  void (__fastcall *v59)(__int64, HSTRING *); // rbx
  PCWSTR v60; // rax
  int v61; // eax
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // rdx
  __int64 v65; // rcx
  void (__fastcall ***v66)(_QWORD, GUID *, __int64 *); // rcx
  int v68; // [rsp+20h] [rbp-E0h]
  int v69; // [rsp+28h] [rbp-D8h]
  int v70; // [rsp+30h] [rbp-D0h]
  int v71; // [rsp+38h] [rbp-C8h]
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v73; // [rsp+48h] [rbp-B8h] BYREF
  char v74; // [rsp+50h] [rbp-B0h] BYREF
  char v75; // [rsp+51h] [rbp-AFh] BYREF
  char v76; // [rsp+52h] [rbp-AEh] BYREF
  _BYTE v77[5]; // [rsp+53h] [rbp-ADh] BYREF
  __int64 v78; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v79; // [rsp+60h] [rbp-A0h] BYREF
  UINT32 length; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v81; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v82; // [rsp+70h] [rbp-90h] BYREF
  __int64 v83; // [rsp+78h] [rbp-88h] BYREF
  void (__fastcall ***v84)(_QWORD, GUID *, __int64 *); // [rsp+80h] [rbp-80h] BYREF
  __int64 v85; // [rsp+88h] [rbp-78h] BYREF
  __int64 v86; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v87[2]; // [rsp+98h] [rbp-68h] BYREF
  _WORD v88[8]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v89; // [rsp+B8h] [rbp-48h]
  __int64 v90; // [rsp+C0h] [rbp-40h]
  _BYTE v91[40]; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t Buffer[56]; // [rsp+F0h] [rbp-10h] BYREF

  v87[1] = a1;
  string = 0;
  length = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77[0] = 0;
  v73 = 0;
  v90 = 7;
  v89 = 0;
  v88[0] = 0;
  v79 = 0;
  v4 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
  v5 = **(void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v79);
  v5(v4, &GUID_a6612fb6_7688_4ace_95fb_359538e7aa01, &v79);
  v78 = 0;
  v6 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
  v7 = *(__int64 (__fastcall **)(void (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*(_QWORD *)*a1 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v78);
  v8 = v7(v6, &v78);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*a1 + 64LL))(*a1, &v74);
    v9 = v11;
    if ( v11 >= 0 )
    {
      a2[288] = v74;
      v13 = v78;
      v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v78 + 96LL);
      WindowsDeleteString(string);
      string = 0;
      v15 = v14(v13, &string);
      v9 = v15;
      if ( v15 >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
        std::wstring::assign(a2, StringRawBuffer);
        v19 = v78;
        v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v78 + 48LL);
        WindowsDeleteString(string);
        string = 0;
        v21 = v20(v19, &string);
        v9 = v21;
        if ( v21 >= 0 )
        {
          v24 = WindowsGetStringRawBuffer(string, &length);
          std::wstring::assign(a2 + 64, v24);
          v25 = v78;
          v26 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v78 + 80LL);
          WindowsDeleteString(string);
          string = 0;
          v27 = v26(v25, &string);
          v9 = v27;
          if ( v27 >= 0 )
          {
            v30 = WindowsGetStringRawBuffer(string, &length);
            std::wstring::assign(a2 + 96, v30);
            v31 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v79 + 80LL))(v79, &v75);
            v9 = v31;
            if ( v31 >= 0 )
            {
              a2[289] = v75;
              v34 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v79 + 88LL))(v79, &v76);
              v9 = v34;
              if ( v34 >= 0 )
              {
                a2[290] = v76;
                v37 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v79 + 96LL))(v79, v77);
                v9 = v37;
                if ( v37 >= 0 )
                {
                  a2[291] = v77[0];
                  v82 = 0;
                  v40 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v78 + 64LL))(v78, &v82);
                  v9 = v40;
                  if ( v40 >= 0 )
                  {
                    ArchString = GetArchString(v91, v82);
                    std::wstring::operator=(a2 + 160, ArchString);
                    LOBYTE(v44) = 1;
                    std::wstring::_Tidy(v91, v44, 0);
                    v45 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a1 + 72LL))(*a1, &v73);
                    v9 = v45;
                    if ( v45 >= 0 )
                    {
                      v81 = 0;
                      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v73 + 56LL))(v73, &v81);
                      if ( v81 )
                      {
                        v86 = 0;
                        v87[0] = 0;
                        for ( i = 0; i < v81; ++i )
                        {
                          (*(void (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v73 + 48LL))(v73, 0, &v86);
                          v49 = v86;
                          v50 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v86 + 48LL);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(v87);
                          v50(v49, v87);
                          v51 = WindowsGetStringRawBuffer(string, &length);
                          std::wstring::append(v88, v51);
                          std::wstring::append(v88, L";");
                        }
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(v87);
                        v52 = v86;
                        if ( v86 )
                        {
                          v86 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
                        }
                      }
                      std::wstring::operator=(a2 + 256, v88);
                      v85 = 0;
                      v84 = 0;
                      v53 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
                      v54 = *(__int64 (__fastcall **)(void (__fastcall ***)(_QWORD, GUID *, __int64 *), void (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)*a1 + 56LL);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v84);
                      v55 = v54(v53, &v84);
                      if ( v55 < 0 )
                      {
                        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
                          WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            58,
                            &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
                            (unsigned int)v55);
                      }
                      else
                      {
                        v56 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
                        v57 = **v84;
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v85);
                        v57(v56, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v85);
                        v58 = v85;
                        v59 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v85 + 96LL);
                        WindowsDeleteString(string);
                        string = 0;
                        v59(v58, &string);
                        v60 = WindowsGetStringRawBuffer(string, &length);
                        std::wstring::assign(a2 + 224, v60);
                      }
                      v83 = 0;
                      v61 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v78 + 56LL))(v78, &v83);
                      v9 = v61;
                      if ( v61 >= 0 )
                      {
                        memset_0(Buffer, 0, 0x64u);
                        v71 = HIWORD(v83);
                        v70 = WORD2(v83);
                        v69 = WORD1(v83);
                        v68 = (unsigned __int16)v83;
                        _snwprintf_s(Buffer, 0x32u, 0xFFFFFFFFFFFFFFFFuLL, L"%d.%d.%d.%d", v68, v69, v70, v71);
                        std::wstring::assign(a2 + 128, Buffer);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v84);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v85);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v78);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v79);
                        LOBYTE(v64) = 1;
                        std::wstring::_Tidy(v88, v64, 0);
                        v65 = v73;
                        if ( v73 )
                        {
                          v73 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                        }
                      }
                      else
                      {
                        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                          WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            59,
                            &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
                            (unsigned int)v61);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v84);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v85);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v78);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v79);
                        LOBYTE(v62) = 1;
                        std::wstring::_Tidy(v88, v62, 0);
                        v63 = v73;
                        if ( v73 )
                        {
                          v73 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
                        }
                      }
                    }
                    else
                    {
                      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          57,
                          &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
                          (unsigned int)v45);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v78);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v79);
                      LOBYTE(v46) = 1;
                      std::wstring::_Tidy(v88, v46, 0);
                      v47 = v73;
                      if ( v73 )
                      {
                        v73 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
                      }
                    }
                  }
                  else
                  {
                    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        56,
                        &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
                        (unsigned int)v40);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v78);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v79);
                    LOBYTE(v41) = 1;
                    std::wstring::_Tidy(v88, v41, 0);
                    v42 = v73;
                    if ( v73 )
                    {
                      v73 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
                    }
                  }
                }
                else
                {
                  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      55,
                      &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
                      (unsigned int)v37);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v78);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v79);
                  LOBYTE(v38) = 1;
                  std::wstring::_Tidy(v88, v38, 0);
                  v39 = v73;
                  if ( v73 )
                  {
                    v73 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
                  }
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    54,
                    &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
                    (unsigned int)v34);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v78);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v79);
                LOBYTE(v35) = 1;
                std::wstring::_Tidy(v88, v35, 0);
                v36 = v73;
                if ( v73 )
                {
                  v73 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
                }
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  53,
                  &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
                  (unsigned int)v31);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v78);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v79);
              LOBYTE(v32) = 1;
              std::wstring::_Tidy(v88, v32, 0);
              v33 = v73;
              if ( v73 )
              {
                v73 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
              }
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                52,
                &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
                (unsigned int)v27);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v78);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v79);
            LOBYTE(v28) = 1;
            std::wstring::_Tidy(v88, v28, 0);
            v29 = v73;
            if ( v73 )
            {
              v73 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              51,
              &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
              (unsigned int)v21);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v78);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v79);
          LOBYTE(v22) = 1;
          std::wstring::_Tidy(v88, v22, 0);
          v23 = v73;
          if ( v73 )
          {
            v73 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            50,
            &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
            (unsigned int)v15);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v78);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v79);
        LOBYTE(v16) = 1;
        std::wstring::_Tidy(v88, v16, 0);
        v17 = v73;
        if ( v73 )
        {
          v73 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
          (unsigned int)v11);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v78);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v79);
      LOBYTE(v12) = 1;
      std::wstring::_Tidy(v88, v12, 0);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
        (unsigned int)v8);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v78);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v79);
    LOBYTE(v10) = 1;
    std::wstring::_Tidy(v88, v10, 0);
  }
  WindowsDeleteString(string);
  v66 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
  if ( *a1 )
  {
    *a1 = 0;
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v66)[2])(v66);
  }
  return v9;
}

```

## disassembly

```asm
0x180015c2c  mov     [rsp-8+arg_10], rbx
0x180015c31  mov     [rsp-8+arg_18], rsi
0x180015c36  push    rbp
0x180015c37  push    rdi
0x180015c38  push    r12
0x180015c3a  push    r14
0x180015c3c  push    r15
0x180015c3e  lea     rbp, [rsp-70h]
0x180015c43  sub     rsp, 170h
0x180015c4a  mov     rax, cs:__security_cookie
0x180015c51  xor     rax, rsp
0x180015c54  mov     [rbp+90h+var_30], rax
0x180015c58  mov     r14, rdx
0x180015c5b  mov     r15, rcx
0x180015c5e  mov     [rbp+90h+var_F0], rcx
0x180015c62  xor     r12d, r12d
0x180015c65  mov     [rsp+190h+string], r12
0x180015c6a  mov     [rsp+190h+length], r12d
0x180015c6f  mov     [rsp+190h+var_140], r12b
0x180015c74  mov     [rsp+190h+var_13F], r12b
0x180015c79  mov     [rsp+190h+var_13E], r12b
0x180015c7e  mov     [rsp+190h+var_13D], r12b
0x180015c83  mov     [rsp+190h+var_148], r12
0x180015c88  mov     [rbp+90h+var_D0], 7
0x180015c90  mov     [rbp+90h+var_D8], r12
0x180015c94  mov     [rbp+90h+var_E8], r12w
0x180015c99  mov     [rsp+190h+var_130], r12
0x180015c9e  mov     rdi, [rcx]
0x180015ca1  mov     rax, [rdi]
0x180015ca4  mov     rbx, [rax]
0x180015ca7  lea     rcx, [rsp+190h+var_130]
0x180015cac  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180015cb1  lea     r8, [rsp+190h+var_130]
0x180015cb6  lea     rdx, _GUID_a6612fb6_7688_4ace_95fb_359538e7aa01
0x180015cbd  mov     rcx, rdi
0x180015cc0  mov     rax, rbx
0x180015cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cc8  nop
0x180015cc9  mov     [rsp+190h+var_138], r12
0x180015cce  mov     rdi, [r15]
0x180015cd1  mov     rax, [rdi]
0x180015cd4  mov     rbx, [rax+30h]
0x180015cd8  lea     rcx, [rsp+190h+var_138]
0x180015cdd  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180015ce2  lea     rdx, [rsp+190h+var_138]
0x180015ce7  mov     rcx, rdi
0x180015cea  mov     rax, rbx
0x180015ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cf2  mov     ebx, eax
0x180015cf4  test    eax, eax
0x180015cf6  jns     short loc_180015D70
0x180015cf8  lea     rsi, WPP_GLOBAL_Control
0x180015cff  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d06  cmp     rcx, rsi
0x180015d09  jz      short loc_180015D2A
0x180015d0b  test    byte ptr [rcx+1Ch], 4
0x180015d0f  jz      short loc_180015D2A
0x180015d11  lea     edx, [r12+30h]
0x180015d16  mov     r9d, eax
0x180015d19  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x180015d20  mov     rcx, [rcx+10h]
0x180015d24  call    WPP_SF_d
0x180015d29  nop
0x180015d2a  lea     rcx, [rsp+190h+var_138]
0x180015d2f  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180015d34  nop
0x180015d35  lea     rcx, [rsp+190h+var_130]
0x180015d3a  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180015d3f  nop
0x180015d40  xor     r8d, r8d
0x180015d43  mov     dl, 1
0x180015d45  lea     rcx, [rbp+90h+var_E8]
0x180015d49  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015d4e  nop
0x180015d4f  mov     rcx, [rsp+190h+var_148]
0x180015d54  test    rcx, rcx
0x180015d57  jz      short loc_180015D6B
0x180015d59  mov     [rsp+190h+var_148], r12
0x180015d5e  mov     rax, [rcx]
0x180015d61  mov     rax, [rax+10h]
0x180015d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d6a  nop
0x180015d6b  jmp     loc_1800166D7
0x180015d70  mov     rcx, [r15]
0x180015d73  mov     rax, [rcx]
0x180015d76  lea     rdx, [rsp+190h+var_140]
0x180015d7b  mov     rax, [rax+40h]
0x180015d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d84  mov     ebx, eax
0x180015d86  test    eax, eax
0x180015d88  jns     short loc_180015E02
0x180015d8a  lea     rsi, WPP_GLOBAL_Control
0x180015d91  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d98  cmp     rcx, rsi
0x180015d9b  jz      short loc_180015DBC
0x180015d9d  test    byte ptr [rcx+1Ch], 4
0x180015da1  jz      short loc_180015DBC
0x180015da3  mov     edx, 31h ; '1'
0x180015da8  mov     r9d, eax
0x180015dab  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x180015db2  mov     rcx, [rcx+10h]
0x180015db6  call    WPP_SF_d
0x180015dbb  nop
0x180015dbc  lea     rcx, [rsp+190h+var_138]
0x180015dc1  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180015dc6  nop
0x180015dc7  lea     rcx, [rsp+190h+var_130]
0x180015dcc  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180015dd1  nop
0x180015dd2  xor     r8d, r8d
0x180015dd5  mov     dl, 1
0x180015dd7  lea     rcx, [rbp+90h+var_E8]
0x180015ddb  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015de0  nop
0x180015de1  mov     rcx, [rsp+190h+var_148]
0x180015de6  test    rcx, rcx
0x180015de9  jz      short loc_180015DFD
0x180015deb  mov     [rsp+190h+var_148], r12
0x180015df0  mov     rax, [rcx]
0x180015df3  mov     rax, [rax+10h]
0x180015df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dfc  nop
0x180015dfd  jmp     loc_1800166D7
0x180015e02  mov     al, [rsp+190h+var_140]
0x180015e06  mov     [r14+120h], al
0x180015e0d  mov     rdi, [rsp+190h+var_138]
0x180015e12  mov     rax, [rdi]
0x180015e15  mov     rbx, [rax+60h]
0x180015e19  mov     rcx, [rsp+190h+string]; string
0x180015e1e  call    cs:__imp_WindowsDeleteString
0x180015e25  nop     dword ptr [rax+rax+00h]
0x180015e2a  mov     [rsp+190h+string], r12
0x180015e2f  lea     rdx, [rsp+190h+string]
0x180015e34  mov     rcx, rdi
0x180015e37  mov     rax, rbx
0x180015e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e3f  mov     ebx, eax
0x180015e41  test    eax, eax
0x180015e43  jns     short loc_180015EBD
0x180015e45  lea     rsi, WPP_GLOBAL_Control
0x180015e4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e53  cmp     rcx, rsi
0x180015e56  jz      short loc_180015E77
0x180015e58  test    byte ptr [rcx+1Ch], 4
0x180015e5c  jz      short loc_180015E77
0x180015e5e  mov     edx, 32h ; '2'
0x180015e63  mov     r9d, eax
0x180015e66  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x180015e6d  mov     rcx, [rcx+10h]
0x180015e71  call    WPP_SF_d
0x180015e76  nop
0x180015e77  lea     rcx, [rsp+190h+var_138]
0x180015e7c  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180015e81  nop
0x180015e82  lea     rcx, [rsp+190h+var_130]
0x180015e87  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180015e8c  nop
0x180015e8d  xor     r8d, r8d
0x180015e90  mov     dl, 1
0x180015e92  lea     rcx, [rbp+90h+var_E8]
0x180015e96  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015e9b  nop
0x180015e9c  mov     rcx, [rsp+190h+var_148]
0x180015ea1  test    rcx, rcx
0x180015ea4  jz      short loc_180015EB8
0x180015ea6  mov     [rsp+190h+var_148], r12
0x180015eab  mov     rax, [rcx]
0x180015eae  mov     rax, [rax+10h]
0x180015eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eb7  nop
0x180015eb8  jmp     loc_1800166D7
0x180015ebd  lea     rdx, [rsp+190h+length]; length
0x180015ec2  mov     rcx, [rsp+190h+string]; string
0x180015ec7  call    cs:__imp_WindowsGetStringRawBuffer
0x180015ece  nop     dword ptr [rax+rax+00h]
0x180015ed3  mov     rdx, rax
0x180015ed6  mov     rcx, r14
0x180015ed9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180015ede  mov     rdi, [rsp+190h+var_138]
0x180015ee3  mov     rax, [rdi]
0x180015ee6  mov     rbx, [rax+30h]
0x180015eea  mov     rcx, [rsp+190h+string]; string
0x180015eef  call    cs:__imp_WindowsDeleteString
0x180015ef6  nop     dword ptr [rax+rax+00h]
0x180015efb  mov     [rsp+190h+string], r12
0x180015f00  lea     rdx, [rsp+190h+string]
0x180015f05  mov     rcx, rdi
0x180015f08  mov     rax, rbx
0x180015f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f10  mov     ebx, eax
0x180015f12  test    eax, eax
0x180015f14  jns     short loc_180015F8E
0x180015f16  lea     rsi, WPP_GLOBAL_Control
0x180015f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f24  cmp     rcx, rsi
0x180015f27  jz      short loc_180015F48
0x180015f29  test    byte ptr [rcx+1Ch], 4
0x180015f2d  jz      short loc_180015F48
0x180015f2f  mov     edx, 33h ; '3'
0x180015f34  mov     r9d, eax
0x180015f37  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x180015f3e  mov     rcx, [rcx+10h]
0x180015f42  call    WPP_SF_d
0x180015f47  nop
0x180015f48  lea     rcx, [rsp+190h+var_138]
0x180015f4d  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180015f52  nop
0x180015f53  lea     rcx, [rsp+190h+var_130]
0x180015f58  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180015f5d  nop
0x180015f5e  xor     r8d, r8d
0x180015f61  mov     dl, 1
0x180015f63  lea     rcx, [rbp+90h+var_E8]
0x180015f67  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015f6c  nop
0x180015f6d  mov     rcx, [rsp+190h+var_148]
0x180015f72  test    rcx, rcx
0x180015f75  jz      short loc_180015F89
0x180015f77  mov     [rsp+190h+var_148], r12
0x180015f7c  mov     rax, [rcx]
0x180015f7f  mov     rax, [rax+10h]
0x180015f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f88  nop
0x180015f89  jmp     loc_1800166D7
0x180015f8e  lea     rdx, [rsp+190h+length]; length
0x180015f93  mov     rcx, [rsp+190h+string]; string
0x180015f98  call    cs:__imp_WindowsGetStringRawBuffer
0x180015f9f  nop     dword ptr [rax+rax+00h]
0x180015fa4  lea     rcx, [r14+40h]
0x180015fa8  mov     rdx, rax
0x180015fab  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180015fb0  mov     rdi, [rsp+190h+var_138]
0x180015fb5  mov     rax, [rdi]
0x180015fb8  mov     rbx, [rax+50h]
0x180015fbc  mov     rcx, [rsp+190h+string]; string
0x180015fc1  call    cs:__imp_WindowsDeleteString
0x180015fc8  nop     dword ptr [rax+rax+00h]
0x180015fcd  mov     [rsp+190h+string], r12
0x180015fd2  lea     rdx, [rsp+190h+string]
0x180015fd7  mov     rcx, rdi
0x180015fda  mov     rax, rbx
0x180015fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fe2  mov     ebx, eax
0x180015fe4  test    eax, eax
0x180015fe6  jns     short loc_180016060
0x180015fe8  lea     rsi, WPP_GLOBAL_Control
0x180015fef  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ff6  cmp     rcx, rsi
0x180015ff9  jz      short loc_18001601A
0x180015ffb  test    byte ptr [rcx+1Ch], 4
0x180015fff  jz      short loc_18001601A
0x180016001  mov     edx, 34h ; '4'
0x180016006  mov     r9d, eax
0x180016009  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x180016010  mov     rcx, [rcx+10h]
0x180016014  call    WPP_SF_d
0x180016019  nop
0x18001601a  lea     rcx, [rsp+190h+var_138]
0x18001601f  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180016024  nop
0x180016025  lea     rcx, [rsp+190h+var_130]
0x18001602a  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x18001602f  nop
0x180016030  xor     r8d, r8d
0x180016033  mov     dl, 1
0x180016035  lea     rcx, [rbp+90h+var_E8]
0x180016039  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001603e  nop
0x18001603f  mov     rcx, [rsp+190h+var_148]
0x180016044  test    rcx, rcx
0x180016047  jz      short loc_18001605B
0x180016049  mov     [rsp+190h+var_148], r12
0x18001604e  mov     rax, [rcx]
0x180016051  mov     rax, [rax+10h]
0x180016055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001605a  nop
0x18001605b  jmp     loc_1800166D7
0x180016060  lea     rdx, [rsp+190h+length]; length
0x180016065  mov     rcx, [rsp+190h+string]; string
0x18001606a  call    cs:__imp_WindowsGetStringRawBuffer
0x180016071  nop     dword ptr [rax+rax+00h]
0x180016076  lea     rcx, [r14+60h]
0x18001607a  mov     rdx, rax
0x18001607d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180016082  mov     rcx, [rsp+190h+var_130]
0x180016087  mov     rax, [rcx]
0x18001608a  lea     rdx, [rsp+190h+var_13F]
0x18001608f  mov     rax, [rax+50h]
0x180016093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016098  mov     ebx, eax
0x18001609a  test    eax, eax
0x18001609c  jns     short loc_180016116
0x18001609e  lea     rsi, WPP_GLOBAL_Control
0x1800160a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800160ac  cmp     rcx, rsi
0x1800160af  jz      short loc_1800160D0
0x1800160b1  test    byte ptr [rcx+1Ch], 4
0x1800160b5  jz      short loc_1800160D0
0x1800160b7  mov     edx, 35h ; '5'
0x1800160bc  mov     r9d, eax
  ... truncated ...
```
