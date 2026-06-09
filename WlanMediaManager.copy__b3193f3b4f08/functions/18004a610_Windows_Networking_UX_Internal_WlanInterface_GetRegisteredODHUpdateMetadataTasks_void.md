# Windows::Networking::UX::Internal::WlanInterface::_GetRegisteredODHUpdateMetadataTasks(void)

- ea: `0x18004a610`
- end: `0x18004a9a1`
- name: `?_GetRegisteredODHUpdateMetadataTasks@WlanInterface@Internal@UX@Networking@Windows@@IEAA?AV?$vector@USebTask@Internal@UX@Networking@Windows@@V?$allocator@USebTask@Internal@UX@Networking@Windows@@@std@@@std@@XZ`
- size: `913`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004c5dc`

## callees

- `0x180003ed0`
- `0x180004a70`
- `0x180007a2c`
- `0x180007d10`
- `0x18000b86c`
- `0x18000de4c`
- `0x18000de74`
- `0x18001b230`
- `0x180029d00`
- `0x180037628`
- `0x180037930`
- `0x18003a04c`
- `0x18003a1c8`
- `0x18003a1e4`
- `0x18004a610`
- `0x18004ca20`
- `0x180051ca0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a71e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a71e`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18004a6a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18004a6a9`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004a92a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004a92a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a6e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a6e6`
- `SystemEventsBrokerClient!SebQueryEventPackage` at `0x18004a80c`
- `SystemEventsBrokerClient!SebQueryEventPackage` at `0x18004a80c`

## string_xrefs

- `0x18004a712`: `Software\Microsoft\WcmSvc\Tethering\Tasks\UpdateMetadata`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
HKEY __fastcall Windows::Networking::UX::Internal::WlanInterface::_GetRegisteredODHUpdateMetadataTasks(
        __int64 a1,
        HKEY a2)
{
  unsigned int v3; // eax
  unsigned int v4; // eax
  DWORD v5; // esi
  DWORD i; // edx
  int v7; // eax
  char v8; // di
  int v9; // edx
  int v10; // r8d
  PVOID v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // eax
  unsigned int v15; // [rsp+20h] [rbp-E0h]
  unsigned int v16; // [rsp+20h] [rbp-E0h]
  unsigned int v17; // [rsp+20h] [rbp-E0h]
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchValueName; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  int v22; // [rsp+58h] [rbp-A8h]
  HKEY phkResult[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v24; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[16]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v26; // [rsp+90h] [rbp-70h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  phkResult[1] = a2;
  v22 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 275, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  std::vector<Windows::Networking::UX::Internal::Profile *>::vector<Windows::Networking::UX::Internal::Profile *>(a2);
  v22 = 1;
  hKey = 0;
  phkResult[0] = 0;
  v3 = RegOpenCurrentUser(0xF003Fu, phkResult);
  if ( v3 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xE2A,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
      (const char *)v3,
      v15);
  hKey = 0;
  v4 = RegOpenKeyExW(phkResult[0], L"Software\\Microsoft\\WcmSvc\\Tethering\\Tasks\\UpdateMetadata", 0, 0x20019u, &hKey);
  if ( v4 != 2 )
  {
    if ( v4 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xE33,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
        (const char *)v4,
        v16);
    v5 = 0;
    memset_0(ValueName, 0, 0x208u);
    for ( i = 0; ; i = v5 )
    {
      cchValueName = 260;
      *(_OWORD *)Data = 0;
      cbData = 16;
      v13 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, 0, Data, &cbData);
      if ( v13 == 259 )
        break;
      if ( v13 )
      {
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0xE43,
          (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
          (const char *)v13,
          v17);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            276,
            &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
            ValueName);
      }
      else
      {
        v18 = 0;
        v26 = (unsigned __int64)&v18;
        LOBYTE(v27) = 1;
        v24 = *(_OWORD *)Data;
        v7 = SebQueryEventPackage(&v24, (char *)&v26 + 8);
        if ( v7 >= 0 )
        {
          v8 = 0;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xE4A,
            (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
            (const char *)(unsigned int)v7,
            v17);
          v8 = 1;
        }
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v26);
        if ( !v8 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_SS_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, (unsigned int)ValueName, v18, (__int64)Data);
          v26 = *(_OWORD *)Data;
          v27 = v18;
          v18 = 0;
          v12 = *((_QWORD *)a2 + 1);
          if ( v12 == *((_QWORD *)a2 + 2) )
          {
            std::vector<Windows::Networking::UX::Internal::SebTask>::_Emplace_reallocate<Windows::Networking::UX::Internal::SebTask>(
              a2,
              v12,
              &v26);
          }
          else
          {
            std::_Default_allocator_traits<std::allocator<Windows::Networking::UX::Internal::SebTask>>::construct<Windows::Networking::UX::Internal::SebTask,Windows::Networking::UX::Internal::SebTask>(
              v11,
              v12,
              &v26);
            *((_QWORD *)a2 + 1) += 24LL;
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v18);
      }
      ++v5;
      memset_0(ValueName, 0, 0x208u);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 278, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
  return a2;
}

```

## disassembly

```asm
0x18004a610  mov     [rsp-8+arg_0], rbx
0x18004a615  mov     [rsp-8+arg_10], rsi
0x18004a61a  push    rbp
0x18004a61b  push    rdi
0x18004a61c  push    r15
0x18004a61e  lea     rbp, [rsp-1D0h]
0x18004a626  sub     rsp, 2D0h
0x18004a62d  mov     rax, cs:__security_cookie
0x18004a634  xor     rax, rsp
0x18004a637  mov     [rbp+1E0h+var_20], rax
0x18004a63e  mov     rbx, rdx
0x18004a641  mov     [rsp+2E0h+var_278], rdx
0x18004a646  mov     [rsp+2E0h+var_288], 1
0x18004a64e  lea     r15, WPP_GLOBAL_Control
0x18004a655  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a65c  cmp     rcx, r15
0x18004a65f  jz      short loc_18004A67C
0x18004a661  test    byte ptr [rcx+1Ch], 40h
0x18004a665  jz      short loc_18004A67C
0x18004a667  mov     edx, 113h
0x18004a66c  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18004a673  mov     rcx, [rcx+10h]
0x18004a677  call    WPP_SF_
0x18004a67c  mov     rcx, rbx
0x18004a67f  call    ??0?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::Networking::UX::Internal::Profile *>::vector<Windows::Networking::UX::Internal::Profile *>(void)
0x18004a684  nop
0x18004a685  mov     [rsp+2E0h+var_288], 1
0x18004a68d  mov     [rsp+2E0h+hKey], 0
0x18004a696  mov     [rsp+2E0h+phkResult], 0
0x18004a69f  lea     rdx, [rsp+2E0h+phkResult]; phkResult
0x18004a6a4  mov     ecx, 0F003Fh; samDesired
0x18004a6a9  call    cs:__imp_RegOpenCurrentUser
0x18004a6af  mov     rcx, [rbp+1E8h]; this
0x18004a6b6  test    eax, eax
0x18004a6b8  jz      short loc_18004A6CF
0x18004a6ba  mov     r9d, eax; char *
0x18004a6bd  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18004a6c4  mov     edx, 0E2Ah; void *
0x18004a6c9  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18004a6cf  mov     rdi, [rsp+2E0h+hKey]
0x18004a6d4  test    rdi, rdi
0x18004a6d7  jz      short loc_18004A6F6
0x18004a6d9  lea     rcx, [rsp+2E0h+var_2A0]; this
0x18004a6de  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004a6e3  mov     rcx, rdi; hKey
0x18004a6e6  call    cs:__imp_RegCloseKey
0x18004a6ec  lea     rcx, [rsp+2E0h+var_2A0]; this
0x18004a6f1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004a6f6  mov     [rsp+2E0h+hKey], 0
0x18004a6ff  lea     rax, [rsp+2E0h+hKey]
0x18004a704  mov     [rsp+2E0h+var_2C0], rax; unsigned int
0x18004a709  mov     r9d, 20019h; samDesired
0x18004a70f  xor     r8d, r8d; ulOptions
0x18004a712  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\WcmSvc\\Tethering"...
0x18004a719  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x18004a71e  call    cs:__imp_RegOpenKeyExW
0x18004a724  cmp     eax, 2
0x18004a727  jz      loc_18004A961
0x18004a72d  mov     rcx, [rbp+1E8h]; this
0x18004a734  test    eax, eax
0x18004a736  jz      short loc_18004A74D
0x18004a738  mov     r9d, eax; char *
0x18004a73b  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18004a742  mov     edx, 0E33h; void *
0x18004a747  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18004a74d  xor     esi, esi
0x18004a74f  xor     edx, edx; Val
0x18004a751  mov     r8d, 208h; Size
0x18004a757  lea     rcx, [rbp+1E0h+ValueName]; void *
0x18004a75b  call    memset_0
0x18004a760  lea     rax, [rsp+2E0h+cbData]
0x18004a765  mov     [rsp+2E0h+lpcbData], rax
0x18004a76a  lea     rax, [rbp+1E0h+Data]
0x18004a76e  mov     [rsp+2E0h+lpData], rax
0x18004a773  mov     [rsp+2E0h+lpType], rsi
0x18004a778  mov     [rsp+2E0h+var_2C0], rsi
0x18004a77d  xor     edx, edx
0x18004a77f  jmp     loc_18004A905
0x18004a784  mov     rcx, [rbp+1E8h]; this
0x18004a78b  test    eax, eax
0x18004a78d  jz      short loc_18004A7DB
0x18004a78f  mov     r9d, eax; char *
0x18004a792  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18004a799  mov     edx, 0E43h; void *
0x18004a79e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18004a7a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a7aa  cmp     rcx, r15
0x18004a7ad  jz      loc_18004A8CB
0x18004a7b3  test    byte ptr [rcx+1Ch], 2
0x18004a7b7  jz      loc_18004A8CB
0x18004a7bd  mov     edx, 114h
0x18004a7c2  lea     r9, [rbp+1E0h+ValueName]
0x18004a7c6  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18004a7cd  mov     rcx, [rcx+10h]
0x18004a7d1  call    WPP_SF_S
0x18004a7d6  jmp     loc_18004A8CB
0x18004a7db  mov     [rsp+2E0h+var_2A0], 0
0x18004a7e4  lea     rax, [rsp+2E0h+var_2A0]
0x18004a7e9  mov     qword ptr [rbp+1E0h+var_250], rax
0x18004a7ed  mov     qword ptr [rbp+1E0h+var_250+8], 0
0x18004a7f5  mov     byte ptr [rbp+1E0h+var_240], 1
0x18004a7f9  movaps  xmm0, xmmword ptr [rbp+1E0h+Data]
0x18004a7fd  movdqa  [rsp+2E0h+var_270], xmm0
0x18004a803  lea     rdx, [rbp+1E0h+var_250+8]
0x18004a807  lea     rcx, [rsp+2E0h+var_270]
0x18004a80c  call    cs:__imp_SebQueryEventPackage
0x18004a812  mov     rcx, [rbp+1E8h]; this
0x18004a819  test    eax, eax
0x18004a81b  jns     short loc_18004A836
0x18004a81d  mov     r9d, eax; char *
0x18004a820  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18004a827  mov     edx, 0E4Ah; void *
0x18004a82c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004a831  mov     dil, 1
0x18004a834  jmp     short loc_18004A839
0x18004a836  xor     dil, dil
0x18004a839  lea     rcx, [rbp+1E0h+var_250]
0x18004a83d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18004a842  test    dil, dil
0x18004a845  jnz     short loc_18004A8C1
0x18004a847  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a84e  cmp     rcx, r15
0x18004a851  jz      short loc_18004A879
0x18004a853  test    byte ptr [rcx+1Ch], 8
0x18004a857  jz      short loc_18004A879
0x18004a859  lea     rax, [rbp+1E0h+Data]
0x18004a85d  mov     [rsp+2E0h+lpType], rax
0x18004a862  mov     rax, [rsp+2E0h+var_2A0]
0x18004a867  mov     [rsp+2E0h+var_2C0], rax
0x18004a86c  lea     r9, [rbp+1E0h+ValueName]
0x18004a870  mov     rcx, [rcx+10h]
0x18004a874  call    WPP_SF_SS_guid_
0x18004a879  movaps  xmm0, xmmword ptr [rbp+1E0h+Data]
0x18004a87d  movdqu  [rbp+1E0h+var_250], xmm0
0x18004a882  mov     rax, [rsp+2E0h+var_2A0]
0x18004a887  mov     [rbp+1E0h+var_240], rax
0x18004a88b  mov     [rsp+2E0h+var_2A0], 0
0x18004a894  mov     rdx, [rbx+8]
0x18004a898  lea     r8, [rbp+1E0h+var_250]
0x18004a89c  cmp     rdx, [rbx+10h]
0x18004a8a0  jz      short loc_18004A8AE
0x18004a8a2  call    ??$construct@USebTask@Internal@UX@Networking@Windows@@U12345@@?$_Default_allocator_traits@V?$allocator@USebTask@Internal@UX@Networking@Windows@@@std@@@std@@SAXAEAV?$allocator@USebTask@Internal@UX@Networking@Windows@@@1@QEAUSebTask@Internal@UX@Networking@Windows@@$$QEAU34567@@Z; std::_Default_allocator_traits<std::allocator<Windows::Networking::UX::Internal::SebTask>>::construct<Windows::Networking::UX::Internal::SebTask,Windows::Networking::UX::Internal::SebTask>(std::allocator<Windows::Networking::UX::Internal::SebTask> &,Windows::Networking::UX::Internal::SebTask * const,Windows::Networking::UX::Internal::SebTask &&)
0x18004a8a7  add     qword ptr [rbx+8], 18h
0x18004a8ac  jmp     short loc_18004A8B7
0x18004a8ae  mov     rcx, rbx
0x18004a8b1  call    ??$_Emplace_reallocate@USebTask@Internal@UX@Networking@Windows@@@?$vector@USebTask@Internal@UX@Networking@Windows@@V?$allocator@USebTask@Internal@UX@Networking@Windows@@@std@@@std@@AEAAPEAUSebTask@Internal@UX@Networking@Windows@@QEAU23456@$$QEAU23456@@Z; std::vector<Windows::Networking::UX::Internal::SebTask>::_Emplace_reallocate<Windows::Networking::UX::Internal::SebTask>(Windows::Networking::UX::Internal::SebTask * const,Windows::Networking::UX::Internal::SebTask &&)
0x18004a8b6  nop
0x18004a8b7  lea     rcx, [rbp+1E0h+var_240]
0x18004a8bb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004a8c0  nop
0x18004a8c1  lea     rcx, [rsp+2E0h+var_2A0]
0x18004a8c6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004a8cb  inc     esi
0x18004a8cd  xor     edx, edx; Val
0x18004a8cf  mov     r8d, 208h; Size
0x18004a8d5  lea     rcx, [rbp+1E0h+ValueName]; void *
0x18004a8d9  call    memset_0
0x18004a8de  lea     rax, [rsp+2E0h+cbData]
0x18004a8e3  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18004a8e8  lea     rax, [rbp+1E0h+Data]
0x18004a8ec  mov     [rsp+2E0h+lpData], rax; lpData
0x18004a8f1  mov     [rsp+2E0h+lpType], 0; lpType
0x18004a8fa  mov     [rsp+2E0h+var_2C0], 0; int
0x18004a903  mov     edx, esi; dwIndex
0x18004a905  xorps   xmm0, xmm0
0x18004a908  mov     [rsp+2E0h+cchValueName], 104h
0x18004a910  movups  xmmword ptr [rbp+1E0h+Data], xmm0
0x18004a914  mov     [rsp+2E0h+cbData], 10h
0x18004a91c  lea     r9, [rsp+2E0h+cchValueName]; lpcchValueName
0x18004a921  lea     r8, [rbp+1E0h+ValueName]; lpValueName
0x18004a925  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18004a92a  call    cs:__imp_RegEnumValueW
0x18004a930  cmp     eax, 103h
0x18004a935  jnz     loc_18004A784
0x18004a93b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a942  cmp     rcx, r15
0x18004a945  jz      short loc_18004A961
0x18004a947  test    byte ptr [rcx+1Ch], 40h
0x18004a94b  jz      short loc_18004A961
0x18004a94d  lea     edx, [rax+13h]
0x18004a950  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18004a957  mov     rcx, [rcx+10h]
0x18004a95b  call    WPP_SF_
0x18004a960  nop
0x18004a961  lea     rcx, [rsp+2E0h+hKey]
0x18004a966  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004a96b  nop
0x18004a96c  lea     rcx, [rsp+2E0h+phkResult]
0x18004a971  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004a976  nop
0x18004a977  mov     rax, rbx
0x18004a97a  mov     rcx, [rbp+1E0h+var_20]
0x18004a981  xor     rcx, rsp; StackCookie
0x18004a984  call    __security_check_cookie
0x18004a989  lea     r11, [rsp+2E0h+var_10]
0x18004a991  mov     rbx, [r11+20h]
0x18004a995  mov     rsi, [r11+30h]
0x18004a999  mov     rsp, r11
0x18004a99c  pop     r15
0x18004a99e  pop     rdi
0x18004a99f  pop     rbp
0x18004a9a0  retn
```
