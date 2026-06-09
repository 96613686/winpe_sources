# LCIEGetEDPHostPolicyForUrl

- ea: `0x18010fa94`
- end: `0x18010fc76`
- name: `LCIEGetEDPHostPolicyForUrl`
- size: `482`
- prototype: `__int64 __fastcall(LPCWSTR pwzURI)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18010fc7c`

## callees

- `0x18003b010`
- `0x1800476d0`
- `0x18008a620`
- `0x18009f5f0`
- `0x18010effc`
- `0x18010f0c8`
- `0x18010f448`
- `0x18010fa94`
- `0x18010fef8`
- `0x18011a410`
- `0x18011c010`

## import_xrefs

- `iertutil!CreateUri` at `0x18010faeb`
- `iertutil!CreateUri` at `0x18010faeb`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010fb40`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010fbee`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010fc19`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010fb40`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010fbee`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010fc19`
- `OLEAUT32!__imp_SysAllocString` at `0x18010fb52`
- `OLEAUT32!__imp_SysAllocString` at `0x18010fc00`
- `OLEAUT32!__imp_SysAllocString` at `0x18010fc2b`
- `OLEAUT32!__imp_SysAllocString` at `0x18010fb52`
- `OLEAUT32!__imp_SysAllocString` at `0x18010fc00`
- `OLEAUT32!__imp_SysAllocString` at `0x18010fc2b`
- `OLEAUT32!__imp_SysFreeString` at `0x18010fbd0`
- `OLEAUT32!__imp_SysFreeString` at `0x18010fc47`
- `OLEAUT32!__imp_SysFreeString` at `0x18010fbd0`
- `OLEAUT32!__imp_SysFreeString` at `0x18010fc47`

## pseudocode

```c
__int64 __fastcall LCIEGetEDPHostPolicyForUrl(WCHAR *pwzURI, int a2, BSTR *a3, _BYTE *a4)
{
  int EDPHostPolicyForFile; // ebx
  DWORD v9; // eax
  int v10; // eax
  const OLECHAR *CurrentEnterpriseID; // rax
  IUri *v12; // rdi
  HRESULT (__stdcall *GetPropertyBSTR)(IUri *, Uri_PROPERTY, BSTR *, DWORD); // rbx
  const OLECHAR *v14; // rax
  const OLECHAR *v15; // rax
  BSTR bstrString[2]; // [rsp+30h] [rbp-10h] BYREF
  int v18; // [rsp+80h] [rbp+40h] BYREF
  IUri *ppURI; // [rsp+88h] [rbp+48h] BYREF

  EDPHostPolicyForFile = 0;
  *a4 = 0;
  if ( a3 && BrowserUtilEdp::IsEdpEnforcementEnabled((BrowserUtilEdp *)pwzURI) )
  {
    ppURI = 0;
    v9 = HelperAddUriDefaultFlags(0x3002B80u, 4u);
    if ( CreateUri(pwzURI, v9, 0, &ppURI) < 0 )
      goto LABEL_28;
    v18 = 0;
    if ( ((unsigned int (__fastcall *)(IUri *, int *))ppURI->lpVtbl->GetScheme)(ppURI, &v18) )
      goto LABEL_28;
    if ( v18 == 9 )
    {
      EDPHostPolicyForFile = GetEDPHostPolicyForFile(ppURI);
    }
    else
    {
      v10 = IsEDPModeNeutralIUri(ppURI);
      if ( !a2 )
      {
        if ( v10 )
        {
          *a4 = 1;
          if ( (unsigned __int8)IEConfiguration_GetBool(536870914) )
          {
            CurrentEnterpriseID = (const OLECHAR *)GetCurrentEnterpriseID();
            *a3 = SysAllocString(CurrentEnterpriseID);
          }
        }
      }
      if ( *a4 )
        goto LABEL_28;
      if ( !(unsigned __int8)UriUsesNetwork(ppURI) )
      {
        if ( !a2 )
          *a4 = 1;
        if ( (unsigned __int8)IEConfiguration_GetBool(536870914) )
        {
          v15 = (const OLECHAR *)GetCurrentEnterpriseID();
          *a3 = SysAllocString(v15);
        }
        goto LABEL_28;
      }
      v12 = ppURI;
      bstrString[0] = 0;
      GetPropertyBSTR = ppURI->lpVtbl->GetPropertyBSTR;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        bstrString,
        0);
      EDPHostPolicyForFile = ((__int64 (__fastcall *)(IUri *, __int64, BSTR *))GetPropertyBSTR)(v12, 6, bstrString);
      if ( !EDPHostPolicyForFile )
      {
        EDPHostPolicyForFile = NetworkIsolationGetEnterpriseIdSync(bstrString[0]);
        if ( EDPHostPolicyForFile == -2147023436 )
          EDPHostPolicyForFile = 0;
      }
      if ( bstrString[0] )
        SysFreeString(bstrString[0]);
      if ( EDPHostPolicyForFile == -2147013895 )
      {
        if ( a2 )
        {
LABEL_27:
          SysFreeString(*a3);
          EDPHostPolicyForFile = 0;
          *a3 = 0;
          *a4 = 0;
          goto LABEL_28;
        }
        *a4 = 1;
        EDPHostPolicyForFile = 0;
        if ( !(unsigned __int8)IEConfiguration_GetBool(536870914) )
        {
LABEL_28:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppURI);
          return (unsigned int)EDPHostPolicyForFile;
        }
        v14 = (const OLECHAR *)GetCurrentEnterpriseID();
        *a3 = SysAllocString(v14);
      }
    }
    if ( EDPHostPolicyForFile < 0 )
      goto LABEL_27;
    goto LABEL_28;
  }
  return (unsigned int)EDPHostPolicyForFile;
}

```

## disassembly

```asm
0x18010fa94  mov     [rsp-28h+arg_0], rbx
0x18010fa99  push    rbp
0x18010fa9a  push    rsi
0x18010fa9b  push    rdi
0x18010fa9c  push    r14
0x18010fa9e  push    r15
0x18010faa0  mov     rbp, rsp
0x18010faa3  sub     rsp, 40h
0x18010faa7  xor     ebx, ebx
0x18010faa9  mov     r14, r9
0x18010faac  mov     [r9], bl
0x18010faaf  mov     rsi, r8
0x18010fab2  mov     r15d, edx
0x18010fab5  mov     rdi, rcx
0x18010fab8  test    r8, r8
0x18010fabb  jz      loc_18010FC63
0x18010fac1  call    ?IsEdpEnforcementEnabled@BrowserUtilEdp@@YA_NXZ; BrowserUtilEdp::IsEdpEnforcementEnabled(void)
0x18010fac6  test    al, al
0x18010fac8  jz      loc_18010FC63
0x18010face  lea     edx, [rbx+4]; unsigned int
0x18010fad1  mov     [rbp+ppURI], rbx
0x18010fad5  mov     ecx, 3002B80h; unsigned int
0x18010fada  call    ?HelperAddUriDefaultFlags@@YAKKK@Z; HelperAddUriDefaultFlags(ulong,ulong)
0x18010fadf  mov     edx, eax; dwFlags
0x18010fae1  lea     r9, [rbp+ppURI]; ppURI
0x18010fae5  mov     rcx, rdi; pwzURI
0x18010fae8  xor     r8d, r8d; dwReserved
0x18010faeb  call    cs:__imp_CreateUri
0x18010faf1  test    eax, eax
0x18010faf3  js      loc_18010FC5A
0x18010faf9  mov     rcx, [rbp+ppURI]
0x18010fafd  lea     rdx, [rbp+arg_10]
0x18010fb01  mov     [rbp+arg_10], ebx
0x18010fb04  mov     rax, [rcx]
0x18010fb07  mov     rax, [rax+0C0h]
0x18010fb0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fb13  test    eax, eax
0x18010fb15  jnz     loc_18010FC5A
0x18010fb1b  cmp     [rbp+arg_10], 9
0x18010fb1f  mov     rcx, [rbp+ppURI]; struct IUri *
0x18010fb23  jz      loc_18010FC36
0x18010fb29  call    ?IsEDPModeNeutralIUri@@YAHPEAUIUri@@@Z; IsEDPModeNeutralIUri(IUri *)
0x18010fb2e  test    r15d, r15d
0x18010fb31  jnz     short loc_18010FB5B
0x18010fb33  test    eax, eax
0x18010fb35  jz      short loc_18010FB5B
0x18010fb37  mov     ecx, 20000002h
0x18010fb3c  mov     byte ptr [r14], 1
0x18010fb40  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18010fb46  test    al, al
0x18010fb48  jz      short loc_18010FB5B
0x18010fb4a  call    GetCurrentEnterpriseID
0x18010fb4f  mov     rcx, rax; psz
0x18010fb52  call    cs:__imp_SysAllocString
0x18010fb58  mov     [rsi], rax
0x18010fb5b  cmp     [r14], bl
0x18010fb5e  jnz     loc_18010FC5A
0x18010fb64  mov     rcx, [rbp+ppURI]; struct IUri *
0x18010fb68  call    UriUsesNetwork
0x18010fb6d  test    al, al
0x18010fb6f  jz      loc_18010FC0B
0x18010fb75  mov     rdi, [rbp+ppURI]
0x18010fb79  lea     rcx, [rbp+bstrString]
0x18010fb7d  mov     [rbp+bstrString], rbx
0x18010fb81  xor     edx, edx
0x18010fb83  mov     rax, [rdi]
0x18010fb86  mov     rbx, [rax+18h]
0x18010fb8a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18010fb8f  mov     r9d, 2
0x18010fb95  lea     r8, [rbp+bstrString]
0x18010fb99  mov     rcx, rdi
0x18010fb9c  mov     rax, rbx
0x18010fb9f  lea     edx, [r9+4]
0x18010fba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fba8  mov     ebx, eax
0x18010fbaa  test    eax, eax
0x18010fbac  jnz     short loc_18010FBC7
0x18010fbae  mov     rcx, [rbp+bstrString]; wszServerName
0x18010fbb2  mov     rdx, rsi
0x18010fbb5  call    NetworkIsolationGetEnterpriseIdSync
0x18010fbba  mov     ebx, eax
0x18010fbbc  xor     eax, eax
0x18010fbbe  cmp     ebx, 800705B4h
0x18010fbc4  cmovz   ebx, eax
0x18010fbc7  mov     rcx, [rbp+bstrString]; bstrString
0x18010fbcb  test    rcx, rcx
0x18010fbce  jz      short loc_18010FBD6
0x18010fbd0  call    cs:__imp_SysFreeString
0x18010fbd6  cmp     ebx, 80072AF9h
0x18010fbdc  jnz     short loc_18010FC40
0x18010fbde  test    r15d, r15d
0x18010fbe1  jnz     short loc_18010FC44
0x18010fbe3  mov     ecx, 20000002h
0x18010fbe8  mov     byte ptr [r14], 1
0x18010fbec  xor     ebx, ebx
0x18010fbee  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18010fbf4  test    al, al
0x18010fbf6  jz      short loc_18010FC5A
0x18010fbf8  call    GetCurrentEnterpriseID
0x18010fbfd  mov     rcx, rax; psz
0x18010fc00  call    cs:__imp_SysAllocString
0x18010fc06  mov     [rsi], rax
0x18010fc09  jmp     short loc_18010FC40
0x18010fc0b  test    r15d, r15d
0x18010fc0e  jnz     short loc_18010FC14
0x18010fc10  mov     byte ptr [r14], 1
0x18010fc14  mov     ecx, 20000002h
0x18010fc19  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18010fc1f  test    al, al
0x18010fc21  jz      short loc_18010FC5A
0x18010fc23  call    GetCurrentEnterpriseID
0x18010fc28  mov     rcx, rax; psz
0x18010fc2b  call    cs:__imp_SysAllocString
0x18010fc31  mov     [rsi], rax
0x18010fc34  jmp     short loc_18010FC5A
0x18010fc36  mov     rdx, rsi
0x18010fc39  call    GetEDPHostPolicyForFile
0x18010fc3e  mov     ebx, eax
0x18010fc40  test    ebx, ebx
0x18010fc42  jns     short loc_18010FC5A
0x18010fc44  mov     rcx, [rsi]; bstrString
0x18010fc47  call    cs:__imp_SysFreeString
0x18010fc4d  xor     ebx, ebx
0x18010fc4f  mov     qword ptr [rsi], 0
0x18010fc56  mov     byte ptr [r14], 0
0x18010fc5a  lea     rcx, [rbp+ppURI]
0x18010fc5e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18010fc63  mov     eax, ebx
0x18010fc65  mov     rbx, [rsp+40h+arg_0]
0x18010fc6a  add     rsp, 40h
0x18010fc6e  pop     r15
0x18010fc70  pop     r14
0x18010fc72  pop     rdi
0x18010fc73  pop     rsi
0x18010fc74  pop     rbp
0x18010fc75  retn
```
