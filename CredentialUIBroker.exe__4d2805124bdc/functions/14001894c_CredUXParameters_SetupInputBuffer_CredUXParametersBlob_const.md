# CredUXParameters::_SetupInputBuffer(CredUXParametersBlob const *)

- ea: `0x14001894c`
- end: `0x1400189f8`
- name: `?_SetupInputBuffer@CredUXParameters@@AEAAJPEBUCredUXParametersBlob@@@Z`
- size: `172`
- prototype: `__int64 __fastcall(CredUXParameters *__hidden this, const struct CredUXParametersBlob *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140013ae4`

## callees

- `0x140003620`
- `0x140005c08`
- `0x14000e920`
- `0x1400136fc`
- `0x14001894c`

## string_xrefs

- `0x1400189cb`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::_SetupInputBuffer(CredUXParameters *this, const struct CredUXParametersBlob *a2)
{
  __int64 v2; // r8
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-38h] BYREF
  GUID v8; // [rsp+24h] [rbp-34h]
  int v9; // [rsp+34h] [rbp-24h]
  __int64 v10; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = *((_QWORD *)a2 + 5);
  if ( v2 )
  {
    v9 = *((_DWORD *)a2 + 12);
    v10 = v2;
  }
  else
  {
    v9 = 0;
    v10 = 0;
  }
  v7 = **((_DWORD **)a2 + 4);
  v8 = GUID_NULL;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 144);
  v4 = Microsoft::WRL::Details::MakeAndInitialize<CCredentialProviderSerialization,ICredProviderCredentialSerialization,_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION &>(
         (char *)this + 144,
         &v7);
  v5 = v4;
  if ( v4 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x21F,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
    (const char *)(unsigned int)v4,
    v7);
  return v5;
}

```

## disassembly

```asm
0x14001894c  push    rbx
0x14001894e  sub     rsp, 50h
0x140018952  mov     rax, cs:__security_cookie
0x140018959  xor     rax, rsp
0x14001895c  mov     [rsp+58h+var_18], rax
0x140018961  mov     r8, [rdx+28h]
0x140018965  mov     rbx, rcx
0x140018968  test    r8, r8
0x14001896b  jz      short loc_14001897B
0x14001896d  mov     eax, [rdx+30h]
0x140018970  mov     [rsp+58h+var_24], eax
0x140018974  mov     [rsp+58h+var_20], r8
0x140018979  jmp     short loc_14001898C
0x14001897b  mov     [rsp+58h+var_24], 0
0x140018983  mov     [rsp+58h+var_20], 0
0x14001898c  mov     rax, [rdx+20h]
0x140018990  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140018997  mov     ecx, [rax]
0x140018999  mov     [rsp+58h+var_38], ecx; int
0x14001899d  lea     rcx, [rbx+90h]
0x1400189a4  movdqu  [rsp+58h+var_34], xmm0
0x1400189aa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400189af  lea     rdx, [rsp+58h+var_38]
0x1400189b4  lea     rcx, [rbx+90h]
0x1400189bb  call    ??$MakeAndInitialize@VCCredentialProviderSerialization@@UICredProviderCredentialSerialization@@AEAU_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION@@@Details@WRL@Microsoft@@YAJPEAPEAUICredProviderCredentialSerialization@@AEAU_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CCredentialProviderSerialization,ICredProviderCredentialSerialization,_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION &>(ICredProviderCredentialSerialization * *,_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION &)
0x1400189c0  mov     ebx, eax
0x1400189c2  test    eax, eax
0x1400189c4  jns     short loc_1400189E3
0x1400189c6  mov     rcx, [rsp+58h]; this
0x1400189cb  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x1400189d2  mov     r9d, eax; char *
0x1400189d5  mov     edx, 21Fh; void *
0x1400189da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400189df  mov     eax, ebx
0x1400189e1  jmp     short loc_1400189E5
0x1400189e3  xor     eax, eax
0x1400189e5  mov     rcx, [rsp+58h+var_18]
0x1400189ea  xor     rcx, rsp; StackCookie
0x1400189ed  call    __security_check_cookie
0x1400189f2  add     rsp, 50h
0x1400189f6  pop     rbx
0x1400189f7  retn
```
