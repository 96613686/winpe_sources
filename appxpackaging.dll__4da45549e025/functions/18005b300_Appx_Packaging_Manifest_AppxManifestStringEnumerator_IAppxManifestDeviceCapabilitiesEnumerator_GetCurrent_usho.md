# Appx::Packaging::Manifest::AppxManifestStringEnumerator<IAppxManifestDeviceCapabilitiesEnumerator>::GetCurrent(ushort * *)

- ea: `0x18005b300`
- end: `0x18005b57a`
- name: `?GetCurrent@?$AppxManifestStringEnumerator@UIAppxManifestDeviceCapabilitiesEnumerator@@@Manifest@Packaging@Appx@@UEAAJPEAPEAG@Z`
- size: `634`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180016e30`
- `0x18001711c`
- `0x18005b300`
- `0x180071f50`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b4b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b569`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b4b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b569`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b3e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b43f`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b4c5`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b3e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b43f`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b4c5`
- `OLEAUT32!__imp_SysStringLen` at `0x18005b3b3`
- `OLEAUT32!__imp_SysStringLen` at `0x18005b3b3`

## string_xrefs

- `0x18005b3cb`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x18005b42c`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x18005b4e9`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x18005b50d`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x18005b52f`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x18005b551`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestStringEnumerator<IAppxManifestDeviceCapabilitiesEnumerator>::GetCurrent(
        __int64 a1,
        LPVOID *a2)
{
  unsigned int CurrentNode; // ebx
  struct IXMLDOMNode *v5; // rdi
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rbx
  int v7; // eax
  __int64 v8; // rcx
  struct IXMLDOMNode *v9; // rcx
  void (*Release)(void); // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  struct IXMLDOMNode *v13; // rcx
  int v15; // eax
  LPVOID pv[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  __int64 v18; // [rsp+68h] [rbp+38h] BYREF
  struct IXMLDOMNode *v19; // [rsp+70h] [rbp+40h] BYREF
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
    return CurrentNode;
  }
  v19 = 0;
  v18 = 0;
  pbstr = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v19);
  CurrentNode = Appx::Packaging::Manifest::AppxManifestEnumeratorBase::GetCurrentNode(
                  (Appx::Packaging::Manifest::AppxManifestEnumeratorBase *)(a1 + 16),
                  &v19);
  if ( (CurrentNode & 0x80000000) != 0 )
  {
    v11 = 556;
LABEL_12:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
      (const char *)CurrentNode,
      (int)pv[0]);
    goto LABEL_13;
  }
  v5 = v19;
  selectSingleNode = v19->lpVtbl->selectSingleNode;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v18);
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD, __int64 *))selectSingleNode)(
         v5,
         *(_QWORD *)(a1 + 32),
         &v18);
  CurrentNode = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x22E,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
      (const char *)(unsigned int)v7,
      (int)pv[0]);
    goto LABEL_21;
  }
  if ( !v18 )
  {
    CurrentNode = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x230,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
      (const char *)0x8000FFFFLL,
      (int)pv[0]);
    goto LABEL_21;
  }
  CurrentNode = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v18 + 208LL))(v18, &pbstr);
  if ( (CurrentNode & 0x80000000) != 0 )
  {
    v11 = 562;
    goto LABEL_12;
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
    SysFreeString(pbstr);
    v8 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    v9 = v19;
    if ( v19 )
    {
      v19 = 0;
      Release = (void (*)(void))v9->lpVtbl->Release;
LABEL_17:
      Release();
      return CurrentNode;
    }
    return CurrentNode;
  }
  pv[0] = 0;
  v15 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromBStr(
          pv,
          pbstr);
  CurrentNode = v15;
  if ( v15 >= 0 )
  {
    *a2 = pv[0];
    CoTaskMemFree(0);
LABEL_21:
    SysFreeString(pbstr);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v18);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v19);
    return CurrentNode;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x238,
    (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
    (const char *)(unsigned int)v15,
    (int)pv[0]);
  CoTaskMemFree(pv[0]);
LABEL_13:
  SysFreeString(pbstr);
  v12 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v13 = v19;
  if ( v19 )
  {
    v19 = 0;
    Release = (void (*)(void))v13->lpVtbl->Release;
    goto LABEL_17;
  }
  return CurrentNode;
}

```

## disassembly

```asm
0x18005b300  mov     [rsp-28h+arg_0], rbx
0x18005b305  push    rbp
0x18005b306  push    rsi
0x18005b307  push    rdi
0x18005b308  push    r14
0x18005b30a  push    r15
0x18005b30c  mov     rbp, rsp
0x18005b30f  sub     rsp, 30h
0x18005b313  xor     r15d, r15d
0x18005b316  mov     rsi, rdx
0x18005b319  mov     r14, rcx
0x18005b31c  test    rdx, rdx
0x18005b31f  jz      loc_18005B509
0x18005b325  lea     rcx, [rbp+arg_10]
0x18005b329  mov     [rbp+arg_10], r15
0x18005b32d  mov     [rbp+arg_8], r15
0x18005b331  mov     [rbp+pbstr], r15
0x18005b335  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005b33a  lea     rcx, [r14+10h]; this
0x18005b33e  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18005b342  call    ?GetCurrentNode@AppxManifestEnumeratorBase@Manifest@Packaging@Appx@@IEAAJPEAPEAUIXMLDOMNode@@@Z; Appx::Packaging::Manifest::AppxManifestEnumeratorBase::GetCurrentNode(IXMLDOMNode * *)
0x18005b347  mov     ebx, eax
0x18005b349  test    eax, eax
0x18005b34b  js      loc_18005B423
0x18005b351  mov     rdi, [rbp+arg_10]
0x18005b355  lea     rcx, [rbp+arg_8]
0x18005b359  mov     rax, [rdi]
0x18005b35c  mov     rbx, [rax+128h]
0x18005b363  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005b368  mov     rdx, [r14+20h]
0x18005b36c  lea     r8, [rbp+arg_8]
0x18005b370  mov     rcx, rdi
0x18005b373  mov     rax, rbx
0x18005b376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b37b  mov     ebx, eax
0x18005b37d  test    eax, eax
0x18005b37f  js      loc_18005B4E5
0x18005b385  mov     rcx, [rbp+arg_8]
0x18005b389  test    rcx, rcx
0x18005b38c  jz      loc_18005B52B
0x18005b392  mov     rax, [rcx]
0x18005b395  lea     rdx, [rbp+pbstr]
0x18005b399  mov     rax, [rax+0D0h]
0x18005b3a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b3a5  mov     ebx, eax
0x18005b3a7  test    eax, eax
0x18005b3a9  js      loc_18005B4FF
0x18005b3af  mov     rcx, [rbp+pbstr]; pbstr
0x18005b3b3  call    cs:__imp_SysStringLen
0x18005b3ba  nop     dword ptr [rax+rax+00h]
0x18005b3bf  test    eax, eax
0x18005b3c1  jnz     loc_18005B491
0x18005b3c7  mov     rcx, [rbp+28h]; this
0x18005b3cb  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x18005b3d2  mov     ebx, 8000FFFFh
0x18005b3d7  mov     edx, 235h; void *
0x18005b3dc  mov     r9d, ebx; char *
0x18005b3df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b3e4  mov     rcx, [rbp+pbstr]; bstrString
0x18005b3e8  call    cs:__imp_SysFreeString
0x18005b3ef  nop     dword ptr [rax+rax+00h]
0x18005b3f4  mov     rcx, [rbp+arg_8]
0x18005b3f8  test    rcx, rcx
0x18005b3fb  jz      short loc_18005B40D
0x18005b3fd  mov     [rbp+arg_8], r15
0x18005b401  mov     rax, [rcx]
0x18005b404  mov     rax, [rax+10h]
0x18005b408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b40d  mov     rcx, [rbp+arg_10]
0x18005b411  test    rcx, rcx
0x18005b414  jz      short loc_18005B47D
0x18005b416  mov     [rbp+arg_10], r15
0x18005b41a  mov     rdx, [rcx]
0x18005b41d  mov     rax, [rdx+10h]
0x18005b421  jmp     short loc_18005B478
0x18005b423  mov     edx, 22Ch; void *
0x18005b428  mov     rcx, [rbp+28h]; this
0x18005b42c  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x18005b433  mov     r9d, ebx; char *
0x18005b436  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005b43b  mov     rcx, [rbp+pbstr]; bstrString
0x18005b43f  call    cs:__imp_SysFreeString
0x18005b446  nop     dword ptr [rax+rax+00h]
0x18005b44b  mov     rcx, [rbp+arg_8]
0x18005b44f  test    rcx, rcx
0x18005b452  jz      short loc_18005B464
0x18005b454  mov     [rbp+arg_8], r15
0x18005b458  mov     rax, [rcx]
0x18005b45b  mov     rax, [rax+10h]
0x18005b45f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b464  mov     rcx, [rbp+arg_10]
0x18005b468  test    rcx, rcx
0x18005b46b  jz      short loc_18005B47D
0x18005b46d  mov     [rbp+arg_10], r15
0x18005b471  mov     rax, [rcx]
0x18005b474  mov     rax, [rax+10h]
0x18005b478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b47d  mov     eax, ebx
0x18005b47f  mov     rbx, [rsp+30h+arg_0]
0x18005b484  add     rsp, 30h
0x18005b488  pop     r15
0x18005b48a  pop     r14
0x18005b48c  pop     rdi
0x18005b48d  pop     rsi
0x18005b48e  pop     rbp
0x18005b48f  retn
0x18005b491  mov     rdx, [rbp+pbstr]
0x18005b495  lea     rcx, [rbp+pv]
0x18005b499  mov     [rbp+pv], r15
0x18005b49d  call    ?CopyFromBStr@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJQEAG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromBStr(ushort * const)
0x18005b4a2  mov     ebx, eax
0x18005b4a4  test    eax, eax
0x18005b4a6  js      loc_18005B54D
0x18005b4ac  mov     rax, [rbp+pv]
0x18005b4b0  xor     ecx, ecx; pv
0x18005b4b2  mov     [rsi], rax
0x18005b4b5  call    cs:__imp_CoTaskMemFree
0x18005b4bc  nop     dword ptr [rax+rax+00h]
0x18005b4c1  mov     rcx, [rbp+pbstr]; bstrString
0x18005b4c5  call    cs:__imp_SysFreeString
0x18005b4cc  nop     dword ptr [rax+rax+00h]
0x18005b4d1  lea     rcx, [rbp+arg_8]
0x18005b4d5  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005b4da  lea     rcx, [rbp+arg_10]
0x18005b4de  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005b4e3  jmp     short loc_18005B47D
0x18005b4e5  mov     rcx, [rbp+28h]; this
0x18005b4e9  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x18005b4f0  mov     r9d, eax; char *
0x18005b4f3  mov     edx, 22Eh; void *
0x18005b4f8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005b4fd  jmp     short loc_18005B4C1
0x18005b4ff  mov     edx, 232h
0x18005b504  jmp     loc_18005B428
0x18005b509  mov     rcx, [rbp+28h]; this
0x18005b50d  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x18005b514  mov     ebx, 80004003h
0x18005b519  mov     edx, 225h; void *
0x18005b51e  mov     r9d, ebx; char *
0x18005b521  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b526  jmp     loc_18005B47D
0x18005b52b  mov     rcx, [rbp+28h]; this
0x18005b52f  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x18005b536  mov     ebx, 8000FFFFh
0x18005b53b  mov     edx, 230h; void *
0x18005b540  mov     r9d, ebx; char *
0x18005b543  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b548  jmp     loc_18005B4C1
0x18005b54d  mov     rcx, [rbp+28h]; this
0x18005b551  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x18005b558  mov     r9d, ebx; char *
0x18005b55b  mov     edx, 238h; void *
0x18005b560  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005b565  mov     rcx, [rbp+pv]; pv
0x18005b569  call    cs:__imp_CoTaskMemFree
0x18005b570  nop     dword ptr [rax+rax+00h]
0x18005b575  jmp     loc_18005B43B
```
