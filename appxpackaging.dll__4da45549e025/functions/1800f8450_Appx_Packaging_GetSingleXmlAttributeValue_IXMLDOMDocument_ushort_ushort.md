# Appx::Packaging::GetSingleXmlAttributeValue(IXMLDOMDocument *,ushort *,ushort * *)

- ea: `0x1800f8450`
- end: `0x1800f8598`
- name: `?GetSingleXmlAttributeValue@Packaging@Appx@@YAJPEAUIXMLDOMDocument@@PEAGPEAPEAG@Z`
- size: `328`
- prototype: `__int64 __fastcall(Appx::Packaging *__hidden this, struct IXMLDOMDocument *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f82f8`
- `0x1800f83a4`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x18001711c`
- `0x1800f8450`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8544`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f855b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8544`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f855b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f84ff`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f856b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f84ff`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f856b`

## string_xrefs

- `0x1800f84a5`: `onecore\printscan\appxpackaging\publisherbridging\src\publisherbridgingartifactreader.cpp`
- `0x1800f84e7`: `onecore\printscan\appxpackaging\publisherbridging\src\publisherbridgingartifactreader.cpp`
- `0x1800f852c`: `onecore\printscan\appxpackaging\publisherbridging\src\publisherbridgingartifactreader.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::GetSingleXmlAttributeValue(
        Appx::Packaging *this,
        struct IXMLDOMDocument *a2,
        LPVOID *a3,
        unsigned __int16 **a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *v8)(Appx::Packaging *, struct IXMLDOMDocument *, __int64 *); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  int v12; // eax
  LPVOID pv[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  BSTR bstrString; // [rsp+50h] [rbp+20h] BYREF
  __int64 v17; // [rsp+68h] [rbp+38h] BYREF

  v4 = *(_QWORD *)this;
  v17 = 0;
  v8 = *(__int64 (__fastcall **)(Appx::Packaging *, struct IXMLDOMDocument *, __int64 *))(v4 + 296);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v17);
  v9 = v8(this, a2, &v17);
  v10 = v9;
  if ( v9 >= 0 )
  {
    bstrString = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v17 + 208LL))(v17, &bstrString);
    v10 = v11;
    if ( v11 >= 0 )
    {
      pv[0] = 0;
      v12 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromBStr(
              pv,
              bstrString);
      v10 = v12;
      if ( v12 >= 0 )
      {
        *a3 = pv[0];
        CoTaskMemFree(0);
        SysFreeString(bstrString);
        v10 = 0;
        goto LABEL_9;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D,
        (unsigned int)"onecore\\printscan\\appxpackaging\\publisherbridging\\src\\publisherbridgingartifactreader.cpp",
        (const char *)(unsigned int)v12,
        (int)pv[0]);
      CoTaskMemFree(pv[0]);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecore\\printscan\\appxpackaging\\publisherbridging\\src\\publisherbridgingartifactreader.cpp",
        (const char *)(unsigned int)v11,
        (int)pv[0]);
    }
    SysFreeString(bstrString);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecore\\printscan\\appxpackaging\\publisherbridging\\src\\publisherbridgingartifactreader.cpp",
      (const char *)(unsigned int)v9,
      (int)pv[0]);
  }
LABEL_9:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v17);
  return v10;
}

```

## disassembly

```asm
0x1800f8450  mov     [rsp-18h+arg_8], rbx
0x1800f8455  mov     [rsp-18h+arg_10], rsi
0x1800f845a  push    rbp
0x1800f845b  push    rdi
0x1800f845c  push    r14
0x1800f845e  mov     rbp, rsp
0x1800f8461  sub     rsp, 30h
0x1800f8465  mov     rax, [rcx]
0x1800f8468  mov     rsi, rcx
0x1800f846b  lea     rcx, [rbp+arg_18]
0x1800f846f  mov     [rbp+arg_18], 0
0x1800f8477  mov     r14, r8
0x1800f847a  mov     rdi, rdx
0x1800f847d  mov     rbx, [rax+128h]
0x1800f8484  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f8489  lea     r8, [rbp+arg_18]
0x1800f848d  mov     rdx, rdi
0x1800f8490  mov     rcx, rsi
0x1800f8493  mov     rax, rbx
0x1800f8496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f849b  mov     ebx, eax
0x1800f849d  test    eax, eax
0x1800f849f  jns     short loc_1800F84BE
0x1800f84a1  mov     rcx, [rbp+18h]; this
0x1800f84a5  lea     r8, aOnecorePrintsc_141; "onecore\\printscan\\appxpackaging\\publ"...
0x1800f84ac  mov     r9d, eax; char *
0x1800f84af  mov     edx, 27h ; '''; void *
0x1800f84b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f84b9  jmp     loc_1800F8579
0x1800f84be  mov     rcx, [rbp+arg_18]
0x1800f84c2  lea     rdx, [rbp+bstrString]
0x1800f84c6  mov     [rbp+bstrString], 0
0x1800f84ce  mov     rax, [rcx]
0x1800f84d1  mov     rax, [rax+0D0h]
0x1800f84d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f84dd  mov     ebx, eax
0x1800f84df  test    eax, eax
0x1800f84e1  jns     short loc_1800F850D
0x1800f84e3  mov     rcx, [rbp+18h]; this
0x1800f84e7  lea     r8, aOnecorePrintsc_141; "onecore\\printscan\\appxpackaging\\publ"...
0x1800f84ee  mov     r9d, eax; char *
0x1800f84f1  mov     edx, 2Ah ; '*'; void *
0x1800f84f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f84fb  mov     rcx, [rbp+bstrString]; bstrString
0x1800f84ff  call    cs:__imp_SysFreeString
0x1800f8506  nop     dword ptr [rax+rax+00h]
0x1800f850b  jmp     short loc_1800F8579
0x1800f850d  mov     rdx, [rbp+bstrString]
0x1800f8511  lea     rcx, [rbp+pv]
0x1800f8515  mov     [rbp+pv], 0
0x1800f851d  call    ?CopyFromBStr@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJQEAG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromBStr(ushort * const)
0x1800f8522  mov     ebx, eax
0x1800f8524  test    eax, eax
0x1800f8526  jns     short loc_1800F8552
0x1800f8528  mov     rcx, [rbp+18h]; this
0x1800f852c  lea     r8, aOnecorePrintsc_141; "onecore\\printscan\\appxpackaging\\publ"...
0x1800f8533  mov     r9d, eax; char *
0x1800f8536  mov     edx, 2Dh ; '-'; void *
0x1800f853b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8540  mov     rcx, [rbp+pv]; pv
0x1800f8544  call    cs:__imp_CoTaskMemFree
0x1800f854b  nop     dword ptr [rax+rax+00h]
0x1800f8550  jmp     short loc_1800F84FB
0x1800f8552  mov     rax, [rbp+pv]
0x1800f8556  xor     ecx, ecx; pv
0x1800f8558  mov     [r14], rax
0x1800f855b  call    cs:__imp_CoTaskMemFree
0x1800f8562  nop     dword ptr [rax+rax+00h]
0x1800f8567  mov     rcx, [rbp+bstrString]; bstrString
0x1800f856b  call    cs:__imp_SysFreeString
0x1800f8572  nop     dword ptr [rax+rax+00h]
0x1800f8577  xor     ebx, ebx
0x1800f8579  lea     rcx, [rbp+arg_18]
0x1800f857d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f8582  mov     rsi, [rsp+30h+arg_10]
0x1800f8587  mov     eax, ebx
0x1800f8589  mov     rbx, [rsp+30h+arg_8]
0x1800f858e  add     rsp, 30h
0x1800f8592  pop     r14
0x1800f8594  pop     rdi
0x1800f8595  pop     rbp
0x1800f8596  retn
```
