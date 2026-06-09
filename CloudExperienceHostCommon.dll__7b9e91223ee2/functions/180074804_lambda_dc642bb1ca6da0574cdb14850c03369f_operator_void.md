# _lambda_dc642bb1ca6da0574cdb14850c03369f_::operator()(void)

- ea: `0x180074804`
- end: `0x180074bc6`
- name: `??R_lambda_dc642bb1ca6da0574cdb14850c03369f_@@QEBA@XZ`
- size: `962`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180074bcc`

## callees

- `0x180003a70`
- `0x180005174`
- `0x1800153f8`
- `0x18001a540`
- `0x180074804`
- `0x180078878`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180074952`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180074952`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180074939`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180074939`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800749e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074acd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074b2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800749e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074acd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074b2c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180074a50`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180074a50`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall _lambda_dc642bb1ca6da0574cdb14850c03369f_::operator()(__int64 a1)
{
  int v2; // ebx
  __int64 v3; // rdx
  __int64 *v4; // rcx
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rbx
  __int64 (__fastcall *v11)(__int64, HSTRING, _QWORD); // rdi
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  int v16; // eax
  int ActivationFactory; // eax
  __int64 v18; // rax
  int v19; // eax
  HSTRING v21; // [rsp+20h] [rbp-29h] BYREF
  __int64 (__fastcall ***v22)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-21h] BYREF
  __int64 v23; // [rsp+30h] [rbp-19h] BYREF
  __int64 v24; // [rsp+38h] [rbp-11h] BYREF
  int v25; // [rsp+40h] [rbp-9h] BYREF
  __int64 v26; // [rsp+48h] [rbp-1h] BYREF
  __int64 *v27; // [rsp+50h] [rbp+7h] BYREF
  __int64 (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+60h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v2 = **(_DWORD **)a1;
  if ( v2 < 0 )
  {
    v3 = 232;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
      (const char *)(unsigned int)v2,
      (int)v21);
    return (unsigned int)v2;
  }
  v25 = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD, int *))(***(_QWORD ***)(a1 + 8) + 48LL))(**(_QWORD **)(a1 + 8), &v25);
  if ( v2 < 0 )
  {
    v3 = 234;
    goto LABEL_37;
  }
  if ( v25 )
  {
    if ( v25 == 1 )
    {
      v2 = -2147024894;
      v3 = 263;
    }
    else if ( v25 == 2 )
    {
      v2 = -2147024846;
      v3 = 267;
    }
    else
    {
      v2 = -2147467259;
      v3 = 271;
    }
    goto LABEL_37;
  }
  v28 = 0;
  v4 = **(__int64 ***)(a1 + 8);
  v5 = *v4;
  v28 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(v5 + 56))(v4, &v28);
  v2 = v6;
  if ( v6 >= 0 )
  {
    if ( v28 )
    {
      v23 = 0;
      v9 = (**v28)(v28, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v23);
      v2 = v9;
      if ( v9 >= 0 )
      {
        v22 = 0;
        v10 = v23;
        v11 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v23 + 48LL);
        v22 = 0;
        if ( WindowsCreateStringReference(L"Result", 6u, &hstringHeader, &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v12 = v11(v10, string, &v22);
        v2 = v12;
        if ( v12 >= 0 )
        {
          v24 = 0;
          v13 = (**v22)(v22, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v24);
          v2 = v13;
          if ( v13 >= 0 )
          {
            v21 = 0;
            v14 = v24;
            v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 152LL);
            WindowsDeleteString(0);
            v21 = 0;
            v16 = v15(v14, &v21);
            v2 = v16;
            if ( v16 >= 0 )
            {
              v27 = 0;
              *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                (HSTRING_HEADER *)&string,
                L"CloudExperienceHostAPI.HostedApplicationResult",
                0x2Fu,
                0x2Eu);
              ActivationFactory = RoGetActivationFactory(
                                    *(_QWORD *)&hstringHeader.Reserved.Reserved2[16],
                                    &GUID_93ca117b_0c6e_4c5b_9a57_0bf38a869447,
                                    &v27);
              v2 = ActivationFactory;
              if ( ActivationFactory >= 0 )
              {
                v26 = 0;
                v18 = *v27;
                v26 = 0;
                v19 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v18 + 48))(v27, v21, &v26);
                v2 = v19;
                if ( v19 >= 0 )
                {
                  Windows::Internal::CMarshaledInterfaceResult<CloudExperienceHostAPI::IHostedApplicationResult>::Set(
                    **(_QWORD **)(a1 + 16),
                    v26);
                  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v26);
                  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v27);
                  WindowsDeleteString(v21);
                  v21 = 0;
                  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v24);
                  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v22);
                  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v23);
                  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v28);
                  return 0;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x102,
                  (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
                  (const char *)(unsigned int)v19,
                  (int)v21);
                wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v26);
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xFF,
                  (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
                  (const char *)(unsigned int)ActivationFactory,
                  (int)v21);
              }
              wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v27);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xFC,
                (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
                (const char *)(unsigned int)v16,
                (int)v21);
            }
            WindowsDeleteString(v21);
            v21 = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xF9,
              (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
              (const char *)(unsigned int)v13,
              (int)v21);
          }
          wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v24);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF7,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
            (const char *)(unsigned int)v12,
            (int)v21);
        }
        wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v22);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF4,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
          (const char *)(unsigned int)v9,
          (int)v21);
      }
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v23);
      goto LABEL_30;
    }
    v2 = -2147418113;
    v7 = 2147549183LL;
    v8 = 240;
  }
  else
  {
    v7 = (unsigned int)v6;
    v8 = 239;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
    (const char *)v7,
    (int)v21);
LABEL_30:
  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v28);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180074804  mov     [rsp-8+arg_8], rbx
0x180074809  mov     [rsp-8+arg_10], rsi
0x18007480e  push    rbp
0x18007480f  push    rdi
0x180074810  push    r14
0x180074812  lea     rbp, [rsp-47h]
0x180074817  sub     rsp, 90h
0x18007481e  mov     rax, cs:__security_cookie
0x180074825  xor     rax, rsp
0x180074828  mov     [rbp+57h+var_20], rax
0x18007482c  mov     rsi, rcx
0x18007482f  mov     rax, [rcx]
0x180074832  mov     ebx, [rax]
0x180074834  xor     r14d, r14d
0x180074837  test    ebx, ebx
0x180074839  jns     short loc_180074845
0x18007483b  mov     edx, 0E8h
0x180074840  jmp     loc_180074B8D
0x180074845  mov     [rbp+57h+var_60], r14d
0x180074849  mov     rax, [rcx+8]
0x18007484d  mov     rcx, [rax]
0x180074850  mov     rax, [rcx]
0x180074853  lea     rdx, [rbp+57h+var_60]
0x180074857  mov     rax, [rax+30h]
0x18007485b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074860  mov     ebx, eax
0x180074862  test    eax, eax
0x180074864  jns     short loc_180074870
0x180074866  mov     edx, 0EAh
0x18007486b  jmp     loc_180074B8D
0x180074870  mov     eax, [rbp+57h+var_60]
0x180074873  test    eax, eax
0x180074875  jnz     loc_180074B61
0x18007487b  mov     [rbp+57h+var_48], r14
0x18007487f  mov     rax, [rsi+8]
0x180074883  mov     rcx, [rax]
0x180074886  mov     rax, [rcx]
0x180074889  mov     [rbp+57h+var_48], r14
0x18007488d  lea     rdx, [rbp+57h+var_48]
0x180074891  mov     rax, [rax+38h]
0x180074895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007489a  mov     ebx, eax
0x18007489c  test    eax, eax
0x18007489e  jns     short loc_1800748AA
0x1800748a0  mov     r9d, eax
0x1800748a3  mov     edx, 0EFh
0x1800748a8  jmp     short loc_1800748C0
0x1800748aa  mov     rcx, [rbp+57h+var_48]
0x1800748ae  test    rcx, rcx
0x1800748b1  jnz     short loc_1800748D5
0x1800748b3  mov     ebx, 8000FFFFh
0x1800748b8  mov     r9d, ebx; char *
0x1800748bb  mov     edx, 0F0h; void *
0x1800748c0  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800748c7  mov     rcx, [rbp+5Fh]; this
0x1800748cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800748d0  jmp     loc_180074AF5
0x1800748d5  mov     [rbp+57h+var_70], r14
0x1800748d9  mov     rax, [rcx]
0x1800748dc  lea     r8, [rbp+57h+var_70]
0x1800748e0  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x1800748e7  mov     rax, [rax]
0x1800748ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800748ef  mov     ebx, eax
0x1800748f1  test    eax, eax
0x1800748f3  jns     short loc_180074912
0x1800748f5  mov     rcx, [rbp+5Fh]; this
0x1800748f9  mov     r9d, eax; char *
0x1800748fc  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\cloudexperiencehost"...
0x180074903  mov     edx, 0F4h; void *
0x180074908  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007490d  jmp     loc_180074AEB
0x180074912  mov     [rbp+57h+var_78], r14
0x180074916  mov     rbx, [rbp+57h+var_70]
0x18007491a  mov     rax, [rbx]
0x18007491d  mov     rdi, [rax+30h]
0x180074921  mov     [rbp+57h+var_78], r14
0x180074925  lea     r9, [rbp+57h+string]; string
0x180074929  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18007492d  mov     edx, 6; length
0x180074932  lea     rcx, aResult; "Result"
0x180074939  call    cs:__imp_WindowsCreateStringReference
0x18007493f  test    eax, eax
0x180074941  jns     short loc_180074958
0x180074943  xor     r9d, r9d; lpArguments
0x180074946  xor     r8d, r8d; nNumberOfArguments
0x180074949  lea     edx, [r9+1]; dwExceptionFlags
0x18007494d  mov     ecx, 0C000000Dh; dwExceptionCode
0x180074952  call    cs:__imp_RaiseException
0x180074958  lea     r8, [rbp+57h+var_78]
0x18007495c  mov     rdx, [rbp+57h+string]
0x180074960  mov     rcx, rbx
0x180074963  mov     rax, rdi
0x180074966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007496b  mov     ebx, eax
0x18007496d  test    eax, eax
0x18007496f  jns     short loc_18007498E
0x180074971  mov     rcx, [rbp+5Fh]; this
0x180074975  mov     r9d, eax; char *
0x180074978  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\cloudexperiencehost"...
0x18007497f  mov     edx, 0F7h; void *
0x180074984  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074989  jmp     loc_180074AE1
0x18007498e  mov     [rbp+57h+var_68], r14
0x180074992  mov     rcx, [rbp+57h+var_78]
0x180074996  mov     rax, [rcx]
0x180074999  lea     r8, [rbp+57h+var_68]
0x18007499d  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x1800749a4  mov     rax, [rax]
0x1800749a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800749ac  mov     ebx, eax
0x1800749ae  test    eax, eax
0x1800749b0  jns     short loc_1800749CF
0x1800749b2  mov     rcx, [rbp+5Fh]; this
0x1800749b6  mov     r9d, eax; char *
0x1800749b9  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800749c0  mov     edx, 0F9h; void *
0x1800749c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800749ca  jmp     loc_180074AD7
0x1800749cf  mov     [rbp+57h+var_80], r14
0x1800749d3  mov     rdi, [rbp+57h+var_68]
0x1800749d7  mov     rax, [rdi]
0x1800749da  mov     rbx, [rax+98h]
0x1800749e1  xor     ecx, ecx; string
0x1800749e3  call    cs:__imp_WindowsDeleteString
0x1800749e9  mov     [rbp+57h+var_80], r14
0x1800749ed  lea     rdx, [rbp+57h+var_80]
0x1800749f1  mov     rcx, rdi
0x1800749f4  mov     rax, rbx
0x1800749f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800749fc  mov     ebx, eax
0x1800749fe  test    eax, eax
0x180074a00  jns     short loc_180074A1F
0x180074a02  mov     rcx, [rbp+5Fh]; this
0x180074a06  mov     r9d, eax; char *
0x180074a09  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\cloudexperiencehost"...
0x180074a10  mov     edx, 0FCh; void *
0x180074a15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074a1a  jmp     loc_180074AC9
0x180074a1f  mov     [rbp+57h+var_50], r14
0x180074a23  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], r14
0x180074a27  mov     r9d, 2Eh ; '.'; unsigned int
0x180074a2d  lea     r8d, [r9+1]; unsigned int
0x180074a31  lea     rdx, ?RuntimeClass_CloudExperienceHostAPI_HostedApplicationResult@@3QBGB; "CloudExperienceHostAPI.HostedApplicatio"...
0x180074a38  lea     rcx, [rbp+57h+string]; hstringHeader
0x180074a3c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180074a41  lea     r8, [rbp+57h+var_50]
0x180074a45  lea     rdx, _GUID_93ca117b_0c6e_4c5b_9a57_0bf38a869447
0x180074a4c  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x180074a50  call    cs:__imp_RoGetActivationFactory
0x180074a56  mov     ebx, eax
0x180074a58  test    eax, eax
0x180074a5a  jns     short loc_180074A76
0x180074a5c  mov     rcx, [rbp+5Fh]; this
0x180074a60  mov     r9d, eax; char *
0x180074a63  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\cloudexperiencehost"...
0x180074a6a  mov     edx, 0FFh; void *
0x180074a6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074a74  jmp     short loc_180074ABF
0x180074a76  mov     [rbp+57h+var_58], r14
0x180074a7a  mov     rcx, [rbp+57h+var_50]
0x180074a7e  mov     rax, [rcx]
0x180074a81  mov     [rbp+57h+var_58], r14
0x180074a85  lea     r8, [rbp+57h+var_58]
0x180074a89  mov     rdx, [rbp+57h+var_80]
0x180074a8d  mov     rax, [rax+30h]
0x180074a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074a96  mov     ebx, eax
0x180074a98  test    eax, eax
0x180074a9a  jns     short loc_180074B03
0x180074a9c  mov     rcx, [rbp+5Fh]; this
0x180074aa0  mov     r9d, eax; char *
0x180074aa3  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\cloudexperiencehost"...
0x180074aaa  mov     edx, 102h; void *
0x180074aaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074ab4  nop
0x180074ab5  lea     rcx, [rbp+57h+var_58]
0x180074ab9  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180074abe  nop
0x180074abf  lea     rcx, [rbp+57h+var_50]
0x180074ac3  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180074ac8  nop
0x180074ac9  mov     rcx, [rbp+57h+var_80]; string
0x180074acd  call    cs:__imp_WindowsDeleteString
0x180074ad3  mov     [rbp+57h+var_80], r14
0x180074ad7  lea     rcx, [rbp+57h+var_68]
0x180074adb  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180074ae0  nop
0x180074ae1  lea     rcx, [rbp+57h+var_78]
0x180074ae5  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180074aea  nop
0x180074aeb  lea     rcx, [rbp+57h+var_70]
0x180074aef  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180074af4  nop
0x180074af5  lea     rcx, [rbp+57h+var_48]
0x180074af9  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180074afe  jmp     loc_180074BA0
0x180074b03  mov     rcx, [rsi+10h]
0x180074b07  mov     rdx, [rbp+57h+var_58]
0x180074b0b  mov     rcx, [rcx]
0x180074b0e  call    ?Set@?$CMarshaledInterfaceResult@UIHostedApplicationResult@CloudExperienceHostAPI@@@Internal@Windows@@QEAAJPEAUIHostedApplicationResult@CloudExperienceHostAPI@@@Z; Windows::Internal::CMarshaledInterfaceResult<CloudExperienceHostAPI::IHostedApplicationResult>::Set(CloudExperienceHostAPI::IHostedApplicationResult *)
0x180074b13  nop
0x180074b14  lea     rcx, [rbp+57h+var_58]
0x180074b18  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180074b1d  nop
0x180074b1e  lea     rcx, [rbp+57h+var_50]
0x180074b22  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180074b27  nop
0x180074b28  mov     rcx, [rbp+57h+var_80]; string
0x180074b2c  call    cs:__imp_WindowsDeleteString
0x180074b32  mov     [rbp+57h+var_80], r14
0x180074b36  lea     rcx, [rbp+57h+var_68]
0x180074b3a  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180074b3f  nop
0x180074b40  lea     rcx, [rbp+57h+var_78]
0x180074b44  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180074b49  nop
0x180074b4a  lea     rcx, [rbp+57h+var_70]
0x180074b4e  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180074b53  nop
0x180074b54  lea     rcx, [rbp+57h+var_48]
0x180074b58  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180074b5d  xor     eax, eax
0x180074b5f  jmp     short loc_180074BA2
0x180074b61  cmp     eax, 1
0x180074b64  jnz     short loc_180074B72
0x180074b66  mov     ebx, 80070002h
0x180074b6b  mov     edx, 107h
0x180074b70  jmp     short loc_180074B8D
0x180074b72  cmp     eax, 2
0x180074b75  jnz     short loc_180074B83
0x180074b77  mov     ebx, 80070032h
0x180074b7c  mov     edx, 10Bh
0x180074b81  jmp     short loc_180074B8D
0x180074b83  mov     ebx, 80004005h
0x180074b88  mov     edx, 10Fh; void *
0x180074b8d  mov     r9d, ebx; char *
0x180074b90  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\cloudexperiencehost"...
0x180074b97  mov     rcx, [rbp+5Fh]; this
0x180074b9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074ba0  mov     eax, ebx
0x180074ba2  mov     rcx, [rbp+57h+var_20]
0x180074ba6  xor     rcx, rsp; StackCookie
0x180074ba9  call    __security_check_cookie
0x180074bae  lea     r11, [rsp+0A0h+var_10]
0x180074bb6  mov     rbx, [r11+28h]
0x180074bba  mov     rsi, [r11+30h]
0x180074bbe  mov     rsp, r11
0x180074bc1  pop     r14
0x180074bc3  pop     rdi
0x180074bc4  pop     rbp
0x180074bc5  retn
```
