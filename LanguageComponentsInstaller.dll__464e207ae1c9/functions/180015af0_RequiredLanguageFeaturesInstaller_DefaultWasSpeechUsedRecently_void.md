# RequiredLanguageFeaturesInstaller::DefaultWasSpeechUsedRecently(void)

- ea: `0x180015af0`
- end: `0x180015bb1`
- name: `?DefaultWasSpeechUsedRecently@RequiredLanguageFeaturesInstaller@@CA_NXZ`
- size: `193`
- prototype: `char(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180003520`
- `0x180015af0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015b4c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015b4c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180015b64`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180015b64`

## pseudocode

```c
char RequiredLanguageFeaturesInstaller::DefaultWasSpeechUsedRecently(void)
{
  char v0; // bl
  struct _FILETIME v2; // [rsp+40h] [rbp-28h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int64 v4; // [rsp+50h] [rbp-18h] BYREF

  v4 = 0;
  v2.dwLowDateTime = 8;
  v0 = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Speech_OneCore\\CloudSettings",
          L"LastCheck",
          0x48u,
          0,
          &v4,
          (LPDWORD)&v2) )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    if ( v4 > *(_QWORD *)&SystemTimeAsFileTime || *(_QWORD *)&SystemTimeAsFileTime - v4 < 0x1600A3910000LL )
      return 1;
  }
  return v0;
}

```

## disassembly

```asm
0x180015af0  mov     r11, rsp
0x180015af3  push    rbx
0x180015af4  sub     rsp, 60h
0x180015af8  mov     rax, cs:__security_cookie
0x180015aff  xor     rax, rsp
0x180015b02  mov     [rsp+68h+var_10], rax
0x180015b07  lea     rax, [r11-28h]
0x180015b0b  mov     qword ptr [r11-18h], 0
0x180015b13  mov     [r11-38h], rax
0x180015b17  lea     r8, aLastcheck; "LastCheck"
0x180015b1e  lea     rax, [r11-18h]
0x180015b22  mov     dword ptr [rsp+68h+var_28], 8
0x180015b2a  mov     [r11-40h], rax
0x180015b2e  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Speech_OneCore\\Cl"...
0x180015b35  mov     r9d, 48h ; 'H'; dwFlags
0x180015b3b  mov     qword ptr [r11-48h], 0
0x180015b43  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180015b4a  xor     bl, bl
0x180015b4c  call    cs:__imp_RegGetValueW
0x180015b52  test    eax, eax
0x180015b54  jnz     short loc_180015B9C
0x180015b56  lea     rcx, [rsp+68h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180015b5b  mov     qword ptr [rsp+68h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180015b64  call    cs:__imp_GetSystemTimeAsFileTime
0x180015b6a  mov     eax, [rsp+68h+SystemTimeAsFileTime.dwHighDateTime]
0x180015b6e  mov     dword ptr [rsp+68h+var_28+4], eax
0x180015b72  mov     eax, [rsp+68h+SystemTimeAsFileTime.dwLowDateTime]
0x180015b76  mov     dword ptr [rsp+68h+var_28], eax
0x180015b7a  mov     rax, [rsp+68h+var_28]
0x180015b7f  cmp     [rsp+68h+var_18], rax
0x180015b84  ja      short loc_180015B9A
0x180015b86  sub     rax, [rsp+68h+var_18]
0x180015b8b  mov     rcx, 1600A3910000h
0x180015b95  cmp     rax, rcx
0x180015b98  jnb     short loc_180015B9C
0x180015b9a  mov     bl, 1
0x180015b9c  mov     al, bl
0x180015b9e  mov     rcx, [rsp+68h+var_10]
0x180015ba3  xor     rcx, rsp; StackCookie
0x180015ba6  call    __security_check_cookie
0x180015bab  add     rsp, 60h
0x180015baf  pop     rbx
0x180015bb0  retn
```
