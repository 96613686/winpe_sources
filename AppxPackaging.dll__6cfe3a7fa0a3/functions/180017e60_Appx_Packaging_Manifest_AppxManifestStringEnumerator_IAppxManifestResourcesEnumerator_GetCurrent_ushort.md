# Appx::Packaging::Manifest::AppxManifestStringEnumerator<IAppxManifestResourcesEnumerator>::GetCurrent(ushort * *)

- ea: `0x180017e60`
- end: `0x18001809a`
- name: `?GetCurrent@?$AppxManifestStringEnumerator@UIAppxManifestResourcesEnumerator@@@Manifest@Packaging@Appx@@UEAAJPEAPEAG@Z`
- size: `570`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180016e30`
- `0x18001711c`
- `0x180017e60`
- `0x180071f50`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017f4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018026`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017f4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018026`
- `OLEAUT32!__imp_SysFreeString` at `0x180017f5b`
- `OLEAUT32!__imp_SysFreeString` at `0x180017fe3`
- `OLEAUT32!__imp_SysFreeString` at `0x180017f5b`
- `OLEAUT32!__imp_SysFreeString` at `0x180017fe3`
- `OLEAUT32!__imp_SysStringLen` at `0x180017f13`
- `OLEAUT32!__imp_SysStringLen` at `0x180017f13`

## string_xrefs

- `0x180017fb6`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x180017fcb`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x18001800e`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x180018038`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x18001805a`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x18001807c`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestStringEnumerator<IAppxManifestResourcesEnumerator>::GetCurrent(
        __int64 a1,
        LPVOID *a2)
{
  int CurrentNode; // ebx
  struct IXMLDOMNode *v5; // rdi
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rbx
  int v7; // eax
  int v8; // eax
  __int64 v9; // rcx
  struct IXMLDOMNode *v10; // rcx
  __int64 v12; // rdx
  LPVOID pv[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  __int64 v15; // [rsp+68h] [rbp+38h] BYREF
  struct IXMLDOMNode *v16; // [rsp+70h] [rbp+40h] BYREF
  BSTR pbstr; // [rsp+78h] [rbp+48h] BYREF

  if ( !a2 )
  {
    CurrentNode = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x225,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
      (const char *)0x80004003LL,
      (int)pv[0]);
    return (unsigned int)CurrentNode;
  }
  v16 = 0;
  v15 = 0;
  pbstr = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v16);
  CurrentNode = Appx::Packaging::Manifest::AppxManifestEnumeratorBase::GetCurrentNode(
                  (Appx::Packaging::Manifest::AppxManifestEnumeratorBase *)(a1 + 16),
                  &v16);
  if ( CurrentNode < 0 )
  {
    v12 = 556;
LABEL_15:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
      (const char *)(unsigned int)CurrentNode,
      (int)pv[0]);
    goto LABEL_9;
  }
  v5 = v16;
  selectSingleNode = v16->lpVtbl->selectSingleNode;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v15);
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD, __int64 *))selectSingleNode)(
         v5,
         *(_QWORD *)(a1 + 32),
         &v15);
  CurrentNode = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x22E,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
      (const char *)(unsigned int)v7,
      (int)pv[0]);
LABEL_17:
    SysFreeString(pbstr);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v15);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v16);
    return (unsigned int)CurrentNode;
  }
  if ( !v15 )
  {
    CurrentNode = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x230,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
      (const char *)0x8000FFFFLL,
      (int)pv[0]);
    goto LABEL_9;
  }
  CurrentNode = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v15 + 208LL))(v15, &pbstr);
  if ( CurrentNode < 0 )
  {
    v12 = 562;
    goto LABEL_15;
  }
  if ( !SysStringLen(pbstr) )
  {
    CurrentNode = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x235,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
      (const char *)0x8000FFFFLL,
      (int)pv[0]);
    goto LABEL_17;
  }
  pv[0] = 0;
  v8 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromBStr(
         pv,
         pbstr);
  CurrentNode = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x238,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
      (const char *)(unsigned int)v8,
      (int)pv[0]);
    CoTaskMemFree(pv[0]);
    goto LABEL_17;
  }
  *a2 = pv[0];
  CoTaskMemFree(0);
LABEL_9:
  SysFreeString(pbstr);
  v9 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v10 = v16;
  if ( v16 )
  {
    v16 = 0;
    ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
  }
  return (unsigned int)CurrentNode;
}

```

## disassembly

```asm
0x180017e60  mov     [rsp-28h+arg_0], rbx
0x180017e65  push    rbp
0x180017e66  push    rsi
0x180017e67  push    rdi
0x180017e68  push    r14
0x180017e6a  push    r15
0x180017e6c  mov     rbp, rsp
0x180017e6f  sub     rsp, 30h
0x180017e73  xor     r15d, r15d
0x180017e76  mov     rsi, rdx
0x180017e79  mov     r14, rcx
0x180017e7c  test    rdx, rdx
0x180017e7f  jz      loc_180018056
0x180017e85  lea     rcx, [rbp+arg_10]
0x180017e89  mov     [rbp+arg_10], r15
0x180017e8d  mov     [rbp+arg_8], r15
0x180017e91  mov     [rbp+pbstr], r15
0x180017e95  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180017e9a  lea     rcx, [r14+10h]; this
0x180017e9e  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x180017ea2  call    ?GetCurrentNode@AppxManifestEnumeratorBase@Manifest@Packaging@Appx@@IEAAJPEAPEAUIXMLDOMNode@@@Z; Appx::Packaging::Manifest::AppxManifestEnumeratorBase::GetCurrentNode(IXMLDOMNode * *)
0x180017ea7  mov     ebx, eax
0x180017ea9  test    eax, eax
0x180017eab  js      loc_180017FAD
0x180017eb1  mov     rdi, [rbp+arg_10]
0x180017eb5  lea     rcx, [rbp+arg_8]
0x180017eb9  mov     rax, [rdi]
0x180017ebc  mov     rbx, [rax+128h]
0x180017ec3  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180017ec8  mov     rdx, [r14+20h]
0x180017ecc  lea     r8, [rbp+arg_8]
0x180017ed0  mov     rcx, rdi
0x180017ed3  mov     rax, rbx
0x180017ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017edb  mov     ebx, eax
0x180017edd  test    eax, eax
0x180017edf  js      loc_180017FC7
0x180017ee5  mov     rcx, [rbp+arg_8]
0x180017ee9  test    rcx, rcx
0x180017eec  jz      loc_180018034
0x180017ef2  mov     rax, [rcx]
0x180017ef5  lea     rdx, [rbp+pbstr]
0x180017ef9  mov     rax, [rax+0D0h]
0x180017f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f05  mov     ebx, eax
0x180017f07  test    eax, eax
0x180017f09  js      loc_180018003
0x180017f0f  mov     rcx, [rbp+pbstr]; pbstr
0x180017f13  call    cs:__imp_SysStringLen
0x180017f1a  nop     dword ptr [rax+rax+00h]
0x180017f1f  test    eax, eax
0x180017f21  jz      loc_180018078
0x180017f27  mov     rdx, [rbp+pbstr]
0x180017f2b  lea     rcx, [rbp+pv]
0x180017f2f  mov     [rbp+pv], r15
0x180017f33  call    ?CopyFromBStr@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJQEAG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromBStr(ushort * const)
0x180017f38  mov     ebx, eax
0x180017f3a  test    eax, eax
0x180017f3c  js      loc_18001800A
0x180017f42  mov     rax, [rbp+pv]
0x180017f46  xor     ecx, ecx; pv
0x180017f48  mov     [rsi], rax
0x180017f4b  call    cs:__imp_CoTaskMemFree
0x180017f52  nop     dword ptr [rax+rax+00h]
0x180017f57  mov     rcx, [rbp+pbstr]; bstrString
0x180017f5b  call    cs:__imp_SysFreeString
0x180017f62  nop     dword ptr [rax+rax+00h]
0x180017f67  mov     rcx, [rbp+arg_8]
0x180017f6b  test    rcx, rcx
0x180017f6e  jz      short loc_180017F80
0x180017f70  mov     [rbp+arg_8], r15
0x180017f74  mov     rax, [rcx]
0x180017f77  mov     rax, [rax+10h]
0x180017f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f80  mov     rcx, [rbp+arg_10]
0x180017f84  test    rcx, rcx
0x180017f87  jz      short loc_180017F99
0x180017f89  mov     [rbp+arg_10], r15
0x180017f8d  mov     rax, [rcx]
0x180017f90  mov     rax, [rax+10h]
0x180017f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f99  mov     eax, ebx
0x180017f9b  mov     rbx, [rsp+30h+arg_0]
0x180017fa0  add     rsp, 30h
0x180017fa4  pop     r15
0x180017fa6  pop     r14
0x180017fa8  pop     rdi
0x180017fa9  pop     rsi
0x180017faa  pop     rbp
0x180017fab  retn
0x180017fad  mov     edx, 22Ch; void *
0x180017fb2  mov     rcx, [rbp+28h]; this
0x180017fb6  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x180017fbd  mov     r9d, ebx; char *
0x180017fc0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017fc5  jmp     short loc_180017F57
0x180017fc7  mov     rcx, [rbp+28h]; this
0x180017fcb  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x180017fd2  mov     r9d, ebx; char *
0x180017fd5  mov     edx, 22Eh; void *
0x180017fda  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017fdf  mov     rcx, [rbp+pbstr]; bstrString
0x180017fe3  call    cs:__imp_SysFreeString
0x180017fea  nop     dword ptr [rax+rax+00h]
0x180017fef  lea     rcx, [rbp+arg_8]
0x180017ff3  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180017ff8  lea     rcx, [rbp+arg_10]
0x180017ffc  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180018001  jmp     short loc_180017F99
0x180018003  mov     edx, 232h
0x180018008  jmp     short loc_180017FB2
0x18001800a  mov     rcx, [rbp+28h]; this
0x18001800e  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x180018015  mov     r9d, ebx; char *
0x180018018  mov     edx, 238h; void *
0x18001801d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018022  mov     rcx, [rbp+pv]; pv
0x180018026  call    cs:__imp_CoTaskMemFree
0x18001802d  nop     dword ptr [rax+rax+00h]
0x180018032  jmp     short loc_180017FDF
0x180018034  mov     rcx, [rbp+28h]; this
0x180018038  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x18001803f  mov     ebx, 8000FFFFh
0x180018044  mov     edx, 230h; void *
0x180018049  mov     r9d, ebx; char *
0x18001804c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018051  jmp     loc_180017F57
0x180018056  mov     rcx, [rbp+28h]; this
0x18001805a  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x180018061  mov     ebx, 80004003h
0x180018066  mov     edx, 225h; void *
0x18001806b  mov     r9d, ebx; char *
0x18001806e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018073  jmp     loc_180017F99
0x180018078  mov     rcx, [rbp+28h]; this
0x18001807c  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x180018083  mov     ebx, 8000FFFFh
0x180018088  mov     edx, 235h; void *
0x18001808d  mov     r9d, ebx; char *
0x180018090  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018095  jmp     loc_180017FDF
```
