# CIEVaultStore::FindCredentialsFromStore(CIECredentialManagerBase *,ushort const *,credential_query_type,ulong *,_WEBCREDENTIAL * *)

- ea: `0x180022bdc`
- end: `0x180022fba`
- name: `?FindCredentialsFromStore@CIEVaultStore@@QEAAJPEAVCIECredentialManagerBase@@PEBGW4credential_query_type@@PEAKPEAPEAU_WEBCREDENTIAL@@@Z`
- size: `990`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180022a70`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x18000a4d0`
- `0x18001bf70`
- `0x180021c68`
- `0x180021ef0`
- `0x1800222b4`
- `0x1800225cc`
- `0x1800228a8`
- `0x180022bdc`
- `0x180022fc0`
- `0x180023bec`
- `0x180023d70`
- `0x180023df8`
- `0x18002b4e0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022dc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022e09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022f05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022f11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022dc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022e09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022f05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022f11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022e98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022ea8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022e98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022ea8`
- `OLEAUT32!__imp_SysFreeString` at `0x180022f7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180022f7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CIEVaultStore::FindCredentialsFromStore(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        int a4,
        _DWORD *a5,
        __int64 *a6)
{
  _DWORD *v8; // r13
  int v9; // ebx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v12; // rax
  __int64 v13; // r12
  __int64 v14; // r15
  __int64 v15; // rsi
  unsigned int v16; // r14d
  unsigned int v17; // r13d
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD, struct ABI::Windows::Security::Credentials::IPasswordCredential **); // rbx
  struct ABI::Windows::Security::Credentials::IPasswordCredential *v20; // rdi
  __int64 (__fastcall *v21)(struct ABI::Windows::Security::Credentials::IPasswordCredential *, HSTRING *); // rbx
  struct ABI::Windows::Security::Credentials::IPasswordCredential *v22; // rdi
  __int64 (__fastcall *v23)(struct ABI::Windows::Security::Credentials::IPasswordCredential *, HSTRING *); // rbx
  bool v24; // al
  unsigned int v25; // edx
  unsigned int v26; // edi
  const unsigned __int16 *StringRawBuffer; // rbx
  const unsigned __int16 *v28; // rax
  int v30; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v31; // [rsp+34h] [rbp-CCh] BYREF
  struct ABI::Windows::Security::Credentials::IPasswordCredential *v32; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v33; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v34; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+68h] [rbp-98h]
  int v39; // [rsp+70h] [rbp-90h]
  _DWORD *v40; // [rsp+78h] [rbp-88h]
  __int64 *v41; // [rsp+80h] [rbp-80h]
  HSTRING_HEADER v42; // [rsp+88h] [rbp-78h] BYREF
  _OWORD v43[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v44; // [rsp+D0h] [rbp-30h]
  char v45; // [rsp+D8h] [rbp-28h]
  char v46[4174]; // [rsp+DAh] [rbp-26h] BYREF
  __int64 v47; // [rsp+1128h] [rbp+1028h]
  int v48; // [rsp+1130h] [rbp+1030h]

  LODWORD(v32) = a4;
  v8 = a5;
  v40 = a5;
  v41 = a6;
  v37 = a2;
  v38 = 0;
  v39 = 1;
  bstrString = 0;
  v9 = CleanUri(a3, &bstrString);
  v30 = v9;
  if ( v9 >= 0 )
  {
    v34 = 0;
    v10 = *(_QWORD *)(a1 + 520);
    v11 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v10 + 72LL);
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v34);
    v33 = (HSTRING)bstrString;
    v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v42, (const WCHAR **)&v33);
    v9 = v11(v10, v12[1].Reserved.Reserved1, &v34);
    v30 = v9;
    if ( v9 >= 0 )
    {
      v31 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v34 + 56LL))(v34, &v31);
      v30 = v9;
      if ( v9 >= 0 )
      {
        v13 = *(_QWORD *)(a2 + 16);
        v14 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 16LL))(v13, 40LL * v31);
        CAutoIECredential<CIECredentialManager>::Free(&v37);
        v38 = v14;
        v39 = 1;
        if ( v14 )
        {
          v39 = v31;
          v9 = 0;
          v30 = 0;
          v15 = 0;
          v16 = 0;
          if ( !v31 )
            goto LABEL_22;
          v17 = (unsigned int)v32;
          do
          {
            if ( v9 < 0 )
              break;
            v32 = 0;
            v18 = v34;
            v19 = *(__int64 (__fastcall **)(__int64, _QWORD, struct ABI::Windows::Security::Credentials::IPasswordCredential **))(*(_QWORD *)v34 + 48LL);
            Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v32);
            v9 = v19(v18, v16, &v32);
            v30 = v9;
            if ( v9 >= 0 && IsIECredential(v32) )
            {
              v33 = 0;
              v20 = v32;
              v21 = *(__int64 (__fastcall **)(struct ABI::Windows::Security::Credentials::IPasswordCredential *, HSTRING *))(*(_QWORD *)v32 + 48LL);
              WindowsDeleteString(0);
              v33 = 0;
              v9 = v21(v20, &v33);
              v30 = v9;
              if ( v9 >= 0 )
              {
                string = 0;
                v22 = v32;
                v23 = *(__int64 (__fastcall **)(struct ABI::Windows::Security::Credentials::IPasswordCredential *, HSTRING *))(*(_QWORD *)v32 + 64LL);
                WindowsDeleteString(0);
                string = 0;
                v9 = v23(v22, &string);
                v30 = v9;
                if ( v9 >= 0 )
                {
                  v24 = IsHiddenCredential(v32);
                  if ( (unsigned __int8)DoesCredentialMatchHiddenType(v17, v24) )
                  {
                    v26 = v25;
                    v45 = 0;
                    v47 = 0;
                    v48 = 0;
                    memset(v43, 0, sizeof(v43));
                    v44 = 0;
                    memset_0(v46, 0, 0x1048u);
                    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                    v28 = WindowsGetStringRawBuffer(v33, 0);
                    v9 = CIESecureCredential::InitializeFromStrings(
                           (CIESecureCredential *)v43,
                           v28,
                           StringRawBuffer,
                           0,
                           v26,
                           1);
                    v30 = v9;
                    if ( v9 >= 0 )
                    {
                      v9 = CopyIECredential(v13, v43, v14 + 40 * v15);
                      v30 = v9;
                      if ( v9 >= 0 )
                        v15 = (unsigned int)(v15 + 1);
                    }
                    CIESecureCredential::~CIESecureCredential((CIESecureCredential *)v43);
                  }
                }
                WindowsDeleteString(string);
              }
              WindowsDeleteString(v33);
            }
            Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v32);
            ++v16;
          }
          while ( v16 < v31 );
          v8 = v40;
          if ( !(_DWORD)v15 )
          {
LABEL_22:
            v9 = -2147023728;
            v30 = -2147023728;
          }
          if ( v9 >= 0 )
          {
            v38 = 0;
            v39 = 0;
            *v41 = v14;
            *v8 = v15;
          }
        }
        else
        {
          v9 = -2147024882;
          v30 = -2147024882;
        }
      }
    }
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v34);
  }
  BrowserTelemetry::CredentialsFindFromStoreCompleted<long &>((__int64)&v30);
  SysFreeString(bstrString);
  CAutoIECredential<CIECredentialManager>::Free(&v37);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180022bdc  mov     [rsp-8+arg_18], rbx
0x180022be1  push    rbp
0x180022be2  push    rsi
0x180022be3  push    rdi
0x180022be4  push    r12
0x180022be6  push    r13
0x180022be8  push    r14
0x180022bea  push    r15
0x180022bec  lea     rbp, [rsp-1050h]
0x180022bf4  mov     eax, 1150h
0x180022bf9  call    _alloca_probe
0x180022bfe  sub     rsp, rax
0x180022c01  mov     rax, cs:__security_cookie
0x180022c08  xor     rax, rsp
0x180022c0b  mov     [rbp+1080h+var_40], rax
0x180022c12  mov     dword ptr [rsp+1180h+var_1148], r9d
0x180022c17  mov     r12, rdx
0x180022c1a  mov     rdi, rcx
0x180022c1d  mov     r13, [rbp+1080h+arg_20]
0x180022c24  mov     [rsp+1180h+var_1108], r13
0x180022c29  mov     rax, [rbp+1080h+arg_28]
0x180022c30  mov     [rbp+1080h+var_1100], rax
0x180022c34  mov     [rsp+1180h+var_1120], rdx
0x180022c39  xor     esi, esi
0x180022c3b  mov     [rsp+1180h+var_1118], rsi
0x180022c40  lea     r14d, [rsi+1]
0x180022c44  mov     [rsp+1180h+var_1110], r14d
0x180022c49  mov     [rsp+1180h+bstrString], rsi
0x180022c4e  lea     rdx, [rsp+1180h+bstrString]; unsigned __int16 **
0x180022c53  mov     rcx, r8; unsigned __int16 *
0x180022c56  call    ?CleanUri@@YAJPEBGPEAPEAG@Z; CleanUri(ushort const *,ushort * *)
0x180022c5b  mov     ebx, eax
0x180022c5d  mov     [rsp+1180h+var_1150], eax
0x180022c61  test    eax, eax
0x180022c63  js      loc_180022F6C
0x180022c69  mov     [rsp+1180h+var_1138], rsi
0x180022c6e  mov     rdi, [rdi+208h]
0x180022c75  mov     rax, [rdi]
0x180022c78  mov     rbx, [rax+48h]
0x180022c7c  lea     rcx, [rsp+1180h+var_1138]
0x180022c81  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180022c86  mov     rax, [rsp+1180h+bstrString]
0x180022c8b  mov     [rsp+1180h+var_1140], rax
0x180022c90  lea     rdx, [rsp+1180h+var_1140]
0x180022c95  lea     rcx, [rbp+1080h+var_10F8]
0x180022c99  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180022c9e  nop
0x180022c9f  lea     r8, [rsp+1180h+var_1138]
0x180022ca4  mov     rdx, [rax+18h]
0x180022ca8  mov     rcx, rdi
0x180022cab  mov     rax, rbx
0x180022cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cb3  mov     ebx, eax
0x180022cb5  mov     [rsp+1180h+var_1150], eax
0x180022cb9  test    eax, eax
0x180022cbb  js      loc_180022F62
0x180022cc1  mov     [rsp+1180h+var_114C], esi
0x180022cc5  mov     rcx, [rsp+1180h+var_1138]
0x180022cca  mov     rax, [rcx]
0x180022ccd  lea     rdx, [rsp+1180h+var_114C]
0x180022cd2  mov     rax, [rax+38h]
0x180022cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cdb  mov     ebx, eax
0x180022cdd  mov     [rsp+1180h+var_1150], eax
0x180022ce1  test    eax, eax
0x180022ce3  js      loc_180022F62
0x180022ce9  mov     r12, [r12+10h]
0x180022cee  mov     rcx, [r12]
0x180022cf2  mov     eax, [rsp+1180h+var_114C]
0x180022cf6  lea     rdx, [rax+rax*4]
0x180022cfa  shl     rdx, 3
0x180022cfe  mov     rax, [rcx+10h]
0x180022d02  mov     rcx, r12
0x180022d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d0a  mov     r15, rax
0x180022d0d  lea     rcx, [rsp+1180h+var_1120]
0x180022d12  call    ?Free@?$CAutoIECredential@VCIECredentialManager@@@@AEAAXXZ; CAutoIECredential<CIECredentialManager>::Free(void)
0x180022d17  mov     [rsp+1180h+var_1118], r15
0x180022d1c  mov     [rsp+1180h+var_1110], r14d
0x180022d21  test    r15, r15
0x180022d24  jnz     short loc_180022D34
0x180022d26  mov     ebx, 8007000Eh
0x180022d2b  mov     [rsp+1180h+var_1150], ebx
0x180022d2f  jmp     loc_180022F62
0x180022d34  mov     eax, [rsp+1180h+var_114C]
0x180022d38  mov     [rsp+1180h+var_1110], eax
0x180022d3c  xor     ebx, ebx
0x180022d3e  mov     [rsp+1180h+var_1150], ebx
0x180022d42  xor     esi, esi
0x180022d44  xor     r14d, r14d
0x180022d47  test    eax, eax
0x180022d49  jz      loc_180022F39
0x180022d4f  mov     r13d, dword ptr [rsp+1180h+var_1148]
0x180022d54  test    ebx, ebx
0x180022d56  js      loc_180022F30
0x180022d5c  mov     [rsp+1180h+var_1148], 0
0x180022d65  mov     rdi, [rsp+1180h+var_1138]
0x180022d6a  mov     rax, [rdi]
0x180022d6d  mov     rbx, [rax+30h]
0x180022d71  lea     rcx, [rsp+1180h+var_1148]
0x180022d76  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180022d7b  lea     r8, [rsp+1180h+var_1148]
0x180022d80  mov     edx, r14d
0x180022d83  mov     rcx, rdi
0x180022d86  mov     rax, rbx
0x180022d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d8e  mov     ebx, eax
0x180022d90  mov     [rsp+1180h+var_1150], eax
0x180022d94  test    eax, eax
0x180022d96  js      loc_180022F18
0x180022d9c  mov     rcx, [rsp+1180h+var_1148]; struct ABI::Windows::Security::Credentials::IPasswordCredential *
0x180022da1  call    ?IsIECredential@@YA_NPEAUIPasswordCredential@Credentials@Security@Windows@ABI@@@Z; IsIECredential(ABI::Windows::Security::Credentials::IPasswordCredential *)
0x180022da6  test    al, al
0x180022da8  jz      loc_180022F18
0x180022dae  mov     [rsp+1180h+var_1140], 0
0x180022db7  mov     rdi, [rsp+1180h+var_1148]
0x180022dbc  mov     rax, [rdi]
0x180022dbf  mov     rbx, [rax+30h]
0x180022dc3  xor     ecx, ecx; string
0x180022dc5  call    cs:__imp_WindowsDeleteString
0x180022dcb  mov     [rsp+1180h+var_1140], 0
0x180022dd4  lea     rdx, [rsp+1180h+var_1140]
0x180022dd9  mov     rcx, rdi
0x180022ddc  mov     rax, rbx
0x180022ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022de4  mov     ebx, eax
0x180022de6  mov     [rsp+1180h+var_1150], eax
0x180022dea  test    eax, eax
0x180022dec  js      loc_180022F0C
0x180022df2  mov     [rsp+1180h+string], 0
0x180022dfb  mov     rdi, [rsp+1180h+var_1148]
0x180022e00  mov     rax, [rdi]
0x180022e03  mov     rbx, [rax+40h]
0x180022e07  xor     ecx, ecx; string
0x180022e09  call    cs:__imp_WindowsDeleteString
0x180022e0f  mov     [rsp+1180h+string], 0
0x180022e18  lea     rdx, [rsp+1180h+string]
0x180022e1d  mov     rcx, rdi
0x180022e20  mov     rax, rbx
0x180022e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e28  mov     ebx, eax
0x180022e2a  mov     [rsp+1180h+var_1150], eax
0x180022e2e  test    eax, eax
0x180022e30  js      loc_180022F00
0x180022e36  mov     rcx, [rsp+1180h+var_1148]; struct ABI::Windows::Security::Credentials::IPasswordCredential *
0x180022e3b  call    ?IsHiddenCredential@@YA_NPEAUIPasswordCredential@Credentials@Security@Windows@ABI@@@Z; IsHiddenCredential(ABI::Windows::Security::Credentials::IPasswordCredential *)
0x180022e40  movzx   edx, al
0x180022e43  mov     ecx, r13d
0x180022e46  call    ?DoesCredentialMatchHiddenType@@YA_NW4credential_query_type@@_N@Z; DoesCredentialMatchHiddenType(credential_query_type,bool)
0x180022e4b  test    al, al
0x180022e4d  jz      loc_180022F00
0x180022e53  mov     edi, edx
0x180022e55  mov     [rbp+1080h+var_10A8], 0
0x180022e59  mov     [rbp+1080h+var_58], 0
0x180022e64  mov     [rbp+1080h+var_50], 0
0x180022e6e  xorps   xmm0, xmm0
0x180022e71  xor     eax, eax
0x180022e73  movups  [rbp+1080h+var_10D0], xmm0
0x180022e77  movups  [rbp+1080h+var_10C0], xmm0
0x180022e7b  mov     [rbp+1080h+var_10B0], rax
0x180022e7f  xor     edx, edx; Val
0x180022e81  mov     r8d, 1048h; Size
0x180022e87  lea     rcx, [rbp+1080h+var_10A6]; void *
0x180022e8b  call    memset_0
0x180022e90  nop
0x180022e91  xor     edx, edx; length
0x180022e93  mov     rcx, [rsp+1180h+string]; string
0x180022e98  call    cs:__imp_WindowsGetStringRawBuffer
0x180022e9e  mov     rbx, rax
0x180022ea1  xor     edx, edx; length
0x180022ea3  mov     rcx, [rsp+1180h+var_1140]; string
0x180022ea8  call    cs:__imp_WindowsGetStringRawBuffer
0x180022eae  mov     [rsp+1180h+var_1158], 1; int
0x180022eb6  mov     [rsp+1180h+var_1160], edi; unsigned int
0x180022eba  xor     r9d, r9d; unsigned __int16 *
0x180022ebd  mov     r8, rbx; unsigned __int16 *
0x180022ec0  mov     rdx, rax; unsigned __int16 *
0x180022ec3  lea     rcx, [rbp+1080h+var_10D0]; this
0x180022ec7  call    ?InitializeFromStrings@CIESecureCredential@@QEAAJPEBG00KH@Z; CIESecureCredential::InitializeFromStrings(ushort const *,ushort const *,ushort const *,ulong,int)
0x180022ecc  mov     ebx, eax
0x180022ece  mov     [rsp+1180h+var_1150], eax
0x180022ed2  test    eax, eax
0x180022ed4  js      short loc_180022EF6
0x180022ed6  lea     rcx, [rsi+rsi*4]
0x180022eda  lea     r8, [r15+rcx*8]
0x180022ede  lea     rdx, [rbp+1080h+var_10D0]
0x180022ee2  mov     rcx, r12
0x180022ee5  call    CopyIECredential
0x180022eea  mov     ebx, eax
0x180022eec  mov     [rsp+1180h+var_1150], eax
0x180022ef0  test    eax, eax
0x180022ef2  js      short loc_180022EF6
0x180022ef4  inc     esi
0x180022ef6  lea     rcx, [rbp+1080h+var_10D0]; this
0x180022efa  call    ??1CIESecureCredential@@QEAA@XZ; CIESecureCredential::~CIESecureCredential(void)
0x180022eff  nop
0x180022f00  mov     rcx, [rsp+1180h+string]; string
0x180022f05  call    cs:__imp_WindowsDeleteString
0x180022f0b  nop
0x180022f0c  mov     rcx, [rsp+1180h+var_1140]; string
0x180022f11  call    cs:__imp_WindowsDeleteString
0x180022f17  nop
0x180022f18  lea     rcx, [rsp+1180h+var_1148]
0x180022f1d  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180022f22  inc     r14d
0x180022f25  cmp     r14d, [rsp+1180h+var_114C]
0x180022f2a  jb      loc_180022D54
0x180022f30  test    esi, esi
0x180022f32  mov     r13, [rsp+1180h+var_1108]
0x180022f37  jnz     short loc_180022F42
0x180022f39  mov     ebx, 80070490h
0x180022f3e  mov     [rsp+1180h+var_1150], ebx
0x180022f42  test    ebx, ebx
0x180022f44  js      short loc_180022F62
0x180022f46  mov     [rsp+1180h+var_1118], 0
0x180022f4f  mov     [rsp+1180h+var_1110], 0
0x180022f57  mov     rax, [rbp+1080h+var_1100]
0x180022f5b  mov     [rax], r15
0x180022f5e  mov     [r13+0], esi
0x180022f62  lea     rcx, [rsp+1180h+var_1138]
0x180022f67  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180022f6c  lea     rcx, [rsp+1180h+var_1150]
0x180022f71  call    ??$CredentialsFindFromStoreCompleted@AEAJ@BrowserTelemetry@@SAXAEAJ@Z; BrowserTelemetry::CredentialsFindFromStoreCompleted<long &>(long &)
0x180022f76  nop
0x180022f77  mov     rcx, [rsp+1180h+bstrString]; bstrString
0x180022f7c  call    cs:__imp_SysFreeString
0x180022f82  nop
0x180022f83  lea     rcx, [rsp+1180h+var_1120]
0x180022f88  call    ?Free@?$CAutoIECredential@VCIECredentialManager@@@@AEAAXXZ; CAutoIECredential<CIECredentialManager>::Free(void)
0x180022f8d  nop
0x180022f8e  mov     eax, ebx
0x180022f90  mov     rcx, [rbp+1080h+var_40]
0x180022f97  xor     rcx, rsp; StackCookie
0x180022f9a  call    __security_check_cookie
0x180022f9f  mov     rbx, [rsp+1180h+arg_18]
0x180022fa7  add     rsp, 1150h
0x180022fae  pop     r15
0x180022fb0  pop     r14
0x180022fb2  pop     r13
0x180022fb4  pop     r12
0x180022fb6  pop     rdi
0x180022fb7  pop     rsi
0x180022fb8  pop     rbp
0x180022fb9  retn
```
