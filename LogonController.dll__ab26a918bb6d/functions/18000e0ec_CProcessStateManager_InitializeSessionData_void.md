# CProcessStateManager::_InitializeSessionData(void)

- ea: `0x18000e0ec`
- end: `0x18000e332`
- name: `?_InitializeSessionData@CProcessStateManager@@AEAAXXZ`
- size: `582`
- prototype: `void __fastcall(CProcessStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d2c8`

## callees

- `0x180004b70`
- `0x18000e0ec`
- `0x18006c000`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e194`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e290`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e194`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e290`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e246`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e308`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e246`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e308`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e1d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e1d1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e153`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e233`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e153`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e233`

## pseudocode

```c
void __fastcall CProcessStateManager::_InitializeSessionData(CProcessStateManager *this)
{
  char v2; // bl
  LSTATUS ValueW; // eax
  int v4; // ecx
  HKEY v5; // rcx
  bool v6; // di
  LSTATUS v7; // eax
  signed int v8; // ecx
  HKEY v9; // rcx
  DWORD dwDisposition; // [rsp+58h] [rbp+7h] BYREF
  unsigned int v11; // [rsp+60h] [rbp+Fh] BYREF
  HKEY hKey; // [rsp+68h] [rbp+17h] BYREF
  HKEY hkey; // [rsp+70h] [rbp+1Fh] BYREF
  int pvData; // [rsp+78h] [rbp+27h] BYREF
  WCHAR SubKey[8]; // [rsp+80h] [rbp+2Fh] BYREF

  v2 = 1;
  hkey = 0;
  if ( RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\SessionData",
         0,
         0,
         1u,
         0x2001Fu,
         0,
         &hkey,
         0) )
  {
    goto LABEL_21;
  }
  pvData = 0;
  dwDisposition = 4;
  ValueW = RegGetValueW(hkey, 0, L"BootLogon", 0x10u, 0, &pvData, &dwDisposition);
  v4 = -2147024896;
  dwDisposition = 0;
  if ( ValueW <= 0 )
    v4 = ValueW;
  *((_BYTE *)this + 120) = v4 < 0;
  RegSetValueExW(hkey, L"BootLogon", 0, 4u, (const BYTE *)&dwDisposition, 4u);
  if ( (int)StringCchPrintfW(SubKey, 8u, L"%d", NtCurrentPeb()->SessionId) >= 0 )
  {
    hKey = 0;
    dwDisposition = 0;
    RegCreateKeyExW(hkey, SubKey, 0, 0, 1u, 0x2001Fu, 0, &hKey, &dwDisposition);
    v5 = hKey;
    hKey = 0;
    if ( v5 )
      RegCloseKey(v5);
  }
  LODWORD(hKey) = 0;
  dwDisposition = 4;
  v6 = 0;
  v7 = RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\SessionData",
         L"AllowLockScreen",
         0x10000012u,
         (LPDWORD)&hKey,
         &v11,
         &dwDisposition);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 == 234 )
    {
      LOWORD(v8) = 13;
    }
    else if ( v7 <= 0 )
    {
      goto LABEL_18;
    }
    goto LABEL_17;
  }
  LOWORD(v8) = 13;
  if ( (_DWORD)hKey != 4 )
  {
    if ( dwDisposition == 4 && (unsigned __int16)(v11 - 48) <= 1u )
    {
      v8 = 0;
      v6 = (_WORD)v11 == 49;
      goto LABEL_18;
    }
LABEL_17:
    v8 = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_18;
  }
  if ( v11 > 1 )
    goto LABEL_17;
  v8 = 0;
  v6 = v11 == 1;
LABEL_18:
  if ( v8 >= 0 )
    v2 = v6;
  *((_BYTE *)this + 121) = v2;
LABEL_21:
  v9 = hkey;
  hkey = 0;
  if ( v9 )
    RegCloseKey(v9);
}

```

## disassembly

```asm
0x18000e0ec  mov     r11, rsp
0x18000e0ef  mov     [r11+10h], rbx
0x18000e0f3  mov     [r11+18h], rsi
0x18000e0f7  push    rbp
0x18000e0f8  push    rdi
0x18000e0f9  push    r14
0x18000e0fb  lea     rbp, [r11-5Fh]
0x18000e0ff  sub     rsp, 90h
0x18000e106  mov     rax, cs:__security_cookie
0x18000e10d  xor     rax, rsp
0x18000e110  mov     [rbp+57h+var_18], rax
0x18000e114  xor     r14d, r14d
0x18000e117  lea     rax, [rbp+57h+hkey]
0x18000e11b  mov     [r11-68h], r14
0x18000e11f  lea     rdx, aSoftwareMicros_26; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000e126  mov     [r11-70h], rax
0x18000e12a  mov     rsi, rcx
0x18000e12d  mov     [r11-78h], r14
0x18000e131  mov     edi, 2001Fh
0x18000e136  lea     ebx, [r14+1]
0x18000e13a  mov     [rsp+0A0h+samDesired], edi; samDesired
0x18000e13e  xor     r9d, r9d; lpClass
0x18000e141  mov     [rsp+0A0h+dwOptions], ebx; dwOptions
0x18000e145  xor     r8d, r8d; Reserved
0x18000e148  mov     [rbp+57h+hkey], r14
0x18000e14c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e153  call    cs:__imp_RegCreateKeyExW
0x18000e159  test    eax, eax
0x18000e15b  jnz     loc_18000E2FB
0x18000e161  mov     rcx, [rbp+57h+hkey]; hkey
0x18000e165  lea     rax, [rbp+57h+dwDisposition]
0x18000e169  mov     [rsp+0A0h+pcbData], rax; pcbData
0x18000e16e  lea     r9d, [r14+10h]; dwFlags
0x18000e172  lea     rax, [rbp+57h+pvData]
0x18000e176  mov     [rbp+57h+pvData], r14d
0x18000e17a  mov     qword ptr [rsp+0A0h+samDesired], rax; pvData
0x18000e17f  lea     r8, aBootlogon; "BootLogon"
0x18000e186  xor     edx, edx; lpSubKey
0x18000e188  mov     qword ptr [rsp+0A0h+dwOptions], r14; pdwType
0x18000e18d  mov     [rbp+57h+dwDisposition], 4
0x18000e194  call    cs:__imp_RegGetValueW
0x18000e19a  mov     ecx, 80070000h
0x18000e19f  mov     [rsp+0A0h+samDesired], 4; cbData
0x18000e1a7  test    eax, eax
0x18000e1a9  mov     [rbp+57h+dwDisposition], r14d
0x18000e1ad  lea     r9d, [r14+4]; dwType
0x18000e1b1  cmovle  ecx, eax
0x18000e1b4  lea     rdx, aBootlogon; "BootLogon"
0x18000e1bb  shr     ecx, 1Fh
0x18000e1be  lea     rax, [rbp+57h+dwDisposition]
0x18000e1c2  mov     [rsi+78h], cl
0x18000e1c5  xor     r8d, r8d; Reserved
0x18000e1c8  mov     rcx, [rbp+57h+hkey]; hKey
0x18000e1cc  mov     qword ptr [rsp+0A0h+dwOptions], rax; lpData
0x18000e1d1  call    cs:__imp_RegSetValueExW
0x18000e1d7  mov     r9, gs:60h
0x18000e1e0  lea     r8, aD; "%d"
0x18000e1e7  lea     edx, [rbx+7]; unsigned __int64
0x18000e1ea  lea     rcx, [rbp+57h+SubKey]; unsigned __int16 *
0x18000e1ee  mov     r9d, [r9+2C0h]
0x18000e1f5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e1fa  test    eax, eax
0x18000e1fc  js      short loc_18000E24C
0x18000e1fe  mov     rcx, [rbp+57h+hkey]; hKey
0x18000e202  lea     rax, [rbp+57h+dwDisposition]
0x18000e206  mov     [rsp+0A0h+lpdwDisposition], rax; lpdwDisposition
0x18000e20b  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18000e20f  lea     rax, [rbp+57h+hKey]
0x18000e213  mov     [rbp+57h+hKey], r14
0x18000e217  mov     [rsp+0A0h+phkResult], rax; phkResult
0x18000e21c  xor     r9d, r9d; lpClass
0x18000e21f  mov     [rsp+0A0h+pcbData], r14; lpSecurityAttributes
0x18000e224  xor     r8d, r8d; Reserved
0x18000e227  mov     [rsp+0A0h+samDesired], edi; samDesired
0x18000e22b  mov     [rsp+0A0h+dwOptions], ebx; dwOptions
0x18000e22f  mov     [rbp+57h+dwDisposition], r14d
0x18000e233  call    cs:__imp_RegCreateKeyExW
0x18000e239  mov     rcx, [rbp+57h+hKey]; hKey
0x18000e23d  mov     [rbp+57h+hKey], r14
0x18000e241  test    rcx, rcx
0x18000e244  jz      short loc_18000E24C
0x18000e246  call    cs:__imp_RegCloseKey
0x18000e24c  lea     rax, [rbp+57h+dwDisposition]
0x18000e250  mov     dword ptr [rbp+57h+hKey], r14d
0x18000e254  mov     [rsp+0A0h+pcbData], rax; pcbData
0x18000e259  lea     r8, aAllowlockscree; "AllowLockScreen"
0x18000e260  lea     rax, [rbp+57h+var_48]
0x18000e264  mov     [rbp+57h+dwDisposition], 4
0x18000e26b  mov     qword ptr [rsp+0A0h+samDesired], rax; pvData
0x18000e270  lea     rdx, aSoftwareMicros_26; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000e277  lea     rax, [rbp+57h+hKey]
0x18000e27b  mov     r9d, 10000012h; dwFlags
0x18000e281  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000e288  mov     qword ptr [rsp+0A0h+dwOptions], rax; pdwType
0x18000e28d  mov     edi, r14d
0x18000e290  call    cs:__imp_RegGetValueW
0x18000e296  mov     ecx, eax
0x18000e298  test    eax, eax
0x18000e29a  jnz     short loc_18000E2D8
0x18000e29c  cmp     dword ptr [rbp+57h+hKey], 4
0x18000e2a0  lea     ecx, [rax+0Dh]
0x18000e2a3  jnz     short loc_18000E2B3
0x18000e2a5  cmp     [rbp+57h+var_48], ebx
0x18000e2a8  ja      short loc_18000E2EA
0x18000e2aa  mov     ecx, r14d
0x18000e2ad  setz    dil
0x18000e2b1  jmp     short loc_18000E2F3
0x18000e2b3  cmp     [rbp+57h+dwDisposition], 4
0x18000e2b7  jnz     short loc_18000E2EA
0x18000e2b9  movzx   eax, word ptr [rbp+57h+var_48]
0x18000e2bd  sub     ax, 30h ; '0'
0x18000e2c1  cmp     ax, bx
0x18000e2c4  ja      short loc_18000E2EA
0x18000e2c6  mov     eax, 31h ; '1'
0x18000e2cb  mov     ecx, r14d
0x18000e2ce  cmp     ax, word ptr [rbp+57h+var_48]
0x18000e2d2  setz    dil
0x18000e2d6  jmp     short loc_18000E2F3
0x18000e2d8  cmp     eax, 0EAh
0x18000e2dd  jnz     short loc_18000E2E6
0x18000e2df  mov     ecx, 0Dh
0x18000e2e4  jmp     short loc_18000E2EA
0x18000e2e6  test    eax, eax
0x18000e2e8  jle     short loc_18000E2F3
0x18000e2ea  movzx   ecx, cx
0x18000e2ed  or      ecx, 80070000h
0x18000e2f3  test    ecx, ecx
0x18000e2f5  cmovns  ebx, edi
0x18000e2f8  mov     [rsi+79h], bl
0x18000e2fb  mov     rcx, [rbp+57h+hkey]; hKey
0x18000e2ff  mov     [rbp+57h+hkey], r14
0x18000e303  test    rcx, rcx
0x18000e306  jz      short loc_18000E30E
0x18000e308  call    cs:__imp_RegCloseKey
0x18000e30e  mov     rcx, [rbp+57h+var_18]
0x18000e312  xor     rcx, rsp; StackCookie
0x18000e315  call    __security_check_cookie
0x18000e31a  lea     r11, [rsp+0A0h+var_10]
0x18000e322  mov     rbx, [r11+28h]
0x18000e326  mov     rsi, [r11+30h]
0x18000e32a  mov     rsp, r11
0x18000e32d  pop     r14
0x18000e32f  pop     rdi
0x18000e330  pop     rbp
0x18000e331  retn
```
