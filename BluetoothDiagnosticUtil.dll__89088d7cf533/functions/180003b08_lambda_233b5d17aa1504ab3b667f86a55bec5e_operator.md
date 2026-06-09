# _lambda_233b5d17aa1504ab3b667f86a55bec5e_::operator()

- ea: `0x180003b08`
- end: `0x180004208`
- name: `_lambda_233b5d17aa1504ab3b667f86a55bec5e_::operator()`
- size: `1792`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005e60`

## callees

- `0x180001ca4`
- `0x180003b08`
- `0x180006280`
- `0x180006c6c`
- `0x180008130`
- `0x180008580`
- `0x180009c90`
- `0x18000b010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180003f67`
- `msvcrt!wcscpy_s` at `0x180003f67`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180003d97`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180003d97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003b90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003cb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003d50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003e6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003b90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003cb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003d50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003e6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003c3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004059`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003c3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004059`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003f37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003f37`

## pseudocode

```c
// Hidden C++ exception states: #wind=33
__int64 __fastcall lambda_233b5d17aa1504ab3b667f86a55bec5e_::operator()(wchar_t ***a1, __int64 a2, __int64 a3)
{
  int v4; // eax
  unsigned int v5; // r8d
  _QWORD *v6; // rbx
  __int64 v7; // rdi
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  int v11; // eax
  unsigned int v12; // r8d
  wil::details::in1diag3 *v13; // rcx
  int v14; // eax
  unsigned int v15; // r8d
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  int v18; // eax
  unsigned int v19; // r8d
  int v20; // eax
  unsigned int v21; // r8d
  _QWORD *v22; // rbx
  __int64 (__fastcall **v23)(_QWORD *, GUID *, _QWORD *); // rdi
  HRESULT v24; // eax
  int v25; // edx
  unsigned int v26; // r8d
  int v27; // eax
  unsigned int v28; // r8d
  wil::details::in1diag3 *v29; // rcx
  int v30; // eax
  unsigned int v31; // r8d
  HRESULT v32; // eax
  int v33; // edx
  unsigned int v34; // r8d
  int ActivationFactory; // eax
  unsigned int v36; // r8d
  wil::details::in1diag3 *v37; // rcx
  int v38; // eax
  unsigned int v39; // r8d
  int v40; // eax
  unsigned int v41; // r8d
  int v42; // eax
  unsigned int v43; // r8d
  _QWORD *v44; // rbx
  __int64 v45; // rdi
  HRESULT v46; // eax
  int v47; // edx
  unsigned int v48; // r8d
  int v49; // eax
  unsigned int v50; // r8d
  wil::details::in1diag3 *v51; // rcx
  int v52; // eax
  unsigned int v53; // r8d
  int v54; // eax
  unsigned int v55; // r8d
  const wchar_t *StringRawBuffer; // rbx
  __int64 v57; // rcx
  __int64 (__fastcall ***v58)(_QWORD, GUID *, _QWORD *); // rcx
  _QWORD *v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  _QWORD *v64; // rcx
  unsigned int v65; // r8d
  const char *v66; // r9
  __int64 v67; // rcx
  __int64 (__fastcall ***v68)(_QWORD, GUID *, _QWORD *); // rcx
  _QWORD *v69; // rcx
  __int64 result; // rax
  int v71; // [rsp+20h] [rbp-B8h]
  char v72[4]; // [rsp+30h] [rbp-A8h] BYREF
  UINT32 length; // [rsp+34h] [rbp-A4h] BYREF
  __int64 v74; // [rsp+38h] [rbp-A0h] BYREF
  HSTRING v75; // [rsp+40h] [rbp-98h] BYREF
  _QWORD *v76; // [rsp+48h] [rbp-90h] BYREF
  __int64 v77; // [rsp+50h] [rbp-88h] BYREF
  __int64 (__fastcall ***v78)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-80h] BYREF
  _QWORD *v79; // [rsp+60h] [rbp-78h] BYREF
  __int64 v80; // [rsp+68h] [rbp-70h] BYREF
  int v81[2]; // [rsp+70h] [rbp-68h] BYREF
  __int64 v82; // [rsp+78h] [rbp-60h] BYREF
  __int64 v83; // [rsp+80h] [rbp-58h] BYREF
  __int64 (__fastcall ***v84)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp-50h] BYREF
  _QWORD *v85; // [rsp+90h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-40h] BYREF
  HSTRING string; // [rsp+B0h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  try
  {
    v85 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)a3 + 88LL))(a3, &v85);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x169, v5, (const char *)(unsigned int)v4, v71);
    v84 = 0;
    v6 = v85;
    v7 = *v85;
    string = 0;
    v8 = WindowsCreateStringReference(L"System.Devices.DeviceInstanceId", 0x1Fu, &hstringHeader, &string);
    if ( v8 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
    }
    else
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, _QWORD))(v7 + 48))(v6, string, &v84);
      v13 = retaddr;
      if ( v11 >= 0 )
      {
        if ( !v84 )
          wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x16C, (unsigned int)retaddr, (const char *)0x10D2, v71);
        v83 = 0;
        v14 = (**v84)(v84, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v83);
        if ( v14 < 0 )
          wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x16E, v15, (const char *)(unsigned int)v14, v71);
        v75 = 0;
        v16 = v83;
        v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v83 + 152LL);
        WindowsDeleteString(0);
        v75 = 0;
        v18 = v17(v16, &v75);
        if ( v18 < 0 )
          wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x170, v19, (const char *)(unsigned int)v18, v71);
        v76 = 0;
        v20 = Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::Make(&v76);
        if ( v20 < 0 )
          wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x174, v21, (const char *)(unsigned int)v20, v71);
        v22 = v76;
        v23 = (__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD *))*v76;
        string = 0;
        v24 = WindowsCreateStringReference(L"System.Devices.Present", 0x16u, &hstringHeader, &string);
        if ( v24 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v24, v25, v26);
        }
        else
        {
          v27 = ((__int64 (__fastcall **)(_QWORD *, GUID *, HSTRING))v23)[11](v22, 0, string);
          v29 = retaddr;
          if ( v27 >= 0 )
          {
            v82 = 0;
            v30 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v76)(
                    v76,
                    &GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e,
                    &v82);
            if ( v30 < 0 )
              wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x177, v31, (const char *)(unsigned int)v30, v71);
            *(_QWORD *)v81 = 0;
            v74 = 0;
            string = 0;
            v32 = WindowsCreateStringReference(
                    L"Windows.Devices.Enumeration.DeviceInformation",
                    0x2Du,
                    &hstringHeader,
                    &string);
            if ( v32 < 0 )
            {
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v32, v33, v34);
            }
            else
            {
              ActivationFactory = RoGetActivationFactory(string, &GUID_493b4f34_a84f_45fd_9167_15d1cb1bd1f9, &v74);
              v37 = retaddr;
              if ( ActivationFactory >= 0 )
              {
                v38 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64, __int64))(*(_QWORD *)v74 + 56LL))(
                        v74,
                        v75,
                        v82,
                        3);
                if ( v38 < 0 )
                  wil::details::in1diag3::_Throw_Hr(
                    retaddr,
                    (void *)0x183,
                    v39,
                    (const char *)(unsigned int)v38,
                    (int)v81);
                v80 = 0;
                v40 = BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *>,Windows::Devices::Enumeration::IDeviceInformation>(
                        *(_QWORD *)v81,
                        &v80);
                if ( v40 < 0 )
                  wil::details::in1diag3::_Throw_Hr(
                    retaddr,
                    (void *)0x188,
                    v41,
                    (const char *)(unsigned int)v40,
                    (int)v81);
                v79 = 0;
                v42 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v80 + 88LL))(v80, &v79);
                if ( v42 < 0 )
                  wil::details::in1diag3::_Throw_Hr(
                    retaddr,
                    (void *)0x18C,
                    v43,
                    (const char *)(unsigned int)v42,
                    (int)v81);
                v78 = 0;
                v44 = v79;
                v45 = *v79;
                string = 0;
                v46 = WindowsCreateStringReference(L"System.Devices.Present", 0x16u, &hstringHeader, &string);
                if ( v46 < 0 )
                {
                  Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v46, v47, v48);
                }
                else
                {
                  v49 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, _QWORD))(v45 + 48))(v44, string, &v78);
                  v51 = retaddr;
                  if ( v49 >= 0 )
                  {
                    if ( !v78 )
                      wil::details::in1diag3::_Throw_Hr(
                        retaddr,
                        (void *)0x18F,
                        (unsigned int)retaddr,
                        (const char *)0x10D2,
                        (int)v81);
                    v77 = 0;
                    v52 = (**v78)(v78, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v77);
                    if ( v52 < 0 )
                      wil::details::in1diag3::_Throw_Hr(
                        retaddr,
                        (void *)0x191,
                        v53,
                        (const char *)(unsigned int)v52,
                        (int)v81);
                    v72[0] = 0;
                    v54 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v77 + 144LL))(v77, v72);
                    if ( v54 < 0 )
                      wil::details::in1diag3::_Throw_Hr(
                        retaddr,
                        (void *)0x193,
                        v55,
                        (const char *)(unsigned int)v54,
                        (int)v81);
                    if ( v72[0] )
                    {
                      length = 0;
                      StringRawBuffer = WindowsGetStringRawBuffer(v75, &length);
                      std::vector<unsigned short>::resize(*a1, length + 1);
                      wcscpy_s(**a1, (*a1)[1] - **a1, StringRawBuffer);
                    }
                    v57 = v77;
                    if ( v77 )
                    {
                      v77 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
                    }
                    v58 = v78;
                    if ( v78 )
                    {
                      v78 = 0;
                      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v58)[2])(v58);
                    }
                    v59 = v79;
                    if ( v79 )
                    {
                      v79 = 0;
                      (*(void (__fastcall **)(_QWORD *))(*v59 + 16LL))(v59);
                    }
                    v60 = v80;
                    if ( v80 )
                    {
                      v80 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
                    }
                    v61 = v74;
                    if ( v74 )
                    {
                      v74 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
                    }
                    v62 = *(_QWORD *)v81;
                    if ( *(_QWORD *)v81 )
                    {
                      *(_QWORD *)v81 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
                    }
                    v63 = v82;
                    if ( v82 )
                    {
                      v82 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
                    }
                    v64 = v76;
                    if ( v76 )
                    {
                      v76 = 0;
                      (*(void (__fastcall **)(_QWORD *))(*v64 + 16LL))(v64);
                    }
                    WindowsDeleteString(v75);
                    v75 = 0;
                    v67 = v83;
                    if ( v83 )
                    {
                      v83 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
                    }
                    v68 = v84;
                    if ( v84 )
                    {
                      v84 = 0;
                      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v68)[2])(v68);
                    }
                    v69 = v85;
                    if ( v85 )
                    {
                      v85 = 0;
                      (*(void (__fastcall **)(_QWORD *))(*v69 + 16LL))(v69);
                    }
                    return 0;
                  }
                }
                wil::details::in1diag3::_Throw_Hr(v51, (void *)0x18E, v50, (const char *)(unsigned int)v49, (int)v81);
              }
            }
            wil::details::in1diag3::_Throw_Hr(
              v37,
              (void *)0x17D,
              v36,
              (const char *)(unsigned int)ActivationFactory,
              v71);
          }
        }
        wil::details::in1diag3::_Throw_Hr(v29, (void *)0x175, v28, (const char *)(unsigned int)v27, v71);
      }
    }
    wil::details::in1diag3::_Throw_Hr(v13, (void *)0x16B, v12, (const char *)(unsigned int)v11, v71);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x19D, v65, v66);
  }
  return result;
}

```

## disassembly

```asm
0x180003b08  mov     r11, rsp
0x180003b0b  mov     [r11+10h], rbx
0x180003b0f  push    rsi
0x180003b10  push    rdi
0x180003b11  push    r14
0x180003b13  sub     rsp, 0C0h
0x180003b1a  mov     rax, cs:__security_cookie
0x180003b21  xor     rax, rsp
0x180003b24  mov     [rsp+0D8h+var_20], rax
0x180003b2c  mov     rsi, rcx
0x180003b2f  xor     r14d, r14d
0x180003b32  mov     [r11-48h], r14
0x180003b36  mov     rax, [r8]
0x180003b39  lea     rdx, [r11-48h]
0x180003b3d  mov     rcx, r8
0x180003b40  mov     rax, [rax+58h]
0x180003b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b49  mov     rcx, [rsp+0D8h]; this
0x180003b51  test    eax, eax
0x180003b53  js      loc_1800040FD
0x180003b59  mov     [rsp+0D8h+var_50], r14
0x180003b61  mov     rbx, [rsp+0D8h+var_48]
0x180003b69  mov     rdi, [rbx]
0x180003b6c  mov     [rsp+0D8h+string], r14
0x180003b74  lea     r9, [rsp+0D8h+string]; string
0x180003b7c  lea     r8, [rsp+0D8h+hstringHeader]; hstringHeader
0x180003b84  mov     edx, 1Fh; length
0x180003b89  lea     rcx, sourceString; "System.Devices.DeviceInstanceId"
0x180003b90  call    cs:__imp_WindowsCreateStringReference
0x180003b97  nop     dword ptr [rax+rax+00h]
0x180003b9c  test    eax, eax
0x180003b9e  js      loc_18000410B
0x180003ba4  lea     r8, [rsp+0D8h+var_50]
0x180003bac  mov     rdx, [rsp+0D8h+string]
0x180003bb4  mov     rcx, rbx
0x180003bb7  mov     rax, [rdi+30h]
0x180003bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bc0  mov     rcx, [rsp+0D8h]
0x180003bc8  test    eax, eax
0x180003bca  js      loc_180004113
0x180003bd0  mov     rcx, [rsp+0D8h+var_50]
0x180003bd8  test    rcx, rcx
0x180003bdb  setz    al
0x180003bde  mov     r8, [rsp+0D8h]; unsigned int
0x180003be6  test    al, al
0x180003be8  jnz     loc_180004121
0x180003bee  mov     [rsp+0D8h+var_58], r14
0x180003bf6  mov     rax, [rcx]
0x180003bf9  lea     r8, [rsp+0D8h+var_58]
0x180003c01  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180003c08  mov     rax, [rax]
0x180003c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c10  nop
0x180003c11  mov     rcx, [rsp+0D8h]; this
0x180003c19  test    eax, eax
0x180003c1b  js      loc_180004135
0x180003c21  mov     [rsp+0D8h+var_98], r14
0x180003c26  mov     rdi, [rsp+0D8h+var_58]
0x180003c2e  mov     rax, [rdi]
0x180003c31  mov     rbx, [rax+98h]
0x180003c38  xor     ecx, ecx; string
0x180003c3a  call    cs:__imp_WindowsDeleteString
0x180003c41  nop     dword ptr [rax+rax+00h]
0x180003c46  mov     [rsp+0D8h+var_98], r14
0x180003c4b  lea     rdx, [rsp+0D8h+var_98]
0x180003c50  mov     rcx, rdi
0x180003c53  mov     rax, rbx
0x180003c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c5b  mov     rcx, [rsp+0D8h]; this
0x180003c63  test    eax, eax
0x180003c65  js      loc_180004143
0x180003c6b  mov     [rsp+0D8h+var_90], r14
0x180003c70  lea     rcx, [rsp+0D8h+var_90]
0x180003c75  call    ?Make@?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@SAJPEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::Make(Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x180003c7a  mov     rcx, [rsp+0D8h]; this
0x180003c82  test    eax, eax
0x180003c84  js      loc_180004151
0x180003c8a  mov     rbx, [rsp+0D8h+var_90]
0x180003c8f  mov     rdi, [rbx]
0x180003c92  mov     [rsp+0D8h+string], r14
0x180003c9a  lea     r9, [rsp+0D8h+string]; string
0x180003ca2  lea     r8, [rsp+0D8h+hstringHeader]; hstringHeader
0x180003caa  mov     edx, 16h; length
0x180003caf  lea     rcx, aSystemDevicesP; "System.Devices.Present"
0x180003cb6  call    cs:__imp_WindowsCreateStringReference
0x180003cbd  nop     dword ptr [rax+rax+00h]
0x180003cc2  test    eax, eax
0x180003cc4  js      loc_18000415E
0x180003cca  mov     r8, [rsp+0D8h+string]
0x180003cd2  xor     edx, edx
0x180003cd4  mov     rcx, rbx
0x180003cd7  mov     rax, [rdi+58h]
0x180003cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ce0  mov     rcx, [rsp+0D8h]
0x180003ce8  test    eax, eax
0x180003cea  js      loc_180004166
0x180003cf0  mov     [rsp+0D8h+var_60], r14
0x180003cf5  mov     rcx, [rsp+0D8h+var_90]
0x180003cfa  mov     rax, [rcx]
0x180003cfd  lea     r8, [rsp+0D8h+var_60]
0x180003d02  lea     rdx, _GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e
0x180003d09  mov     rax, [rax]
0x180003d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d11  nop
0x180003d12  mov     rcx, [rsp+0D8h]; this
0x180003d1a  test    eax, eax
0x180003d1c  js      loc_180004174
0x180003d22  mov     qword ptr [rsp+0D8h+var_68], r14
0x180003d27  mov     [rsp+0D8h+var_A0], r14
0x180003d2c  mov     [rsp+0D8h+string], r14
0x180003d34  lea     r9, [rsp+0D8h+string]; string
0x180003d3c  lea     r8, [rsp+0D8h+hstringHeader]; hstringHeader
0x180003d44  mov     edx, 2Dh ; '-'; length
0x180003d49  lea     rcx, ?RuntimeClass_Windows_Devices_Enumeration_DeviceInformation@@3QBGB; "Windows.Devices.Enumeration.DeviceInfor"...
0x180003d50  call    cs:__imp_WindowsCreateStringReference
0x180003d57  nop     dword ptr [rax+rax+00h]
0x180003d5c  test    eax, eax
0x180003d5e  js      loc_180004182
0x180003d64  mov     rbx, [rsp+0D8h+string]
0x180003d6c  mov     rcx, [rsp+0D8h+var_A0]
0x180003d71  test    rcx, rcx
0x180003d74  jz      short loc_180003D88
0x180003d76  mov     [rsp+0D8h+var_A0], r14
0x180003d7b  mov     rax, [rcx]
0x180003d7e  mov     rax, [rax+10h]
0x180003d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d87  nop
0x180003d88  lea     r8, [rsp+0D8h+var_A0]
0x180003d8d  lea     rdx, _GUID_493b4f34_a84f_45fd_9167_15d1cb1bd1f9
0x180003d94  mov     rcx, rbx
0x180003d97  call    cs:__imp_RoGetActivationFactory
0x180003d9e  nop     dword ptr [rax+rax+00h]
0x180003da3  mov     rcx, [rsp+0D8h]
0x180003dab  test    eax, eax
0x180003dad  js      loc_18000418A
0x180003db3  mov     rcx, [rsp+0D8h+var_A0]
0x180003db8  mov     rax, [rcx]
0x180003dbb  lea     rdx, [rsp+0D8h+var_68]
0x180003dc0  mov     qword ptr [rsp+0D8h+var_B8], rdx; int
0x180003dc5  mov     r9d, 3
0x180003dcb  mov     r8, [rsp+0D8h+var_60]
0x180003dd0  mov     rdx, [rsp+0D8h+var_98]
0x180003dd5  mov     rax, [rax+38h]
0x180003dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dde  mov     rcx, [rsp+0D8h]; this
0x180003de6  test    eax, eax
0x180003de8  js      loc_180004198
0x180003dee  mov     [rsp+0D8h+var_70], r14
0x180003df3  lea     rdx, [rsp+0D8h+var_70]
0x180003df8  mov     rcx, qword ptr [rsp+0D8h+var_68]
0x180003dfd  call    ??$BlockOnCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@23@UIDeviceInformation@Enumeration@Devices@3@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIDeviceInformation@Enumeration@Devices@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *>,Windows::Devices::Enumeration::IDeviceInformation>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Enumeration::IDeviceInformation>>,tagCOWAIT_FLAGS,void *)
0x180003e02  mov     rcx, [rsp+0D8h]; this
0x180003e0a  test    eax, eax
0x180003e0c  js      loc_1800041A6
0x180003e12  mov     [rsp+0D8h+var_78], r14
0x180003e17  mov     rcx, [rsp+0D8h+var_70]
0x180003e1c  mov     rax, [rcx]
0x180003e1f  lea     rdx, [rsp+0D8h+var_78]
0x180003e24  mov     rax, [rax+58h]
0x180003e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e2d  mov     rcx, [rsp+0D8h]; this
0x180003e35  test    eax, eax
0x180003e37  js      loc_1800041B4
0x180003e3d  mov     [rsp+0D8h+var_80], r14
0x180003e42  mov     rbx, [rsp+0D8h+var_78]
0x180003e47  mov     rdi, [rbx]
0x180003e4a  mov     [rsp+0D8h+string], r14
0x180003e52  lea     r9, [rsp+0D8h+string]; string
0x180003e5a  lea     r8, [rsp+0D8h+hstringHeader]; hstringHeader
0x180003e62  mov     edx, 16h; length
0x180003e67  lea     rcx, aSystemDevicesP; "System.Devices.Present"
0x180003e6e  call    cs:__imp_WindowsCreateStringReference
0x180003e75  nop     dword ptr [rax+rax+00h]
0x180003e7a  test    eax, eax
0x180003e7c  js      loc_1800041C2
0x180003e82  lea     r8, [rsp+0D8h+var_80]
0x180003e87  mov     rdx, [rsp+0D8h+string]
0x180003e8f  mov     rcx, rbx
0x180003e92  mov     rax, [rdi+30h]
0x180003e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e9b  mov     rcx, [rsp+0D8h]
0x180003ea3  test    eax, eax
0x180003ea5  js      loc_1800041CA
0x180003eab  mov     rcx, [rsp+0D8h+var_80]
0x180003eb0  test    rcx, rcx
0x180003eb3  setz    al
0x180003eb6  mov     r8, [rsp+0D8h]; unsigned int
0x180003ebe  test    al, al
0x180003ec0  jnz     loc_1800041D8
0x180003ec6  mov     [rsp+0D8h+var_88], r14
0x180003ecb  mov     rax, [rcx]
0x180003ece  lea     r8, [rsp+0D8h+var_88]
0x180003ed3  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180003eda  mov     rax, [rax]
0x180003edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ee2  nop
0x180003ee3  mov     rcx, [rsp+0D8h]; this
0x180003eeb  test    eax, eax
0x180003eed  js      loc_1800041EC
0x180003ef3  mov     [rsp+0D8h+var_A8], r14b
0x180003ef8  mov     rcx, [rsp+0D8h+var_88]
0x180003efd  mov     rax, [rcx]
0x180003f00  lea     rdx, [rsp+0D8h+var_A8]
0x180003f05  mov     rax, [rax+90h]
0x180003f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f11  mov     rcx, [rsp+0D8h]; this
0x180003f19  test    eax, eax
0x180003f1b  js      loc_1800041F9
0x180003f21  cmp     [rsp+0D8h+var_A8], r14b
0x180003f26  jz      short loc_180003F74
0x180003f28  mov     [rsp+0D8h+length], r14d
0x180003f2d  lea     rdx, [rsp+0D8h+length]; length
0x180003f32  mov     rcx, [rsp+0D8h+var_98]; string
0x180003f37  call    cs:__imp_WindowsGetStringRawBuffer
0x180003f3e  nop     dword ptr [rax+rax+00h]
0x180003f43  mov     rbx, rax
0x180003f46  mov     edx, [rsp+0D8h+length]
0x180003f4a  inc     edx
0x180003f4c  mov     rcx, [rsi]
0x180003f4f  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180003f54  mov     rdx, [rsi]
0x180003f57  mov     rcx, [rdx]; Destination
0x180003f5a  mov     rdx, [rdx+8]
0x180003f5e  sub     rdx, rcx
0x180003f61  sar     rdx, 1; SizeInWords
0x180003f64  mov     r8, rbx; Source
0x180003f67  call    cs:__imp_wcscpy_s
0x180003f6e  nop     dword ptr [rax+rax+00h]
0x180003f73  nop
0x180003f74  mov     rcx, [rsp+0D8h+var_88]
0x180003f79  test    rcx, rcx
0x180003f7c  jz      short loc_180003F90
0x180003f7e  mov     [rsp+0D8h+var_88], r14
0x180003f83  mov     rax, [rcx]
0x180003f86  mov     rax, [rax+10h]
0x180003f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f8f  nop
0x180003f90  mov     rcx, [rsp+0D8h+var_80]
0x180003f95  test    rcx, rcx
0x180003f98  jz      short loc_180003FAC
0x180003f9a  mov     [rsp+0D8h+var_80], r14
0x180003f9f  mov     rax, [rcx]
0x180003fa2  mov     rax, [rax+10h]
0x180003fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fab  nop
0x180003fac  mov     rcx, [rsp+0D8h+var_78]
0x180003fb1  test    rcx, rcx
0x180003fb4  jz      short loc_180003FC8
0x180003fb6  mov     [rsp+0D8h+var_78], r14
0x180003fbb  mov     rax, [rcx]
0x180003fbe  mov     rax, [rax+10h]
0x180003fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fc7  nop
0x180003fc8  mov     rcx, [rsp+0D8h+var_70]
0x180003fcd  test    rcx, rcx
0x180003fd0  jz      short loc_180003FE4
0x180003fd2  mov     [rsp+0D8h+var_70], r14
0x180003fd7  mov     rax, [rcx]
0x180003fda  mov     rax, [rax+10h]
0x180003fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fe3  nop
0x180003fe4  mov     rcx, [rsp+0D8h+var_A0]
0x180003fe9  test    rcx, rcx
0x180003fec  jz      short loc_180004000
0x180003fee  mov     [rsp+0D8h+var_A0], r14
0x180003ff3  mov     rax, [rcx]
0x180003ff6  mov     rax, [rax+10h]
0x180003ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fff  nop
0x180004000  mov     rcx, qword ptr [rsp+0D8h+var_68]
0x180004005  test    rcx, rcx
0x180004008  jz      short loc_18000401C
0x18000400a  mov     qword ptr [rsp+0D8h+var_68], r14
0x18000400f  mov     rax, [rcx]
0x180004012  mov     rax, [rax+10h]
0x180004016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000401b  nop
0x18000401c  mov     rcx, [rsp+0D8h+var_60]
0x180004021  test    rcx, rcx
0x180004024  jz      short loc_180004038
0x180004026  mov     [rsp+0D8h+var_60], r14
0x18000402b  mov     rax, [rcx]
0x18000402e  mov     rax, [rax+10h]
0x180004032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004037  nop
0x180004038  mov     rcx, [rsp+0D8h+var_90]
0x18000403d  test    rcx, rcx
0x180004040  jz      short loc_180004054
0x180004042  mov     [rsp+0D8h+var_90], r14
0x180004047  mov     rax, [rcx]
0x18000404a  mov     rax, [rax+10h]
0x18000404e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004053  nop
0x180004054  mov     rcx, [rsp+0D8h+var_98]; string
0x180004059  call    cs:__imp_WindowsDeleteString
0x180004060  nop     dword ptr [rax+rax+00h]
0x180004065  mov     [rsp+0D8h+var_98], r14
0x18000406a  mov     rcx, [rsp+0D8h+var_58]
0x180004072  test    rcx, rcx
0x180004075  jz      short loc_18000408C
  ... truncated ...
```
