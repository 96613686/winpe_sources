# GetEventInfo(ushort const *,EventSoundInfo *)

- ea: `0x18007fc28`
- end: `0x18007fe94`
- name: `?GetEventInfo@@YAJPEBGPEAUEventSoundInfo@@@Z`
- size: `620`
- prototype: `int(const unsigned __int16 *, struct EventSoundInfo *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800cb18c`
- `0x1800cb3c4`

## callees

- `0x1800165ac`
- `0x18007fc28`
- `0x18007fe9c`
- `0x180087e80`
- `0x180095600`
- `0x18009d564`
- `0x1800c87dc`
- `0x1800c87fc`
- `0x1800c89e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18007fe51`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18007fe51`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007fd39`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007fd39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007fcd2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007fdad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007fcd2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007fdad`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetEventInfo(const unsigned __int16 *a1, struct EventSoundInfo *a2)
{
  unsigned int ValueW; // eax
  __int64 v4; // rdx
  unsigned int v5; // ebx
  int RingerVibrateState; // eax
  const WCHAR *v7; // rbx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  int v12; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY v13[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pvData[528]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR v16[264]; // [rsp+480h] [rbp+380h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6A8h] [rbp+5A8h]

  hkey = 0;
  pcbData = 0;
  v12 = 3;
  v13[0] = 0;
  LODWORD(phkResult) = (_DWORD)a1;
  ValueW = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"Software\\Microsoft\\EventSounds\\Sounds");
  if ( ValueW )
  {
    v4 = 138;
LABEL_5:
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v4,
           (unsigned int)"avcore\\audiocore\\client\\audioplayer\\lib\\soundhelpers.cpp",
           (const char *)ValueW,
           (unsigned int)phkResult);
    goto LABEL_17;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hkey);
  if ( ValueW )
  {
    v4 = 139;
    goto LABEL_5;
  }
  pcbData = 520;
  ValueW = RegGetValueW(hkey, 0, L"Category", 2u, 0, pvData, &pcbData);
  if ( ValueW )
  {
    v4 = 143;
    goto LABEL_5;
  }
  phkResult = (PHKEY)pvData;
  ValueW = StringCchPrintfW(v16, 0x104u, L"%s\\%s", L"Software\\Microsoft\\EventSounds\\SoundCategories");
  if ( ValueW )
  {
    v4 = 146;
    goto LABEL_5;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    v13,
    0);
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v16, 0, 0x20019u, v13);
  if ( ValueW )
  {
    v4 = 147;
    goto LABEL_5;
  }
  RingerVibrateState = GetRingerVibrateState((enum Windows::Media::Internal::RingerVibrateState *)&v12);
  if ( RingerVibrateState < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"avcore\\audiocore\\client\\audioplayer\\lib\\soundhelpers.cpp",
      (const char *)(unsigned int)RingerVibrateState,
      (int)phkResult);
  v7 = off_180141448[v12];
  GetEventInfoFromRegistry(v13[0], 0, a2);
  GetEventInfoFromRegistry(v13[0], v7, a2);
  GetEventInfoFromRegistry(hkey, 0, a2);
  GetEventInfoFromRegistry(hkey, v7, a2);
  if ( *((_BYTE *)a2 + 312) )
    _o_wcscpy_s((char *)a2 + 44, 96, L"p");
  v5 = 0;
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v13);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return v5;
}

```

## disassembly

```asm
0x18007fc28  mov     [rsp-8+arg_10], rbx
0x18007fc2d  mov     [rsp-8+arg_18], rdi
0x18007fc32  push    rbp
0x18007fc33  lea     rbp, [rsp-5A0h]
0x18007fc3b  sub     rsp, 6A0h
0x18007fc42  mov     rax, cs:__security_cookie
0x18007fc49  xor     rax, rsp
0x18007fc4c  mov     [rbp+5A0h+var_10], rax
0x18007fc53  mov     rdi, rdx
0x18007fc56  mov     [rsp+6A0h+hkey], 0
0x18007fc5f  mov     [rsp+6A0h+var_658], 0
0x18007fc67  mov     [rsp+6A0h+var_654], 3
0x18007fc6f  mov     [rsp+6A0h+var_650], 0
0x18007fc78  mov     [rsp+6A0h+phkResult], rcx
0x18007fc7d  lea     r9, aSoftwareMicros; "Software\\Microsoft\\EventSounds\\Sound"...
0x18007fc84  lea     r8, aSS; "%s\\%s"
0x18007fc8b  mov     edx, 104h; unsigned __int64
0x18007fc90  lea     rcx, [rsp+6A0h+SubKey]; unsigned __int16 *
0x18007fc95  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007fc9a  test    eax, eax
0x18007fc9c  jz      short loc_18007FCA5
0x18007fc9e  mov     edx, 8Ah
0x18007fca3  jmp     short loc_18007FCE1
0x18007fca5  xor     edx, edx
0x18007fca7  lea     rcx, [rsp+6A0h+hkey]
0x18007fcac  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18007fcb1  lea     rax, [rsp+6A0h+hkey]
0x18007fcb6  mov     [rsp+6A0h+phkResult], rax; unsigned int
0x18007fcbb  mov     ebx, 20019h
0x18007fcc0  mov     r9d, ebx; samDesired
0x18007fcc3  xor     r8d, r8d; ulOptions
0x18007fcc6  lea     rdx, [rsp+6A0h+SubKey]; lpSubKey
0x18007fccb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007fcd2  call    cs:__imp_RegOpenKeyExW
0x18007fcd8  test    eax, eax
0x18007fcda  jz      short loc_18007FCFE
0x18007fcdc  mov     edx, 8Bh; void *
0x18007fce1  mov     rcx, [rbp+5A8h]; this
0x18007fce8  mov     r9d, eax; char *
0x18007fceb  lea     r8, aAvcoreAudiocor_61; "avcore\\audiocore\\client\\audioplayer"...
0x18007fcf2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007fcf7  mov     ebx, eax
0x18007fcf9  jmp     loc_18007FE59
0x18007fcfe  mov     [rsp+6A0h+var_658], 208h
0x18007fd06  lea     rax, [rsp+6A0h+var_658]
0x18007fd0b  mov     [rsp+6A0h+pcbData], rax; pcbData
0x18007fd10  lea     rax, [rbp+5A0h+var_430]
0x18007fd17  mov     [rsp+6A0h+pvData], rax; pvData
0x18007fd1c  mov     [rsp+6A0h+phkResult], 0; pdwType
0x18007fd25  mov     r9d, 2; dwFlags
0x18007fd2b  lea     r8, aCategory; "Category"
0x18007fd32  xor     edx, edx; lpSubKey
0x18007fd34  mov     rcx, [rsp+6A0h+hkey]; hkey
0x18007fd39  call    cs:__imp_RegGetValueW
0x18007fd3f  test    eax, eax
0x18007fd41  jz      short loc_18007FD4A
0x18007fd43  mov     edx, 8Fh
0x18007fd48  jmp     short loc_18007FCE1
0x18007fd4a  lea     rax, [rbp+5A0h+var_430]
0x18007fd51  mov     [rsp+6A0h+phkResult], rax
0x18007fd56  lea     r9, aSoftwareMicros_6; "Software\\Microsoft\\EventSounds\\Sound"...
0x18007fd5d  lea     r8, aSS; "%s\\%s"
0x18007fd64  mov     edx, 104h; unsigned __int64
0x18007fd69  lea     rcx, [rbp+5A0h+var_220]; unsigned __int16 *
0x18007fd70  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007fd75  test    eax, eax
0x18007fd77  jz      short loc_18007FD83
0x18007fd79  mov     edx, 92h
0x18007fd7e  jmp     loc_18007FCE1
0x18007fd83  xor     edx, edx
0x18007fd85  lea     rcx, [rsp+6A0h+var_650]
0x18007fd8a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18007fd8f  lea     rax, [rsp+6A0h+var_650]
0x18007fd94  mov     [rsp+6A0h+phkResult], rax; int
0x18007fd99  mov     r9d, ebx; samDesired
0x18007fd9c  xor     r8d, r8d; ulOptions
0x18007fd9f  lea     rdx, [rbp+5A0h+var_220]; lpSubKey
0x18007fda6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007fdad  call    cs:__imp_RegOpenKeyExW
0x18007fdb3  test    eax, eax
0x18007fdb5  jz      short loc_18007FDC1
0x18007fdb7  mov     edx, 93h
0x18007fdbc  jmp     loc_18007FCE1
0x18007fdc1  lea     rcx, [rsp+6A0h+var_654]; enum Windows::Media::Internal::RingerVibrateState *
0x18007fdc6  call    ?GetRingerVibrateState@@YAJPEAW4RingerVibrateState@Internal@Media@Windows@@@Z; GetRingerVibrateState(Windows::Media::Internal::RingerVibrateState *)
0x18007fdcb  mov     rcx, [rbp+5A8h]; this
0x18007fdd2  test    eax, eax
0x18007fdd4  jns     short loc_18007FDEA
0x18007fdd6  mov     r9d, eax; char *
0x18007fdd9  lea     r8, aAvcoreAudiocor_61; "avcore\\audiocore\\client\\audioplayer"...
0x18007fde0  mov     edx, 95h; void *
0x18007fde5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007fdea  movsxd  rax, [rsp+6A0h+var_654]
0x18007fdef  lea     rbx, off_180141448; "RingerOffVibrateOff"
0x18007fdf6  mov     rbx, [rbx+rax*8]
0x18007fdfa  mov     r8, rdi; struct EventSoundInfo *
0x18007fdfd  xor     edx, edx; lpSubKey
0x18007fdff  mov     rcx, [rsp+6A0h+var_650]; hkey
0x18007fe04  call    ?GetEventInfoFromRegistry@@YAJPEAUHKEY__@@PEBGPEAUEventSoundInfo@@@Z; GetEventInfoFromRegistry(HKEY__ *,ushort const *,EventSoundInfo *)
0x18007fe09  mov     r8, rdi; struct EventSoundInfo *
0x18007fe0c  mov     rdx, rbx; lpSubKey
0x18007fe0f  mov     rcx, [rsp+6A0h+var_650]; hkey
0x18007fe14  call    ?GetEventInfoFromRegistry@@YAJPEAUHKEY__@@PEBGPEAUEventSoundInfo@@@Z; GetEventInfoFromRegistry(HKEY__ *,ushort const *,EventSoundInfo *)
0x18007fe19  mov     r8, rdi; struct EventSoundInfo *
0x18007fe1c  xor     edx, edx; lpSubKey
0x18007fe1e  mov     rcx, [rsp+6A0h+hkey]; hkey
0x18007fe23  call    ?GetEventInfoFromRegistry@@YAJPEAUHKEY__@@PEBGPEAUEventSoundInfo@@@Z; GetEventInfoFromRegistry(HKEY__ *,ushort const *,EventSoundInfo *)
0x18007fe28  mov     r8, rdi; struct EventSoundInfo *
0x18007fe2b  mov     rdx, rbx; lpSubKey
0x18007fe2e  mov     rcx, [rsp+6A0h+hkey]; hkey
0x18007fe33  call    ?GetEventInfoFromRegistry@@YAJPEAUHKEY__@@PEBGPEAUEventSoundInfo@@@Z; GetEventInfoFromRegistry(HKEY__ *,ushort const *,EventSoundInfo *)
0x18007fe38  cmp     byte ptr [rdi+138h], 0
0x18007fe3f  jz      short loc_18007FE57
0x18007fe41  lea     rcx, [rdi+2Ch]
0x18007fe45  lea     r8, aP; "p"
0x18007fe4c  mov     edx, 60h ; '`'
0x18007fe51  call    cs:__imp__o_wcscpy_s
0x18007fe57  xor     ebx, ebx
0x18007fe59  lea     rcx, [rsp+6A0h+var_650]
0x18007fe5e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007fe63  nop
0x18007fe64  lea     rcx, [rsp+6A0h+hkey]
0x18007fe69  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007fe6e  mov     eax, ebx
0x18007fe70  mov     rcx, [rbp+5A0h+var_10]
0x18007fe77  xor     rcx, rsp; StackCookie
0x18007fe7a  call    __security_check_cookie
0x18007fe7f  lea     r11, [rsp+6A0h+var_s0]
0x18007fe87  mov     rbx, [r11+20h]
0x18007fe8b  mov     rdi, [r11+28h]
0x18007fe8f  mov     rsp, r11
0x18007fe92  pop     rbp
0x18007fe93  retn
```
