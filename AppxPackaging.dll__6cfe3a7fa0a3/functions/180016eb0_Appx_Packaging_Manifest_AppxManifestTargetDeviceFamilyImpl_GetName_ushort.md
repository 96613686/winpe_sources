# Appx::Packaging::Manifest::AppxManifestTargetDeviceFamilyImpl::GetName(ushort * *)

- ea: `0x180016eb0`
- end: `0x180017115`
- name: `?GetName@AppxManifestTargetDeviceFamilyImpl@Manifest@Packaging@Appx@@UEAAJPEAPEAG@Z`
- size: `613`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::AppxManifestTargetDeviceFamilyImpl *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005eb8`
- `0x180010f40`
- `0x1800133fc`
- `0x180016eb0`
- `0x18001711c`
- `0x180071f50`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017064`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017064`
- `OLEAUT32!__imp_SysFreeString` at `0x180016fe1`
- `OLEAUT32!__imp_SysFreeString` at `0x180016ff1`
- `OLEAUT32!__imp_SysFreeString` at `0x180016fe1`
- `OLEAUT32!__imp_SysFreeString` at `0x180016ff1`
- `OLEAUT32!__imp_SysStringLen` at `0x180016f86`
- `OLEAUT32!__imp_SysStringLen` at `0x180016f86`

## string_xrefs

- `0x180016fc9`: `onecore\printscan\appxpackaging\manifest\src\appxmanifesttargetplatform.cpp`
- `0x180017079`: `onecore\printscan\appxpackaging\manifest\src\appxmanifesttargetplatform.cpp`
- `0x1800170bc`: `onecore\printscan\appxpackaging\manifest\src\appxmanifesttargetplatform.cpp`
- `0x1800170f7`: `onecore\printscan\appxpackaging\manifest\src\appxmanifesttargetplatform.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestTargetDeviceFamilyImpl::GetName(
        Appx::Packaging::Manifest::AppxManifestTargetDeviceFamilyImpl *this,
        unsigned __int16 **a2,
        __int64 a3,
        struct Common::AutoBStr *a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, BSTR, unsigned __int16 **); // rbx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  unsigned __int16 *v13; // rcx
  unsigned __int16 *v15; // rcx
  int v16; // eax
  unsigned __int16 *v17; // rcx
  int v18; // [rsp+20h] [rbp-30h] BYREF
  const OLECHAR *v19; // [rsp+28h] [rbp-28h]
  int v20; // [rsp+30h] [rbp-20h]
  const wchar_t *v21; // [rsp+38h] [rbp-18h]
  int v22; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  unsigned __int16 *v24; // [rsp+78h] [rbp+28h] BYREF
  BSTR pbstr; // [rsp+80h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+38h] BYREF

  if ( !a2 )
  {
    v7 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifesttargetplatform.cpp",
      (const char *)0x80004003LL,
      v18);
    return v7;
  }
  bstrString = 0;
  v18 = 4;
  v19 = L"Name";
  v20 = 4;
  v21 = L"']";
  v22 = 0;
  v6 = Appx::Packaging::BuildXPath(
         (Appx::Packaging *)&v18,
         (const struct Appx::Packaging::XPathComponent *)1,
         &bstrString,
         a4);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifesttargetplatform.cpp",
      (const char *)(unsigned int)v6,
      v18);
    goto LABEL_14;
  }
  v8 = *((_QWORD *)this + 2);
  v24 = 0;
  pbstr = 0;
  v9 = *(__int64 (__fastcall **)(__int64, BSTR, unsigned __int16 **))(*(_QWORD *)v8 + 296LL);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v24);
  v10 = v9(v8, bstrString, &v24);
  v7 = v10;
  if ( v10 >= 0 )
  {
    if ( v24 )
    {
      v11 = (*(__int64 (__fastcall **)(unsigned __int16 *, BSTR *))(*(_QWORD *)v24 + 208LL))(v24, &pbstr);
      v7 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x51,
          (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
          (const char *)(unsigned int)v11,
          v18);
LABEL_10:
        v13 = v24;
        if ( v24 )
        {
          v24 = 0;
          (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v13 + 16LL))(v13);
        }
        goto LABEL_12;
      }
      if ( SysStringLen(pbstr) )
      {
        v15 = v24;
        if ( v24 )
        {
          v24 = 0;
          (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v15 + 16LL))(v15);
        }
        v24 = 0;
        v16 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromBStr(
                (LPVOID *)&v24,
                pbstr);
        v7 = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x3C,
            (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifesttargetplatform.cpp",
            (const char *)(unsigned int)v16,
            v18);
          v17 = v24;
        }
        else
        {
          v17 = 0;
          *a2 = v24;
        }
        CoTaskMemFree(v17);
        goto LABEL_13;
      }
      v12 = 84;
    }
    else
    {
      v12 = 79;
    }
    v7 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)0x8000FFFFLL,
      v18);
    goto LABEL_10;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x4D,
    (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
    (const char *)(unsigned int)v10,
    v18);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v24);
LABEL_12:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x39,
    (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifesttargetplatform.cpp",
    (const char *)v7,
    v18);
LABEL_13:
  SysFreeString(pbstr);
LABEL_14:
  SysFreeString(bstrString);
  return v7;
}

```

## disassembly

```asm
0x180016eb0  mov     [rsp-18h+arg_0], rbx
0x180016eb5  push    rbp
0x180016eb6  push    rsi
0x180016eb7  push    rdi
0x180016eb8  mov     rbp, rsp
0x180016ebb  sub     rsp, 50h
0x180016ebf  mov     rsi, rdx
0x180016ec2  mov     rdi, rcx
0x180016ec5  test    rdx, rdx
0x180016ec8  jz      loc_1800170F3
0x180016ece  mov     ecx, 4
0x180016ed3  mov     [rbp+bstrString], 0
0x180016edb  lea     rax, ?Name@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Name"
0x180016ee2  mov     [rbp+var_30], ecx
0x180016ee5  mov     [rbp+var_28], rax
0x180016ee9  lea     r8, [rbp+bstrString]; unsigned int
0x180016eed  mov     [rbp+var_20], ecx
0x180016ef0  lea     rax, asc_1801177B4; "']"
0x180016ef7  lea     edx, [rcx-3]; struct Appx::Packaging::XPathComponent *
0x180016efa  mov     [rbp+var_18], rax
0x180016efe  lea     rcx, [rbp+var_30]; this
0x180016f02  mov     [rbp+var_10], 0
0x180016f09  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x180016f0e  mov     ebx, eax
0x180016f10  test    eax, eax
0x180016f12  js      loc_180017075
0x180016f18  mov     rdi, [rdi+10h]
0x180016f1c  lea     rcx, [rbp+arg_8]
0x180016f20  mov     [rbp+arg_8], 0
0x180016f28  mov     [rbp+pbstr], 0
0x180016f30  mov     rax, [rdi]
0x180016f33  mov     rbx, [rax+128h]
0x180016f3a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180016f3f  mov     rdx, [rbp+bstrString]
0x180016f43  lea     r8, [rbp+arg_8]
0x180016f47  mov     rcx, rdi
0x180016f4a  mov     rax, rbx
0x180016f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f52  mov     ebx, eax
0x180016f54  test    eax, eax
0x180016f56  js      loc_180017092
0x180016f5c  mov     rcx, [rbp+arg_8]
0x180016f60  test    rcx, rcx
0x180016f63  jz      short loc_180016F9F
0x180016f65  mov     rax, [rcx]
0x180016f68  lea     rdx, [rbp+pbstr]
0x180016f6c  mov     rax, [rax+0D0h]
0x180016f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f78  mov     ebx, eax
0x180016f7a  test    eax, eax
0x180016f7c  js      loc_1800170D6
0x180016f82  mov     rcx, [rbp+pbstr]; pbstr
0x180016f86  call    cs:__imp_SysStringLen
0x180016f8d  nop     dword ptr [rax+rax+00h]
0x180016f92  test    eax, eax
0x180016f94  jnz     loc_180017023
0x180016f9a  lea     edx, [rax+54h]
0x180016f9d  jmp     short loc_180016FA4
0x180016f9f  mov     edx, 4Fh ; 'O'; void *
0x180016fa4  mov     rcx, [rbp+18h]; this
0x180016fa8  lea     r8, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x180016faf  mov     ebx, 8000FFFFh
0x180016fb4  mov     r9d, ebx; char *
0x180016fb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016fbc  mov     rcx, [rbp+arg_8]
0x180016fc0  test    rcx, rcx
0x180016fc3  jnz     short loc_18001700D
0x180016fc5  mov     rcx, [rbp+18h]; this
0x180016fc9  lea     r8, aOnecorePrintsc_164; "onecore\\printscan\\appxpackaging\\mani"...
0x180016fd0  mov     r9d, ebx; char *
0x180016fd3  mov     edx, 39h ; '9'; void *
0x180016fd8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016fdd  mov     rcx, [rbp+pbstr]; bstrString
0x180016fe1  call    cs:__imp_SysFreeString
0x180016fe8  nop     dword ptr [rax+rax+00h]
0x180016fed  mov     rcx, [rbp+bstrString]; bstrString
0x180016ff1  call    cs:__imp_SysFreeString
0x180016ff8  nop     dword ptr [rax+rax+00h]
0x180016ffd  mov     eax, ebx
0x180016fff  mov     rbx, [rsp+50h+arg_0]
0x180017004  add     rsp, 50h
0x180017008  pop     rdi
0x180017009  pop     rsi
0x18001700a  pop     rbp
0x18001700b  retn
0x18001700d  mov     [rbp+arg_8], 0
0x180017015  mov     rax, [rcx]
0x180017018  mov     rax, [rax+10h]
0x18001701c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017021  jmp     short loc_180016FC5
0x180017023  mov     rcx, [rbp+arg_8]
0x180017027  test    rcx, rcx
0x18001702a  jz      short loc_180017040
0x18001702c  mov     [rbp+arg_8], 0
0x180017034  mov     rax, [rcx]
0x180017037  mov     rax, [rax+10h]
0x18001703b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017040  mov     rdx, [rbp+pbstr]
0x180017044  lea     rcx, [rbp+arg_8]
0x180017048  mov     [rbp+arg_8], 0
0x180017050  call    ?CopyFromBStr@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJQEAG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromBStr(ushort * const)
0x180017055  mov     ebx, eax
0x180017057  test    eax, eax
0x180017059  js      short loc_1800170B8
0x18001705b  mov     rax, [rbp+arg_8]
0x18001705f  xor     ecx, ecx; pv
0x180017061  mov     [rsi], rax
0x180017064  call    cs:__imp_CoTaskMemFree
0x18001706b  nop     dword ptr [rax+rax+00h]
0x180017070  jmp     loc_180016FDD
0x180017075  mov     rcx, [rbp+18h]; this
0x180017079  lea     r8, aOnecorePrintsc_164; "onecore\\printscan\\appxpackaging\\mani"...
0x180017080  mov     r9d, eax; char *
0x180017083  mov     edx, 36h ; '6'; void *
0x180017088  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001708d  jmp     loc_180016FED
0x180017092  mov     rcx, [rbp+18h]; this
0x180017096  lea     r8, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x18001709d  mov     r9d, eax; char *
0x1800170a0  mov     edx, 4Dh ; 'M'; void *
0x1800170a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800170aa  lea     rcx, [rbp+arg_8]
0x1800170ae  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800170b3  jmp     loc_180016FC5
0x1800170b8  mov     rcx, [rbp+18h]; this
0x1800170bc  lea     r8, aOnecorePrintsc_164; "onecore\\printscan\\appxpackaging\\mani"...
0x1800170c3  mov     r9d, eax; char *
0x1800170c6  mov     edx, 3Ch ; '<'; void *
0x1800170cb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800170d0  mov     rcx, [rbp+arg_8]
0x1800170d4  jmp     short loc_180017064
0x1800170d6  mov     rcx, [rbp+18h]; this
0x1800170da  lea     r8, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x1800170e1  mov     r9d, eax; char *
0x1800170e4  mov     edx, 51h ; 'Q'; void *
0x1800170e9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800170ee  jmp     loc_180016FBC
0x1800170f3  mov     rcx, [rbp+18h]; this
0x1800170f7  lea     r8, aOnecorePrintsc_164; "onecore\\printscan\\appxpackaging\\mani"...
0x1800170fe  mov     ebx, 80004003h
0x180017103  mov     edx, 32h ; '2'; void *
0x180017108  mov     r9d, ebx; char *
0x18001710b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017110  jmp     loc_180016FFD
```
