# DmGetWindowsAIKKeyFromProviderInternal(ushort const *,int,unsigned __int64 *)

- ea: `0x18008b33c`
- end: `0x18008b4c5`
- name: `?DmGetWindowsAIKKeyFromProviderInternal@@YAJPEBGHPEA_K@Z`
- size: `393`
- prototype: `__int64 __fastcall(wchar_t *String1, int, unsigned __int64 *)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180087674`
- `0x180087920`
- `0x180088330`
- `0x18008aab0`
- `0x18008b330`

## callees

- `0x180053c78`
- `0x18005427c`
- `0x18005cb4c`
- `0x180062728`
- `0x18008b33c`
- `0x18008b7dc`
- `0x1800b2690`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x18008b3f1`
- `ncrypt!NCryptFreeObject` at `0x18008b3f1`
- `ncrypt!NCryptOpenStorageProvider` at `0x18008b385`
- `ncrypt!NCryptOpenStorageProvider` at `0x18008b385`
- `ncrypt!NCryptOpenKey` at `0x18008b428`
- `ncrypt!NCryptOpenKey` at `0x18008b428`

## string_xrefs

- `0x18008b3ac`: `DmGetWindowsAIKKeyFromProviderInternal: NCryptOpenStorageProvider`
- `0x18008b447`: `DmGetWindowsAIKKeyFromProviderInternal: NCryptOpenKey(aik)`

## pseudocode

```c
__int64 __fastcall DmGetWindowsAIKKeyFromProviderInternal(wchar_t *String1, int a2, unsigned __int64 *a3)
{
  SECURITY_STATUS v6; // edi
  const wchar_t *v7; // r8
  NCRYPT_HANDLE v8; // rdi
  _BYTE v10[16]; // [rsp+30h] [rbp-10h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+60h] [rbp+20h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+78h] [rbp+38h] BYREF

  phProvider = 0;
  hObject = 0;
  if ( !String1 || !a3 )
  {
    v6 = -2147024809;
    if ( a2 != 1 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_20;
    v7 = L"DmGetWindowsAIKKeyFromProviderInternal: Invalid argument(s)";
    goto LABEL_19;
  }
  v6 = NCryptOpenStorageProvider(&phProvider, String1, 0);
  if ( v6 < 0 )
  {
    if ( a2 != 1 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_20;
    v7 = L"DmGetWindowsAIKKeyFromProviderInternal: NCryptOpenStorageProvider";
    goto LABEL_19;
  }
  if ( !wcsncmp_0(String1, L"Microsoft Platform Crypto Provider", 0x2Au) )
    DmSetWindowsAIKStorageLocation(phProvider, a2);
  v8 = hObject;
  if ( hObject )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v10);
    NCryptFreeObject(v8);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v10);
  }
  hObject = 0;
  v6 = NCryptOpenKey(phProvider, &hObject, L"Windows AIK", 0, 0);
  if ( v6 >= 0 )
  {
    *a3 = hObject;
    hObject = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    return 0;
  }
  if ( a2 == 1 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
  {
    v7 = L"DmGetWindowsAIKKeyFromProviderInternal: NCryptOpenKey(aik)";
LABEL_19:
    McTemplateU0zd_EventWriteTransfer(String1, EnterpriseDiagnosticsTPMFunctionFailure, v7, (unsigned int)v6);
  }
LABEL_20:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18008b33c  mov     [rsp-18h+arg_8], rbx
0x18008b341  mov     [rsp-18h+arg_10], rsi
0x18008b346  push    rbp
0x18008b347  push    rdi
0x18008b348  push    r14
0x18008b34a  mov     rbp, rsp
0x18008b34d  sub     rsp, 40h
0x18008b351  mov     [rbp+phProvider], 0
0x18008b359  mov     r14, r8
0x18008b35c  mov     [rbp+hObject], 0
0x18008b364  mov     ebx, edx
0x18008b366  mov     rsi, rcx
0x18008b369  test    rcx, rcx
0x18008b36c  jz      loc_18008B475
0x18008b372  test    r8, r8
0x18008b375  jz      loc_18008B475
0x18008b37b  mov     rdx, rcx; pszProviderName
0x18008b37e  xor     r8d, r8d; dwFlags
0x18008b381  lea     rcx, [rbp+phProvider]; phProvider
0x18008b385  call    cs:__imp_NCryptOpenStorageProvider
0x18008b38c  nop     dword ptr [rax+rax+00h]
0x18008b391  mov     edi, eax
0x18008b393  test    eax, eax
0x18008b395  jns     short loc_18008B3B8
0x18008b397  cmp     ebx, 1
0x18008b39a  jnz     loc_18008B49D
0x18008b3a0  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, bl
0x18008b3a6  jz      loc_18008B49D
0x18008b3ac  lea     r8, aDmgetwindowsai_3; "DmGetWindowsAIKKeyFromProviderInternal:"...
0x18008b3b3  jmp     loc_18008B48E
0x18008b3b8  mov     r8d, 2Ah ; '*'; MaxCount
0x18008b3be  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x18008b3c5  mov     rcx, rsi; String1
0x18008b3c8  call    wcsncmp_0
0x18008b3cd  test    eax, eax
0x18008b3cf  jnz     short loc_18008B3DC
0x18008b3d1  mov     rcx, [rbp+phProvider]; hObject
0x18008b3d5  mov     edx, ebx; int
0x18008b3d7  call    ?DmSetWindowsAIKStorageLocation@@YAJ_KH@Z; DmSetWindowsAIKStorageLocation(unsigned __int64,int)
0x18008b3dc  mov     rdi, [rbp+hObject]
0x18008b3e0  test    rdi, rdi
0x18008b3e3  jz      short loc_18008B406
0x18008b3e5  lea     rcx, [rbp+var_10]; this
0x18008b3e9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18008b3ee  mov     rcx, rdi; hObject
0x18008b3f1  call    cs:__imp_NCryptFreeObject
0x18008b3f8  nop     dword ptr [rax+rax+00h]
0x18008b3fd  lea     rcx, [rbp+var_10]; this
0x18008b401  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18008b406  mov     rcx, [rbp+phProvider]; hProvider
0x18008b40a  lea     r8, pszKeyName; "Windows AIK"
0x18008b411  xor     r9d, r9d; dwLegacyKeySpec
0x18008b414  mov     [rbp+hObject], 0
0x18008b41c  lea     rdx, [rbp+hObject]; phKey
0x18008b420  mov     [rsp+40h+dwFlags], 0; dwFlags
0x18008b428  call    cs:__imp_NCryptOpenKey
0x18008b42f  nop     dword ptr [rax+rax+00h]
0x18008b434  mov     edi, eax
0x18008b436  test    eax, eax
0x18008b438  jns     short loc_18008B450
0x18008b43a  cmp     ebx, 1
0x18008b43d  jnz     short loc_18008B49D
0x18008b43f  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, bl
0x18008b445  jz      short loc_18008B49D
0x18008b447  lea     r8, aDmgetwindowsai_2; "DmGetWindowsAIKKeyFromProviderInternal:"...
0x18008b44e  jmp     short loc_18008B48E
0x18008b450  mov     rax, [rbp+hObject]
0x18008b454  lea     rcx, [rbp+hObject]
0x18008b458  mov     [r14], rax
0x18008b45b  mov     [rbp+hObject], 0
0x18008b463  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008b468  lea     rcx, [rbp+phProvider]
0x18008b46c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008b471  xor     eax, eax
0x18008b473  jmp     short loc_18008B4B1
0x18008b475  mov     edi, 80070057h
0x18008b47a  cmp     ebx, 1
0x18008b47d  jnz     short loc_18008B49D
0x18008b47f  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, bl
0x18008b485  jz      short loc_18008B49D
0x18008b487  lea     r8, aDmgetwindowsai_1; "DmGetWindowsAIKKeyFromProviderInternal:"...
0x18008b48e  mov     r9d, edi
0x18008b491  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x18008b498  call    McTemplateU0zd_EventWriteTransfer
0x18008b49d  lea     rcx, [rbp+hObject]
0x18008b4a1  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008b4a6  lea     rcx, [rbp+phProvider]
0x18008b4aa  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008b4af  mov     eax, edi
0x18008b4b1  mov     rbx, [rsp+40h+arg_8]
0x18008b4b6  mov     rsi, [rsp+40h+arg_10]
0x18008b4bb  add     rsp, 40h
0x18008b4bf  pop     r14
0x18008b4c1  pop     rdi
0x18008b4c2  pop     rbp
0x18008b4c3  retn
```
