# Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService(ushort const *,Windows::Networking::UX::MbConnectionProfileType,WWAN_PROFILE &)

- ea: `0x18000867c`
- end: `0x18000886d`
- name: `?_ReadWwanProfileFromService@MBCategory@Internal@UX@Networking@Windows@@AEAAJPEBGW4MbConnectionProfileType@345@AEAUWWAN_PROFILE@@@Z`
- size: `497`
- prototype: `int __high(const unsigned __int16 *, enum Windows::Networking::UX::MbConnectionProfileType, struct WWAN_PROFILE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18003b5f8`
- `0x180041260`

## callees

- `0x18000867c`
- `0x180008c84`
- `0x18002f151`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180008730`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180008774`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180008730`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180008774`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetDMConfigProfile` at `0x1800087ac`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetDMConfigProfile` at `0x1800087ac`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileIstream` at `0x1800086bf`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileIstream` at `0x1800086bf`
- `WwanPrfl!WwanProfileLoadXml` at `0x1800087f4`
- `WwanPrfl!WwanProfileLoadXml` at `0x1800087f4`

## string_xrefs

- `0x1800086eb`: `Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService`
- `0x18000871b`: `Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService`
- `0x18000881f`: `Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService`
- `0x180008853`: `Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService`
- `0x1800087c5`: `Failed to call WwanGetDMConfigProfile. profileName=%ls, HRESULT=0x%x`
- `0x180008814`: `Failed to call WwanProfileLoadXml. profileName=%ls, HRESULT=0x%x, invalidReason=%d`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService(
        __int64 a1,
        const wchar_t *a2,
        int a3,
        _QWORD *a4)
{
  __int64 v6; // rcx
  int ProfileIstream; // eax
  signed int v8; // ebx
  const char *v9; // r8
  unsigned int v10; // edx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int DMConfigProfile; // eax
  int v15; // eax
  __int64 v16; // [rsp+20h] [rbp-28h]
  int v17; // [rsp+30h] [rbp-18h] BYREF
  void *Src[2]; // [rsp+38h] [rbp-10h] BYREF
  unsigned int v19; // [rsp+80h] [rbp+38h] BYREF

  if ( !a3 )
  {
    v6 = *(_QWORD *)(a1 + 304);
    v19 = 0;
    v17 = 0;
    Src[0] = 0;
    ProfileIstream = WwanGetProfileIstream(v6, a2, &v17, &v19, Src);
    v8 = ProfileIstream;
    if ( ProfileIstream > 0 )
      v8 = (unsigned __int16)ProfileIstream | 0x80070000;
    if ( v8 < 0 )
    {
      v9 = "Failed to call WwanGetProfileIstream. profileName=%ls, HRESULT=0x%x";
      v10 = 4547;
LABEL_6:
      LODWORD(v16) = v8;
      MBSettingUXLogging::Error(
        "Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService",
        v10,
        v9,
        a2,
        v16);
LABEL_9:
      WwanFreeMemory(Src[0]);
      return (unsigned int)v8;
    }
    if ( v19 < 0x18D8 )
    {
      MBSettingUXLogging::Error(
        "Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService",
        0x11CEu,
        "WwanGetProfileIstream returned bad size. HRESULT=0x%x, profileName=%ls, dwWwanDataSize=%d",
        v8,
        a2,
        v19);
      v8 = -2147467259;
      goto LABEL_9;
    }
    memcpy_0(a4, Src[0], 0x18B0u);
    a4[557] = 0;
    a4[559] = 0;
    a4[789] = 0;
LABEL_11:
    WwanFreeMemory(Src[0]);
    return 0;
  }
  if ( a3 == 1 )
  {
    v12 = a1 + 24;
    Src[0] = 0;
    v13 = *(_QWORD *)(a1 + 304);
    v19 = 0;
    DMConfigProfile = WwanGetDMConfigProfile(v13, v12, a2, Src);
    v8 = DMConfigProfile;
    if ( DMConfigProfile > 0 )
      v8 = (unsigned __int16)DMConfigProfile | 0x80070000;
    if ( v8 < 0 )
    {
      v9 = "Failed to call WwanGetDMConfigProfile. profileName=%ls, HRESULT=0x%x";
      v10 = 4585;
      goto LABEL_6;
    }
    v15 = WwanProfileLoadXml(a4, Src[0], 0, 0, &v19, 1);
    v8 = v15;
    if ( v15 > 0 )
      v8 = (unsigned __int16)v15 | 0x80070000;
    if ( v8 < 0 )
    {
      MBSettingUXLogging::Error(
        "Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService",
        0x11F5u,
        "Failed to call WwanProfileLoadXml. profileName=%ls, HRESULT=0x%x, invalidReason=%d",
        a2,
        v8,
        v19);
      goto LABEL_9;
    }
    goto LABEL_11;
  }
  MBSettingUXLogging::Error(
    "Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService",
    0x11FBu,
    "Unknown profile type. profileName=%ls, HRESULT=0x%x",
    a2,
    0);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000867c  push    rbp
0x18000867e  push    rbx
0x18000867f  push    rsi
0x180008680  push    rdi
0x180008681  mov     rbp, rsp
0x180008684  sub     rsp, 48h
0x180008688  mov     rsi, r9
0x18000868b  mov     rdi, rdx
0x18000868e  test    r8d, r8d
0x180008691  jnz     loc_180008781
0x180008697  mov     rcx, [rcx+130h]
0x18000869e  lea     rax, [rbp+Src]
0x1800086a2  mov     [rbp+arg_10], r8d
0x1800086a6  lea     r9, [rbp+arg_10]
0x1800086aa  mov     [rbp+var_18], r8d
0x1800086ae  lea     r8, [rbp+var_18]
0x1800086b2  mov     [rsp+48h+var_28], rax
0x1800086b7  mov     [rbp+Src], 0
0x1800086bf  call    cs:__imp_WwanGetProfileIstream
0x1800086c5  mov     ebx, eax
0x1800086c7  test    eax, eax
0x1800086c9  jle     short loc_1800086D4
0x1800086cb  movzx   ebx, ax
0x1800086ce  or      ebx, 80070000h
0x1800086d4  test    ebx, ebx
0x1800086d6  jns     short loc_1800086F9
0x1800086d8  lea     r8, aFailedToCallWw_4; "Failed to call WwanGetProfileIstream. p"...
0x1800086df  mov     edx, 11C3h; unsigned int
0x1800086e4  mov     r9, rdi
0x1800086e7  mov     dword ptr [rsp+48h+var_28], ebx
0x1800086eb  lea     rcx, aWindowsNetwork_186; "Windows::Networking::UX::Internal::MBCa"...
0x1800086f2  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x1800086f7  jmp     short loc_18000872C
0x1800086f9  mov     eax, [rbp+arg_10]
0x1800086fc  cmp     eax, 18D8h
0x180008701  jnb     short loc_18000873D
0x180008703  mov     [rsp+48h+var_20], eax
0x180008707  lea     r8, aWwangetprofile_3; "WwanGetProfileIstream returned bad size"...
0x18000870e  mov     r9d, ebx
0x180008711  mov     [rsp+48h+var_28], rdi
0x180008716  mov     edx, 11CEh; unsigned int
0x18000871b  lea     rcx, aWindowsNetwork_186; "Windows::Networking::UX::Internal::MBCa"...
0x180008722  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x180008727  mov     ebx, 80004005h
0x18000872c  mov     rcx, [rbp+Src]
0x180008730  call    cs:__imp_WwanFreeMemory
0x180008736  mov     eax, ebx
0x180008738  jmp     loc_180008864
0x18000873d  mov     rdx, [rbp+Src]; Src
0x180008741  mov     r8d, 18B0h; Size
0x180008747  mov     rcx, rsi; void *
0x18000874a  call    memcpy_0
0x18000874f  mov     qword ptr [rsi+1168h], 0
0x18000875a  mov     qword ptr [rsi+1178h], 0
0x180008765  mov     qword ptr [rsi+18A8h], 0
0x180008770  mov     rcx, [rbp+Src]
0x180008774  call    cs:__imp_WwanFreeMemory
0x18000877a  xor     eax, eax
0x18000877c  jmp     loc_180008864
0x180008781  cmp     r8d, 1
0x180008785  jnz     loc_18000883C
0x18000878b  lea     rdx, [rcx+18h]
0x18000878f  mov     [rbp+Src], 0
0x180008797  mov     rcx, [rcx+130h]
0x18000879e  lea     r9, [rbp+Src]
0x1800087a2  mov     r8, rdi
0x1800087a5  mov     [rbp+arg_10], 0
0x1800087ac  call    cs:__imp_WwanGetDMConfigProfile
0x1800087b2  mov     ebx, eax
0x1800087b4  test    eax, eax
0x1800087b6  jle     short loc_1800087C1
0x1800087b8  movzx   ebx, ax
0x1800087bb  or      ebx, 80070000h
0x1800087c1  test    ebx, ebx
0x1800087c3  jns     short loc_1800087D6
0x1800087c5  lea     r8, aFailedToCallWw_5; "Failed to call WwanGetDMConfigProfile. "...
0x1800087cc  mov     edx, 11E9h
0x1800087d1  jmp     loc_1800086E4
0x1800087d6  mov     rdx, [rbp+Src]
0x1800087da  lea     rax, [rbp+arg_10]
0x1800087de  mov     [rsp+48h+var_20], 1
0x1800087e6  xor     r9d, r9d
0x1800087e9  xor     r8d, r8d
0x1800087ec  mov     [rsp+48h+var_28], rax
0x1800087f1  mov     rcx, rsi
0x1800087f4  call    cs:__imp_WwanProfileLoadXml
0x1800087fa  mov     ebx, eax
0x1800087fc  test    eax, eax
0x1800087fe  jle     short loc_180008809
0x180008800  movzx   ebx, ax
0x180008803  or      ebx, 80070000h
0x180008809  test    ebx, ebx
0x18000880b  jns     loc_180008770
0x180008811  mov     eax, [rbp+arg_10]
0x180008814  lea     r8, aFailedToCallWw_0; "Failed to call WwanProfileLoadXml. prof"...
0x18000881b  mov     [rsp+48h+var_20], eax
0x18000881f  lea     rcx, aWindowsNetwork_186; "Windows::Networking::UX::Internal::MBCa"...
0x180008826  mov     r9, rdi
0x180008829  mov     dword ptr [rsp+48h+var_28], ebx
0x18000882d  mov     edx, 11F5h; unsigned int
0x180008832  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x180008837  jmp     loc_18000872C
0x18000883c  mov     r9, rdi
0x18000883f  mov     dword ptr [rsp+48h+var_28], 0
0x180008847  lea     r8, aUnknownProfile; "Unknown profile type. profileName=%ls, "...
0x18000884e  mov     edx, 11FBh; unsigned int
0x180008853  lea     rcx, aWindowsNetwork_186; "Windows::Networking::UX::Internal::MBCa"...
0x18000885a  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x18000885f  mov     eax, 80070057h
0x180008864  add     rsp, 48h
0x180008868  pop     rdi
0x180008869  pop     rsi
0x18000886a  pop     rbx
0x18000886b  pop     rbp
0x18000886c  retn
```
