# Appx::Packaging::ContentGroupMap::SourceContentGroupMapReaderImpl::InitializeRequiredRoot(void)

- ea: `0x1800eb420`
- end: `0x1800eb5de`
- name: `?InitializeRequiredRoot@SourceContentGroupMapReaderImpl@ContentGroupMap@Packaging@Appx@@AEAAJXZ`
- size: `446`
- prototype: `__int64 __fastcall(Appx::Packaging::ContentGroupMap::SourceContentGroupMapReaderImpl *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800eb64c`

## callees

- `0x180005eb8`
- `0x180010f40`
- `0x1800133fc`
- `0x1800bb058`
- `0x1800eb420`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eb574`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eb5a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eb574`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eb5a9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800eb5c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800eb5c4`

## string_xrefs

- `0x1800eb4bd`: `onecore\printscan\appxpackaging\streammap\src\sourcecontentgroupmapreader.cpp`
- `0x1800eb514`: `onecore\printscan\appxpackaging\streammap\src\sourcecontentgroupmapreader.cpp`
- `0x1800eb564`: `onecore\printscan\appxpackaging\streammap\src\sourcecontentgroupmapreader.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::ContentGroupMap::SourceContentGroupMapReaderImpl::InitializeRequiredRoot(
        Appx::Packaging::ContentGroupMap::SourceContentGroupMapReaderImpl *this,
        __int64 a2,
        __int64 a3,
        struct Common::AutoBStr *a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, BSTR, char *); // rbx
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 (__fastcall *v12)(Appx::Packaging::ContentGroupMap::SourceContentGroupMapReaderImpl *, __int64 *); // rbx
  int v13; // eax
  int v14; // eax
  __int64 v15; // r9
  __int64 v16; // rdx
  int v18; // [rsp+20h] [rbp-30h] BYREF
  const unsigned __int16 *v19; // [rsp+28h] [rbp-28h]
  int v20; // [rsp+30h] [rbp-20h]
  const wchar_t *v21; // [rsp+38h] [rbp-18h]
  int v22; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  __int64 v24; // [rsp+88h] [rbp+38h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp+48h] BYREF

  bstrString = 0;
  v19 = L"s:ContentGroupMap/s:Required/s:ContentGroup";
  v20 = 43;
  v21 = L"']";
  v22 = 0;
  v18 = 1;
  v5 = Appx::Packaging::BuildXPath(
         (Appx::Packaging *)&v18,
         (const struct Appx::Packaging::XPathComponent *)1,
         &bstrString,
         a4);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 102;
LABEL_5:
    v10 = (unsigned int)v5;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\printscan\\appxpackaging\\streammap\\src\\sourcecontentgroupmapreader.cpp",
      (const char *)v10,
      v18);
    goto LABEL_18;
  }
  v8 = *((_QWORD *)this + 4);
  v9 = *(__int64 (__fastcall **)(__int64, BSTR, char *))(*(_QWORD *)v8 + 296LL);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease((char *)this + 88);
  v5 = v9(v8, bstrString, (char *)this + 88);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 103;
    goto LABEL_5;
  }
  if ( !*((_QWORD *)this + 11) )
  {
    v6 = -2146958837;
    v7 = 106;
    v10 = 2148008459LL;
    goto LABEL_6;
  }
  v11 = *(_QWORD *)this;
  v24 = 0;
  v12 = *(__int64 (__fastcall **)(Appx::Packaging::ContentGroupMap::SourceContentGroupMapReaderImpl *, __int64 *))(v11 + 24);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v24);
  v13 = v12(this, &v24);
  v6 = v13;
  if ( v13 >= 0 )
  {
    pv = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v24 + 24LL))(v24, &pv);
    v6 = v14;
    if ( v14 >= 0 )
    {
      if ( Common::String::Equals((const unsigned __int16 *)pv, L"Required") )
      {
        CoTaskMemFree(pv);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v24);
        v6 = 0;
        goto LABEL_18;
      }
      v6 = -2146958837;
      v16 = 115;
      v15 = 2148008459LL;
    }
    else
    {
      v15 = (unsigned int)v14;
      v16 = 113;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\printscan\\appxpackaging\\streammap\\src\\sourcecontentgroupmapreader.cpp",
      (const char *)v15,
      v18);
    CoTaskMemFree(pv);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecore\\printscan\\appxpackaging\\streammap\\src\\sourcecontentgroupmapreader.cpp",
      (const char *)(unsigned int)v13,
      v18);
  }
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v24);
LABEL_18:
  SysFreeString(bstrString);
  return v6;
}

```

## disassembly

```asm
0x1800eb420  push    rbp
0x1800eb422  push    rbx
0x1800eb423  push    rsi
0x1800eb424  push    rdi
0x1800eb425  push    r14
0x1800eb427  mov     rbp, rsp
0x1800eb42a  sub     rsp, 50h
0x1800eb42e  lea     rax, ?RequiredStreamNodeXPath@SourceContentGroupMap@Packaging@Appx@@3QBGB; "s:ContentGroupMap/s:Required/s:ContentG"...
0x1800eb435  mov     [rbp+bstrString], 0
0x1800eb43d  mov     [rbp+var_28], rax
0x1800eb441  lea     r8, [rbp+bstrString]; unsigned int
0x1800eb445  lea     rax, asc_1801177B4; "']"
0x1800eb44c  mov     [rbp+var_20], 2Bh ; '+'
0x1800eb453  mov     rsi, rcx
0x1800eb456  mov     [rbp+var_18], rax
0x1800eb45a  mov     edx, 1; struct Appx::Packaging::XPathComponent *
0x1800eb45f  mov     [rbp+var_10], 0
0x1800eb466  lea     rcx, [rbp+var_30]; this
0x1800eb46a  mov     [rbp+var_30], edx
0x1800eb46d  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x1800eb472  mov     ebx, eax
0x1800eb474  test    eax, eax
0x1800eb476  jns     short loc_1800EB47F
0x1800eb478  mov     edx, 66h ; 'f'
0x1800eb47d  jmp     short loc_1800EB4B6
0x1800eb47f  mov     rdi, [rsi+20h]
0x1800eb483  lea     r14, [rsi+58h]
0x1800eb487  mov     rcx, r14
0x1800eb48a  mov     rax, [rdi]
0x1800eb48d  mov     rbx, [rax+128h]
0x1800eb494  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800eb499  mov     rdx, [rbp+bstrString]
0x1800eb49d  mov     r8, r14
0x1800eb4a0  mov     rcx, rdi
0x1800eb4a3  mov     rax, rbx
0x1800eb4a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb4ab  mov     ebx, eax
0x1800eb4ad  test    eax, eax
0x1800eb4af  jns     short loc_1800EB4CE
0x1800eb4b1  mov     edx, 67h ; 'g'; void *
0x1800eb4b6  mov     r9d, eax; char *
0x1800eb4b9  mov     rcx, [rbp+28h]; this
0x1800eb4bd  lea     r8, aOnecorePrintsc_167; "onecore\\printscan\\appxpackaging\\stre"...
0x1800eb4c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eb4c9  jmp     loc_1800EB5C0
0x1800eb4ce  cmp     qword ptr [r14], 0
0x1800eb4d2  jnz     short loc_1800EB4E3
0x1800eb4d4  mov     ebx, 8008020Bh
0x1800eb4d9  mov     edx, 6Ah ; 'j'
0x1800eb4de  mov     r9d, ebx
0x1800eb4e1  jmp     short loc_1800EB4B9
0x1800eb4e3  mov     rax, [rsi]
0x1800eb4e6  lea     rcx, [rbp+arg_8]
0x1800eb4ea  mov     [rbp+arg_8], 0
0x1800eb4f2  mov     rbx, [rax+18h]
0x1800eb4f6  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800eb4fb  lea     rdx, [rbp+arg_8]
0x1800eb4ff  mov     rcx, rsi
0x1800eb502  mov     rax, rbx
0x1800eb505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb50a  mov     ebx, eax
0x1800eb50c  test    eax, eax
0x1800eb50e  jns     short loc_1800EB536
0x1800eb510  mov     rcx, [rbp+28h]; this
0x1800eb514  lea     r8, aOnecorePrintsc_167; "onecore\\printscan\\appxpackaging\\stre"...
0x1800eb51b  mov     r9d, eax; char *
0x1800eb51e  mov     edx, 6Eh ; 'n'; void *
0x1800eb523  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eb528  lea     rcx, [rbp+arg_8]
0x1800eb52c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800eb531  jmp     loc_1800EB5C0
0x1800eb536  mov     rcx, [rbp+arg_8]
0x1800eb53a  lea     rdx, [rbp+pv]
0x1800eb53e  mov     [rbp+pv], 0
0x1800eb546  mov     rax, [rcx]
0x1800eb549  mov     rax, [rax+18h]
0x1800eb54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb552  mov     ebx, eax
0x1800eb554  test    eax, eax
0x1800eb556  jns     short loc_1800EB582
0x1800eb558  mov     r9d, eax; char *
0x1800eb55b  mov     edx, 71h ; 'q'; void *
0x1800eb560  mov     rcx, [rbp+28h]; this
0x1800eb564  lea     r8, aOnecorePrintsc_167; "onecore\\printscan\\appxpackaging\\stre"...
0x1800eb56b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eb570  mov     rcx, [rbp+pv]; pv
0x1800eb574  call    cs:__imp_CoTaskMemFree
0x1800eb57b  nop     dword ptr [rax+rax+00h]
0x1800eb580  jmp     short loc_1800EB528
0x1800eb582  mov     rcx, [rbp+pv]; unsigned __int16 *
0x1800eb586  lea     rdx, ?RequiredGroupName@SourceContentGroupMap@Packaging@Appx@@3QBGB; "Required"
0x1800eb58d  call    ?Equals@String@Common@@SA_NPEBG0@Z; Common::String::Equals(ushort const *,ushort const *)
0x1800eb592  test    al, al
0x1800eb594  jnz     short loc_1800EB5A5
0x1800eb596  mov     ebx, 8008020Bh
0x1800eb59b  mov     edx, 73h ; 's'
0x1800eb5a0  mov     r9d, ebx
0x1800eb5a3  jmp     short loc_1800EB560
0x1800eb5a5  mov     rcx, [rbp+pv]; pv
0x1800eb5a9  call    cs:__imp_CoTaskMemFree
0x1800eb5b0  nop     dword ptr [rax+rax+00h]
0x1800eb5b5  lea     rcx, [rbp+arg_8]
0x1800eb5b9  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800eb5be  xor     ebx, ebx
0x1800eb5c0  mov     rcx, [rbp+bstrString]; bstrString
0x1800eb5c4  call    cs:__imp_SysFreeString
0x1800eb5cb  nop     dword ptr [rax+rax+00h]
0x1800eb5d0  mov     eax, ebx
0x1800eb5d2  add     rsp, 50h
0x1800eb5d6  pop     r14
0x1800eb5d8  pop     rdi
0x1800eb5d9  pop     rsi
0x1800eb5da  pop     rbx
0x1800eb5db  pop     rbp
0x1800eb5dc  retn
```
