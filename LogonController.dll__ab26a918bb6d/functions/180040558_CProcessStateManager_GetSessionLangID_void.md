# CProcessStateManager::GetSessionLangID(void)

- ea: `0x180040558`
- end: `0x1800406bf`
- name: `?GetSessionLangID@CProcessStateManager@@QEAAGXZ`
- size: `359`
- prototype: `unsigned __int16 __fastcall(CProcessStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040310`

## callees

- `0x180004b70`
- `0x180040558`
- `0x18006c000`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800406a7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800406a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800405b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040607`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800405b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040607`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040620`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004064f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040620`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004064f`

## pseudocode

```c
__int64 __fastcall CProcessStateManager::GetSessionLangID(CProcessStateManager *this)
{
  ULONG SessionId; // ebx
  LSTATUS v2; // eax
  bool v3; // sf
  signed int v4; // ebx
  LSTATUS v5; // eax
  __int16 v6; // ax
  int v7; // ecx
  unsigned __int16 v8; // bx
  HKEY v9; // rcx
  unsigned int pvData; // [rsp+40h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-20h] BYREF
  WCHAR SubKey[8]; // [rsp+58h] [rbp-18h] BYREF

  hkey = 0;
  pvData = 0;
  hKey = 0;
  SessionId = NtCurrentPeb()->SessionId;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\SessionData",
         0,
         8u,
         &hKey);
  v3 = v2 < 0;
  if ( v2 > 0 )
    v3 = 1;
  if ( !v3 )
  {
    v4 = StringCchPrintfW(SubKey, 8u, L"%d", SessionId);
    if ( v4 >= 0 )
    {
      v5 = RegOpenKeyExW(hKey, SubKey, 0, 1u, &hkey);
      v4 = v5;
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
    }
    RegCloseKey(hKey);
    if ( v4 >= 0 )
    {
      LODWORD(hKey) = 4;
      RegGetValueW(hkey, 0, L"UserLanguageID", 0x10u, 0, &pvData, (LPDWORD)&hKey);
    }
  }
  v6 = pvData;
  if ( pvData > 0x7FFF )
  {
    v6 = -1;
    v7 = -2147024362;
  }
  else
  {
    v7 = 0;
  }
  v8 = 0;
  v3 = v7 < 0;
  v9 = hkey;
  hkey = 0;
  if ( !v3 )
    v8 = v6;
  if ( v9 )
    RegCloseKey(v9);
  return v8;
}

```

## disassembly

```asm
0x180040558  mov     [rsp-8+arg_0], rbx
0x18004055d  push    rbp
0x18004055e  mov     rbp, rsp
0x180040561  sub     rsp, 70h
0x180040565  mov     rax, cs:__security_cookie
0x18004056c  xor     rax, rsp
0x18004056f  mov     [rbp+var_8], rax
0x180040573  mov     [rbp+hkey], 0
0x18004057b  lea     rdx, aSoftwareMicros_26; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180040582  mov     [rbp+var_30], 0
0x180040589  mov     r9d, 8; samDesired
0x18004058f  mov     rax, gs:60h
0x180040598  xor     r8d, r8d; ulOptions
0x18004059b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800405a2  mov     [rbp+hKey], 0
0x1800405aa  mov     ebx, [rax+2C0h]
0x1800405b0  lea     rax, [rbp+hKey]
0x1800405b4  mov     [rsp+70h+phkResult], rax; phkResult
0x1800405b9  call    cs:__imp_RegOpenKeyExW
0x1800405bf  test    eax, eax
0x1800405c1  jle     short loc_1800405CD
0x1800405c3  movzx   eax, ax
0x1800405c6  or      eax, 80070000h
0x1800405cb  test    eax, eax
0x1800405cd  js      short loc_18004062A
0x1800405cf  mov     r9d, ebx
0x1800405d2  lea     r8, aD; "%d"
0x1800405d9  mov     edx, 8; unsigned __int64
0x1800405de  lea     rcx, [rbp+SubKey]; unsigned __int16 *
0x1800405e2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800405e7  mov     ebx, eax
0x1800405e9  test    eax, eax
0x1800405eb  js      short loc_18004061C
0x1800405ed  mov     rcx, [rbp+hKey]; hKey
0x1800405f1  lea     rax, [rbp+hkey]
0x1800405f5  mov     r9d, 1; samDesired
0x1800405fb  mov     [rsp+70h+phkResult], rax; phkResult
0x180040600  xor     r8d, r8d; ulOptions
0x180040603  lea     rdx, [rbp+SubKey]; lpSubKey
0x180040607  call    cs:__imp_RegOpenKeyExW
0x18004060d  mov     ebx, eax
0x18004060f  test    eax, eax
0x180040611  jle     short loc_18004061C
0x180040613  movzx   ebx, ax
0x180040616  or      ebx, 80070000h
0x18004061c  mov     rcx, [rbp+hKey]; hKey
0x180040620  call    cs:__imp_RegCloseKey
0x180040626  test    ebx, ebx
0x180040628  jns     short loc_180040672
0x18004062a  mov     eax, [rbp+var_30]
0x18004062d  cmp     eax, 7FFFh
0x180040632  ja      short loc_1800406B2
0x180040634  xor     ecx, ecx
0x180040636  xor     ebx, ebx
0x180040638  test    ecx, ecx
0x18004063a  mov     rcx, [rbp+hkey]; hKey
0x18004063e  mov     [rbp+hkey], 0
0x180040646  cmovns  bx, ax
0x18004064a  test    rcx, rcx
0x18004064d  jz      short loc_180040655
0x18004064f  call    cs:__imp_RegCloseKey
0x180040655  movzx   eax, bx
0x180040658  mov     rcx, [rbp+var_8]
0x18004065c  xor     rcx, rsp; StackCookie
0x18004065f  call    __security_check_cookie
0x180040664  mov     rbx, [rsp+70h+arg_0]
0x18004066c  add     rsp, 70h
0x180040670  pop     rbp
0x180040671  retn
0x180040672  mov     rcx, [rbp+hkey]; hkey
0x180040676  lea     rax, [rbp+hKey]
0x18004067a  mov     [rsp+70h+pcbData], rax; pcbData
0x18004067f  lea     r8, aUserlanguageid; "UserLanguageID"
0x180040686  lea     rax, [rbp+var_30]
0x18004068a  mov     dword ptr [rbp+hKey], 4
0x180040691  mov     [rsp+70h+pvData], rax; pvData
0x180040696  mov     r9d, 10h; dwFlags
0x18004069c  xor     edx, edx; lpSubKey
0x18004069e  mov     [rsp+70h+phkResult], 0; pdwType
0x1800406a7  call    cs:__imp_RegGetValueW
0x1800406ad  jmp     loc_18004062A
0x1800406b2  or      eax, 0FFFFFFFFh
0x1800406b5  mov     ecx, 80070216h
0x1800406ba  jmp     loc_180040636
```
