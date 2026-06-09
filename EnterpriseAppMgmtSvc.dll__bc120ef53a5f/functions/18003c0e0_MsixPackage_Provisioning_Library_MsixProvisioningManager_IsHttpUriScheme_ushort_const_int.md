# MsixPackage::Provisioning::Library::MsixProvisioningManager::IsHttpUriScheme(ushort const *,int *)

- ea: `0x18003c0e0`
- end: `0x18003c2b8`
- name: `?IsHttpUriScheme@MsixProvisioningManager@Library@Provisioning@MsixPackage@@AEAAJPEBGPEAH@Z`
- size: `472`
- prototype: `int(MsixPackage::Provisioning::Library::MsixProvisioningManager *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18003c008`

## callees

- `0x18000d3dc`
- `0x18001d160`
- `0x18003c0e0`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003c1fc`
- `msvcrt!_wcsicmp` at `0x18003c224`
- `msvcrt!_wcsicmp` at `0x18003c1fc`
- `msvcrt!_wcsicmp` at `0x18003c224`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003c247`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003c247`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c17e`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c26c`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c17e`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c26c`
- `urlmon!CreateUri` at `0x18003c11d`
- `urlmon!CreateUri` at `0x18003c11d`

## string_xrefs

- `0x18003c162`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`

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
  __int64 v8; // r8
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
    std::wstring::assign(String1, bstrString);
    v9 = (const wchar_t *)String1;
    if ( v15 >= 8 )
      v9 = String1[0];
    if ( !_wcsicmp(v9, L"http") )
      goto LABEL_17;
    v10 = (const wchar_t *)String1;
    if ( v15 >= 8 )
      v10 = String1[0];
    if ( !_wcsicmp(v10, L"https") )
LABEL_17:
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
0x18003c0e0  mov     r11, rsp
0x18003c0e3  mov     [r11+8], rbx
0x18003c0e7  mov     [r11+20h], rsi
0x18003c0eb  push    rdi
0x18003c0ec  sub     rsp, 60h
0x18003c0f0  mov     rax, cs:__security_cookie
0x18003c0f7  xor     rax, rsp
0x18003c0fa  mov     [rsp+68h+var_18], rax
0x18003c0ff  mov     rdi, r8
0x18003c102  mov     rax, rdx
0x18003c105  xor     esi, esi
0x18003c107  mov     [r8], esi
0x18003c10a  mov     [r11-40h], rsi
0x18003c10e  lea     r9, [r11-40h]; ppURI
0x18003c112  xor     r8d, r8d; dwReserved
0x18003c115  mov     edx, 12900h; dwFlags
0x18003c11a  mov     rcx, rax; pwzURI
0x18003c11d  call    cs:__imp_CreateUri
0x18003c124  nop     dword ptr [rax+rax+00h]
0x18003c129  test    eax, eax
0x18003c12b  js      loc_18003C279
0x18003c131  mov     [rsp+68h+bstrString], rsi
0x18003c136  mov     rcx, [rsp+68h+var_40]
0x18003c13b  mov     rax, [rcx]
0x18003c13e  mov     [rsp+68h+bstrString], rsi; int
0x18003c143  lea     rdx, [rsp+68h+bstrString]
0x18003c148  mov     rax, [rax+98h]
0x18003c14f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c154  mov     ebx, eax
0x18003c156  test    eax, eax
0x18003c158  jns     short loc_18003C1A9
0x18003c15a  mov     rcx, [rsp+68h]; this
0x18003c15f  mov     r9d, eax; char *
0x18003c162  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c169  mov     edx, 2E2h; void *
0x18003c16e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c173  nop
0x18003c174  mov     rcx, [rsp+68h+bstrString]; bstrString
0x18003c179  test    rcx, rcx
0x18003c17c  jz      short loc_18003C18B
0x18003c17e  call    cs:__imp_SysFreeString
0x18003c185  nop     dword ptr [rax+rax+00h]
0x18003c18a  nop
0x18003c18b  mov     rcx, [rsp+68h+var_40]
0x18003c190  test    rcx, rcx
0x18003c193  jz      short loc_18003C1A2
0x18003c195  mov     rax, [rcx]
0x18003c198  mov     rax, [rax+10h]
0x18003c19c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c1a1  nop
0x18003c1a2  mov     eax, ebx
0x18003c1a4  jmp     loc_18003C298
0x18003c1a9  mov     ebx, 7
0x18003c1ae  mov     [rsp+68h+var_20], rbx
0x18003c1b3  mov     [rsp+68h+var_28], rsi
0x18003c1b8  mov     word ptr [rsp+68h+String1], si
0x18003c1bd  mov     rdx, [rsp+68h+bstrString]; Src
0x18003c1c2  cmp     [rdx], si
0x18003c1c5  jnz     short loc_18003C1CC
0x18003c1c7  mov     r8, rsi
0x18003c1ca  jmp     short loc_18003C1DA
0x18003c1cc  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003c1d0  inc     r8
0x18003c1d3  cmp     [rdx+r8*2], si
0x18003c1d8  jnz     short loc_18003C1D0
0x18003c1da  lea     rcx, [rsp+68h+String1]; void *
0x18003c1df  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003c1e4  lea     rcx, [rsp+68h+String1]
0x18003c1e9  cmp     [rsp+68h+var_20], 8
0x18003c1ef  cmovnb  rcx, [rsp+68h+String1]; String1
0x18003c1f5  lea     rdx, aHttp; "http"
0x18003c1fc  call    cs:__imp__wcsicmp
0x18003c203  nop     dword ptr [rax+rax+00h]
0x18003c208  test    eax, eax
0x18003c20a  jz      short loc_18003C234
0x18003c20c  lea     rcx, [rsp+68h+String1]
0x18003c211  cmp     [rsp+68h+var_20], 8
0x18003c217  cmovnb  rcx, [rsp+68h+String1]; String1
0x18003c21d  lea     rdx, aHttps; "https"
0x18003c224  call    cs:__imp__wcsicmp
0x18003c22b  nop     dword ptr [rax+rax+00h]
0x18003c230  test    eax, eax
0x18003c232  jnz     short loc_18003C23A
0x18003c234  mov     dword ptr [rdi], 1
0x18003c23a  cmp     [rsp+68h+var_20], 8
0x18003c240  jb      short loc_18003C253
0x18003c242  mov     rcx, [rsp+68h+String1]
0x18003c247  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003c24e  nop     dword ptr [rax+rax+00h]
0x18003c253  mov     [rsp+68h+var_20], rbx
0x18003c258  mov     [rsp+68h+var_28], rsi
0x18003c25d  mov     word ptr [rsp+68h+String1], si
0x18003c262  mov     rcx, [rsp+68h+bstrString]; bstrString
0x18003c267  test    rcx, rcx
0x18003c26a  jz      short loc_18003C279
0x18003c26c  call    cs:__imp_SysFreeString
0x18003c273  nop     dword ptr [rax+rax+00h]
0x18003c278  nop
0x18003c279  mov     rcx, [rsp+68h+var_40]
0x18003c27e  test    rcx, rcx
0x18003c281  jz      short loc_18003C290
0x18003c283  mov     rax, [rcx]
0x18003c286  mov     rax, [rax+10h]
0x18003c28a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c28f  nop
0x18003c290  xor     eax, eax
0x18003c292  jmp     short loc_18003C298
0x18003c294  mov     eax, dword ptr [rsp+68h+bstrString]
0x18003c298  mov     rcx, [rsp+68h+var_18]
0x18003c29d  xor     rcx, rsp; StackCookie
0x18003c2a0  call    __security_check_cookie
0x18003c2a5  lea     r11, [rsp+68h+var_8]
0x18003c2aa  mov     rbx, [r11+10h]
0x18003c2ae  mov     rsi, [r11+28h]
0x18003c2b2  mov     rsp, r11
0x18003c2b5  pop     rdi
0x18003c2b6  retn
```
