# Microsoft::Authentication::Validation::FindProviderForUser(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,Windows::Security::Credentials::IWebAccountProvider * *)

- ea: `0x1400159a4`
- end: `0x140015bfe`
- name: `?FindProviderForUser@Validation@Authentication@Microsoft@@CAJPEAUIUser@System@Windows@@PEAUHSTRING__@@1PEAPEAUIWebAccountProvider@Credentials@Security@6@@Z`
- size: `602`
- prototype: `__int64 __fastcall(struct Windows::System::IUser *, HSTRING, HSTRING, struct Windows::Security::Credentials::IWebAccountProvider **)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400152cc`
- `0x14001563c`

## callees

- `0x140002d30`
- `0x14000aab8`
- `0x14000c32c`
- `0x14000e030`
- `0x1400132cc`
- `0x14001379c`
- `0x1400159a4`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140015bba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140015bba`

## string_xrefs

- `0x140015aed`: `onecoreuap\enduser\NUI\OneCore\common\include\EnterpriseAttached.h`
- `0x140015ba7`: `onecoreuap\enduser\NUI\OneCore\common\include\EnterpriseAttached.h`
- `0x140015a05`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Authentication::Validation::FindProviderForUser(
        struct Windows::System::IUser *a1,
        HSTRING a2,
        HSTRING a3,
        struct Windows::Security::Credentials::IWebAccountProvider **a4)
{
  int v8; // eax
  int v9; // ebx
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall **v13)(_QWORD, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v14)(_QWORD, HSTRING, int *); // rbx
  int v15; // eax
  __int64 (__fastcall *v16)(_QWORD, _QWORD, _QWORD); // rbx
  int v17; // eax
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v19)(_QWORD, GUID *, __int64 *); // rdi
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, HSTRING, HSTRING, struct Windows::System::IUser *); // rbx
  __int64 v24; // rdi
  struct Windows::Security::Credentials::IWebAccountProvider *v25; // rax
  int *v27; // [rsp+20h] [rbp-60h]
  int v28[2]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v29; // [rsp+38h] [rbp-48h] BYREF
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-40h] BYREF
  _QWORD v31[2]; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  __int64 v33; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v31[0] = 0;
  v30 = 0;
  *(_QWORD *)v28 = 0;
  v31[1] = 0;
  v33 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
    0x46u,
    0x45u);
  v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(
         v33,
         &v30);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = (unsigned int)v8;
    v11 = 138;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\enduser\\NUI\\OneCore\\common\\include\\EnterpriseAttached.h",
      (const char *)v10,
      (int)v27);
    goto LABEL_21;
  }
  if ( !a1 )
  {
    v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v30;
    v13 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v30;
    if ( a3 )
    {
      v16 = v13[12];
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v28);
      v17 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), HSTRING, HSTRING, int *))v16)(
              v12,
              a2,
              a3,
              v28);
      v9 = v17;
      if ( v17 < 0 )
      {
        v10 = (unsigned int)v17;
        v11 = 148;
        goto LABEL_20;
      }
    }
    else
    {
      v14 = (__int64 (__fastcall *)(_QWORD, HSTRING, int *))v13[11];
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v28);
      v15 = v14(v12, a2, v28);
      v9 = v15;
      if ( v15 < 0 )
      {
        v10 = (unsigned int)v15;
        v11 = 144;
        goto LABEL_20;
      }
    }
    goto LABEL_15;
  }
  v29 = 0;
  v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v30;
  v19 = **v30;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
  v20 = v19(v18, &GUID_f584184a_8b57_4820_b6a4_70a5b6fcf44a, &v29);
  v9 = v20;
  if ( v20 < 0 )
  {
    v21 = 154;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecoreuap\\enduser\\NUI\\OneCore\\common\\include\\EnterpriseAttached.h",
      (const char *)(unsigned int)v20,
      (int)v27);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
    goto LABEL_21;
  }
  v22 = v29;
  v23 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, struct Windows::System::IUser *))(*(_QWORD *)v29 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v28);
  v27 = v28;
  v20 = v23(v22, a2, a3, a1);
  v9 = v20;
  if ( v20 < 0 )
  {
    v21 = 155;
    goto LABEL_11;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
LABEL_15:
  v24 = *(_QWORD *)v28;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v31);
  v9 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(v24);
  if ( v9 < 0 || (v9 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v24 + 64LL))(v24, v31), v9 < 0) )
  {
    v10 = (unsigned int)v9;
    v11 = 158;
    goto LABEL_20;
  }
  v25 = (struct Windows::Security::Credentials::IWebAccountProvider *)v31[0];
  v9 = 0;
  if ( v31[0] )
  {
    v31[0] = 0;
    *a4 = v25;
  }
LABEL_21:
  WindowsDeleteString(0);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v28);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v31);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400159a4  push    rbp
0x1400159a6  push    rbx
0x1400159a7  push    rsi
0x1400159a8  push    rdi
0x1400159a9  push    r12
0x1400159ab  push    r14
0x1400159ad  push    r15
0x1400159af  mov     rbp, rsp
0x1400159b2  sub     rsp, 80h
0x1400159b9  mov     rax, cs:__security_cookie
0x1400159c0  xor     rax, rsp
0x1400159c3  mov     [rbp+var_8], rax
0x1400159c7  mov     r12, r9
0x1400159ca  mov     rsi, r8
0x1400159cd  mov     r15, rdx
0x1400159d0  mov     r14, rcx
0x1400159d3  mov     [rbp+var_38], 0
0x1400159db  mov     [rbp+var_40], 0
0x1400159e3  mov     qword ptr [rbp+var_50], 0
0x1400159eb  mov     [rbp+var_30], 0
0x1400159f3  mov     [rbp+var_10], 0
0x1400159fb  mov     r9d, 45h ; 'E'; unsigned int
0x140015a01  lea     r8d, [r9+1]; unsigned int
0x140015a05  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x140015a0c  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x140015a10  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140015a15  lea     rdx, [rbp+var_40]
0x140015a19  mov     rcx, [rbp+var_10]
0x140015a1d  call    ??$GetActivationFactory@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>)
0x140015a22  mov     ebx, eax
0x140015a24  test    eax, eax
0x140015a26  jns     short loc_140015A35
0x140015a28  mov     r9d, eax
0x140015a2b  mov     edx, 8Ah
0x140015a30  jmp     loc_140015BA7
0x140015a35  test    r14, r14
0x140015a38  jnz     short loc_140015AB1
0x140015a3a  mov     rdi, [rbp+var_40]
0x140015a3e  lea     rcx, [rbp+var_50]
0x140015a42  mov     rax, [rdi]
0x140015a45  test    rsi, rsi
0x140015a48  jnz     short loc_140015A7C
0x140015a4a  mov     rbx, [rax+58h]
0x140015a4e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140015a53  lea     r8, [rbp+var_50]
0x140015a57  mov     rdx, r15
0x140015a5a  mov     rcx, rdi
0x140015a5d  mov     rax, rbx
0x140015a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015a65  mov     ebx, eax
0x140015a67  test    eax, eax
0x140015a69  jns     loc_140015B56
0x140015a6f  mov     r9d, eax
0x140015a72  mov     edx, 90h
0x140015a77  jmp     loc_140015BA7
0x140015a7c  mov     rbx, [rax+60h]
0x140015a80  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140015a85  lea     r9, [rbp+var_50]
0x140015a89  mov     r8, rsi
0x140015a8c  mov     rdx, r15
0x140015a8f  mov     rcx, rdi
0x140015a92  mov     rax, rbx
0x140015a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015a9a  mov     ebx, eax
0x140015a9c  test    eax, eax
0x140015a9e  jns     loc_140015B56
0x140015aa4  mov     r9d, eax
0x140015aa7  mov     edx, 94h
0x140015aac  jmp     loc_140015BA7
0x140015ab1  mov     [rbp+var_48], 0
0x140015ab9  mov     rbx, [rbp+var_40]
0x140015abd  mov     rax, [rbx]
0x140015ac0  mov     rdi, [rax]
0x140015ac3  lea     rcx, [rbp+var_48]
0x140015ac7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140015acc  lea     r8, [rbp+var_48]
0x140015ad0  lea     rdx, _GUID_f584184a_8b57_4820_b6a4_70a5b6fcf44a
0x140015ad7  mov     rcx, rbx
0x140015ada  mov     rax, rdi
0x140015add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015ae2  mov     ebx, eax
0x140015ae4  test    eax, eax
0x140015ae6  jns     short loc_140015B0F
0x140015ae8  mov     edx, 9Ah; void *
0x140015aed  lea     r8, aOnecoreuapEndu_59; "onecoreuap\\enduser\\NUI\\OneCore\\comm"...
0x140015af4  mov     r9d, eax; char *
0x140015af7  mov     rcx, [rbp+38h]; this
0x140015afb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015b00  nop
0x140015b01  lea     rcx, [rbp+var_48]
0x140015b05  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140015b0a  jmp     loc_140015BB8
0x140015b0f  mov     rdi, [rbp+var_48]
0x140015b13  mov     rax, [rdi]
0x140015b16  mov     rbx, [rax+30h]
0x140015b1a  lea     rcx, [rbp+var_50]
0x140015b1e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140015b23  lea     rax, [rbp+var_50]
0x140015b27  mov     qword ptr [rsp+80h+var_60], rax; int
0x140015b2c  mov     r9, r14
0x140015b2f  mov     r8, rsi
0x140015b32  mov     rdx, r15
0x140015b35  mov     rcx, rdi
0x140015b38  mov     rax, rbx
0x140015b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015b40  mov     ebx, eax
0x140015b42  test    eax, eax
0x140015b44  jns     short loc_140015B4D
0x140015b46  mov     edx, 9Bh
0x140015b4b  jmp     short loc_140015AED
0x140015b4d  lea     rcx, [rbp+var_48]
0x140015b51  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140015b56  mov     rdi, qword ptr [rbp+var_50]
0x140015b5a  lea     rcx, [rbp+var_38]
0x140015b5e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140015b63  mov     rcx, rdi
0x140015b66  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)
0x140015b6b  mov     ebx, eax
0x140015b6d  test    eax, eax
0x140015b6f  js      short loc_140015B9F
0x140015b71  mov     rax, [rdi]
0x140015b74  lea     rdx, [rbp+var_38]
0x140015b78  mov     rcx, rdi
0x140015b7b  mov     rax, [rax+40h]
0x140015b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015b84  mov     ebx, eax
0x140015b86  test    eax, eax
0x140015b88  js      short loc_140015B9F
0x140015b8a  mov     rax, [rbp+var_38]
0x140015b8e  xor     ebx, ebx
0x140015b90  test    rax, rax
0x140015b93  jz      short loc_140015BB8
0x140015b95  mov     [rbp+var_38], rbx
0x140015b99  mov     [r12], rax
0x140015b9d  jmp     short loc_140015BB8
0x140015b9f  mov     r9d, ebx; char *
0x140015ba2  mov     edx, 9Eh; void *
0x140015ba7  lea     r8, aOnecoreuapEndu_59; "onecoreuap\\enduser\\NUI\\OneCore\\comm"...
0x140015bae  mov     rcx, [rbp+38h]; this
0x140015bb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015bb7  nop
0x140015bb8  xor     ecx, ecx; string
0x140015bba  call    cs:__imp_WindowsDeleteString
0x140015bc0  nop
0x140015bc1  lea     rcx, [rbp+var_50]
0x140015bc5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140015bca  nop
0x140015bcb  lea     rcx, [rbp+var_40]
0x140015bcf  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140015bd4  nop
0x140015bd5  lea     rcx, [rbp+var_38]
0x140015bd9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140015bde  mov     eax, ebx
0x140015be0  mov     rcx, [rbp+var_8]
0x140015be4  xor     rcx, rsp; StackCookie
0x140015be7  call    __security_check_cookie
0x140015bec  add     rsp, 80h
0x140015bf3  pop     r15
0x140015bf5  pop     r14
0x140015bf7  pop     r12
0x140015bf9  pop     rdi
0x140015bfa  pop     rsi
0x140015bfb  pop     rbx
0x140015bfc  pop     rbp
0x140015bfd  retn
```
