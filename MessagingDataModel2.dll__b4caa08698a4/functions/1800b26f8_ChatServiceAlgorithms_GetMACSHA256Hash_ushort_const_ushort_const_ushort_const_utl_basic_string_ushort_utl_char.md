# ChatServiceAlgorithms::GetMACSHA256Hash(ushort const *,ushort const *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x1800b26f8`
- end: `0x1800b2f84`
- name: `?GetMACSHA256Hash@ChatServiceAlgorithms@@SAJPEBG00PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `2188`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a3a40`

## callees

- `0x180008870`
- `0x18000a754`
- `0x18000b7d4`
- `0x18001768c`
- `0x18002bb1c`
- `0x180030bd0`
- `0x18006b108`
- `0x180084738`
- `0x18008b890`
- `0x1800b266c`
- `0x1800b26d8`
- `0x1800b26f8`
- `0x1800b3484`
- `0x1800b35ec`
- `0x1800b3808`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b2936`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b29ac`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b2ae6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b2936`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b29ac`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b2ae6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2a15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2a4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2efb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2a15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2a4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2efb`

## string_xrefs

- `0x1800b2abb`: `Windows.Security.Cryptography.CryptographicBuffer`
- `0x1800b290b`: `Windows.Security.Cryptography.Core.HashAlgorithmProvider`
- `0x1800b2981`: `Windows.Security.Cryptography.Core.HashAlgorithmNames`
- `0x1800b2768`: `msmsgs@msnmsgr.com`

## pseudocode

```c
__int64 __fastcall ChatServiceAlgorithms::GetMACSHA256Hash(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v6; // r14d
  __int64 v7; // r15
  __int64 v8; // rcx
  unsigned __int64 v9; // r15
  unsigned int *v10; // rsi
  unsigned int v11; // ecx
  unsigned int v12; // r9d
  __int64 v13; // r8
  unsigned __int64 v14; // rdx
  unsigned int v15; // ecx
  unsigned int v16; // r11d
  unsigned __int64 v17; // rdx
  unsigned int v18; // ecx
  unsigned int v19; // edx
  unsigned __int64 v20; // r10
  unsigned int v21; // ecx
  unsigned int v22; // r10d
  unsigned __int64 v23; // rdx
  int ActivationFactory; // eax
  __int64 v25; // rcx
  void (*v26)(void); // rax
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, HSTRING *); // rbx
  int v32; // eax
  int v33; // eax
  __int64 v34; // rcx
  int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, PVOID, _QWORD, __int64 *); // rbx
  char v39; // r8
  HSTRING_HEADER *v40; // rax
  int v41; // eax
  int v42; // eax
  int v43; // eax
  __int64 v44; // rdi
  unsigned int *v45; // rbx
  unsigned int v46; // r10d
  __int64 i; // r11
  __int64 v48; // rax
  __int64 v49; // r10
  unsigned int v50; // r9d
  int v51; // r8d
  __int64 v52; // r10
  int v53; // edx
  __int64 v54; // rcx
  unsigned int *v55; // rdi
  int v56; // eax
  unsigned int j; // esi
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v64; // [rsp+48h] [rbp-B8h]
  __int64 v65; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v66; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v68; // [rsp+68h] [rbp-98h] BYREF
  __int64 v69; // [rsp+70h] [rbp-90h] BYREF
  __int64 v70; // [rsp+78h] [rbp-88h] BYREF
  __int64 v71; // [rsp+80h] [rbp-80h] BYREF
  unsigned int *v72; // [rsp+88h] [rbp-78h] BYREF
  __int64 v73; // [rsp+90h] [rbp-70h] BYREF
  unsigned int *v74; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v75[2]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v76[2]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int *v77; // [rsp+E0h] [rbp-20h] BYREF
  int v78; // [rsp+E8h] [rbp-18h] BYREF
  _OWORD v79[2]; // [rsp+F0h] [rbp-10h] BYREF

  memset(v75, 0, sizeof(v75));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v75);
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                          v75,
                          a1)
    && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                          v75,
                          L"msmsgs@msnmsgr.com") )
  {
    v7 = *((_QWORD *)&v75[0] + 1);
    v8 = *(_QWORD *)&v75[0];
    if ( (((__int64)(*((_QWORD *)&v75[0] + 1) - *(_QWORD *)&v75[0]) >> 1) & 7) == 0 )
      goto LABEL_7;
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                            v75,
                            8 - (((__int64)(*((_QWORD *)&v75[0] + 1) - *(_QWORD *)&v75[0]) >> 1) & 7)) )
    {
      v7 = *((_QWORD *)&v75[0] + 1);
      v8 = *(_QWORD *)&v75[0];
LABEL_7:
      v77 = 0;
      v9 = (unsigned __int64)((v7 - v8) >> 1) >> 2;
      utl::make_unique<unsigned int [0],0>(&v77, (unsigned int)v9);
      v10 = v77;
      v11 = 0;
      v12 = 0;
      if ( (_DWORD)v9 )
      {
        v13 = 0;
        do
        {
          v10[v13] = 0;
          v14 = v11;
          v15 = v11 + 1;
          if ( v14 >= (__int64)(*((_QWORD *)&v75[0] + 1) - *(_QWORD *)&v75[0]) >> 1 )
            __int2c();
          v16 = *(unsigned __int16 *)(*(_QWORD *)&v75[0] + 2 * v14);
          v10[v13] = v16;
          v17 = v15;
          v18 = v15 + 1;
          if ( v17 >= (__int64)(*((_QWORD *)&v75[0] + 1) - *(_QWORD *)&v75[0]) >> 1 )
            __int2c();
          v19 = v16 + (*(unsigned __int16 *)(*(_QWORD *)&v75[0] + 2 * v17) << 8);
          v20 = v18;
          v10[v13] = v19;
          v21 = v18 + 1;
          if ( v20 >= (__int64)(*((_QWORD *)&v75[0] + 1) - *(_QWORD *)&v75[0]) >> 1 )
            __int2c();
          v22 = v19 + (*(unsigned __int16 *)(*(_QWORD *)&v75[0] + 2 * v20) << 16);
          v23 = v21;
          v10[v13] = v22;
          v11 = v21 + 1;
          if ( v23 >= (__int64)(*((_QWORD *)&v75[0] + 1) - *(_QWORD *)&v75[0]) >> 1 )
            __int2c();
          ++v12;
          v10[v13++] = v22 + (*(unsigned __int16 *)(*(_QWORD *)&v75[0] + 2 * v23) << 24);
        }
        while ( v12 < (unsigned int)v9 );
      }
      memset(v79, 0, sizeof(v79));
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v79);
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               v79,
                               a1)
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               v79,
                               L"Q1P7W2E4J9R8U3S5") )
      {
        v6 = -2147024882;
        Log_HREvent_94(-2147024882);
        goto LABEL_86;
      }
      v65 = 0;
      v64 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Security.Cryptography.Core.HashAlgorithmProvider",
        0x39u,
        0x38u);
      ActivationFactory = RoGetActivationFactory(v64, &GUID_9fac9741_5cc4_4336_ae38_6212b75a915a, &v65);
      v6 = ActivationFactory;
      if ( ActivationFactory >= 0 )
      {
        v66 = 0;
        v64 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Security.Cryptography.Core.HashAlgorithmNames",
          0x36u,
          0x35u);
        v27 = RoGetActivationFactory(v64, &GUID_6b5e0516_de96_4f0a_8d57_dcc9dae36c76, &v66);
        v6 = v27;
        if ( v27 >= 0 )
        {
          v30 = v66;
          string = 0;
          v31 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v66 + 64LL);
          WindowsDeleteString(0);
          string = 0;
          v32 = v31(v30, &string);
          v6 = v32;
          if ( v32 >= 0 )
          {
            v68 = 0;
            v33 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v65 + 48LL))(v65, string, &v68);
            v6 = v33;
            if ( v33 >= 0 )
            {
              v69 = 0;
              v64 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                &hstringHeader,
                L"Windows.Security.Cryptography.CryptographicBuffer",
                0x32u,
                0x31u);
              v35 = RoGetActivationFactory(v64, &GUID_320b7e22_3cb0_4cdf_8663_1d28910065eb, &v69);
              v6 = v35;
              if ( v35 >= 0 )
              {
                v37 = v69;
                v70 = 0;
                v38 = *(__int64 (__fastcall **)(__int64, PVOID, _QWORD, __int64 *))(*(_QWORD *)v69 + 120LL);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
                v72 = *(unsigned int **)&v79[0];
                v40 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                        &hstringHeader,
                        (const WCHAR **)&v72,
                        v39);
                v41 = v38(v37, v40[1].Reserved.Reserved1, 0, &v70);
                v6 = v41;
                if ( v41 >= 0 )
                {
                  v71 = 0;
                  v42 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v68 + 64LL))(v68, v70, &v71);
                  v6 = v42;
                  if ( v42 >= 0 )
                  {
                    v78 = 0;
                    v73 = 0;
                    v43 = (*(__int64 (__fastcall **)(__int64, __int64, int *, __int64 *))(*(_QWORD *)v69 + 80LL))(
                            v69,
                            v71,
                            &v78,
                            &v73);
                    v6 = v43;
                    if ( v43 >= 0 )
                    {
                      v44 = v73;
                      v72 = 0;
                      utl::make_unique<unsigned int [0],0>(&v72, 4u);
                      v45 = v72;
                      v46 = 0;
                      for ( i = 0; i != 4; ++i )
                      {
                        v45[i] = 0;
                        v48 = v46;
                        v49 = v46 + 1;
                        v50 = *(unsigned __int8 *)(v48 + v44);
                        v45[i] = v50;
                        v51 = *(unsigned __int8 *)(v49 + v44);
                        v52 = (unsigned int)(v49 + 1);
                        v51 <<= 8;
                        v45[i] = v51 + v50;
                        v53 = *(unsigned __int8 *)(v52 + v44) << 16;
                        v54 = (unsigned int)(v52 + 1);
                        v46 = v52 + 2;
                        v45[i] = v50 + v53 + v51;
                        v45[i] = v50 + v51 + v53 + (*(unsigned __int8 *)(v54 + v44) << 24);
                      }
                      v74 = 0;
                      utl::make_unique<unsigned int [0],0>(&v74, 2u);
                      v55 = v74;
                      v56 = ChatServiceAlgorithms::_CS64(v10, v9, v45, v74);
                      v6 = v56;
                      if ( v56 >= 0 )
                      {
                        *v45 ^= *v55;
                        v45[1] ^= v55[1];
                        v45[2] ^= *v55;
                        v45[3] ^= v55[1];
                        memset(v76, 0, sizeof(v76));
                        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v76);
                        for ( j = 0; j < 4; ++j )
                        {
                          if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(
                                                   v76,
                                                   a0123456789abcd_0[(v45[j] >> 4) & 0xF])
                            || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(
                                                   v76,
                                                   a0123456789abcd_0[v45[j] & 0xF])
                            || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(
                                                   v76,
                                                   a0123456789abcd_0[(unsigned __int8)HIBYTE(LOWORD(v45[j])) >> 4])
                            || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(
                                                   v76,
                                                   a0123456789abcd_0[(v45[j] >> 8) & 0xF])
                            || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(
                                                   v76,
                                                   a0123456789abcd_0[(v45[j] >> 20) & 0xF])
                            || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(
                                                   v76,
                                                   a0123456789abcd_0[HIWORD(v45[j]) & 0xF])
                            || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(
                                                   v76,
                                                   a0123456789abcd_0[(unsigned __int64)v45[j] >> 28])
                            || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(
                                                   v76,
                                                   a0123456789abcd_0[HIBYTE(v45[j]) & 0xF]) )
                          {
                            goto LABEL_76;
                          }
                        }
                        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                                 a4,
                                                 *(_QWORD *)&v76[0]) )
                        {
LABEL_76:
                          v6 = -2147024882;
                          Log_HREvent_94(-2147024882);
                          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v76);
                          goto LABEL_55;
                        }
                        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v76);
                        utl::unique_ptr<unsigned int [0],utl::default_delete<unsigned int [0]>>::~unique_ptr<unsigned int [0],utl::default_delete<unsigned int [0]>>(&v74);
                        utl::unique_ptr<unsigned int [0],utl::default_delete<unsigned int [0]>>::~unique_ptr<unsigned int [0],utl::default_delete<unsigned int [0]>>(&v72);
                        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v73);
                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
                        v58 = v69;
                        if ( v69 )
                        {
                          v69 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
                        }
                        v59 = v68;
                        if ( v68 )
                        {
                          v68 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
                        }
                        WindowsDeleteString(string);
                        v60 = v66;
                        string = 0;
                        if ( v66 )
                        {
                          v66 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
                        }
                        v61 = v65;
                        if ( v65 )
                        {
                          v65 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
                        }
                        v6 = 0;
                        goto LABEL_86;
                      }
                      Log_HREvent_94(v56);
LABEL_55:
                      utl::unique_ptr<unsigned int [0],utl::default_delete<unsigned int [0]>>::~unique_ptr<unsigned int [0],utl::default_delete<unsigned int [0]>>(&v74);
                      utl::unique_ptr<unsigned int [0],utl::default_delete<unsigned int [0]>>::~unique_ptr<unsigned int [0],utl::default_delete<unsigned int [0]>>(&v72);
                    }
                    else
                    {
                      Log_HREvent_94(v43);
                    }
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v73);
                  }
                  else
                  {
                    Log_HREvent_94(v42);
                  }
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
                }
                else
                {
                  Log_HREvent_94(v41);
                }
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
              }
              else
              {
                Log_HREvent_94(v35);
              }
              v36 = v69;
              if ( v69 )
              {
                v69 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              }
            }
            else
            {
              Log_HREvent_94(v33);
            }
            v34 = v68;
            if ( v68 )
            {
              v68 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
            }
          }
          else
          {
            Log_HREvent_94(v32);
          }
          WindowsDeleteString(string);
          string = 0;
        }
        else
        {
          Log_HREvent_94(v27);
        }
        v28 = v66;
        if ( v66 )
        {
          v66 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        }
        v29 = v65;
        if ( !v65 )
        {
LABEL_86:
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v79);
          utl::unique_ptr<unsigned int [0],utl::default_delete<unsigned int [0]>>::~unique_ptr<unsigned int [0],utl::default_delete<unsigned int [0]>>(&v77);
          goto LABEL_87;
        }
        v65 = 0;
        v26 = *(void (**)(void))(*(_QWORD *)v29 + 16LL);
      }
      else
      {
        Log_HREvent_94(ActivationFactory);
        v25 = v65;
        if ( !v65 )
          goto LABEL_86;
        v65 = 0;
        v26 = *(void (**)(void))(*(_QWORD *)v25 + 16LL);
      }
      v26();
      goto LABEL_86;
    }
  }
  v6 = -2147024882;
  Log_HREvent_94(-2147024882);
LABEL_87:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v75);
  return v6;
}

```

## disassembly

```asm
0x1800b26f8  mov     [rsp-8+arg_8], rbx
0x1800b26fd  push    rbp
0x1800b26fe  push    rsi
0x1800b26ff  push    rdi
0x1800b2700  push    r12
0x1800b2702  push    r13
0x1800b2704  push    r14
0x1800b2706  push    r15
0x1800b2708  lea     rbp, [rsp-20h]
0x1800b270d  sub     rsp, 120h
0x1800b2714  mov     rax, cs:__security_cookie
0x1800b271b  xor     rax, rsp
0x1800b271e  mov     [rbp+50h+var_40], rax
0x1800b2722  xorps   xmm0, xmm0
0x1800b2725  mov     rbx, rcx
0x1800b2728  lea     rcx, [rbp+50h+var_B0]
0x1800b272c  mov     r12, r9
0x1800b272f  movups  [rbp+50h+var_B0], xmm0
0x1800b2733  movups  [rbp+50h+var_A0], xmm0
0x1800b2737  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800b273c  mov     rdx, rbx
0x1800b273f  lea     rcx, [rbp+50h+var_B0]
0x1800b2743  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800b2748  xor     r13d, r13d
0x1800b274b  test    al, al
0x1800b274d  jnz     short loc_1800B2768
0x1800b274f  lea     r9d, [r13+0Bh]
0x1800b2753  mov     r14d, 8007000Eh
0x1800b2759  xor     edx, edx
0x1800b275b  mov     ecx, r14d; int
0x1800b275e  call    Log_HREvent_94
0x1800b2763  jmp     loc_1800B2F51
0x1800b2768  lea     rdx, aMsmsgsMsnmsgrC; "msmsgs@msnmsgr.com"
0x1800b276f  lea     rcx, [rbp+50h+var_B0]
0x1800b2773  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800b2778  test    al, al
0x1800b277a  jnz     short loc_1800B2784
0x1800b277c  mov     r9d, 0Ch
0x1800b2782  jmp     short loc_1800B2753
0x1800b2784  mov     r15, qword ptr [rbp+50h+var_B0+8]
0x1800b2788  mov     rcx, qword ptr [rbp+50h+var_B0]
0x1800b278c  mov     rax, r15
0x1800b278f  sub     rax, rcx
0x1800b2792  sar     rax, 1
0x1800b2795  test    al, 7
0x1800b2797  jz      short loc_1800B27C1
0x1800b2799  and     eax, 7
0x1800b279c  lea     rcx, [rbp+50h+var_B0]
0x1800b27a0  mov     edx, 8
0x1800b27a5  sub     rdx, rax
0x1800b27a8  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_KG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(unsigned __int64,ushort)
0x1800b27ad  test    al, al
0x1800b27af  jnz     short loc_1800B27B9
0x1800b27b1  mov     r9d, 12h
0x1800b27b7  jmp     short loc_1800B2753
0x1800b27b9  mov     r15, qword ptr [rbp+50h+var_B0+8]
0x1800b27bd  mov     rcx, qword ptr [rbp+50h+var_B0]
0x1800b27c1  sub     r15, rcx
0x1800b27c4  mov     [rbp+50h+var_70], r13
0x1800b27c8  sar     r15, 1
0x1800b27cb  lea     rcx, [rbp+50h+var_70]
0x1800b27cf  shr     r15, 2
0x1800b27d3  mov     edx, r15d
0x1800b27d6  call    ??$make_unique@$$BY0A@I$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@IU?$default_delete@$$BY0A@I@utl@@@0@_K@Z; utl::make_unique<uint [0],0>(unsigned __int64)
0x1800b27db  mov     rsi, [rbp+50h+var_70]
0x1800b27df  mov     ecx, r13d
0x1800b27e2  mov     r9d, r13d
0x1800b27e5  mov     edi, 1
0x1800b27ea  test    r15d, r15d
0x1800b27ed  jz      loc_1800B28A5
0x1800b27f3  mov     r8, r13
0x1800b27f6  mov     [rsi+r8*4], r13d
0x1800b27fa  mov     rax, qword ptr [rbp+50h+var_B0+8]
0x1800b27fe  mov     r10, qword ptr [rbp+50h+var_B0]
0x1800b2802  sub     rax, r10
0x1800b2805  mov     edx, ecx
0x1800b2807  sar     rax, 1
0x1800b280a  add     ecx, edi
0x1800b280c  cmp     rdx, rax
0x1800b280f  jb      short loc_1800B2813
0x1800b2811  int     2Ch; Windows NT - assertion failure
0x1800b2813  movzx   r11d, word ptr [r10+rdx*2]
0x1800b2818  mov     [rsi+r8*4], r11d
0x1800b281c  mov     rax, qword ptr [rbp+50h+var_B0+8]
0x1800b2820  mov     r10, qword ptr [rbp+50h+var_B0]
0x1800b2824  sub     rax, r10
0x1800b2827  mov     edx, ecx
0x1800b2829  sar     rax, 1
0x1800b282c  add     ecx, edi
0x1800b282e  cmp     rdx, rax
0x1800b2831  jb      short loc_1800B2835
0x1800b2833  int     2Ch; Windows NT - assertion failure
0x1800b2835  movzx   edx, word ptr [r10+rdx*2]
0x1800b283a  shl     edx, 8
0x1800b283d  add     edx, r11d
0x1800b2840  mov     r10d, ecx
0x1800b2843  mov     [rsi+r8*4], edx
0x1800b2847  add     ecx, edi
0x1800b2849  mov     rax, qword ptr [rbp+50h+var_B0+8]
0x1800b284d  mov     r11, qword ptr [rbp+50h+var_B0]
0x1800b2851  sub     rax, r11
0x1800b2854  sar     rax, 1
0x1800b2857  cmp     r10, rax
0x1800b285a  jb      short loc_1800B285E
0x1800b285c  int     2Ch; Windows NT - assertion failure
0x1800b285e  movzx   r10d, word ptr [r11+r10*2]
0x1800b2863  shl     r10d, 10h
0x1800b2867  add     r10d, edx
0x1800b286a  mov     edx, ecx
0x1800b286c  mov     [rsi+r8*4], r10d
0x1800b2870  add     ecx, edi
0x1800b2872  mov     rax, qword ptr [rbp+50h+var_B0+8]
0x1800b2876  mov     r11, qword ptr [rbp+50h+var_B0]
0x1800b287a  sub     rax, r11
0x1800b287d  sar     rax, 1
0x1800b2880  cmp     rdx, rax
0x1800b2883  jb      short loc_1800B2887
0x1800b2885  int     2Ch; Windows NT - assertion failure
0x1800b2887  movzx   eax, word ptr [r11+rdx*2]
0x1800b288c  add     r9d, edi
0x1800b288f  shl     eax, 18h
0x1800b2892  add     eax, r10d
0x1800b2895  mov     [rsi+r8*4], eax
0x1800b2899  add     r8, rdi
0x1800b289c  cmp     r9d, r15d
0x1800b289f  jb      loc_1800B27F6
0x1800b28a5  xorps   xmm0, xmm0
0x1800b28a8  lea     rcx, [rbp+50h+var_60]
0x1800b28ac  movups  [rbp+50h+var_60], xmm0
0x1800b28b0  movups  [rbp+50h+var_50], xmm0
0x1800b28b4  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800b28b9  mov     rdx, rbx
0x1800b28bc  lea     rcx, [rbp+50h+var_60]
0x1800b28c0  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800b28c5  test    al, al
0x1800b28c7  jnz     short loc_1800B28D1
0x1800b28c9  mov     r9d, 22h ; '"'
0x1800b28cf  jmp     short loc_1800B28EB
0x1800b28d1  lea     rdx, aQ1p7w2e4j9r8u3; "Q1P7W2E4J9R8U3S5"
0x1800b28d8  lea     rcx, [rbp+50h+var_60]
0x1800b28dc  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800b28e1  test    al, al
0x1800b28e3  jnz     short loc_1800B2900
0x1800b28e5  mov     r9d, 23h ; '#'
0x1800b28eb  mov     r14d, 8007000Eh
0x1800b28f1  xor     edx, edx
0x1800b28f3  mov     ecx, r14d; int
0x1800b28f6  call    Log_HREvent_94
0x1800b28fb  jmp     loc_1800B2F3F
0x1800b2900  mov     r9d, 38h ; '8'; unsigned int
0x1800b2906  mov     [rsp+150h+var_100], r13
0x1800b290b  lea     rdx, ?RuntimeClass_Windows_Security_Cryptography_Core_HashAlgorithmProvider@@3QBGB; "Windows.Security.Cryptography.Core.Hash"...
0x1800b2912  mov     [rsp+150h+var_108], r13
0x1800b2917  lea     rcx, [rsp+150h+hstringHeader]; hstringHeader
0x1800b291c  lea     r8d, [r9+1]; unsigned int
0x1800b2920  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b2925  mov     rcx, [rsp+150h+var_108]
0x1800b292a  lea     r8, [rsp+150h+var_100]
0x1800b292f  lea     rdx, _GUID_9fac9741_5cc4_4336_ae38_6212b75a915a
0x1800b2936  call    cs:__imp_RoGetActivationFactory
0x1800b293c  mov     r14d, eax
0x1800b293f  test    eax, eax
0x1800b2941  jns     short loc_1800B2976
0x1800b2943  mov     r9d, 28h ; '('
0x1800b2949  mov     edx, edi
0x1800b294b  mov     ecx, eax; int
0x1800b294d  call    Log_HREvent_94
0x1800b2952  mov     rcx, [rsp+150h+var_100]
0x1800b2957  test    rcx, rcx
0x1800b295a  jz      loc_1800B2F3F
0x1800b2960  mov     [rsp+150h+var_100], r13
0x1800b2965  mov     rdx, [rcx]
0x1800b2968  mov     rax, [rdx+10h]
0x1800b296c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2971  jmp     loc_1800B2F3F
0x1800b2976  mov     r9d, 35h ; '5'; unsigned int
0x1800b297c  mov     [rsp+150h+var_F8], r13
0x1800b2981  lea     rdx, ?RuntimeClass_Windows_Security_Cryptography_Core_HashAlgorithmNames@@3QBGB; "Windows.Security.Cryptography.Core.Hash"...
0x1800b2988  mov     [rsp+150h+var_108], r13
0x1800b298d  lea     rcx, [rsp+150h+hstringHeader]; hstringHeader
0x1800b2992  lea     r8d, [r9+1]; unsigned int
0x1800b2996  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b299b  mov     rcx, [rsp+150h+var_108]
0x1800b29a0  lea     r8, [rsp+150h+var_F8]
0x1800b29a5  lea     rdx, _GUID_6b5e0516_de96_4f0a_8d57_dcc9dae36c76
0x1800b29ac  call    cs:__imp_RoGetActivationFactory
0x1800b29b2  mov     r14d, eax
0x1800b29b5  test    eax, eax
0x1800b29b7  jns     short loc_1800B2A02
0x1800b29b9  mov     r9d, 2Dh ; '-'
0x1800b29bf  mov     edx, edi
0x1800b29c1  mov     ecx, eax; int
0x1800b29c3  call    Log_HREvent_94
0x1800b29c8  mov     rcx, [rsp+150h+var_F8]
0x1800b29cd  test    rcx, rcx
0x1800b29d0  jz      short loc_1800B29E3
0x1800b29d2  mov     [rsp+150h+var_F8], r13
0x1800b29d7  mov     rax, [rcx]
0x1800b29da  mov     rax, [rax+10h]
0x1800b29de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b29e3  mov     rcx, [rsp+150h+var_100]
0x1800b29e8  test    rcx, rcx
0x1800b29eb  jz      loc_1800B2F3F
0x1800b29f1  mov     [rsp+150h+var_100], r13
0x1800b29f6  mov     rax, [rcx]
0x1800b29f9  mov     rax, [rax+10h]
0x1800b29fd  jmp     loc_1800B296C
0x1800b2a02  mov     rdi, [rsp+150h+var_F8]
0x1800b2a07  xor     ecx, ecx; string
0x1800b2a09  mov     [rsp+150h+string], r13
0x1800b2a0e  mov     rax, [rdi]
0x1800b2a11  mov     rbx, [rax+40h]
0x1800b2a15  call    cs:__imp_WindowsDeleteString
0x1800b2a1b  lea     rdx, [rsp+150h+string]
0x1800b2a20  mov     [rsp+150h+string], r13
0x1800b2a25  mov     rcx, rdi
0x1800b2a28  mov     rax, rbx
0x1800b2a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2a30  mov     r14d, eax
0x1800b2a33  test    eax, eax
0x1800b2a35  jns     short loc_1800B2A5C
0x1800b2a37  mov     edx, 1
0x1800b2a3c  mov     ecx, eax; int
0x1800b2a3e  lea     r9d, [rdx+2Fh]
0x1800b2a42  call    Log_HREvent_94
0x1800b2a47  mov     rcx, [rsp+150h+string]; string
0x1800b2a4c  call    cs:__imp_WindowsDeleteString
0x1800b2a52  mov     [rsp+150h+string], r13
0x1800b2a57  jmp     loc_1800B29C8
0x1800b2a5c  mov     rcx, [rsp+150h+var_100]
0x1800b2a61  lea     r8, [rsp+150h+var_E8]
0x1800b2a66  mov     rdx, [rsp+150h+string]
0x1800b2a6b  mov     [rsp+150h+var_E8], r13
0x1800b2a70  mov     rax, [rcx]
0x1800b2a73  mov     rax, [rax+30h]
0x1800b2a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2a7c  mov     r14d, eax
0x1800b2a7f  test    eax, eax
0x1800b2a81  jns     short loc_1800B2AB0
0x1800b2a83  mov     edx, 1
0x1800b2a88  mov     ecx, eax; int
0x1800b2a8a  lea     r9d, [rdx+32h]
0x1800b2a8e  call    Log_HREvent_94
0x1800b2a93  mov     rcx, [rsp+150h+var_E8]
0x1800b2a98  test    rcx, rcx
0x1800b2a9b  jz      short loc_1800B2A47
0x1800b2a9d  mov     [rsp+150h+var_E8], r13
0x1800b2aa2  mov     rax, [rcx]
0x1800b2aa5  mov     rax, [rax+10h]
0x1800b2aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2aae  jmp     short loc_1800B2A47
0x1800b2ab0  mov     r9d, 31h ; '1'; unsigned int
0x1800b2ab6  mov     [rsp+150h+var_E0], r13
0x1800b2abb  lea     rdx, ?RuntimeClass_Windows_Security_Cryptography_CryptographicBuffer@@3QBGB; "Windows.Security.Cryptography.Cryptogra"...
0x1800b2ac2  mov     [rsp+150h+var_108], r13
0x1800b2ac7  lea     rcx, [rsp+150h+hstringHeader]; hstringHeader
0x1800b2acc  lea     r8d, [r9+1]; unsigned int
0x1800b2ad0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b2ad5  mov     rcx, [rsp+150h+var_108]
0x1800b2ada  lea     r8, [rsp+150h+var_E0]
0x1800b2adf  lea     rdx, _GUID_320b7e22_3cb0_4cdf_8663_1d28910065eb
0x1800b2ae6  call    cs:__imp_RoGetActivationFactory
0x1800b2aec  mov     r14d, eax
0x1800b2aef  test    eax, eax
0x1800b2af1  jns     short loc_1800B2B23
0x1800b2af3  mov     edx, 1
0x1800b2af8  mov     ecx, eax; int
0x1800b2afa  lea     r9d, [rdx+37h]
0x1800b2afe  call    Log_HREvent_94
0x1800b2b03  mov     rcx, [rsp+150h+var_E0]
0x1800b2b08  test    rcx, rcx
0x1800b2b0b  jz      short loc_1800B2A93
0x1800b2b0d  mov     [rsp+150h+var_E0], r13
0x1800b2b12  mov     rax, [rcx]
0x1800b2b15  mov     rax, [rax+10h]
0x1800b2b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2b1e  jmp     loc_1800B2A93
0x1800b2b23  mov     rdi, [rsp+150h+var_E0]
0x1800b2b28  lea     rcx, [rsp+150h+var_D8]
0x1800b2b2d  mov     [rsp+150h+var_D8], r13
0x1800b2b32  mov     rax, [rdi]
0x1800b2b35  mov     rbx, [rax+78h]
0x1800b2b39  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b2b3e  mov     rdx, qword ptr [rbp+50h+var_60]
0x1800b2b42  lea     rcx, [rsp+150h+hstringHeader]
0x1800b2b47  mov     [rbp+50h+var_C8], rdx
0x1800b2b4b  lea     rdx, [rbp+50h+var_C8]
0x1800b2b4f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800b2b54  lea     r9, [rsp+150h+var_D8]
0x1800b2b59  xor     r8d, r8d
0x1800b2b5c  mov     rcx, rdi
0x1800b2b5f  mov     rdx, [rax+18h]
0x1800b2b63  mov     rax, rbx
0x1800b2b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2b6b  mov     r14d, eax
0x1800b2b6e  test    eax, eax
0x1800b2b70  jns     short loc_1800B2B91
0x1800b2b72  mov     edx, 1
0x1800b2b77  mov     ecx, eax; int
0x1800b2b79  lea     r9d, [rdx+3Bh]
  ... truncated ...
```
