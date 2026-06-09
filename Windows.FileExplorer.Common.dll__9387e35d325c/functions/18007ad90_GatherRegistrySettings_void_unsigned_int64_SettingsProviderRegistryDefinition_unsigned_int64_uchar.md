# GatherRegistrySettings(void *,unsigned __int64,SettingsProviderRegistryDefinition *,unsigned __int64 *,uchar * *)

- ea: `0x18007ad90`
- end: `0x18007b056`
- name: `?GatherRegistrySettings@@YAJPEAX_KPEAUSettingsProviderRegistryDefinition@@PEA_KPEAPEAE@Z`
- size: `710`
- prototype: `__int64 __usercall@<rax>(PSID Sid@<rcx>, unsigned __int64@<rdx>, struct SettingsProviderRegistryDefinition *@<r8>, unsigned __int64 *@<r9>, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006dd30`

## callees

- `0x1800077c8`
- `0x180013c5c`
- `0x180029dfc`
- `0x18002f75c`
- `0x18003169c`
- `0x1800361c8`
- `0x180037780`
- `0x1800386f0`
- `0x180044074`
- `0x18007a590`
- `0x18007a814`
- `0x18007ad90`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007af36`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007af36`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007ae42`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007ae42`

## string_xrefs

- `0x18007add5`: `onecore\windows\hvsi\settings\src\registryutils\registryutils.cpp`
- `0x18007ae00`: `onecore\windows\hvsi\settings\src\registryutils\registryutils.cpp`
- `0x18007ae54`: `onecore\windows\hvsi\settings\src\registryutils\registryutils.cpp`
- `0x18007aebd`: `onecore\windows\hvsi\settings\src\registryutils\registryutils.cpp`
- `0x18007af59`: `onecore\windows\hvsi\settings\src\registryutils\registryutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall GatherRegistrySettings(
        PSID Sid,
        __int64 a2,
        struct SettingsProviderRegistryDefinition *a3,
        unsigned __int64 *a4,
        unsigned __int8 **a5)
{
  const unsigned __int16 *v8; // rdx
  const char *v9; // r9
  unsigned int LastError; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  void *v13; // rcx
  SIZE_T v14; // r14
  unsigned __int8 *v15; // rax
  unsigned __int8 *v16; // rbx
  LPWSTR StringSid; // [rsp+20h] [rbp-D8h] BYREF
  void *Src[2]; // [rsp+28h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C0h]
  _QWORD v20[2]; // [rsp+40h] [rbp-B8h] BYREF
  _BYTE v21[128]; // [rsp+50h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registryutils.cpp",
      (const char *)0x80004003LL,
      (int)StringSid);
    return 2147500035LL;
  }
  if ( !a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registryutils.cpp",
      (const char *)0x80004003LL,
      (int)StringSid);
    return 2147500035LL;
  }
  *a4 = 0;
  *a5 = 0;
  v8 = 0;
  StringSid = 0;
  if ( Sid )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0,
      a3);
    if ( !ConvertSidToStringSidW(Sid, &StringSid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2D,
                    (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registryutils.cpp",
                    v9);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      return LastError;
    }
    v8 = StringSid;
  }
  RegistryStore::RegistryStore((RegistryStore *)v21, v8);
  std::vector<_GUID>::vector<_GUID>(Src);
  v11 = RegistryStore::GatherRegistrySettings((RegistryStore *)v21);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registryutils.cpp",
      (const char *)(unsigned int)v11,
      (int)StringSid);
    if ( Src[0] )
    {
      std::_Deallocate<16>(Src[0], v19 - (unsigned __int64)Src[0]);
      *(_OWORD *)Src = 0;
      v19 = 0;
    }
    RegistryStore::~RegistryStore((RegistryStore *)v21);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    return v12;
  }
  v13 = Src[0];
  if ( Src[0] != Src[1] )
  {
    v14 = (char *)Src[1] - (char *)Src[0] + 8;
    v15 = (unsigned __int8 *)LocalAlloc(0x40u, v14);
    v16 = v15;
    v20[0] = v15;
    if ( !v15 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registryutils.cpp",
        (const char *)0x8007000ELL,
        (int)StringSid);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v20);
      if ( Src[0] )
      {
        std::_Deallocate<16>(Src[0], v19 - (unsigned __int64)Src[0]);
        *(_OWORD *)Src = 0;
        v19 = 0;
      }
      RegistryStore::~RegistryStore((RegistryStore *)v21);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      return 2147942414LL;
    }
    *(_QWORD *)v15 = 3;
    memcpy_0(v15 + 8, Src[0], (char *)Src[1] - (char *)Src[0]);
    *a4 = v14;
    v20[0] = 0;
    *a5 = v16;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v20);
    v13 = Src[0];
  }
  if ( v13 )
  {
    std::_Deallocate<16>(v13, v19 - (_QWORD)v13);
    *(_OWORD *)Src = 0;
    v19 = 0;
  }
  RegistryStore::~RegistryStore((RegistryStore *)v21);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  return 0;
}

```

## disassembly

```asm
0x18007ad90  mov     [rsp+arg_8], rbx
0x18007ad95  push    rsi
0x18007ad96  push    rdi
0x18007ad97  push    r14
0x18007ad99  sub     rsp, 0E0h
0x18007ada0  mov     rax, cs:__security_cookie
0x18007ada7  xor     rax, rsp
0x18007adaa  mov     [rsp+0F8h+var_28], rax
0x18007adb2  mov     rdi, r9
0x18007adb5  mov     rbx, rcx
0x18007adb8  mov     rsi, [rsp+0F8h+arg_20]
0x18007adc0  test    r9, r9
0x18007adc3  jnz     short loc_18007ADEB
0x18007adc5  mov     rcx, [rsp+0F8h]; this
0x18007adcd  mov     ebx, 80004003h
0x18007add2  mov     r9d, ebx; char *
0x18007add5  lea     r8, aOnecoreWindows_0; "onecore\\windows\\hvsi\\settings\\src\\"...
0x18007addc  lea     edx, [rdi+22h]; void *
0x18007addf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ade4  mov     eax, ebx
0x18007ade6  jmp     loc_18007B031
0x18007adeb  test    rsi, rsi
0x18007adee  jnz     short loc_18007AE16
0x18007adf0  mov     rcx, [rsp+0F8h]; this
0x18007adf8  mov     ebx, 80004003h
0x18007adfd  mov     r9d, ebx; char *
0x18007ae00  lea     r8, aOnecoreWindows_0; "onecore\\windows\\hvsi\\settings\\src\\"...
0x18007ae07  lea     edx, [rsi+23h]; void *
0x18007ae0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ae0f  mov     eax, ebx
0x18007ae11  jmp     loc_18007B031
0x18007ae16  mov     qword ptr [r9], 0
0x18007ae1d  mov     qword ptr [rsi], 0
0x18007ae24  xor     edx, edx
0x18007ae26  mov     [rsp+0F8h+StringSid], rdx; int
0x18007ae2b  test    rbx, rbx
0x18007ae2e  jz      short loc_18007AE7B
0x18007ae30  lea     rcx, [rsp+0F8h+StringSid]
0x18007ae35  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18007ae3a  lea     rdx, [rsp+0F8h+StringSid]; StringSid
0x18007ae3f  mov     rcx, rbx; Sid
0x18007ae42  call    cs:__imp_ConvertSidToStringSidW
0x18007ae48  test    eax, eax
0x18007ae4a  jnz     short loc_18007AE76
0x18007ae4c  mov     rcx, [rsp+0F8h]; this
0x18007ae54  lea     r8, aOnecoreWindows_0; "onecore\\windows\\hvsi\\settings\\src\\"...
0x18007ae5b  lea     edx, [rax+2Dh]; void *
0x18007ae5e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007ae63  mov     ebx, eax
0x18007ae65  lea     rcx, [rsp+0F8h+StringSid]
0x18007ae6a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007ae6f  mov     eax, ebx
0x18007ae71  jmp     loc_18007B031
0x18007ae76  mov     rdx, [rsp+0F8h+StringSid]; unsigned __int16 *
0x18007ae7b  lea     rcx, [rsp+0F8h+var_A8]; this
0x18007ae80  call    ??0RegistryStore@@QEAA@PEBG@Z; RegistryStore::RegistryStore(ushort const *)
0x18007ae85  nop
0x18007ae86  lea     rcx, [rsp+0F8h+Src]
0x18007ae8b  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18007ae90  nop
0x18007ae91  lea     r9, [rsp+0F8h+Src]
0x18007ae96  lea     r8, ?g_configForHostSyncRootManagerRegistryValue@@3PAUSettingsProviderRegistryDefinition@@A; SettingsProviderRegistryDefinition near * g_configForHostSyncRootManagerRegistryValue
0x18007ae9d  mov     edx, 3
0x18007aea2  lea     rcx, [rsp+0F8h+var_A8]; this
0x18007aea7  call    ?GatherRegistrySettings@RegistryStore@@QEAAJ_KPEAUSettingsProviderRegistryDefinition@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; RegistryStore::GatherRegistrySettings(unsigned __int64,SettingsProviderRegistryDefinition *,std::vector<uchar> &)
0x18007aeac  mov     ebx, eax
0x18007aeae  test    eax, eax
0x18007aeb0  jns     short loc_18007AF14
0x18007aeb2  mov     rcx, [rsp+0F8h]; this
0x18007aeba  mov     r9d, eax; char *
0x18007aebd  lea     r8, aOnecoreWindows_0; "onecore\\windows\\hvsi\\settings\\src\\"...
0x18007aec4  mov     edx, 32h ; '2'; void *
0x18007aec9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007aece  nop
0x18007aecf  mov     rcx, [rsp+0F8h+Src]
0x18007aed4  test    rcx, rcx
0x18007aed7  jz      short loc_18007AEF8
0x18007aed9  mov     rdx, [rsp+0F8h+var_C0]
0x18007aede  sub     rdx, rcx
0x18007aee1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007aee6  xorps   xmm0, xmm0
0x18007aee9  movdqu  xmmword ptr [rsp+0F8h+Src], xmm0
0x18007aeef  mov     [rsp+0F8h+var_C0], 0
0x18007aef8  lea     rcx, [rsp+0F8h+var_A8]; this
0x18007aefd  call    ??1RegistryStore@@QEAA@XZ; RegistryStore::~RegistryStore(void)
0x18007af02  nop
0x18007af03  lea     rcx, [rsp+0F8h+StringSid]
0x18007af08  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007af0d  mov     eax, ebx
0x18007af0f  jmp     loc_18007B031
0x18007af14  mov     rax, [rsp+0F8h+Src+8]
0x18007af19  mov     rcx, [rsp+0F8h+Src]
0x18007af1e  cmp     rcx, rax
0x18007af21  jz      loc_18007AFF0
0x18007af27  sub     rax, rcx
0x18007af2a  lea     r14, [rax+8]
0x18007af2e  mov     rdx, r14; uBytes
0x18007af31  mov     ecx, 40h ; '@'; uFlags
0x18007af36  call    cs:__imp_LocalAlloc
0x18007af3c  mov     rbx, rax
0x18007af3f  mov     [rsp+0F8h+var_B8], rax
0x18007af44  test    rax, rax
0x18007af47  jnz     short loc_18007AFB5
0x18007af49  mov     rcx, [rsp+0F8h]; this
0x18007af51  mov     ebx, 8007000Eh
0x18007af56  mov     r9d, ebx; char *
0x18007af59  lea     r8, aOnecoreWindows_0; "onecore\\windows\\hvsi\\settings\\src\\"...
0x18007af60  lea     edx, [rax+3Ah]; void *
0x18007af63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007af68  lea     rcx, [rsp+0F8h+var_B8]
0x18007af6d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007af72  nop
0x18007af73  mov     rcx, [rsp+0F8h+Src]
0x18007af78  test    rcx, rcx
0x18007af7b  jz      short loc_18007AF9C
0x18007af7d  mov     rdx, [rsp+0F8h+var_C0]
0x18007af82  sub     rdx, rcx
0x18007af85  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007af8a  xorps   xmm0, xmm0
0x18007af8d  movdqu  xmmword ptr [rsp+0F8h+Src], xmm0
0x18007af93  mov     [rsp+0F8h+var_C0], 0
0x18007af9c  lea     rcx, [rsp+0F8h+var_A8]; this
0x18007afa1  call    ??1RegistryStore@@QEAA@XZ; RegistryStore::~RegistryStore(void)
0x18007afa6  nop
0x18007afa7  lea     rcx, [rsp+0F8h+StringSid]
0x18007afac  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007afb1  mov     eax, ebx
0x18007afb3  jmp     short loc_18007B031
0x18007afb5  mov     qword ptr [rax], 3
0x18007afbc  mov     rdx, [rsp+0F8h+Src]; Src
0x18007afc1  mov     r8, [rsp+0F8h+Src+8]
0x18007afc6  sub     r8, rdx; Size
0x18007afc9  lea     rcx, [rax+8]; void *
0x18007afcd  call    memcpy_0
0x18007afd2  mov     [rdi], r14
0x18007afd5  mov     [rsp+0F8h+var_B8], 0
0x18007afde  mov     [rsi], rbx
0x18007afe1  lea     rcx, [rsp+0F8h+var_B8]
0x18007afe6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007afeb  mov     rcx, [rsp+0F8h+Src]
0x18007aff0  test    rcx, rcx
0x18007aff3  jz      short loc_18007B014
0x18007aff5  mov     rdx, [rsp+0F8h+var_C0]
0x18007affa  sub     rdx, rcx
0x18007affd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007b002  xorps   xmm0, xmm0
0x18007b005  movdqu  xmmword ptr [rsp+0F8h+Src], xmm0
0x18007b00b  mov     [rsp+0F8h+var_C0], 0
0x18007b014  lea     rcx, [rsp+0F8h+var_A8]; this
0x18007b019  call    ??1RegistryStore@@QEAA@XZ; RegistryStore::~RegistryStore(void)
0x18007b01e  nop
0x18007b01f  lea     rcx, [rsp+0F8h+StringSid]
0x18007b024  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007b029  xor     eax, eax
0x18007b02b  jmp     short loc_18007B031
0x18007b02d  mov     eax, dword ptr [rsp+0F8h+StringSid]
0x18007b031  mov     rcx, [rsp+0F8h+var_28]
0x18007b039  xor     rcx, rsp; StackCookie
0x18007b03c  call    __security_check_cookie
0x18007b041  mov     rbx, [rsp+0F8h+arg_8]
0x18007b049  add     rsp, 0E0h
0x18007b050  pop     r14
0x18007b052  pop     rdi
0x18007b053  pop     rsi
0x18007b054  retn
```
