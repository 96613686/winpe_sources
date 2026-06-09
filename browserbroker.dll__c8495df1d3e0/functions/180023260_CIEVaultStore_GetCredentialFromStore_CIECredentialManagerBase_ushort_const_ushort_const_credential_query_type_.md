# CIEVaultStore::GetCredentialFromStore(CIECredentialManagerBase *,ushort const *,ushort const *,credential_query_type,_WEBCREDENTIAL * *)

- ea: `0x180023260`
- end: `0x1800235b1`
- name: `?GetCredentialFromStore@CIEVaultStore@@QEAAJPEAVCIECredentialManagerBase@@PEBG1W4credential_query_type@@PEAPEAU_WEBCREDENTIAL@@@Z`
- size: `849`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180023190`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x18000a4d0`
- `0x18001bf70`
- `0x180021b50`
- `0x180021ef0`
- `0x1800222b4`
- `0x1800225cc`
- `0x1800228a8`
- `0x180022fc0`
- `0x180023260`
- `0x180023bec`
- `0x180023d70`
- `0x180023df8`
- `0x18002b4e0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800233ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800233e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023425`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023537`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002354f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800233ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800233e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023425`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023537`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002354f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800234ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800234bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800234cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800234ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800234bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800234cc`
- `OLEAUT32!__imp_SysFreeString` at `0x180023586`
- `OLEAUT32!__imp_SysFreeString` at `0x180023586`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CIEVaultStore::GetCredentialFromStore(
        __int64 a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        HSTRING a4,
        unsigned int a5,
        __int64 *a6)
{
  int v8; // ebx
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, PVOID, PVOID, struct ABI::Windows::Security::Credentials::IPasswordCredential **); // rdi
  PVOID Reserved1; // rbx
  HSTRING_HEADER *v12; // rax
  __int64 v13; // r15
  __int64 v14; // r14
  struct ABI::Windows::Security::Credentials::IPasswordCredential *v15; // rdi
  __int64 (__fastcall *v16)(struct ABI::Windows::Security::Credentials::IPasswordCredential *, HSTRING *); // rbx
  struct ABI::Windows::Security::Credentials::IPasswordCredential *v17; // rdi
  __int64 (__fastcall *v18)(struct ABI::Windows::Security::Credentials::IPasswordCredential *, HSTRING *); // rbx
  struct ABI::Windows::Security::Credentials::IPasswordCredential *v19; // rdi
  __int64 (__fastcall *v20)(struct ABI::Windows::Security::Credentials::IPasswordCredential *, HSTRING *); // rbx
  bool v21; // al
  unsigned int v22; // edx
  unsigned int v23; // esi
  const unsigned __int16 *StringRawBuffer; // rdi
  const unsigned __int16 *v25; // rbx
  const unsigned __int16 *v26; // rax
  int v28; // [rsp+30h] [rbp-D0h] BYREF
  struct ABI::Windows::Security::Credentials::IPasswordCredential *v29; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v30; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v32; // [rsp+50h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING_HEADER v34; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING_HEADER v35; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v36[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v37; // [rsp+C0h] [rbp-40h]
  char v38; // [rsp+C8h] [rbp-38h]
  _BYTE v39[4174]; // [rsp+CAh] [rbp-36h] BYREF
  __int64 v40; // [rsp+1118h] [rbp+1018h]
  int v41; // [rsp+1120h] [rbp+1020h]

  v30 = a4;
  bstrString = 0;
  v8 = CleanUri(a3, &bstrString);
  v28 = v8;
  if ( v8 >= 0 )
  {
    v29 = 0;
    v9 = *(_QWORD *)(a1 + 520);
    v10 = *(__int64 (__fastcall **)(__int64, PVOID, PVOID, struct ABI::Windows::Security::Credentials::IPasswordCredential **))(*(_QWORD *)v9 + 64LL);
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v29);
    Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v34, (const WCHAR **)&v30)[1].Reserved.Reserved1;
    v30 = (HSTRING)bstrString;
    v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v35, (const WCHAR **)&v30);
    v8 = v10(v9, v12[1].Reserved.Reserved1, Reserved1, &v29);
    v28 = v8;
    if ( v8 >= 0 )
    {
      if ( IsIECredential(v29) )
      {
        v13 = *(_QWORD *)(a2 + 16);
        *(_OWORD *)&v34.Reserved.Reserved1 = a2;
        *(_DWORD *)&v34.Reserved.Reserved2[16] = 1;
        v14 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 16LL))(v13, 40);
        CAutoIECredential<CIECredentialManager>::Free(&v34);
        *(_QWORD *)&v34.Reserved.Reserved2[8] = v14;
        *(_DWORD *)&v34.Reserved.Reserved2[16] = 1;
        if ( v14 )
        {
          v30 = 0;
          v15 = v29;
          v16 = *(__int64 (__fastcall **)(struct ABI::Windows::Security::Credentials::IPasswordCredential *, HSTRING *))(*(_QWORD *)v29 + 48LL);
          WindowsDeleteString(0);
          v30 = 0;
          v8 = v16(v15, &v30);
          v28 = v8;
          if ( v8 >= 0 )
          {
            v32 = 0;
            v17 = v29;
            v18 = *(__int64 (__fastcall **)(struct ABI::Windows::Security::Credentials::IPasswordCredential *, HSTRING *))(*(_QWORD *)v29 + 64LL);
            WindowsDeleteString(0);
            v32 = 0;
            v8 = v18(v17, &v32);
            v28 = v8;
            if ( v8 >= 0 )
            {
              string = 0;
              v19 = v29;
              v20 = *(__int64 (__fastcall **)(struct ABI::Windows::Security::Credentials::IPasswordCredential *, HSTRING *))(*(_QWORD *)v29 + 80LL);
              WindowsDeleteString(0);
              string = 0;
              v8 = v20(v19, &string);
              v28 = v8;
              if ( v8 >= 0 )
              {
                v21 = IsHiddenCredential(v29);
                if ( (unsigned __int8)DoesCredentialMatchHiddenType(a5, v21) )
                {
                  v23 = v22;
                  v38 = 0;
                  v40 = 0;
                  v41 = 0;
                  memset(v36, 0, sizeof(v36));
                  v37 = 0;
                  memset_0(v39, 0, 0x1048u);
                  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                  v25 = WindowsGetStringRawBuffer(v32, 0);
                  v26 = WindowsGetStringRawBuffer(v30, 0);
                  v8 = CIESecureCredential::InitializeFromStrings(
                         (CIESecureCredential *)v36,
                         v26,
                         v25,
                         StringRawBuffer,
                         v23,
                         0);
                  v28 = v8;
                  if ( v8 >= 0 )
                  {
                    v8 = CopyIECredential(v13, v36, v14);
                    v28 = v8;
                    if ( v8 >= 0 )
                    {
                      *(_QWORD *)&v34.Reserved.Reserved2[8] = 0;
                      *(_DWORD *)&v34.Reserved.Reserved2[16] = 0;
                      *a6 = v14;
                    }
                  }
                  CIESecureCredential::~CIESecureCredential((CIESecureCredential *)v36);
                }
                else
                {
                  v8 = -2147023728;
                  v28 = -2147023728;
                }
              }
              WindowsDeleteString(string);
            }
            WindowsDeleteString(v32);
          }
          WindowsDeleteString(v30);
        }
        else
        {
          v8 = -2147024882;
          v28 = -2147024882;
        }
        CAutoIECredential<CIECredentialManager>::Free(&v34);
      }
      else
      {
        v8 = -2147023728;
        v28 = -2147023728;
      }
    }
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v29);
  }
  BrowserTelemetry::CredentialGetFromStoreCompleted<long &>((__int64)&v28);
  SysFreeString(bstrString);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180023260  push    rbp
0x180023262  push    rbx
0x180023263  push    rsi
0x180023264  push    rdi
0x180023265  push    r12
0x180023267  push    r13
0x180023269  push    r14
0x18002326b  push    r15
0x18002326d  lea     rbp, [rsp-1048h]
0x180023275  mov     eax, 1148h
0x18002327a  call    _alloca_probe
0x18002327f  sub     rsp, rax
0x180023282  mov     rax, cs:__security_cookie
0x180023289  xor     rax, rsp
0x18002328c  mov     [rbp+1080h+var_50], rax
0x180023293  mov     r14, rdx
0x180023296  mov     rsi, rcx
0x180023299  mov     [rsp+1180h+var_1140], r9
0x18002329e  mov     r12, [rbp+1080h+arg_28]
0x1800232a5  xor     r13d, r13d
0x1800232a8  mov     [rsp+1180h+bstrString], r13
0x1800232ad  lea     rdx, [rsp+1180h+bstrString]; unsigned __int16 **
0x1800232b2  mov     rcx, r8; unsigned __int16 *
0x1800232b5  call    ?CleanUri@@YAJPEBGPEAPEAG@Z; CleanUri(ushort const *,ushort * *)
0x1800232ba  mov     ebx, eax
0x1800232bc  mov     [rsp+1180h+var_1150], eax
0x1800232c0  test    eax, eax
0x1800232c2  js      loc_180023576
0x1800232c8  mov     [rsp+1180h+var_1148], r13
0x1800232cd  mov     rsi, [rsi+208h]
0x1800232d4  mov     rax, [rsi]
0x1800232d7  mov     rdi, [rax+40h]
0x1800232db  lea     rcx, [rsp+1180h+var_1148]
0x1800232e0  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x1800232e5  lea     rdx, [rsp+1180h+var_1140]
0x1800232ea  lea     rcx, [rsp+1180h+var_1120]
0x1800232ef  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800232f4  nop
0x1800232f5  mov     rbx, [rax+18h]
0x1800232f9  mov     rdx, [rsp+1180h+bstrString]
0x1800232fe  mov     [rsp+1180h+var_1140], rdx
0x180023303  lea     rdx, [rsp+1180h+var_1140]
0x180023308  lea     rcx, [rbp+1080h+var_1100]
0x18002330c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180023311  nop
0x180023312  lea     r9, [rsp+1180h+var_1148]
0x180023317  mov     r8, rbx
0x18002331a  mov     rdx, [rax+18h]
0x18002331e  mov     rcx, rsi
0x180023321  mov     rax, rdi
0x180023324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023329  mov     ebx, eax
0x18002332b  mov     [rsp+1180h+var_1150], eax
0x18002332f  test    eax, eax
0x180023331  js      loc_18002356C
0x180023337  mov     rcx, [rsp+1180h+var_1148]; struct ABI::Windows::Security::Credentials::IPasswordCredential *
0x18002333c  call    ?IsIECredential@@YA_NPEAUIPasswordCredential@Credentials@Security@Windows@ABI@@@Z; IsIECredential(ABI::Windows::Security::Credentials::IPasswordCredential *)
0x180023341  test    al, al
0x180023343  jz      loc_180023563
0x180023349  mov     r15, [r14+10h]
0x18002334d  mov     [rsp+1180h+var_1120], r14
0x180023352  mov     [rsp+1180h+var_1118], r13
0x180023357  lea     ebx, [r13+1]
0x18002335b  mov     [rsp+1180h+var_1110], ebx
0x18002335f  mov     rax, [r15]
0x180023362  lea     edx, [rbx+27h]
0x180023365  mov     rcx, r15
0x180023368  mov     rax, [rax+10h]
0x18002336c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023371  mov     r14, rax
0x180023374  lea     rcx, [rsp+1180h+var_1120]
0x180023379  call    ?Free@?$CAutoIECredential@VCIECredentialManager@@@@AEAAXXZ; CAutoIECredential<CIECredentialManager>::Free(void)
0x18002337e  mov     [rsp+1180h+var_1118], r14
0x180023383  mov     [rsp+1180h+var_1110], ebx
0x180023387  test    r14, r14
0x18002338a  jnz     short loc_18002339A
0x18002338c  mov     ebx, 8007000Eh
0x180023391  mov     [rsp+1180h+var_1150], ebx
0x180023395  jmp     loc_180023556
0x18002339a  mov     [rsp+1180h+var_1140], r13
0x18002339f  mov     rdi, [rsp+1180h+var_1148]
0x1800233a4  mov     rax, [rdi]
0x1800233a7  mov     rbx, [rax+30h]
0x1800233ab  xor     ecx, ecx; string
0x1800233ad  call    cs:__imp_WindowsDeleteString
0x1800233b3  mov     [rsp+1180h+var_1140], r13
0x1800233b8  lea     rdx, [rsp+1180h+var_1140]
0x1800233bd  mov     rcx, rdi
0x1800233c0  mov     rax, rbx
0x1800233c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233c8  mov     ebx, eax
0x1800233ca  mov     [rsp+1180h+var_1150], eax
0x1800233ce  test    eax, eax
0x1800233d0  js      loc_18002354A
0x1800233d6  mov     [rsp+1180h+var_1130], r13
0x1800233db  mov     rdi, [rsp+1180h+var_1148]
0x1800233e0  mov     rax, [rdi]
0x1800233e3  mov     rbx, [rax+40h]
0x1800233e7  xor     ecx, ecx; string
0x1800233e9  call    cs:__imp_WindowsDeleteString
0x1800233ef  mov     [rsp+1180h+var_1130], r13
0x1800233f4  lea     rdx, [rsp+1180h+var_1130]
0x1800233f9  mov     rcx, rdi
0x1800233fc  mov     rax, rbx
0x1800233ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023404  mov     ebx, eax
0x180023406  mov     [rsp+1180h+var_1150], eax
0x18002340a  test    eax, eax
0x18002340c  js      loc_18002353E
0x180023412  mov     [rsp+1180h+string], r13
0x180023417  mov     rdi, [rsp+1180h+var_1148]
0x18002341c  mov     rax, [rdi]
0x18002341f  mov     rbx, [rax+50h]
0x180023423  xor     ecx, ecx; string
0x180023425  call    cs:__imp_WindowsDeleteString
0x18002342b  mov     [rsp+1180h+string], r13
0x180023430  lea     rdx, [rsp+1180h+string]
0x180023435  mov     rcx, rdi
0x180023438  mov     rax, rbx
0x18002343b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023440  mov     ebx, eax
0x180023442  mov     [rsp+1180h+var_1150], eax
0x180023446  test    eax, eax
0x180023448  js      loc_180023532
0x18002344e  mov     rcx, [rsp+1180h+var_1148]; struct ABI::Windows::Security::Credentials::IPasswordCredential *
0x180023453  call    ?IsHiddenCredential@@YA_NPEAUIPasswordCredential@Credentials@Security@Windows@ABI@@@Z; IsHiddenCredential(ABI::Windows::Security::Credentials::IPasswordCredential *)
0x180023458  movzx   edx, al
0x18002345b  mov     ecx, [rbp+1080h+arg_20]
0x180023461  call    ?DoesCredentialMatchHiddenType@@YA_NW4credential_query_type@@_N@Z; DoesCredentialMatchHiddenType(credential_query_type,bool)
0x180023466  test    al, al
0x180023468  jz      loc_180023529
0x18002346e  mov     esi, edx
0x180023470  mov     [rbp+1080h+var_10B8], r13b
0x180023474  mov     [rbp+1080h+var_68], r13
0x18002347b  mov     [rbp+1080h+var_60], r13d
0x180023482  xorps   xmm0, xmm0
0x180023485  xor     eax, eax
0x180023487  movups  [rbp+1080h+var_10E0], xmm0
0x18002348b  movups  [rbp+1080h+var_10D0], xmm0
0x18002348f  mov     [rbp+1080h+var_10C0], rax
0x180023493  xor     edx, edx; Val
0x180023495  mov     r8d, 1048h; Size
0x18002349b  lea     rcx, [rbp+1080h+var_10B6]; void *
0x18002349f  call    memset_0
0x1800234a4  nop
0x1800234a5  xor     edx, edx; length
0x1800234a7  mov     rcx, [rsp+1180h+string]; string
0x1800234ac  call    cs:__imp_WindowsGetStringRawBuffer
0x1800234b2  mov     rdi, rax
0x1800234b5  xor     edx, edx; length
0x1800234b7  mov     rcx, [rsp+1180h+var_1130]; string
0x1800234bc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800234c2  mov     rbx, rax
0x1800234c5  xor     edx, edx; length
0x1800234c7  mov     rcx, [rsp+1180h+var_1140]; string
0x1800234cc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800234d2  mov     [rsp+1180h+var_1158], r13d; int
0x1800234d7  mov     [rsp+1180h+var_1160], esi; unsigned int
0x1800234db  mov     r9, rdi; unsigned __int16 *
0x1800234de  mov     r8, rbx; unsigned __int16 *
0x1800234e1  mov     rdx, rax; unsigned __int16 *
0x1800234e4  lea     rcx, [rbp+1080h+var_10E0]; this
0x1800234e8  call    ?InitializeFromStrings@CIESecureCredential@@QEAAJPEBG00KH@Z; CIESecureCredential::InitializeFromStrings(ushort const *,ushort const *,ushort const *,ulong,int)
0x1800234ed  mov     ebx, eax
0x1800234ef  mov     [rsp+1180h+var_1150], eax
0x1800234f3  test    eax, eax
0x1800234f5  js      short loc_18002351E
0x1800234f7  mov     r8, r14
0x1800234fa  lea     rdx, [rbp+1080h+var_10E0]
0x1800234fe  mov     rcx, r15
0x180023501  call    CopyIECredential
0x180023506  mov     ebx, eax
0x180023508  mov     [rsp+1180h+var_1150], eax
0x18002350c  test    eax, eax
0x18002350e  js      short loc_18002351E
0x180023510  mov     [rsp+1180h+var_1118], r13
0x180023515  mov     [rsp+1180h+var_1110], r13d
0x18002351a  mov     [r12], r14
0x18002351e  lea     rcx, [rbp+1080h+var_10E0]; this
0x180023522  call    ??1CIESecureCredential@@QEAA@XZ; CIESecureCredential::~CIESecureCredential(void)
0x180023527  jmp     short loc_180023532
0x180023529  mov     ebx, 80070490h
0x18002352e  mov     [rsp+1180h+var_1150], ebx
0x180023532  mov     rcx, [rsp+1180h+string]; string
0x180023537  call    cs:__imp_WindowsDeleteString
0x18002353d  nop
0x18002353e  mov     rcx, [rsp+1180h+var_1130]; string
0x180023543  call    cs:__imp_WindowsDeleteString
0x180023549  nop
0x18002354a  mov     rcx, [rsp+1180h+var_1140]; string
0x18002354f  call    cs:__imp_WindowsDeleteString
0x180023555  nop
0x180023556  lea     rcx, [rsp+1180h+var_1120]
0x18002355b  call    ?Free@?$CAutoIECredential@VCIECredentialManager@@@@AEAAXXZ; CAutoIECredential<CIECredentialManager>::Free(void)
0x180023560  nop
0x180023561  jmp     short loc_18002356C
0x180023563  mov     ebx, 80070490h
0x180023568  mov     [rsp+1180h+var_1150], ebx
0x18002356c  lea     rcx, [rsp+1180h+var_1148]
0x180023571  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180023576  lea     rcx, [rsp+1180h+var_1150]
0x18002357b  call    ??$CredentialGetFromStoreCompleted@AEAJ@BrowserTelemetry@@SAXAEAJ@Z; BrowserTelemetry::CredentialGetFromStoreCompleted<long &>(long &)
0x180023580  nop
0x180023581  mov     rcx, [rsp+1180h+bstrString]; bstrString
0x180023586  call    cs:__imp_SysFreeString
0x18002358c  mov     eax, ebx
0x18002358e  mov     rcx, [rbp+1080h+var_50]
0x180023595  xor     rcx, rsp; StackCookie
0x180023598  call    __security_check_cookie
0x18002359d  add     rsp, 1148h
0x1800235a4  pop     r15
0x1800235a6  pop     r14
0x1800235a8  pop     r13
0x1800235aa  pop     r12
0x1800235ac  pop     rdi
0x1800235ad  pop     rsi
0x1800235ae  pop     rbx
0x1800235af  pop     rbp
0x1800235b0  retn
```
