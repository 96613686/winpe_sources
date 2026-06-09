# CloudStoreUtilities::TryOpenPerAccountStorageSubKey(Windows::Internal::Storage::Cloud::Core::PersistenceContext &,Windows::Internal::Storage::Cloud::Core::CloudStoreAccount &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,ushort const *,ulong)

- ea: `0x18003e6dc`
- end: `0x18003e8fe`
- name: `?TryOpenPerAccountStorageSubKey@CloudStoreUtilities@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAVPersistenceContext@Core@Cloud@Storage@Internal@Windows@@AEAVCloudStoreAccount@56789@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBGK@Z`
- size: `546`
- prototype: `__int64 __fastcall(int, int, int, int, int, REGSAM samDesired)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180086bd0`
- `0x180119490`
- `0x1801aefb0`

## callees

- `0x180016cf4`
- `0x1800233f0`
- `0x180023fd4`
- `0x18003e6dc`
- `0x18003e904`
- `0x18003ec80`
- `0x1801201a0`
- `0x1801a6bf8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e898`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e8b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e898`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e8b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e8ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e8c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e8ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e8c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e806`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e806`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e84d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e8a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e8c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e84d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e8a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e8c1`

## string_xrefs

- `0x18003e8d7`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x18003e8ec`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
HKEY __fastcall CloudStoreUtilities::TryOpenPerAccountStorageSubKey(
        HKEY a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        REGSAM samDesired)
{
  HKEY *v8; // r9
  CloudStoreUtilities *v9; // rcx
  int RegistryRootKey; // eax
  HKEY v11; // r14
  HKEY *v12; // rdi
  HKEY v13; // rsi
  const WCHAR *v14; // rdx
  unsigned int v15; // edi
  HKEY v16; // r12
  HKEY *v17; // rsi
  HKEY v18; // r14
  DWORD LastError; // ebx
  DWORD v21; // ebx
  int phkResult; // [rsp+20h] [rbp-59h]
  unsigned int phkResulta; // [rsp+20h] [rbp-59h]
  HKEY hKey[2]; // [rsp+38h] [rbp-41h] BYREF
  HKEY *v25; // [rsp+48h] [rbp-31h] BYREF
  struct _SECURITY_ATTRIBUTES v26; // [rsp+50h] [rbp-29h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+68h] [rbp-11h] BYREF
  unsigned __int64 v28; // [rsp+80h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]

  hKey[1] = a1;
  Utf8StringToWideString(&v25);
  CloudStoreUtilities::GetAccountCommonRegistryRootPath(lpSubKey, a5);
  if ( *(_QWORD *)&v26.bInheritHandle > 7u )
    std::_Deallocate<16>(v25, (const struct std::nothrow_t *)(2LL * *(_QWORD *)&v26.bInheritHandle + 2));
  hKey[0] = 0;
  v25 = hKey;
  *(_QWORD *)&v26.nLength = 0;
  LOBYTE(v26.lpSecurityDescriptor) = 1;
  v9 = (CloudStoreUtilities *)(a2 + 40);
  if ( *(_QWORD *)(a2 + 64) > 7u )
    v9 = *(CloudStoreUtilities **)v9;
  RegistryRootKey = CloudStoreUtilities::GetRegistryRootKey(v9, 0, &v26, v8);
  if ( RegistryRootKey < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x45D,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
      (const char *)(unsigned int)RegistryRootKey,
      phkResult);
  if ( LOBYTE(v26.lpSecurityDescriptor) )
  {
    v11 = *(HKEY *)&v26.nLength;
    v12 = v25;
    v13 = *v25;
    if ( *v25 )
    {
      LastError = GetLastError();
      RegCloseKey(v13);
      SetLastError(LastError);
    }
    *v12 = v11;
  }
  *(_QWORD *)a1 = 0;
  v25 = (HKEY *)a1;
  *(_QWORD *)&v26.nLength = 0;
  LOBYTE(v26.lpSecurityDescriptor) = 1;
  v14 = (const WCHAR *)lpSubKey;
  if ( v28 > 7 )
    v14 = lpSubKey[0];
  v15 = RegOpenKeyExW(hKey[0], v14, 0, samDesired, (PHKEY)&v26);
  if ( LOBYTE(v26.lpSecurityDescriptor) )
  {
    v16 = *(HKEY *)&v26.nLength;
    v17 = v25;
    v18 = *v25;
    if ( *v25 )
    {
      v21 = GetLastError();
      RegCloseKey(v18);
      SetLastError(v21);
    }
    *v17 = v16;
  }
  if ( v15 != 2 && v15 != 1018 && v15 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x463,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
      (const char *)v15,
      phkResulta);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  if ( v28 > 7 )
    std::_Deallocate<16>((void *)lpSubKey[0], (const struct std::nothrow_t *)(2 * v28 + 2));
  return a1;
}

```

## disassembly

```asm
0x18003e6dc  push    rbp
0x18003e6de  push    rbx
0x18003e6df  push    rsi
0x18003e6e0  push    rdi
0x18003e6e1  push    r12
0x18003e6e3  push    r14
0x18003e6e5  push    r15
0x18003e6e7  lea     rbp, [rsp-17h]
0x18003e6ec  sub     rsp, 90h
0x18003e6f3  mov     rax, cs:__security_cookie
0x18003e6fa  xor     rax, rsp
0x18003e6fd  mov     [rbp+47h+var_38], rax
0x18003e701  mov     rdi, r8
0x18003e704  mov     rbx, rdx
0x18003e707  mov     r15, rcx
0x18003e70a  mov     [rbp+47h+var_80], rcx
0x18003e70e  mov     rsi, [rbp+47h+arg_20]
0x18003e712  mov     [rbp+47h+var_90], 0
0x18003e719  mov     rdx, r9
0x18003e71c  lea     rcx, [rbp+47h+var_78]
0x18003e720  call    ?Utf8StringToWideString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; Utf8StringToWideString(std::string const &)
0x18003e725  nop
0x18003e726  cmp     qword ptr [rax+18h], 7
0x18003e72b  jbe     short loc_18003E730
0x18003e72d  mov     rax, [rax]
0x18003e730  mov     qword ptr [rsp+0C0h+phkResult], rsi; int
0x18003e735  lea     r9, aStore_1; "Store"
0x18003e73c  mov     r8, rax
0x18003e73f  mov     rdx, rdi
0x18003e742  lea     rcx, [rbp+47h+lpSubKey]; Src
0x18003e746  call    ?GetAccountCommonRegistryRootPath@CloudStoreUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVCloudStoreAccount@Core@Cloud@Storage@Internal@Windows@@PEBG11@Z; CloudStoreUtilities::GetAccountCommonRegistryRootPath(Windows::Internal::Storage::Cloud::Core::CloudStoreAccount &,ushort const *,ushort const *,ushort const *)
0x18003e74b  nop
0x18003e74c  mov     rdx, [rbp+47h+var_60]
0x18003e750  cmp     rdx, 7
0x18003e754  jbe     short loc_18003E767
0x18003e756  lea     rdx, ds:2[rdx*2]
0x18003e75e  mov     rcx, [rbp+47h+var_78]
0x18003e762  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003e767  mov     [rbp+47h+hKey], 0
0x18003e76f  lea     rax, [rbp+47h+hKey]
0x18003e773  mov     [rbp+47h+var_78], rax
0x18003e777  mov     [rbp+47h+var_70], 0
0x18003e77f  mov     [rbp+47h+var_68], 1
0x18003e783  lea     rcx, [rbx+28h]; this
0x18003e787  cmp     qword ptr [rcx+18h], 7
0x18003e78c  ja      loc_18003E890
0x18003e792  lea     r8, [rbp+47h+var_70]; unsigned __int16 *
0x18003e796  xor     edx, edx; unsigned __int16 *
0x18003e798  call    ?GetRegistryRootKey@CloudStoreUtilities@@YAJPEBG0PEAPEAUHKEY__@@@Z; CloudStoreUtilities::GetRegistryRootKey(ushort const *,ushort const *,HKEY__ * *)
0x18003e79d  mov     rcx, [rbp+4Fh]; this
0x18003e7a1  test    eax, eax
0x18003e7a3  js      loc_18003E8D4
0x18003e7a9  cmp     [rbp+47h+var_68], 0
0x18003e7ad  jz      short loc_18003E7C6
0x18003e7af  mov     r14, [rbp+47h+var_70]
0x18003e7b3  mov     rdi, [rbp+47h+var_78]
0x18003e7b7  mov     rsi, [rdi]
0x18003e7ba  test    rsi, rsi
0x18003e7bd  jnz     loc_18003E898
0x18003e7c3  mov     [rdi], r14
0x18003e7c6  mov     qword ptr [r15], 0
0x18003e7cd  mov     [rbp+47h+var_90], 1
0x18003e7d4  mov     [rbp+47h+var_78], r15
0x18003e7d8  mov     [rbp+47h+var_70], 0
0x18003e7e0  mov     [rbp+47h+var_68], 1
0x18003e7e4  lea     rdx, [rbp+47h+lpSubKey]
0x18003e7e8  cmp     [rbp+47h+var_40], 7
0x18003e7ed  cmova   rdx, [rbp+47h+lpSubKey]; lpSubKey
0x18003e7f2  lea     rax, [rbp+47h+var_70]
0x18003e7f6  mov     qword ptr [rsp+0C0h+phkResult], rax; unsigned int
0x18003e7fb  mov     r9d, [rbp+47h+samDesired]; samDesired
0x18003e7ff  xor     r8d, r8d; ulOptions
0x18003e802  mov     rcx, [rbp+47h+hKey]; hKey
0x18003e806  call    cs:__imp_RegOpenKeyExW
0x18003e80c  mov     edi, eax
0x18003e80e  cmp     [rbp+47h+var_68], 0
0x18003e812  jz      short loc_18003E82B
0x18003e814  mov     r12, [rbp+47h+var_70]
0x18003e818  mov     rsi, [rbp+47h+var_78]
0x18003e81c  mov     r14, [rsi]
0x18003e81f  test    r14, r14
0x18003e822  jnz     loc_18003E8B6
0x18003e828  mov     [rsi], r12
0x18003e82b  cmp     edi, 2
0x18003e82e  jz      short loc_18003E844
0x18003e830  cmp     edi, 3FAh
0x18003e836  jz      short loc_18003E844
0x18003e838  mov     rcx, [rbp+4Fh]; this
0x18003e83c  test    edi, edi
0x18003e83e  jnz     loc_18003E8E9
0x18003e844  mov     rcx, [rbp+47h+hKey]; hKey
0x18003e848  test    rcx, rcx
0x18003e84b  jz      short loc_18003E854
0x18003e84d  call    cs:__imp_RegCloseKey
0x18003e853  nop
0x18003e854  mov     rdx, [rbp+47h+var_40]
0x18003e858  cmp     rdx, 7
0x18003e85c  jbe     short loc_18003E86F
0x18003e85e  lea     rdx, ds:2[rdx*2]
0x18003e866  mov     rcx, [rbp+47h+lpSubKey]
0x18003e86a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003e86f  mov     rax, r15
0x18003e872  mov     rcx, [rbp+47h+var_38]
0x18003e876  xor     rcx, rsp; StackCookie
0x18003e879  call    __security_check_cookie
0x18003e87e  add     rsp, 90h
0x18003e885  pop     r15
0x18003e887  pop     r14
0x18003e889  pop     r12
0x18003e88b  pop     rdi
0x18003e88c  pop     rsi
0x18003e88d  pop     rbx
0x18003e88e  pop     rbp
0x18003e88f  retn
0x18003e890  mov     rcx, [rcx]
0x18003e893  jmp     loc_18003E792
0x18003e898  call    cs:__imp_GetLastError
0x18003e89e  mov     ebx, eax
0x18003e8a0  mov     rcx, rsi; hKey
0x18003e8a3  call    cs:__imp_RegCloseKey
0x18003e8a9  mov     ecx, ebx; dwErrCode
0x18003e8ab  call    cs:__imp_SetLastError
0x18003e8b1  jmp     loc_18003E7C3
0x18003e8b6  call    cs:__imp_GetLastError
0x18003e8bc  mov     ebx, eax
0x18003e8be  mov     rcx, r14; hKey
0x18003e8c1  call    cs:__imp_RegCloseKey
0x18003e8c7  mov     ecx, ebx; dwErrCode
0x18003e8c9  call    cs:__imp_SetLastError
0x18003e8cf  jmp     loc_18003E828
0x18003e8d4  mov     r9d, eax; char *
0x18003e8d7  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18003e8de  mov     edx, 45Dh; void *
0x18003e8e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e8e9  mov     r9d, edi; char *
0x18003e8ec  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18003e8f3  mov     edx, 463h; void *
0x18003e8f8  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
