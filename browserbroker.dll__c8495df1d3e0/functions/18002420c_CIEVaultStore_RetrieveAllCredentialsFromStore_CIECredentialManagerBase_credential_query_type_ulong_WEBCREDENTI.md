# CIEVaultStore::RetrieveAllCredentialsFromStore(CIECredentialManagerBase *,credential_query_type,ulong *,_WEBCREDENTIAL * *)

- ea: `0x18002420c`
- end: `0x1800245a8`
- name: `?RetrieveAllCredentialsFromStore@CIEVaultStore@@QEAAJPEAVCIECredentialManagerBase@@W4credential_query_type@@PEAKPEAPEAU_WEBCREDENTIAL@@@Z`
- size: `924`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800241e0`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x18000a4d0`
- `0x18000dc94`
- `0x180021d80`
- `0x180021ef0`
- `0x1800225cc`
- `0x1800228a8`
- `0x180022fc0`
- `0x180023bec`
- `0x180023d70`
- `0x180023df8`
- `0x18002420c`
- `0x18002b4e0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800243c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002440a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800244fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024509`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800243c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002440a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800244fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024509`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024490`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800244a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024490`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800244a0`

## string_xrefs

- `0x180024323`: `onecoreuap\inetcore\lib\common\credmgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CIEVaultStore::RetrieveAllCredentialsFromStore(
        __int64 a1,
        __int64 a2,
        int a3,
        _DWORD *a4,
        __int64 *a5)
{
  _DWORD *v5; // r13
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // ebx
  __int64 v10; // r12
  __int64 v11; // r15
  const char *v12; // r9
  __int64 v13; // rsi
  unsigned int v14; // r14d
  unsigned int v15; // r13d
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, struct ABI::Windows::Security::Credentials::IPasswordCredential **); // rbx
  struct ABI::Windows::Security::Credentials::IPasswordCredential *v18; // rdi
  __int64 (__fastcall *v19)(struct ABI::Windows::Security::Credentials::IPasswordCredential *, HSTRING *); // rbx
  struct ABI::Windows::Security::Credentials::IPasswordCredential *v20; // rdi
  __int64 (__fastcall *v21)(struct ABI::Windows::Security::Credentials::IPasswordCredential *, HSTRING *); // rbx
  bool v22; // al
  unsigned int v23; // edx
  unsigned int v24; // edi
  const unsigned __int16 *StringRawBuffer; // rbx
  const unsigned __int16 *v26; // rax
  int v28; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v29; // [rsp+34h] [rbp-CCh] BYREF
  struct ABI::Windows::Security::Credentials::IPasswordCredential *v30; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v33; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A0h]
  int v36; // [rsp+68h] [rbp-98h]
  _DWORD *v37; // [rsp+70h] [rbp-90h]
  __int64 *v38; // [rsp+78h] [rbp-88h]
  _OWORD v39[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-60h]
  char v41; // [rsp+A8h] [rbp-58h]
  char v42[4174]; // [rsp+AAh] [rbp-56h] BYREF
  __int64 v43; // [rsp+10F8h] [rbp+FF8h]
  int v44; // [rsp+1100h] [rbp+1000h]
  wil::details::in1diag3 *retaddr; // [rsp+1158h] [rbp+1058h]

  v5 = a4;
  v37 = a4;
  LODWORD(v30) = a3;
  v38 = a5;
  v34 = a2;
  v35 = 0;
  v36 = 1;
  v31 = 0;
  v7 = *(_QWORD *)(a1 + 520);
  v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 88LL);
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v31);
  v9 = v8(v7, &v31);
  v28 = v9;
  if ( v9 >= 0 )
  {
    v29 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v31 + 56LL))(v31, &v29);
    v28 = v9;
    if ( v9 >= 0 )
    {
      v10 = *(_QWORD *)(a2 + 16);
      v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 16LL))(v10, 40LL * v29);
      CAutoIECredential<CIECredentialManager>::Free(&v34);
      v35 = v11;
      v36 = 1;
      if ( !v11 )
        wil::details::in1diag3::_FailFast_NullAlloc(
          retaddr,
          (void *)0x1FF,
          (int)"onecoreuap\\inetcore\\lib\\common\\credmgr.cpp",
          v12);
      v36 = v29;
      v9 = 0;
      v28 = 0;
      v13 = 0;
      v14 = 0;
      if ( !v29 )
        goto LABEL_21;
      v15 = (unsigned int)v30;
      do
      {
        if ( v9 < 0 )
          break;
        v30 = 0;
        v16 = v31;
        v17 = *(__int64 (__fastcall **)(__int64, _QWORD, struct ABI::Windows::Security::Credentials::IPasswordCredential **))(*(_QWORD *)v31 + 48LL);
        Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v30);
        v9 = v17(v16, v14, &v30);
        v28 = v9;
        if ( v9 >= 0 && IsIECredential(v30) )
        {
          v33 = 0;
          v18 = v30;
          v19 = *(__int64 (__fastcall **)(struct ABI::Windows::Security::Credentials::IPasswordCredential *, HSTRING *))(*(_QWORD *)v30 + 48LL);
          WindowsDeleteString(0);
          v33 = 0;
          v9 = v19(v18, &v33);
          v28 = v9;
          if ( v9 >= 0 )
          {
            string = 0;
            v20 = v30;
            v21 = *(__int64 (__fastcall **)(struct ABI::Windows::Security::Credentials::IPasswordCredential *, HSTRING *))(*(_QWORD *)v30 + 64LL);
            WindowsDeleteString(0);
            string = 0;
            v9 = v21(v20, &string);
            v28 = v9;
            if ( v9 >= 0 )
            {
              v22 = IsHiddenCredential(v30);
              if ( (unsigned __int8)DoesCredentialMatchHiddenType(v15, v22) )
              {
                v24 = v23;
                v41 = 0;
                v43 = 0;
                v44 = 0;
                memset(v39, 0, sizeof(v39));
                v40 = 0;
                memset_0(v42, 0, 0x1048u);
                StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                v26 = WindowsGetStringRawBuffer(v33, 0);
                v9 = CIESecureCredential::InitializeFromStrings(
                       (CIESecureCredential *)v39,
                       v26,
                       StringRawBuffer,
                       0,
                       v24,
                       0);
                v28 = v9;
                if ( v9 >= 0 )
                {
                  v9 = CopyIECredential(v10, v39, v11 + 40 * v13);
                  v28 = v9;
                  if ( v9 >= 0 )
                    v13 = (unsigned int)(v13 + 1);
                }
                CIESecureCredential::~CIESecureCredential((CIESecureCredential *)v39);
              }
            }
            WindowsDeleteString(string);
          }
          WindowsDeleteString(v33);
        }
        Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v30);
        ++v14;
      }
      while ( v14 < v29 );
      v5 = v37;
      if ( !(_DWORD)v13 )
      {
LABEL_21:
        v9 = -2147023728;
        v28 = -2147023728;
      }
      if ( v9 >= 0 )
      {
        v35 = 0;
        v36 = 0;
        *v38 = v11;
        *v5 = v13;
      }
    }
  }
  BrowserTelemetry::CredentialsRetrieveAllFromStoreCompleted<long &>((__int64)&v28);
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v31);
  CAutoIECredential<CIECredentialManager>::Free(&v34);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002420c  mov     [rsp-8+arg_10], rbx
0x180024211  push    rbp
0x180024212  push    rsi
0x180024213  push    rdi
0x180024214  push    r12
0x180024216  push    r13
0x180024218  push    r14
0x18002421a  push    r15
0x18002421c  lea     rbp, [rsp-1020h]
0x180024224  mov     eax, 1120h
0x180024229  call    _alloca_probe
0x18002422e  sub     rsp, rax
0x180024231  mov     rax, cs:__security_cookie
0x180024238  xor     rax, rsp
0x18002423b  mov     [rbp+1050h+var_40], rax
0x180024242  mov     r13, r9
0x180024245  mov     [rsp+1150h+var_10E0], r9
0x18002424a  mov     dword ptr [rsp+1150h+var_1118], r8d
0x18002424f  mov     r12, rdx
0x180024252  mov     rax, [rbp+1050h+arg_20]
0x180024259  mov     [rsp+1150h+var_10D8], rax
0x18002425e  mov     [rsp+1150h+var_10F8], rdx
0x180024263  mov     [rsp+1150h+var_10F0], 0
0x18002426c  mov     esi, 1
0x180024271  mov     [rsp+1150h+var_10E8], esi
0x180024275  mov     [rsp+1150h+var_1110], 0
0x18002427e  mov     rdi, [rcx+208h]
0x180024285  mov     rax, [rdi]
0x180024288  mov     rbx, [rax+58h]
0x18002428c  lea     rcx, [rsp+1150h+var_1110]
0x180024291  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180024296  lea     rdx, [rsp+1150h+var_1110]
0x18002429b  mov     rcx, rdi
0x18002429e  mov     rax, rbx
0x1800242a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242a6  mov     ebx, eax
0x1800242a8  mov     [rsp+1150h+var_1120], eax
0x1800242ac  test    eax, eax
0x1800242ae  js      loc_18002455B
0x1800242b4  mov     [rsp+1150h+var_111C], 0
0x1800242bc  mov     rcx, [rsp+1150h+var_1110]
0x1800242c1  mov     rax, [rcx]
0x1800242c4  lea     rdx, [rsp+1150h+var_111C]
0x1800242c9  mov     rax, [rax+38h]
0x1800242cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242d2  mov     ebx, eax
0x1800242d4  mov     [rsp+1150h+var_1120], eax
0x1800242d8  test    eax, eax
0x1800242da  js      loc_18002455B
0x1800242e0  mov     r12, [r12+10h]
0x1800242e5  mov     rcx, [r12]
0x1800242e9  mov     eax, [rsp+1150h+var_111C]
0x1800242ed  lea     rdx, [rax+rax*4]
0x1800242f1  shl     rdx, 3
0x1800242f5  mov     rax, [rcx+10h]
0x1800242f9  mov     rcx, r12
0x1800242fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024301  mov     r15, rax
0x180024304  lea     rcx, [rsp+1150h+var_10F8]
0x180024309  call    ?Free@?$CAutoIECredential@VCIECredentialManager@@@@AEAAXXZ; CAutoIECredential<CIECredentialManager>::Free(void)
0x18002430e  mov     [rsp+1150h+var_10F0], r15
0x180024313  mov     [rsp+1150h+var_10E8], esi
0x180024317  mov     rcx, [rbp+1058h]; this
0x18002431e  test    r15, r15
0x180024321  jnz     short loc_180024335
0x180024323  lea     r8, aOnecoreuapInet_4; "onecoreuap\\inetcore\\lib\\common\\cred"...
0x18002432a  mov     edx, 1FFh; void *
0x18002432f  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x180024335  mov     eax, [rsp+1150h+var_111C]
0x180024339  mov     [rsp+1150h+var_10E8], eax
0x18002433d  xor     ebx, ebx
0x18002433f  mov     [rsp+1150h+var_1120], ebx
0x180024343  xor     esi, esi
0x180024345  xor     r14d, r14d
0x180024348  test    eax, eax
0x18002434a  jz      loc_180024531
0x180024350  mov     r13d, dword ptr [rsp+1150h+var_1118]
0x180024355  test    ebx, ebx
0x180024357  js      loc_180024528
0x18002435d  mov     [rsp+1150h+var_1118], 0
0x180024366  mov     rdi, [rsp+1150h+var_1110]
0x18002436b  mov     rax, [rdi]
0x18002436e  mov     rbx, [rax+30h]
0x180024372  lea     rcx, [rsp+1150h+var_1118]
0x180024377  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18002437c  lea     r8, [rsp+1150h+var_1118]
0x180024381  mov     edx, r14d
0x180024384  mov     rcx, rdi
0x180024387  mov     rax, rbx
0x18002438a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002438f  mov     ebx, eax
0x180024391  mov     [rsp+1150h+var_1120], eax
0x180024395  test    eax, eax
0x180024397  js      loc_180024510
0x18002439d  mov     rcx, [rsp+1150h+var_1118]; struct ABI::Windows::Security::Credentials::IPasswordCredential *
0x1800243a2  call    ?IsIECredential@@YA_NPEAUIPasswordCredential@Credentials@Security@Windows@ABI@@@Z; IsIECredential(ABI::Windows::Security::Credentials::IPasswordCredential *)
0x1800243a7  test    al, al
0x1800243a9  jz      loc_180024510
0x1800243af  mov     [rsp+1150h+var_1100], 0
0x1800243b8  mov     rdi, [rsp+1150h+var_1118]
0x1800243bd  mov     rax, [rdi]
0x1800243c0  mov     rbx, [rax+30h]
0x1800243c4  xor     ecx, ecx; string
0x1800243c6  call    cs:__imp_WindowsDeleteString
0x1800243cc  mov     [rsp+1150h+var_1100], 0
0x1800243d5  lea     rdx, [rsp+1150h+var_1100]
0x1800243da  mov     rcx, rdi
0x1800243dd  mov     rax, rbx
0x1800243e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243e5  mov     ebx, eax
0x1800243e7  mov     [rsp+1150h+var_1120], eax
0x1800243eb  test    eax, eax
0x1800243ed  js      loc_180024504
0x1800243f3  mov     [rsp+1150h+string], 0
0x1800243fc  mov     rdi, [rsp+1150h+var_1118]
0x180024401  mov     rax, [rdi]
0x180024404  mov     rbx, [rax+40h]
0x180024408  xor     ecx, ecx; string
0x18002440a  call    cs:__imp_WindowsDeleteString
0x180024410  mov     [rsp+1150h+string], 0
0x180024419  lea     rdx, [rsp+1150h+string]
0x18002441e  mov     rcx, rdi
0x180024421  mov     rax, rbx
0x180024424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024429  mov     ebx, eax
0x18002442b  mov     [rsp+1150h+var_1120], eax
0x18002442f  test    eax, eax
0x180024431  js      loc_1800244F8
0x180024437  mov     rcx, [rsp+1150h+var_1118]; struct ABI::Windows::Security::Credentials::IPasswordCredential *
0x18002443c  call    ?IsHiddenCredential@@YA_NPEAUIPasswordCredential@Credentials@Security@Windows@ABI@@@Z; IsHiddenCredential(ABI::Windows::Security::Credentials::IPasswordCredential *)
0x180024441  movzx   edx, al
0x180024444  mov     ecx, r13d
0x180024447  call    ?DoesCredentialMatchHiddenType@@YA_NW4credential_query_type@@_N@Z; DoesCredentialMatchHiddenType(credential_query_type,bool)
0x18002444c  test    al, al
0x18002444e  jz      loc_1800244F8
0x180024454  mov     edi, edx
0x180024456  xor     eax, eax
0x180024458  mov     [rbp+1050h+var_10A8], al
0x18002445b  mov     [rbp+1050h+var_58], rax
0x180024462  mov     [rbp+1050h+var_50], eax
0x180024468  xorps   xmm0, xmm0
0x18002446b  movups  [rbp+1050h+var_10D0], xmm0
0x18002446f  movups  [rbp+1050h+var_10C0], xmm0
0x180024473  mov     [rbp+1050h+var_10B0], rax
0x180024477  xor     edx, edx; Val
0x180024479  mov     r8d, 1048h; Size
0x18002447f  lea     rcx, [rbp+1050h+var_10A6]; void *
0x180024483  call    memset_0
0x180024488  nop
0x180024489  xor     edx, edx; length
0x18002448b  mov     rcx, [rsp+1150h+string]; string
0x180024490  call    cs:__imp_WindowsGetStringRawBuffer
0x180024496  mov     rbx, rax
0x180024499  xor     edx, edx; length
0x18002449b  mov     rcx, [rsp+1150h+var_1100]; string
0x1800244a0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800244a6  mov     [rsp+1150h+var_1128], 0; int
0x1800244ae  mov     [rsp+1150h+var_1130], edi; unsigned int
0x1800244b2  xor     r9d, r9d; unsigned __int16 *
0x1800244b5  mov     r8, rbx; unsigned __int16 *
0x1800244b8  mov     rdx, rax; unsigned __int16 *
0x1800244bb  lea     rcx, [rbp+1050h+var_10D0]; this
0x1800244bf  call    ?InitializeFromStrings@CIESecureCredential@@QEAAJPEBG00KH@Z; CIESecureCredential::InitializeFromStrings(ushort const *,ushort const *,ushort const *,ulong,int)
0x1800244c4  mov     ebx, eax
0x1800244c6  mov     [rsp+1150h+var_1120], eax
0x1800244ca  test    eax, eax
0x1800244cc  js      short loc_1800244EE
0x1800244ce  lea     rcx, [rsi+rsi*4]
0x1800244d2  lea     r8, [r15+rcx*8]
0x1800244d6  lea     rdx, [rbp+1050h+var_10D0]
0x1800244da  mov     rcx, r12
0x1800244dd  call    CopyIECredential
0x1800244e2  mov     ebx, eax
0x1800244e4  mov     [rsp+1150h+var_1120], eax
0x1800244e8  test    eax, eax
0x1800244ea  js      short loc_1800244EE
0x1800244ec  inc     esi
0x1800244ee  lea     rcx, [rbp+1050h+var_10D0]; this
0x1800244f2  call    ??1CIESecureCredential@@QEAA@XZ; CIESecureCredential::~CIESecureCredential(void)
0x1800244f7  nop
0x1800244f8  mov     rcx, [rsp+1150h+string]; string
0x1800244fd  call    cs:__imp_WindowsDeleteString
0x180024503  nop
0x180024504  mov     rcx, [rsp+1150h+var_1100]; string
0x180024509  call    cs:__imp_WindowsDeleteString
0x18002450f  nop
0x180024510  lea     rcx, [rsp+1150h+var_1118]
0x180024515  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18002451a  inc     r14d
0x18002451d  cmp     r14d, [rsp+1150h+var_111C]
0x180024522  jb      loc_180024355
0x180024528  test    esi, esi
0x18002452a  mov     r13, [rsp+1150h+var_10E0]
0x18002452f  jnz     short loc_18002453A
0x180024531  mov     ebx, 80070490h
0x180024536  mov     [rsp+1150h+var_1120], ebx
0x18002453a  test    ebx, ebx
0x18002453c  js      short loc_18002455B
0x18002453e  mov     [rsp+1150h+var_10F0], 0
0x180024547  mov     [rsp+1150h+var_10E8], 0
0x18002454f  mov     rax, [rsp+1150h+var_10D8]
0x180024554  mov     [rax], r15
0x180024557  mov     [r13+0], esi
0x18002455b  lea     rcx, [rsp+1150h+var_1120]
0x180024560  call    ??$CredentialsRetrieveAllFromStoreCompleted@AEAJ@BrowserTelemetry@@SAXAEAJ@Z; BrowserTelemetry::CredentialsRetrieveAllFromStoreCompleted<long &>(long &)
0x180024565  nop
0x180024566  lea     rcx, [rsp+1150h+var_1110]
0x18002456b  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180024570  nop
0x180024571  lea     rcx, [rsp+1150h+var_10F8]
0x180024576  call    ?Free@?$CAutoIECredential@VCIECredentialManager@@@@AEAAXXZ; CAutoIECredential<CIECredentialManager>::Free(void)
0x18002457b  nop
0x18002457c  mov     eax, ebx
0x18002457e  mov     rcx, [rbp+1050h+var_40]
0x180024585  xor     rcx, rsp; StackCookie
0x180024588  call    __security_check_cookie
0x18002458d  mov     rbx, [rsp+1150h+arg_10]
0x180024595  add     rsp, 1120h
0x18002459c  pop     r15
0x18002459e  pop     r14
0x1800245a0  pop     r13
0x1800245a2  pop     r12
0x1800245a4  pop     rdi
0x1800245a5  pop     rsi
0x1800245a6  pop     rbp
0x1800245a7  retn
```
