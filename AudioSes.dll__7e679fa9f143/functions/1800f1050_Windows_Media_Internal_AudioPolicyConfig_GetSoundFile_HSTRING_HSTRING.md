# Windows::Media::Internal::AudioPolicyConfig::GetSoundFile(HSTRING__ *,HSTRING__ * *)

- ea: `0x1800f1050`
- end: `0x1800f124f`
- name: `?GetSoundFile@AudioPolicyConfig@Internal@Media@Windows@@UEAAJPEAUHSTRING__@@PEAPEAU5@@Z`
- size: `511`
- prototype: `int(Windows::Media::Internal::AudioPolicyConfig *__hidden this, HSTRING, HSTRING *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180010a90`
- `0x1800165ac`
- `0x180087e80`
- `0x18009d564`
- `0x1800f1050`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f1120`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f11a8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f1120`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f11a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f11ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f1210`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f11ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f1210`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1091`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1134`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1091`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1134`

## string_xrefs

- `0x1800f10ce`: `avcore\audiocore\client\audiopolicymanager\lib\audiopolicyconfigmanager.cpp`
- `0x1800f11db`: `avcore\audiocore\client\audiopolicymanager\lib\audiopolicyconfigmanager.cpp`

## pseudocode

```c
HRESULT __fastcall Windows::Media::Internal::AudioPolicyConfig::GetSoundFile(
        Windows::Media::Internal::AudioPolicyConfig *this,
        HSTRING a2,
        HSTRING *a3)
{
  HRESULT String; // ebx
  __int64 v6; // rdx
  unsigned int ValueW; // eax
  __int64 v9; // rdx
  unsigned int pdwType; // [rsp+20h] [rbp-E0h]
  DWORD pcbData[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR sourceString[264]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+498h] [rbp+398h]

  pcbData[0] = 520;
  pdwType = (unsigned int)WindowsGetStringRawBuffer(a2, 0);
  String = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"OSDATA\\SOFTWARE\\Microsoft\\EventSounds\\Sounds");
  if ( String < 0 )
  {
    v6 = 1510;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"avcore\\audiocore\\client\\audiopolicymanager\\lib\\audiopolicyconfigmanager.cpp",
      (const char *)(unsigned int)String,
      pdwType);
    return String;
  }
  pcbData[0] = 520;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"Sound", 2u, 0, sourceString, pcbData);
  if ( ValueW != 2 )
    goto LABEL_10;
  pdwType = (unsigned int)WindowsGetStringRawBuffer(a2, 0);
  String = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"Software\\Microsoft\\EventSounds\\Sounds");
  if ( String < 0 )
  {
    v6 = 1523;
    goto LABEL_3;
  }
  pcbData[0] = 520;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"Sound", 2u, 0, sourceString, pcbData);
  if ( ValueW == 2 )
  {
    String = WindowsCreateString(0, 0, a3);
    if ( String < 0 )
    {
      v6 = 1532;
      goto LABEL_3;
    }
  }
  else
  {
LABEL_10:
    if ( ValueW )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x602,
               (unsigned int)"avcore\\audiocore\\client\\audiopolicymanager\\lib\\audiopolicyconfigmanager.cpp",
               (const char *)ValueW,
               pdwType);
    v9 = -1;
    do
      ++v9;
    while ( sourceString[v9] );
    String = WindowsCreateString(sourceString, v9, a3);
    if ( String < 0 )
    {
      v6 = 1543;
      goto LABEL_3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800f1050  mov     [rsp-8+arg_0], rbx
0x1800f1055  mov     [rsp-8+arg_18], rsi
0x1800f105a  push    rbp
0x1800f105b  push    rdi
0x1800f105c  push    r14
0x1800f105e  lea     rbp, [rsp-380h]
0x1800f1066  sub     rsp, 480h
0x1800f106d  mov     rax, cs:__security_cookie
0x1800f1074  xor     rax, rsp
0x1800f1077  mov     [rbp+390h+var_20], rax
0x1800f107e  mov     rsi, rdx
0x1800f1081  mov     [rsp+490h+var_450], 208h
0x1800f1089  mov     rcx, rsi; string
0x1800f108c  xor     edx, edx; length
0x1800f108e  mov     rdi, r8
0x1800f1091  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f1097  lea     r9, aOsdataSoftware; "OSDATA\\SOFTWARE\\Microsoft\\EventSound"...
0x1800f109e  mov     edx, 104h; unsigned __int64
0x1800f10a3  lea     r8, aSS; "%s\\%s"
0x1800f10aa  mov     [rsp+490h+pdwType], rax; int
0x1800f10af  lea     rcx, [rsp+490h+SubKey]; unsigned __int16 *
0x1800f10b4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800f10b9  xor     r14d, r14d
0x1800f10bc  mov     ebx, eax
0x1800f10be  test    eax, eax
0x1800f10c0  jns     short loc_1800F10E4
0x1800f10c2  mov     edx, 5E6h; void *
0x1800f10c7  mov     rcx, [rbp+398h]; this
0x1800f10ce  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\client\\audiopolicym"...
0x1800f10d5  mov     r9d, ebx; char *
0x1800f10d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f10dd  mov     eax, ebx
0x1800f10df  jmp     loc_1800F1228
0x1800f10e4  lea     rax, [rsp+490h+var_450]
0x1800f10e9  mov     [rsp+490h+var_450], 208h
0x1800f10f1  mov     [rsp+490h+pcbData], rax; pcbData
0x1800f10f6  lea     r8, aSound_0; "Sound"
0x1800f10fd  lea     rax, [rbp+390h+sourceString]
0x1800f1104  mov     r9d, 2; dwFlags
0x1800f110a  mov     [rsp+490h+pvData], rax; pvData
0x1800f110f  lea     rdx, [rsp+490h+SubKey]; lpSubKey
0x1800f1114  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800f111b  mov     [rsp+490h+pdwType], r14; unsigned int
0x1800f1120  call    cs:__imp_RegGetValueW
0x1800f1126  cmp     eax, 2
0x1800f1129  jnz     loc_1800F11D0
0x1800f112f  xor     edx, edx; length
0x1800f1131  mov     rcx, rsi; string
0x1800f1134  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f113a  lea     r9, aSoftwareMicros; "Software\\Microsoft\\EventSounds\\Sound"...
0x1800f1141  mov     edx, 104h; unsigned __int64
0x1800f1146  lea     r8, aSS; "%s\\%s"
0x1800f114d  mov     [rsp+490h+pdwType], rax
0x1800f1152  lea     rcx, [rsp+490h+SubKey]; unsigned __int16 *
0x1800f1157  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800f115c  mov     ebx, eax
0x1800f115e  test    eax, eax
0x1800f1160  jns     short loc_1800F116C
0x1800f1162  mov     edx, 5F3h
0x1800f1167  jmp     loc_1800F10C7
0x1800f116c  lea     rax, [rsp+490h+var_450]
0x1800f1171  mov     [rsp+490h+var_450], 208h
0x1800f1179  mov     [rsp+490h+pcbData], rax; pcbData
0x1800f117e  lea     r8, aSound_0; "Sound"
0x1800f1185  lea     rax, [rbp+390h+sourceString]
0x1800f118c  mov     r9d, 2; dwFlags
0x1800f1192  mov     [rsp+490h+pvData], rax; pvData
0x1800f1197  lea     rdx, [rsp+490h+SubKey]; lpSubKey
0x1800f119c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800f11a3  mov     [rsp+490h+pdwType], r14; pdwType
0x1800f11a8  call    cs:__imp_RegGetValueW
0x1800f11ae  cmp     eax, 2
0x1800f11b1  jnz     short loc_1800F11D0
0x1800f11b3  mov     r8, rdi; string
0x1800f11b6  xor     edx, edx; length
0x1800f11b8  xor     ecx, ecx; sourceString
0x1800f11ba  call    cs:__imp_WindowsCreateString
0x1800f11c0  mov     ebx, eax
0x1800f11c2  test    eax, eax
0x1800f11c4  jns     short loc_1800F1226
0x1800f11c6  mov     edx, 5FCh
0x1800f11cb  jmp     loc_1800F10C7
0x1800f11d0  test    eax, eax
0x1800f11d2  jz      short loc_1800F11F1
0x1800f11d4  mov     rcx, [rbp+398h]; this
0x1800f11db  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\client\\audiopolicym"...
0x1800f11e2  mov     r9d, eax; char *
0x1800f11e5  mov     edx, 602h; void *
0x1800f11ea  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800f11ef  jmp     short loc_1800F1228
0x1800f11f1  lea     rax, [rbp+390h+sourceString]
0x1800f11f8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800f11fc  inc     rdx; length
0x1800f11ff  cmp     [rax+rdx*2], r14w
0x1800f1204  jnz     short loc_1800F11FC
0x1800f1206  mov     r8, rdi; string
0x1800f1209  lea     rcx, [rbp+390h+sourceString]; sourceString
0x1800f1210  call    cs:__imp_WindowsCreateString
0x1800f1216  mov     ebx, eax
0x1800f1218  test    eax, eax
0x1800f121a  jns     short loc_1800F1226
0x1800f121c  mov     edx, 607h
0x1800f1221  jmp     loc_1800F10C7
0x1800f1226  xor     eax, eax
0x1800f1228  mov     rcx, [rbp+390h+var_20]
0x1800f122f  xor     rcx, rsp; StackCookie
0x1800f1232  call    __security_check_cookie
0x1800f1237  lea     r11, [rsp+490h+var_10]
0x1800f123f  mov     rbx, [r11+20h]
0x1800f1243  mov     rsi, [r11+38h]
0x1800f1247  mov     rsp, r11
0x1800f124a  pop     r14
0x1800f124c  pop     rdi
0x1800f124d  pop     rbp
0x1800f124e  retn
```
