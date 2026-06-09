# Windows::Internal::WiFiCloudStore::DeleteRetryCountForProfile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_GUID const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)

- ea: `0x180010cb4`
- end: `0x180010d77`
- name: `?DeleteRetryCountForProfile@WiFiCloudStore@Internal@Windows@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@W4ProfileModificationType@123@W4ProfileGeneration@123@PEBG@Z`
- size: `195`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003c170`
- `0x18003cc40`

## callees

- `0x1800079f0`
- `0x180010cb4`
- `0x1800111a8`
- `0x180025308`
- `0x18002a030`
- `0x180031ce4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d5e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180010d01`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180010d01`

## string_xrefs

- `0x180010d15`: `onecore\net\wificloudstore\registry\lib\wificdscommonreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LSTATUS __fastcall Windows::Internal::WiFiCloudStore::DeleteRetryCountForProfile(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  const WCHAR *v6; // rdx
  unsigned int v7; // eax
  LSTATUS result; // eax
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  LPCWSTR lpValueName[2]; // [rsp+38h] [rbp-30h] BYREF
  __m128i si128; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+10h]

  Windows::Internal::WiFiCloudStore::OpenProfileSyncRetryKeyForUser(&hKey);
  Windows::Internal::WiFiCloudStore::ProfileNameToCDSReferenceId(lpValueName, a1);
  v6 = (const WCHAR *)lpValueName;
  if ( si128.m128i_i64[1] > 7uLL )
    v6 = lpValueName[0];
  v7 = RegDeleteValueW(hKey, v6);
  if ( (v7 & 0xFFFFFFFD) != 0 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x14E,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdscommonreg.cpp",
      (const char *)v7,
      a5);
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>((void *)lpValueName[0], 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  result = 0;
  LOWORD(lpValueName[0]) = 0;
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x180010cb4  push    rbp
0x180010cb6  push    rbx
0x180010cb7  mov     rbp, rsp
0x180010cba  sub     rsp, 68h
0x180010cbe  mov     rax, cs:__security_cookie
0x180010cc5  xor     rax, rsp
0x180010cc8  mov     [rbp+var_10], rax
0x180010ccc  mov     rbx, rcx
0x180010ccf  mov     rax, qword ptr [rbp+arg_20]
0x180010cd3  mov     qword ptr [rsp+68h+var_48], rax; unsigned int
0x180010cd8  lea     rcx, [rbp+hKey]
0x180010cdc  call    ?OpenProfileSyncRetryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@W4ProfileModificationType@123@W4ProfileGeneration@123@PEBG@Z; Windows::Internal::WiFiCloudStore::OpenProfileSyncRetryKeyForUser(_GUID const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)
0x180010ce1  nop
0x180010ce2  mov     rdx, rbx
0x180010ce5  lea     rcx, [rbp+lpValueName]
0x180010ce9  call    ?ProfileNameToCDSReferenceId@WiFiCloudStore@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@@Z; Windows::Internal::WiFiCloudStore::ProfileNameToCDSReferenceId(std::wstring const &)
0x180010cee  nop
0x180010cef  lea     rdx, [rbp+lpValueName]
0x180010cf3  cmp     [rbp+var_18], 7
0x180010cf8  cmova   rdx, [rbp+lpValueName]; lpValueName
0x180010cfd  mov     rcx, [rbp+hKey]; hKey
0x180010d01  call    cs:__imp_RegDeleteValueW
0x180010d07  test    eax, 0FFFFFFFDh
0x180010d0c  jz      short loc_180010D27
0x180010d0e  mov     rcx, [rbp+10h]; this
0x180010d12  mov     r9d, eax; char *
0x180010d15  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x180010d1c  mov     edx, 14Eh; void *
0x180010d21  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180010d27  mov     rdx, [rbp+var_18]
0x180010d2b  cmp     rdx, 7
0x180010d2f  jbe     short loc_180010D42
0x180010d31  lea     rdx, ds:2[rdx*2]
0x180010d39  mov     rcx, [rbp+lpValueName]
0x180010d3d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180010d42  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180010d4a  movdqu  xmmword ptr [rbp-20h], xmm0
0x180010d4f  xor     eax, eax
0x180010d51  mov     word ptr [rbp+lpValueName], ax
0x180010d55  mov     rcx, [rbp+hKey]; hKey
0x180010d59  test    rcx, rcx
0x180010d5c  jz      short loc_180010D64
0x180010d5e  call    cs:__imp_RegCloseKey
0x180010d64  mov     rcx, [rbp+var_10]
0x180010d68  xor     rcx, rsp; StackCookie
0x180010d6b  call    __security_check_cookie
0x180010d70  add     rsp, 68h
0x180010d74  pop     rbx
0x180010d75  pop     rbp
0x180010d76  retn
```
