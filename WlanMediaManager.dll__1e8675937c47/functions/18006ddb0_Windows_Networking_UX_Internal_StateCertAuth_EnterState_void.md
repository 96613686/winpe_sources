# Windows::Networking::UX::Internal::StateCertAuth::EnterState(void)

- ea: `0x18006ddb0`
- end: `0x18006e3a6`
- name: `?EnterState@StateCertAuth@Internal@UX@Networking@Windows@@UEAAXXZ`
- size: `1526`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::StateCertAuth *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180003ed0`
- `0x180008e30`
- `0x18000de4c`
- `0x18001d4d4`
- `0x18006a4fc`
- `0x18006b280`
- `0x18006cc68`
- `0x18006d36c`
- `0x18006d584`
- `0x18006ddb0`
- `0x180085aec`
- `0x180085c2c`
- `0x180085dc0`
- `0x180085e9c`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18006df68`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18006df68`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18006df8b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18006dfa3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18006df8b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18006dfa3`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18006df21`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18006df47`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18006df21`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18006df47`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18006df34`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18006df5a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18006df34`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18006df5a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18006df7b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18006df7b`
- `CRYPT32!CertOpenSystemStoreW` at `0x18006de9d`
- `CRYPT32!CertOpenSystemStoreW` at `0x18006de9d`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18006dec1`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18006dec1`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18006e1c5`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18006e1c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Windows::Networking::UX::Internal::StateCertAuth::EnterState(
        Windows::Networking::UX::Internal::StateCertAuth *this)
{
  Windows::Networking::UX::Internal::StateCertAuth *v1; // r13
  __int64 v2; // rdx
  __int64 v3; // r8
  int v4; // eax
  __int64 v5; // rdx
  HCERTSTORE *v6; // r8
  PVOID *v7; // rcx
  const CERT_CONTEXT *v8; // r14
  int v9; // r15d
  HCERTSTORE v10; // rax
  PCCERT_CONTEXT v11; // rax
  unsigned int CertName; // eax
  unsigned int v13; // r12d
  unsigned int CertFriendlyName; // eax
  unsigned int v15; // eax
  int v16; // edx
  int v17; // r8d
  unsigned int v18; // eax
  int v19; // edx
  int v20; // r8d
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned __int16 *v23; // rdx
  int v24; // r12d
  const CERT_CONTEXT *v25; // rax
  const CERT_CONTEXT **v26; // rdx
  __int64 *v27; // rcx
  __int64 v28; // rax
  _BYTE v29[4]; // [rsp+40h] [rbp-D8h] BYREF
  int v30; // [rsp+44h] [rbp-D4h] BYREF
  Windows::Networking::UX::Internal::CWiFiCertSelectUIPrompt *v31; // [rsp+48h] [rbp-D0h] BYREF
  HCERTSTORE *v32; // [rsp+50h] [rbp-C8h]
  int v33; // [rsp+58h] [rbp-C0h]
  FILETIME FileTime; // [rsp+60h] [rbp-B8h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+68h] [rbp-B0h] BYREF
  FILETIME FileTime1; // [rsp+70h] [rbp-A8h] BYREF
  unsigned __int16 *v37; // [rsp+78h] [rbp-A0h] BYREF
  unsigned __int16 *v38; // [rsp+80h] [rbp-98h] BYREF
  unsigned __int16 *v39; // [rsp+88h] [rbp-90h] BYREF
  unsigned __int16 *v40; // [rsp+90h] [rbp-88h] BYREF
  unsigned __int16 *v41; // [rsp+98h] [rbp-80h] BYREF
  unsigned __int16 *v42; // [rsp+A0h] [rbp-78h] BYREF
  PCCERT_CONTEXT v43; // [rsp+A8h] [rbp-70h] BYREF
  const CERT_CONTEXT *v44; // [rsp+B0h] [rbp-68h]
  Windows::Networking::UX::Internal::StateCertAuth *v45; // [rsp+B8h] [rbp-60h]
  SYSTEMTIME v46; // [rsp+C0h] [rbp-58h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+D0h] [rbp-48h] BYREF
  struct _SYSTEMTIME v48; // [rsp+E0h] [rbp-38h] BYREF

  v1 = this;
  v45 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids);
  Windows::Networking::UX::Internal::StateBase::EnterState(v1);
  v31 = 0;
  v29[0] = 0;
  v30 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31, v2, v3);
  v4 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::Internal::CWiFiCertSelectUIPrompt,Windows::Networking::UX::Internal::CWiFiCertSelectUIPrompt,int,bool>(
         &v31,
         &v30,
         v29);
  if ( v4 < 0 )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids,
          (unsigned int)v4);
        goto LABEL_51;
      }
      goto LABEL_52;
    }
    goto LABEL_55;
  }
  v8 = 0;
  v9 = 0;
  v30 = 0;
  v10 = CertOpenSystemStoreW(0, L"my");
  v6 = (HCERTSTORE *)((char *)v1 + 240);
  v32 = (HCERTSTORE *)((char *)v1 + 240);
  *((_QWORD *)v1 + 30) = v10;
  if ( v10 )
  {
    while ( 1 )
    {
      v11 = CertEnumCertificatesInStore(*v6, v8);
      v8 = v11;
      v44 = v11;
      if ( !v11 )
      {
        v27 = (__int64 *)*((_QWORD *)v1 + 2);
        v28 = *v27;
        if ( v9 )
        {
          (*(void (__fastcall **)(__int64 *, Windows::Networking::UX::Internal::CWiFiCertSelectUIPrompt *))(v28 + 16))(
            v27,
            v31);
        }
        else
        {
          (*(void (__fastcall **)(__int64 *, __int64))(v28 + 288))(v27, 21);
          (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v1 + 2) + 8LL))(*((_QWORD *)v1 + 2), 14);
        }
LABEL_51:
        v7 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_52;
      }
      LocalFileTime = 0;
      FileTime = 0;
      FileTime1 = 0;
      SystemTime = 0;
      v48 = 0;
      v46 = 0;
      FileTimeToLocalFileTime(&v11->pCertInfo->NotBefore, &LocalFileTime);
      FileTimeToSystemTime(&LocalFileTime, &SystemTime);
      FileTimeToLocalFileTime(&v8->pCertInfo->NotAfter, &FileTime);
      FileTimeToSystemTime(&FileTime, &v48);
      GetLocalTime(&v46);
      SystemTimeToFileTime(&v46, &FileTime1);
      if ( CompareFileTime(&FileTime1, &FileTime) > 0 || CompareFileTime(&FileTime1, &LocalFileTime) < 0 )
        break;
      v42 = 0;
      v41 = 0;
      v40 = 0;
      v39 = 0;
      v38 = 0;
      v37 = 0;
      CertName = GetCertName(v8, &v42);
      v13 = CertName;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids, CertName);
      CertFriendlyName = GetCertFriendlyName(v8, 0, &v41);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          87,
          &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids,
          CertFriendlyName);
      v15 = GetCertFriendlyName(v8, 1u, &v40);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids, v15);
      v18 = FormatDateString(v8->pCertInfo->NotBefore, v16, v17, &v39);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids, v18);
      v21 = FormatDateString(v8->pCertInfo->NotAfter, v19, v20, &v38);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids, v21);
      v22 = FormatThumbprintString(v8, &v37);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids, v22);
      if ( !v13 || (v23 = v42) == 0 )
        v23 = v41;
      v24 = Windows::Networking::UX::Internal::CWiFiCertSelectUIPrompt::AddCertInfoEntry(
              v31,
              v23,
              (unsigned __int8)v39,
              v41,
              v40,
              v39,
              v38,
              v37);
      if ( v24 >= 0 )
      {
        v25 = CertDuplicateCertificateContext(v8);
        v43 = v25;
        if ( v25 )
        {
          v26 = (const CERT_CONTEXT **)*((_QWORD *)v1 + 32);
          if ( v26 == *((const CERT_CONTEXT ***)v1 + 33) )
          {
            try
            {
              std::vector<_CERT_CONTEXT const *>::_Emplace_reallocate<_CERT_CONTEXT const * const &>(
                (char *)v1 + 248,
                v26,
                &v43);
            }
            catch ( std::exception )
            {
              v33 = -2147024882;
              CertFreeCertificateContext(v43);
              v24 = v33;
              v8 = v44;
              v9 = v30;
              v1 = v45;
              goto LABEL_39;
            }
          }
          else
          {
            *v26 = v25;
            *((_QWORD *)v1 + 32) += 8LL;
          }
          v30 = ++v9;
        }
        else
        {
          v24 = -2147024882;
        }
      }
LABEL_39:
      CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&v37);
      CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&v38);
      CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&v39);
      CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&v40);
      CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&v41);
      CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&v42);
      v30 = v9;
      v6 = v32;
      if ( v24 < 0 )
      {
LABEL_42:
        v6 = v32;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            92,
            &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids,
            (unsigned int)v24);
          v6 = v32;
        }
      }
    }
    v24 = -2146762495;
    goto LABEL_42;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids);
      goto LABEL_51;
    }
LABEL_52:
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
      WPP_SF_(v7[2], 94, &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids);
  }
LABEL_55:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31, v5, v6);
}

```

## disassembly

```asm
0x18006ddb0  mov     [rsp+arg_8], rsi
0x18006ddb5  mov     [rsp+arg_10], r12
0x18006ddba  push    r13
0x18006ddbc  push    r14
0x18006ddbe  push    r15
0x18006ddc0  sub     rsp, 100h
0x18006ddc7  mov     rax, cs:__security_cookie
0x18006ddce  xor     rax, rsp
0x18006ddd1  mov     [rsp+118h+var_28], rax
0x18006ddd9  mov     r13, rcx
0x18006dddc  mov     [rsp+118h+var_60], rcx
0x18006dde4  lea     rsi, WPP_GLOBAL_Control
0x18006ddeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ddf2  cmp     rcx, rsi
0x18006ddf5  jz      short loc_18006DE12
0x18006ddf7  test    byte ptr [rcx+1Ch], 8
0x18006ddfb  jz      short loc_18006DE12
0x18006ddfd  mov     edx, 54h ; 'T'
0x18006de02  lea     r8, WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids
0x18006de09  mov     rcx, [rcx+10h]
0x18006de0d  call    WPP_SF_
0x18006de12  mov     rcx, r13; this
0x18006de15  call    ?EnterState@StateBase@Internal@UX@Networking@Windows@@UEAAXXZ; Windows::Networking::UX::Internal::StateBase::EnterState(void)
0x18006de1a  mov     [rsp+118h+var_D0], 0
0x18006de23  mov     [rsp+118h+var_D8], 0
0x18006de28  mov     [rsp+118h+var_D4], 0
0x18006de30  lea     rcx, [rsp+118h+var_D0]
0x18006de35  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006de3a  lea     r8, [rsp+118h+var_D8]
0x18006de3f  lea     rdx, [rsp+118h+var_D4]
0x18006de44  lea     rcx, [rsp+118h+var_D0]
0x18006de49  call    ??$MakeAndInitialize@VCWiFiCertSelectUIPrompt@Internal@UX@Networking@Windows@@V12345@H_N@Details@WRL@Microsoft@@YAJPEAPEAVCWiFiCertSelectUIPrompt@Internal@UX@Networking@Windows@@$$QEAH$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::Internal::CWiFiCertSelectUIPrompt,Windows::Networking::UX::Internal::CWiFiCertSelectUIPrompt,int,bool>(Windows::Networking::UX::Internal::CWiFiCertSelectUIPrompt * *,int &&,bool &&)
0x18006de4e  test    eax, eax
0x18006de50  jns     short loc_18006DE89
0x18006de52  mov     rcx, cs:WPP_GLOBAL_Control
0x18006de59  cmp     rcx, rsi
0x18006de5c  jz      loc_18006E372
0x18006de62  test    byte ptr [rcx+1Ch], 2
0x18006de66  jz      loc_18006E351
0x18006de6c  mov     edx, 55h ; 'U'
0x18006de71  mov     r9d, eax
0x18006de74  lea     r8, WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids
0x18006de7b  mov     rcx, [rcx+10h]
0x18006de7f  call    WPP_SF_d
0x18006de84  jmp     loc_18006E34A
0x18006de89  xor     r14d, r14d
0x18006de8c  xor     r15d, r15d
0x18006de8f  mov     [rsp+118h+var_D4], r15d
0x18006de94  lea     rdx, szSubsystemProtocol; "my"
0x18006de9b  xor     ecx, ecx; hProv
0x18006de9d  call    cs:__imp_CertOpenSystemStoreW
0x18006dea3  lea     r8, [r13+0F0h]
0x18006deaa  mov     [rsp+118h+var_C8], r8
0x18006deaf  mov     [r8], rax
0x18006deb2  test    rax, rax
0x18006deb5  jz      loc_18006E323
0x18006debb  mov     rdx, r14; pPrevCertContext
0x18006debe  mov     rcx, [r8]; hCertStore
0x18006dec1  call    cs:__imp_CertEnumCertificatesInStore
0x18006dec7  mov     r14, rax
0x18006deca  mov     [rsp+118h+var_68], rax
0x18006ded2  test    rax, rax
0x18006ded5  jz      loc_18006E2DF
0x18006dedb  mov     qword ptr [rsp+118h+LocalFileTime.dwLowDateTime], 0
0x18006dee4  mov     qword ptr [rsp+118h+FileTime.dwLowDateTime], 0
0x18006deed  mov     qword ptr [rsp+118h+FileTime1.dwLowDateTime], 0
0x18006def6  xorps   xmm0, xmm0
0x18006def9  movups  xmmword ptr [rsp+118h+SystemTime.wYear], xmm0
0x18006df01  xorps   xmm1, xmm1
0x18006df04  movups  xmmword ptr [rsp+118h+var_38.wYear], xmm1
0x18006df0c  movups  xmmword ptr [rsp+118h+var_58.wYear], xmm0
0x18006df14  mov     rcx, [rax+18h]
0x18006df18  add     rcx, 40h ; '@'; lpFileTime
0x18006df1c  lea     rdx, [rsp+118h+LocalFileTime]; lpLocalFileTime
0x18006df21  call    cs:__imp_FileTimeToLocalFileTime
0x18006df27  lea     rdx, [rsp+118h+SystemTime]; lpSystemTime
0x18006df2f  lea     rcx, [rsp+118h+LocalFileTime]; lpFileTime
0x18006df34  call    cs:__imp_FileTimeToSystemTime
0x18006df3a  mov     rcx, [r14+18h]
0x18006df3e  add     rcx, 48h ; 'H'; lpFileTime
0x18006df42  lea     rdx, [rsp+118h+FileTime]; lpLocalFileTime
0x18006df47  call    cs:__imp_FileTimeToLocalFileTime
0x18006df4d  lea     rdx, [rsp+118h+var_38]; lpSystemTime
0x18006df55  lea     rcx, [rsp+118h+FileTime]; lpFileTime
0x18006df5a  call    cs:__imp_FileTimeToSystemTime
0x18006df60  lea     rcx, [rsp+118h+var_58]; lpSystemTime
0x18006df68  call    cs:__imp_GetLocalTime
0x18006df6e  lea     rdx, [rsp+118h+FileTime1]; lpFileTime
0x18006df73  lea     rcx, [rsp+118h+var_58]; lpSystemTime
0x18006df7b  call    cs:__imp_SystemTimeToFileTime
0x18006df81  lea     rdx, [rsp+118h+FileTime]; lpFileTime2
0x18006df86  lea     rcx, [rsp+118h+FileTime1]; lpFileTime1
0x18006df8b  call    cs:__imp_CompareFileTime
0x18006df91  test    eax, eax
0x18006df93  jg      loc_18006E298
0x18006df99  lea     rdx, [rsp+118h+LocalFileTime]; lpFileTime2
0x18006df9e  lea     rcx, [rsp+118h+FileTime1]; lpFileTime1
0x18006dfa3  call    cs:__imp_CompareFileTime
0x18006dfa9  test    eax, eax
0x18006dfab  js      loc_18006E298
0x18006dfb1  mov     [rsp+118h+var_78], 0
0x18006dfbd  mov     [rsp+118h+var_80], 0
0x18006dfc9  mov     [rsp+118h+var_88], 0
0x18006dfd5  mov     [rsp+118h+var_90], 0
0x18006dfe1  mov     [rsp+118h+var_98], 0
0x18006dfed  mov     [rsp+118h+var_A0], 0
0x18006dff6  lea     rdx, [rsp+118h+var_78]; unsigned __int16 **
0x18006dffe  mov     rcx, r14; struct _CERT_CONTEXT *
0x18006e001  call    ?GetCertName@@YAHPEBU_CERT_CONTEXT@@PEAPEAG@Z; GetCertName(_CERT_CONTEXT const *,ushort * *)
0x18006e006  mov     r12d, eax
0x18006e009  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e010  cmp     rcx, rsi
0x18006e013  jz      short loc_18006E033
0x18006e015  test    byte ptr [rcx+1Ch], 8
0x18006e019  jz      short loc_18006E033
0x18006e01b  mov     edx, 56h ; 'V'
0x18006e020  mov     r9d, eax
0x18006e023  lea     r8, WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids
0x18006e02a  mov     rcx, [rcx+10h]
0x18006e02e  call    WPP_SF_d
0x18006e033  lea     r8, [rsp+118h+var_80]; unsigned __int16 **
0x18006e03b  xor     edx, edx; dwFlags
0x18006e03d  mov     rcx, r14; pCertContext
0x18006e040  call    ?GetCertFriendlyName@@YAHPEBU_CERT_CONTEXT@@KPEAPEAG@Z; GetCertFriendlyName(_CERT_CONTEXT const *,ulong,ushort * *)
0x18006e045  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e04c  cmp     rcx, rsi
0x18006e04f  jz      short loc_18006E06F
0x18006e051  test    byte ptr [rcx+1Ch], 8
0x18006e055  jz      short loc_18006E06F
0x18006e057  mov     edx, 57h ; 'W'
0x18006e05c  mov     r9d, eax
0x18006e05f  lea     r8, WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids
0x18006e066  mov     rcx, [rcx+10h]
0x18006e06a  call    WPP_SF_d
0x18006e06f  lea     r8, [rsp+118h+var_88]; unsigned __int16 **
0x18006e077  mov     edx, 1; dwFlags
0x18006e07c  mov     rcx, r14; pCertContext
0x18006e07f  call    ?GetCertFriendlyName@@YAHPEBU_CERT_CONTEXT@@KPEAPEAG@Z; GetCertFriendlyName(_CERT_CONTEXT const *,ulong,ushort * *)
0x18006e084  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e08b  cmp     rcx, rsi
0x18006e08e  jz      short loc_18006E0AE
0x18006e090  test    byte ptr [rcx+1Ch], 8
0x18006e094  jz      short loc_18006E0AE
0x18006e096  mov     edx, 58h ; 'X'
0x18006e09b  mov     r9d, eax
0x18006e09e  lea     r8, WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids
0x18006e0a5  mov     rcx, [rcx+10h]
0x18006e0a9  call    WPP_SF_d
0x18006e0ae  mov     rcx, [r14+18h]
0x18006e0b2  lea     r9, [rsp+118h+var_90]; unsigned __int16 **
0x18006e0ba  mov     rcx, [rcx+40h]; struct _FILETIME
0x18006e0be  call    ?FormatDateString@@YAHU_FILETIME@@HHPEAPEAG@Z; FormatDateString(_FILETIME,int,int,ushort * *)
0x18006e0c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e0ca  cmp     rcx, rsi
0x18006e0cd  jz      short loc_18006E0ED
0x18006e0cf  test    byte ptr [rcx+1Ch], 8
0x18006e0d3  jz      short loc_18006E0ED
0x18006e0d5  mov     edx, 59h ; 'Y'
0x18006e0da  mov     r9d, eax
0x18006e0dd  lea     r8, WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids
0x18006e0e4  mov     rcx, [rcx+10h]
0x18006e0e8  call    WPP_SF_d
0x18006e0ed  mov     rcx, [r14+18h]
0x18006e0f1  lea     r9, [rsp+118h+var_98]; unsigned __int16 **
0x18006e0f9  mov     rcx, [rcx+48h]; struct _FILETIME
0x18006e0fd  call    ?FormatDateString@@YAHU_FILETIME@@HHPEAPEAG@Z; FormatDateString(_FILETIME,int,int,ushort * *)
0x18006e102  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e109  cmp     rcx, rsi
0x18006e10c  jz      short loc_18006E12C
0x18006e10e  test    byte ptr [rcx+1Ch], 8
0x18006e112  jz      short loc_18006E12C
0x18006e114  mov     edx, 5Ah ; 'Z'
0x18006e119  mov     r9d, eax
0x18006e11c  lea     r8, WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids
0x18006e123  mov     rcx, [rcx+10h]
0x18006e127  call    WPP_SF_d
0x18006e12c  lea     rdx, [rsp+118h+var_A0]; unsigned __int16 **
0x18006e131  mov     rcx, r14; struct _CERT_CONTEXT *
0x18006e134  call    ?FormatThumbprintString@@YAHPEBU_CERT_CONTEXT@@PEAPEAG@Z; FormatThumbprintString(_CERT_CONTEXT const *,ushort * *)
0x18006e139  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e140  cmp     rcx, rsi
0x18006e143  jz      short loc_18006E163
0x18006e145  test    byte ptr [rcx+1Ch], 8
0x18006e149  jz      short loc_18006E163
0x18006e14b  mov     edx, 5Bh ; '['
0x18006e150  mov     r9d, eax
0x18006e153  lea     r8, WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids
0x18006e15a  mov     rcx, [rcx+10h]
0x18006e15e  call    WPP_SF_d
0x18006e163  mov     rax, [rsp+118h+var_A0]
0x18006e168  mov     rcx, [rsp+118h+var_98]
0x18006e170  mov     r8, [rsp+118h+var_90]; unsigned __int8
0x18006e178  mov     r10, [rsp+118h+var_88]
0x18006e180  mov     r9, [rsp+118h+var_80]; unsigned __int16 *
0x18006e188  test    r12d, r12d
0x18006e18b  jz      short loc_18006E19A
0x18006e18d  mov     rdx, [rsp+118h+var_78]
0x18006e195  test    rdx, rdx
0x18006e198  jnz     short loc_18006E19D
0x18006e19a  mov     rdx, r9; unsigned __int16 *
0x18006e19d  mov     [rsp+118h+var_E0], rax; unsigned __int16 *
0x18006e1a2  mov     [rsp+118h+var_E8], rcx; unsigned __int16 *
0x18006e1a7  mov     [rsp+118h+var_F0], r8; unsigned __int16 *
0x18006e1ac  mov     [rsp+118h+var_F8], r10; unsigned __int16 *
0x18006e1b1  mov     rcx, [rsp+118h+var_D0]; this
0x18006e1b6  call    ?AddCertInfoEntry@CWiFiCertSelectUIPrompt@Internal@UX@Networking@Windows@@QEAAJPEBGE00000@Z; Windows::Networking::UX::Internal::CWiFiCertSelectUIPrompt::AddCertInfoEntry(ushort const *,uchar,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18006e1bb  mov     r12d, eax
0x18006e1be  test    eax, eax
0x18006e1c0  js      short loc_18006E233
0x18006e1c2  mov     rcx, r14; pCertContext
0x18006e1c5  call    cs:__imp_CertDuplicateCertificateContext
0x18006e1cb  mov     [rsp+118h+var_70], rax
0x18006e1d3  test    rax, rax
0x18006e1d6  jz      short loc_18006E22D
0x18006e1d8  lea     rcx, [r13+0F8h]
0x18006e1df  mov     rdx, [rcx+8]
0x18006e1e3  cmp     rdx, [rcx+10h]
0x18006e1e7  jz      short loc_18006E1F3
0x18006e1e9  mov     [rdx], rax
0x18006e1ec  add     qword ptr [rcx+8], 8
0x18006e1f1  jmp     short loc_18006E200
0x18006e1f3  lea     r8, [rsp+118h+var_70]
0x18006e1fb  call    ??$_Emplace_reallocate@AEBQEBU_CERT_CONTEXT@@@?$vector@PEBU_CERT_CONTEXT@@V?$allocator@PEBU_CERT_CONTEXT@@@std@@@std@@AEAAPEAPEBU_CERT_CONTEXT@@QEAPEBU2@AEBQEBU2@@Z; std::vector<_CERT_CONTEXT const *>::_Emplace_reallocate<_CERT_CONTEXT const * const &>(_CERT_CONTEXT const * * const,_CERT_CONTEXT const * const &)
0x18006e200  inc     r15d
0x18006e203  mov     [rsp+118h+var_D4], r15d
0x18006e208  jmp     short loc_18006E233
0x18006e20a  lea     rsi, WPP_GLOBAL_Control
0x18006e211  mov     r12d, [rsp+118h+var_C0]
0x18006e216  mov     r14, [rsp+118h+var_68]
0x18006e21e  mov     r15d, [rsp+118h+var_D4]
0x18006e223  mov     r13, [rsp+118h+var_60]
0x18006e22b  jmp     short loc_18006E233
0x18006e22d  mov     r12d, 8007000Eh
0x18006e233  lea     rcx, [rsp+118h+var_A0]
0x18006e238  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x18006e23d  nop
0x18006e23e  lea     rcx, [rsp+118h+var_98]
0x18006e246  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x18006e24b  nop
0x18006e24c  lea     rcx, [rsp+118h+var_90]
0x18006e254  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x18006e259  nop
0x18006e25a  lea     rcx, [rsp+118h+var_88]
0x18006e262  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x18006e267  nop
0x18006e268  lea     rcx, [rsp+118h+var_80]
0x18006e270  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x18006e275  nop
0x18006e276  lea     rcx, [rsp+118h+var_78]
0x18006e27e  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x18006e283  mov     [rsp+118h+var_D4], r15d
0x18006e288  test    r12d, r12d
0x18006e28b  mov     r8, [rsp+118h+var_C8]
0x18006e290  jns     loc_18006DEBB
0x18006e296  jmp     short loc_18006E29E
0x18006e298  mov     r12d, 800B0101h
0x18006e29e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e2a5  cmp     rcx, rsi
0x18006e2a8  mov     r8, [rsp+118h+var_C8]
0x18006e2ad  jz      loc_18006DEBB
0x18006e2b3  test    byte ptr [rcx+1Ch], 2
0x18006e2b7  jz      loc_18006DEBB
0x18006e2bd  mov     edx, 5Ch ; '\'
0x18006e2c2  mov     r9d, r12d
0x18006e2c5  lea     r8, WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids
0x18006e2cc  mov     rcx, [rcx+10h]
0x18006e2d0  call    WPP_SF_d
0x18006e2d5  mov     r8, [rsp+118h+var_C8]
0x18006e2da  jmp     loc_18006DEBB
0x18006e2df  mov     rcx, [r13+10h]
0x18006e2e3  mov     rax, [rcx]
0x18006e2e6  test    r15d, r15d
0x18006e2e9  jz      short loc_18006E2FB
0x18006e2eb  mov     rdx, [rsp+118h+var_D0]
0x18006e2f0  mov     rax, [rax+10h]
0x18006e2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e2f9  jmp     short loc_18006E34A
0x18006e2fb  mov     edx, 15h
0x18006e300  mov     rax, [rax+120h]
0x18006e307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e30c  mov     rcx, [r13+10h]
0x18006e310  mov     rax, [rcx]
0x18006e313  mov     edx, 0Eh
0x18006e318  mov     rax, [rax+8]
0x18006e31c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e321  jmp     short loc_18006E34A
0x18006e323  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e32a  cmp     rcx, rsi
0x18006e32d  jz      short loc_18006E372
0x18006e32f  test    byte ptr [rcx+1Ch], 2
0x18006e333  jz      short loc_18006E351
0x18006e335  mov     edx, 5Dh ; ']'
0x18006e33a  lea     r8, WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids
0x18006e341  mov     rcx, [rcx+10h]
0x18006e345  call    WPP_SF_
0x18006e34a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e351  cmp     rcx, rsi
0x18006e354  jz      short loc_18006E372
0x18006e356  test    byte ptr [rcx+1Ch], 8
0x18006e35a  jz      short loc_18006E372
  ... truncated ...
```
