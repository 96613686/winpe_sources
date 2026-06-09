# Windows::ApplicationModel::Contacts::Internal::ContactDisplayInformation::_InitializeContactDisplayName(Windows::ApplicationModel::Contacts::IContact2 *)

- ea: `0x1801d2a5c`
- end: `0x1801d2d6f`
- name: `?_InitializeContactDisplayName@ContactDisplayInformation@Internal@Contacts@ApplicationModel@Windows@@AEAAJPEAUIContact2@345@@Z`
- size: `787`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Contacts::Internal::ContactDisplayInformation *__hidden this, struct Windows::ApplicationModel::Contacts::IContact2 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1801d2d78`

## callees

- `0x180009dd0`
- `0x1800ed2c0`
- `0x1801cd614`
- `0x1801d2a5c`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2abb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2af5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2b2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2b69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2c17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2ca9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2cc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2cec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2d18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2d28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2d38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2d48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2abb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2af5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2b2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2b69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2c17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2ca9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2cc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2cec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2d18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2d28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2d38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2d48`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Contacts::Internal::ContactDisplayInformation::_InitializeContactDisplayName(
        HSTRING *this,
        __int64 (__fastcall ***a2)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *))
{
  __int64 (__fastcall **v2)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v5)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rbx
  int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  __int64 (__fastcall **v15)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v16)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rbx
  HSTRING v17; // rsi
  HSTRING v18; // rdi
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rdi
  HSTRING v21; // rcx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, HSTRING *); // rbx
  int v24; // eax
  __int64 (__fastcall **v25)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v26)(struct Windows::ApplicationModel::Contacts::IContact2 *, __int64 *); // rbx
  _lambda_aec159daf75c9a566e43618f77172940_ *v27; // rax
  HSTRING v28; // rcx
  __int64 v30; // [rsp+20h] [rbp-30h] BYREF
  HSTRING v31; // [rsp+28h] [rbp-28h] BYREF
  __int64 v32; // [rsp+30h] [rbp-20h] BYREF
  HSTRING string; // [rsp+38h] [rbp-18h] BYREF
  _BYTE v34[16]; // [rsp+40h] [rbp-10h] BYREF
  HSTRING v35; // [rsp+98h] [rbp+48h] BYREF
  HSTRING v36; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v37; // [rsp+A8h] [rbp+58h] BYREF

  v2 = *a2;
  v37 = 0;
  v5 = *v2;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v37);
  v6 = v5((struct Windows::ApplicationModel::Contacts::IContact2 *)a2, &GUID_f404e97b_9034_453c_8ebf_140a38c86f1d, &v37);
  if ( v6 >= 0 )
  {
    v7 = v37;
    v36 = 0;
    v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 48LL);
    WindowsDeleteString(0);
    v36 = 0;
    v6 = v8(v7, &v36);
    if ( v6 < 0 )
    {
LABEL_34:
      WindowsDeleteString(v36);
      goto LABEL_35;
    }
    v9 = v37;
    v35 = 0;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 64LL);
    WindowsDeleteString(0);
    v35 = 0;
    v6 = v10(v9, &v35);
    if ( v6 < 0 )
    {
LABEL_33:
      WindowsDeleteString(v35);
      goto LABEL_34;
    }
    v11 = v37;
    v31 = 0;
    v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 96LL);
    WindowsDeleteString(0);
    v31 = 0;
    v6 = v12(v11, &v31);
    if ( v6 < 0 )
    {
LABEL_32:
      WindowsDeleteString(v31);
      goto LABEL_33;
    }
    v13 = v37;
    string = 0;
    v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 112LL);
    WindowsDeleteString(0);
    string = 0;
    v6 = v14(v13, &string);
    if ( v6 < 0 )
    {
LABEL_31:
      WindowsDeleteString(string);
      goto LABEL_32;
    }
    v15 = *a2;
    v30 = 0;
    v16 = *v15;
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v30);
    v6 = v16(
           (struct Windows::ApplicationModel::Contacts::IContact2 *)a2,
           &GUID_811233d1_3151_4e14_83da_ad47404c0b41,
           &v30);
    if ( v6 < 0 )
    {
LABEL_30:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v30);
      goto LABEL_31;
    }
    v17 = v36;
    v18 = v35;
    if ( v36 && v35 )
    {
      v19 = v30;
      v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 72LL);
LABEL_28:
      WindowsDeleteString(this[6]);
      this[6] = 0;
      v24 = v20(v19, this + 6);
      goto LABEL_29;
    }
    if ( string )
    {
      if ( v31 )
      {
        if ( !v36 )
        {
          v21 = this[6];
          if ( !v35 )
          {
            v22 = v30;
            v23 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 80LL);
            WindowsDeleteString(v21);
            this[6] = 0;
            v24 = v23(v22, this + 6);
LABEL_29:
            v6 = v24;
            goto LABEL_30;
          }
          goto LABEL_24;
        }
LABEL_26:
        v28 = this[6];
        v36 = 0;
        WindowsDeleteString(v28);
        this[6] = v17;
        goto LABEL_30;
      }
    }
    else if ( v31 )
    {
      if ( v36 )
        goto LABEL_26;
      goto LABEL_27;
    }
    if ( !string )
    {
      if ( v36 )
        goto LABEL_26;
      if ( !v35 )
      {
        v25 = *a2;
        v32 = 0;
        v26 = (__int64 (__fastcall *)(struct Windows::ApplicationModel::Contacts::IContact2 *, __int64 *))v25[16];
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
        v6 = v26((struct Windows::ApplicationModel::Contacts::IContact2 *)a2, &v32);
        if ( v6 >= 0 )
        {
          v27 = _lambda_aec159daf75c9a566e43618f77172940_::_lambda_aec159daf75c9a566e43618f77172940_(
                  (_lambda_aec159daf75c9a566e43618f77172940_ *)v34,
                  (struct CSearchSuggestionsProvider *)this);
          v6 = IterateOverVector_Windows::ApplicationModel::Contacts::ContactJobInfo__lambda_1322b4bfb983f315d52d35d98b81b5ca___(
                 v32,
                 v27);
        }
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
        goto LABEL_30;
      }
LABEL_23:
      v21 = this[6];
LABEL_24:
      v35 = 0;
      WindowsDeleteString(v21);
      this[6] = v18;
      goto LABEL_30;
    }
    if ( v35 )
      goto LABEL_23;
LABEL_27:
    v19 = v30;
    v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 80LL);
    goto LABEL_28;
  }
LABEL_35:
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v37);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801d2a5c  push    rbp
0x1801d2a5e  push    rbx
0x1801d2a5f  push    rsi
0x1801d2a60  push    rdi
0x1801d2a61  push    r12
0x1801d2a63  push    r14
0x1801d2a65  push    r15
0x1801d2a67  mov     rbp, rsp
0x1801d2a6a  sub     rsp, 50h
0x1801d2a6e  mov     rax, [rdx]
0x1801d2a71  mov     r14, rcx
0x1801d2a74  xor     r12d, r12d
0x1801d2a77  lea     rcx, [rbp+arg_18]
0x1801d2a7b  mov     r15, rdx
0x1801d2a7e  mov     [rbp+arg_18], r12
0x1801d2a82  mov     rbx, [rax]
0x1801d2a85  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d2a8a  lea     r8, [rbp+arg_18]
0x1801d2a8e  mov     rcx, r15
0x1801d2a91  lea     rdx, _GUID_f404e97b_9034_453c_8ebf_140a38c86f1d
0x1801d2a98  mov     rax, rbx
0x1801d2a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d2aa0  mov     ebx, eax
0x1801d2aa2  test    eax, eax
0x1801d2aa4  js      loc_1801D2D54
0x1801d2aaa  mov     rdi, [rbp+arg_18]
0x1801d2aae  xor     ecx, ecx; string
0x1801d2ab0  mov     [rbp+arg_10], r12
0x1801d2ab4  mov     rax, [rdi]
0x1801d2ab7  mov     rbx, [rax+30h]
0x1801d2abb  call    cs:__imp_WindowsDeleteString
0x1801d2ac2  nop     dword ptr [rax+rax+00h]
0x1801d2ac7  lea     rdx, [rbp+arg_10]
0x1801d2acb  mov     [rbp+arg_10], r12
0x1801d2acf  mov     rcx, rdi
0x1801d2ad2  mov     rax, rbx
0x1801d2ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d2ada  mov     ebx, eax
0x1801d2adc  test    eax, eax
0x1801d2ade  js      loc_1801D2D44
0x1801d2ae4  mov     rdi, [rbp+arg_18]
0x1801d2ae8  xor     ecx, ecx; string
0x1801d2aea  mov     [rbp+arg_8], r12
0x1801d2aee  mov     rax, [rdi]
0x1801d2af1  mov     rbx, [rax+40h]
0x1801d2af5  call    cs:__imp_WindowsDeleteString
0x1801d2afc  nop     dword ptr [rax+rax+00h]
0x1801d2b01  lea     rdx, [rbp+arg_8]
0x1801d2b05  mov     [rbp+arg_8], r12
0x1801d2b09  mov     rcx, rdi
0x1801d2b0c  mov     rax, rbx
0x1801d2b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d2b14  mov     ebx, eax
0x1801d2b16  test    eax, eax
0x1801d2b18  js      loc_1801D2D34
0x1801d2b1e  mov     rdi, [rbp+arg_18]
0x1801d2b22  xor     ecx, ecx; string
0x1801d2b24  mov     [rbp+var_28], r12
0x1801d2b28  mov     rax, [rdi]
0x1801d2b2b  mov     rbx, [rax+60h]
0x1801d2b2f  call    cs:__imp_WindowsDeleteString
0x1801d2b36  nop     dword ptr [rax+rax+00h]
0x1801d2b3b  lea     rdx, [rbp+var_28]
0x1801d2b3f  mov     [rbp+var_28], r12
0x1801d2b43  mov     rcx, rdi
0x1801d2b46  mov     rax, rbx
0x1801d2b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d2b4e  mov     ebx, eax
0x1801d2b50  test    eax, eax
0x1801d2b52  js      loc_1801D2D24
0x1801d2b58  mov     rdi, [rbp+arg_18]
0x1801d2b5c  xor     ecx, ecx; string
0x1801d2b5e  mov     [rbp+string], r12
0x1801d2b62  mov     rax, [rdi]
0x1801d2b65  mov     rbx, [rax+70h]
0x1801d2b69  call    cs:__imp_WindowsDeleteString
0x1801d2b70  nop     dword ptr [rax+rax+00h]
0x1801d2b75  lea     rdx, [rbp+string]
0x1801d2b79  mov     [rbp+string], r12
0x1801d2b7d  mov     rcx, rdi
0x1801d2b80  mov     rax, rbx
0x1801d2b83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d2b88  mov     ebx, eax
0x1801d2b8a  test    eax, eax
0x1801d2b8c  js      loc_1801D2D14
0x1801d2b92  mov     rax, [r15]
0x1801d2b95  lea     rcx, [rbp+var_30]
0x1801d2b99  mov     [rbp+var_30], r12
0x1801d2b9d  mov     rbx, [rax]
0x1801d2ba0  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d2ba5  lea     r8, [rbp+var_30]
0x1801d2ba9  mov     rcx, r15
0x1801d2bac  lea     rdx, _GUID_811233d1_3151_4e14_83da_ad47404c0b41
0x1801d2bb3  mov     rax, rbx
0x1801d2bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d2bbb  mov     ebx, eax
0x1801d2bbd  test    eax, eax
0x1801d2bbf  js      loc_1801D2D0B
0x1801d2bc5  mov     rsi, [rbp+arg_10]
0x1801d2bc9  mov     rdi, [rbp+arg_8]
0x1801d2bcd  test    rsi, rsi
0x1801d2bd0  jz      short loc_1801D2BE7
0x1801d2bd2  test    rdi, rdi
0x1801d2bd5  jz      short loc_1801D2BE7
0x1801d2bd7  mov     rsi, [rbp+var_30]
0x1801d2bdb  mov     rax, [rsi]
0x1801d2bde  mov     rdi, [rax+48h]
0x1801d2be2  jmp     loc_1801D2CE5
0x1801d2be7  mov     rax, [rbp+string]
0x1801d2beb  test    rax, rax
0x1801d2bee  jz      short loc_1801D2C36
0x1801d2bf0  cmp     [rbp+var_28], r12
0x1801d2bf4  jz      short loc_1801D2C3C
0x1801d2bf6  test    rsi, rsi
0x1801d2bf9  jnz     loc_1801D2CC0
0x1801d2bff  mov     rcx, [r14+30h]; string
0x1801d2c03  test    rdi, rdi
0x1801d2c06  jnz     loc_1801D2CA5
0x1801d2c0c  mov     rdi, [rbp+var_30]
0x1801d2c10  mov     rax, [rdi]
0x1801d2c13  mov     rbx, [rax+50h]
0x1801d2c17  call    cs:__imp_WindowsDeleteString
0x1801d2c1e  nop     dword ptr [rax+rax+00h]
0x1801d2c23  lea     rdx, [r14+30h]
0x1801d2c27  mov     [r14+30h], r12
0x1801d2c2b  mov     rcx, rdi
0x1801d2c2e  mov     rax, rbx
0x1801d2c31  jmp     loc_1801D2D04
0x1801d2c36  cmp     [rbp+var_28], r12
0x1801d2c3a  jnz     short loc_1801D2CBB
0x1801d2c3c  test    rax, rax
0x1801d2c3f  jnz     short loc_1801D2C9C
0x1801d2c41  test    rsi, rsi
0x1801d2c44  jnz     short loc_1801D2CC0
0x1801d2c46  test    rdi, rdi
0x1801d2c49  jnz     short loc_1801D2CA1
0x1801d2c4b  mov     rax, [r15]
0x1801d2c4e  lea     rcx, [rbp+var_20]
0x1801d2c52  mov     [rbp+var_20], r12
0x1801d2c56  mov     rbx, [rax+80h]
0x1801d2c5d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d2c62  lea     rdx, [rbp+var_20]
0x1801d2c66  mov     rcx, r15
0x1801d2c69  mov     rax, rbx
0x1801d2c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d2c71  mov     ebx, eax
0x1801d2c73  test    eax, eax
0x1801d2c75  js      short loc_1801D2C91
0x1801d2c77  mov     rdx, r14; struct CSearchSuggestionsProvider *
0x1801d2c7a  lea     rcx, [rbp+var_10]; this
0x1801d2c7e  call    ??0_lambda_aec159daf75c9a566e43618f77172940_@@QEAA@PEAVCSearchSuggestionsProvider@@@Z; _lambda_aec159daf75c9a566e43618f77172940_::_lambda_aec159daf75c9a566e43618f77172940_(CSearchSuggestionsProvider *)
0x1801d2c83  mov     rcx, [rbp+var_20]
0x1801d2c87  mov     rdx, rax
0x1801d2c8a  call    IterateOverVector_Windows__ApplicationModel__Contacts__ContactJobInfo__lambda_1322b4bfb983f315d52d35d98b81b5ca___
0x1801d2c8f  mov     ebx, eax
0x1801d2c91  lea     rcx, [rbp+var_20]
0x1801d2c95  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d2c9a  jmp     short loc_1801D2D0B
0x1801d2c9c  test    rdi, rdi
0x1801d2c9f  jz      short loc_1801D2CDA
0x1801d2ca1  mov     rcx, [r14+30h]; string
0x1801d2ca5  mov     [rbp+arg_8], r12
0x1801d2ca9  call    cs:__imp_WindowsDeleteString
0x1801d2cb0  nop     dword ptr [rax+rax+00h]
0x1801d2cb5  mov     [r14+30h], rdi
0x1801d2cb9  jmp     short loc_1801D2D0B
0x1801d2cbb  test    rsi, rsi
0x1801d2cbe  jz      short loc_1801D2CDA
0x1801d2cc0  mov     rcx, [r14+30h]; string
0x1801d2cc4  mov     [rbp+arg_10], r12
0x1801d2cc8  call    cs:__imp_WindowsDeleteString
0x1801d2ccf  nop     dword ptr [rax+rax+00h]
0x1801d2cd4  mov     [r14+30h], rsi
0x1801d2cd8  jmp     short loc_1801D2D0B
0x1801d2cda  mov     rsi, [rbp+var_30]
0x1801d2cde  mov     rax, [rsi]
0x1801d2ce1  mov     rdi, [rax+50h]
0x1801d2ce5  lea     rbx, [r14+30h]
0x1801d2ce9  mov     rcx, [rbx]; string
0x1801d2cec  call    cs:__imp_WindowsDeleteString
0x1801d2cf3  nop     dword ptr [rax+rax+00h]
0x1801d2cf8  mov     rdx, rbx
0x1801d2cfb  mov     [rbx], r12
0x1801d2cfe  mov     rcx, rsi
0x1801d2d01  mov     rax, rdi
0x1801d2d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d2d09  mov     ebx, eax
0x1801d2d0b  lea     rcx, [rbp+var_30]
0x1801d2d0f  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d2d14  mov     rcx, [rbp+string]; string
0x1801d2d18  call    cs:__imp_WindowsDeleteString
0x1801d2d1f  nop     dword ptr [rax+rax+00h]
0x1801d2d24  mov     rcx, [rbp+var_28]; string
0x1801d2d28  call    cs:__imp_WindowsDeleteString
0x1801d2d2f  nop     dword ptr [rax+rax+00h]
0x1801d2d34  mov     rcx, [rbp+arg_8]; string
0x1801d2d38  call    cs:__imp_WindowsDeleteString
0x1801d2d3f  nop     dword ptr [rax+rax+00h]
0x1801d2d44  mov     rcx, [rbp+arg_10]; string
0x1801d2d48  call    cs:__imp_WindowsDeleteString
0x1801d2d4f  nop     dword ptr [rax+rax+00h]
0x1801d2d54  lea     rcx, [rbp+arg_18]
0x1801d2d58  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d2d5d  mov     eax, ebx
0x1801d2d5f  add     rsp, 50h
0x1801d2d63  pop     r15
0x1801d2d65  pop     r14
0x1801d2d67  pop     r12
0x1801d2d69  pop     rdi
0x1801d2d6a  pop     rsi
0x1801d2d6b  pop     rbx
0x1801d2d6c  pop     rbp
0x1801d2d6d  retn
```
