# ParseIdentityData(HSTRING__ *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *,_GUID *)

- ea: `0x18011b84c`
- end: `0x18011bb04`
- name: `?ParseIdentityData@@YAJPEAUHSTRING__@@PEAPEAU1@11PEAU_GUID@@@Z`
- size: `696`
- prototype: `__int64 __usercall@<rax>(HSTRING@<rcx>, HSTRING *@<rdx>, HSTRING *@<r8>, HSTRING *@<r9>, struct _GUID *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18007d7fc`
- `0x1800843f0`
- `0x1800fa5b8`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x1800252e8`
- `0x1800d5db4`
- `0x1800db560`
- `0x18011b84c`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011b8f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011b953`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011b9ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011ba09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011ba69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011bac0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011bace`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011badc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011b8f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011b953`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011b9ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011ba09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011ba69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011bac0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011bace`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011badc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011ba51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011ba51`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ParseIdentityData(HSTRING a1, HSTRING *a2, HSTRING *a3, HSTRING *a4, struct _GUID *a5)
{
  int v9; // ebx
  struct Windows::Data::Json::IJsonObject *v10; // rdi
  __int64 (__fastcall *v11)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *); // rbx
  struct Windows::Data::Json::IJsonObject *v12; // rdi
  __int64 (__fastcall *v13)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *); // rbx
  struct Windows::Data::Json::IJsonObject *v14; // rdi
  __int64 (__fastcall *v15)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *); // rbx
  struct Windows::Data::Json::IJsonObject *v16; // rdi
  __int64 (__fastcall *v17)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  HSTRING v19; // rax
  HSTRING v20; // rax
  HSTRING v21; // rax
  struct Windows::Data::Json::IJsonObject *v23; // [rsp+20h] [rbp-51h] BYREF
  HSTRING v24; // [rsp+28h] [rbp-49h] BYREF
  HSTRING v25; // [rsp+30h] [rbp-41h] BYREF
  HSTRING string; // [rsp+38h] [rbp-39h] BYREF
  HSTRING v27; // [rsp+40h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-29h] BYREF
  __int64 v29; // [rsp+60h] [rbp-11h]
  struct _GUID v30; // [rsp+68h] [rbp-9h] BYREF

  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  string = 0;
  v25 = 0;
  v24 = 0;
  v30 = GUID_NULL;
  v23 = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v23);
  v9 = Json_Parse(a1, &v23);
  if ( v9 >= 0 )
  {
    if ( !a2
      || (v10 = v23,
          v11 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *))(*(_QWORD *)v23 + 80LL),
          WindowsDeleteString(string),
          string = 0,
          v29 = 0,
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"WebAccountId", 0xDu, 0xCu),
          v9 = v11(v10, v29, &string),
          v9 >= 0) )
    {
      if ( !a3
        || (v12 = v23,
            v13 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *))(*(_QWORD *)v23 + 80LL),
            WindowsDeleteString(v25),
            v25 = 0,
            v29 = 0,
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
              &hstringHeader,
              L"AccountProviderId",
              0x12u,
              0x11u),
            v9 = v13(v12, v29, &v25),
            v9 >= 0) )
      {
        if ( !a4
          || (v14 = v23,
              v15 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *))(*(_QWORD *)v23 + 80LL),
              WindowsDeleteString(v24),
              v24 = 0,
              v29 = 0,
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Authority", 0xAu, 9u),
              v9 = v15(v14, v29, &v24),
              v9 >= 0) )
        {
          if ( !a5 )
            goto LABEL_20;
          v27 = 0;
          v16 = v23;
          v17 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *))(*(_QWORD *)v23 + 80LL);
          WindowsDeleteString(0);
          v27 = 0;
          v29 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"ConnectedAccountProvider",
            0x19u,
            0x18u);
          v9 = v17(v16, v29, &v27);
          if ( v9 >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(v27, 0);
            v9 = GuidFromString(StringRawBuffer, &v30);
          }
          WindowsDeleteString(v27);
          if ( v9 >= 0 )
          {
LABEL_20:
            if ( a2 )
            {
              v19 = string;
              string = 0;
              *a2 = v19;
            }
            if ( a3 )
            {
              v20 = v25;
              v25 = 0;
              *a3 = v20;
            }
            if ( a4 )
            {
              v21 = v24;
              v24 = 0;
              *a4 = v21;
            }
            if ( a5 )
              *a5 = v30;
          }
        }
      }
    }
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v23);
  WindowsDeleteString(v24);
  v24 = 0;
  WindowsDeleteString(v25);
  v25 = 0;
  WindowsDeleteString(string);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18011b84c  push    rbp
0x18011b84e  push    rbx
0x18011b84f  push    rsi
0x18011b850  push    rdi
0x18011b851  push    r12
0x18011b853  push    r13
0x18011b855  push    r14
0x18011b857  push    r15
0x18011b859  lea     rbp, [rsp-17h]
0x18011b85e  sub     rsp, 88h
0x18011b865  mov     rax, cs:__security_cookie
0x18011b86c  xor     rax, rsp
0x18011b86f  mov     [rbp+4Fh+var_48], rax
0x18011b873  mov     rsi, r9
0x18011b876  mov     r14, r8
0x18011b879  mov     r12, rdx
0x18011b87c  mov     rbx, rcx
0x18011b87f  mov     r15, [rbp+4Fh+arg_20]
0x18011b883  xor     r13d, r13d
0x18011b886  test    rdx, rdx
0x18011b889  jz      short loc_18011B88E
0x18011b88b  mov     [rdx], r13
0x18011b88e  test    r14, r14
0x18011b891  jz      short loc_18011B896
0x18011b893  mov     [r8], r13
0x18011b896  test    rsi, rsi
0x18011b899  jz      short loc_18011B89E
0x18011b89b  mov     [r9], r13
0x18011b89e  test    r15, r15
0x18011b8a1  jz      short loc_18011B8AA
0x18011b8a3  xorps   xmm0, xmm0
0x18011b8a6  movups  xmmword ptr [r15], xmm0
0x18011b8aa  mov     [rbp+4Fh+string], r13
0x18011b8ae  mov     [rbp+4Fh+var_90], r13
0x18011b8b2  mov     [rbp+4Fh+var_98], r13
0x18011b8b6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18011b8bd  movdqu  xmmword ptr [rbp+4Fh+var_58.Data1], xmm0
0x18011b8c2  mov     [rbp+4Fh+var_A0], r13
0x18011b8c6  lea     rcx, [rbp+4Fh+var_A0]
0x18011b8ca  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18011b8cf  lea     rdx, [rbp+4Fh+var_A0]; struct Windows::Data::Json::IJsonObject **
0x18011b8d3  mov     rcx, rbx; HSTRING
0x18011b8d6  call    ?Json_Parse@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@Windows@@@Z; Json_Parse(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18011b8db  mov     ebx, eax
0x18011b8dd  test    eax, eax
0x18011b8df  js      loc_18011BAB2
0x18011b8e5  test    r12, r12
0x18011b8e8  jz      short loc_18011B93F
0x18011b8ea  mov     rdi, [rbp+4Fh+var_A0]
0x18011b8ee  mov     rax, [rdi]
0x18011b8f1  mov     rbx, [rax+50h]
0x18011b8f5  mov     rcx, [rbp+4Fh+string]; string
0x18011b8f9  call    cs:__imp_WindowsDeleteString
0x18011b8ff  mov     [rbp+4Fh+string], r13
0x18011b903  mov     [rbp+4Fh+var_60], r13
0x18011b907  mov     r9d, 0Ch; unsigned int
0x18011b90d  lea     r8d, [r9+1]; unsigned int
0x18011b911  lea     rdx, aWebaccountid; "WebAccountId"
0x18011b918  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x18011b91c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18011b921  nop
0x18011b922  lea     r8, [rbp+4Fh+string]
0x18011b926  mov     rdx, [rbp+4Fh+var_60]
0x18011b92a  mov     rcx, rdi
0x18011b92d  mov     rax, rbx
0x18011b930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011b935  mov     ebx, eax
0x18011b937  test    eax, eax
0x18011b939  js      loc_18011BAB2
0x18011b93f  test    r14, r14
0x18011b942  jz      short loc_18011B999
0x18011b944  mov     rdi, [rbp+4Fh+var_A0]
0x18011b948  mov     rax, [rdi]
0x18011b94b  mov     rbx, [rax+50h]
0x18011b94f  mov     rcx, [rbp+4Fh+var_90]; string
0x18011b953  call    cs:__imp_WindowsDeleteString
0x18011b959  mov     [rbp+4Fh+var_90], r13
0x18011b95d  mov     [rbp+4Fh+var_60], r13
0x18011b961  mov     r9d, 11h; unsigned int
0x18011b967  lea     r8d, [r9+1]; unsigned int
0x18011b96b  lea     rdx, aAccountprovide; "AccountProviderId"
0x18011b972  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x18011b976  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18011b97b  nop
0x18011b97c  lea     r8, [rbp+4Fh+var_90]
0x18011b980  mov     rdx, [rbp+4Fh+var_60]
0x18011b984  mov     rcx, rdi
0x18011b987  mov     rax, rbx
0x18011b98a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011b98f  mov     ebx, eax
0x18011b991  test    eax, eax
0x18011b993  js      loc_18011BAB2
0x18011b999  test    rsi, rsi
0x18011b99c  jz      short loc_18011B9F3
0x18011b99e  mov     rdi, [rbp+4Fh+var_A0]
0x18011b9a2  mov     rax, [rdi]
0x18011b9a5  mov     rbx, [rax+50h]
0x18011b9a9  mov     rcx, [rbp+4Fh+var_98]; string
0x18011b9ad  call    cs:__imp_WindowsDeleteString
0x18011b9b3  mov     [rbp+4Fh+var_98], r13
0x18011b9b7  mov     [rbp+4Fh+var_60], r13
0x18011b9bb  mov     r9d, 9; unsigned int
0x18011b9c1  lea     r8d, [r9+1]; unsigned int
0x18011b9c5  lea     rdx, aAuthority; "Authority"
0x18011b9cc  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x18011b9d0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18011b9d5  nop
0x18011b9d6  lea     r8, [rbp+4Fh+var_98]
0x18011b9da  mov     rdx, [rbp+4Fh+var_60]
0x18011b9de  mov     rcx, rdi
0x18011b9e1  mov     rax, rbx
0x18011b9e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011b9e9  mov     ebx, eax
0x18011b9eb  test    eax, eax
0x18011b9ed  js      loc_18011BAB2
0x18011b9f3  test    r15, r15
0x18011b9f6  jz      short loc_18011BA73
0x18011b9f8  mov     [rbp+4Fh+var_80], r13
0x18011b9fc  mov     rdi, [rbp+4Fh+var_A0]
0x18011ba00  mov     rax, [rdi]
0x18011ba03  mov     rbx, [rax+50h]
0x18011ba07  xor     ecx, ecx; string
0x18011ba09  call    cs:__imp_WindowsDeleteString
0x18011ba0f  mov     [rbp+4Fh+var_80], r13
0x18011ba13  mov     [rbp+4Fh+var_60], r13
0x18011ba17  mov     r9d, 18h; unsigned int
0x18011ba1d  lea     r8d, [r9+1]; unsigned int
0x18011ba21  lea     rdx, aConnectedaccou; "ConnectedAccountProvider"
0x18011ba28  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x18011ba2c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18011ba31  nop
0x18011ba32  lea     r8, [rbp+4Fh+var_80]
0x18011ba36  mov     rdx, [rbp+4Fh+var_60]
0x18011ba3a  mov     rcx, rdi
0x18011ba3d  mov     rax, rbx
0x18011ba40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011ba45  mov     ebx, eax
0x18011ba47  test    eax, eax
0x18011ba49  js      short loc_18011BA65
0x18011ba4b  xor     edx, edx; length
0x18011ba4d  mov     rcx, [rbp+4Fh+var_80]; string
0x18011ba51  call    cs:__imp_WindowsGetStringRawBuffer
0x18011ba57  lea     rdx, [rbp+4Fh+var_58]; struct _GUID *
0x18011ba5b  mov     rcx, rax; unsigned __int16 *
0x18011ba5e  call    ?GuidFromString@@YAJPEBGPEAU_GUID@@@Z; GuidFromString(ushort const *,_GUID *)
0x18011ba63  mov     ebx, eax
0x18011ba65  mov     rcx, [rbp+4Fh+var_80]; string
0x18011ba69  call    cs:__imp_WindowsDeleteString
0x18011ba6f  test    ebx, ebx
0x18011ba71  js      short loc_18011BAB2
0x18011ba73  test    r12, r12
0x18011ba76  jz      short loc_18011BA84
0x18011ba78  mov     rax, [rbp+4Fh+string]
0x18011ba7c  mov     [rbp+4Fh+string], r13
0x18011ba80  mov     [r12], rax
0x18011ba84  test    r14, r14
0x18011ba87  jz      short loc_18011BA94
0x18011ba89  mov     rax, [rbp+4Fh+var_90]
0x18011ba8d  mov     [rbp+4Fh+var_90], r13
0x18011ba91  mov     [r14], rax
0x18011ba94  test    rsi, rsi
0x18011ba97  jz      short loc_18011BAA4
0x18011ba99  mov     rax, [rbp+4Fh+var_98]
0x18011ba9d  mov     [rbp+4Fh+var_98], r13
0x18011baa1  mov     [rsi], rax
0x18011baa4  test    r15, r15
0x18011baa7  jz      short loc_18011BAB2
0x18011baa9  movups  xmm0, xmmword ptr [rbp+4Fh+var_58.Data1]
0x18011baad  movdqu  xmmword ptr [r15], xmm0
0x18011bab2  lea     rcx, [rbp+4Fh+var_A0]
0x18011bab6  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18011babb  nop
0x18011babc  mov     rcx, [rbp+4Fh+var_98]; string
0x18011bac0  call    cs:__imp_WindowsDeleteString
0x18011bac6  mov     [rbp+4Fh+var_98], r13
0x18011baca  mov     rcx, [rbp+4Fh+var_90]; string
0x18011bace  call    cs:__imp_WindowsDeleteString
0x18011bad4  mov     [rbp+4Fh+var_90], r13
0x18011bad8  mov     rcx, [rbp+4Fh+string]; string
0x18011badc  call    cs:__imp_WindowsDeleteString
0x18011bae2  mov     eax, ebx
0x18011bae4  mov     rcx, [rbp+4Fh+var_48]
0x18011bae8  xor     rcx, rsp; StackCookie
0x18011baeb  call    __security_check_cookie
0x18011baf0  add     rsp, 88h
0x18011baf7  pop     r15
0x18011baf9  pop     r14
0x18011bafb  pop     r13
0x18011bafd  pop     r12
0x18011baff  pop     rdi
0x18011bb00  pop     rsi
0x18011bb01  pop     rbx
0x18011bb02  pop     rbp
0x18011bb03  retn
```
