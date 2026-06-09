# RoutingRegistryHelper::WriteAppletIdRegKeys(HKEY__ *,_AppletId *,ulong)

- ea: `0x18003c0c4`
- end: `0x18003c2a0`
- name: `?WriteAppletIdRegKeys@RoutingRegistryHelper@@CAJPEAUHKEY__@@PEAU_AppletId@@K@Z`
- size: `476`
- prototype: `__int64 __fastcall(HKEY, struct _AppletId *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003bc1c`

## callees

- `0x1800049a0`
- `0x18000d4ec`
- `0x18003c0c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c197`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c197`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c1aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c1aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c1a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c243`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c261`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c270`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c1a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c243`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c261`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c270`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c134`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c1e6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c134`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c1e6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c227`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c227`

## pseudocode

```c
__int64 __fastcall RoutingRegistryHelper::WriteAppletIdRegKeys(HKEY a1, const BYTE *a2, unsigned int a3)
{
  LSTATUS v5; // eax
  signed int v6; // edi
  __int64 v7; // rsi
  int v8; // eax
  HKEY v9; // r14
  DWORD LastError; // ebx
  bool v11; // sf
  HKEY v12; // rcx
  bool v13; // sf
  HKEY hKey; // [rsp+58h] [rbp-9h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-1h] BYREF
  WCHAR SubKey[8]; // [rsp+68h] [rbp+7h] BYREF
  __int128 v18; // [rsp+78h] [rbp+17h]

  phkResult = 0;
  v5 = RegCreateKeyExW(a1, L"AppletIds", 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 >= 0 )
  {
    v6 = 0;
    v7 = 0;
    if ( a3 )
    {
      while ( 1 )
      {
        hKey = 0;
        *(_OWORD *)SubKey = 0;
        v18 = 0;
        v8 = StringCchPrintfW(SubKey, 0x10u, L"%d", (unsigned int)v7);
        if ( v8 < 0 )
          break;
        v9 = hKey;
        if ( hKey )
        {
          LastError = GetLastError();
          RegCloseKey(v9);
          SetLastError(LastError);
        }
        hKey = 0;
        v8 = RegCreateKeyExW(phkResult, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
        v11 = v8 < 0;
        if ( v8 > 0 )
        {
          v8 = (unsigned __int16)v8 | 0x80070000;
          v11 = v8 < 0;
        }
        v12 = hKey;
        if ( v11 )
          goto LABEL_19;
        v8 = RegSetValueExW(hKey, L"AppletId", 0, 3u, &a2[20 * v7 + 4], *(_DWORD *)&a2[20 * v7]);
        v13 = v8 < 0;
        if ( v8 > 0 )
        {
          v8 = (unsigned __int16)v8 | 0x80070000;
          v13 = v8 < 0;
        }
        v12 = hKey;
        if ( v13 )
          goto LABEL_19;
        if ( hKey )
          RegCloseKey(hKey);
        v7 = (unsigned int)(v7 + 1);
        if ( (unsigned int)v7 >= a3 )
          goto LABEL_21;
      }
      v12 = hKey;
LABEL_19:
      v6 = v8;
      if ( v12 )
        RegCloseKey(v12);
    }
  }
LABEL_21:
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003c0c4  mov     r11, rsp
0x18003c0c7  mov     [r11+18h], rbx
0x18003c0cb  mov     [r11+20h], rsi
0x18003c0cf  push    rbp
0x18003c0d0  push    rdi
0x18003c0d1  push    r12
0x18003c0d3  push    r14
0x18003c0d5  push    r15
0x18003c0d7  lea     rbp, [r11-5Fh]
0x18003c0db  sub     rsp, 90h
0x18003c0e2  mov     rax, cs:__security_cookie
0x18003c0e9  xor     rax, rsp
0x18003c0ec  mov     [rbp+57h+var_30], rax
0x18003c0f0  mov     qword ptr [r11-78h], 0
0x18003c0f8  lea     rax, [rbp+57h+var_58]
0x18003c0fc  mov     [r11-80h], rax
0x18003c100  mov     r15d, r8d
0x18003c103  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003c10c  mov     r12, rdx
0x18003c10f  mov     [rsp+0B0h+samDesired], 2001Fh; samDesired
0x18003c117  lea     rdx, aAppletids; "AppletIds"
0x18003c11e  xor     r9d, r9d; lpClass
0x18003c121  mov     [rsp+0B0h+dwOptions], 0; dwOptions
0x18003c129  xor     r8d, r8d; Reserved
0x18003c12c  mov     [rbp+57h+var_58], 0
0x18003c134  call    cs:__imp_RegCreateKeyExW
0x18003c13a  mov     edi, eax
0x18003c13c  mov     ebx, 80070000h
0x18003c141  test    eax, eax
0x18003c143  jle     short loc_18003C14A
0x18003c145  movzx   edi, ax
0x18003c148  or      edi, ebx
0x18003c14a  test    edi, edi
0x18003c14c  js      loc_18003C267
0x18003c152  xor     edi, edi
0x18003c154  xor     esi, esi
0x18003c156  test    r15d, r15d
0x18003c159  jz      loc_18003C267
0x18003c15f  xorps   xmm0, xmm0
0x18003c162  mov     [rbp+57h+hKey], rdi
0x18003c166  mov     r9d, esi
0x18003c169  lea     r8, aD; "%d"
0x18003c170  mov     edx, 10h; unsigned __int64
0x18003c175  lea     rcx, [rbp+57h+SubKey]; unsigned __int16 *
0x18003c179  movups  xmmword ptr [rbp+57h+SubKey], xmm0
0x18003c17d  movups  [rbp+57h+var_40], xmm0
0x18003c181  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c186  test    eax, eax
0x18003c188  js      loc_18003C256
0x18003c18e  mov     r14, [rbp+57h+hKey]
0x18003c192  test    r14, r14
0x18003c195  jz      short loc_18003C1B5
0x18003c197  call    cs:__imp_GetLastError
0x18003c19d  mov     rcx, r14; hKey
0x18003c1a0  mov     ebx, eax
0x18003c1a2  call    cs:__imp_RegCloseKey
0x18003c1a8  mov     ecx, ebx; dwErrCode
0x18003c1aa  call    cs:__imp_SetLastError
0x18003c1b0  mov     ebx, 80070000h
0x18003c1b5  mov     rcx, [rbp+57h+var_58]; hKey
0x18003c1b9  lea     rax, [rbp+57h+hKey]
0x18003c1bd  mov     [rsp+0B0h+lpdwDisposition], rdi; lpdwDisposition
0x18003c1c2  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18003c1c6  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18003c1cb  xor     r9d, r9d; lpClass
0x18003c1ce  mov     [rsp+0B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18003c1d3  xor     r8d, r8d; Reserved
0x18003c1d6  mov     [rsp+0B0h+samDesired], 2001Fh; samDesired
0x18003c1de  mov     [rsp+0B0h+dwOptions], edi; dwOptions
0x18003c1e2  mov     [rbp+57h+hKey], rdi
0x18003c1e6  call    cs:__imp_RegCreateKeyExW
0x18003c1ec  test    eax, eax
0x18003c1ee  jle     short loc_18003C1F7
0x18003c1f0  movzx   eax, ax
0x18003c1f3  or      eax, ebx
0x18003c1f5  test    eax, eax
0x18003c1f7  mov     rcx, [rbp+57h+hKey]; hKey
0x18003c1fb  js      short loc_18003C25A
0x18003c1fd  lea     rax, [rsi+rsi*4]
0x18003c201  mov     r9d, 3; dwType
0x18003c207  lea     rdx, [r12+4]
0x18003c20c  xor     r8d, r8d; Reserved
0x18003c20f  lea     rdx, [rdx+rax*4]
0x18003c213  mov     eax, [r12+rax*4]
0x18003c217  mov     [rsp+0B0h+samDesired], eax; cbData
0x18003c21b  mov     qword ptr [rsp+0B0h+dwOptions], rdx; lpData
0x18003c220  lea     rdx, aAppletid; "AppletId"
0x18003c227  call    cs:__imp_RegSetValueExW
0x18003c22d  test    eax, eax
0x18003c22f  jle     short loc_18003C238
0x18003c231  movzx   eax, ax
0x18003c234  or      eax, ebx
0x18003c236  test    eax, eax
0x18003c238  mov     rcx, [rbp+57h+hKey]; hKey
0x18003c23c  js      short loc_18003C25A
0x18003c23e  test    rcx, rcx
0x18003c241  jz      short loc_18003C249
0x18003c243  call    cs:__imp_RegCloseKey
0x18003c249  inc     esi
0x18003c24b  cmp     esi, r15d
0x18003c24e  jb      loc_18003C15F
0x18003c254  jmp     short loc_18003C267
0x18003c256  mov     rcx, [rbp+57h+hKey]; hKey
0x18003c25a  mov     edi, eax
0x18003c25c  test    rcx, rcx
0x18003c25f  jz      short loc_18003C267
0x18003c261  call    cs:__imp_RegCloseKey
0x18003c267  mov     rcx, [rbp+57h+var_58]; hKey
0x18003c26b  test    rcx, rcx
0x18003c26e  jz      short loc_18003C276
0x18003c270  call    cs:__imp_RegCloseKey
0x18003c276  mov     eax, edi
0x18003c278  mov     rcx, [rbp+57h+var_30]
0x18003c27c  xor     rcx, rsp; StackCookie
0x18003c27f  call    __security_check_cookie
0x18003c284  lea     r11, [rsp+0B0h+var_20]
0x18003c28c  mov     rbx, [r11+40h]
0x18003c290  mov     rsi, [r11+48h]
0x18003c294  mov     rsp, r11
0x18003c297  pop     r15
0x18003c299  pop     r14
0x18003c29b  pop     r12
0x18003c29d  pop     rdi
0x18003c29e  pop     rbp
0x18003c29f  retn
```
