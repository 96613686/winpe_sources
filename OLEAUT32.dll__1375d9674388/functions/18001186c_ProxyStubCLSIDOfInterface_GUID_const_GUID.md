# ProxyStubCLSIDOfInterface(_GUID const &,_GUID *)

- ea: `0x18001186c`
- end: `0x180011b1e`
- name: `?ProxyStubCLSIDOfInterface@@YAJAEBU_GUID@@PEAU1@@Z`
- size: `690`
- prototype: `__int64 __fastcall(GUID *rguid, struct _GUID *)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180010e00`
- `0x1800110d0`
- `0x18004b060`
- `0x18004b490`

## callees

- `0x18001186c`
- `0x180012750`
- `0x180014f04`
- `0x1800161b8`
- `0x18004d900`
- `0x18004ebb0`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001197f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011995`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001197f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011995`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180011904`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180011904`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800118e0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800118e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001195c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001195c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011969`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011969`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800118f1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800118f1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011a14`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011a14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011a67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011acd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011afc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011a67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011acd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011afc`
- `ext-ms-win-sxs-oleautomation-l1-1-0!SxsOleAut32MapIIDToProxyStubCLSID` at `0x1800118b7`
- `ext-ms-win-sxs-oleautomation-l1-1-0!SxsOleAut32MapIIDToProxyStubCLSID` at `0x1800118b7`

## string_xrefs

- `0x1800118f7`: `\ProxyStubClsid32`
- `0x180011a27`: `mincore\com\oleaut32\dispatch\psfactry.cpp`
- `0x180011abc`: `mincore\com\oleaut32\dispatch\psfactry.cpp`

## pseudocode

```c
__int64 __fastcall ProxyStubCLSIDOfInterface(GUID *rguid, struct _GUID *a2)
{
  __int64 result; // rax
  int v5; // edx
  LSTATUS ValueW; // ebx
  GUID v7; // xmm0
  HRESULT Instance; // eax
  unsigned int v9; // ebx
  HKEY v10; // rdi
  __int64 (__fastcall *v11)(HKEY, GUID *, HSTRING *, int *); // rbx
  int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  GUID v15; // xmm0
  HSTRING v16; // rcx
  int pdwType; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+54h] [rbp-ACh] BYREF
  int v22[4]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE pvData[80]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[10]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[118]; // [rsp+D4h] [rbp-2Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  pcbData = 0;
  if ( !(unsigned __int8)IsSxsOleAut32MapConfiguredClsidToReferenceClsidPresent() )
    goto LABEL_4;
  result = SxsOleAut32MapIIDToProxyStubCLSID(rguid, a2);
  if ( (int)result < 0 )
    return result;
  if ( (_DWORD)result == 1 )
  {
LABEL_4:
    _o_wcscpy_s(SubKey, 128, L"Interface\\");
    StringFromGUID2(rguid, sz, 40);
    _o_wcscat_s(SubKey, 128, L"\\ProxyStubClsid32");
    pcbData = 78;
    hkey = 0;
    if ( !(unsigned int)OpenClassesRootKeyExW(SubKey, v5, &hkey) )
    {
      ValueW = RegGetValueW(hkey, 0, 0, 6u, 0, pvData, &pcbData);
      RegCloseKey(hkey);
      if ( !ValueW )
      {
        if ( (unsigned int)_o__wcsicmp(pvData, L"{00020420-0000-0000-C000-000000000046}") )
        {
          if ( (unsigned int)_o__wcsicmp(pvData, L"{00020424-0000-0000-C000-000000000046}") )
            return 2147500037LL;
          v7 = CLSID_PSAutomation;
        }
        else
        {
          v7 = CLSID_PSDispatch;
        }
        *a2 = v7;
        return 0;
      }
    }
    hkey = 0;
    Microsoft::WRL::ComPtr<ITypeInfo>::InternalRelease(&hkey);
    Instance = CoCreateInstance(
                 &GUID_00000346_0000_0000_c000_000000000046,
                 0,
                 1u,
                 &GUID_419c4e35_36bc_4780_845d_a05c51d9f770,
                 (LPVOID *)&hkey);
    v9 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x209,
        (unsigned int)"mincore\\com\\oleaut32\\dispatch\\psfactry.cpp",
        (const char *)(unsigned int)Instance,
        pdwType);
LABEL_26:
      Microsoft::WRL::ComPtr<ITypeInfo>::InternalRelease(&hkey);
      return v9;
    }
    v10 = hkey;
    string = 0;
    v21 = 0;
    *(_OWORD *)v22 = 0;
    v11 = *(__int64 (__fastcall **)(HKEY, GUID *, HSTRING *, int *))(*(_QWORD *)hkey + 24LL);
    WindowsDeleteString(0);
    string = 0;
    v12 = v11(v10, rguid, &string, &v21);
    v9 = v12;
    if ( v12 < 0 )
    {
      v13 = (unsigned int)v12;
      v14 = 527;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"mincore\\com\\oleaut32\\dispatch\\psfactry.cpp",
        (const char *)v13,
        (int)v22);
      WindowsDeleteString(string);
LABEL_25:
      string = 0;
      goto LABEL_26;
    }
    if ( v21 == 1 )
    {
      v15 = CLSID_PSAutomation;
    }
    else
    {
      if ( v21 != 2 )
      {
        v9 = -2147467259;
        v14 = 540;
        v13 = 2147500037LL;
        goto LABEL_19;
      }
      v15 = CLSID_PSDispatch;
    }
    v16 = string;
    *a2 = v15;
    WindowsDeleteString(v16);
    v9 = 0;
    goto LABEL_25;
  }
  return 0;
}

```

## disassembly

```asm
0x18001186c  mov     [rsp-8+arg_10], rbx
0x180011871  mov     [rsp-8+arg_18], rsi
0x180011876  push    rbp
0x180011877  push    rdi
0x180011878  push    r14
0x18001187a  lea     rbp, [rsp-0D0h]
0x180011882  sub     rsp, 1D0h
0x180011889  mov     rax, cs:__security_cookie
0x180011890  xor     rax, rsp
0x180011893  mov     [rbp+0E0h+var_20], rax
0x18001189a  mov     rsi, rdx
0x18001189d  mov     [rsp+1E0h+var_190], 0
0x1800118a5  mov     r14, rcx
0x1800118a8  call    IsSxsOleAut32MapConfiguredClsidToReferenceClsidPresent
0x1800118ad  test    al, al
0x1800118af  jz      short loc_1800118CE
0x1800118b1  mov     rdx, rsi
0x1800118b4  mov     rcx, r14
0x1800118b7  call    cs:__imp_SxsOleAut32MapIIDToProxyStubCLSID
0x1800118bd  test    eax, eax
0x1800118bf  js      loc_1800119AC
0x1800118c5  cmp     eax, 1
0x1800118c8  jnz     loc_1800119AA
0x1800118ce  mov     ebx, 80h
0x1800118d3  lea     r8, aInterface; "Interface\\"
0x1800118da  mov     edx, ebx
0x1800118dc  lea     rcx, [rbp+0E0h+SubKey]
0x1800118e0  call    cs:__imp__o_wcscpy_s
0x1800118e6  lea     r8d, [rbx-58h]; cchMax
0x1800118ea  mov     rcx, r14; rguid
0x1800118ed  lea     rdx, [rbp+0E0h+sz]; lpsz
0x1800118f1  call    cs:__imp_StringFromGUID2
0x1800118f7  lea     r8, aProxystubclsid; "\\ProxyStubClsid32"
0x1800118fe  mov     edx, ebx
0x180011900  lea     rcx, [rbp+0E0h+SubKey]
0x180011904  call    cs:__imp__o_wcscat_s
0x18001190a  lea     r8, [rsp+1E0h+hkey]
0x18001190f  mov     [rsp+1E0h+var_190], 4Eh ; 'N'
0x180011917  lea     rcx, [rbp+0E0h+SubKey]; lpSubKey
0x18001191b  mov     [rsp+1E0h+hkey], 0
0x180011924  call    OpenClassesRootKeyExW
0x180011929  test    eax, eax
0x18001192b  jnz     loc_1800119E3
0x180011931  mov     rcx, [rsp+1E0h+hkey]; hkey
0x180011936  lea     rax, [rsp+1E0h+var_190]
0x18001193b  mov     [rsp+1E0h+pcbData], rax; pcbData
0x180011940  lea     r9d, [rbx-7Ah]; dwFlags
0x180011944  lea     rax, [rsp+1E0h+var_170]
0x180011949  xor     r8d, r8d; lpValue
0x18001194c  mov     [rsp+1E0h+pvData], rax; pvData
0x180011951  xor     edx, edx; lpSubKey
0x180011953  mov     [rsp+1E0h+pdwType], 0; pdwType
0x18001195c  call    cs:__imp_RegGetValueW
0x180011962  mov     rcx, [rsp+1E0h+hkey]; hKey
0x180011967  mov     ebx, eax
0x180011969  call    cs:__imp_RegCloseKey
0x18001196f  test    ebx, ebx
0x180011971  jnz     short loc_1800119E3
0x180011973  lea     rdx, a00020420000000; "{00020420-0000-0000-C000-000000000046}"
0x18001197a  lea     rcx, [rsp+1E0h+var_170]
0x18001197f  call    cs:__imp__o__wcsicmp
0x180011985  test    eax, eax
0x180011987  jz      short loc_1800119D3
0x180011989  lea     rdx, a00020424000000; "{00020424-0000-0000-C000-000000000046}"
0x180011990  lea     rcx, [rsp+1E0h+var_170]
0x180011995  call    cs:__imp__o__wcsicmp
0x18001199b  test    eax, eax
0x18001199d  jnz     short loc_1800119DC
0x18001199f  movups  xmm0, xmmword ptr cs:CLSID_PSAutomation.Data1
0x1800119a6  movdqu  xmmword ptr [rsi], xmm0
0x1800119aa  xor     eax, eax
0x1800119ac  mov     rcx, [rbp+0E0h+var_20]
0x1800119b3  xor     rcx, rsp; StackCookie
0x1800119b6  call    __security_check_cookie
0x1800119bb  lea     r11, [rsp+1E0h+var_10]
0x1800119c3  mov     rbx, [r11+30h]
0x1800119c7  mov     rsi, [r11+38h]
0x1800119cb  mov     rsp, r11
0x1800119ce  pop     r14
0x1800119d0  pop     rdi
0x1800119d1  pop     rbp
0x1800119d2  retn
0x1800119d3  movups  xmm0, xmmword ptr cs:CLSID_PSDispatch.Data1
0x1800119da  jmp     short loc_1800119A6
0x1800119dc  mov     eax, 80004005h
0x1800119e1  jmp     short loc_1800119AC
0x1800119e3  lea     rcx, [rsp+1E0h+hkey]
0x1800119e8  mov     [rsp+1E0h+hkey], 0
0x1800119f1  call    ?InternalRelease@?$ComPtr@UITypeInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ITypeInfo>::InternalRelease(void)
0x1800119f6  xor     edx, edx; pUnkOuter
0x1800119f8  lea     rax, [rsp+1E0h+hkey]
0x1800119fd  lea     r9, _GUID_419c4e35_36bc_4780_845d_a05c51d9f770; riid
0x180011a04  mov     [rsp+1E0h+pdwType], rax; int
0x180011a09  lea     rcx, _GUID_00000346_0000_0000_c000_000000000046; rclsid
0x180011a10  lea     r8d, [rdx+1]; dwClsContext
0x180011a14  call    cs:__imp_CoCreateInstance
0x180011a1a  mov     ebx, eax
0x180011a1c  test    eax, eax
0x180011a1e  jns     short loc_180011A40
0x180011a20  mov     rcx, [rbp+0E8h]; this
0x180011a27  lea     r8, aMincoreComOlea_2; "mincore\\com\\oleaut32\\dispatch\\psfac"...
0x180011a2e  mov     r9d, eax; char *
0x180011a31  mov     edx, 209h; void *
0x180011a36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011a3b  jmp     loc_180011B0D
0x180011a40  mov     rdi, [rsp+1E0h+hkey]
0x180011a45  xorps   xmm0, xmm0
0x180011a48  mov     [rsp+1E0h+string], 0
0x180011a51  xor     ecx, ecx; string
0x180011a53  mov     [rsp+1E0h+var_18C], 0
0x180011a5b  movups  xmmword ptr [rsp+1E0h+var_188], xmm0
0x180011a60  mov     rax, [rdi]
0x180011a63  mov     rbx, [rax+18h]
0x180011a67  call    cs:__imp_WindowsDeleteString
0x180011a6d  lea     rax, [rsp+1E0h+var_188]
0x180011a72  mov     [rsp+1E0h+string], 0
0x180011a7b  mov     [rsp+1E0h+pdwType], rax; int
0x180011a80  lea     r9, [rsp+1E0h+var_18C]
0x180011a85  mov     rax, rbx
0x180011a88  lea     r8, [rsp+1E0h+string]
0x180011a8d  mov     rdx, r14
0x180011a90  mov     rcx, rdi
0x180011a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a98  mov     ebx, eax
0x180011a9a  test    eax, eax
0x180011a9c  jns     short loc_180011AD5
0x180011a9e  mov     r9d, eax
0x180011aa1  mov     edx, 20Fh
0x180011aa6  jmp     short loc_180011AB5
0x180011aa8  mov     ebx, 80004005h
0x180011aad  mov     edx, 21Ch; void *
0x180011ab2  mov     r9d, ebx; char *
0x180011ab5  mov     rcx, [rbp+0E8h]; this
0x180011abc  lea     r8, aMincoreComOlea_2; "mincore\\com\\oleaut32\\dispatch\\psfac"...
0x180011ac3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011ac8  mov     rcx, [rsp+1E0h+string]; string
0x180011acd  call    cs:__imp_WindowsDeleteString
0x180011ad3  jmp     short loc_180011B04
0x180011ad5  mov     ecx, [rsp+1E0h+var_18C]
0x180011ad9  sub     ecx, 1
0x180011adc  jz      short loc_180011AEC
0x180011ade  cmp     ecx, 1
0x180011ae1  jnz     short loc_180011AA8
0x180011ae3  movups  xmm0, xmmword ptr cs:CLSID_PSDispatch.Data1
0x180011aea  jmp     short loc_180011AF3
0x180011aec  movups  xmm0, xmmword ptr cs:CLSID_PSAutomation.Data1
0x180011af3  mov     rcx, [rsp+1E0h+string]; string
0x180011af8  movdqu  xmmword ptr [rsi], xmm0
0x180011afc  call    cs:__imp_WindowsDeleteString
0x180011b02  xor     ebx, ebx
0x180011b04  mov     [rsp+1E0h+string], 0
0x180011b0d  lea     rcx, [rsp+1E0h+hkey]
0x180011b12  call    ?InternalRelease@?$ComPtr@UITypeInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ITypeInfo>::InternalRelease(void)
0x180011b17  mov     eax, ebx
0x180011b19  jmp     loc_1800119AC
```
