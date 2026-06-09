# EnterpriseModernAppManagement::GetProductIDsRootKey(int,HKEY__ *,Common::RegistryKey &)

- ea: `0x18002a908`
- end: `0x18002ab32`
- name: `?GetProductIDsRootKey@EnterpriseModernAppManagement@@YAJHPEAUHKEY__@@AEAVRegistryKey@Common@@@Z`
- size: `554`
- prototype: `int(EnterpriseModernAppManagement *__hidden this, int, HKEY, struct Common::RegistryKey *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029ca0`
- `0x18002a32c`

## callees

- `0x18000cfe8`
- `0x18001d1fc`
- `0x18002a6ec`
- `0x18002a908`
- `0x1800315d4`
- `0x180065d48`
- `0x180065ea8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aaad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aaf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ab02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aaad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aaf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ab02`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18002a96c`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18002a96c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a99f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002aa00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002aac2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ab17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a99f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002aa00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002aac2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ab17`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EnterpriseModernAppManagement::GetProductIDsRootKey(
        EnterpriseModernAppManagement *this,
        HKEY a2,
        HKEY *a3,
        struct Common::RegistryKey *a4)
{
  int v6; // r14d
  LSTATUS v7; // eax
  const char *v8; // r9
  unsigned int v9; // ebx
  HKEY v10; // rcx
  bool v11; // cc
  WCHAR *v13; // rbx
  HKEY v14; // rcx
  int HKLMStateSeparationRedirectionPath; // eax
  int v16; // eax
  unsigned int v17; // edi
  LSTATUS v18; // eax
  int v19; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HKEY phkResult; // [rsp+68h] [rbp+28h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+38h] BYREF

  v6 = (int)this;
  if ( a2 )
  {
    if ( (unsigned __int64)a2 + 0x7FFFFFFF <= 1 )
      goto LABEL_5;
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(this, 0);
  }
  MicrosoftTelemetryAssertTriggeredNoArgs(this, a2);
LABEL_5:
  phkResult = 0;
  hMem = 0;
  if ( a2 == HKEY_CURRENT_USER )
  {
    v7 = RegOpenCurrentUser(0xF003Fu, &phkResult);
    v9 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4BB,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
        (const char *)(unsigned int)v7,
        v19);
LABEL_8:
      v10 = phkResult;
      v11 = (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_9:
      if ( v11 )
        RegCloseKey(v10);
      return v9;
    }
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &hMem,
      (char *)L"Software\\Microsoft\\EnterpriseModernAppManagement\\AppIDs",
      0xFFFFFFFFFFFFFFFFuLL,
      v8);
    v13 = (WCHAR *)hMem;
    if ( !hMem )
    {
      v9 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4BE,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
        (const char *)0x8007000ELL,
        v19);
      goto LABEL_8;
    }
  }
  else
  {
    v14 = phkResult;
    if ( phkResult != a2 )
    {
      if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(phkResult);
      phkResult = a2;
    }
    HKLMStateSeparationRedirectionPath = EnterpriseModernAppManagement::GetHKLMStateSeparationRedirectionPath(
                                           (__int64)v14,
                                           (__int64)a2,
                                           &hMem);
    v9 = HKLMStateSeparationRedirectionPath;
    if ( HKLMStateSeparationRedirectionPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C9,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
        (const char *)(unsigned int)HKLMStateSeparationRedirectionPath,
        v19);
      if ( hMem )
        LocalFree(hMem);
      v10 = phkResult;
      v11 = (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
      goto LABEL_9;
    }
    v13 = (WCHAR *)hMem;
  }
  v16 = Common::RegistryKey::Open(a3, phkResult, v13, 0xF003Fu);
  v17 = v16;
  if ( v16 != -2147024894 )
  {
    if ( v16 >= 0 )
      goto LABEL_35;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D4,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
      (const char *)(unsigned int)v16,
      v19);
    if ( v13 )
      LocalFree(v13);
    goto LABEL_28;
  }
  if ( !v6 )
    goto LABEL_32;
  v18 = Common::RegistryKey::Create(a3, phkResult, v13);
  v17 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D0,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
      (const char *)(unsigned int)v18,
      v19);
    if ( v13 )
      LocalFree(v13);
LABEL_28:
    if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(phkResult);
    return v17;
  }
LABEL_35:
  if ( v13 )
    LocalFree(v13);
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(phkResult);
  return 0;
}

```

## disassembly

```asm
0x18002a908  mov     [rsp-18h+arg_0], rbx
0x18002a90d  mov     [rsp-18h+arg_10], rsi
0x18002a912  push    rbp
0x18002a913  push    rdi
0x18002a914  push    r14
0x18002a916  mov     rbp, rsp
0x18002a919  sub     rsp, 40h
0x18002a91d  mov     rsi, r8
0x18002a920  mov     rbx, rdx
0x18002a923  mov     r14d, ecx
0x18002a926  test    rdx, rdx
0x18002a929  jnz     short loc_18002A932
0x18002a92b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002a930  jmp     short loc_18002A93F
0x18002a932  lea     rax, [rdx+7FFFFFFFh]
0x18002a939  cmp     rax, 1
0x18002a93d  jbe     short loc_18002A944
0x18002a93f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002a944  mov     [rbp+phkResult], 0
0x18002a94c  mov     [rbp+hMem], 0
0x18002a954  mov     edi, 0F003Fh
0x18002a959  cmp     rbx, 0FFFFFFFF80000001h
0x18002a960  jnz     loc_18002A9ED
0x18002a966  lea     rdx, [rbp+phkResult]; phkResult
0x18002a96a  mov     ecx, edi; samDesired
0x18002a96c  call    cs:__imp_RegOpenCurrentUser
0x18002a972  mov     ebx, eax
0x18002a974  test    eax, eax
0x18002a976  jns     short loc_18002A9AC
0x18002a978  mov     rcx, [rbp+18h]; this
0x18002a97c  mov     r9d, eax; char *
0x18002a97f  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002a986  mov     edx, 4BBh; void *
0x18002a98b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a990  nop
0x18002a991  mov     rcx, [rbp+phkResult]; hKey
0x18002a995  lea     rdx, [rcx-1]
0x18002a999  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002a99d  ja      short loc_18002A9A5
0x18002a99f  call    cs:__imp_RegCloseKey
0x18002a9a5  mov     eax, ebx
0x18002a9a7  jmp     loc_18002AB1F
0x18002a9ac  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002a9b0  lea     rdx, ?c_AppIDsRegistryPath@EnterpriseModernAppManagement@@3QBGB; "Software\\Microsoft\\EnterpriseModernAp"...
0x18002a9b7  lea     rcx, [rbp+hMem]
0x18002a9bb  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002a9c0  mov     rbx, [rbp+hMem]
0x18002a9c4  test    rbx, rbx
0x18002a9c7  jnz     loc_18002AA57
0x18002a9cd  mov     rcx, [rbp+18h]; this
0x18002a9d1  mov     ebx, 8007000Eh
0x18002a9d6  mov     r9d, ebx; char *
0x18002a9d9  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002a9e0  mov     edx, 4BEh; void *
0x18002a9e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a9ea  nop
0x18002a9eb  jmp     short loc_18002A991
0x18002a9ed  mov     rcx, [rbp+phkResult]; hKey
0x18002a9f1  cmp     rcx, rbx
0x18002a9f4  jz      short loc_18002AA0A
0x18002a9f6  lea     rax, [rcx-1]
0x18002a9fa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002a9fe  ja      short loc_18002AA06
0x18002aa00  call    cs:__imp_RegCloseKey
0x18002aa06  mov     [rbp+phkResult], rbx
0x18002aa0a  lea     r8, [rbp+hMem]
0x18002aa0e  call    ?GetHKLMStateSeparationRedirectionPath@EnterpriseModernAppManagement@@YAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; EnterpriseModernAppManagement::GetHKLMStateSeparationRedirectionPath(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002aa13  mov     ebx, eax
0x18002aa15  test    eax, eax
0x18002aa17  jns     short loc_18002AA53
0x18002aa19  mov     rcx, [rbp+18h]; this
0x18002aa1d  mov     r9d, eax; char *
0x18002aa20  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002aa27  mov     edx, 4C9h; void *
0x18002aa2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002aa31  nop
0x18002aa32  mov     rcx, [rbp+hMem]; hMem
0x18002aa36  test    rcx, rcx
0x18002aa39  jz      short loc_18002AA42
0x18002aa3b  call    cs:__imp_LocalFree
0x18002aa41  nop
0x18002aa42  mov     rcx, [rbp+phkResult]
0x18002aa46  lea     rax, [rcx-1]
0x18002aa4a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002aa4e  jmp     loc_18002A99D
0x18002aa53  mov     rbx, [rbp+hMem]
0x18002aa57  mov     r9d, edi; samDesired
0x18002aa5a  mov     r8, rbx; lpSubKey
0x18002aa5d  mov     rdx, [rbp+phkResult]; hKey
0x18002aa61  mov     rcx, rsi; phkResult
0x18002aa64  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18002aa69  mov     edi, eax
0x18002aa6b  cmp     eax, 80070002h
0x18002aa70  jnz     short loc_18002AACC
0x18002aa72  test    r14d, r14d
0x18002aa75  jz      short loc_18002AAD0
0x18002aa77  mov     r8, rbx; lpSubKey
0x18002aa7a  mov     rdx, [rbp+phkResult]; hKey
0x18002aa7e  mov     rcx, rsi; phkResult
0x18002aa81  call    ?Create@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGKKQEAU_SECURITY_ATTRIBUTES@@PEAK@Z; Common::RegistryKey::Create(HKEY__ * const,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES * const,ulong *)
0x18002aa86  mov     edi, eax
0x18002aa88  test    eax, eax
0x18002aa8a  jns     short loc_18002AAFA
0x18002aa8c  mov     rcx, [rbp+18h]; this
0x18002aa90  mov     r9d, eax; char *
0x18002aa93  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002aa9a  mov     edx, 4D0h; void *
0x18002aa9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002aaa4  nop
0x18002aaa5  test    rbx, rbx
0x18002aaa8  jz      short loc_18002AAB4
0x18002aaaa  mov     rcx, rbx; hMem
0x18002aaad  call    cs:__imp_LocalFree
0x18002aab3  nop
0x18002aab4  mov     rcx, [rbp+phkResult]; hKey
0x18002aab8  lea     rax, [rcx-1]
0x18002aabc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002aac0  ja      short loc_18002AAC8
0x18002aac2  call    cs:__imp_RegCloseKey
0x18002aac8  mov     eax, edi
0x18002aaca  jmp     short loc_18002AB1F
0x18002aacc  test    edi, edi
0x18002aace  jns     short loc_18002AAFA
0x18002aad0  mov     rcx, [rbp+18h]; this
0x18002aad4  mov     r9d, edi; char *
0x18002aad7  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002aade  mov     edx, 4D4h; void *
0x18002aae3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002aae8  nop
0x18002aae9  test    rbx, rbx
0x18002aaec  jz      short loc_18002AAF8
0x18002aaee  mov     rcx, rbx; hMem
0x18002aaf1  call    cs:__imp_LocalFree
0x18002aaf7  nop
0x18002aaf8  jmp     short loc_18002AAB4
0x18002aafa  test    rbx, rbx
0x18002aafd  jz      short loc_18002AB09
0x18002aaff  mov     rcx, rbx; hMem
0x18002ab02  call    cs:__imp_LocalFree
0x18002ab08  nop
0x18002ab09  mov     rcx, [rbp+phkResult]; hKey
0x18002ab0d  lea     rax, [rcx-1]
0x18002ab11  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ab15  ja      short loc_18002AB1D
0x18002ab17  call    cs:__imp_RegCloseKey
0x18002ab1d  xor     eax, eax
0x18002ab1f  mov     rbx, [rsp+40h+arg_0]
0x18002ab24  mov     rsi, [rsp+40h+arg_10]
0x18002ab29  add     rsp, 40h
0x18002ab2d  pop     r14
0x18002ab2f  pop     rdi
0x18002ab30  pop     rbp
0x18002ab31  retn
```
