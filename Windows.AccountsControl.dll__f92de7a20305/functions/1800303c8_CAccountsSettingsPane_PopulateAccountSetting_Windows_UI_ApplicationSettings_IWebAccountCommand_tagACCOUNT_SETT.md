# CAccountsSettingsPane::_PopulateAccountSetting(Windows::UI::ApplicationSettings::IWebAccountCommand *,tagACCOUNT_SETTING *)

- ea: `0x1800303c8`
- end: `0x1800305d2`
- name: `?_PopulateAccountSetting@CAccountsSettingsPane@@AEAAJPEAUIWebAccountCommand@ApplicationSettings@UI@Windows@@PEAUtagACCOUNT_SETTING@@@Z`
- size: `522`
- prototype: `int(CAccountsSettingsPane *__hidden this, struct Windows::UI::ApplicationSettings::IWebAccountCommand *, struct tagACCOUNT_SETTING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002a400`

## callees

- `0x180011ffc`
- `0x180018f90`
- `0x18001c434`
- `0x180030004`
- `0x1800303c8`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030436`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800305b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030436`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800305b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030480`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030480`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CAccountsSettingsPane::_PopulateAccountSetting(
        CAccountsSettingsPane *this,
        struct Windows::UI::ApplicationSettings::IWebAccountCommand *a2,
        struct tagACCOUNT_SETTING *a3)
{
  __int64 (__fastcall *v5)(struct Windows::UI::ApplicationSettings::IWebAccountCommand *, __int64 *); // rbx
  int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  __int64 v9; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  CAccountsSettingsPane *v14; // rcx
  __int64 v15; // rax
  char v16; // al
  HSTRING string; // [rsp+30h] [rbp-28h] BYREF
  __int64 v19; // [rsp+38h] [rbp-20h] BYREF
  __int64 v20; // [rsp+40h] [rbp-18h]
  __int64 v21; // [rsp+48h] [rbp-10h]
  CAccountsSettingsPane *v22; // [rsp+90h] [rbp+38h] BYREF
  int v23; // [rsp+98h] [rbp+40h] BYREF
  __int64 v24; // [rsp+A0h] [rbp+48h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v25; // [rsp+A8h] [rbp+50h] BYREF

  v22 = this;
  *(_QWORD *)a3 = 0;
  *((_QWORD *)a3 + 1) = 0;
  *((_QWORD *)a3 + 2) = 0;
  *((_DWORD *)a3 + 6) = 2;
  v24 = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::UI::ApplicationSettings::IWebAccountCommand *, __int64 *))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  v6 = v5(a2, &v24);
  if ( v6 >= 0 )
  {
    string = 0;
    v7 = v24;
    v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v6 = v8(v7, &string);
    if ( v6 >= 0 )
    {
      v19 = 0;
      v20 = 0;
      v21 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v19);
      v9 = -1;
      v20 = -1;
      v21 = -1;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      do
        ++v9;
      while ( StringRawBuffer[v9] );
      v6 = _AllocStringWorker<CTCoAllocPolicy>(&v19, v11, StringRawBuffer);
      if ( v6 >= 0 )
      {
        LODWORD(v22) = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, CAccountsSettingsPane **))(*(_QWORD *)v24 + 64LL))(v24, &v22);
        if ( v6 >= 0 )
        {
          *((_DWORD *)a3 + 7) = 0;
          v23 = 0;
          v6 = (*(__int64 (__fastcall **)(struct Windows::UI::ApplicationSettings::IWebAccountCommand *, int *))(*(_QWORD *)a2 + 64LL))(
                 a2,
                 &v23);
          if ( v6 >= 0 )
          {
            v25 = 0;
            v12 = v24;
            v13 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)v24 + 48LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
            v6 = v13(v12, &v25);
            if ( v6 >= 0 )
            {
              v6 = CAccountsSettingsPane::_PopulateAccountProviderSetting(v14, v25, a3);
              if ( v6 >= 0 )
              {
                *((_DWORD *)a3 + 8) = 1;
                v15 = v19;
                v19 = 0;
                v21 = 0;
                v20 = 0;
                *((_QWORD *)a3 + 2) = v15;
                if ( (_DWORD)v22 )
                {
                  if ( (_DWORD)v22 == 1 )
                  {
                    *((_DWORD *)a3 + 6) = 1;
                  }
                  else if ( (_DWORD)v22 == 2 )
                  {
                    *((_DWORD *)a3 + 6) = 2;
                  }
                }
                else
                {
                  *((_DWORD *)a3 + 6) = 0;
                }
                v16 = v23;
                if ( (v23 & 1) != 0 )
                  *((_DWORD *)a3 + 7) |= 1u;
                if ( (v16 & 2) != 0 )
                  *((_DWORD *)a3 + 7) |= 2u;
                if ( (v16 & 4) != 0 )
                  *((_DWORD *)a3 + 7) |= 4u;
                if ( (v16 & 8) != 0 )
                  *((_DWORD *)a3 + 7) |= 8u;
                if ( (v16 & 0x10) != 0 )
                  *((_DWORD *)a3 + 7) |= 0x10u;
              }
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
          }
        }
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v19);
    }
    WindowsDeleteString(string);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800303c8  mov     [rsp-30h+arg_0], rcx
0x1800303cd  push    rbp
0x1800303ce  push    rbx
0x1800303cf  push    rsi
0x1800303d0  push    rdi
0x1800303d1  push    r14
0x1800303d3  push    r15
0x1800303d5  mov     rbp, rsp
0x1800303d8  sub     rsp, 58h
0x1800303dc  mov     rsi, r8
0x1800303df  mov     r14, rdx
0x1800303e2  xor     r15d, r15d
0x1800303e5  mov     [r8], r15
0x1800303e8  mov     [r8+8], r15
0x1800303ec  mov     [r8+10h], r15
0x1800303f0  mov     dword ptr [r8+18h], 2
0x1800303f8  mov     [rbp+arg_10], r15
0x1800303fc  mov     rax, [rdx]
0x1800303ff  mov     rbx, [rax+30h]
0x180030403  lea     rcx, [rbp+arg_10]
0x180030407  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003040c  lea     rdx, [rbp+arg_10]
0x180030410  mov     rcx, r14
0x180030413  mov     rax, rbx
0x180030416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003041b  mov     ebx, eax
0x18003041d  test    eax, eax
0x18003041f  js      loc_1800305BA
0x180030425  mov     [rbp+string], r15
0x180030429  mov     rdi, [rbp+arg_10]
0x18003042d  mov     rax, [rdi]
0x180030430  mov     rbx, [rax+38h]
0x180030434  xor     ecx, ecx; string
0x180030436  call    cs:__imp_WindowsDeleteString
0x18003043c  mov     [rbp+string], r15
0x180030440  lea     rdx, [rbp+string]
0x180030444  mov     rcx, rdi
0x180030447  mov     rax, rbx
0x18003044a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003044f  mov     ebx, eax
0x180030451  test    eax, eax
0x180030453  js      loc_1800305AF
0x180030459  mov     [rbp+var_20], r15
0x18003045d  mov     [rbp+var_18], r15
0x180030461  mov     [rbp+var_10], r15
0x180030465  lea     rcx, [rbp+var_20]
0x180030469  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003046e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180030472  mov     [rbp+var_18], rbx
0x180030476  mov     [rbp+var_10], rbx
0x18003047a  xor     edx, edx; length
0x18003047c  mov     rcx, [rbp+string]; string
0x180030480  call    cs:__imp_WindowsGetStringRawBuffer
0x180030486  inc     rbx
0x180030489  cmp     [rax+rbx*2], r15w
0x18003048e  jnz     short loc_180030486
0x180030490  lea     rcx, [rbp+var_20]
0x180030494  mov     [rsp+58h+var_30], rcx
0x180030499  mov     r9, rbx
0x18003049c  mov     r8, rax
0x18003049f  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800304a4  mov     ebx, eax
0x1800304a6  test    eax, eax
0x1800304a8  js      loc_1800305A5
0x1800304ae  mov     dword ptr [rbp+arg_0], r15d
0x1800304b2  mov     rcx, [rbp+arg_10]
0x1800304b6  mov     rax, [rcx]
0x1800304b9  lea     rdx, [rbp+arg_0]
0x1800304bd  mov     rax, [rax+40h]
0x1800304c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304c6  mov     ebx, eax
0x1800304c8  test    eax, eax
0x1800304ca  js      loc_1800305A5
0x1800304d0  mov     [rsi+1Ch], r15d
0x1800304d4  mov     [rbp+arg_8], r15d
0x1800304d8  mov     rax, [r14]
0x1800304db  lea     rdx, [rbp+arg_8]
0x1800304df  mov     rcx, r14
0x1800304e2  mov     rax, [rax+40h]
0x1800304e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304eb  mov     ebx, eax
0x1800304ed  test    eax, eax
0x1800304ef  js      loc_1800305A5
0x1800304f5  mov     [rbp+arg_18], r15
0x1800304f9  mov     rdi, [rbp+arg_10]
0x1800304fd  mov     rax, [rdi]
0x180030500  mov     rbx, [rax+30h]
0x180030504  lea     rcx, [rbp+arg_18]
0x180030508  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003050d  lea     rdx, [rbp+arg_18]
0x180030511  mov     rcx, rdi
0x180030514  mov     rax, rbx
0x180030517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003051c  mov     ebx, eax
0x18003051e  test    eax, eax
0x180030520  js      short loc_18003059B
0x180030522  mov     r8, rsi; struct tagACCOUNT_PROVIDER_SETTING *
0x180030525  mov     rdx, [rbp+arg_18]; struct Windows::Security::Credentials::IWebAccountProvider *
0x180030529  call    ?_PopulateAccountProviderSetting@CAccountsSettingsPane@@AEAAJPEAUIWebAccountProvider@Credentials@Security@Windows@@PEAUtagACCOUNT_PROVIDER_SETTING@@@Z; CAccountsSettingsPane::_PopulateAccountProviderSetting(Windows::Security::Credentials::IWebAccountProvider *,tagACCOUNT_PROVIDER_SETTING *)
0x18003052e  mov     ebx, eax
0x180030530  test    eax, eax
0x180030532  js      short loc_18003059B
0x180030534  mov     edx, 1
0x180030539  mov     [rsi+20h], edx
0x18003053c  mov     rax, [rbp+var_20]
0x180030540  mov     [rbp+var_20], r15
0x180030544  mov     [rbp+var_10], r15
0x180030548  mov     [rbp+var_18], r15
0x18003054c  mov     [rsi+10h], rax
0x180030550  mov     ecx, dword ptr [rbp+arg_0]
0x180030553  test    ecx, ecx
0x180030555  jz      short loc_18003056D
0x180030557  sub     ecx, edx
0x180030559  jz      short loc_180030568
0x18003055b  cmp     ecx, edx
0x18003055d  jnz     short loc_180030571
0x18003055f  mov     dword ptr [rsi+18h], 2
0x180030566  jmp     short loc_180030571
0x180030568  mov     [rsi+18h], edx
0x18003056b  jmp     short loc_180030571
0x18003056d  mov     [rsi+18h], r15d
0x180030571  mov     eax, [rbp+arg_8]
0x180030574  test    dl, al
0x180030576  jz      short loc_18003057B
0x180030578  or      [rsi+1Ch], edx
0x18003057b  test    al, 2
0x18003057d  jz      short loc_180030583
0x18003057f  or      dword ptr [rsi+1Ch], 2
0x180030583  test    al, 4
0x180030585  jz      short loc_18003058B
0x180030587  or      dword ptr [rsi+1Ch], 4
0x18003058b  test    al, 8
0x18003058d  jz      short loc_180030593
0x18003058f  or      dword ptr [rsi+1Ch], 8
0x180030593  test    al, 10h
0x180030595  jz      short loc_18003059B
0x180030597  or      dword ptr [rsi+1Ch], 10h
0x18003059b  lea     rcx, [rbp+arg_18]
0x18003059f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800305a4  nop
0x1800305a5  lea     rcx, [rbp+var_20]
0x1800305a9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800305ae  nop
0x1800305af  mov     rcx, [rbp+string]; string
0x1800305b3  call    cs:__imp_WindowsDeleteString
0x1800305b9  nop
0x1800305ba  lea     rcx, [rbp+arg_10]
0x1800305be  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800305c3  mov     eax, ebx
0x1800305c5  add     rsp, 58h
0x1800305c9  pop     r15
0x1800305cb  pop     r14
0x1800305cd  pop     rdi
0x1800305ce  pop     rsi
0x1800305cf  pop     rbx
0x1800305d0  pop     rbp
0x1800305d1  retn
```
