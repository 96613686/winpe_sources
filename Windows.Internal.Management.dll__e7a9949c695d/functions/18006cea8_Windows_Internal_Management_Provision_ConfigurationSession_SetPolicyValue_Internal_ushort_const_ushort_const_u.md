# Windows::Internal::Management::Provision::ConfigurationSession::SetPolicyValue_Internal(ushort const *,ushort const *,ushort const *,ushort const *,Windows::Internal::Management::Provision::IConfigurationData *)

- ea: `0x18006cea8`
- end: `0x18006d5a9`
- name: `?SetPolicyValue_Internal@ConfigurationSession@Provision@Management@Internal@Windows@@CAJPEBG000PEAUIConfigurationData@2345@@Z`
- size: `1793`
- prototype: `__int64 __usercall@<rax>(OLECHAR *psz@<rcx>, OLECHAR *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, struct Windows::Internal::Management::Provision::IConfigurationData *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006b36c`

## callees

- `0x180004d50`
- `0x18000992c`
- `0x18000a2a4`
- `0x18000a8e8`
- `0x18003ed58`
- `0x18006cea8`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006d000`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006d000`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006d331`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006d331`
- `OLEAUT32!__imp_SysAllocString` at `0x18006d009`
- `OLEAUT32!__imp_SysAllocString` at `0x18006d3a0`
- `OLEAUT32!__imp_SysAllocString` at `0x18006d42c`
- `OLEAUT32!__imp_SysAllocString` at `0x18006d009`
- `OLEAUT32!__imp_SysAllocString` at `0x18006d3a0`
- `OLEAUT32!__imp_SysAllocString` at `0x18006d42c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18006d395`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18006d395`
- `OLEAUT32!__imp_VariantInit` at `0x18006cf8d`
- `OLEAUT32!__imp_VariantInit` at `0x18006d36c`
- `OLEAUT32!__imp_VariantInit` at `0x18006d419`
- `OLEAUT32!__imp_VariantInit` at `0x18006cf8d`
- `OLEAUT32!__imp_VariantInit` at `0x18006d36c`
- `OLEAUT32!__imp_VariantInit` at `0x18006d419`
- `OLEAUT32!__imp_VariantClear` at `0x18006d401`
- `OLEAUT32!__imp_VariantClear` at `0x18006d48a`
- `OLEAUT32!__imp_VariantClear` at `0x18006d499`
- `OLEAUT32!__imp_VariantClear` at `0x18006d565`
- `OLEAUT32!__imp_VariantClear` at `0x18006d57e`
- `OLEAUT32!__imp_VariantClear` at `0x18006d401`
- `OLEAUT32!__imp_VariantClear` at `0x18006d48a`
- `OLEAUT32!__imp_VariantClear` at `0x18006d499`
- `OLEAUT32!__imp_VariantClear` at `0x18006d565`
- `OLEAUT32!__imp_VariantClear` at `0x18006d57e`
- `DMOleAutUtils!ByteArrayToSafeArray` at `0x18006d278`
- `DMOleAutUtils!ByteArrayToSafeArray` at `0x18006d278`

## string_xrefs

- `0x18006d454`: `OMADM::TargetedUserSID`
- `0x18006cf46`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006d033`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006d107`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006d15e`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006d1c5`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006d22d`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006d28e`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006d347`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006d3eb`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006d474`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006d4e3`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006cf26`: `./%s/Vendor/MSFT/Policy/Config/%s/%s`

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
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64); // rcx
  int v24; // eax
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64); // rcx
  int v26; // eax
  __int64 (__fastcall ***v27)(_QWORD, GUID *, __int64); // rcx
  int v28; // eax
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64); // rcx
  int v30; // eax
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64); // rcx
  __int64 (__fastcall ***v32)(_QWORD, GUID *, __int64); // rcx
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
  __int64 (__fastcall ***v44)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-C8h] BYREF
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
      v22 = (*(__int64 (__fastcall **)(struct Windows::Internal::Management::Provision::IConfigurationData *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)a5 + 64LL))(
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
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v23)[2])(v23);
        }
        goto LABEL_78;
      }
      v46 = 0;
      v24 = Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(
              &v44,
              (__int64)&v46);
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
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v25)[2])(v25);
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
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v27)[2])(v27);
        }
        goto LABEL_78;
      }
      v50 = 0;
      v28 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), unsigned int *))(*v44)[7])(
              v44,
              &v50);
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
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v29)[2])(v29);
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
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v31)[2])(v31);
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
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v32)[2])(v32);
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
0x18006cea8  push    rbp
0x18006ceaa  push    rbx
0x18006ceab  push    rsi
0x18006ceac  push    rdi
0x18006cead  push    r12
0x18006ceaf  push    r13
0x18006ceb1  push    r14
0x18006ceb3  push    r15
0x18006ceb5  lea     rbp, [rsp-228h]
0x18006cebd  sub     rsp, 328h
0x18006cec4  mov     rax, cs:__security_cookie
0x18006cecb  xor     rax, rsp
0x18006cece  mov     [rbp+260h+var_50], rax
0x18006ced5  mov     r10, r9
0x18006ced8  mov     r13, rdx
0x18006cedb  mov     r15, rcx
0x18006cede  mov     rbx, [rbp+260h+arg_20]
0x18006cee5  or      r14, 0FFFFFFFFFFFFFFFFh
0x18006cee9  xor     esi, esi
0x18006ceeb  test    rdx, rdx
0x18006ceee  jz      short loc_18006CF04
0x18006cef0  mov     rax, r14
0x18006cef3  inc     rax
0x18006cef6  cmp     [rdx+rax*2], si
0x18006cefa  jnz     short loc_18006CEF3
0x18006cefc  test    rax, rax
0x18006ceff  mov     r12b, 1
0x18006cf02  jnz     short loc_18006CF07
0x18006cf04  mov     r12b, sil
0x18006cf07  lea     rax, aDevice; "Device"
0x18006cf0e  lea     r9, aUser_0; "User"
0x18006cf15  test    r12b, r12b
0x18006cf18  cmovz   r9, rax
0x18006cf1c  mov     [rsp+360h+var_338], r10
0x18006cf21  mov     [rsp+360h+ppv], r8; int
0x18006cf26  lea     r8, aSVendorMsftPol; "./%s/Vendor/MSFT/Policy/Config/%s/%s"
0x18006cf2d  mov     edx, 104h; unsigned __int64
0x18006cf32  lea     rcx, [rbp+260h+var_260]; unsigned __int16 *
0x18006cf36  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006cf3b  mov     edi, eax
0x18006cf3d  test    eax, eax
0x18006cf3f  jns     short loc_18006CF63
0x18006cf41  mov     edx, 0A6h; void *
0x18006cf46  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006cf4d  mov     r9d, edi; char *
0x18006cf50  mov     rcx, [rbp+268h]; this
0x18006cf57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cf5c  mov     eax, edi
0x18006cf5e  jmp     loc_18006D586
0x18006cf63  mov     [rsp+360h+var_308], esi
0x18006cf67  mov     rax, [rbx]
0x18006cf6a  lea     rdx, [rsp+360h+var_308]
0x18006cf6f  mov     rcx, rbx
0x18006cf72  mov     rax, [rax+30h]
0x18006cf76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cf7b  mov     edi, eax
0x18006cf7d  test    eax, eax
0x18006cf7f  jns     short loc_18006CF88
0x18006cf81  mov     edx, 0AAh
0x18006cf86  jmp     short loc_18006CF46
0x18006cf88  lea     rcx, [rsp+360h+pvarg]; pvarg
0x18006cf8d  call    cs:__imp_VariantInit
0x18006cf93  nop
0x18006cf94  mov     ecx, [rsp+360h+var_308]
0x18006cf98  mov     edi, 8
0x18006cf9d  sub     ecx, 1
0x18006cfa0  jz      loc_18006D0DE
0x18006cfa6  sub     ecx, 1
0x18006cfa9  jz      loc_18006D0A4
0x18006cfaf  sub     ecx, 1
0x18006cfb2  jz      loc_18006D066
0x18006cfb8  sub     ecx, 1
0x18006cfbb  jz      short loc_18006D011
0x18006cfbd  cmp     ecx, 1
0x18006cfc0  jz      short loc_18006CFCC
0x18006cfc2  mov     ebx, 80070057h
0x18006cfc7  jmp     loc_18006D579
0x18006cfcc  mov     [rbp+260h+string], rsi
0x18006cfd0  mov     rax, [rbx]
0x18006cfd3  lea     rdx, [rbp+260h+string]
0x18006cfd7  mov     rcx, rbx
0x18006cfda  mov     rax, [rax+58h]
0x18006cfde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cfe3  mov     ebx, eax
0x18006cfe5  test    eax, eax
0x18006cfe7  jns     short loc_18006CFF0
0x18006cfe9  mov     edx, 0D2h
0x18006cfee  jmp     short loc_18006D033
0x18006cff0  mov     esi, 1
0x18006cff5  mov     word ptr [rsp+360h+pvarg], di
0x18006cffa  xor     edx, edx; length
0x18006cffc  mov     rcx, [rbp+260h+string]; string
0x18006d000  call    cs:__imp_WindowsGetStringRawBuffer
0x18006d006  mov     rcx, rax; psz
0x18006d009  call    cs:__imp_SysAllocString
0x18006d00f  jmp     short loc_18006D05F
0x18006d011  mov     [rbp+260h+var_298], rsi
0x18006d015  mov     rax, [rbx]
0x18006d018  lea     rdx, [rbp+260h+var_298]
0x18006d01c  mov     rcx, rbx
0x18006d01f  mov     rax, [rax+50h]
0x18006d023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d028  mov     ebx, eax
0x18006d02a  test    eax, eax
0x18006d02c  jns     short loc_18006D04E
0x18006d02e  mov     edx, 0BEh; void *
0x18006d033  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006d03a  mov     r9d, eax; char *
0x18006d03d  mov     rcx, [rbp+268h]; this
0x18006d044  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d049  jmp     loc_18006D579
0x18006d04e  mov     esi, 0Bh
0x18006d053  lea     eax, [rsi+9]
0x18006d056  mov     word ptr [rsp+360h+pvarg], ax
0x18006d05b  mov     rax, [rbp+260h+var_298]
0x18006d05f  mov     qword ptr [rsp+360h+pvarg+8], rax
0x18006d064  jmp     short loc_18006D09D
0x18006d066  mov     [rsp+360h+var_304], esi
0x18006d06a  mov     rax, [rbx]
0x18006d06d  lea     rdx, [rsp+360h+var_304]
0x18006d072  mov     rcx, rbx
0x18006d075  mov     rax, [rax+48h]
0x18006d079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d07e  mov     ebx, eax
0x18006d080  test    eax, eax
0x18006d082  jns     short loc_18006D08B
0x18006d084  mov     edx, 0B4h
0x18006d089  jmp     short loc_18006D033
0x18006d08b  mov     eax, 3
0x18006d090  mov     word ptr [rsp+360h+pvarg], ax
0x18006d095  mov     eax, [rsp+360h+var_304]
0x18006d099  mov     dword ptr [rsp+360h+pvarg+8], eax
0x18006d09d  xor     edi, edi
0x18006d09f  jmp     loc_18006D304
0x18006d0a4  mov     [rsp+360h+var_330], sil
0x18006d0a9  mov     rax, [rbx]
0x18006d0ac  lea     rdx, [rsp+360h+var_330]
0x18006d0b1  mov     rcx, rbx
0x18006d0b4  mov     rax, [rax+38h]
0x18006d0b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d0bd  mov     ebx, eax
0x18006d0bf  test    eax, eax
0x18006d0c1  jns     short loc_18006D0CD
0x18006d0c3  mov     edx, 0C8h
0x18006d0c8  jmp     loc_18006D033
0x18006d0cd  mov     eax, 3
0x18006d0d2  mov     word ptr [rsp+360h+pvarg], ax
0x18006d0d7  movzx   eax, [rsp+360h+var_330]
0x18006d0dc  jmp     short loc_18006D099
0x18006d0de  mov     [rsp+360h+var_328], rsi
0x18006d0e3  mov     rax, [rbx]
0x18006d0e6  lea     rdx, [rsp+360h+var_328]
0x18006d0eb  mov     rcx, rbx
0x18006d0ee  mov     rax, [rax+40h]
0x18006d0f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d0f7  mov     ebx, eax
0x18006d0f9  test    eax, eax
0x18006d0fb  jns     short loc_18006D13A
0x18006d0fd  mov     rcx, [rbp+268h]; this
0x18006d104  mov     r9d, eax; char *
0x18006d107  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006d10e  mov     edx, 0DCh; void *
0x18006d113  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d118  nop
0x18006d119  mov     rcx, [rsp+360h+var_328]
0x18006d11e  test    rcx, rcx
0x18006d121  jz      short loc_18006D135
0x18006d123  mov     [rsp+360h+var_328], rsi
0x18006d128  mov     rax, [rcx]
0x18006d12b  mov     rax, [rax+10h]
0x18006d12f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d134  nop
0x18006d135  jmp     loc_18006D579
0x18006d13a  mov     [rsp+360h+var_318], rsi
0x18006d13f  lea     rdx, [rsp+360h+var_318]
0x18006d144  lea     rcx, [rsp+360h+var_328]
0x18006d149  call    ??$As@UIBufferByteAccess@Streams@Storage@Windows@@@?$ComPtr@UIBuffer@Streams@Storage@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIBufferByteAccess@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBufferByteAccess>>)
0x18006d14e  mov     ebx, eax
0x18006d150  test    eax, eax
0x18006d152  jns     short loc_18006D19C
0x18006d154  mov     rcx, [rbp+268h]; this
0x18006d15b  mov     r9d, eax; char *
0x18006d15e  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006d165  mov     edx, 0DFh; void *
0x18006d16a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d16f  nop
0x18006d170  lea     rcx, [rsp+360h+var_318]
0x18006d175  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006d17a  nop
0x18006d17b  mov     rcx, [rsp+360h+var_328]
0x18006d180  test    rcx, rcx
0x18006d183  jz      short loc_18006D197
0x18006d185  mov     [rsp+360h+var_328], rsi
0x18006d18a  mov     rax, [rcx]
0x18006d18d  mov     rax, [rax+10h]
0x18006d191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d196  nop
0x18006d197  jmp     loc_18006D579
0x18006d19c  mov     [rbp+260h+var_290], rsi
0x18006d1a0  mov     rcx, [rsp+360h+var_318]
0x18006d1a5  mov     rax, [rcx]
0x18006d1a8  lea     rdx, [rbp+260h+var_290]
0x18006d1ac  mov     rax, [rax+18h]
0x18006d1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d1b5  mov     ebx, eax
0x18006d1b7  test    eax, eax
0x18006d1b9  jns     short loc_18006D203
0x18006d1bb  mov     rcx, [rbp+268h]; this
0x18006d1c2  mov     r9d, eax; char *
0x18006d1c5  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006d1cc  mov     edx, 0E2h; void *
0x18006d1d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d1d6  nop
0x18006d1d7  lea     rcx, [rsp+360h+var_318]
0x18006d1dc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006d1e1  nop
0x18006d1e2  mov     rcx, [rsp+360h+var_328]
0x18006d1e7  test    rcx, rcx
0x18006d1ea  jz      short loc_18006D1FE
0x18006d1ec  mov     [rsp+360h+var_328], rsi
0x18006d1f1  mov     rax, [rcx]
0x18006d1f4  mov     rax, [rax+10h]
0x18006d1f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d1fd  nop
0x18006d1fe  jmp     loc_18006D579
0x18006d203  mov     [rsp+360h+var_300], esi
0x18006d207  mov     rcx, [rsp+360h+var_328]
0x18006d20c  mov     rax, [rcx]
0x18006d20f  lea     rdx, [rsp+360h+var_300]
0x18006d214  mov     rax, [rax+38h]
0x18006d218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d21d  mov     ebx, eax
0x18006d21f  test    eax, eax
0x18006d221  jns     short loc_18006D26B
0x18006d223  mov     rcx, [rbp+268h]; this
0x18006d22a  mov     r9d, eax; char *
0x18006d22d  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006d234  mov     edx, 0E5h; void *
0x18006d239  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d23e  nop
0x18006d23f  lea     rcx, [rsp+360h+var_318]
0x18006d244  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006d249  nop
0x18006d24a  mov     rcx, [rsp+360h+var_328]
0x18006d24f  test    rcx, rcx
0x18006d252  jz      short loc_18006D266
0x18006d254  mov     [rsp+360h+var_328], rsi
0x18006d259  mov     rax, [rcx]
0x18006d25c  mov     rax, [rax+10h]
0x18006d260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d265  nop
0x18006d266  jmp     loc_18006D579
0x18006d26b  lea     r8, [rsp+360h+pvarg+8]
0x18006d270  mov     edx, [rsp+360h+var_300]
0x18006d274  mov     rcx, [rbp+260h+var_290]
0x18006d278  call    cs:__imp_?ByteArrayToSafeArray@@YAJPEAEKPEAPEAUtagSAFEARRAY@@@Z; ByteArrayToSafeArray(uchar *,ulong,tagSAFEARRAY * *)
0x18006d27e  mov     ebx, eax
0x18006d280  test    eax, eax
0x18006d282  jns     short loc_18006D2CC
0x18006d284  mov     rcx, [rbp+268h]; this
0x18006d28b  mov     r9d, eax; char *
0x18006d28e  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006d295  mov     edx, 0E7h; void *
0x18006d29a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d29f  nop
0x18006d2a0  lea     rcx, [rsp+360h+var_318]
0x18006d2a5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006d2aa  nop
0x18006d2ab  mov     rcx, [rsp+360h+var_328]
0x18006d2b0  test    rcx, rcx
0x18006d2b3  jz      short loc_18006D2C7
0x18006d2b5  mov     [rsp+360h+var_328], rsi
0x18006d2ba  mov     rax, [rcx]
0x18006d2bd  mov     rax, [rax+10h]
0x18006d2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d2c6  nop
0x18006d2c7  jmp     loc_18006D579
0x18006d2cc  mov     esi, 6
0x18006d2d1  mov     eax, 2011h
0x18006d2d6  mov     word ptr [rsp+360h+pvarg], ax
0x18006d2db  lea     rcx, [rsp+360h+var_318]
0x18006d2e0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006d2e5  nop
0x18006d2e6  mov     rcx, [rsp+360h+var_328]
0x18006d2eb  xor     edi, edi
0x18006d2ed  test    rcx, rcx
0x18006d2f0  jz      short loc_18006D304
0x18006d2f2  mov     [rsp+360h+var_328], rdi
0x18006d2f7  mov     rax, [rcx]
0x18006d2fa  mov     rax, [rax+10h]
0x18006d2fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d303  nop
0x18006d304  mov     [rsp+360h+var_320], rdi
0x18006d309  lea     rcx, [rsp+360h+var_320]
0x18006d30e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006d313  lea     rax, [rsp+360h+var_320]
0x18006d318  mov     [rsp+360h+ppv], rax; int
0x18006d31d  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x18006d324  xor     edx, edx; pUnkOuter
0x18006d326  lea     r8d, [rdx+1]; dwClsContext
  ... truncated ...
```
