# MsixPackage::Provisioning::Library::MsixProvisioningManager::IsHttpUriScheme(ushort const *,int *)

- ea: `0x180038b98`
- end: `0x180038d4c`
- name: `?IsHttpUriScheme@MsixProvisioningManager@Library@Provisioning@MsixPackage@@AEAAJPEBGPEAH@Z`
- size: `436`
- prototype: `int(MsixPackage::Provisioning::Library::MsixProvisioningManager *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180038ac0`

## callees

- `0x18000cfe8`
- `0x18001bf0c`
- `0x180038b98`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180038ca8`
- `msvcrt!_wcsicmp` at `0x180038cca`
- `msvcrt!_wcsicmp` at `0x180038ca8`
- `msvcrt!_wcsicmp` at `0x180038cca`
- `msvcrt!??3@YAXPEAX@Z` at `0x180038ce7`
- `msvcrt!??3@YAXPEAX@Z` at `0x180038ce7`
- `OLEAUT32!__imp_SysFreeString` at `0x180038c30`
- `OLEAUT32!__imp_SysFreeString` at `0x180038d06`
- `OLEAUT32!__imp_SysFreeString` at `0x180038c30`
- `OLEAUT32!__imp_SysFreeString` at `0x180038d06`
- `urlmon!CreateUri` at `0x180038bd5`
- `urlmon!CreateUri` at `0x180038bd5`

## string_xrefs

- `0x180038c14`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningManager::IsHttpUriScheme(
        MsixPackage::Provisioning::Library::MsixProvisioningManager *this,
        const unsigned __int16 *a2,
        int *a3)
{
  struct IUriVtbl *lpVtbl; // rax
  int v5; // eax
  unsigned int v6; // ebx
  unsigned __int64 v8; // r8
  const wchar_t *v9; // rcx
  const wchar_t *v10; // rcx
  BSTR bstrString; // [rsp+20h] [rbp-48h] BYREF
  IUri *v12; // [rsp+28h] [rbp-40h] BYREF
  wchar_t *String1[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v14; // [rsp+40h] [rbp-28h]
  unsigned __int64 v15; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a3 = 0;
  v12 = 0;
  if ( CreateUri(a2, 0x12900u, 0, &v12) >= 0 )
  {
    bstrString = 0;
    lpVtbl = v12->lpVtbl;
    bstrString = 0;
    v5 = ((__int64 (__fastcall *)(IUri *, BSTR *))lpVtbl->GetSchemeName)(v12, &bstrString);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E2,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
        (const char *)(unsigned int)v5,
        (int)bstrString);
      if ( bstrString )
        SysFreeString(bstrString);
      if ( v12 )
        ((void (__fastcall *)(IUri *))v12->lpVtbl->Release)(v12);
      return v6;
    }
    v15 = 7;
    v14 = 0;
    LOWORD(String1[0]) = 0;
    if ( *bstrString )
    {
      v8 = -1;
      do
        ++v8;
      while ( bstrString[v8] );
    }
    else
    {
      v8 = 0;
    }
    std::wstring::assign(String1, (char *)bstrString, v8);
    v9 = (const wchar_t *)String1;
    if ( v15 >= 8 )
      v9 = String1[0];
    if ( !_wcsicmp(v9, L"http") )
      goto LABEL_18;
    v10 = (const wchar_t *)String1;
    if ( v15 >= 8 )
      v10 = String1[0];
    if ( !_wcsicmp(v10, L"https") )
LABEL_18:
      *a3 = 1;
    if ( v15 >= 8 )
      operator delete(String1[0]);
    v15 = 7;
    v14 = 0;
    LOWORD(String1[0]) = 0;
    if ( bstrString )
      SysFreeString(bstrString);
  }
  if ( v12 )
    ((void (__fastcall *)(IUri *))v12->lpVtbl->Release)(v12);
  return 0;
}

```

## disassembly

```asm
0x180038b98  mov     r11, rsp
0x180038b9b  mov     [r11+8], rbx
0x180038b9f  mov     [r11+20h], rsi
0x180038ba3  push    rdi
0x180038ba4  sub     rsp, 60h
0x180038ba8  mov     rax, cs:__security_cookie
0x180038baf  xor     rax, rsp
0x180038bb2  mov     [rsp+68h+var_18], rax
0x180038bb7  mov     rdi, r8
0x180038bba  mov     rax, rdx
0x180038bbd  xor     esi, esi
0x180038bbf  mov     [r8], esi
0x180038bc2  mov     [r11-40h], rsi
0x180038bc6  lea     r9, [r11-40h]; ppURI
0x180038bca  xor     r8d, r8d; dwReserved
0x180038bcd  mov     edx, 12900h; dwFlags
0x180038bd2  mov     rcx, rax; pwzURI
0x180038bd5  call    cs:__imp_CreateUri
0x180038bdb  test    eax, eax
0x180038bdd  js      loc_180038D0D
0x180038be3  mov     [rsp+68h+bstrString], rsi
0x180038be8  mov     rcx, [rsp+68h+var_40]
0x180038bed  mov     rax, [rcx]
0x180038bf0  mov     [rsp+68h+bstrString], rsi; int
0x180038bf5  lea     rdx, [rsp+68h+bstrString]
0x180038bfa  mov     rax, [rax+98h]
0x180038c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c06  mov     ebx, eax
0x180038c08  test    eax, eax
0x180038c0a  jns     short loc_180038C55
0x180038c0c  mov     rcx, [rsp+68h]; this
0x180038c11  mov     r9d, eax; char *
0x180038c14  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180038c1b  mov     edx, 2E2h; void *
0x180038c20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038c25  nop
0x180038c26  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180038c2b  test    rcx, rcx
0x180038c2e  jz      short loc_180038C37
0x180038c30  call    cs:__imp_SysFreeString
0x180038c36  nop
0x180038c37  mov     rcx, [rsp+68h+var_40]
0x180038c3c  test    rcx, rcx
0x180038c3f  jz      short loc_180038C4E
0x180038c41  mov     rax, [rcx]
0x180038c44  mov     rax, [rax+10h]
0x180038c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c4d  nop
0x180038c4e  mov     eax, ebx
0x180038c50  jmp     loc_180038D2C
0x180038c55  mov     ebx, 7
0x180038c5a  mov     [rsp+68h+var_20], rbx
0x180038c5f  mov     [rsp+68h+var_28], rsi
0x180038c64  mov     word ptr [rsp+68h+String1], si
0x180038c69  mov     rdx, [rsp+68h+bstrString]; Src
0x180038c6e  cmp     [rdx], si
0x180038c71  jnz     short loc_180038C78
0x180038c73  mov     r8, rsi
0x180038c76  jmp     short loc_180038C86
0x180038c78  or      r8, 0FFFFFFFFFFFFFFFFh
0x180038c7c  inc     r8
0x180038c7f  cmp     [rdx+r8*2], si
0x180038c84  jnz     short loc_180038C7C
0x180038c86  lea     rcx, [rsp+68h+String1]; void *
0x180038c8b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180038c90  lea     rcx, [rsp+68h+String1]
0x180038c95  cmp     [rsp+68h+var_20], 8
0x180038c9b  cmovnb  rcx, [rsp+68h+String1]; String1
0x180038ca1  lea     rdx, aHttp; "http"
0x180038ca8  call    cs:__imp__wcsicmp
0x180038cae  test    eax, eax
0x180038cb0  jz      short loc_180038CD4
0x180038cb2  lea     rcx, [rsp+68h+String1]
0x180038cb7  cmp     [rsp+68h+var_20], 8
0x180038cbd  cmovnb  rcx, [rsp+68h+String1]; String1
0x180038cc3  lea     rdx, aHttps; "https"
0x180038cca  call    cs:__imp__wcsicmp
0x180038cd0  test    eax, eax
0x180038cd2  jnz     short loc_180038CDA
0x180038cd4  mov     dword ptr [rdi], 1
0x180038cda  cmp     [rsp+68h+var_20], 8
0x180038ce0  jb      short loc_180038CED
0x180038ce2  mov     rcx, [rsp+68h+String1]
0x180038ce7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180038ced  mov     [rsp+68h+var_20], rbx
0x180038cf2  mov     [rsp+68h+var_28], rsi
0x180038cf7  mov     word ptr [rsp+68h+String1], si
0x180038cfc  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180038d01  test    rcx, rcx
0x180038d04  jz      short loc_180038D0D
0x180038d06  call    cs:__imp_SysFreeString
0x180038d0c  nop
0x180038d0d  mov     rcx, [rsp+68h+var_40]
0x180038d12  test    rcx, rcx
0x180038d15  jz      short loc_180038D24
0x180038d17  mov     rax, [rcx]
0x180038d1a  mov     rax, [rax+10h]
0x180038d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d23  nop
0x180038d24  xor     eax, eax
0x180038d26  jmp     short loc_180038D2C
0x180038d28  mov     eax, dword ptr [rsp+68h+bstrString]
0x180038d2c  mov     rcx, [rsp+68h+var_18]
0x180038d31  xor     rcx, rsp; StackCookie
0x180038d34  call    __security_check_cookie
0x180038d39  lea     r11, [rsp+68h+var_8]
0x180038d3e  mov     rbx, [r11+10h]
0x180038d42  mov     rsi, [r11+28h]
0x180038d46  mov     rsp, r11
0x180038d49  pop     rdi
0x180038d4a  retn
```
