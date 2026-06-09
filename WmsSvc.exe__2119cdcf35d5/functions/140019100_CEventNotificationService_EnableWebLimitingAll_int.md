# CEventNotificationService::EnableWebLimitingAll(int)

- ea: `0x140019100`
- end: `0x1400192a5`
- name: `?EnableWebLimitingAll@CEventNotificationService@@UEAAJH@Z`
- size: `421`
- prototype: `__int64 __fastcall(CEventNotificationService *this, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140019100`
- `0x14005bc30`
- `0x14006c590`
- `0x140073544`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400191a8`
- `ADVAPI32!RegOpenKeyExW` at `0x1400191a8`
- `ADVAPI32!RegCloseKey` at `0x140019282`
- `ADVAPI32!RegCloseKey` at `0x140019282`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400191f0`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400191f0`
- `ADVAPI32!RegEnumKeyExW` at `0x140019223`
- `ADVAPI32!RegEnumKeyExW` at `0x140019223`
- `ADVAPI32!RegDeleteKeyW` at `0x140019255`
- `ADVAPI32!RegDeleteKeyW` at `0x140019255`
- `msvcrt!_wcsicmp` at `0x140019241`
- `msvcrt!_wcsicmp` at `0x140019241`

## string_xrefs

- `0x140019162`: `CEventNotificationService::EnableWebLimitingAll - fIsInLimiting = %d\n`

## pseudocode

```c
__int64 __fastcall CEventNotificationService::EnableWebLimitingAll(CEventNotificationService *this, unsigned int a2)
{
  int v3; // ebx
  LSTATUS v4; // eax
  bool v5; // cc
  DWORD v6; // eax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(Name, 0, 0x208u);
  cchName = 260;
  hKey = 0;
  cSubKeys = 0;
  v3 = CUserManagement::s_VerifyAccessLevelEx(3u, 0);
  if ( v3 >= 0 )
  {
    DEBUGMSG(L"CEventNotificationService::EnableWebLimitingAll - fIsInLimiting = %d\n", a2);
    v3 = EnableWebLimitAll(a2);
    if ( v3 >= 0 && !a2 )
    {
      v4 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows Multipoint Server\\Orchestration\\WebLimiting",
             0,
             0xF003Fu,
             &hKey);
      v5 = v4 <= 0;
      if ( v4 )
        goto LABEL_12;
      v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
LABEL_9:
      v5 = v4 <= 0;
      if ( v4 )
      {
LABEL_12:
        if ( v5 )
          v3 = v4;
        else
          v3 = (unsigned __int16)v4 | 0x80070000;
      }
      else
      {
        while ( 1 )
        {
          v6 = cSubKeys;
          if ( !cSubKeys )
            break;
          --cSubKeys;
          if ( RegEnumKeyExW(hKey, v6 - 1, Name, &cchName, 0, 0, 0, 0) )
            break;
          cchName = 260;
          if ( _wcsicmp(Name, L"Global") )
          {
            v4 = RegDeleteKeyW(hKey, Name);
            goto LABEL_9;
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140019100  push    rbp
0x140019102  push    rbx
0x140019103  push    rsi
0x140019104  push    rdi
0x140019105  lea     rbp, [rsp-198h]
0x14001910d  sub     rsp, 298h
0x140019114  mov     rax, cs:__security_cookie
0x14001911b  xor     rax, rsp
0x14001911e  mov     [rbp+1B0h+var_30], rax
0x140019125  mov     edi, edx
0x140019127  lea     rcx, [rsp+2B0h+Name]; void *
0x14001912c  xor     edx, edx; Val
0x14001912e  mov     r8d, 208h; Size
0x140019134  call    memset_0
0x140019139  xor     esi, esi
0x14001913b  mov     [rsp+2B0h+cchName], 104h
0x140019143  xor     edx, edx
0x140019145  mov     [rsp+2B0h+hKey], rsi
0x14001914a  mov     [rsp+2B0h+cSubKeys], esi
0x14001914e  lea     ecx, [rsi+3]
0x140019151  call    ?s_VerifyAccessLevelEx@CUserManagement@@SAJW4EUserAccessLevel@@H@Z; CUserManagement::s_VerifyAccessLevelEx(EUserAccessLevel,int)
0x140019156  mov     ebx, eax
0x140019158  test    eax, eax
0x14001915a  js      loc_140019278
0x140019160  mov     edx, edi
0x140019162  lea     rcx, aCeventnotifica_144; "CEventNotificationService::EnableWebLim"...
0x140019169  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14001916e  mov     ecx, edi; int
0x140019170  call    ?EnableWebLimitAll@@YAJH@Z; EnableWebLimitAll(int)
0x140019175  mov     ebx, eax
0x140019177  test    eax, eax
0x140019179  js      loc_140019278
0x14001917f  test    edi, edi
0x140019181  jnz     loc_140019278
0x140019187  lea     rax, [rsp+2B0h+hKey]
0x14001918c  mov     r9d, 0F003Fh; samDesired
0x140019192  xor     r8d, r8d; ulOptions
0x140019195  mov     [rsp+2B0h+phkResult], rax; phkResult
0x14001919a  lea     rdx, ?g_kszWebLimitingRegKey@@3QBGB; "Software\\Microsoft\\Windows Multipoint"...
0x1400191a1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400191a8  call    cs:__imp_RegOpenKeyExW
0x1400191ae  test    eax, eax
0x1400191b0  jnz     loc_140019269
0x1400191b6  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1400191bb  lea     rax, [rsp+2B0h+cSubKeys]
0x1400191c0  mov     [rsp+2B0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1400191c5  xor     r9d, r9d; lpReserved
0x1400191c8  mov     [rsp+2B0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x1400191cd  xor     r8d, r8d; lpcchClass
0x1400191d0  mov     [rsp+2B0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x1400191d5  xor     edx, edx; lpClass
0x1400191d7  mov     [rsp+2B0h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x1400191dc  mov     [rsp+2B0h+lpcValues], rsi; lpcValues
0x1400191e1  mov     [rsp+2B0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x1400191e6  mov     [rsp+2B0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x1400191eb  mov     [rsp+2B0h+phkResult], rax; lpcSubKeys
0x1400191f0  call    cs:__imp_RegQueryInfoKeyW
0x1400191f6  jmp     short loc_14001925B
0x1400191f8  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1400191fd  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x140019202  dec     eax
0x140019204  mov     [rsp+2B0h+lpcValues], rsi; lpftLastWriteTime
0x140019209  mov     [rsp+2B0h+lpcbMaxClassLen], rsi; lpcchClass
0x14001920e  lea     r8, [rsp+2B0h+Name]; lpName
0x140019213  mov     [rsp+2B0h+lpcbMaxSubKeyLen], rsi; lpClass
0x140019218  mov     edx, eax; dwIndex
0x14001921a  mov     [rsp+2B0h+phkResult], rsi; lpReserved
0x14001921f  mov     [rsp+2B0h+cSubKeys], eax
0x140019223  call    cs:__imp_RegEnumKeyExW
0x140019229  test    eax, eax
0x14001922b  jnz     short loc_140019278
0x14001922d  lea     rdx, ?g_kszWmsGlobal@@3QBGB; "Global"
0x140019234  mov     [rsp+2B0h+cchName], 104h
0x14001923c  lea     rcx, [rsp+2B0h+Name]; String1
0x140019241  call    cs:__imp__wcsicmp
0x140019247  test    eax, eax
0x140019249  jz      short loc_14001925F
0x14001924b  mov     rcx, [rsp+2B0h+hKey]; hKey
0x140019250  lea     rdx, [rsp+2B0h+Name]; lpSubKey
0x140019255  call    cs:__imp_RegDeleteKeyW
0x14001925b  test    eax, eax
0x14001925d  jnz     short loc_140019269
0x14001925f  mov     eax, [rsp+2B0h+cSubKeys]
0x140019263  test    eax, eax
0x140019265  jnz     short loc_1400191F8
0x140019267  jmp     short loc_140019278
0x140019269  jg      short loc_14001926F
0x14001926b  mov     ebx, eax
0x14001926d  jmp     short loc_140019278
0x14001926f  movzx   ebx, ax
0x140019272  or      ebx, 80070000h
0x140019278  mov     rcx, [rsp+2B0h+hKey]; hKey
0x14001927d  test    rcx, rcx
0x140019280  jz      short loc_140019288
0x140019282  call    cs:__imp_RegCloseKey
0x140019288  mov     eax, ebx
0x14001928a  mov     rcx, [rbp+1B0h+var_30]
0x140019291  xor     rcx, rsp; StackCookie
0x140019294  call    __security_check_cookie
0x140019299  add     rsp, 298h
0x1400192a0  pop     rdi
0x1400192a1  pop     rsi
0x1400192a2  pop     rbx
0x1400192a3  pop     rbp
0x1400192a4  retn
```
