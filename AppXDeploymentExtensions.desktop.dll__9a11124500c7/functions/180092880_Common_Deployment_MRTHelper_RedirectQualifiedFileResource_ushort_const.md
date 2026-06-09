# Common::Deployment::MRTHelper::RedirectQualifiedFileResource(ushort const *)

- ea: `0x180092880`
- end: `0x180092ff4`
- name: `?RedirectQualifiedFileResource@MRTHelper@Deployment@Common@@AEAAJPEBG@Z`
- size: `1908`
- prototype: `int(Common::Deployment::MRTHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180092498`

## callees

- `0x180006970`
- `0x180009dc0`
- `0x180012fc8`
- `0x180015590`
- `0x18001d920`
- `0x18003d814`
- `0x18003d8f4`
- `0x180056c2c`
- `0x180092880`
- `0x1800aed10`
- `0x1800af1bc`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092cd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092d5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092d93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092cd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092d5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092d93`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800929b7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800929b7`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180092c91`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180092f0c`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180092c91`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180092f0c`
- `KERNEL32!CopyFileW` at `0x180092ca9`
- `KERNEL32!CopyFileW` at `0x180092f26`
- `KERNEL32!CopyFileW` at `0x180092ca9`
- `KERNEL32!CopyFileW` at `0x180092f26`

## string_xrefs

- `0x180092945`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x180092cf2`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x180092d33`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x180092d81`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x180092e49`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x180092ed5`: `onecore\admin\appmodel\common\mrthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Common::Deployment::MRTHelper::RedirectQualifiedFileResource(
        Common::Deployment::MRTHelper *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // r14
  HRESULT v5; // ebx
  wil::details::in1diag3 *v6; // rcx
  __int64 v7; // rdx
  unsigned __int64 v8; // r9
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, GUID *, __int64 *); // rbx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, const wchar_t *, __int64 *); // rbx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, const unsigned __int16 *, GUID *, __int64 *); // rbx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  unsigned int v18; // esi
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64 *); // rbx
  wil::details::in1diag3 *v21; // rcx
  int v22; // eax
  int v23; // eax
  wil::details::in1diag3 *v24; // rcx
  const struct std::nothrow_t *v25; // rdx
  Common::Deployment *v26; // rdi
  const unsigned __int16 *v27; // rdx
  int Directory; // eax
  const struct std::nothrow_t *v29; // rdx
  const struct std::nothrow_t *v30; // rdx
  Common::Deployment *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rdx
  unsigned __int64 v34; // r9
  int v35; // eax
  int v36; // eax
  int v37; // eax
  wil::details::in1diag3 *v38; // rcx
  __int64 v39; // rdx
  const struct std::nothrow_t *v40; // rdx
  const struct std::nothrow_t *v41; // rdx
  Common::Deployment *v42; // rbx
  const unsigned __int16 *v43; // rdx
  int v44; // eax
  HRESULT v45; // edi
  const struct std::nothrow_t *v46; // rdx
  const struct std::nothrow_t *v47; // rdx
  int ppv; // [rsp+20h] [rbp-E0h]
  __int64 v49; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v50; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v51; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v52; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v55; // [rsp+60h] [rbp-A0h] BYREF
  Common::Deployment *v56[2]; // [rsp+68h] [rbp-98h] BYREF
  int v57; // [rsp+78h] [rbp-88h]
  unsigned int v58; // [rsp+80h] [rbp-80h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp-78h] BYREF
  void *v60; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v61[4]; // [rsp+98h] [rbp-68h] BYREF
  int v62; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v63[8]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v64; // [rsp+B8h] [rbp-48h]
  wchar_t v65; // [rsp+C8h] [rbp-38h]
  WCHAR FileName[264]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v67[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+4F0h] [rbp+3F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+748h] [rbp+648h]

  v50 = 0;
  v53 = 0;
  v52 = 0;
  v51 = 0;
  v49 = 0;
  *(_OWORD *)v63 = *(_OWORD *)L"%s\\resources.pri";
  v64 = *(_OWORD *)L"rces.pri";
  v65 = aSResourcesPri[16];
  *(_QWORD *)v61 = *(_QWORD *)L"%s\\%s";
  v62 = *(_DWORD *)L"s";
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(*((_QWORD *)this + 6) + 2 * v4) );
  v5 = StringCchPrintfW(v67, 0x104u, v63);
  v6 = retaddr;
  if ( v5 < 0 )
  {
    v7 = 623;
LABEL_5:
    v8 = (unsigned int)v5;
LABEL_6:
    wil::details::in1diag3::_Log_Hr(
      v6,
      (void *)v7,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
      (const char *)v8,
      ppv);
LABEL_7:
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v49);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v51);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v52);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v53);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v50);
    return (unsigned int)v5;
  }
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v50);
  v5 = CoCreateInstance(
         &GUID_dbce7e40_7345_439d_b12c_114a11819a09,
         0,
         1u,
         &GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c,
         &v50);
  v6 = retaddr;
  if ( v5 < 0 )
  {
    v7 = 625;
    goto LABEL_5;
  }
  v5 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)v50 + 48LL))(v50, v67);
  v6 = retaddr;
  if ( v5 < 0 )
  {
    v7 = 626;
    goto LABEL_5;
  }
  v10 = v50;
  v11 = *(__int64 (__fastcall **)(LPVOID, GUID *, __int64 *))(*(_QWORD *)v50 + 56LL);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v53);
  v5 = v11(v10, &GUID_6e21e72b_b9b0_42ae_a686_983cf784edcd, &v53);
  v6 = retaddr;
  if ( v5 < 0 )
  {
    v7 = 627;
    goto LABEL_5;
  }
  v12 = v53;
  v13 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v53 + 32LL);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v52);
  v5 = v13(v12, L"Files", &v52);
  v6 = retaddr;
  if ( v5 < 0 )
  {
    v7 = 628;
    goto LABEL_5;
  }
  v14 = v52;
  v15 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, GUID *, __int64 *))(*(_QWORD *)v52 + 88LL);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v51);
  v5 = v15(v14, a2, &GUID_c2ac6f97_54f2_445a_8f62_d87b9537f9b2, &v51);
  v6 = retaddr;
  if ( v5 < 0 )
  {
    v7 = 629;
    goto LABEL_5;
  }
  v16 = v51;
  v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 64LL);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v49);
  v5 = v17(v16, &v49);
  v6 = retaddr;
  if ( v5 < 0 )
  {
    v7 = 630;
    goto LABEL_5;
  }
  v58 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v49 + 24LL))(v49, &v58);
  v6 = retaddr;
  if ( v5 < 0 )
  {
    v7 = 633;
    goto LABEL_5;
  }
  v18 = 0;
  while ( 2 )
  {
    if ( v18 < v58 )
    {
      v55 = 0;
      lpExistingFileName = 0;
      v19 = v49;
      v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v49 + 32LL);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v55);
      v5 = v20(v19, v18, &v55);
      v21 = retaddr;
      if ( v5 < 0 )
      {
        v34 = (unsigned int)v5;
        v33 = 639;
      }
      else
      {
        v22 = (*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v55 + 32LL))(v55, &lpExistingFileName);
        v5 = v22;
        v21 = retaddr;
        if ( v22 < 0 )
        {
          v33 = 640;
        }
        else
        {
          if ( !lpExistingFileName )
          {
            CoTaskMemFree(0);
            v5 = -2147467261;
LABEL_53:
            Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v55);
            goto LABEL_7;
          }
          ppv = (_DWORD)lpExistingFileName + 2 + 2 * v4;
          v22 = StringCchPrintfW(FileName, 0x104u, v61, *((_QWORD *)this + 15));
          v5 = v22;
          v21 = retaddr;
          if ( v22 >= 0 )
          {
            *(_OWORD *)v56 = 0;
            v57 = 0;
            v23 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v56, FileName);
            v5 = v23;
            v24 = retaddr;
            if ( v23 < 0 )
            {
              v32 = 646;
LABEL_44:
              wil::details::in1diag3::_Log_Hr(
                v24,
                (void *)v32,
                (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
                (const char *)(unsigned int)v23,
                ppv);
              v31 = v56[1];
              if ( !v56[1] )
                goto LABEL_52;
            }
            else
            {
              LODWORD(v25) = v56[0];
              do
              {
                v25 = (const struct std::nothrow_t *)(unsigned int)((_DWORD)v25 - 1);
                if ( (int)v25 < 0 )
                {
                  if ( v56[1] )
                    operator delete(v56[1], v25);
                  v5 = -2147024809;
                  goto LABEL_52;
                }
              }
              while ( *((_WORD *)v56[1] + (int)v25) != 92 );
              v23 = Common::StringBuffer::SetLength((Common::StringBuffer *)v56, (unsigned int)v25);
              v5 = v23;
              v24 = retaddr;
              if ( v23 < 0 )
              {
                v32 = 648;
                goto LABEL_44;
              }
              TokenHandle = 0;
              Common::AutoNoImpersonateDuringScope::DropImpersonation(&TokenHandle);
              v26 = v56[1];
              Directory = Common::Deployment::RecursiveCreateDirectory(v56[1], v27);
              v5 = Directory;
              if ( Directory >= 0 )
              {
                SetFileAttributesW(FileName, 0x80u);
                CopyFileW(lpExistingFileName, FileName, 0);
                Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&TokenHandle);
                if ( v26 )
                  operator delete(v26, v29);
                CoTaskMemFree((LPVOID)lpExistingFileName);
                Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v55);
                ++v18;
                continue;
              }
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x28C,
                (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
                (const char *)(unsigned int)Directory,
                ppv);
              Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&TokenHandle);
              if ( !v26 )
                goto LABEL_52;
              v31 = v26;
            }
            operator delete(v31, v30);
LABEL_52:
            CoTaskMemFree((LPVOID)lpExistingFileName);
            goto LABEL_53;
          }
          v33 = 643;
        }
        v34 = (unsigned int)v22;
      }
      wil::details::in1diag3::_Log_Hr(
        v21,
        (void *)v33,
        (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
        (const char *)v34,
        ppv);
      goto LABEL_52;
    }
    break;
  }
  ppv = (int)a2;
  v35 = StringCchPrintfW(ExistingFileName, 0x104u, v61, *((_QWORD *)this + 6));
  v5 = v35;
  v6 = retaddr;
  if ( v35 < 0 )
  {
    v8 = (unsigned int)v35;
    v7 = 665;
    goto LABEL_6;
  }
  ppv = (int)a2;
  v36 = StringCchPrintfW(FileName, 0x104u, v61, *((_QWORD *)this + 15));
  v5 = v36;
  v6 = retaddr;
  if ( v36 < 0 )
  {
    v8 = (unsigned int)v36;
    v7 = 666;
    goto LABEL_6;
  }
  *(_OWORD *)v56 = 0;
  v57 = 0;
  v37 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v56, FileName);
  v5 = v37;
  v38 = retaddr;
  if ( v37 < 0 )
  {
    v39 = 669;
LABEL_60:
    wil::details::in1diag3::_Log_Hr(
      v38,
      (void *)v39,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
      (const char *)(unsigned int)v37,
      (int)a2);
    if ( v56[1] )
      operator delete(v56[1], v40);
    goto LABEL_7;
  }
  LODWORD(v41) = v56[0];
  do
  {
    v41 = (const struct std::nothrow_t *)(unsigned int)((_DWORD)v41 - 1);
    if ( (int)v41 < 0 )
    {
      if ( v56[1] )
        operator delete(v56[1], v41);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v49);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v51);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v52);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v53);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v50);
      return 2147942487LL;
    }
  }
  while ( *((_WORD *)v56[1] + (int)v41) != 92 );
  v37 = Common::StringBuffer::SetLength((Common::StringBuffer *)v56, (unsigned int)v41);
  v5 = v37;
  v38 = retaddr;
  if ( v37 < 0 )
  {
    v39 = 671;
    goto LABEL_60;
  }
  v60 = 0;
  Common::AutoNoImpersonateDuringScope::DropImpersonation(&v60);
  v42 = v56[1];
  v44 = Common::Deployment::RecursiveCreateDirectory(v56[1], v43);
  v45 = v44;
  if ( v44 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2A3,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
      (const char *)(unsigned int)v44,
      (int)a2);
    Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&v60);
    if ( v42 )
      operator delete(v42, v46);
    v5 = v45;
    goto LABEL_7;
  }
  SetFileAttributesW(FileName, 0x80u);
  CopyFileW(ExistingFileName, FileName, 0);
  Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&v60);
  if ( v42 )
    operator delete(v42, v47);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v49);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v51);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v53);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v50);
  return 0;
}

```

## disassembly

```asm
0x180092880  mov     [rsp-8+arg_10], rbx
0x180092885  push    rbp
0x180092886  push    rsi
0x180092887  push    rdi
0x180092888  push    r12
0x18009288a  push    r13
0x18009288c  push    r14
0x18009288e  push    r15
0x180092890  lea     rbp, [rsp-610h]
0x180092898  sub     rsp, 710h
0x18009289f  mov     rax, cs:__security_cookie
0x1800928a6  xor     rax, rsp
0x1800928a9  mov     [rbp+640h+var_40], rax
0x1800928b0  mov     r12, rdx
0x1800928b3  mov     r15, rcx
0x1800928b6  xor     r13d, r13d
0x1800928b9  mov     [rsp+740h+var_708], r13
0x1800928be  mov     [rsp+740h+var_6F0], r13
0x1800928c3  mov     [rsp+740h+var_6F8], r13
0x1800928c8  mov     [rsp+740h+var_700], r13
0x1800928cd  mov     [rsp+740h+var_710], r13
0x1800928d2  movups  xmm0, xmmword ptr cs:aSResourcesPri; "%s\\resources.pri"
0x1800928d9  movups  xmmword ptr [rbp+640h+var_698], xmm0
0x1800928dd  movups  xmm1, xmmword ptr cs:aSResourcesPri+10h; "rces.pri"
0x1800928e4  movups  [rbp+640h+var_688], xmm1
0x1800928e8  movzx   eax, word ptr cs:aSResourcesPri+20h; ""
0x1800928ef  mov     [rbp+640h+var_678], ax
0x1800928f3  movsd   xmm0, qword ptr cs:aSS; "%s\\%s"
0x1800928fb  movsd   qword ptr [rbp+640h+var_6A8], xmm0
0x180092900  mov     eax, dword ptr cs:aSS+8; "s"
0x180092906  mov     [rbp+640h+var_6A0], eax
0x180092909  mov     r9, [rcx+30h]
0x18009290d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180092911  inc     r14
0x180092914  cmp     [r9+r14*2], r13w
0x180092919  jnz     short loc_180092911
0x18009291b  lea     r8, [rbp+640h+var_698]; unsigned __int16 *
0x18009291f  mov     edx, 104h; unsigned __int64
0x180092924  lea     rcx, [rbp+640h+var_460]; unsigned __int16 *
0x18009292b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180092930  mov     ebx, eax
0x180092932  mov     rcx, [rbp+648h]; this
0x180092939  test    eax, eax
0x18009293b  jns     short loc_18009298F
0x18009293d  mov     edx, 26Fh; void *
0x180092942  mov     r9d, ebx; char *
0x180092945  lea     r8, aOnecoreAdminAp_133; "onecore\\admin\\appmodel\\common\\mrthe"...
0x18009294c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180092951  nop
0x180092952  lea     rcx, [rsp+740h+var_710]
0x180092957  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18009295c  nop
0x18009295d  lea     rcx, [rsp+740h+var_700]
0x180092962  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180092967  nop
0x180092968  lea     rcx, [rsp+740h+var_6F8]
0x18009296d  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180092972  nop
0x180092973  lea     rcx, [rsp+740h+var_6F0]
0x180092978  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18009297d  nop
0x18009297e  lea     rcx, [rsp+740h+var_708]
0x180092983  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180092988  mov     eax, ebx
0x18009298a  jmp     loc_180092FC9
0x18009298f  lea     rcx, [rsp+740h+var_708]
0x180092994  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180092999  lea     rax, [rsp+740h+var_708]
0x18009299e  mov     qword ptr [rsp+740h+ppv], rax; int
0x1800929a3  lea     r9, _GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c; riid
0x1800929aa  xor     edx, edx; pUnkOuter
0x1800929ac  lea     r8d, [rdx+1]; dwClsContext
0x1800929b0  lea     rcx, _GUID_dbce7e40_7345_439d_b12c_114a11819a09; rclsid
0x1800929b7  call    cs:__imp_CoCreateInstance
0x1800929be  nop     dword ptr [rax+rax+00h]
0x1800929c3  mov     ebx, eax
0x1800929c5  mov     rcx, [rbp+648h]
0x1800929cc  test    eax, eax
0x1800929ce  jns     short loc_1800929DA
0x1800929d0  mov     edx, 271h
0x1800929d5  jmp     loc_180092942
0x1800929da  mov     rcx, [rsp+740h+var_708]
0x1800929df  mov     rax, [rcx]
0x1800929e2  lea     rdx, [rbp+640h+var_460]
0x1800929e9  mov     rax, [rax+30h]
0x1800929ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800929f2  mov     ebx, eax
0x1800929f4  mov     rcx, [rbp+648h]
0x1800929fb  test    eax, eax
0x1800929fd  jns     short loc_180092A09
0x1800929ff  mov     edx, 272h
0x180092a04  jmp     loc_180092942
0x180092a09  mov     rdi, [rsp+740h+var_708]
0x180092a0e  mov     rax, [rdi]
0x180092a11  mov     rbx, [rax+38h]
0x180092a15  lea     rcx, [rsp+740h+var_6F0]
0x180092a1a  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180092a1f  lea     r8, [rsp+740h+var_6F0]
0x180092a24  lea     rdx, _GUID_6e21e72b_b9b0_42ae_a686_983cf784edcd
0x180092a2b  mov     rcx, rdi
0x180092a2e  mov     rax, rbx
0x180092a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092a36  mov     ebx, eax
0x180092a38  mov     rcx, [rbp+648h]
0x180092a3f  test    eax, eax
0x180092a41  jns     short loc_180092A4D
0x180092a43  mov     edx, 273h
0x180092a48  jmp     loc_180092942
0x180092a4d  mov     rdi, [rsp+740h+var_6F0]
0x180092a52  mov     rax, [rdi]
0x180092a55  mov     rbx, [rax+20h]
0x180092a59  lea     rcx, [rsp+740h+var_6F8]
0x180092a5e  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180092a63  lea     r8, [rsp+740h+var_6F8]
0x180092a68  lea     rdx, aFiles; "Files"
0x180092a6f  mov     rcx, rdi
0x180092a72  mov     rax, rbx
0x180092a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092a7a  mov     ebx, eax
0x180092a7c  mov     rcx, [rbp+648h]
0x180092a83  test    eax, eax
0x180092a85  jns     short loc_180092A91
0x180092a87  mov     edx, 274h
0x180092a8c  jmp     loc_180092942
0x180092a91  mov     rdi, [rsp+740h+var_6F8]
0x180092a96  mov     rax, [rdi]
0x180092a99  mov     rbx, [rax+58h]
0x180092a9d  lea     rcx, [rsp+740h+var_700]
0x180092aa2  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180092aa7  lea     r9, [rsp+740h+var_700]
0x180092aac  lea     r8, _GUID_c2ac6f97_54f2_445a_8f62_d87b9537f9b2
0x180092ab3  mov     rdx, r12
0x180092ab6  mov     rcx, rdi
0x180092ab9  mov     rax, rbx
0x180092abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092ac1  mov     ebx, eax
0x180092ac3  mov     rcx, [rbp+648h]
0x180092aca  test    eax, eax
0x180092acc  jns     short loc_180092AD8
0x180092ace  mov     edx, 275h
0x180092ad3  jmp     loc_180092942
0x180092ad8  mov     rdi, [rsp+740h+var_700]
0x180092add  mov     rax, [rdi]
0x180092ae0  mov     rbx, [rax+40h]
0x180092ae4  lea     rcx, [rsp+740h+var_710]
0x180092ae9  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180092aee  lea     rdx, [rsp+740h+var_710]
0x180092af3  mov     rcx, rdi
0x180092af6  mov     rax, rbx
0x180092af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092afe  mov     ebx, eax
0x180092b00  mov     rcx, [rbp+648h]
0x180092b07  test    eax, eax
0x180092b09  jns     short loc_180092B15
0x180092b0b  mov     edx, 276h
0x180092b10  jmp     loc_180092942
0x180092b15  mov     [rbp+640h+var_6C0], r13d
0x180092b19  mov     rcx, [rsp+740h+var_710]
0x180092b1e  mov     rax, [rcx]
0x180092b21  lea     rdx, [rbp+640h+var_6C0]
0x180092b25  mov     rax, [rax+18h]
0x180092b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092b2e  mov     ebx, eax
0x180092b30  mov     rcx, [rbp+648h]
0x180092b37  test    eax, eax
0x180092b39  jns     short loc_180092B45
0x180092b3b  mov     edx, 279h
0x180092b40  jmp     loc_180092942
0x180092b45  mov     esi, r13d
0x180092b48  cmp     esi, [rbp+640h+var_6C0]
0x180092b4b  jnb     loc_180092DAF
0x180092b51  mov     [rsp+740h+var_6E0], r13
0x180092b56  mov     [rsp+740h+lpExistingFileName], r13
0x180092b5b  mov     rdi, [rsp+740h+var_710]
0x180092b60  mov     rax, [rdi]
0x180092b63  mov     rbx, [rax+20h]
0x180092b67  lea     rcx, [rsp+740h+var_6E0]
0x180092b6c  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180092b71  lea     r8, [rsp+740h+var_6E0]
0x180092b76  mov     edx, esi
0x180092b78  mov     rcx, rdi
0x180092b7b  mov     rax, rbx
0x180092b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092b83  mov     ebx, eax
0x180092b85  mov     rcx, [rbp+648h]; this
0x180092b8c  test    eax, eax
0x180092b8e  js      loc_180092D79
0x180092b94  mov     rcx, [rsp+740h+var_6E0]
0x180092b99  mov     rax, [rcx]
0x180092b9c  lea     rdx, [rsp+740h+lpExistingFileName]
0x180092ba1  mov     rax, [rax+20h]
0x180092ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092baa  mov     ebx, eax
0x180092bac  mov     rcx, [rbp+648h]
0x180092bb3  test    eax, eax
0x180092bb5  js      loc_180092D6F
0x180092bbb  mov     rax, [rsp+740h+lpExistingFileName]
0x180092bc0  test    rax, rax
0x180092bc3  jz      loc_180092D5A
0x180092bc9  lea     rcx, [rax+2]
0x180092bcd  lea     rcx, [rcx+r14*2]
0x180092bd1  mov     qword ptr [rsp+740h+ppv], rcx; int
0x180092bd6  mov     r9, [r15+78h]
0x180092bda  lea     r8, [rbp+640h+var_6A8]; unsigned __int16 *
0x180092bde  mov     edx, 104h; unsigned __int64
0x180092be3  lea     rcx, [rbp+640h+FileName]; unsigned __int16 *
0x180092be7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180092bec  mov     ebx, eax
0x180092bee  mov     rcx, [rbp+648h]
0x180092bf5  test    eax, eax
0x180092bf7  js      loc_180092D53
0x180092bfd  xorps   xmm0, xmm0
0x180092c00  movups  xmmword ptr [rsp+740h+var_6D8], xmm0
0x180092c05  mov     [rsp+740h+var_6C8], r13d
0x180092c0a  lea     rdx, [rbp+640h+FileName]; unsigned __int16 *
0x180092c0e  lea     rcx, [rsp+740h+var_6D8]; this
0x180092c13  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180092c18  mov     ebx, eax
0x180092c1a  mov     rcx, [rbp+648h]; this
0x180092c21  test    eax, eax
0x180092c23  js      loc_180092D2E
0x180092c29  mov     edx, dword ptr [rsp+740h+var_6D8]
0x180092c2d  mov     rcx, [rsp+740h+var_6D8+8]; void *
0x180092c32  dec     edx; struct std::nothrow_t *
0x180092c34  test    edx, edx
0x180092c36  js      loc_180092D1D
0x180092c3c  movsxd  rax, edx
0x180092c3f  cmp     word ptr [rcx+rax*2], 5Ch ; '\'
0x180092c44  jnz     short loc_180092C32
0x180092c46  lea     rcx, [rsp+740h+var_6D8]; this
0x180092c4b  call    ?SetLength@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetLength(ulong)
0x180092c50  mov     ebx, eax
0x180092c52  mov     rcx, [rbp+648h]
0x180092c59  test    eax, eax
0x180092c5b  js      loc_180092D16
0x180092c61  mov     [rbp+640h+TokenHandle], r13
0x180092c65  lea     rcx, [rbp+640h+TokenHandle]; TokenHandle
0x180092c69  call    ?DropImpersonation@AutoNoImpersonateDuringScope@Common@@QEAAJXZ; Common::AutoNoImpersonateDuringScope::DropImpersonation(void)
0x180092c6e  mov     rdi, [rsp+740h+var_6D8+8]
0x180092c73  mov     rcx, rdi; this
0x180092c76  call    ?RecursiveCreateDirectory@Deployment@Common@@YAJPEBG@Z; Common::Deployment::RecursiveCreateDirectory(ushort const *)
0x180092c7b  mov     ebx, eax
0x180092c7d  mov     rcx, [rbp+648h]; this
0x180092c84  test    eax, eax
0x180092c86  js      short loc_180092CEF
0x180092c88  mov     edx, 80h; dwFileAttributes
0x180092c8d  lea     rcx, [rbp+640h+FileName]; lpFileName
0x180092c91  call    cs:__imp_SetFileAttributesW
0x180092c98  nop     dword ptr [rax+rax+00h]
0x180092c9d  xor     r8d, r8d; bFailIfExists
0x180092ca0  lea     rdx, [rbp+640h+FileName]; lpNewFileName
0x180092ca4  mov     rcx, [rsp+740h+lpExistingFileName]; lpExistingFileName
0x180092ca9  call    cs:__imp_CopyFileW
0x180092cb0  nop     dword ptr [rax+rax+00h]
0x180092cb5  lea     rcx, [rbp+640h+TokenHandle]; this
0x180092cb9  call    ??1AutoNoImpersonateDuringScope@Common@@QEAA@XZ; Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope(void)
0x180092cbe  test    rdi, rdi
0x180092cc1  jz      short loc_180092CCC
0x180092cc3  mov     rcx, rdi; void *
0x180092cc6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180092ccb  nop
0x180092ccc  mov     rcx, [rsp+740h+lpExistingFileName]; pv
0x180092cd1  call    cs:__imp_CoTaskMemFree
0x180092cd8  nop     dword ptr [rax+rax+00h]
0x180092cdd  nop
0x180092cde  lea     rcx, [rsp+740h+var_6E0]
0x180092ce3  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180092ce8  inc     esi
0x180092cea  jmp     loc_180092B48
0x180092cef  mov     r9d, eax; char *
0x180092cf2  lea     r8, aOnecoreAdminAp_133; "onecore\\admin\\appmodel\\common\\mrthe"...
0x180092cf9  mov     edx, 28Ch; void *
0x180092cfe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180092d03  lea     rcx, [rbp+640h+TokenHandle]; this
0x180092d07  call    ??1AutoNoImpersonateDuringScope@Common@@QEAA@XZ; Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope(void)
0x180092d0c  test    rdi, rdi
0x180092d0f  jz      short loc_180092D8E
0x180092d11  mov     rcx, rdi
0x180092d14  jmp     short loc_180092D4C
0x180092d16  mov     edx, 288h
0x180092d1b  jmp     short loc_180092D33
0x180092d1d  test    rcx, rcx
0x180092d20  jz      short loc_180092D27
0x180092d22  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180092d27  mov     ebx, 80070057h
0x180092d2c  jmp     short loc_180092D8E
0x180092d2e  mov     edx, 286h; void *
0x180092d33  lea     r8, aOnecoreAdminAp_133; "onecore\\admin\\appmodel\\common\\mrthe"...
0x180092d3a  mov     r9d, eax; char *
0x180092d3d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180092d42  mov     rcx, [rsp+740h+var_6D8+8]; void *
0x180092d47  test    rcx, rcx
0x180092d4a  jz      short loc_180092D8E
0x180092d4c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180092d51  jmp     short loc_180092D8E
0x180092d53  mov     edx, 283h
0x180092d58  jmp     short loc_180092D74
0x180092d5a  xor     ecx, ecx; pv
0x180092d5c  call    cs:__imp_CoTaskMemFree
0x180092d63  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
