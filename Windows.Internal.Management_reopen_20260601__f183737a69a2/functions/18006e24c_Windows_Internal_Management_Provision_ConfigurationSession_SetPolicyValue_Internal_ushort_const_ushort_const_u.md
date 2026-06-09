# Windows::Internal::Management::Provision::ConfigurationSession::SetPolicyValue_Internal(ushort const *,ushort const *,ushort const *,ushort const *,Windows::Internal::Management::Provision::IConfigurationData *)

- ea: `0x18006e24c`
- end: `0x18006e9a8`
- name: `?SetPolicyValue_Internal@ConfigurationSession@Provision@Management@Internal@Windows@@CAJPEBG000PEAUIConfigurationData@2345@@Z`
- size: `1884`
- prototype: `__int64 __usercall@<rax>(OLECHAR *psz@<rcx>, OLECHAR *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, struct Windows::Internal::Management::Provision::IConfigurationData *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006c5c4`

## callees

- `0x180004eb0`
- `0x180009be4`
- `0x18000a5c4`
- `0x18000ac30`
- `0x18003e74c`
- `0x18006e24c`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e3aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e3aa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006e6ed`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006e6ed`
- `OLEAUT32!__imp_SysAllocString` at `0x18006e3b9`
- `OLEAUT32!__imp_SysAllocString` at `0x18006e76e`
- `OLEAUT32!__imp_SysAllocString` at `0x18006e80c`
- `OLEAUT32!__imp_SysAllocString` at `0x18006e3b9`
- `OLEAUT32!__imp_SysAllocString` at `0x18006e76e`
- `OLEAUT32!__imp_SysAllocString` at `0x18006e80c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18006e75d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18006e75d`
- `OLEAUT32!__imp_VariantInit` at `0x18006e331`
- `OLEAUT32!__imp_VariantInit` at `0x18006e72e`
- `OLEAUT32!__imp_VariantInit` at `0x18006e7f3`
- `OLEAUT32!__imp_VariantInit` at `0x18006e331`
- `OLEAUT32!__imp_VariantInit` at `0x18006e72e`
- `OLEAUT32!__imp_VariantInit` at `0x18006e7f3`
- `OLEAUT32!__imp_VariantClear` at `0x18006e7d5`
- `OLEAUT32!__imp_VariantClear` at `0x18006e870`
- `OLEAUT32!__imp_VariantClear` at `0x18006e885`
- `OLEAUT32!__imp_VariantClear` at `0x18006e957`
- `OLEAUT32!__imp_VariantClear` at `0x18006e976`
- `OLEAUT32!__imp_VariantClear` at `0x18006e7d5`
- `OLEAUT32!__imp_VariantClear` at `0x18006e870`
- `OLEAUT32!__imp_VariantClear` at `0x18006e885`
- `OLEAUT32!__imp_VariantClear` at `0x18006e957`
- `OLEAUT32!__imp_VariantClear` at `0x18006e976`
- `DMOleAutUtils!ByteArrayToSafeArray` at `0x18006e62e`
- `DMOleAutUtils!ByteArrayToSafeArray` at `0x18006e62e`

## string_xrefs

- `0x18006e83a`: `OMADM::TargetedUserSID`
- `0x18006e2ea`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006e3e9`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006e4bd`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006e514`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006e57b`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006e5e3`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006e64a`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006e709`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006e7bf`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006e85a`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006e8d5`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006e2ca`: `./%s/Vendor/MSFT/Policy/Config/%s/%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::Internal::Management::Provision::ConfigurationSession::SetPolicyValue_Internal(
        OLECHAR *psz,
        OLECHAR *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct Windows::Internal::Management::Provision::IConfigurationData *a5)
{
  __int64 v8; // r14
  unsigned int v9; // esi
  __int64 v10; // rax
  char v11; // r12
  const wchar_t *v12; // r9
  int v13; // edi
  __int64 v14; // rdx
  unsigned int v16; // ebx
  int v17; // eax
  __int64 v18; // rdx
  const OLECHAR *StringRawBuffer; // rax
  BSTR v20; // rax
  LONG v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rcx
  HRESULT v33; // eax
  BSTR v34; // rax
  int v35; // eax
  int v36; // eax
  LPVOID v37; // rdi
  __int64 (__fastcall *v38)(LPVOID, unsigned __int16 *, __int64 *); // rbx
  int v39; // eax
  __int64 v40; // rdx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  _BYTE v43[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v44; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v45; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v46; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v47; // [rsp+50h] [rbp-B0h] BYREF
  int v48; // [rsp+58h] [rbp-A8h] BYREF
  LONG v49; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v50; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG v52; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG v53; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR *v55; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int8 *v56; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG v57; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v58[264]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  v8 = -1;
  v9 = 0;
  if ( !a2 )
    goto LABEL_5;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  v11 = 1;
  if ( !v10 )
LABEL_5:
    v11 = 0;
  v12 = L"User";
  if ( !v11 )
    v12 = L"Device";
  v13 = StringCchPrintfW(v58, 0x104u, L"./%s/Vendor/MSFT/Policy/Config/%s/%s", v12, a3, a4);
  if ( v13 < 0 )
  {
    v14 = 166;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
      (const char *)(unsigned int)v13,
      ppv);
    return (unsigned int)v13;
  }
  v48 = 0;
  v13 = (*(__int64 (__fastcall **)(struct Windows::Internal::Management::Provision::IConfigurationData *, int *))(*(_QWORD *)a5 + 48LL))(
          a5,
          &v48);
  if ( v13 < 0 )
  {
    v14 = 170;
    goto LABEL_10;
  }
  VariantInit(&pvarg);
  switch ( v48 )
  {
    case 1:
      v44 = 0;
      v22 = (*(__int64 (__fastcall **)(struct Windows::Internal::Management::Provision::IConfigurationData *, __int64 *))(*(_QWORD *)a5 + 64LL))(
              a5,
              &v44);
      v16 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDC,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
          (const char *)(unsigned int)v22,
          ppv);
        v23 = v44;
        if ( v44 )
        {
          v44 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        }
        goto LABEL_78;
      }
      v46 = 0;
      v24 = Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(
              &v44,
              &v46);
      v16 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDF,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
          (const char *)(unsigned int)v24,
          ppv);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
        v25 = v44;
        if ( v44 )
        {
          v44 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        }
        goto LABEL_78;
      }
      v56 = 0;
      v26 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 **))(*(_QWORD *)v46 + 24LL))(v46, &v56);
      v16 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE2,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
          (const char *)(unsigned int)v26,
          ppv);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
        v27 = v44;
        if ( v44 )
        {
          v44 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
        goto LABEL_78;
      }
      v50 = 0;
      v28 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v44 + 56LL))(v44, &v50);
      v16 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE5,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
          (const char *)(unsigned int)v28,
          ppv);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
        v29 = v44;
        if ( v44 )
        {
          v44 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
        goto LABEL_78;
      }
      v30 = ByteArrayToSafeArray(v56, v50, &pvarg.parray);
      v16 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE7,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
          (const char *)(unsigned int)v30,
          ppv);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
        v31 = v44;
        if ( v44 )
        {
          v44 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        }
        goto LABEL_78;
      }
      v9 = 6;
      pvarg.vt = 8209;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      v32 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      }
LABEL_56:
      v45 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      v33 = CoCreateInstance(
              &GUID_66d0db14_5638_475f_a386_629522d8c461,
              0,
              1u,
              &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
              &v45);
      v16 = v33;
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF8,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
          (const char *)(unsigned int)v33,
          ppva);
LABEL_58:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        goto LABEL_78;
      }
      VariantInit(&v52);
      v52.vt = 8;
      if ( *psz == 123 )
      {
        do
          ++v8;
        while ( psz[v8] );
        v34 = SysAllocStringLen(psz + 1, (int)v8 - 2);
      }
      else
      {
        v34 = SysAllocString(psz);
      }
      v52.llVal = (LONGLONG)v34;
      v53 = v52;
      v35 = (*(__int64 (__fastcall **)(LPVOID, const char *, VARIANTARG *))(*(_QWORD *)v45 + 104LL))(
              v45,
              L"OMADM::AccountID",
              &v53);
      v16 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x107,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
          (const char *)(unsigned int)v35,
          ppva);
LABEL_65:
        VariantClear(&v52);
        goto LABEL_58;
      }
      if ( v11 )
      {
        VariantInit(&v53);
        v53.vt = 8;
        v53.llVal = (LONGLONG)SysAllocString(a2);
        v57 = v53;
        v36 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(*(_QWORD *)v45 + 104LL))(
                v45,
                L"OMADM::TargetedUserSID",
                &v57);
        v16 = v36;
        if ( v36 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x10E,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
            (const char *)(unsigned int)v36,
            ppva);
          VariantClear(&v53);
          goto LABEL_65;
        }
        VariantClear(&v53);
      }
      v47 = 0;
      v37 = v45;
      v38 = *(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, __int64 *))(*(_QWORD *)v45 + 80LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      v39 = v38(v37, v58, &v47);
      v16 = v39;
      if ( v39 >= 0 )
      {
        v57 = pvarg;
        v39 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, _QWORD))(*(_QWORD *)v47 + 96LL))(v47, &v57, v9);
        v16 = v39;
        if ( v39 >= 0 )
        {
          v39 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v45 + 24LL))(v45);
          v16 = v39;
          if ( v39 >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
            VariantClear(&v52);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
            v16 = 0;
            goto LABEL_78;
          }
          v40 = 277;
        }
        else
        {
          v40 = 276;
        }
      }
      else
      {
        v40 = 274;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v40,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
        (const char *)(unsigned int)v39,
        ppva);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      goto LABEL_65;
    case 2:
      v43[0] = 0;
      v17 = (*(__int64 (__fastcall **)(struct Windows::Internal::Management::Provision::IConfigurationData *, _BYTE *))(*(_QWORD *)a5 + 56LL))(
              a5,
              v43);
      v16 = v17;
      if ( v17 < 0 )
      {
        v18 = 200;
        goto LABEL_24;
      }
      pvarg.vt = 3;
      v21 = v43[0];
LABEL_30:
      pvarg.lVal = v21;
      goto LABEL_56;
    case 3:
      v49 = 0;
      v17 = (*(__int64 (__fastcall **)(struct Windows::Internal::Management::Provision::IConfigurationData *, LONG *))(*(_QWORD *)a5 + 72LL))(
              a5,
              &v49);
      v16 = v17;
      if ( v17 < 0 )
      {
        v18 = 180;
        goto LABEL_24;
      }
      pvarg.vt = 3;
      v21 = v49;
      goto LABEL_30;
    case 4:
      v55 = 0;
      v17 = (*(__int64 (__fastcall **)(struct Windows::Internal::Management::Provision::IConfigurationData *, OLECHAR **))(*(_QWORD *)a5 + 80LL))(
              a5,
              &v55);
      v16 = v17;
      if ( v17 < 0 )
      {
        v18 = 190;
        goto LABEL_24;
      }
      v9 = 11;
      pvarg.vt = 20;
      v20 = v55;
      goto LABEL_26;
    case 5:
      string = 0;
      v17 = (*(__int64 (__fastcall **)(struct Windows::Internal::Management::Provision::IConfigurationData *, HSTRING *))(*(_QWORD *)a5 + 88LL))(
              a5,
              &string);
      v16 = v17;
      if ( v17 < 0 )
      {
        v18 = 210;
LABEL_24:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
          (const char *)(unsigned int)v17,
          ppv);
        goto LABEL_78;
      }
      v9 = 1;
      pvarg.vt = 8;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v20 = SysAllocString(StringRawBuffer);
LABEL_26:
      pvarg.llVal = (LONGLONG)v20;
      goto LABEL_56;
  }
  v16 = -2147024809;
LABEL_78:
  VariantClear(&pvarg);
  return v16;
}

```

## disassembly

```asm
0x18006e24c  push    rbp
0x18006e24e  push    rbx
0x18006e24f  push    rsi
0x18006e250  push    rdi
0x18006e251  push    r12
0x18006e253  push    r13
0x18006e255  push    r14
0x18006e257  push    r15
0x18006e259  lea     rbp, [rsp-228h]
0x18006e261  sub     rsp, 328h
0x18006e268  mov     rax, cs:__security_cookie
0x18006e26f  xor     rax, rsp
0x18006e272  mov     [rbp+260h+var_50], rax
0x18006e279  mov     r10, r9
0x18006e27c  mov     r13, rdx
0x18006e27f  mov     r15, rcx
0x18006e282  mov     rbx, [rbp+260h+arg_20]
0x18006e289  or      r14, 0FFFFFFFFFFFFFFFFh
0x18006e28d  xor     esi, esi
0x18006e28f  test    rdx, rdx
0x18006e292  jz      short loc_18006E2A8
0x18006e294  mov     rax, r14
0x18006e297  inc     rax
0x18006e29a  cmp     [rdx+rax*2], si
0x18006e29e  jnz     short loc_18006E297
0x18006e2a0  test    rax, rax
0x18006e2a3  mov     r12b, 1
0x18006e2a6  jnz     short loc_18006E2AB
0x18006e2a8  mov     r12b, sil
0x18006e2ab  lea     rax, aDevice; "Device"
0x18006e2b2  lea     r9, aUser_0; "User"
0x18006e2b9  test    r12b, r12b
0x18006e2bc  cmovz   r9, rax
0x18006e2c0  mov     [rsp+360h+var_338], r10
0x18006e2c5  mov     [rsp+360h+ppv], r8; int
0x18006e2ca  lea     r8, aSVendorMsftPol; "./%s/Vendor/MSFT/Policy/Config/%s/%s"
0x18006e2d1  mov     edx, 104h; unsigned __int64
0x18006e2d6  lea     rcx, [rbp+260h+var_260]; unsigned __int16 *
0x18006e2da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006e2df  mov     edi, eax
0x18006e2e1  test    eax, eax
0x18006e2e3  jns     short loc_18006E307
0x18006e2e5  mov     edx, 0A6h; void *
0x18006e2ea  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006e2f1  mov     r9d, edi; char *
0x18006e2f4  mov     rcx, [rbp+268h]; this
0x18006e2fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e300  mov     eax, edi
0x18006e302  jmp     loc_18006E984
0x18006e307  mov     [rsp+360h+var_308], esi
0x18006e30b  mov     rax, [rbx]
0x18006e30e  lea     rdx, [rsp+360h+var_308]
0x18006e313  mov     rcx, rbx
0x18006e316  mov     rax, [rax+30h]
0x18006e31a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e31f  mov     edi, eax
0x18006e321  test    eax, eax
0x18006e323  jns     short loc_18006E32C
0x18006e325  mov     edx, 0AAh
0x18006e32a  jmp     short loc_18006E2EA
0x18006e32c  lea     rcx, [rsp+360h+pvarg]; pvarg
0x18006e331  call    cs:__imp_VariantInit
0x18006e338  nop     dword ptr [rax+rax+00h]
0x18006e33d  nop
0x18006e33e  mov     ecx, [rsp+360h+var_308]
0x18006e342  mov     edi, 8
0x18006e347  sub     ecx, 1
0x18006e34a  jz      loc_18006E494
0x18006e350  sub     ecx, 1
0x18006e353  jz      loc_18006E45A
0x18006e359  sub     ecx, 1
0x18006e35c  jz      loc_18006E41C
0x18006e362  sub     ecx, 1
0x18006e365  jz      short loc_18006E3C7
0x18006e367  cmp     ecx, 1
0x18006e36a  jz      short loc_18006E376
0x18006e36c  mov     ebx, 80070057h
0x18006e371  jmp     loc_18006E971
0x18006e376  mov     [rbp+260h+string], rsi
0x18006e37a  mov     rax, [rbx]
0x18006e37d  lea     rdx, [rbp+260h+string]
0x18006e381  mov     rcx, rbx
0x18006e384  mov     rax, [rax+58h]
0x18006e388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e38d  mov     ebx, eax
0x18006e38f  test    eax, eax
0x18006e391  jns     short loc_18006E39A
0x18006e393  mov     edx, 0D2h
0x18006e398  jmp     short loc_18006E3E9
0x18006e39a  mov     esi, 1
0x18006e39f  mov     word ptr [rsp+360h+pvarg], di
0x18006e3a4  xor     edx, edx; length
0x18006e3a6  mov     rcx, [rbp+260h+string]; string
0x18006e3aa  call    cs:__imp_WindowsGetStringRawBuffer
0x18006e3b1  nop     dword ptr [rax+rax+00h]
0x18006e3b6  mov     rcx, rax; psz
0x18006e3b9  call    cs:__imp_SysAllocString
0x18006e3c0  nop     dword ptr [rax+rax+00h]
0x18006e3c5  jmp     short loc_18006E415
0x18006e3c7  mov     [rbp+260h+var_298], rsi
0x18006e3cb  mov     rax, [rbx]
0x18006e3ce  lea     rdx, [rbp+260h+var_298]
0x18006e3d2  mov     rcx, rbx
0x18006e3d5  mov     rax, [rax+50h]
0x18006e3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e3de  mov     ebx, eax
0x18006e3e0  test    eax, eax
0x18006e3e2  jns     short loc_18006E404
0x18006e3e4  mov     edx, 0BEh; void *
0x18006e3e9  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006e3f0  mov     r9d, eax; char *
0x18006e3f3  mov     rcx, [rbp+268h]; this
0x18006e3fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e3ff  jmp     loc_18006E971
0x18006e404  mov     esi, 0Bh
0x18006e409  lea     eax, [rsi+9]
0x18006e40c  mov     word ptr [rsp+360h+pvarg], ax
0x18006e411  mov     rax, [rbp+260h+var_298]
0x18006e415  mov     qword ptr [rsp+360h+pvarg+8], rax
0x18006e41a  jmp     short loc_18006E453
0x18006e41c  mov     [rsp+360h+var_304], esi
0x18006e420  mov     rax, [rbx]
0x18006e423  lea     rdx, [rsp+360h+var_304]
0x18006e428  mov     rcx, rbx
0x18006e42b  mov     rax, [rax+48h]
0x18006e42f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e434  mov     ebx, eax
0x18006e436  test    eax, eax
0x18006e438  jns     short loc_18006E441
0x18006e43a  mov     edx, 0B4h
0x18006e43f  jmp     short loc_18006E3E9
0x18006e441  mov     eax, 3
0x18006e446  mov     word ptr [rsp+360h+pvarg], ax
0x18006e44b  mov     eax, [rsp+360h+var_304]
0x18006e44f  mov     dword ptr [rsp+360h+pvarg+8], eax
0x18006e453  xor     edi, edi
0x18006e455  jmp     loc_18006E6C0
0x18006e45a  mov     [rsp+360h+var_330], sil
0x18006e45f  mov     rax, [rbx]
0x18006e462  lea     rdx, [rsp+360h+var_330]
0x18006e467  mov     rcx, rbx
0x18006e46a  mov     rax, [rax+38h]
0x18006e46e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e473  mov     ebx, eax
0x18006e475  test    eax, eax
0x18006e477  jns     short loc_18006E483
0x18006e479  mov     edx, 0C8h
0x18006e47e  jmp     loc_18006E3E9
0x18006e483  mov     eax, 3
0x18006e488  mov     word ptr [rsp+360h+pvarg], ax
0x18006e48d  movzx   eax, [rsp+360h+var_330]
0x18006e492  jmp     short loc_18006E44F
0x18006e494  mov     [rsp+360h+var_328], rsi
0x18006e499  mov     rax, [rbx]
0x18006e49c  lea     rdx, [rsp+360h+var_328]
0x18006e4a1  mov     rcx, rbx
0x18006e4a4  mov     rax, [rax+40h]
0x18006e4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e4ad  mov     ebx, eax
0x18006e4af  test    eax, eax
0x18006e4b1  jns     short loc_18006E4F0
0x18006e4b3  mov     rcx, [rbp+268h]; this
0x18006e4ba  mov     r9d, eax; char *
0x18006e4bd  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006e4c4  mov     edx, 0DCh; void *
0x18006e4c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e4ce  nop
0x18006e4cf  mov     rcx, [rsp+360h+var_328]
0x18006e4d4  test    rcx, rcx
0x18006e4d7  jz      short loc_18006E4EB
0x18006e4d9  mov     [rsp+360h+var_328], rsi
0x18006e4de  mov     rax, [rcx]
0x18006e4e1  mov     rax, [rax+10h]
0x18006e4e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e4ea  nop
0x18006e4eb  jmp     loc_18006E971
0x18006e4f0  mov     [rsp+360h+var_318], rsi
0x18006e4f5  lea     rdx, [rsp+360h+var_318]
0x18006e4fa  lea     rcx, [rsp+360h+var_328]
0x18006e4ff  call    ??$As@UIBufferByteAccess@Streams@Storage@Windows@@@?$ComPtr@UIBuffer@Streams@Storage@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIBufferByteAccess@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBufferByteAccess>>)
0x18006e504  mov     ebx, eax
0x18006e506  test    eax, eax
0x18006e508  jns     short loc_18006E552
0x18006e50a  mov     rcx, [rbp+268h]; this
0x18006e511  mov     r9d, eax; char *
0x18006e514  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006e51b  mov     edx, 0DFh; void *
0x18006e520  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e525  nop
0x18006e526  lea     rcx, [rsp+360h+var_318]
0x18006e52b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e530  nop
0x18006e531  mov     rcx, [rsp+360h+var_328]
0x18006e536  test    rcx, rcx
0x18006e539  jz      short loc_18006E54D
0x18006e53b  mov     [rsp+360h+var_328], rsi
0x18006e540  mov     rax, [rcx]
0x18006e543  mov     rax, [rax+10h]
0x18006e547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e54c  nop
0x18006e54d  jmp     loc_18006E971
0x18006e552  mov     [rbp+260h+var_290], rsi
0x18006e556  mov     rcx, [rsp+360h+var_318]
0x18006e55b  mov     rax, [rcx]
0x18006e55e  lea     rdx, [rbp+260h+var_290]
0x18006e562  mov     rax, [rax+18h]
0x18006e566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e56b  mov     ebx, eax
0x18006e56d  test    eax, eax
0x18006e56f  jns     short loc_18006E5B9
0x18006e571  mov     rcx, [rbp+268h]; this
0x18006e578  mov     r9d, eax; char *
0x18006e57b  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006e582  mov     edx, 0E2h; void *
0x18006e587  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e58c  nop
0x18006e58d  lea     rcx, [rsp+360h+var_318]
0x18006e592  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e597  nop
0x18006e598  mov     rcx, [rsp+360h+var_328]
0x18006e59d  test    rcx, rcx
0x18006e5a0  jz      short loc_18006E5B4
0x18006e5a2  mov     [rsp+360h+var_328], rsi
0x18006e5a7  mov     rax, [rcx]
0x18006e5aa  mov     rax, [rax+10h]
0x18006e5ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e5b3  nop
0x18006e5b4  jmp     loc_18006E971
0x18006e5b9  mov     [rsp+360h+var_300], esi
0x18006e5bd  mov     rcx, [rsp+360h+var_328]
0x18006e5c2  mov     rax, [rcx]
0x18006e5c5  lea     rdx, [rsp+360h+var_300]
0x18006e5ca  mov     rax, [rax+38h]
0x18006e5ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e5d3  mov     ebx, eax
0x18006e5d5  test    eax, eax
0x18006e5d7  jns     short loc_18006E621
0x18006e5d9  mov     rcx, [rbp+268h]; this
0x18006e5e0  mov     r9d, eax; char *
0x18006e5e3  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006e5ea  mov     edx, 0E5h; void *
0x18006e5ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e5f4  nop
0x18006e5f5  lea     rcx, [rsp+360h+var_318]
0x18006e5fa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e5ff  nop
0x18006e600  mov     rcx, [rsp+360h+var_328]
0x18006e605  test    rcx, rcx
0x18006e608  jz      short loc_18006E61C
0x18006e60a  mov     [rsp+360h+var_328], rsi
0x18006e60f  mov     rax, [rcx]
0x18006e612  mov     rax, [rax+10h]
0x18006e616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e61b  nop
0x18006e61c  jmp     loc_18006E971
0x18006e621  lea     r8, [rsp+360h+pvarg+8]
0x18006e626  mov     edx, [rsp+360h+var_300]
0x18006e62a  mov     rcx, [rbp+260h+var_290]
0x18006e62e  call    cs:__imp_?ByteArrayToSafeArray@@YAJPEAEKPEAPEAUtagSAFEARRAY@@@Z; ByteArrayToSafeArray(uchar *,ulong,tagSAFEARRAY * *)
0x18006e635  nop     dword ptr [rax+rax+00h]
0x18006e63a  mov     ebx, eax
0x18006e63c  test    eax, eax
0x18006e63e  jns     short loc_18006E688
0x18006e640  mov     rcx, [rbp+268h]; this
0x18006e647  mov     r9d, eax; char *
0x18006e64a  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006e651  mov     edx, 0E7h; void *
0x18006e656  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e65b  nop
0x18006e65c  lea     rcx, [rsp+360h+var_318]
0x18006e661  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e666  nop
0x18006e667  mov     rcx, [rsp+360h+var_328]
0x18006e66c  test    rcx, rcx
0x18006e66f  jz      short loc_18006E683
0x18006e671  mov     [rsp+360h+var_328], rsi
0x18006e676  mov     rax, [rcx]
0x18006e679  mov     rax, [rax+10h]
0x18006e67d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e682  nop
0x18006e683  jmp     loc_18006E971
0x18006e688  mov     esi, 6
0x18006e68d  mov     eax, 2011h
0x18006e692  mov     word ptr [rsp+360h+pvarg], ax
0x18006e697  lea     rcx, [rsp+360h+var_318]
0x18006e69c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e6a1  nop
0x18006e6a2  mov     rcx, [rsp+360h+var_328]
0x18006e6a7  xor     edi, edi
0x18006e6a9  test    rcx, rcx
0x18006e6ac  jz      short loc_18006E6C0
0x18006e6ae  mov     [rsp+360h+var_328], rdi
0x18006e6b3  mov     rax, [rcx]
0x18006e6b6  mov     rax, [rax+10h]
0x18006e6ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e6bf  nop
0x18006e6c0  mov     [rsp+360h+var_320], rdi
0x18006e6c5  lea     rcx, [rsp+360h+var_320]
0x18006e6ca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e6cf  lea     rax, [rsp+360h+var_320]
  ... truncated ...
```
