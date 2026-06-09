# Appx::Packaging::Manifest::AppxManifestStringEnumerator<IAppxManifestCapabilitiesEnumerator>::GetCurrent(ushort * *)

- ea: `0x180016bb0`
- end: `0x180016e28`
- name: `?GetCurrent@?$AppxManifestStringEnumerator@UIAppxManifestCapabilitiesEnumerator@@@Manifest@Packaging@Appx@@UEAAJPEAPEAG@Z`
- size: `632`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180016bb0`
- `0x180016e30`
- `0x18001711c`
- `0x180071f50`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016c9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016c9b`
- `OLEAUT32!__imp_SysFreeString` at `0x180016cab`
- `OLEAUT32!__imp_SysFreeString` at `0x180016d19`
- `OLEAUT32!__imp_SysFreeString` at `0x180016da2`
- `OLEAUT32!__imp_SysFreeString` at `0x180016cab`
- `OLEAUT32!__imp_SysFreeString` at `0x180016d19`
- `OLEAUT32!__imp_SysFreeString` at `0x180016da2`
- `OLEAUT32!__imp_SysStringLen` at `0x180016c63`
- `OLEAUT32!__imp_SysStringLen` at `0x180016c63`

## string_xrefs

- `0x180016d09`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x180016d47`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x180016d64`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x180016d85`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x180016de8`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x180016e0a`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestStringEnumerator<IAppxManifestCapabilitiesEnumerator>::GetCurrent(
        __int64 a1,
        _QWORD *a2)
{
  unsigned int CurrentNode; // ebx
  struct IXMLDOMNode *v5; // rdi
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rbx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  void *v10; // rcx
  __int64 v11; // rcx
  struct IXMLDOMNode *v12; // rcx
  void (*Release)(void); // rax
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rcx
  struct IXMLDOMNode *v18; // rcx
  LPVOID v19; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  __int64 v21; // [rsp+68h] [rbp+38h] BYREF
  struct IXMLDOMNode *v22; // [rsp+70h] [rbp+40h] BYREF
  BSTR pbstr; // [rsp+78h] [rbp+48h] BYREF

  if ( !a2 )
  {
    CurrentNode = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x225,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
      (const char *)0x80004003LL,
      (int)v19);
    return CurrentNode;
  }
  v22 = 0;
  v21 = 0;
  pbstr = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v22);
  CurrentNode = Appx::Packaging::Manifest::AppxManifestEnumeratorBase::GetCurrentNode(
                  (Appx::Packaging::Manifest::AppxManifestEnumeratorBase *)(a1 + 16),
                  &v22);
  if ( (CurrentNode & 0x80000000) != 0 )
  {
    v15 = CurrentNode;
    v16 = 556;
    goto LABEL_17;
  }
  v5 = v22;
  selectSingleNode = v22->lpVtbl->selectSingleNode;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v21);
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD, __int64 *))selectSingleNode)(
         v5,
         *(_QWORD *)(a1 + 32),
         &v21);
  CurrentNode = v7;
  if ( v7 < 0 )
  {
    v15 = (unsigned int)v7;
    v16 = 558;
LABEL_17:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
      (const char *)v15,
      (int)v19);
LABEL_18:
    SysFreeString(pbstr);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v21);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v22);
    return CurrentNode;
  }
  if ( !v21 )
  {
    CurrentNode = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x230,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
      (const char *)0x8000FFFFLL,
      (int)v19);
    goto LABEL_18;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v21 + 208LL))(v21, &pbstr);
  CurrentNode = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
      (const char *)(unsigned int)v8,
      (int)v19);
LABEL_10:
    SysFreeString(pbstr);
    v11 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    v12 = v22;
    if ( v22 )
    {
      v22 = 0;
      Release = (void (*)(void))v12->lpVtbl->Release;
LABEL_14:
      Release();
      return CurrentNode;
    }
    return CurrentNode;
  }
  if ( SysStringLen(pbstr) )
  {
    v19 = 0;
    v9 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromBStr(
           &v19,
           pbstr);
    CurrentNode = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x238,
        (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
        (const char *)(unsigned int)v9,
        (int)v19);
      v10 = v19;
    }
    else
    {
      v10 = 0;
      *a2 = v19;
    }
    CoTaskMemFree(v10);
    goto LABEL_10;
  }
  CurrentNode = -2147418113;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x235,
    (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
    (const char *)0x8000FFFFLL,
    (int)v19);
  SysFreeString(pbstr);
  v17 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v18 = v22;
  if ( v22 )
  {
    v22 = 0;
    Release = (void (*)(void))v18->lpVtbl->Release;
    goto LABEL_14;
  }
  return CurrentNode;
}

```

## disassembly

```asm
0x180016bb0  mov     [rsp-28h+arg_0], rbx
0x180016bb5  push    rbp
0x180016bb6  push    rsi
0x180016bb7  push    rdi
0x180016bb8  push    r14
0x180016bba  push    r15
0x180016bbc  mov     rbp, rsp
0x180016bbf  sub     rsp, 30h
0x180016bc3  xor     r15d, r15d
0x180016bc6  mov     rsi, rdx
0x180016bc9  mov     r14, rcx
0x180016bcc  test    rdx, rdx
0x180016bcf  jz      loc_180016DE4
0x180016bd5  lea     rcx, [rbp+arg_10]
0x180016bd9  mov     [rbp+arg_10], r15
0x180016bdd  mov     [rbp+arg_8], r15
0x180016be1  mov     [rbp+pbstr], r15
0x180016be5  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180016bea  lea     rcx, [r14+10h]; this
0x180016bee  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x180016bf2  call    ?GetCurrentNode@AppxManifestEnumeratorBase@Manifest@Packaging@Appx@@IEAAJPEAPEAUIXMLDOMNode@@@Z; Appx::Packaging::Manifest::AppxManifestEnumeratorBase::GetCurrentNode(IXMLDOMNode * *)
0x180016bf7  mov     ebx, eax
0x180016bf9  test    eax, eax
0x180016bfb  js      loc_180016D39
0x180016c01  mov     rdi, [rbp+arg_10]
0x180016c05  lea     rcx, [rbp+arg_8]
0x180016c09  mov     rax, [rdi]
0x180016c0c  mov     rbx, [rax+128h]
0x180016c13  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180016c18  mov     rdx, [r14+20h]
0x180016c1c  lea     r8, [rbp+arg_8]
0x180016c20  mov     rcx, rdi
0x180016c23  mov     rax, rbx
0x180016c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c2b  mov     ebx, eax
0x180016c2d  test    eax, eax
0x180016c2f  js      loc_180016CFD
0x180016c35  mov     rcx, [rbp+arg_8]
0x180016c39  test    rcx, rcx
0x180016c3c  jz      loc_180016E06
0x180016c42  mov     rax, [rcx]
0x180016c45  lea     rdx, [rbp+pbstr]
0x180016c49  mov     rax, [rax+0D0h]
0x180016c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c55  mov     ebx, eax
0x180016c57  test    eax, eax
0x180016c59  js      loc_180016D43
0x180016c5f  mov     rcx, [rbp+pbstr]; pbstr
0x180016c63  call    cs:__imp_SysStringLen
0x180016c6a  nop     dword ptr [rax+rax+00h]
0x180016c6f  test    eax, eax
0x180016c71  jz      loc_180016D81
0x180016c77  mov     rdx, [rbp+pbstr]
0x180016c7b  lea     rcx, [rbp+var_10]
0x180016c7f  mov     [rbp+var_10], r15
0x180016c83  call    ?CopyFromBStr@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJQEAG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromBStr(ushort * const)
0x180016c88  mov     ebx, eax
0x180016c8a  test    eax, eax
0x180016c8c  js      loc_180016D60
0x180016c92  mov     rax, [rbp+var_10]
0x180016c96  xor     ecx, ecx; pv
0x180016c98  mov     [rsi], rax
0x180016c9b  call    cs:__imp_CoTaskMemFree
0x180016ca2  nop     dword ptr [rax+rax+00h]
0x180016ca7  mov     rcx, [rbp+pbstr]; bstrString
0x180016cab  call    cs:__imp_SysFreeString
0x180016cb2  nop     dword ptr [rax+rax+00h]
0x180016cb7  mov     rcx, [rbp+arg_8]
0x180016cbb  test    rcx, rcx
0x180016cbe  jz      short loc_180016CD0
0x180016cc0  mov     [rbp+arg_8], r15
0x180016cc4  mov     rax, [rcx]
0x180016cc7  mov     rax, [rax+10h]
0x180016ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cd0  mov     rcx, [rbp+arg_10]
0x180016cd4  test    rcx, rcx
0x180016cd7  jz      short loc_180016CE9
0x180016cd9  mov     [rbp+arg_10], r15
0x180016cdd  mov     rax, [rcx]
0x180016ce0  mov     rax, [rax+10h]
0x180016ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ce9  mov     eax, ebx
0x180016ceb  mov     rbx, [rsp+30h+arg_0]
0x180016cf0  add     rsp, 30h
0x180016cf4  pop     r15
0x180016cf6  pop     r14
0x180016cf8  pop     rdi
0x180016cf9  pop     rsi
0x180016cfa  pop     rbp
0x180016cfb  retn
0x180016cfd  mov     r9d, eax; char *
0x180016d00  mov     edx, 22Eh; void *
0x180016d05  mov     rcx, [rbp+28h]; this
0x180016d09  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x180016d10  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016d15  mov     rcx, [rbp+pbstr]; bstrString
0x180016d19  call    cs:__imp_SysFreeString
0x180016d20  nop     dword ptr [rax+rax+00h]
0x180016d25  lea     rcx, [rbp+arg_8]
0x180016d29  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180016d2e  lea     rcx, [rbp+arg_10]
0x180016d32  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180016d37  jmp     short loc_180016CE9
0x180016d39  mov     r9d, ebx
0x180016d3c  mov     edx, 22Ch
0x180016d41  jmp     short loc_180016D05
0x180016d43  mov     rcx, [rbp+28h]; this
0x180016d47  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x180016d4e  mov     r9d, ebx; char *
0x180016d51  mov     edx, 232h; void *
0x180016d56  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016d5b  jmp     loc_180016CA7
0x180016d60  mov     rcx, [rbp+28h]; this
0x180016d64  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x180016d6b  mov     r9d, ebx; char *
0x180016d6e  mov     edx, 238h; void *
0x180016d73  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016d78  mov     rcx, [rbp+var_10]
0x180016d7c  jmp     loc_180016C9B
0x180016d81  mov     rcx, [rbp+28h]; this
0x180016d85  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x180016d8c  mov     ebx, 8000FFFFh
0x180016d91  mov     edx, 235h; void *
0x180016d96  mov     r9d, ebx; char *
0x180016d99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016d9e  mov     rcx, [rbp+pbstr]; bstrString
0x180016da2  call    cs:__imp_SysFreeString
0x180016da9  nop     dword ptr [rax+rax+00h]
0x180016dae  mov     rcx, [rbp+arg_8]
0x180016db2  test    rcx, rcx
0x180016db5  jz      short loc_180016DC7
0x180016db7  mov     [rbp+arg_8], r15
0x180016dbb  mov     rax, [rcx]
0x180016dbe  mov     rax, [rax+10h]
0x180016dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dc7  mov     rcx, [rbp+arg_10]
0x180016dcb  test    rcx, rcx
0x180016dce  jz      loc_180016CE9
0x180016dd4  mov     [rbp+arg_10], r15
0x180016dd8  mov     rdx, [rcx]
0x180016ddb  mov     rax, [rdx+10h]
0x180016ddf  jmp     loc_180016CE4
0x180016de4  mov     rcx, [rbp+28h]; this
0x180016de8  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x180016def  mov     ebx, 80004003h
0x180016df4  mov     edx, 225h; void *
0x180016df9  mov     r9d, ebx; char *
0x180016dfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016e01  jmp     loc_180016CE9
0x180016e06  mov     rcx, [rbp+28h]; this
0x180016e0a  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x180016e11  mov     ebx, 8000FFFFh
0x180016e16  mov     edx, 230h; void *
0x180016e1b  mov     r9d, ebx; char *
0x180016e1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016e23  jmp     loc_180016D15
```
