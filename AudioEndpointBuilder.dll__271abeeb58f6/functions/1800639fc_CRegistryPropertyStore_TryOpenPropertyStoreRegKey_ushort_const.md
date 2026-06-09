# CRegistryPropertyStore::TryOpenPropertyStoreRegKey(ushort const *)

- ea: `0x1800639fc`
- end: `0x180063be7`
- name: `?TryOpenPropertyStoreRegKey@CRegistryPropertyStore@@IEAAJPEBG@Z`
- size: `491`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180063bf0`

## callees

- `0x180001140`
- `0x18001b5bc`
- `0x18001deb0`
- `0x180033464`
- `0x1800364d4`
- `0x18003e530`
- `0x18003e920`
- `0x1800632fc`
- `0x180063364`
- `0x1800639fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180063ab2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180063ab2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063ad9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063ad9`

## string_xrefs

- `0x180063b5c`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x180063bac`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x180063b7a`: `Failed to open registry key %ls with access 0x%08x`

## pseudocode

```c
__int64 __fastcall CRegistryPropertyStore::TryOpenPropertyStoreRegKey(HKEY *this, const unsigned __int16 *a2)
{
  const struct _tlgProvider_t *v4; // rax
  int v5; // r9d
  int *v6; // rbx
  int v7; // r8d
  char *v8; // rcx
  unsigned int Key; // eax
  _QWORD *v10; // rdi
  char *v11; // rbx
  __int64 v12; // rax
  unsigned int v13; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-88h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-78h]
  int v17; // [rsp+50h] [rbp-58h] BYREF
  const unsigned __int16 *v18; // [rsp+58h] [rbp-50h] BYREF
  _QWORD v19[2]; // [rsp+60h] [rbp-48h] BYREF
  unsigned __int64 v20; // [rsp+70h] [rbp-38h]
  unsigned __int64 v21; // [rsp+78h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v4 = MMDevApiTelemetryProvider::Provider();
  v6 = (int *)(this + 74);
  v7 = *(_DWORD *)v4;
  if ( *(_DWORD *)v4 > 5u )
  {
    v17 = *v6;
    v18 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)v4,
      (unsigned int)byte_1800786F9,
      v7,
      v5,
      (__int64)&v18,
      (__int64)&v17);
  }
  v8 = (char *)(this + 1);
  if ( (*(_BYTE *)v6 & 2) != 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      v8,
      0);
    Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, *v6 | 0x100, 0, this + 1, 0);
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      v8,
      0);
    Key = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, *v6 | 0x100, this + 1);
  }
  if ( Key == 2 )
    return 0;
  if ( Key != 5 )
  {
    if ( Key )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x13A,
               (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
               (const char *)Key,
               dwOptions);
    return 0;
  }
  std::wstring::wstring(v19, a2);
  v10 = v19;
  if ( v21 > 7 )
    v10 = (_QWORD *)v19[0];
  if ( v20 < 0x16
    || (v11 = (char *)v10 + 2 * v20, v12 = _std_search_2(v10, v11, L"MMDevices\\Audio\\Remote", 22), (char *)v12 == v11)
    || (v12 - (__int64)v10) >> 1 == -1
    || ((_BYTE)this[74] & 2) == 0 )
  {
    LODWORD(lpSecurityAttributes) = *((_DWORD *)this + 148);
    v13 = wil::details::in1diag3::Return_Win32Msg(
            retaddr,
            (void *)0x135,
            (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
            (const char *)5,
            (unsigned int)"Failed to open registry key %ls with access 0x%08x",
            (const char *)a2,
            lpSecurityAttributes);
  }
  else
  {
    v13 = -2147024891;
  }
  std::wstring::_Tidy_deallocate(v19);
  return v13;
}

```

## disassembly

```asm
0x1800639fc  mov     [rsp+arg_10], rbx
0x180063a01  push    rbp
0x180063a02  push    rsi
0x180063a03  push    rdi
0x180063a04  sub     rsp, 90h
0x180063a0b  mov     rax, cs:__security_cookie
0x180063a12  xor     rax, rsp
0x180063a15  mov     [rsp+0A8h+var_28], rax
0x180063a1d  mov     rbp, rdx
0x180063a20  mov     rsi, rcx
0x180063a23  call    ?Provider@MMDevApiTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MMDevApiTelemetryProvider::Provider(void)
0x180063a28  lea     rbx, [rsi+250h]
0x180063a2f  mov     r8d, [rax]
0x180063a32  cmp     r8d, 5
0x180063a36  jbe     short loc_180063A66
0x180063a38  mov     ecx, [rbx]
0x180063a3a  lea     rdx, byte_1800786F9
0x180063a41  mov     [rsp+0A8h+var_58], ecx
0x180063a45  lea     rcx, [rsp+0A8h+var_58]
0x180063a4a  mov     qword ptr [rsp+0A8h+samDesired], rcx
0x180063a4f  lea     rcx, [rsp+0A8h+var_50]
0x180063a54  mov     qword ptr [rsp+0A8h+dwOptions], rcx
0x180063a59  mov     rcx, rax
0x180063a5c  mov     [rsp+0A8h+var_50], rbp
0x180063a61  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180063a66  xor     edx, edx
0x180063a68  lea     rdi, [rsi+8]
0x180063a6c  test    byte ptr [rbx], 2
0x180063a6f  mov     rcx, rdi
0x180063a72  jz      short loc_180063ABA
0x180063a74  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180063a79  mov     eax, [rbx]
0x180063a7b  xor     r9d, r9d; lpClass
0x180063a7e  mov     [rsp+0A8h+lpdwDisposition], 0; lpdwDisposition
0x180063a87  bts     eax, 8
0x180063a8b  mov     [rsp+0A8h+phkResult], rdi; phkResult
0x180063a90  xor     r8d, r8d; Reserved
0x180063a93  mov     [rsp+0A8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180063a9c  mov     rdx, rbp; lpSubKey
0x180063a9f  mov     [rsp+0A8h+samDesired], eax; samDesired
0x180063aa3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180063aaa  mov     [rsp+0A8h+dwOptions], 0; dwOptions
0x180063ab2  call    cs:__imp_RegCreateKeyExW
0x180063ab8  jmp     short loc_180063ADF
0x180063aba  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180063abf  mov     r9d, [rbx]
0x180063ac2  xor     r8d, r8d; ulOptions
0x180063ac5  bts     r9d, 8; samDesired
0x180063aca  mov     qword ptr [rsp+0A8h+dwOptions], rdi; unsigned int
0x180063acf  mov     rdx, rbp; lpSubKey
0x180063ad2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180063ad9  call    cs:__imp_RegOpenKeyExW
0x180063adf  cmp     eax, 2
0x180063ae2  jz      loc_180063BC2
0x180063ae8  cmp     eax, 5
0x180063aeb  jnz     loc_180063BA0
0x180063af1  mov     rdx, rbp
0x180063af4  lea     rcx, [rsp+0A8h+var_48]
0x180063af9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180063afe  cmp     [rsp+0A8h+var_30], 7
0x180063b04  lea     rdi, [rsp+0A8h+var_48]
0x180063b09  mov     rax, [rsp+0A8h+var_38]
0x180063b0e  mov     r9d, 16h
0x180063b14  cmova   rdi, [rsp+0A8h+var_48]
0x180063b1a  cmp     rax, r9
0x180063b1d  jb      short loc_180063B56
0x180063b1f  lea     rbx, [rdi+rax*2]
0x180063b23  mov     rcx, rdi
0x180063b26  mov     rdx, rbx
0x180063b29  lea     r8, aMmdevicesAudio; "MMDevices\\Audio\\Remote"
0x180063b30  call    __std_search_2
0x180063b35  cmp     rax, rbx
0x180063b38  jz      short loc_180063B56
0x180063b3a  sub     rax, rdi
0x180063b3d  sar     rax, 1
0x180063b40  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180063b44  jz      short loc_180063B56
0x180063b46  test    byte ptr [rsi+250h], 2
0x180063b4d  jz      short loc_180063B56
0x180063b4f  mov     ebx, 80070005h
0x180063b54  jmp     short loc_180063B92
0x180063b56  mov     eax, [rsi+250h]
0x180063b5c  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180063b63  mov     rcx, [rsp+0A8h]; this
0x180063b6b  mov     r9d, 5; char *
0x180063b71  mov     dword ptr [rsp+0A8h+lpSecurityAttributes], eax
0x180063b75  mov     edx, 135h; void *
0x180063b7a  lea     rax, aFailedToOpenRe; "Failed to open registry key %ls with ac"...
0x180063b81  mov     qword ptr [rsp+0A8h+samDesired], rbp; char *
0x180063b86  mov     qword ptr [rsp+0A8h+dwOptions], rax; unsigned int
0x180063b8b  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180063b90  mov     ebx, eax
0x180063b92  lea     rcx, [rsp+0A8h+var_48]
0x180063b97  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063b9c  mov     eax, ebx
0x180063b9e  jmp     short loc_180063BC4
0x180063ba0  test    eax, eax
0x180063ba2  jz      short loc_180063BC2
0x180063ba4  mov     rcx, [rsp+0A8h]; this
0x180063bac  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180063bb3  mov     r9d, eax; char *
0x180063bb6  mov     edx, 13Ah; void *
0x180063bbb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180063bc0  jmp     short loc_180063BC4
0x180063bc2  xor     eax, eax
0x180063bc4  mov     rcx, [rsp+0A8h+var_28]
0x180063bcc  xor     rcx, rsp; StackCookie
0x180063bcf  call    __security_check_cookie
0x180063bd4  mov     rbx, [rsp+0A8h+arg_10]
0x180063bdc  add     rsp, 90h
0x180063be3  pop     rdi
0x180063be4  pop     rsi
0x180063be5  pop     rbp
0x180063be6  retn
```
