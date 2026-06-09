# Container::Manager::Agent::Core::_anonymous_namespace_::StopBootTraceIfNeeded

- ea: `0x18001edfc`
- end: `0x18001f50b`
- name: `Container::Manager::Agent::Core::_anonymous_namespace_::StopBootTraceIfNeeded`
- size: `1807`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001fb70`

## callees

- `0x180002140`
- `0x180002534`
- `0x1800045e4`
- `0x180007b4c`
- `0x1800095f8`
- `0x180009e10`
- `0x18000a070`
- `0x18000a59c`
- `0x18000af30`
- `0x18000b3b0`
- `0x18000b5b0`
- `0x18000b7a0`
- `0x18000bb98`
- `0x18000bc38`
- `0x18000cb58`
- `0x18001edfc`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x18001f038`
- `RPCRT4!UuidFromStringW` at `0x18001f038`
- `ntdll!RtlDoesFileExists_U` at `0x18001ee9f`
- `ntdll!RtlDoesFileExists_U` at `0x18001ee9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ef16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f0bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f3c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f4cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ef16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f0bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f3c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f4cb`

## string_xrefs

- `0x18001efb7`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x18001f06e`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x18001ee64`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001eef8`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001f09f`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001f126`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001f195`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001f21a`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001f28b`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001f353`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001f417`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001f456`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`

## pseudocode

```c
__int64 Container::Manager::Agent::Core::_anonymous_namespace_::StopBootTraceIfNeeded()
{
  WCHAR *v0; // rcx
  __int64 v1; // rcx
  WCHAR *v2; // rcx
  int v3; // eax
  __int64 v4; // rdx
  unsigned int v5; // edi
  WCHAR *v6; // rcx
  int StringValue; // eax
  unsigned int v9; // esi
  unsigned int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  struct Path *v13; // rdx
  int SystemDirectoryPath; // eax
  __int64 v15; // rdx
  int v16; // eax
  unsigned int v17; // [rsp+20h] [rbp-E0h]
  HKEY hKey[2]; // [rsp+30h] [rbp-D0h] BYREF
  PCWSTR FileName[2]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v20[8]; // [rsp+50h] [rbp-B0h] BYREF
  void *v21; // [rsp+60h] [rbp-A0h] BYREF
  char *v22; // [rsp+68h] [rbp-98h]
  _WORD v23[8]; // [rsp+70h] [rbp-90h] BYREF
  void *v24; // [rsp+80h] [rbp-80h] BYREF
  char *v25; // [rsp+88h] [rbp-78h]
  _WORD v26[8]; // [rsp+90h] [rbp-70h] BYREF
  void *v27[2]; // [rsp+A0h] [rbp-60h] BYREF
  _WORD v28[8]; // [rsp+B0h] [rbp-50h] BYREF
  void *v29[2]; // [rsp+C0h] [rbp-40h] BYREF
  _WORD v30[8]; // [rsp+D0h] [rbp-30h] BYREF
  char *v31; // [rsp+E0h] [rbp-20h] BYREF
  RPC_WSTR StringUuid; // [rsp+E8h] [rbp-18h] BYREF
  _WORD *v33; // [rsp+F0h] [rbp-10h]
  _WORD v34[8]; // [rsp+F8h] [rbp-8h] BYREF
  const wchar_t *v35; // [rsp+108h] [rbp+8h]
  __int64 v36; // [rsp+110h] [rbp+10h]
  UUID Uuid; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  hKey[1] = (HKEY)16;
  FileName[0] = v20;
  hKey[0] = (HKEY)L"C:\\ContainerLogs";
  FileName[1] = v20;
  v20[0] = 0;
  if ( !(unsigned __int8)Csl::Path::Assign((Csl::Path *)FileName) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x169,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
      (const char *)0x8007000ELL,
      v17);
    v0 = (WCHAR *)FileName[0];
    if ( FileName[0] == v20 )
      return 2147942414LL;
LABEL_71:
    operator delete(v0, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  if ( RtlDoesFileExists_U(FileName[0]) )
  {
    hKey[0] = 0;
    v3 = Csl::OpenRegistryKey(v1, L"SYSTEM\\CurrentControlSet\\Control", 131097, hKey);
    v5 = v3;
    if ( v3 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x175,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
        (const char *)(unsigned int)v3,
        v17);
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
      v6 = (WCHAR *)FileName[0];
      if ( FileName[0] == v20 )
        return v5;
      goto LABEL_11;
    }
    StringUuid = v34;
    v33 = v34;
    v34[0] = 0;
    Uuid = 0;
    StringValue = Csl::RegistryKey::GetStringValue(hKey, v4, &StringUuid);
    v9 = StringValue;
    if ( StringValue < 0 )
    {
      v5 = -2147024894;
      if ( StringValue != -2147024894 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x46C,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
          (const char *)(unsigned int)StringValue,
          (int)"Failed to get guid value with name '%ws'",
          (const char *)L"ContainerId");
        if ( StringUuid != v34 )
          operator delete(StringUuid, (const struct std::nothrow_t *)&std::nothrow);
        v5 = v9;
        goto LABEL_26;
      }
      if ( StringUuid != v34 )
        goto LABEL_25;
      goto LABEL_26;
    }
    if ( (unsigned __int64)(v33 - StringUuid) < 0x24 )
    {
      v5 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
        (const char *)0x80070057LL,
        v17);
      goto LABEL_24;
    }
    v10 = UuidFromStringW(StringUuid, &Uuid);
    if ( v10 )
    {
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x47,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
             (const char *)v10,
             v17);
      if ( (v5 & 0x80000000) != 0 )
      {
LABEL_24:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x470,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
          (const char *)v5,
          v17);
        if ( StringUuid != v34 )
LABEL_25:
          operator delete(StringUuid, (const struct std::nothrow_t *)&std::nothrow);
LABEL_26:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x178,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
          (const char *)v5,
          v17);
        goto LABEL_27;
      }
    }
    if ( StringUuid != v34 )
      operator delete(StringUuid, (const struct std::nothrow_t *)&std::nothrow);
    v24 = v26;
    v25 = (char *)v26;
    v26[0] = 0;
    v11 = Csl::GuidToString(&Uuid, &v24);
    v5 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17C,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
        (const char *)(unsigned int)v11,
        v17);
LABEL_35:
      if ( v24 != v26 )
        operator delete(v24, (const struct std::nothrow_t *)&std::nothrow);
LABEL_27:
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
      v6 = (WCHAR *)FileName[0];
      if ( FileName[0] == v20 )
        return v5;
LABEL_11:
      operator delete(v6, (const struct std::nothrow_t *)&std::nothrow);
      return v5;
    }
    v21 = v23;
    v22 = (char *)v23;
    v23[0] = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             &v21,
                             L"guest_boot_",
                             11) )
    {
      v12 = 383;
LABEL_39:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
        (const char *)0x8007000ELL,
        v17);
      goto LABEL_64;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v21,
                             v24,
                             (v25 - (_BYTE *)v24) >> 1) )
    {
      v12 = 384;
      goto LABEL_39;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v21,
                             L".etl",
                             4) )
    {
      v12 = 385;
      goto LABEL_39;
    }
    v27[0] = v28;
    v27[1] = v28;
    v28[0] = 0;
    SystemDirectoryPath = Csl::GetSystemDirectoryPath((Csl *)v27, v13);
    v5 = SystemDirectoryPath;
    if ( SystemDirectoryPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x184,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
        (const char *)(unsigned int)SystemDirectoryPath,
        v17);
LABEL_46:
      if ( v27[0] != v28 )
        operator delete(v27[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v21 != v23 )
        operator delete(v21, (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_35;
    }
    v36 = 7;
    v35 = L"wpr.exe";
    if ( (unsigned __int8)Csl::Path::Append((Csl::Path *)v27) )
    {
      v29[0] = v30;
      v29[1] = v30;
      v30[0] = 0;
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
        v29,
        v27);
      if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                              v29,
                              L" -boottrace -stopboot ",
                              22) )
      {
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v29,
                                L"C:\\ContainerLogs",
                                16) )
        {
          if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  v29,
                                  L"\\",
                                  1) )
          {
            if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                    v29,
                                    v21,
                                    (v22 - (_BYTE *)v21) >> 1) )
            {
              LODWORD(v31) = 0;
              v16 = Csl::ExecuteCommandLine((WCHAR **)v29, (DWORD *)&v31, 0, 0xFFFFFFFF);
              v5 = v16;
              if ( v16 >= 0 )
              {
                if ( !(_DWORD)v31 )
                {
                  if ( v29[0] != v30 )
                    operator delete(v29[0], (const struct std::nothrow_t *)&std::nothrow);
                  if ( v27[0] != v28 )
                    operator delete(v27[0], (const struct std::nothrow_t *)&std::nothrow);
                  if ( v21 != v23 )
                    operator delete(v21, (const struct std::nothrow_t *)&std::nothrow);
                  if ( v24 != v26 )
                    operator delete(v24, (const struct std::nothrow_t *)&std::nothrow);
                  if ( hKey[0] )
                    RegCloseKey(hKey[0]);
                  v2 = (WCHAR *)FileName[0];
                  if ( FileName[0] == v20 )
                    return 0;
                  goto LABEL_90;
                }
                v5 = wil::details::in1diag3::Return_Win32(
                       retaddr,
                       (void *)0x191,
                       (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
                       (const char *)(unsigned int)v31,
                       v17);
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x190,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
                  (const char *)(unsigned int)v16,
                  v17);
              }
              if ( v29[0] != v30 )
                operator delete(v29[0], (const struct std::nothrow_t *)&std::nothrow);
              goto LABEL_46;
            }
            v15 = 396;
          }
          else
          {
            v15 = 395;
          }
        }
        else
        {
          v15 = 394;
        }
      }
      else
      {
        v15 = 393;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
        (const char *)0x8007000ELL,
        v17);
      if ( v29[0] != v30 )
        operator delete(v29[0], (const struct std::nothrow_t *)&std::nothrow);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x185,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
        (const char *)0x8007000ELL,
        v17);
    }
    if ( v27[0] != v28 )
      operator delete(v27[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_64:
    if ( v21 != v23 )
      operator delete(v21, (const struct std::nothrow_t *)&std::nothrow);
    if ( v24 != v26 )
      operator delete(v24, (const struct std::nothrow_t *)&std::nothrow);
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    v0 = (WCHAR *)FileName[0];
    if ( FileName[0] == v20 )
      return 2147942414LL;
    goto LABEL_71;
  }
  v2 = (WCHAR *)FileName[0];
  if ( FileName[0] != v20 )
LABEL_90:
    operator delete(v2, (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x18001edfc  push    rbp
0x18001edfe  push    rbx
0x18001edff  push    rsi
0x18001ee00  push    rdi
0x18001ee01  push    r14
0x18001ee03  lea     rbp, [rsp-30h]
0x18001ee08  sub     rsp, 130h
0x18001ee0f  mov     rax, cs:__security_cookie
0x18001ee16  xor     rax, rsp
0x18001ee19  mov     [rbp+50h+var_28], rax
0x18001ee1d  lea     rax, [rsp+150h+var_100]
0x18001ee22  mov     [rsp+150h+var_118], 10h
0x18001ee2b  mov     [rsp+150h+FileName], rax
0x18001ee30  lea     r14, aCContainerlogs; "C:\\ContainerLogs"
0x18001ee37  lea     rax, [rsp+150h+var_100]
0x18001ee3c  mov     [rsp+150h+hKey], r14
0x18001ee41  mov     [rsp+150h+var_108], rax
0x18001ee46  lea     rdx, [rsp+150h+hKey]
0x18001ee4b  xor     eax, eax
0x18001ee4d  lea     rcx, [rsp+150h+FileName]; this
0x18001ee52  mov     [rsp+150h+var_100], ax
0x18001ee57  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18001ee5c  test    al, al
0x18001ee5e  jnz     short loc_18001EE9A
0x18001ee60  mov     rcx, [rbp+58h]; this
0x18001ee64  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18001ee6b  mov     r9d, 8007000Eh; char *
0x18001ee71  mov     edx, 169h; void *
0x18001ee76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ee7b  mov     rcx, [rsp+150h+FileName]
0x18001ee80  lea     rax, [rsp+150h+var_100]
0x18001ee85  cmp     rcx, rax
0x18001ee88  jz      loc_18001F3E8
0x18001ee8e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001ee95  jmp     loc_18001F3E3
0x18001ee9a  mov     rcx, [rsp+150h+FileName]; FileName
0x18001ee9f  call    cs:__imp_RtlDoesFileExists_U
0x18001eea6  nop     dword ptr [rax+rax+00h]
0x18001eeab  test    al, al
0x18001eead  jnz     short loc_18001EECE
0x18001eeaf  mov     rcx, [rsp+150h+FileName]
0x18001eeb4  lea     rax, [rsp+150h+var_100]
0x18001eeb9  cmp     rcx, rax
0x18001eebc  jz      loc_18001F4EE
0x18001eec2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001eec9  jmp     loc_18001F4E9
0x18001eece  lea     r9, [rsp+150h+hKey]
0x18001eed3  mov     [rsp+150h+hKey], 0
0x18001eedc  mov     r8d, 20019h
0x18001eee2  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control"
0x18001eee9  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x18001eeee  mov     edi, eax
0x18001eef0  test    eax, eax
0x18001eef2  jns     short loc_18001EF44
0x18001eef4  mov     rcx, [rbp+58h]; this
0x18001eef8  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18001eeff  mov     r9d, eax; char *
0x18001ef02  mov     edx, 175h; void *
0x18001ef07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ef0c  mov     rcx, [rsp+150h+hKey]; hKey
0x18001ef11  test    rcx, rcx
0x18001ef14  jz      short loc_18001EF22
0x18001ef16  call    cs:__imp_RegCloseKey
0x18001ef1d  nop     dword ptr [rax+rax+00h]
0x18001ef22  mov     rcx, [rsp+150h+FileName]; void *
0x18001ef27  lea     rax, [rsp+150h+var_100]
0x18001ef2c  cmp     rcx, rax
0x18001ef2f  jz      short loc_18001EF3D
0x18001ef31  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ef38  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ef3d  mov     eax, edi
0x18001ef3f  jmp     loc_18001F4F0
0x18001ef44  lea     rax, [rbp+50h+var_58]
0x18001ef48  xorps   xmm0, xmm0
0x18001ef4b  mov     [rbp+50h+StringUuid], rax
0x18001ef4f  lea     r8, [rbp+50h+StringUuid]
0x18001ef53  lea     rax, [rbp+50h+var_58]
0x18001ef57  mov     [rbp+50h+var_60], rax
0x18001ef5b  lea     rcx, [rsp+150h+hKey]
0x18001ef60  xor     eax, eax
0x18001ef62  mov     [rbp+50h+var_58], ax
0x18001ef66  movups  xmmword ptr [rbp+50h+Uuid.Data1], xmm0
0x18001ef6a  call    ?GetStringValue@RegistryKey@Csl@@QEBAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::RegistryKey::GetStringValue(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18001ef6f  mov     esi, eax
0x18001ef71  test    eax, eax
0x18001ef73  jns     loc_18001EFFA
0x18001ef79  mov     edi, 80070002h
0x18001ef7e  cmp     eax, edi
0x18001ef80  jnz     short loc_18001EFA7
0x18001ef82  mov     rcx, [rbp+50h+StringUuid]; void *
0x18001ef86  lea     rax, [rbp+50h+var_58]
0x18001ef8a  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001ef91  cmp     rcx, rax
0x18001ef94  jz      loc_18001F09B
0x18001ef9a  mov     rdx, rbx; struct std::nothrow_t *
0x18001ef9d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001efa2  jmp     loc_18001F09B
0x18001efa7  mov     rcx, [rbp+58h]; this
0x18001efab  lea     rax, Value; "ContainerId"
0x18001efb2  mov     [rsp+150h+var_128], rax; char *
0x18001efb7  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18001efbe  lea     rax, aFailedToGetGui; "Failed to get guid value with name '%ws"...
0x18001efc5  mov     r9d, esi; char *
0x18001efc8  mov     edx, 46Ch; void *
0x18001efcd  mov     qword ptr [rsp+150h+var_130], rax; int
0x18001efd2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001efd7  mov     rcx, [rbp+50h+StringUuid]; void *
0x18001efdb  lea     rax, [rbp+50h+var_58]
0x18001efdf  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001efe6  cmp     rcx, rax
0x18001efe9  jz      short loc_18001EFF3
0x18001efeb  mov     rdx, rbx; struct std::nothrow_t *
0x18001efee  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001eff3  mov     edi, esi
0x18001eff5  jmp     loc_18001F09B
0x18001effa  mov     rcx, [rbp+50h+StringUuid]; StringUuid
0x18001effe  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001f005  mov     rax, [rbp+50h+var_60]
0x18001f009  sub     rax, rcx
0x18001f00c  sar     rax, 1
0x18001f00f  cmp     rax, 24h ; '$'
0x18001f013  jnb     short loc_18001F034
0x18001f015  mov     rcx, [rbp+58h]; this
0x18001f019  lea     r8, aOnecoreBaseGen_14; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18001f020  mov     edi, 80070057h
0x18001f025  mov     edx, 45h ; 'E'; void *
0x18001f02a  mov     r9d, edi; char *
0x18001f02d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f032  jmp     short loc_18001F06A
0x18001f034  lea     rdx, [rbp+50h+Uuid]; Uuid
0x18001f038  call    cs:__imp_UuidFromStringW
0x18001f03f  nop     dword ptr [rax+rax+00h]
0x18001f044  test    eax, eax
0x18001f046  jz      loc_18001F0E4
0x18001f04c  mov     rcx, [rbp+58h]; this
0x18001f050  lea     r8, aOnecoreBaseGen_14; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18001f057  mov     r9d, eax; char *
0x18001f05a  mov     edx, 47h ; 'G'; void *
0x18001f05f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001f064  mov     edi, eax
0x18001f066  test    eax, eax
0x18001f068  jns     short loc_18001F0E4
0x18001f06a  mov     rcx, [rbp+58h]; this
0x18001f06e  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18001f075  mov     r9d, edi; char *
0x18001f078  mov     edx, 470h; void *
0x18001f07d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f082  mov     rcx, [rbp+50h+StringUuid]; void *
0x18001f086  lea     rax, [rbp+50h+var_58]
0x18001f08a  cmp     rcx, rax
0x18001f08d  jz      short loc_18001F097
0x18001f08f  mov     rdx, rbx; struct std::nothrow_t *
0x18001f092  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f097  test    edi, edi
0x18001f099  jns     short loc_18001F0F9
0x18001f09b  mov     rcx, [rbp+58h]; this
0x18001f09f  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18001f0a6  mov     r9d, edi; char *
0x18001f0a9  mov     edx, 178h; void *
0x18001f0ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f0b3  mov     rcx, [rsp+150h+hKey]; hKey
0x18001f0b8  test    rcx, rcx
0x18001f0bb  jz      short loc_18001F0C9
0x18001f0bd  call    cs:__imp_RegCloseKey
0x18001f0c4  nop     dword ptr [rax+rax+00h]
0x18001f0c9  mov     rcx, [rsp+150h+FileName]
0x18001f0ce  lea     rax, [rsp+150h+var_100]
0x18001f0d3  cmp     rcx, rax
0x18001f0d6  jz      loc_18001EF3D
0x18001f0dc  mov     rdx, rbx
0x18001f0df  jmp     loc_18001EF38
0x18001f0e4  mov     rcx, [rbp+50h+StringUuid]; void *
0x18001f0e8  lea     rax, [rbp+50h+var_58]
0x18001f0ec  cmp     rcx, rax
0x18001f0ef  jz      short loc_18001F0F9
0x18001f0f1  mov     rdx, rbx; struct std::nothrow_t *
0x18001f0f4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f0f9  lea     rax, [rbp+50h+var_C0]
0x18001f0fd  mov     [rbp+50h+var_D0], rax
0x18001f101  lea     rdx, [rbp+50h+var_D0]
0x18001f105  lea     rax, [rbp+50h+var_C0]
0x18001f109  mov     [rbp+50h+var_C8], rax
0x18001f10d  lea     rcx, [rbp+50h+Uuid]
0x18001f111  xor     eax, eax
0x18001f113  mov     [rbp+50h+var_C0], ax
0x18001f117  call    ?GuidToString@Csl@@YAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::GuidToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18001f11c  mov     edi, eax
0x18001f11e  test    eax, eax
0x18001f120  jns     short loc_18001F158
0x18001f122  mov     rcx, [rbp+58h]; this
0x18001f126  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18001f12d  mov     r9d, eax; char *
0x18001f130  mov     edx, 17Ch; void *
0x18001f135  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f13a  mov     rcx, [rbp+50h+var_D0]; void *
0x18001f13e  lea     rax, [rbp+50h+var_C0]
0x18001f142  cmp     rcx, rax
0x18001f145  jz      loc_18001F0B3
0x18001f14b  mov     rdx, rbx; struct std::nothrow_t *
0x18001f14e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f153  jmp     loc_18001F0B3
0x18001f158  lea     rax, [rsp+150h+var_E0]
0x18001f15d  mov     [rsp+150h+var_F0], rax
0x18001f162  lea     rdx, aGuestBoot; "guest_boot_"
0x18001f169  lea     rax, [rsp+150h+var_E0]
0x18001f16e  mov     [rsp+150h+var_E8], rax
0x18001f173  lea     rcx, [rsp+150h+var_F0]
0x18001f178  xor     eax, eax
0x18001f17a  mov     [rsp+150h+var_E0], ax
0x18001f17f  lea     r8d, [rax+0Bh]
0x18001f183  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18001f188  test    al, al
0x18001f18a  jnz     short loc_18001F1AC
0x18001f18c  mov     edx, 17Fh; void *
0x18001f191  mov     rcx, [rbp+58h]; this
0x18001f195  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18001f19c  mov     r9d, 8007000Eh; char *
0x18001f1a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f1a7  jmp     loc_18001F38F
0x18001f1ac  mov     r8, [rbp+50h+var_C8]
0x18001f1b0  lea     rcx, [rsp+150h+var_F0]
0x18001f1b5  mov     rdx, [rbp+50h+var_D0]
0x18001f1b9  sub     r8, rdx
0x18001f1bc  sar     r8, 1
0x18001f1bf  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18001f1c4  test    al, al
0x18001f1c6  jnz     short loc_18001F1CF
0x18001f1c8  mov     edx, 180h
0x18001f1cd  jmp     short loc_18001F191
0x18001f1cf  mov     r8d, 4
0x18001f1d5  lea     rdx, aEtl; ".etl"
0x18001f1dc  lea     rcx, [rsp+150h+var_F0]
0x18001f1e1  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18001f1e6  test    al, al
0x18001f1e8  jnz     short loc_18001F1F1
0x18001f1ea  mov     edx, 181h
0x18001f1ef  jmp     short loc_18001F191
0x18001f1f1  lea     rax, [rbp+50h+var_A0]
0x18001f1f5  mov     [rbp+50h+var_B0], rax
0x18001f1f9  lea     rcx, [rbp+50h+var_B0]; this
0x18001f1fd  lea     rax, [rbp+50h+var_A0]
0x18001f201  mov     [rbp+50h+var_A8], rax
0x18001f205  xor     eax, eax
0x18001f207  mov     [rbp+50h+var_A0], ax
0x18001f20b  call    ?GetSystemDirectoryPath@Csl@@YAJAEAVPath@1@@Z; Csl::GetSystemDirectoryPath(Csl::Path &)
0x18001f210  mov     edi, eax
0x18001f212  test    eax, eax
0x18001f214  jns     short loc_18001F263
0x18001f216  mov     rcx, [rbp+58h]; this
0x18001f21a  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18001f221  mov     r9d, eax; char *
0x18001f224  mov     edx, 184h; void *
0x18001f229  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f22e  mov     rcx, [rbp+50h+var_B0]; void *
0x18001f232  lea     rax, [rbp+50h+var_A0]
0x18001f236  cmp     rcx, rax
0x18001f239  jz      short loc_18001F243
0x18001f23b  mov     rdx, rbx; struct std::nothrow_t *
0x18001f23e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f243  mov     rcx, [rsp+150h+var_F0]; void *
0x18001f248  lea     rax, [rsp+150h+var_E0]
0x18001f24d  cmp     rcx, rax
0x18001f250  jz      loc_18001F13A
0x18001f256  mov     rdx, rbx; struct std::nothrow_t *
0x18001f259  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f25e  jmp     loc_18001F13A
0x18001f263  lea     rax, aWprExe; "wpr.exe"
0x18001f26a  mov     [rbp+50h+var_40], 7
0x18001f272  lea     rdx, [rbp+50h+var_48]
0x18001f276  mov     [rbp+50h+var_48], rax
0x18001f27a  lea     rcx, [rbp+50h+var_B0]; this
0x18001f27e  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18001f283  test    al, al
0x18001f285  jnz     short loc_18001F2A7
0x18001f287  mov     rcx, [rbp+58h]; this
0x18001f28b  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18001f292  mov     r9d, 8007000Eh; char *
0x18001f298  mov     edx, 185h; void *
0x18001f29d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f2a2  jmp     loc_18001F37A
0x18001f2a7  lea     rax, [rbp+50h+var_80]
0x18001f2ab  mov     [rbp+50h+var_90], rax
0x18001f2af  lea     rdx, [rbp+50h+var_B0]
0x18001f2b3  lea     rax, [rbp+50h+var_80]
0x18001f2b7  mov     [rbp+50h+var_88], rax
0x18001f2bb  lea     rcx, [rbp+50h+var_90]
0x18001f2bf  xor     eax, eax
0x18001f2c1  mov     [rbp+50h+var_80], ax
0x18001f2c5  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x18001f2ca  mov     r8d, 16h
0x18001f2d0  lea     rdx, aBoottraceStopb; " -boottrace -stopboot "
0x18001f2d7  lea     rcx, [rbp+50h+var_90]
0x18001f2db  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18001f2e0  test    al, al
0x18001f2e2  jnz     short loc_18001F2EB
0x18001f2e4  mov     edx, 189h
0x18001f2e9  jmp     short loc_18001F34F
0x18001f2eb  mov     r8d, 10h
0x18001f2f1  lea     rcx, [rbp+50h+var_90]
0x18001f2f5  mov     rdx, r14
  ... truncated ...
```
