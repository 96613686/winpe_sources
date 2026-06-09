# ContainerManager::PrepareAndVerifyRootPath(void)

- ea: `0x18001cac0`
- end: `0x18001cd20`
- name: `?PrepareAndVerifyRootPath@ContainerManager@@AEAAJXZ`
- size: `608`
- prototype: `__int64 __fastcall(ContainerManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c4fc`

## callees

- `0x18000a8e0`
- `0x18000b180`
- `0x18000cab0`
- `0x180018194`
- `0x180019c94`
- `0x18001cac0`
- `0x180020378`
- `0x18002c640`
- `0x18002d518`
- `0x1800592e4`
- `0x1800593dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cb2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cb2b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001cb1b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001cb1b`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18001cbbd`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18001cbbd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ContainerManager::PrepareAndVerifyRootPath(ContainerManager *this)
{
  DWORD LastError; // eax
  signed int v3; // ebx
  int BasicProfileFolderPath; // eax
  const unsigned __int16 *v5; // rdx
  NgcUtils *v6; // rcx
  int DirectoriesInPath; // eax
  const unsigned __int16 *const *v8; // rdx
  struct _SECURITY_ATTRIBUTES *v9; // r9
  const unsigned __int16 *const *v11; // rdx
  struct _SECURITY_ATTRIBUTES *v12; // r9
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  void **v14; // [rsp+38h] [rbp-C8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v16[2]; // [rsp+48h] [rbp-B8h] BYREF
  PSECURITY_DESCRIPTOR v17; // [rsp+50h] [rbp-B0h]
  __int64 v18; // [rsp+58h] [rbp-A8h]
  _QWORD v19[3]; // [rsp+60h] [rbp-A0h] BYREF
  NgcUtils *v20[5]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v21[528]; // [rsp+A0h] [rbp-60h] BYREF

  v14 = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
  SecurityDescriptor = 0;
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v14);
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:PAI(A;OICI;FA;;;SY)(A;OICI;FA;;;S-1-5-80-2381253463-2694003897-3435975801-3559003598-683041300)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    *(_QWORD *)v16 = 24;
    v18 = 0;
    v17 = SecurityDescriptor;
    memset_0(v21, 0, 0x208u);
    BasicProfileFolderPath = GetBasicProfileFolderPath(8, 0, v21, 260);
    v3 = BasicProfileFolderPath;
    if ( BasicProfileFolderPath >= 0 )
    {
      v19[0] = v21;
      v19[1] = L"Microsoft";
      v19[2] = L"Ngc";
      std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v20);
      v3 = NgcUtils::ComposePath(v19, 3, v20);
      if ( v3 >= 0 )
      {
        v6 = (NgcUtils *)v20;
        if ( v20[3] > (NgcUtils *)7 )
          v6 = v20[0];
        DirectoriesInPath = NgcUtils::CheckForDirectory(v6, v5);
        v3 = DirectoriesInPath;
        if ( (unsigned int)(DirectoriesInPath + 2147024894) <= 1 )
        {
          DirectoriesInPath = NgcUtils::CreateDirectoriesInPath((NgcUtils *)v19, v8, (unsigned int)v16, v9);
          v3 = DirectoriesInPath;
          if ( DirectoriesInPath == -2147024891 )
          {
            if ( (unsigned int)dword_1800BE0B8 > 3 )
            {
              v13 = -2147024891;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                (unsigned int)&dword_1800BE0B8,
                (unsigned int)&dword_1800A6EEC,
                0,
                0,
                (__int64)&v13);
            }
            DirectoriesInPath = NgcUtils::CreateDirectoriesInPath((NgcUtils *)v19, v11, 0, v12);
            v3 = DirectoriesInPath;
          }
        }
        if ( DirectoriesInPath >= 0 )
          std::wstring::operator=(this, v20);
      }
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v20);
    }
    else if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v13 = BasicProfileFolderPath;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800BE0B8,
        (unsigned int)byte_1800A6F23,
        0,
        0,
        (__int64)&v13);
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v13 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800BE0B8,
        (unsigned int)&word_1800A6F4E,
        0,
        0,
        (__int64)&v13);
    }
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
  }
  v14 = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v14);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001cac0  push    rbp
0x18001cac2  push    rbx
0x18001cac3  push    rdi
0x18001cac4  push    r14
0x18001cac6  lea     rbp, [rsp-1C8h]
0x18001cace  sub     rsp, 2C8h
0x18001cad5  mov     rax, cs:__security_cookie
0x18001cadc  xor     rax, rsp
0x18001cadf  mov     [rbp+1E0h+var_30], rax
0x18001cae6  mov     rdi, rcx
0x18001cae9  lea     r14, ??_7?$HandleT@USecurityDescriptorTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable'
0x18001caf0  mov     [rsp+2E0h+var_2A8], r14
0x18001caf5  mov     [rsp+2E0h+SecurityDescriptor], 0
0x18001cafe  lea     rcx, [rsp+2E0h+var_2A8]
0x18001cb03  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001cb08  xor     r9d, r9d; SecurityDescriptorSize
0x18001cb0b  lea     r8, [rsp+2E0h+SecurityDescriptor]; SecurityDescriptor
0x18001cb10  lea     edx, [r9+1]; StringSDRevision
0x18001cb14  lea     rcx, StringSecurityDescriptor; "D:PAI(A;OICI;FA;;;SY)(A;OICI;FA;;;S-1-5"...
0x18001cb1b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001cb22  nop     dword ptr [rax+rax+00h]
0x18001cb27  test    eax, eax
0x18001cb29  jnz     short loc_18001CB81
0x18001cb2b  call    cs:__imp_GetLastError
0x18001cb32  nop     dword ptr [rax+rax+00h]
0x18001cb37  mov     ebx, eax
0x18001cb39  mov     ecx, cs:dword_1800BE0B8
0x18001cb3f  cmp     ecx, 2
0x18001cb42  jbe     short loc_18001CB6B
0x18001cb44  mov     [rsp+2E0h+var_2B0], eax
0x18001cb48  lea     rax, [rsp+2E0h+var_2B0]
0x18001cb4d  mov     [rsp+2E0h+var_2C0], rax
0x18001cb52  xor     r9d, r9d
0x18001cb55  xor     r8d, r8d
0x18001cb58  lea     rdx, word_1800A6F4E
0x18001cb5f  lea     rcx, dword_1800BE0B8
0x18001cb66  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001cb6b  test    ebx, ebx
0x18001cb6d  jle     loc_18001CC8F
0x18001cb73  movzx   ebx, bx
0x18001cb76  or      ebx, 80070000h
0x18001cb7c  jmp     loc_18001CC8F
0x18001cb81  mov     qword ptr [rsp+2E0h+var_298], 18h
0x18001cb8a  mov     [rsp+2E0h+var_288], 0
0x18001cb93  mov     rax, [rsp+2E0h+SecurityDescriptor]
0x18001cb98  mov     [rsp+2E0h+var_290], rax
0x18001cb9d  xor     edx, edx; Val
0x18001cb9f  mov     r8d, 208h; Size
0x18001cba5  lea     rcx, [rbp+1E0h+var_240]; void *
0x18001cba9  call    memset_0
0x18001cbae  mov     r9d, 104h
0x18001cbb4  lea     r8, [rbp+1E0h+var_240]
0x18001cbb8  xor     edx, edx
0x18001cbba  lea     ecx, [rdx+8]
0x18001cbbd  call    cs:__imp_GetBasicProfileFolderPath
0x18001cbc4  nop     dword ptr [rax+rax+00h]
0x18001cbc9  mov     ebx, eax
0x18001cbcb  test    eax, eax
0x18001cbcd  jns     short loc_18001CC0A
0x18001cbcf  mov     ecx, cs:dword_1800BE0B8
0x18001cbd5  cmp     ecx, 2
0x18001cbd8  jbe     loc_18001CC8F
0x18001cbde  mov     [rsp+2E0h+var_2B0], eax
0x18001cbe2  lea     rax, [rsp+2E0h+var_2B0]
0x18001cbe7  mov     [rsp+2E0h+var_2C0], rax
0x18001cbec  xor     r9d, r9d
0x18001cbef  xor     r8d, r8d
0x18001cbf2  lea     rdx, byte_1800A6F23
0x18001cbf9  lea     rcx, dword_1800BE0B8
0x18001cc00  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001cc05  jmp     loc_18001CC8F
0x18001cc0a  lea     rax, [rbp+1E0h+var_240]
0x18001cc0e  mov     [rsp+2E0h+var_280], rax
0x18001cc13  mov     rax, cs:off_180082D50; "Microsoft"
0x18001cc1a  mov     [rsp+2E0h+var_278], rax
0x18001cc1f  mov     rax, cs:off_180082D58; "Ngc"
0x18001cc26  mov     [rsp+2E0h+var_270], rax
0x18001cc2b  lea     rcx, [rsp+2E0h+var_268]
0x18001cc30  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18001cc35  nop
0x18001cc36  lea     r8, [rsp+2E0h+var_268]
0x18001cc3b  mov     edx, 3
0x18001cc40  lea     rcx, [rsp+2E0h+var_280]
0x18001cc45  call    ?ComposePath@NgcUtils@@YAJQEBQEBGKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::ComposePath(ushort const * const * const,ulong,std::wstring *)
0x18001cc4a  mov     ebx, eax
0x18001cc4c  test    eax, eax
0x18001cc4e  js      short loc_18001CC84
0x18001cc50  lea     rcx, [rsp+2E0h+var_268]
0x18001cc55  cmp     [rbp+1E0h+var_250], 7
0x18001cc5a  cmova   rcx, [rsp+2E0h+var_268]; this
0x18001cc60  call    ?CheckForDirectory@NgcUtils@@YAJPEBG@Z; NgcUtils::CheckForDirectory(ushort const *)
0x18001cc65  mov     ebx, eax
0x18001cc67  lea     ecx, [rax+7FF8FFFEh]
0x18001cc6d  cmp     ecx, 1
0x18001cc70  jbe     short loc_18001CCBD
0x18001cc72  test    eax, eax
0x18001cc74  js      short loc_18001CC84
0x18001cc76  lea     rdx, [rsp+2E0h+var_268]
0x18001cc7b  mov     rcx, rdi
0x18001cc7e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001cc83  nop
0x18001cc84  lea     rcx, [rsp+2E0h+var_268]
0x18001cc89  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18001cc8e  nop
0x18001cc8f  mov     [rsp+2E0h+var_2A8], r14
0x18001cc94  lea     rcx, [rsp+2E0h+var_2A8]
0x18001cc99  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001cc9e  mov     eax, ebx
0x18001cca0  mov     rcx, [rbp+1E0h+var_30]
0x18001cca7  xor     rcx, rsp; StackCookie
0x18001ccaa  call    __security_check_cookie
0x18001ccaf  add     rsp, 2C8h
0x18001ccb6  pop     r14
0x18001ccb8  pop     rdi
0x18001ccb9  pop     rbx
0x18001ccba  pop     rbp
0x18001ccbb  retn
0x18001ccbd  lea     r8, [rsp+2E0h+var_298]; unsigned int
0x18001ccc2  lea     rcx, [rsp+2E0h+var_280]; this
0x18001ccc7  call    ?CreateDirectoriesInPath@NgcUtils@@YAJQEBQEBGKPEAU_SECURITY_ATTRIBUTES@@@Z; NgcUtils::CreateDirectoriesInPath(ushort const * const * const,ulong,_SECURITY_ATTRIBUTES *)
0x18001cccc  mov     ebx, eax
0x18001ccce  cmp     eax, 80070005h
0x18001ccd3  jnz     short loc_18001CC72
0x18001ccd5  mov     eax, cs:dword_1800BE0B8
0x18001ccdb  cmp     eax, 3
0x18001ccde  jbe     short loc_18001CD0B
0x18001cce0  mov     [rsp+2E0h+var_2B0], 80070005h
0x18001cce8  lea     rax, [rsp+2E0h+var_2B0]
0x18001cced  mov     [rsp+2E0h+var_2C0], rax
0x18001ccf2  xor     r9d, r9d
0x18001ccf5  xor     r8d, r8d
0x18001ccf8  lea     rdx, dword_1800A6EEC
0x18001ccff  lea     rcx, dword_1800BE0B8
0x18001cd06  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001cd0b  xor     r8d, r8d; unsigned int
0x18001cd0e  lea     rcx, [rsp+2E0h+var_280]; this
0x18001cd13  call    ?CreateDirectoriesInPath@NgcUtils@@YAJQEBQEBGKPEAU_SECURITY_ATTRIBUTES@@@Z; NgcUtils::CreateDirectoriesInPath(ushort const * const * const,ulong,_SECURITY_ATTRIBUTES *)
0x18001cd18  mov     ebx, eax
0x18001cd1a  jmp     loc_18001CC72
```
