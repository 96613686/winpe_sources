# Common::Deployment::MRTHelper::RedirectQualifiedFileResource(ushort const *)

- ea: `0x1800df378`
- end: `0x1800dfa8a`
- name: `?RedirectQualifiedFileResource@MRTHelper@Deployment@Common@@AEAAJPEBG@Z`
- size: `1810`
- prototype: `int(Common::Deployment::MRTHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800defe4`

## callees

- `0x18000b3bc`
- `0x18000e6e0`
- `0x18000fed0`
- `0x180012964`
- `0x18001c348`
- `0x18001c3c8`
- `0x180059270`
- `0x1800a219c`
- `0x1800df378`
- `0x1800dfa90`
- `0x1800f0260`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800df787`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800df9b2`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800df787`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800df9b2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800df4af`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800df4af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df7b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df861`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df7b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df861`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800df799`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800df9c6`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800df799`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800df9c6`

## string_xrefs

- `0x1800df43d`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x1800df7d3`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x1800df80c`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x1800df84f`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x1800df90d`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x1800df980`: `onecore\admin\appmodel\common\mrthelper.cpp`

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
  signed int v25; // edx
  const unsigned __int16 *v26; // rdx
  int Directory; // eax
  __int64 v28; // rdx
  __int64 v29; // rdx
  unsigned __int64 v30; // r9
  int v31; // eax
  int v32; // eax
  int v33; // eax
  wil::details::in1diag3 *v34; // rcx
  __int64 v35; // rdx
  signed int v36; // edx
  const unsigned __int16 *v37; // rdx
  int v38; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  __int64 v40; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v41; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v42; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v43; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v44; // [rsp+50h] [rbp-B0h] BYREF
  Common::Deployment *v45[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v46; // [rsp+68h] [rbp-98h]
  LPCWSTR lpExistingFileName; // [rsp+70h] [rbp-90h] BYREF
  __int64 v48; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v49; // [rsp+80h] [rbp-80h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp-78h] BYREF
  void *v51; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v52[4]; // [rsp+98h] [rbp-68h] BYREF
  int v53; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v54[8]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v55; // [rsp+B8h] [rbp-48h]
  wchar_t v56; // [rsp+C8h] [rbp-38h]
  WCHAR FileName[264]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t Buffer[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+4F0h] [rbp+3F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+748h] [rbp+648h]

  v41 = 0;
  v44 = 0;
  v43 = 0;
  v42 = 0;
  v40 = 0;
  *(_OWORD *)v54 = *(_OWORD *)L"%s\\resources.pri";
  v55 = *(_OWORD *)L"rces.pri";
  v56 = aSResourcesPri[16];
  *(_QWORD *)v52 = *(_QWORD *)L"%s\\%s";
  v53 = *(_DWORD *)L"s";
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(*((_QWORD *)this + 6) + 2 * v4) );
  v5 = StringCchPrintfW(Buffer, 0x104u, v54);
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
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
    return (unsigned int)v5;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  v5 = CoCreateInstance(
         &GUID_dbce7e40_7345_439d_b12c_114a11819a09,
         0,
         1u,
         &GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c,
         &v41);
  v6 = retaddr;
  if ( v5 < 0 )
  {
    v7 = 625;
    goto LABEL_5;
  }
  v5 = (*(__int64 (__fastcall **)(LPVOID, wchar_t *))(*(_QWORD *)v41 + 48LL))(v41, Buffer);
  v6 = retaddr;
  if ( v5 < 0 )
  {
    v7 = 626;
    goto LABEL_5;
  }
  v10 = v41;
  v11 = *(__int64 (__fastcall **)(LPVOID, GUID *, __int64 *))(*(_QWORD *)v41 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  v5 = v11(v10, &GUID_6e21e72b_b9b0_42ae_a686_983cf784edcd, &v44);
  v6 = retaddr;
  if ( v5 < 0 )
  {
    v7 = 627;
    goto LABEL_5;
  }
  v12 = v44;
  v13 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v44 + 32LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  v5 = v13(v12, L"Files", &v43);
  v6 = retaddr;
  if ( v5 < 0 )
  {
    v7 = 628;
    goto LABEL_5;
  }
  v14 = v43;
  v15 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, GUID *, __int64 *))(*(_QWORD *)v43 + 88LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  v5 = v15(v14, a2, &GUID_c2ac6f97_54f2_445a_8f62_d87b9537f9b2, &v42);
  v6 = retaddr;
  if ( v5 < 0 )
  {
    v7 = 629;
    goto LABEL_5;
  }
  v16 = v42;
  v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  v5 = v17(v16, &v40);
  v6 = retaddr;
  if ( v5 < 0 )
  {
    v7 = 630;
    goto LABEL_5;
  }
  v49 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v40 + 24LL))(v40, &v49);
  v6 = retaddr;
  if ( v5 < 0 )
  {
    v7 = 633;
    goto LABEL_5;
  }
  v18 = 0;
  while ( 2 )
  {
    if ( v18 < v49 )
    {
      v48 = 0;
      lpExistingFileName = 0;
      v19 = v40;
      v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v40 + 32LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
      v5 = v20(v19, v18, &v48);
      v21 = retaddr;
      if ( v5 < 0 )
      {
        v30 = (unsigned int)v5;
        v29 = 639;
      }
      else
      {
        v22 = (*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v48 + 32LL))(v48, &lpExistingFileName);
        v5 = v22;
        v21 = retaddr;
        if ( v22 < 0 )
        {
          v29 = 640;
        }
        else
        {
          if ( !lpExistingFileName )
          {
            CoTaskMemFree(0);
            v5 = -2147467261;
LABEL_48:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
            goto LABEL_7;
          }
          ppv = (_DWORD)lpExistingFileName + 2 + 2 * v4;
          v22 = StringCchPrintfW(FileName, 0x104u, v52, *((_QWORD *)this + 15));
          v5 = v22;
          v21 = retaddr;
          if ( v22 >= 0 )
          {
            *(_OWORD *)v45 = 0;
            v46 = 0;
            v23 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v45, FileName);
            v5 = v23;
            v24 = retaddr;
            if ( v23 < 0 )
            {
              v28 = 646;
LABEL_39:
              wil::details::in1diag3::_Log_Hr(
                v24,
                (void *)v28,
                (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
                (const char *)(unsigned int)v23,
                ppv);
            }
            else
            {
              v25 = (signed int)v45[0];
              do
              {
                if ( --v25 < 0 )
                {
                  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v45);
                  v5 = -2147024809;
                  goto LABEL_47;
                }
              }
              while ( *((_WORD *)v45[1] + v25) != 92 );
              v23 = Common::StringBuffer::SetLength((Common::StringBuffer *)v45, v25);
              v5 = v23;
              v24 = retaddr;
              if ( v23 < 0 )
              {
                v28 = 648;
                goto LABEL_39;
              }
              TokenHandle = 0;
              Common::AutoNoImpersonateDuringScope::DropImpersonation(&TokenHandle);
              Directory = Common::Deployment::RecursiveCreateDirectory(v45[1], v26);
              v5 = Directory;
              if ( Directory >= 0 )
              {
                SetFileAttributesW(FileName, 0x80u);
                CopyFileW(lpExistingFileName, FileName, 0);
                Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&TokenHandle);
                Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v45);
                CoTaskMemFree((LPVOID)lpExistingFileName);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
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
            }
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v45);
            goto LABEL_47;
          }
          v29 = 643;
        }
        v30 = (unsigned int)v22;
      }
      wil::details::in1diag3::_Log_Hr(
        v21,
        (void *)v29,
        (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
        (const char *)v30,
        ppv);
LABEL_47:
      CoTaskMemFree((LPVOID)lpExistingFileName);
      goto LABEL_48;
    }
    break;
  }
  ppv = (int)a2;
  v31 = StringCchPrintfW(ExistingFileName, 0x104u, v52, *((_QWORD *)this + 6));
  v5 = v31;
  v6 = retaddr;
  if ( v31 < 0 )
  {
    v8 = (unsigned int)v31;
    v7 = 665;
    goto LABEL_6;
  }
  ppv = (int)a2;
  v32 = StringCchPrintfW(FileName, 0x104u, v52, *((_QWORD *)this + 15));
  v5 = v32;
  v6 = retaddr;
  if ( v32 < 0 )
  {
    v8 = (unsigned int)v32;
    v7 = 666;
    goto LABEL_6;
  }
  *(_OWORD *)v45 = 0;
  v46 = 0;
  v33 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v45, FileName);
  v5 = v33;
  v34 = retaddr;
  if ( v33 < 0 )
  {
    v35 = 669;
LABEL_55:
    wil::details::in1diag3::_Log_Hr(
      v34,
      (void *)v35,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
      (const char *)(unsigned int)v33,
      (int)a2);
LABEL_63:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v45);
    goto LABEL_7;
  }
  v36 = (signed int)v45[0];
  do
  {
    if ( --v36 < 0 )
    {
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v45);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
      return 2147942487LL;
    }
  }
  while ( *((_WORD *)v45[1] + v36) != 92 );
  v33 = Common::StringBuffer::SetLength((Common::StringBuffer *)v45, v36);
  v5 = v33;
  v34 = retaddr;
  if ( v33 < 0 )
  {
    v35 = 671;
    goto LABEL_55;
  }
  v51 = 0;
  Common::AutoNoImpersonateDuringScope::DropImpersonation(&v51);
  v38 = Common::Deployment::RecursiveCreateDirectory(v45[1], v37);
  v5 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2A3,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
      (const char *)(unsigned int)v38,
      (int)a2);
    Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&v51);
    goto LABEL_63;
  }
  SetFileAttributesW(FileName, 0x80u);
  CopyFileW(ExistingFileName, FileName, 0);
  Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&v51);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v45);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  return 0;
}

```

## disassembly

```asm
0x1800df378  mov     [rsp-8+arg_10], rbx
0x1800df37d  push    rbp
0x1800df37e  push    rsi
0x1800df37f  push    rdi
0x1800df380  push    r12
0x1800df382  push    r13
0x1800df384  push    r14
0x1800df386  push    r15
0x1800df388  lea     rbp, [rsp-610h]
0x1800df390  sub     rsp, 710h
0x1800df397  mov     rax, cs:__security_cookie
0x1800df39e  xor     rax, rsp
0x1800df3a1  mov     [rbp+640h+var_40], rax
0x1800df3a8  mov     r12, rdx
0x1800df3ab  mov     r15, rcx
0x1800df3ae  xor     r13d, r13d
0x1800df3b1  mov     [rsp+740h+var_708], r13
0x1800df3b6  mov     [rsp+740h+var_6F0], r13
0x1800df3bb  mov     [rsp+740h+var_6F8], r13
0x1800df3c0  mov     [rsp+740h+var_700], r13
0x1800df3c5  mov     [rsp+740h+var_710], r13
0x1800df3ca  movups  xmm0, xmmword ptr cs:aSResourcesPri; "%s\\resources.pri"
0x1800df3d1  movups  xmmword ptr [rbp+640h+var_698], xmm0
0x1800df3d5  movups  xmm1, xmmword ptr cs:aSResourcesPri+10h; "rces.pri"
0x1800df3dc  movups  [rbp+640h+var_688], xmm1
0x1800df3e0  movzx   eax, word ptr cs:aSResourcesPri+20h; ""
0x1800df3e7  mov     [rbp+640h+var_678], ax
0x1800df3eb  movsd   xmm0, qword ptr cs:aSS; "%s\\%s"
0x1800df3f3  movsd   qword ptr [rbp+640h+var_6A8], xmm0
0x1800df3f8  mov     eax, dword ptr cs:aSS+8; "s"
0x1800df3fe  mov     [rbp+640h+var_6A0], eax
0x1800df401  mov     r9, [rcx+30h]
0x1800df405  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800df409  inc     r14
0x1800df40c  cmp     [r9+r14*2], r13w
0x1800df411  jnz     short loc_1800DF409
0x1800df413  lea     r8, [rbp+640h+var_698]; unsigned __int16 *
0x1800df417  mov     edx, 104h; unsigned __int64
0x1800df41c  lea     rcx, [rbp+640h+Buffer]; Buffer
0x1800df423  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800df428  mov     ebx, eax
0x1800df42a  mov     rcx, [rbp+648h]; this
0x1800df431  test    eax, eax
0x1800df433  jns     short loc_1800DF487
0x1800df435  mov     edx, 26Fh; void *
0x1800df43a  mov     r9d, ebx; char *
0x1800df43d  lea     r8, aOnecoreAdminAp_164; "onecore\\admin\\appmodel\\common\\mrthe"...
0x1800df444  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800df449  nop
0x1800df44a  lea     rcx, [rsp+740h+var_710]
0x1800df44f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800df454  nop
0x1800df455  lea     rcx, [rsp+740h+var_700]
0x1800df45a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800df45f  nop
0x1800df460  lea     rcx, [rsp+740h+var_6F8]
0x1800df465  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800df46a  nop
0x1800df46b  lea     rcx, [rsp+740h+var_6F0]
0x1800df470  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800df475  nop
0x1800df476  lea     rcx, [rsp+740h+var_708]
0x1800df47b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800df480  mov     eax, ebx
0x1800df482  jmp     loc_1800DFA60
0x1800df487  lea     rcx, [rsp+740h+var_708]
0x1800df48c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800df491  lea     rax, [rsp+740h+var_708]
0x1800df496  mov     qword ptr [rsp+740h+ppv], rax; int
0x1800df49b  lea     r9, _GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c; riid
0x1800df4a2  xor     edx, edx; pUnkOuter
0x1800df4a4  lea     r8d, [rdx+1]; dwClsContext
0x1800df4a8  lea     rcx, _GUID_dbce7e40_7345_439d_b12c_114a11819a09; rclsid
0x1800df4af  call    cs:__imp_CoCreateInstance
0x1800df4b5  mov     ebx, eax
0x1800df4b7  mov     rcx, [rbp+648h]
0x1800df4be  test    eax, eax
0x1800df4c0  jns     short loc_1800DF4CC
0x1800df4c2  mov     edx, 271h
0x1800df4c7  jmp     loc_1800DF43A
0x1800df4cc  mov     rcx, [rsp+740h+var_708]
0x1800df4d1  mov     rax, [rcx]
0x1800df4d4  lea     rdx, [rbp+640h+Buffer]
0x1800df4db  mov     rax, [rax+30h]
0x1800df4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df4e4  mov     ebx, eax
0x1800df4e6  mov     rcx, [rbp+648h]
0x1800df4ed  test    eax, eax
0x1800df4ef  jns     short loc_1800DF4FB
0x1800df4f1  mov     edx, 272h
0x1800df4f6  jmp     loc_1800DF43A
0x1800df4fb  mov     rdi, [rsp+740h+var_708]
0x1800df500  mov     rax, [rdi]
0x1800df503  mov     rbx, [rax+38h]
0x1800df507  lea     rcx, [rsp+740h+var_6F0]
0x1800df50c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800df511  lea     r8, [rsp+740h+var_6F0]
0x1800df516  lea     rdx, _GUID_6e21e72b_b9b0_42ae_a686_983cf784edcd
0x1800df51d  mov     rcx, rdi
0x1800df520  mov     rax, rbx
0x1800df523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df528  mov     ebx, eax
0x1800df52a  mov     rcx, [rbp+648h]
0x1800df531  test    eax, eax
0x1800df533  jns     short loc_1800DF53F
0x1800df535  mov     edx, 273h
0x1800df53a  jmp     loc_1800DF43A
0x1800df53f  mov     rdi, [rsp+740h+var_6F0]
0x1800df544  mov     rax, [rdi]
0x1800df547  mov     rbx, [rax+20h]
0x1800df54b  lea     rcx, [rsp+740h+var_6F8]
0x1800df550  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800df555  lea     r8, [rsp+740h+var_6F8]
0x1800df55a  lea     rdx, aFiles; "Files"
0x1800df561  mov     rcx, rdi
0x1800df564  mov     rax, rbx
0x1800df567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df56c  mov     ebx, eax
0x1800df56e  mov     rcx, [rbp+648h]
0x1800df575  test    eax, eax
0x1800df577  jns     short loc_1800DF583
0x1800df579  mov     edx, 274h
0x1800df57e  jmp     loc_1800DF43A
0x1800df583  mov     rdi, [rsp+740h+var_6F8]
0x1800df588  mov     rax, [rdi]
0x1800df58b  mov     rbx, [rax+58h]
0x1800df58f  lea     rcx, [rsp+740h+var_700]
0x1800df594  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800df599  lea     r9, [rsp+740h+var_700]
0x1800df59e  lea     r8, _GUID_c2ac6f97_54f2_445a_8f62_d87b9537f9b2
0x1800df5a5  mov     rdx, r12
0x1800df5a8  mov     rcx, rdi
0x1800df5ab  mov     rax, rbx
0x1800df5ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df5b3  mov     ebx, eax
0x1800df5b5  mov     rcx, [rbp+648h]
0x1800df5bc  test    eax, eax
0x1800df5be  jns     short loc_1800DF5CA
0x1800df5c0  mov     edx, 275h
0x1800df5c5  jmp     loc_1800DF43A
0x1800df5ca  mov     rdi, [rsp+740h+var_700]
0x1800df5cf  mov     rax, [rdi]
0x1800df5d2  mov     rbx, [rax+40h]
0x1800df5d6  lea     rcx, [rsp+740h+var_710]
0x1800df5db  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800df5e0  lea     rdx, [rsp+740h+var_710]
0x1800df5e5  mov     rcx, rdi
0x1800df5e8  mov     rax, rbx
0x1800df5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df5f0  mov     ebx, eax
0x1800df5f2  mov     rcx, [rbp+648h]
0x1800df5f9  test    eax, eax
0x1800df5fb  jns     short loc_1800DF607
0x1800df5fd  mov     edx, 276h
0x1800df602  jmp     loc_1800DF43A
0x1800df607  mov     [rbp+640h+var_6C0], r13d
0x1800df60b  mov     rcx, [rsp+740h+var_710]
0x1800df610  mov     rax, [rcx]
0x1800df613  lea     rdx, [rbp+640h+var_6C0]
0x1800df617  mov     rax, [rax+18h]
0x1800df61b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df620  mov     ebx, eax
0x1800df622  mov     rcx, [rbp+648h]
0x1800df629  test    eax, eax
0x1800df62b  jns     short loc_1800DF637
0x1800df62d  mov     edx, 279h
0x1800df632  jmp     loc_1800DF43A
0x1800df637  mov     esi, r13d
0x1800df63a  mov     edi, 104h
0x1800df63f  cmp     esi, [rbp+640h+var_6C0]
0x1800df642  jnb     loc_1800DF877
0x1800df648  mov     [rsp+740h+var_6C8], r13
0x1800df64d  mov     [rsp+740h+lpExistingFileName], r13
0x1800df652  mov     rdi, [rsp+740h+var_710]
0x1800df657  mov     rax, [rdi]
0x1800df65a  mov     rbx, [rax+20h]
0x1800df65e  lea     rcx, [rsp+740h+var_6C8]
0x1800df663  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800df668  lea     r8, [rsp+740h+var_6C8]
0x1800df66d  mov     edx, esi
0x1800df66f  mov     rcx, rdi
0x1800df672  mov     rax, rbx
0x1800df675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df67a  mov     ebx, eax
0x1800df67c  mov     rcx, [rbp+648h]; this
0x1800df683  test    eax, eax
0x1800df685  js      loc_1800DF847
0x1800df68b  mov     rcx, [rsp+740h+var_6C8]
0x1800df690  mov     rax, [rcx]
0x1800df693  lea     rdx, [rsp+740h+lpExistingFileName]
0x1800df698  mov     rax, [rax+20h]
0x1800df69c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df6a1  mov     ebx, eax
0x1800df6a3  mov     rcx, [rbp+648h]
0x1800df6aa  test    eax, eax
0x1800df6ac  js      loc_1800DF83D
0x1800df6b2  mov     rax, [rsp+740h+lpExistingFileName]
0x1800df6b7  test    rax, rax
0x1800df6ba  jz      loc_1800DF82E
0x1800df6c0  lea     rcx, [rax+2]
0x1800df6c4  lea     rcx, [rcx+r14*2]
0x1800df6c8  mov     qword ptr [rsp+740h+ppv], rcx; int
0x1800df6cd  mov     r9, [r15+78h]
0x1800df6d1  lea     r8, [rbp+640h+var_6A8]; unsigned __int16 *
0x1800df6d5  mov     edi, 104h
0x1800df6da  mov     edx, edi; unsigned __int64
0x1800df6dc  lea     rcx, [rbp+640h+FileName]; Buffer
0x1800df6e0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800df6e5  mov     ebx, eax
0x1800df6e7  mov     rcx, [rbp+648h]
0x1800df6ee  test    eax, eax
0x1800df6f0  js      loc_1800DF827
0x1800df6f6  xorps   xmm0, xmm0
0x1800df6f9  movups  xmmword ptr [rsp+740h+var_6E8], xmm0
0x1800df6fe  mov     [rsp+740h+var_6D8], r13d
0x1800df703  lea     rdx, [rbp+640h+FileName]; unsigned __int16 *
0x1800df707  lea     rcx, [rsp+740h+var_6E8]; this
0x1800df70c  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800df711  mov     ebx, eax
0x1800df713  mov     rcx, [rbp+648h]; this
0x1800df71a  test    eax, eax
0x1800df71c  js      loc_1800DF807
0x1800df722  mov     edx, dword ptr [rsp+740h+var_6E8]
0x1800df726  mov     rcx, [rsp+740h+var_6E8+8]
0x1800df72b  dec     edx; unsigned int
0x1800df72d  test    edx, edx
0x1800df72f  js      loc_1800DF7F6
0x1800df735  movsxd  rax, edx
0x1800df738  cmp     word ptr [rcx+rax*2], 5Ch ; '\'
0x1800df73d  jnz     short loc_1800DF72B
0x1800df73f  lea     rcx, [rsp+740h+var_6E8]; this
0x1800df744  call    ?SetLength@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetLength(ulong)
0x1800df749  mov     ebx, eax
0x1800df74b  mov     rcx, [rbp+648h]
0x1800df752  test    eax, eax
0x1800df754  js      loc_1800DF7EF
0x1800df75a  mov     [rbp+640h+TokenHandle], r13
0x1800df75e  lea     rcx, [rbp+640h+TokenHandle]; TokenHandle
0x1800df762  call    ?DropImpersonation@AutoNoImpersonateDuringScope@Common@@QEAAJXZ; Common::AutoNoImpersonateDuringScope::DropImpersonation(void)
0x1800df767  mov     rcx, [rsp+740h+var_6E8+8]; this
0x1800df76c  call    ?RecursiveCreateDirectory@Deployment@Common@@YAJPEBG@Z; Common::Deployment::RecursiveCreateDirectory(ushort const *)
0x1800df771  mov     ebx, eax
0x1800df773  mov     rcx, [rbp+648h]; this
0x1800df77a  test    eax, eax
0x1800df77c  js      short loc_1800DF7D0
0x1800df77e  mov     edx, 80h; dwFileAttributes
0x1800df783  lea     rcx, [rbp+640h+FileName]; lpFileName
0x1800df787  call    cs:__imp_SetFileAttributesW
0x1800df78d  xor     r8d, r8d; bFailIfExists
0x1800df790  lea     rdx, [rbp+640h+FileName]; lpNewFileName
0x1800df794  mov     rcx, [rsp+740h+lpExistingFileName]; lpExistingFileName
0x1800df799  call    cs:__imp_CopyFileW
0x1800df79f  lea     rcx, [rbp+640h+TokenHandle]; this
0x1800df7a3  call    ??1AutoNoImpersonateDuringScope@Common@@QEAA@XZ; Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope(void)
0x1800df7a8  lea     rcx, [rsp+740h+var_6E8]; this
0x1800df7ad  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800df7b2  nop
0x1800df7b3  mov     rcx, [rsp+740h+lpExistingFileName]; pv
0x1800df7b8  call    cs:__imp_CoTaskMemFree
0x1800df7be  nop
0x1800df7bf  lea     rcx, [rsp+740h+var_6C8]
0x1800df7c4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800df7c9  inc     esi
0x1800df7cb  jmp     loc_1800DF63F
0x1800df7d0  mov     r9d, eax; char *
0x1800df7d3  lea     r8, aOnecoreAdminAp_164; "onecore\\admin\\appmodel\\common\\mrthe"...
0x1800df7da  mov     edx, 28Ch; void *
0x1800df7df  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800df7e4  lea     rcx, [rbp+640h+TokenHandle]; this
0x1800df7e8  call    ??1AutoNoImpersonateDuringScope@Common@@QEAA@XZ; Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope(void)
0x1800df7ed  jmp     short loc_1800DF81B
0x1800df7ef  mov     edx, 288h
0x1800df7f4  jmp     short loc_1800DF80C
0x1800df7f6  lea     rcx, [rsp+740h+var_6E8]; this
0x1800df7fb  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800df800  mov     ebx, 80070057h
0x1800df805  jmp     short loc_1800DF85C
0x1800df807  mov     edx, 286h; void *
0x1800df80c  lea     r8, aOnecoreAdminAp_164; "onecore\\admin\\appmodel\\common\\mrthe"...
0x1800df813  mov     r9d, eax; char *
0x1800df816  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800df81b  lea     rcx, [rsp+740h+var_6E8]; this
0x1800df820  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800df825  jmp     short loc_1800DF85C
0x1800df827  mov     edx, 283h
0x1800df82c  jmp     short loc_1800DF842
0x1800df82e  xor     ecx, ecx; pv
0x1800df830  call    cs:__imp_CoTaskMemFree
0x1800df836  mov     ebx, 80004003h
0x1800df83b  jmp     short loc_1800DF868
0x1800df83d  mov     edx, 280h
0x1800df842  mov     r9d, eax
0x1800df845  jmp     short loc_1800DF84F
0x1800df847  mov     r9d, ebx; char *
0x1800df84a  mov     edx, 27Fh; void *
0x1800df84f  lea     r8, aOnecoreAdminAp_164; "onecore\\admin\\appmodel\\common\\mrthe"...
0x1800df856  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800df85b  nop
0x1800df85c  mov     rcx, [rsp+740h+lpExistingFileName]; pv
0x1800df861  call    cs:__imp_CoTaskMemFree
  ... truncated ...
```
