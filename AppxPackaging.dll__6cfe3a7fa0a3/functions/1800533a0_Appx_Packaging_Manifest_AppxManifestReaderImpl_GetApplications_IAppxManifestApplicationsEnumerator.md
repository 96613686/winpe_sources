# Appx::Packaging::Manifest::AppxManifestReaderImpl::GetApplications(IAppxManifestApplicationsEnumerator * *)

- ea: `0x1800533a0`
- end: `0x18005357e`
- name: `?GetApplications@AppxManifestReaderImpl@Manifest@Packaging@Appx@@UEAAJPEAPEAUIAppxManifestApplicationsEnumerator@@@Z`
- size: `478`
- prototype: `int(Appx::Packaging::Manifest::AppxManifestReaderImpl *__hidden this, struct IAppxManifestApplicationsEnumerator **)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d4690`
- `0x1800d46a0`
- `0x1800d46b0`

## callees

- `0x180005eb8`
- `0x180010f40`
- `0x1800133fc`
- `0x1800533a0`
- `0x180053584`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005346e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053554`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005346e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053554`
- `OLEAUT32!__imp_SysFreeString` at `0x18005347e`
- `OLEAUT32!__imp_SysFreeString` at `0x180053564`
- `OLEAUT32!__imp_SysFreeString` at `0x18005347e`
- `OLEAUT32!__imp_SysFreeString` at `0x180053564`

## string_xrefs

- `0x1800534ba`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x1800534f9`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x180053527`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x18005353c`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestReaderImpl::GetApplications(
        Appx::Packaging::Manifest::AppxManifestReaderImpl *this,
        struct IAppxManifestApplicationsEnumerator **a2,
        __int64 a3,
        struct Common::AutoBStr *a4)
{
  int v6; // eax
  unsigned int v7; // edi
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, BSTR, __int64 *); // rdi
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v14; // rcx
  __int64 v15; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  __int64 v18; // [rsp+58h] [rbp+38h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+68h] [rbp+48h] BYREF

  v18 = 0;
  if ( a2 )
  {
    bstrString = 0;
    v6 = Appx::Packaging::BuildXPath(
           (Appx::Packaging *)&qword_18010B4F0,
           (const struct Appx::Packaging::XPathComponent *)2,
           &bstrString,
           a4);
    v7 = v6;
    if ( v6 < 0 )
    {
      v15 = 584;
    }
    else
    {
      v8 = *((_QWORD *)this + 16);
      v9 = *(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v8 + 288LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v18);
      v6 = v9(v8, bstrString, &v18);
      v7 = v6;
      if ( v6 >= 0 )
      {
        if ( !v18 )
        {
          v7 = -2147418113;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x24B,
            (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
            (const char *)0x8000FFFFLL,
            savedregs);
LABEL_7:
          SysFreeString(bstrString);
          v12 = v18;
          if ( v18 )
          {
            v18 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          }
          return v7;
        }
        v10 = *((_QWORD *)this + 29);
        pv = 0;
        v11 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v10 + 80LL))(v10, &pv);
        v7 = v11;
        if ( v11 >= 0 )
        {
          v7 = Appx::Packaging::Manifest::AppxManifestObjectEnumerator<IAppxManifestApplicationsEnumerator,IAppxManifestApplication,Appx::Packaging::Manifest::AppxManifestApplicationImpl,1>::Create(
                 v18,
                 pv,
                 a2);
          CoTaskMemFree(pv);
          goto LABEL_7;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x24E,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
          (const char *)(unsigned int)v11,
          savedregs);
        CoTaskMemFree(pv);
LABEL_18:
        SysFreeString(bstrString);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v18);
        return v7;
      }
      v15 = 585;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
      (const char *)(unsigned int)v6,
      savedregs);
    goto LABEL_18;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x241,
    (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
    (const char *)0x80004003LL,
    savedregs);
  v14 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800533a0  push    rbp
0x1800533a2  push    rsi
0x1800533a3  push    rdi
0x1800533a4  push    r14
0x1800533a6  push    r15; int
0x1800533a8  mov     rbp, rsp
0x1800533ab  sub     rsp, 20h
0x1800533af  mov     [rbp+arg_8], 0
0x1800533b7  mov     r14, rdx
0x1800533ba  mov     r15, rcx
0x1800533bd  test    rdx, rdx
0x1800533c0  jz      loc_1800534B6
0x1800533c6  lea     r8, [rbp+bstrString]; unsigned int
0x1800533ca  mov     [rbp+bstrString], 0
0x1800533d2  mov     edx, 2; struct Appx::Packaging::XPathComponent *
0x1800533d7  lea     rcx, qword_18010B4F0; this
0x1800533de  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x1800533e3  mov     edi, eax
0x1800533e5  test    eax, eax
0x1800533e7  js      loc_180053517
0x1800533ed  mov     rsi, [r15+80h]
0x1800533f4  lea     rcx, [rbp+arg_8]
0x1800533f8  mov     rax, [rsi]
0x1800533fb  mov     rdi, [rax+120h]
0x180053402  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180053407  mov     rdx, [rbp+bstrString]
0x18005340b  lea     r8, [rbp+arg_8]
0x18005340f  mov     rcx, rsi
0x180053412  mov     rax, rdi
0x180053415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005341a  mov     edi, eax
0x18005341c  test    eax, eax
0x18005341e  js      loc_18005351E
0x180053424  cmp     [rbp+arg_8], 0
0x180053429  jz      loc_1800534F5
0x18005342f  mov     rcx, [r15+0E8h]
0x180053436  lea     rdx, [rbp+pv]
0x18005343a  mov     [rbp+pv], 0
0x180053442  mov     rax, [rcx]
0x180053445  mov     rax, [rax+50h]
0x180053449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005344e  mov     edi, eax
0x180053450  test    eax, eax
0x180053452  js      loc_180053538
0x180053458  mov     rdx, [rbp+pv]
0x18005345c  mov     r8, r14
0x18005345f  mov     rcx, [rbp+arg_8]
0x180053463  call    ?Create@?$AppxManifestObjectEnumerator@UIAppxManifestApplicationsEnumerator@@UIAppxManifestApplication@@VAppxManifestApplicationImpl@Manifest@Packaging@Appx@@$00@Manifest@Packaging@Appx@@SAJPEAUIXMLDOMNodeList@@PEBGPEAPEAUIAppxManifestApplicationsEnumerator@@@Z; Appx::Packaging::Manifest::AppxManifestObjectEnumerator<IAppxManifestApplicationsEnumerator,IAppxManifestApplication,Appx::Packaging::Manifest::AppxManifestApplicationImpl,1>::Create(IXMLDOMNodeList *,ushort const *,IAppxManifestApplicationsEnumerator * *)
0x180053468  mov     rcx, [rbp+pv]; pv
0x18005346c  mov     edi, eax
0x18005346e  call    cs:__imp_CoTaskMemFree
0x180053475  nop     dword ptr [rax+rax+00h]
0x18005347a  mov     rcx, [rbp+bstrString]; bstrString
0x18005347e  call    cs:__imp_SysFreeString
0x180053485  nop     dword ptr [rax+rax+00h]
0x18005348a  mov     rcx, [rbp+arg_8]
0x18005348e  test    rcx, rcx
0x180053491  jz      short loc_1800534A7
0x180053493  mov     [rbp+arg_8], 0
0x18005349b  mov     rdx, [rcx]
0x18005349e  mov     rax, [rdx+10h]
0x1800534a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800534a7  mov     eax, edi
0x1800534a9  add     rsp, 20h
0x1800534ad  pop     r15
0x1800534af  pop     r14
0x1800534b1  pop     rdi
0x1800534b2  pop     rsi
0x1800534b3  pop     rbp
0x1800534b4  retn
0x1800534b6  mov     rcx, [rbp+28h]; this
0x1800534ba  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x1800534c1  mov     r9d, 80004003h; char *
0x1800534c7  mov     edx, 241h; void *
0x1800534cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800534d1  mov     rcx, [rbp+arg_8]
0x1800534d5  test    rcx, rcx
0x1800534d8  jz      short loc_1800534EE
0x1800534da  mov     [rbp+arg_8], 0
0x1800534e2  mov     rdx, [rcx]
0x1800534e5  mov     rax, [rdx+10h]
0x1800534e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800534ee  mov     eax, 80004003h
0x1800534f3  jmp     short loc_1800534A9
0x1800534f5  mov     rcx, [rbp+28h]; this
0x1800534f9  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x180053500  mov     edi, 8000FFFFh
0x180053505  mov     edx, 24Bh; void *
0x18005350a  mov     r9d, edi; char *
0x18005350d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053512  jmp     loc_18005347A
0x180053517  mov     edx, 248h
0x18005351c  jmp     short loc_180053523
0x18005351e  mov     edx, 249h; void *
0x180053523  mov     rcx, [rbp+28h]; this
0x180053527  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x18005352e  mov     r9d, eax; char *
0x180053531  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053536  jmp     short loc_180053560
0x180053538  mov     rcx, [rbp+28h]; this
0x18005353c  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x180053543  mov     r9d, eax; char *
0x180053546  mov     edx, 24Eh; void *
0x18005354b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053550  mov     rcx, [rbp+pv]; pv
0x180053554  call    cs:__imp_CoTaskMemFree
0x18005355b  nop     dword ptr [rax+rax+00h]
0x180053560  mov     rcx, [rbp+bstrString]; bstrString
0x180053564  call    cs:__imp_SysFreeString
0x18005356b  nop     dword ptr [rax+rax+00h]
0x180053570  lea     rcx, [rbp+arg_8]
0x180053574  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180053579  jmp     loc_1800534A7
```
