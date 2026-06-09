# SelectMidiClassDriver(ushort const *,ushort const *)

- ea: `0x18005725c`
- end: `0x18005756e`
- name: `?SelectMidiClassDriver@@YAJPEBG0@Z`
- size: `786`
- prototype: `__int64 __fastcall(const unsigned __int16 *, BYTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180045c80`

## callees

- `0x180010da8`
- `0x18003e920`
- `0x18003f7a4`
- `0x180057118`
- `0x18005725c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800574a7`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800574a7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800573a2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800573a2`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800574b7`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800574b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057310`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800573e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057491`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057310`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800573e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057491`
- `SETUPAPI!SetupDiSetDevicePropertyW` at `0x180057521`
- `SETUPAPI!SetupDiSetDevicePropertyW` at `0x180057521`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x180057423`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x180057423`
- `SETUPAPI!SetupDiBuildDriverInfoList` at `0x1800573d7`
- `SETUPAPI!SetupDiBuildDriverInfoList` at `0x1800573d7`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x1800572fd`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x1800572fd`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x180057383`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x180057383`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180057348`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180057348`
- `SETUPAPI!SetupDiGetDriverInfoDetailW` at `0x180057487`
- `SETUPAPI!SetupDiGetDriverInfoDetailW` at `0x180057487`
- `NEWDEV!DiInstallDevice` at `0x1800574e4`
- `NEWDEV!DiInstallDevice` at `0x1800574e4`

## string_xrefs

- `0x1800572b3`: `avcore\audiocore\server\audioendpointbuilder\dll\midibuilder.cpp`

## pseudocode

```c
__int64 __fastcall SelectMidiClassDriver(const unsigned __int16 *a1, BYTE *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  signed int LastError; // eax
  DWORD v7; // r14d
  char v8; // di
  __int64 v9; // r8
  signed int v10; // eax
  DWORD v11; // esi
  char v12; // dl
  __int16 v13; // r8
  int v14; // r9d
  __int64 v15; // rax
  int RequiredSize; // [rsp+20h] [rbp-E0h]
  wchar_t RequiredSizea; // [rsp+20h] [rbp-E0h]
  PDWORD v19; // [rsp+28h] [rbp-D8h]
  __int64 ClassDevsW; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v21; // [rsp+48h] [rbp-B8h] BYREF
  WINBOOL NeedReboot; // [rsp+4Ch] [rbp-B4h] BYREF
  _SP_DEVINFO_DATA DeviceInfoData; // [rsp+50h] [rbp-B0h] BYREF
  struct _SP_DRVINFO_DATA_V2_W DeviceInstanceId; // [rsp+70h] [rbp-90h] BYREF
  _SP_DRVINFO_DETAIL_DATA_W DriverInfoDetailData; // [rsp+690h] [rbp+590h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D08h] [rbp+C08h]

  ClassDevsW = -1;
  if ( !a2 )
  {
    v4 = 58;
LABEL_3:
    v5 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\midibuilder.cpp",
      (const char *)(unsigned int)v5,
      RequiredSize);
    goto LABEL_33;
  }
  if ( !a1 )
  {
    v4 = 59;
    goto LABEL_3;
  }
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  DeviceInfoData.cbSize = 32;
  ClassDevsW = (__int64)SetupDiGetClassDevsW(&GUID_DEVCLASS_MEDIA, L"USB", 0, 4u);
  if ( ClassDevsW == -1 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
    {
      v4 = 65;
      goto LABEL_4;
    }
  }
  else
  {
    v7 = 0;
    v8 = 0;
    while ( 1 )
    {
      if ( !SetupDiEnumDeviceInfo((HDEVINFO)ClassDevsW, v7, &DeviceInfoData) )
        goto LABEL_32;
      ++v7;
      memset_0(&DeviceInstanceId, 0, 0x208u);
      if ( SetupDiGetDeviceInstanceIdW((HDEVINFO)ClassDevsW, &DeviceInfoData, (PWSTR)&DeviceInstanceId, 0x104u, 0) )
      {
        v9 = -1;
        do
          ++v9;
        while ( a1[v9] );
        if ( !(unsigned int)_o__wcsnicmp(a1, &DeviceInstanceId) )
          break;
      }
    }
    memset_0(&DeviceInstanceId.DriverType, 0, 0x61Cu);
    wcscpy((wchar_t *)&DeviceInstanceId, L"ؠ");
    if ( SetupDiBuildDriverInfoList((HDEVINFO)ClassDevsW, &DeviceInfoData, 2u) )
    {
      v11 = 0;
      while ( SetupDiEnumDriverInfoW((HDEVINFO)ClassDevsW, &DeviceInfoData, 2u, v11, &DeviceInstanceId) && !v8 )
      {
        NeedReboot = 0;
        v21 = 0;
        ++v11;
        memset_0(&DriverInfoDetailData.InfDate, 0, 0x62Cu);
        DriverInfoDetailData.cbSize = 1584;
        if ( SetupDiGetDriverInfoDetailW(
               (HDEVINFO)ClassDevsW,
               &DeviceInfoData,
               &DeviceInstanceId,
               &DriverInfoDetailData,
               0x630u,
               &v21)
          || GetLastError() == 122 )
        {
          o((wchar_t)DriverInfoDetailData.InfFileName, v12, v13, v14, RequiredSizea, *(long double *)&v19);
          if ( wcsstr(DriverInfoDetailData.InfFileName, (const wchar_t *)a2) )
          {
            DiInstallDevice(
              0,
              (HDEVINFO)ClassDevsW,
              &DeviceInfoData,
              (PSP_DRVINFO_DATA)&DeviceInstanceId,
              0,
              &NeedReboot);
            v15 = -1;
            do
              ++v15;
            while ( *(_WORD *)&a2[2 * v15] );
            SetupDiSetDevicePropertyW(
              (HDEVINFO)ClassDevsW,
              &DeviceInfoData,
              &PKEY_DriverSwitchedByAEB,
              0x12u,
              a2,
              2 * v15 + 2,
              0);
            v8 = 1;
          }
        }
      }
LABEL_32:
      v5 = v8 == 0;
      goto LABEL_33;
    }
    v10 = GetLastError();
    v5 = v10;
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
    if ( v5 < 0 )
    {
      v4 = 96;
      goto LABEL_4;
    }
  }
LABEL_33:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int SetupDiDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int SetupDiDestroyDeviceInfoList(void *)>>(&ClassDevsW);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005725c  mov     [rsp-8+arg_10], rbx
0x180057261  push    rbp
0x180057262  push    rsi
0x180057263  push    rdi
0x180057264  push    r12
0x180057266  push    r13
0x180057268  push    r14
0x18005726a  push    r15
0x18005726c  lea     rbp, [rsp-0BD0h]
0x180057274  sub     rsp, 0CD0h
0x18005727b  mov     rax, cs:__security_cookie
0x180057282  xor     rax, rsp
0x180057285  mov     [rbp+0C00h+var_40], rax
0x18005728c  or      r13, 0FFFFFFFFFFFFFFFFh
0x180057290  xor     r12d, r12d
0x180057293  mov     [rsp+0D00h+var_CC0], r13
0x180057298  mov     r15, rdx
0x18005729b  mov     rsi, rcx
0x18005729e  test    rdx, rdx
0x1800572a1  jnz     short loc_1800572C7
0x1800572a3  lea     edx, [r15+3Ah]; void *
0x1800572a7  mov     ebx, 80070057h
0x1800572ac  mov     rcx, [rbp+0C08h]; this
0x1800572b3  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audioendpoin"...
0x1800572ba  mov     r9d, ebx; char *
0x1800572bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800572c2  jmp     loc_180057538
0x1800572c7  test    rsi, rsi
0x1800572ca  jnz     short loc_1800572D1
0x1800572cc  lea     edx, [rsi+3Bh]
0x1800572cf  jmp     short loc_1800572A7
0x1800572d1  xorps   xmm0, xmm0
0x1800572d4  lea     rdx, Enumerator; "USB"
0x1800572db  movups  xmmword ptr [rsp+0D00h+DeviceInfoData.cbSize], xmm0
0x1800572e0  mov     r9d, 4; Flags
0x1800572e6  mov     [rsp+0D00h+DeviceInfoData.cbSize], 20h ; ' '
0x1800572ee  xor     r8d, r8d; hwndParent
0x1800572f1  lea     rcx, GUID_DEVCLASS_MEDIA; ClassGuid
0x1800572f8  movups  xmmword ptr [rsp+0D00h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x1800572fd  call    cs:__imp_SetupDiGetClassDevsW
0x180057303  mov     [rsp+0D00h+var_CC0], rax
0x180057308  mov     rbx, rax
0x18005730b  cmp     rax, r13
0x18005730e  jnz     short loc_180057337
0x180057310  call    cs:__imp_GetLastError
0x180057316  mov     ebx, eax
0x180057318  test    eax, eax
0x18005731a  jle     short loc_180057325
0x18005731c  movzx   ebx, ax
0x18005731f  or      ebx, 80070000h
0x180057325  test    ebx, ebx
0x180057327  jns     loc_180057538
0x18005732d  mov     edx, 41h ; 'A'
0x180057332  jmp     loc_1800572AC
0x180057337  mov     r14d, r12d
0x18005733a  mov     dil, r12b
0x18005733d  lea     r8, [rsp+0D00h+DeviceInfoData]; DeviceInfoData
0x180057342  mov     edx, r14d; MemberIndex
0x180057345  mov     rcx, rbx; DeviceInfoSet
0x180057348  call    cs:__imp_SetupDiEnumDeviceInfo
0x18005734e  test    eax, eax
0x180057350  jz      loc_18005752F
0x180057356  xor     edx, edx; Val
0x180057358  lea     rcx, [rsp+0D00h+DeviceInstanceId]; void *
0x18005735d  mov     r8d, 208h; Size
0x180057363  inc     r14d
0x180057366  call    memset_0
0x18005736b  mov     r9d, 104h; DeviceInstanceIdSize
0x180057371  mov     [rsp+0D00h+RequiredSize], r12; RequiredSize
0x180057376  lea     r8, [rsp+0D00h+DeviceInstanceId]; DeviceInstanceId
0x18005737b  mov     rcx, rbx; DeviceInfoSet
0x18005737e  lea     rdx, [rsp+0D00h+DeviceInfoData]; DeviceInfoData
0x180057383  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x180057389  test    eax, eax
0x18005738b  jz      short loc_18005733D
0x18005738d  mov     r8, r13
0x180057390  inc     r8
0x180057393  cmp     [rsi+r8*2], r12w
0x180057398  jnz     short loc_180057390
0x18005739a  lea     rdx, [rsp+0D00h+DeviceInstanceId]
0x18005739f  mov     rcx, rsi
0x1800573a2  call    cs:__imp__o__wcsnicmp
0x1800573a8  test    eax, eax
0x1800573aa  jnz     short loc_18005733D
0x1800573ac  xor     edx, edx; Val
0x1800573ae  lea     rcx, [rsp+0D00h+var_C8C]; void *
0x1800573b3  mov     r8d, 61Ch; Size
0x1800573b9  call    memset_0
0x1800573be  mov     r14d, 2
0x1800573c4  mov     dword ptr [rsp+0D00h+DeviceInstanceId], 620h
0x1800573cc  mov     r8d, r14d; DriverType
0x1800573cf  lea     rdx, [rsp+0D00h+DeviceInfoData]; DeviceInfoData
0x1800573d4  mov     rcx, rbx; DeviceInfoSet
0x1800573d7  call    cs:__imp_SetupDiBuildDriverInfoList
0x1800573dd  test    eax, eax
0x1800573df  jnz     short loc_180057408
0x1800573e1  call    cs:__imp_GetLastError
0x1800573e7  mov     ebx, eax
0x1800573e9  test    eax, eax
0x1800573eb  jle     short loc_1800573F6
0x1800573ed  movzx   ebx, ax
0x1800573f0  or      ebx, 80070000h
0x1800573f6  test    ebx, ebx
0x1800573f8  jns     loc_180057538
0x1800573fe  mov     edx, 60h ; '`'
0x180057403  jmp     loc_1800572AC
0x180057408  mov     esi, r12d
0x18005740b  lea     rax, [rsp+0D00h+DeviceInstanceId]
0x180057410  mov     r9d, esi; MemberIndex
0x180057413  mov     r8d, r14d; DriverType
0x180057416  mov     [rsp+0D00h+RequiredSize], rax; DriverInfoData
0x18005741b  lea     rdx, [rsp+0D00h+DeviceInfoData]; DeviceInfoData
0x180057420  mov     rcx, rbx; DeviceInfoSet
0x180057423  call    cs:__imp_SetupDiEnumDriverInfoW
0x180057429  test    eax, eax
0x18005742b  jz      loc_18005752F
0x180057431  test    dil, dil
0x180057434  jnz     loc_18005752F
0x18005743a  xor     edx, edx; Val
0x18005743c  mov     [rsp+0D00h+NeedReboot], r12d
0x180057441  mov     r8d, 62Ch; Size
0x180057447  mov     [rsp+0D00h+var_CB8], r12d
0x18005744c  lea     rcx, [rbp+0C00h+DriverInfoDetailData.InfDate]; void *
0x180057453  inc     esi
0x180057455  call    memset_0
0x18005745a  mov     ecx, 630h
0x18005745f  lea     rax, [rsp+0D00h+var_CB8]
0x180057464  mov     [rsp+0D00h+var_CD8], rax; RequiredSize
0x180057469  lea     r9, [rbp+0C00h+DriverInfoDetailData]; DriverInfoDetailData
0x180057470  mov     dword ptr [rsp+0D00h+RequiredSize], ecx; DriverInfoDetailDataSize
0x180057474  lea     r8, [rsp+0D00h+DeviceInstanceId]; DriverInfoData
0x180057479  mov     [rbp+0C00h+DriverInfoDetailData.cbSize], ecx
0x18005747f  lea     rdx, [rsp+0D00h+DeviceInfoData]; DeviceInfoData
0x180057484  mov     rcx, rbx; DeviceInfoSet
0x180057487  call    cs:__imp_SetupDiGetDriverInfoDetailW
0x18005748d  test    eax, eax
0x18005748f  jnz     short loc_1800574A0
0x180057491  call    cs:__imp_GetLastError
0x180057497  cmp     eax, 7Ah ; 'z'
0x18005749a  jnz     loc_18005740B
0x1800574a0  lea     rcx, [rbp+0C00h+DriverInfoDetailData.InfFileName]
0x1800574a7  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1800574ad  mov     rdx, r15; SubStr
0x1800574b0  lea     rcx, [rbp+0C00h+DriverInfoDetailData.InfFileName]; Str
0x1800574b7  call    cs:__imp_wcsstr
0x1800574bd  test    rax, rax
0x1800574c0  jz      loc_18005740B
0x1800574c6  lea     rax, [rsp+0D00h+NeedReboot]
0x1800574cb  mov     rdx, rbx; DeviceInfoSet
0x1800574ce  mov     [rsp+0D00h+var_CD8], rax; NeedReboot
0x1800574d3  lea     r9, [rsp+0D00h+DeviceInstanceId]; DriverInfoData
0x1800574d8  lea     r8, [rsp+0D00h+DeviceInfoData]; DeviceInfoData
0x1800574dd  mov     dword ptr [rsp+0D00h+RequiredSize], r12d; Flags
0x1800574e2  xor     ecx, ecx; hwndParent
0x1800574e4  call    cs:__imp_DiInstallDevice
0x1800574ea  mov     rax, r13
0x1800574ed  inc     rax
0x1800574f0  cmp     [r15+rax*2], r12w
0x1800574f5  jnz     short loc_1800574ED
0x1800574f7  lea     eax, ds:2[rax*2]
0x1800574fe  mov     [rsp+0D00h+Flags], r12d; Flags
0x180057503  mov     dword ptr [rsp+0D00h+var_CD8], eax; PropertyBufferSize
0x180057507  lea     r8, ?PKEY_DriverSwitchedByAEB@@3U_tagpropertykey@@A; PropertyKey
0x18005750e  mov     r9d, 12h; PropertyType
0x180057514  mov     [rsp+0D00h+RequiredSize], r15; PropertyBuffer
0x180057519  lea     rdx, [rsp+0D00h+DeviceInfoData]; DeviceInfoData
0x18005751e  mov     rcx, rbx; DeviceInfoSet
0x180057521  call    cs:__imp_SetupDiSetDevicePropertyW
0x180057527  mov     dil, 1
0x18005752a  jmp     loc_18005740B
0x18005752f  test    dil, dil
0x180057532  mov     ebx, r12d
0x180057535  setz    bl
0x180057538  lea     rcx, [rsp+0D00h+var_CC0]
0x18005753d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?SetupDiDestroyDeviceInfoList@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&SetupDiDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&SetupDiDestroyDeviceInfoList(void *)>>(void)
0x180057542  mov     eax, ebx
0x180057544  mov     rcx, [rbp+0C00h+var_40]
0x18005754b  xor     rcx, rsp; StackCookie
0x18005754e  call    __security_check_cookie
0x180057553  mov     rbx, [rsp+0D00h+arg_10]
0x18005755b  add     rsp, 0CD0h
0x180057562  pop     r15
0x180057564  pop     r14
0x180057566  pop     r13
0x180057568  pop     r12
0x18005756a  pop     rdi
0x18005756b  pop     rsi
0x18005756c  pop     rbp
0x18005756d  retn
```
