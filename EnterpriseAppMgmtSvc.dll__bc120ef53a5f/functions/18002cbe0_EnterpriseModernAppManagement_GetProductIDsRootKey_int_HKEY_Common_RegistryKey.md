# EnterpriseModernAppManagement::GetProductIDsRootKey(int,HKEY__ *,Common::RegistryKey &)

- ea: `0x18002cbe0`
- end: `0x18002ce45`
- name: `?GetProductIDsRootKey@EnterpriseModernAppManagement@@YAJHPEAUHKEY__@@AEAVRegistryKey@Common@@@Z`
- size: `613`
- prototype: `int(EnterpriseModernAppManagement *__hidden this, int, HKEY, struct Common::RegistryKey *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002be98`
- `0x18002c594`

## callees

- `0x18000d3dc`
- `0x18001e358`
- `0x18002c98c`
- `0x18002cbe0`
- `0x18003442c`
- `0x18006b728`
- `0x18006b894`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cd25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cda1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cdf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ce08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cd25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cda1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cdf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ce08`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18002cc44`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18002cc44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cc7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cce4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cdbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ce23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cc7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cce4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cdbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ce23`

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
  unsigned int v8; // ebx
  HKEY v9; // rcx
  bool v10; // cc
  WCHAR *v12; // rbx
  HKEY v13; // rcx
  int HKLMStateSeparationRedirectionPath; // eax
  int v15; // eax
  unsigned int v16; // r9d
  unsigned int v17; // edi
  int v18; // eax
  unsigned int v19; // [rsp+20h] [rbp-20h]
  int v20; // [rsp+20h] [rbp-20h]
  struct _SECURITY_ATTRIBUTES *v21; // [rsp+28h] [rbp-18h]
  unsigned int *v22; // [rsp+30h] [rbp-10h]
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
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  }
  MicrosoftTelemetryAssertTriggeredNoArgs(this);
LABEL_5:
  phkResult = 0;
  hMem = 0;
  if ( a2 == HKEY_CURRENT_USER )
  {
    v7 = RegOpenCurrentUser(0xF003Fu, &phkResult);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4BB,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
        (const char *)(unsigned int)v7,
        v19);
LABEL_8:
      v9 = phkResult;
      v10 = (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_9:
      if ( v10 )
        RegCloseKey(v9);
      return v8;
    }
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &hMem,
      L"Software\\Microsoft\\EnterpriseModernAppManagement\\AppIDs",
      -1);
    v12 = (WCHAR *)hMem;
    if ( !hMem )
    {
      v8 = -2147024882;
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
    v13 = phkResult;
    if ( phkResult != a2 )
    {
      if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(phkResult);
      phkResult = a2;
    }
    HKLMStateSeparationRedirectionPath = EnterpriseModernAppManagement::GetHKLMStateSeparationRedirectionPath(
                                           (__int64)v13,
                                           (__int64)a2,
                                           &hMem);
    v8 = HKLMStateSeparationRedirectionPath;
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
      v9 = phkResult;
      v10 = (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
      goto LABEL_9;
    }
    v12 = (WCHAR *)hMem;
  }
  v15 = Common::RegistryKey::Open(a3, phkResult, v12, 0xF003Fu);
  v17 = v15;
  if ( v15 != -2147024894 )
  {
    if ( v15 >= 0 )
      goto LABEL_35;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D4,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
      (const char *)(unsigned int)v15,
      v19);
    if ( v12 )
      LocalFree(v12);
    goto LABEL_28;
  }
  if ( !v6 )
    goto LABEL_32;
  v18 = Common::RegistryKey::Create(a3, phkResult, v12, v16, v19, v21, v22);
  v17 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D0,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
      (const char *)(unsigned int)v18,
      v20);
    if ( v12 )
      LocalFree(v12);
LABEL_28:
    if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(phkResult);
    return v17;
  }
LABEL_35:
  if ( v12 )
    LocalFree(v12);
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(phkResult);
  return 0;
}

```

## disassembly

```asm
0x18002cbe0  mov     [rsp-18h+arg_0], rbx
0x18002cbe5  mov     [rsp-18h+arg_10], rsi
0x18002cbea  push    rbp
0x18002cbeb  push    rdi
0x18002cbec  push    r14
0x18002cbee  mov     rbp, rsp
0x18002cbf1  sub     rsp, 40h
0x18002cbf5  mov     rsi, r8
0x18002cbf8  mov     rbx, rdx
0x18002cbfb  mov     r14d, ecx
0x18002cbfe  test    rdx, rdx
0x18002cc01  jnz     short loc_18002CC0A
0x18002cc03  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002cc08  jmp     short loc_18002CC17
0x18002cc0a  lea     rax, [rdx+7FFFFFFFh]
0x18002cc11  cmp     rax, 1
0x18002cc15  jbe     short loc_18002CC1C
0x18002cc17  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002cc1c  mov     [rbp+phkResult], 0
0x18002cc24  mov     [rbp+hMem], 0
0x18002cc2c  mov     edi, 0F003Fh
0x18002cc31  cmp     rbx, 0FFFFFFFF80000001h
0x18002cc38  jnz     loc_18002CCD1
0x18002cc3e  lea     rdx, [rbp+phkResult]; phkResult
0x18002cc42  mov     ecx, edi; samDesired
0x18002cc44  call    cs:__imp_RegOpenCurrentUser
0x18002cc4b  nop     dword ptr [rax+rax+00h]
0x18002cc50  mov     ebx, eax
0x18002cc52  test    eax, eax
0x18002cc54  jns     short loc_18002CC90
0x18002cc56  mov     rcx, [rbp+18h]; this
0x18002cc5a  mov     r9d, eax; char *
0x18002cc5d  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002cc64  mov     edx, 4BBh; void *
0x18002cc69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cc6e  nop
0x18002cc6f  mov     rcx, [rbp+phkResult]; hKey
0x18002cc73  lea     rdx, [rcx-1]
0x18002cc77  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002cc7b  ja      short loc_18002CC89
0x18002cc7d  call    cs:__imp_RegCloseKey
0x18002cc84  nop     dword ptr [rax+rax+00h]
0x18002cc89  mov     eax, ebx
0x18002cc8b  jmp     loc_18002CE31
0x18002cc90  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002cc94  lea     rdx, ?c_AppIDsRegistryPath@EnterpriseModernAppManagement@@3QBGB; "Software\\Microsoft\\EnterpriseModernAp"...
0x18002cc9b  lea     rcx, [rbp+hMem]
0x18002cc9f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002cca4  mov     rbx, [rbp+hMem]
0x18002cca8  test    rbx, rbx
0x18002ccab  jnz     loc_18002CD47
0x18002ccb1  mov     rcx, [rbp+18h]; this
0x18002ccb5  mov     ebx, 8007000Eh
0x18002ccba  mov     r9d, ebx; char *
0x18002ccbd  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002ccc4  mov     edx, 4BEh; void *
0x18002ccc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ccce  nop
0x18002cccf  jmp     short loc_18002CC6F
0x18002ccd1  mov     rcx, [rbp+phkResult]; hKey
0x18002ccd5  cmp     rcx, rbx
0x18002ccd8  jz      short loc_18002CCF4
0x18002ccda  lea     rax, [rcx-1]
0x18002ccde  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002cce2  ja      short loc_18002CCF0
0x18002cce4  call    cs:__imp_RegCloseKey
0x18002cceb  nop     dword ptr [rax+rax+00h]
0x18002ccf0  mov     [rbp+phkResult], rbx
0x18002ccf4  lea     r8, [rbp+hMem]
0x18002ccf8  call    ?GetHKLMStateSeparationRedirectionPath@EnterpriseModernAppManagement@@YAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; EnterpriseModernAppManagement::GetHKLMStateSeparationRedirectionPath(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002ccfd  mov     ebx, eax
0x18002ccff  test    eax, eax
0x18002cd01  jns     short loc_18002CD43
0x18002cd03  mov     rcx, [rbp+18h]; this
0x18002cd07  mov     r9d, eax; char *
0x18002cd0a  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002cd11  mov     edx, 4C9h; void *
0x18002cd16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cd1b  nop
0x18002cd1c  mov     rcx, [rbp+hMem]; hMem
0x18002cd20  test    rcx, rcx
0x18002cd23  jz      short loc_18002CD32
0x18002cd25  call    cs:__imp_LocalFree
0x18002cd2c  nop     dword ptr [rax+rax+00h]
0x18002cd31  nop
0x18002cd32  mov     rcx, [rbp+phkResult]
0x18002cd36  lea     rax, [rcx-1]
0x18002cd3a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002cd3e  jmp     loc_18002CC7B
0x18002cd43  mov     rbx, [rbp+hMem]
0x18002cd47  mov     r9d, edi; samDesired
0x18002cd4a  mov     r8, rbx; lpSubKey
0x18002cd4d  mov     rdx, [rbp+phkResult]; hKey
0x18002cd51  mov     rcx, rsi; phkResult
0x18002cd54  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18002cd59  mov     edi, eax
0x18002cd5b  cmp     eax, 80070002h
0x18002cd60  jnz     short loc_18002CDCC
0x18002cd62  test    r14d, r14d
0x18002cd65  jz      short loc_18002CDD0
0x18002cd67  mov     r8, rbx; lpSubKey
0x18002cd6a  mov     rdx, [rbp+phkResult]; hKey
0x18002cd6e  mov     rcx, rsi; phkResult
0x18002cd71  call    ?Create@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGKKQEAU_SECURITY_ATTRIBUTES@@PEAK@Z; Common::RegistryKey::Create(HKEY__ * const,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES * const,ulong *)
0x18002cd76  mov     edi, eax
0x18002cd78  test    eax, eax
0x18002cd7a  jns     loc_18002CE00
0x18002cd80  mov     rcx, [rbp+18h]; this
0x18002cd84  mov     r9d, eax; char *
0x18002cd87  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002cd8e  mov     edx, 4D0h; void *
0x18002cd93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cd98  nop
0x18002cd99  test    rbx, rbx
0x18002cd9c  jz      short loc_18002CDAE
0x18002cd9e  mov     rcx, rbx; hMem
0x18002cda1  call    cs:__imp_LocalFree
0x18002cda8  nop     dword ptr [rax+rax+00h]
0x18002cdad  nop
0x18002cdae  mov     rcx, [rbp+phkResult]; hKey
0x18002cdb2  lea     rax, [rcx-1]
0x18002cdb6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002cdba  ja      short loc_18002CDC8
0x18002cdbc  call    cs:__imp_RegCloseKey
0x18002cdc3  nop     dword ptr [rax+rax+00h]
0x18002cdc8  mov     eax, edi
0x18002cdca  jmp     short loc_18002CE31
0x18002cdcc  test    edi, edi
0x18002cdce  jns     short loc_18002CE00
0x18002cdd0  mov     rcx, [rbp+18h]; this
0x18002cdd4  mov     r9d, edi; char *
0x18002cdd7  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002cdde  mov     edx, 4D4h; void *
0x18002cde3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cde8  nop
0x18002cde9  test    rbx, rbx
0x18002cdec  jz      short loc_18002CDFE
0x18002cdee  mov     rcx, rbx; hMem
0x18002cdf1  call    cs:__imp_LocalFree
0x18002cdf8  nop     dword ptr [rax+rax+00h]
0x18002cdfd  nop
0x18002cdfe  jmp     short loc_18002CDAE
0x18002ce00  test    rbx, rbx
0x18002ce03  jz      short loc_18002CE15
0x18002ce05  mov     rcx, rbx; hMem
0x18002ce08  call    cs:__imp_LocalFree
0x18002ce0f  nop     dword ptr [rax+rax+00h]
0x18002ce14  nop
0x18002ce15  mov     rcx, [rbp+phkResult]; hKey
0x18002ce19  lea     rax, [rcx-1]
0x18002ce1d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ce21  ja      short loc_18002CE2F
0x18002ce23  call    cs:__imp_RegCloseKey
0x18002ce2a  nop     dword ptr [rax+rax+00h]
0x18002ce2f  xor     eax, eax
0x18002ce31  mov     rbx, [rsp+40h+arg_0]
0x18002ce36  mov     rsi, [rsp+40h+arg_10]
0x18002ce3b  add     rsp, 40h
0x18002ce3f  pop     r14
0x18002ce41  pop     rdi
0x18002ce42  pop     rbp
0x18002ce43  retn
```
