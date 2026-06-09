# Appx::Packaging::Manifest::AppxManifestStringEnumerator<IAppxContentGroupFilesEnumerator>::GetCurrent(ushort * *)

- ea: `0x1800ec450`
- end: `0x1800ec5fa`
- name: `?GetCurrent@?$AppxManifestStringEnumerator@UIAppxContentGroupFilesEnumerator@@@Manifest@Packaging@Appx@@UEAAJPEAPEAG@Z`
- size: `426`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180016e30`
- `0x18001711c`
- `0x180071f50`
- `0x1800ec450`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec5be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec5be`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ec5ce`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ec5ce`
- `OLEAUT32!__imp_SysStringLen` at `0x1800ec565`
- `OLEAUT32!__imp_SysStringLen` at `0x1800ec565`

## string_xrefs

- `0x1800ec46d`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x1800ec515`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x1800ec553`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x1800ec59b`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestStringEnumerator<IAppxContentGroupFilesEnumerator>::GetCurrent(
        __int64 a1,
        _QWORD *a2)
{
  unsigned int v4; // ebx
  int CurrentNode; // eax
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  struct IXMLDOMNode *v8; // rdi
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rbx
  int v10; // eax
  __int64 v11; // rdx
  int v12; // eax
  void *v13; // rcx
  LPVOID v15; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  BSTR pbstr; // [rsp+68h] [rbp+38h] BYREF
  __int64 v18; // [rsp+70h] [rbp+40h] BYREF
  struct IXMLDOMNode *v19; // [rsp+78h] [rbp+48h] BYREF

  if ( a2 )
  {
    v19 = 0;
    v18 = 0;
    pbstr = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v19);
    CurrentNode = Appx::Packaging::Manifest::AppxManifestEnumeratorBase::GetCurrentNode(
                    (Appx::Packaging::Manifest::AppxManifestEnumeratorBase *)(a1 + 16),
                    &v19);
    v4 = CurrentNode;
    if ( CurrentNode < 0 )
    {
      v6 = (unsigned int)CurrentNode;
      v7 = 556;
LABEL_13:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
        (const char *)v6,
        (int)v15);
      goto LABEL_20;
    }
    v8 = v19;
    selectSingleNode = v19->lpVtbl->selectSingleNode;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v18);
    v10 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD, __int64 *))selectSingleNode)(
            v8,
            *(_QWORD *)(a1 + 32),
            &v18);
    v4 = v10;
    if ( v10 < 0 )
    {
      v7 = 558;
LABEL_12:
      v6 = (unsigned int)v10;
      goto LABEL_13;
    }
    if ( v18 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v18 + 208LL))(v18, &pbstr);
      v4 = v10;
      if ( v10 < 0 )
      {
        v7 = 562;
        goto LABEL_12;
      }
      if ( SysStringLen(pbstr) )
      {
        v15 = 0;
        v12 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromBStr(
                &v15,
                pbstr);
        v4 = v12;
        if ( v12 >= 0 )
        {
          v13 = 0;
          *a2 = v15;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x238,
            (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
            (const char *)(unsigned int)v12,
            (int)v15);
          v13 = v15;
        }
        CoTaskMemFree(v13);
        goto LABEL_20;
      }
      v11 = 565;
    }
    else
    {
      v11 = 560;
    }
    v4 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
      (const char *)0x8000FFFFLL,
      (int)v15);
LABEL_20:
    SysFreeString(pbstr);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v18);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v19);
    return v4;
  }
  v4 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x225,
    (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
    (const char *)0x80004003LL,
    (int)v15);
  return v4;
}

```

## disassembly

```asm
0x1800ec450  push    rbp
0x1800ec452  push    rbx
0x1800ec453  push    rsi
0x1800ec454  push    rdi
0x1800ec455  push    r14
0x1800ec457  mov     rbp, rsp
0x1800ec45a  sub     rsp, 30h
0x1800ec45e  mov     rsi, rdx
0x1800ec461  mov     r14, rcx
0x1800ec464  test    rdx, rdx
0x1800ec467  jnz     short loc_1800EC48B
0x1800ec469  mov     rcx, [rbp+28h]; this
0x1800ec46d  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x1800ec474  mov     ebx, 80004003h
0x1800ec479  mov     edx, 225h; void *
0x1800ec47e  mov     r9d, ebx; char *
0x1800ec481  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec486  jmp     loc_1800EC5EC
0x1800ec48b  lea     rcx, [rbp+arg_18]
0x1800ec48f  mov     [rbp+arg_18], 0
0x1800ec497  mov     [rbp+arg_10], 0
0x1800ec49f  mov     [rbp+pbstr], 0
0x1800ec4a7  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800ec4ac  lea     rcx, [r14+10h]; this
0x1800ec4b0  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x1800ec4b4  call    ?GetCurrentNode@AppxManifestEnumeratorBase@Manifest@Packaging@Appx@@IEAAJPEAPEAUIXMLDOMNode@@@Z; Appx::Packaging::Manifest::AppxManifestEnumeratorBase::GetCurrentNode(IXMLDOMNode * *)
0x1800ec4b9  mov     ebx, eax
0x1800ec4bb  test    eax, eax
0x1800ec4bd  jns     short loc_1800EC4CC
0x1800ec4bf  mov     r9d, eax
0x1800ec4c2  mov     edx, 22Ch
0x1800ec4c7  jmp     loc_1800EC54F
0x1800ec4cc  mov     rdi, [rbp+arg_18]
0x1800ec4d0  lea     rcx, [rbp+arg_10]
0x1800ec4d4  mov     rax, [rdi]
0x1800ec4d7  mov     rbx, [rax+128h]
0x1800ec4de  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800ec4e3  mov     rdx, [r14+20h]
0x1800ec4e7  lea     r8, [rbp+arg_10]
0x1800ec4eb  mov     rcx, rdi
0x1800ec4ee  mov     rax, rbx
0x1800ec4f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec4f6  mov     ebx, eax
0x1800ec4f8  test    eax, eax
0x1800ec4fa  jns     short loc_1800EC503
0x1800ec4fc  mov     edx, 22Eh
0x1800ec501  jmp     short loc_1800EC54C
0x1800ec503  mov     rcx, [rbp+arg_10]
0x1800ec507  test    rcx, rcx
0x1800ec50a  jnz     short loc_1800EC52E
0x1800ec50c  mov     edx, 230h; void *
0x1800ec511  mov     rcx, [rbp+28h]; this
0x1800ec515  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x1800ec51c  mov     ebx, 8000FFFFh
0x1800ec521  mov     r9d, ebx; char *
0x1800ec524  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec529  jmp     loc_1800EC5CA
0x1800ec52e  mov     rax, [rcx]
0x1800ec531  lea     rdx, [rbp+pbstr]
0x1800ec535  mov     rax, [rax+0D0h]
0x1800ec53c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec541  mov     ebx, eax
0x1800ec543  test    eax, eax
0x1800ec545  jns     short loc_1800EC561
0x1800ec547  mov     edx, 232h; void *
0x1800ec54c  mov     r9d, eax; char *
0x1800ec54f  mov     rcx, [rbp+28h]; this
0x1800ec553  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x1800ec55a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ec55f  jmp     short loc_1800EC5CA
0x1800ec561  mov     rcx, [rbp+pbstr]; pbstr
0x1800ec565  call    cs:__imp_SysStringLen
0x1800ec56c  nop     dword ptr [rax+rax+00h]
0x1800ec571  test    eax, eax
0x1800ec573  jnz     short loc_1800EC57C
0x1800ec575  mov     edx, 235h
0x1800ec57a  jmp     short loc_1800EC511
0x1800ec57c  mov     rdx, [rbp+pbstr]
0x1800ec580  lea     rcx, [rbp+var_10]
0x1800ec584  mov     [rbp+var_10], 0
0x1800ec58c  call    ?CopyFromBStr@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJQEAG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromBStr(ushort * const)
0x1800ec591  mov     ebx, eax
0x1800ec593  test    eax, eax
0x1800ec595  jns     short loc_1800EC5B5
0x1800ec597  mov     rcx, [rbp+28h]; this
0x1800ec59b  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x1800ec5a2  mov     r9d, eax; char *
0x1800ec5a5  mov     edx, 238h; void *
0x1800ec5aa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ec5af  mov     rcx, [rbp+var_10]
0x1800ec5b3  jmp     short loc_1800EC5BE
0x1800ec5b5  mov     rax, [rbp+var_10]
0x1800ec5b9  xor     ecx, ecx; pv
0x1800ec5bb  mov     [rsi], rax
0x1800ec5be  call    cs:__imp_CoTaskMemFree
0x1800ec5c5  nop     dword ptr [rax+rax+00h]
0x1800ec5ca  mov     rcx, [rbp+pbstr]; bstrString
0x1800ec5ce  call    cs:__imp_SysFreeString
0x1800ec5d5  nop     dword ptr [rax+rax+00h]
0x1800ec5da  lea     rcx, [rbp+arg_10]
0x1800ec5de  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800ec5e3  lea     rcx, [rbp+arg_18]
0x1800ec5e7  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800ec5ec  mov     eax, ebx
0x1800ec5ee  add     rsp, 30h
0x1800ec5f2  pop     r14
0x1800ec5f4  pop     rdi
0x1800ec5f5  pop     rsi
0x1800ec5f6  pop     rbx
0x1800ec5f7  pop     rbp
0x1800ec5f8  retn
```
