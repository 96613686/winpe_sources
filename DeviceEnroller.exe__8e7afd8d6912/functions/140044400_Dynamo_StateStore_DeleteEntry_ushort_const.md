# Dynamo::StateStore::DeleteEntry(ushort const *)

- ea: `0x140044400`
- end: `0x1400445fe`
- name: `?DeleteEntry@StateStore@Dynamo@@UEAAXPEBG@Z`
- size: `510`
- prototype: `void __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14000a6e4`
- `0x14003cfb8`
- `0x14004053c`
- `0x1400419a4`
- `0x140044400`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400444e5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400444e5`
- `DMCmnUtils!OmaDmRegistryGetAllSubKeys` at `0x140044448`
- `DMCmnUtils!OmaDmRegistryGetAllSubKeys` at `0x140044448`
- `DMCmnUtils!OmDmRegistryAllocAndGetString` at `0x1400444cc`
- `DMCmnUtils!OmDmRegistryAllocAndGetString` at `0x1400444cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044529`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004453c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004453c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400444a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400444a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140044508`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140044534`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004457c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140044508`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140044534`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004457c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x140044551`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x140044551`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400444f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004456c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400444f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004456c`

## string_xrefs

- `0x1400444c1`: `NodeUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall Dynamo::StateStore::DeleteEntry(HKEY *this, const unsigned __int16 *a2)
{
  int AllSubKeys; // eax
  void *v5; // rdx
  unsigned int v6; // r8d
  const char *v7; // r9
  const WCHAR **v8; // rbx
  unsigned __int16 **v9; // rdi
  const WCHAR *v10; // r14
  unsigned int v11; // eax
  int String; // eax
  HKEY v13; // rdi
  DWORD LastError; // ebx
  unsigned int v15; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-30h]
  unsigned int v17; // [rsp+38h] [rbp-18h] BYREF
  char v18; // [rsp+3Ch] [rbp-14h]
  const WCHAR **v19; // [rsp+40h] [rbp-10h] BYREF
  __int64 v20; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp+40h] BYREF

  v19 = 0;
  v20 = 0;
  v17 = 0;
  v18 = 1;
  AllSubKeys = OmaDmRegistryGetAllSubKeys(this[3], &v17, (unsigned __int16 ***)&v19);
  if ( AllSubKeys < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6C,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\statestore.cpp",
      (const char *)(unsigned int)AllSubKeys,
      phkResult);
  if ( v18 )
    v20 = v17;
  v8 = v19;
  v9 = (unsigned __int16 **)&v19[v20];
  while ( 1 )
  {
    if ( v8 == (const WCHAR **)v9 )
      wil::details::in1diag3::Throw_Win32(retaddr, v5, v6, v7, phkResult);
    v10 = *v8;
    hKey = 0;
    v11 = RegOpenKeyExW(this[3], v10, 0, 0x20019u, &hKey);
    if ( v11 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x70,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\statestore.cpp",
        (const char *)v11,
        phkResult);
    hMem = 0;
    String = OmDmRegistryAllocAndGetString(hKey, L"NodeUri", 0, &hMem);
    if ( String < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x73,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\statestore.cpp",
        (const char *)(unsigned int)String,
        phkResult);
    if ( !(unsigned int)_o__wcsicmp(a2, hMem) )
      break;
    if ( hMem )
      LocalFree(hMem);
    if ( hKey )
      RegCloseKey(hKey);
    ++v8;
  }
  v13 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v13);
    SetLastError(LastError);
  }
  hKey = 0;
  v15 = RegDeleteTreeW(this[3], v10);
  if ( v15 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x78,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\statestore.cpp",
      (const char *)v15,
      phkResult);
  if ( hMem )
    LocalFree(hMem);
  if ( hKey )
    RegCloseKey(hKey);
  wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>((__int64)&v19);
}

```

## disassembly

```asm
0x140044400  mov     [rsp-28h+arg_8], rbx
0x140044405  push    rbp
0x140044406  push    rsi
0x140044407  push    rdi
0x140044408  push    r14
0x14004440a  push    r15
0x14004440c  mov     rbp, rsp
0x14004440f  sub     rsp, 50h
0x140044413  mov     r15, rdx
0x140044416  mov     rsi, rcx
0x140044419  mov     [rbp+var_10], 0
0x140044421  mov     [rbp+var_8], 0
0x140044429  lea     rax, [rbp+var_10]
0x14004442d  mov     [rbp+var_20], rax
0x140044431  mov     [rbp+var_18], 0
0x140044438  mov     [rbp+var_14], 1
0x14004443c  lea     r8, [rbp+var_10]
0x140044440  lea     rdx, [rbp+var_18]
0x140044444  mov     rcx, [rcx+18h]
0x140044448  call    cs:__imp_?OmaDmRegistryGetAllSubKeys@@YAJPEAUHKEY__@@PEAKPEAPEAPEAG@Z; OmaDmRegistryGetAllSubKeys(HKEY__ *,ulong *,ushort * * *)
0x14004444e  mov     rcx, [rbp+28h]; this
0x140044452  test    eax, eax
0x140044454  js      loc_1400445D4
0x14004445a  cmp     [rbp+var_14], 0
0x14004445e  jz      short loc_14004446B
0x140044460  mov     ecx, [rbp+var_18]
0x140044463  mov     rax, [rbp+var_20]
0x140044467  mov     [rax+8], rcx
0x14004446b  mov     rbx, [rbp+var_10]
0x14004446f  mov     rax, [rbp+var_8]
0x140044473  lea     rdi, [rbx+rax*8]
0x140044477  jmp     loc_140044512
0x14004447c  mov     r14, [rbx]
0x14004447f  mov     [rbp+hKey], 0
0x140044487  lea     rax, [rbp+hKey]
0x14004448b  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int
0x140044490  mov     r9d, 20019h; samDesired
0x140044496  xor     r8d, r8d; ulOptions
0x140044499  mov     rdx, r14; lpSubKey
0x14004449c  mov     rcx, [rsi+18h]; hKey
0x1400444a0  call    cs:__imp_RegOpenKeyExW
0x1400444a6  mov     rcx, [rbp+28h]; this
0x1400444aa  test    eax, eax
0x1400444ac  jnz     loc_1400445BF
0x1400444b2  mov     [rbp+hMem], 0
0x1400444ba  lea     r9, [rbp+hMem]
0x1400444be  xor     r8d, r8d
0x1400444c1  lea     rdx, aNodeuri; "NodeUri"
0x1400444c8  mov     rcx, [rbp+hKey]
0x1400444cc  call    cs:__imp_?OmDmRegistryAllocAndGetString@@YAJPEAUHKEY__@@PEBGW4AllocFunction@@PEAPEAG@Z; OmDmRegistryAllocAndGetString(HKEY__ *,ushort const *,AllocFunction,ushort * *)
0x1400444d2  mov     rcx, [rbp+28h]; this
0x1400444d6  test    eax, eax
0x1400444d8  js      loc_1400445A0
0x1400444de  mov     rdx, [rbp+hMem]
0x1400444e2  mov     rcx, r15
0x1400444e5  call    cs:__imp__o__wcsicmp
0x1400444eb  test    eax, eax
0x1400444ed  jz      short loc_140044520
0x1400444ef  mov     rcx, [rbp+hMem]; hMem
0x1400444f3  test    rcx, rcx
0x1400444f6  jz      short loc_1400444FF
0x1400444f8  call    cs:__imp_LocalFree
0x1400444fe  nop
0x1400444ff  mov     rcx, [rbp+hKey]; hKey
0x140044503  test    rcx, rcx
0x140044506  jz      short loc_14004450E
0x140044508  call    cs:__imp_RegCloseKey
0x14004450e  add     rbx, 8
0x140044512  cmp     rbx, rdi
0x140044515  jz      loc_1400445B5
0x14004451b  jmp     loc_14004447C
0x140044520  mov     rdi, [rbp+hKey]
0x140044524  test    rdi, rdi
0x140044527  jz      short loc_140044542
0x140044529  call    cs:__imp_GetLastError
0x14004452f  mov     ebx, eax
0x140044531  mov     rcx, rdi; hKey
0x140044534  call    cs:__imp_RegCloseKey
0x14004453a  mov     ecx, ebx; dwErrCode
0x14004453c  call    cs:__imp_SetLastError
0x140044542  mov     [rbp+hKey], 0
0x14004454a  mov     rdx, r14; lpSubKey
0x14004454d  mov     rcx, [rsi+18h]; hKey
0x140044551  call    cs:__imp_RegDeleteTreeW
0x140044557  mov     rcx, [rbp+28h]; this
0x14004455b  test    eax, eax
0x14004455d  jnz     loc_1400445E9
0x140044563  mov     rcx, [rbp+hMem]; hMem
0x140044567  test    rcx, rcx
0x14004456a  jz      short loc_140044573
0x14004456c  call    cs:__imp_LocalFree
0x140044572  nop
0x140044573  mov     rcx, [rbp+hKey]; hKey
0x140044577  test    rcx, rcx
0x14004457a  jz      short loc_140044583
0x14004457c  call    cs:__imp_RegCloseKey
0x140044582  nop
0x140044583  lea     rcx, [rbp+var_10]
0x140044587  call    ??1?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>(void)
0x14004458c  mov     rbx, [rsp+50h+arg_8]
0x140044594  add     rsp, 50h
0x140044598  pop     r15
0x14004459a  pop     r14
0x14004459c  pop     rdi
0x14004459d  pop     rsi
0x14004459e  pop     rbp
0x14004459f  retn
0x1400445a0  mov     r9d, eax; char *
0x1400445a3  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400445aa  mov     edx, 73h ; 's'; void *
0x1400445af  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400445b5  mov     rcx, [rbp+28h]; this
0x1400445b9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400445bf  mov     r9d, eax; char *
0x1400445c2  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400445c9  mov     edx, 70h ; 'p'; void *
0x1400445ce  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1400445d4  mov     r9d, eax; char *
0x1400445d7  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400445de  mov     edx, 6Ch ; 'l'; void *
0x1400445e3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400445e9  mov     r9d, eax; char *
0x1400445ec  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400445f3  mov     edx, 78h ; 'x'; void *
0x1400445f8  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
