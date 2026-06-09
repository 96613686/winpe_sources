# CAutoLogonManager::_GetRegistryAutoLogonCredential(ushort *,ulong,ushort *,ulong,ushort *,ulong)

- ea: `0x18003dee8`
- end: `0x18003e15a`
- name: `?_GetRegistryAutoLogonCredential@CAutoLogonManager@@AEAAJPEAGK0K0K@Z`
- size: `626`
- prototype: `__int64 __fastcall(CAutoLogonManager *this, unsigned __int16 *, __int64, unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003dbe0`

## callees

- `0x1800325c0`
- `0x180039bb0`
- `0x18003dee8`
- `0x18004eeb4`
- `0x180065c38`
- `0x18006c000`
- `0x180092340`
- `0x1800923f0`
- `0x180092444`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003dfbd`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003dfce`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003dfbd`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003dfce`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003df96`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e009`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e0ad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003df96`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e009`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e0ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003df4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003df4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e12e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e12e`

## pseudocode

```c
__int64 __fastcall CAutoLogonManager::_GetRegistryAutoLogonCredential(
        CAutoLogonManager *this,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int16 *a6)
{
  LSTATUS v9; // eax
  signed int v10; // edi
  LSTATUS ValueW; // eax
  wchar_t *v12; // rbx
  wchar_t *v13; // rax
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  __int64 v16; // rcx
  bool v17; // sf
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // r8d
  int v21; // r9d
  DWORD pcbData; // [rsp+40h] [rbp-30h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-28h] BYREF
  DWORD v25; // [rsp+50h] [rbp-20h] BYREF

  *a2 = 0;
  *a4 = 0;
  *a6 = 0;
  hkey = 0;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", 0, 3u, &hkey);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 >= 0 )
  {
    pcbData = 512;
    ValueW = RegGetValueW(hkey, 0, L"DefaultUserName", 2u, 0, a4, &pcbData);
    v10 = ValueW;
    if ( ValueW )
    {
      *a4 = 0;
      if ( ValueW > 0 )
        v10 = (unsigned __int16)ValueW | 0x80070000;
    }
    if ( v10 >= 0 )
    {
      v12 = wcschr(a4, 0x40u);
      v13 = wcschr(a4, 0x5Cu);
      if ( v12 || v13 )
        goto LABEL_18;
      pcbData = 512;
      v14 = RegGetValueW(hkey, 0, L"DefaultDomainName", 2u, 0, a2, &pcbData);
      v10 = v14;
      if ( v14 )
      {
        *a2 = 0;
        if ( v14 > 0 )
          v10 = (unsigned __int16)v14 | 0x80070000;
      }
      if ( v10 >= 0 && !*a2 || v10 == -2147024894 )
        v10 = StringCchCopyW(a2, 0x100u, L".");
      if ( v10 >= 0 )
      {
LABEL_18:
        pcbData = 0;
        SHRegGetDWORD(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
          L"IsConnectedAutoLogon",
          &pcbData);
        if ( !pcbData )
        {
          v25 = 512;
          v15 = RegGetValueW(hkey, 0, L"DefaultPassword", 2u, 0, a6, &v25);
          v17 = v15 < 0;
          if ( v15 )
          {
            *a6 = 0;
            if ( v15 > 0 )
              v17 = 1;
          }
          if ( v17 && (int)GetLsaSecret(v16, a6) < 0 )
          {
            *a6 = 0;
            CleanupAutoLogon();
            if ( (Microsoft_Windows_Shell_AuthUIEnableBits & 2) != 0 )
              McTemplateU0q_EventWriteTransfer(v19, v18, 2);
            CAutoLogonManager::_UpdateAutoLogonMode(this, 4, v20, v21);
            if ( (Microsoft_Windows_Shell_AuthUIEnableBits & 1) != 0 )
              McGenEventWrite_EventWriteTransfer(
                &Microsoft_Windows_Shell_AuthUI_Context,
                Operational_AutoLogonGetPasswordFailed);
          }
        }
      }
    }
    RegCloseKey(hkey);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003dee8  mov     [rsp-38h+arg_10], rbx
0x18003deed  push    rbp
0x18003deee  push    rsi
0x18003deef  push    rdi
0x18003def0  push    r12
0x18003def2  push    r13
0x18003def4  push    r14
0x18003def6  push    r15
0x18003def8  mov     rbp, rsp
0x18003defb  sub     rsp, 70h
0x18003deff  mov     rax, cs:__security_cookie
0x18003df06  xor     rax, rsp
0x18003df09  mov     [rbp+var_8], rax
0x18003df0d  mov     rsi, [rbp+arg_28]
0x18003df11  lea     rax, [rbp+hkey]
0x18003df15  xor     r13d, r13d
0x18003df18  mov     [rsp+70h+phkResult], rax; phkResult
0x18003df1d  mov     [rdx], r13w
0x18003df21  mov     r15, r9
0x18003df24  mov     [r9], r13w
0x18003df28  mov     r14, rdx
0x18003df2b  mov     r12, rcx
0x18003df2e  mov     [rsi], r13w
0x18003df32  lea     r9d, [r13+3]; samDesired
0x18003df36  mov     [rbp+hkey], r13
0x18003df3a  xor     r8d, r8d; ulOptions
0x18003df3d  lea     rdx, aSoftwareMicros_33; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003df44  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003df4b  call    cs:__imp_RegOpenKeyExW
0x18003df51  mov     edi, eax
0x18003df53  mov     ebx, 80070000h
0x18003df58  test    eax, eax
0x18003df5a  jle     short loc_18003DF61
0x18003df5c  movzx   edi, ax
0x18003df5f  or      edi, ebx
0x18003df61  test    edi, edi
0x18003df63  js      loc_18003E134
0x18003df69  mov     rcx, [rbp+hkey]; hkey
0x18003df6d  lea     rax, [rbp+var_30]
0x18003df71  mov     [rsp+70h+pcbData], rax; pcbData
0x18003df76  lea     r8, aDefaultusernam; "DefaultUserName"
0x18003df7d  mov     [rsp+70h+pvData], r15; pvData
0x18003df82  mov     r9d, 2; dwFlags
0x18003df88  xor     edx, edx; lpSubKey
0x18003df8a  mov     [rsp+70h+phkResult], r13; pdwType
0x18003df8f  mov     [rbp+var_30], 200h
0x18003df96  call    cs:__imp_RegGetValueW
0x18003df9c  mov     edi, eax
0x18003df9e  test    eax, eax
0x18003dfa0  jz      short loc_18003DFAD
0x18003dfa2  mov     [r15], r13w
0x18003dfa6  jle     short loc_18003DFAD
0x18003dfa8  movzx   edi, ax
0x18003dfab  or      edi, ebx
0x18003dfad  test    edi, edi
0x18003dfaf  js      loc_18003E12A
0x18003dfb5  mov     edx, 40h ; '@'; Ch
0x18003dfba  mov     rcx, r15; Str
0x18003dfbd  call    cs:__imp_wcschr
0x18003dfc3  mov     edx, 5Ch ; '\'; Ch
0x18003dfc8  mov     rcx, r15; Str
0x18003dfcb  mov     rbx, rax
0x18003dfce  call    cs:__imp_wcschr
0x18003dfd4  test    rbx, rbx
0x18003dfd7  jnz     short loc_18003E054
0x18003dfd9  test    rax, rax
0x18003dfdc  jnz     short loc_18003E054
0x18003dfde  mov     rcx, [rbp+hkey]; hkey
0x18003dfe2  lea     rax, [rbp+var_30]
0x18003dfe6  mov     [rsp+70h+pcbData], rax; pcbData
0x18003dfeb  lea     r9d, [rbx+2]; dwFlags
0x18003dfef  mov     [rsp+70h+pvData], r14; pvData
0x18003dff4  lea     r8, aDefaultdomainn; "DefaultDomainName"
0x18003dffb  xor     edx, edx; lpSubKey
0x18003dffd  mov     [rsp+70h+phkResult], r13; pdwType
0x18003e002  mov     [rbp+var_30], 200h
0x18003e009  call    cs:__imp_RegGetValueW
0x18003e00f  mov     edi, eax
0x18003e011  test    eax, eax
0x18003e013  jz      short loc_18003E024
0x18003e015  mov     [r14], r13w
0x18003e019  jle     short loc_18003E024
0x18003e01b  movzx   edi, ax
0x18003e01e  or      edi, 80070000h
0x18003e024  test    edi, edi
0x18003e026  js      short loc_18003E02E
0x18003e028  cmp     [r14], r13w
0x18003e02c  jz      short loc_18003E036
0x18003e02e  cmp     edi, 80070002h
0x18003e034  jnz     short loc_18003E04C
0x18003e036  lea     r8, String1; "."
0x18003e03d  mov     edx, 100h; unsigned __int64
0x18003e042  mov     rcx, r14; unsigned __int16 *
0x18003e045  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003e04a  mov     edi, eax
0x18003e04c  test    edi, edi
0x18003e04e  js      loc_18003E12A
0x18003e054  lea     r9, [rbp+var_30]; unsigned int *
0x18003e058  mov     [rbp+var_30], r13d
0x18003e05c  lea     r8, aIsconnectedaut; "IsConnectedAutoLogon"
0x18003e063  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18003e06a  lea     rdx, aSoftwareMicros_33; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003e071  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18003e076  cmp     [rbp+var_30], r13d
0x18003e07a  jnz     loc_18003E12A
0x18003e080  mov     rcx, [rbp+hkey]; hkey
0x18003e084  lea     rax, [rbp+var_20]
0x18003e088  mov     [rsp+70h+pcbData], rax; pcbData
0x18003e08d  lea     r8, SourceString; "DefaultPassword"
0x18003e094  mov     [rsp+70h+pvData], rsi; pvData
0x18003e099  mov     r9d, 2; dwFlags
0x18003e09f  xor     edx, edx; lpSubKey
0x18003e0a1  mov     [rsp+70h+phkResult], r13; pdwType
0x18003e0a6  mov     [rbp+var_20], 200h
0x18003e0ad  call    cs:__imp_RegGetValueW
0x18003e0b3  test    eax, eax
0x18003e0b5  jz      short loc_18003E0C7
0x18003e0b7  mov     [rsi], r13w
0x18003e0bb  jle     short loc_18003E0C7
0x18003e0bd  movzx   eax, ax
0x18003e0c0  or      eax, 80070000h
0x18003e0c5  test    eax, eax
0x18003e0c7  jns     short loc_18003E12A
0x18003e0c9  mov     rdx, rsi
0x18003e0cc  call    _GetLsaSecret
0x18003e0d1  test    eax, eax
0x18003e0d3  jns     short loc_18003E12A
0x18003e0d5  mov     [rsi], r13w
0x18003e0d9  call    _CleanupAutoLogon
0x18003e0de  test    cs:Microsoft_Windows_Shell_AuthUIEnableBits, 2
0x18003e0e5  jz      short loc_18003E0F2
0x18003e0e7  mov     r8d, 2
0x18003e0ed  call    McTemplateU0q_EventWriteTransfer
0x18003e0f2  mov     edx, 4; int
0x18003e0f7  mov     rcx, r12; this
0x18003e0fa  call    ?_UpdateAutoLogonMode@CAutoLogonManager@@AEAAXHHH@Z; CAutoLogonManager::_UpdateAutoLogonMode(int,int,int)
0x18003e0ff  mov     r9d, 1
0x18003e105  test    cs:Microsoft_Windows_Shell_AuthUIEnableBits, r9b
0x18003e10c  jz      short loc_18003E12A
0x18003e10e  lea     rax, [rbp+var_18]
0x18003e112  lea     rdx, Operational_AutoLogonGetPasswordFailed
0x18003e119  mov     [rsp+70h+phkResult], rax
0x18003e11e  lea     rcx, Microsoft_Windows_Shell_AuthUI_Context
0x18003e125  call    McGenEventWrite_EventWriteTransfer
0x18003e12a  mov     rcx, [rbp+hkey]; hKey
0x18003e12e  call    cs:__imp_RegCloseKey
0x18003e134  mov     eax, edi
0x18003e136  mov     rcx, [rbp+var_8]
0x18003e13a  xor     rcx, rsp; StackCookie
0x18003e13d  call    __security_check_cookie
0x18003e142  mov     rbx, [rsp+70h+arg_10]
0x18003e14a  add     rsp, 70h
0x18003e14e  pop     r15
0x18003e150  pop     r14
0x18003e152  pop     r13
0x18003e154  pop     r12
0x18003e156  pop     rdi
0x18003e157  pop     rsi
0x18003e158  pop     rbp
0x18003e159  retn
```
