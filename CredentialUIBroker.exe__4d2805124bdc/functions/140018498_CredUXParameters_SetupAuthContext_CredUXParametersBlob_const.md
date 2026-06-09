# CredUXParameters::_SetupAuthContext(CredUXParametersBlob const *)

- ea: `0x140018498`
- end: `0x1400186b9`
- name: `?_SetupAuthContext@CredUXParameters@@AEAAJPEBUCredUXParametersBlob@@@Z`
- size: `545`
- prototype: `__int64 __fastcall(CredUXParameters *__hidden this, const struct CredUXParametersBlob *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140013ae4`

## callees

- `0x140003620`
- `0x14000b47c`
- `0x14000e920`
- `0x1400136fc`
- `0x140018498`
- `0x14001e060`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140018510`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140018510`

## string_xrefs

- `0x140018520`: `shellcommon\internal\shell\inc\creduxparameters.h`
- `0x140018571`: `shellcommon\internal\shell\inc\creduxparameters.h`
- `0x140018622`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::_SetupAuthContext(CredUXParameters *this, const struct CredUXParametersBlob *a2)
{
  __int64 v2; // rsi
  __int64 v4; // rbx
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64 *); // rbx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v13; // rcx
  __int64 v14; // [rsp+20h] [rbp-50h] BYREF
  __int64 v15; // [rsp+28h] [rbp-48h] BYREF
  __int64 v16; // [rsp+30h] [rbp-40h] BYREF
  void *v17; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v19; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v2 = *((_QWORD *)a2 + 2);
  if ( v2 )
  {
    v16 = 0;
    v19 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Storage.Streams.Buffer",
      0x1Fu,
      0x1Eu);
    v4 = v19;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    ActivationFactory = RoGetActivationFactory(v4, &GUID_71af914d_c10f_484b_bc50_14bc623b3a27, &v16);
    v6 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x229,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
        (const char *)(unsigned int)ActivationFactory,
        v14);
LABEL_15:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
      return v6;
    }
    v7 = v16;
    v14 = 0;
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    v9 = v8(v7, *(unsigned int *)(v2 + 64), &v14);
    v6 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22C,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
        (const char *)(unsigned int)v9,
        v14);
LABEL_14:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
      goto LABEL_15;
    }
    v15 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
    v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v14)(
            v14,
            &GUID_905a0fef_bc53_11df_8c49_001e4fc686da,
            &v15);
    v6 = v10;
    if ( v10 < 0 )
    {
      v11 = 559;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
        (const char *)(unsigned int)v10,
        v14);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
      goto LABEL_14;
    }
    v17 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v15 + 24LL))(v15, &v17);
    v6 = v10;
    if ( v10 < 0 )
    {
      v11 = 562;
      goto LABEL_13;
    }
    memcpy_0(v17, *(const void **)(v2 + 56), *(unsigned int *)(v2 + 64));
    if ( *(_DWORD *)(v2 + 64) )
    {
      v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 64LL))(v14);
      v6 = v10;
      if ( v10 < 0 )
      {
        v11 = 567;
        goto LABEL_13;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 184);
      v13 = v14;
      if ( v14 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
        v13 = v14;
      }
      *((_QWORD *)this + 23) = v13;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  }
  return 0;
}

```

## disassembly

```asm
0x140018498  mov     [rsp-18h+arg_10], rbx
0x14001849d  mov     [rsp-18h+arg_18], rsi
0x1400184a2  push    rbp
0x1400184a3  push    rdi
0x1400184a4  push    r14
0x1400184a6  mov     rbp, rsp
0x1400184a9  sub     rsp, 70h
0x1400184ad  mov     rax, cs:__security_cookie
0x1400184b4  xor     rax, rsp
0x1400184b7  mov     [rbp+var_10], rax
0x1400184bb  mov     rsi, [rdx+10h]
0x1400184bf  mov     r14, rcx
0x1400184c2  test    rsi, rsi
0x1400184c5  jz      loc_140018696
0x1400184cb  mov     r9d, 1Eh; unsigned int
0x1400184d1  mov     [rbp+var_40], 0
0x1400184d9  lea     rdx, ?RuntimeClass_Windows_Storage_Streams_Buffer@@3QBGB; "Windows.Storage.Streams.Buffer"
0x1400184e0  mov     [rbp+var_18], 0
0x1400184e8  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1400184ec  lea     r8d, [r9+1]; unsigned int
0x1400184f0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400184f5  mov     rbx, [rbp+var_18]
0x1400184f9  lea     rcx, [rbp+var_40]
0x1400184fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140018502  lea     r8, [rbp+var_40]
0x140018506  mov     rcx, rbx
0x140018509  lea     rdx, _GUID_71af914d_c10f_484b_bc50_14bc623b3a27
0x140018510  call    cs:__imp_RoGetActivationFactory
0x140018516  mov     ebx, eax
0x140018518  test    eax, eax
0x14001851a  jns     short loc_140018539
0x14001851c  mov     rcx, [rbp+18h]; this
0x140018520  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x140018527  mov     r9d, eax; char *
0x14001852a  mov     edx, 229h; void *
0x14001852f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018534  jmp     loc_140018643
0x140018539  mov     rdi, [rbp+var_40]
0x14001853d  lea     rcx, [rbp+var_50]
0x140018541  mov     [rbp+var_50], 0
0x140018549  mov     rax, [rdi]
0x14001854c  mov     rbx, [rax+30h]
0x140018550  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140018555  mov     edx, [rsi+40h]
0x140018558  lea     r8, [rbp+var_50]
0x14001855c  mov     rcx, rdi
0x14001855f  mov     rax, rbx
0x140018562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018567  mov     ebx, eax
0x140018569  test    eax, eax
0x14001856b  jns     short loc_14001858A
0x14001856d  mov     rcx, [rbp+18h]; this
0x140018571  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x140018578  mov     r9d, eax; char *
0x14001857b  mov     edx, 22Ch; void *
0x140018580  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018585  jmp     loc_14001863A
0x14001858a  lea     rcx, [rbp+var_48]
0x14001858e  mov     [rbp+var_48], 0
0x140018596  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001859b  mov     rcx, [rbp+var_50]
0x14001859f  lea     r8, [rbp+var_48]
0x1400185a3  lea     rdx, _GUID_905a0fef_bc53_11df_8c49_001e4fc686da
0x1400185aa  mov     rax, [rcx]
0x1400185ad  mov     rax, [rax]
0x1400185b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400185b5  mov     ebx, eax
0x1400185b7  test    eax, eax
0x1400185b9  jns     short loc_1400185C2
0x1400185bb  mov     edx, 22Fh
0x1400185c0  jmp     short loc_14001861E
0x1400185c2  mov     rcx, [rbp+var_48]
0x1400185c6  lea     rdx, [rbp+var_38]
0x1400185ca  mov     [rbp+var_38], 0
0x1400185d2  mov     rax, [rcx]
0x1400185d5  mov     rax, [rax+18h]
0x1400185d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400185de  mov     ebx, eax
0x1400185e0  test    eax, eax
0x1400185e2  jns     short loc_1400185EB
0x1400185e4  mov     edx, 232h
0x1400185e9  jmp     short loc_14001861E
0x1400185eb  mov     r8d, [rsi+40h]; Size
0x1400185ef  mov     rdx, [rsi+38h]; Src
0x1400185f3  mov     rcx, [rbp+var_38]; void *
0x1400185f7  call    memcpy_0
0x1400185fc  mov     edx, [rsi+40h]
0x1400185ff  test    edx, edx
0x140018601  jz      short loc_14001867B
0x140018603  mov     rcx, [rbp+var_50]
0x140018607  mov     rax, [rcx]
0x14001860a  mov     rax, [rax+40h]
0x14001860e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018613  mov     ebx, eax
0x140018615  test    eax, eax
0x140018617  jns     short loc_140018650
0x140018619  mov     edx, 237h; void *
0x14001861e  mov     rcx, [rbp+18h]; this
0x140018622  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x140018629  mov     r9d, eax; char *
0x14001862c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018631  lea     rcx, [rbp+var_48]
0x140018635  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001863a  lea     rcx, [rbp+var_50]
0x14001863e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140018643  lea     rcx, [rbp+var_40]
0x140018647  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001864c  mov     eax, ebx
0x14001864e  jmp     short loc_140018698
0x140018650  lea     rbx, [r14+0B8h]
0x140018657  mov     rcx, rbx
0x14001865a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001865f  mov     rcx, [rbp+var_50]
0x140018663  test    rcx, rcx
0x140018666  jz      short loc_140018678
0x140018668  mov     rax, [rcx]
0x14001866b  mov     rax, [rax+8]
0x14001866f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018674  mov     rcx, [rbp+var_50]
0x140018678  mov     [rbx], rcx
0x14001867b  lea     rcx, [rbp+var_48]
0x14001867f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140018684  lea     rcx, [rbp+var_50]
0x140018688  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001868d  lea     rcx, [rbp+var_40]
0x140018691  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140018696  xor     eax, eax
0x140018698  mov     rcx, [rbp+var_10]
0x14001869c  xor     rcx, rsp; StackCookie
0x14001869f  call    __security_check_cookie
0x1400186a4  lea     r11, [rsp+70h+var_s0]
0x1400186a9  mov     rbx, [r11+30h]
0x1400186ad  mov     rsi, [r11+38h]
0x1400186b1  mov     rsp, r11
0x1400186b4  pop     r14
0x1400186b6  pop     rdi
0x1400186b7  pop     rbp
0x1400186b8  retn
```
