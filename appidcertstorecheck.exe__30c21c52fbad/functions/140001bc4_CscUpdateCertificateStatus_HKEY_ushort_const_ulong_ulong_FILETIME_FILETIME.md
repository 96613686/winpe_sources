# CscUpdateCertificateStatus(HKEY__ *,ushort const *,ulong,ulong,_FILETIME *,_FILETIME *)

- ea: `0x140001bc4`
- end: `0x140001f9a`
- name: `?CscUpdateCertificateStatus@@YAKPEAUHKEY__@@PEBGKKPEAU_FILETIME@@2@Z`
- size: `982`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, int, int, FILETIME *lpFileTime2, FILETIME *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140001fa0`

## callees

- `0x140001bc4`
- `0x140002334`
- `0x14000239c`
- `0x140002b48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001f54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001f54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140001f6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140001f6e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001c2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001c2a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001c66`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001d1b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001dc3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001e7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001c66`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001d1b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001dc3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001e7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001f0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001f7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001f0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001f7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140001cdc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140001d88`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140001e3f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140001ef8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140001cdc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140001d88`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140001e3f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140001ef8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140001f45`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140001f45`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140001de4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140001e9d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140001de4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140001e9d`

## pseudocode

```c
__int64 __fastcall CscUpdateCertificateStatus(
        HKEY a1,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        FILETIME *lpFileTime2,
        FILETIME *a6)
{
  DWORD LastError; // ebx
  int v8; // edi
  LSTATUS v9; // eax
  __int64 v10; // r8
  const BYTE *v11; // rbx
  LSTATUS v12; // eax
  __int64 v13; // r8
  const BYTE *v14; // r14
  HANDLE FileW; // rax
  void *v16; // rdi
  DWORD cbData; // [rsp+40h] [rbp-30h] BYREF
  DWORD Type; // [rsp+44h] [rbp-2Ch] BYREF
  BYTE Data[4]; // [rsp+48h] [rbp-28h] BYREF
  BYTE v21[4]; // [rsp+4Ch] [rbp-24h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-20h] BYREF
  BYTE v23[8]; // [rsp+58h] [rbp-18h] BYREF
  BYTE v24[8]; // [rsp+60h] [rbp-10h] BYREF
  int lpData; // [rsp+A0h] [rbp+30h] BYREF
  int v26; // [rsp+A8h] [rbp+38h] BYREF

  v26 = a4;
  lpData = a3;
  hKey = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v21 = 0;
  *(_QWORD *)v23 = 0;
  *(_QWORD *)v24 = 0;
  Type = 0;
  cbData = 0;
  LastError = RegOpenKeyExW(a1, a2, 0, 0x2001Fu, &hKey);
  if ( !LastError )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"Unknown", 0, &Type, Data, &cbData) && Type == 4 && cbData == 4 )
    {
      v8 = 0;
      if ( *(_DWORD *)Data == lpData )
        goto LABEL_10;
    }
    v8 = 1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, lpData, (_DWORD)a2, lpData);
    LastError = RegSetValueExW(hKey, L"Unknown", 0, 4u, (const BYTE *)&lpData, 4u);
    if ( !LastError )
    {
LABEL_10:
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"Untrusted", 0, &Type, v21, &cbData)
        && Type == 4
        && cbData == 4
        && *(_DWORD *)v21 == v26 )
      {
        goto LABEL_18;
      }
      v8 = 1;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v26, (_DWORD)a2, v26);
      LastError = RegSetValueExW(hKey, L"Untrusted", 0, 4u, (const BYTE *)&v26, 4u);
      if ( !LastError )
      {
LABEL_18:
        cbData = 8;
        v9 = RegQueryValueExW(hKey, L"NotBefore", 0, &Type, v23, &cbData);
        v11 = (const BYTE *)lpFileTime2;
        if ( !v9 && Type == 11 && cbData == 8 && !CompareFileTime((const FILETIME *)v23, lpFileTime2) )
          goto LABEL_26;
        v8 = 1;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v10, a2);
        }
        LastError = RegSetValueExW(hKey, L"NotBefore", 0, 0xBu, v11, 8u);
        if ( !LastError )
        {
LABEL_26:
          cbData = 8;
          v12 = RegQueryValueExW(hKey, L"NotAfter", 0, &Type, v24, &cbData);
          v14 = (const BYTE *)a6;
          LastError = v12;
          if ( !v12 && Type == 11 && cbData == 8 && !CompareFileTime((const FILETIME *)v24, a6) )
            goto LABEL_34;
          v8 = 1;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v13, a2);
          }
          LastError = RegSetValueExW(hKey, L"NotAfter", 0, 0xBu, v14, 8u);
          if ( !LastError )
          {
LABEL_34:
            if ( v8 )
            {
              RegCloseKey(hKey);
              hKey = 0;
              FileW = CreateFileW(L"\\\\.\\AppID", 0x40000000u, 0, 0, 3u, 0, 0);
              v16 = FileW;
              if ( FileW == (HANDLE)-1LL )
              {
                LastError = GetLastError();
              }
              else
              {
                LastError = AiUpdateDriverCertDataFromRegistry(FileW);
                CloseHandle(v16);
              }
            }
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return LastError;
}

```

## disassembly

```asm
0x140001bc4  mov     r11, rsp
0x140001bc7  mov     [r11+8], rbx
0x140001bcb  mov     [r11+10h], rsi
0x140001bcf  mov     [r11+20h], r9d
0x140001bd3  mov     [r11+18h], r8d
0x140001bd7  push    rbp
0x140001bd8  push    rdi
0x140001bd9  push    r14
0x140001bdb  mov     rbp, rsp
0x140001bde  sub     rsp, 70h
0x140001be2  lea     rax, [rbp+hKey]
0x140001be6  mov     [rbp+hKey], 0
0x140001bee  mov     r9d, 2001Fh; samDesired
0x140001bf4  mov     [r11-68h], rax
0x140001bf8  xor     r8d, r8d; ulOptions
0x140001bfb  mov     dword ptr [rbp+Data], 0
0x140001c02  mov     rsi, rdx
0x140001c05  mov     dword ptr [rbp+var_24], 0
0x140001c0c  mov     qword ptr [rbp+var_18], 0
0x140001c14  mov     qword ptr [rbp+var_10], 0
0x140001c1c  mov     [rbp+Type], 0
0x140001c23  mov     [rbp+cbData], 0
0x140001c2a  call    cs:__imp_RegOpenKeyExW
0x140001c30  mov     ebx, eax
0x140001c32  test    eax, eax
0x140001c34  jnz     loc_140001F74
0x140001c3a  mov     rcx, [rbp+hKey]; hKey
0x140001c3e  lea     r14d, [rax+4]
0x140001c42  lea     rax, [rbp+cbData]
0x140001c46  mov     [rbp+cbData], r14d
0x140001c4a  mov     [rsp+70h+lpcbData], rax; lpcbData
0x140001c4f  lea     r9, [rbp+Type]; lpType
0x140001c53  lea     rax, [rbp+Data]
0x140001c57  xor     r8d, r8d; lpReserved
0x140001c5a  lea     rdx, aUnknown; "Unknown"
0x140001c61  mov     [rsp+70h+lpData], rax; lpData
0x140001c66  call    cs:__imp_RegQueryValueExW
0x140001c6c  mov     r8d, [rbp+arg_10]
0x140001c70  lea     rbx, WPP_GLOBAL_Control
0x140001c77  test    eax, eax
0x140001c79  jnz     short loc_140001C8F
0x140001c7b  cmp     [rbp+Type], r14d
0x140001c7f  jnz     short loc_140001C8F
0x140001c81  cmp     [rbp+cbData], r14d
0x140001c85  jnz     short loc_140001C8F
0x140001c87  xor     edi, edi
0x140001c89  cmp     dword ptr [rbp+Data], r8d
0x140001c8d  jz      short loc_140001CF3
0x140001c8f  mov     edi, 1
0x140001c94  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c9b  cmp     rcx, rbx
0x140001c9e  jz      short loc_140001CBD
0x140001ca0  test    dword ptr [rcx+1Ch], 1000h
0x140001ca7  jz      short loc_140001CBD
0x140001ca9  mov     rcx, [rcx+10h]
0x140001cad  lea     edx, [rdi+11h]
0x140001cb0  mov     r9, rsi
0x140001cb3  mov     dword ptr [rsp+70h+lpData], r8d
0x140001cb8  call    WPP_SF_Sd
0x140001cbd  mov     rcx, [rbp+hKey]; hKey
0x140001cc1  lea     rax, [rbp+arg_10]
0x140001cc5  mov     dword ptr [rsp+70h+lpcbData], r14d; cbData
0x140001cca  lea     rdx, aUnknown; "Unknown"
0x140001cd1  mov     r9d, r14d; dwType
0x140001cd4  mov     [rsp+70h+lpData], rax; lpData
0x140001cd9  xor     r8d, r8d; Reserved
0x140001cdc  call    cs:__imp_RegSetValueExW
0x140001ce2  mov     ebx, eax
0x140001ce4  test    eax, eax
0x140001ce6  jnz     loc_140001F74
0x140001cec  lea     rbx, WPP_GLOBAL_Control
0x140001cf3  mov     rcx, [rbp+hKey]; hKey
0x140001cf7  lea     rax, [rbp+cbData]
0x140001cfb  mov     [rsp+70h+lpcbData], rax; lpcbData
0x140001d00  lea     r9, [rbp+Type]; lpType
0x140001d04  lea     rax, [rbp+var_24]
0x140001d08  mov     [rbp+cbData], r14d
0x140001d0c  xor     r8d, r8d; lpReserved
0x140001d0f  mov     [rsp+70h+lpData], rax; lpData
0x140001d14  lea     rdx, aUntrusted; "Untrusted"
0x140001d1b  call    cs:__imp_RegQueryValueExW
0x140001d21  mov     r8d, [rbp+arg_18]
0x140001d25  test    eax, eax
0x140001d27  jnz     short loc_140001D3B
0x140001d29  cmp     [rbp+Type], r14d
0x140001d2d  jnz     short loc_140001D3B
0x140001d2f  cmp     [rbp+cbData], r14d
0x140001d33  jnz     short loc_140001D3B
0x140001d35  cmp     dword ptr [rbp+var_24], r8d
0x140001d39  jz      short loc_140001D98
0x140001d3b  mov     edi, 1
0x140001d40  mov     rcx, cs:WPP_GLOBAL_Control
0x140001d47  cmp     rcx, rbx
0x140001d4a  jz      short loc_140001D69
0x140001d4c  test    dword ptr [rcx+1Ch], 1000h
0x140001d53  jz      short loc_140001D69
0x140001d55  mov     rcx, [rcx+10h]
0x140001d59  lea     edx, [rdi+12h]
0x140001d5c  mov     r9, rsi
0x140001d5f  mov     dword ptr [rsp+70h+lpData], r8d
0x140001d64  call    WPP_SF_Sd
0x140001d69  mov     rcx, [rbp+hKey]; hKey
0x140001d6d  lea     rax, [rbp+arg_18]
0x140001d71  mov     dword ptr [rsp+70h+lpcbData], r14d; cbData
0x140001d76  lea     rdx, aUntrusted; "Untrusted"
0x140001d7d  mov     r9d, r14d; dwType
0x140001d80  mov     [rsp+70h+lpData], rax; lpData
0x140001d85  xor     r8d, r8d; Reserved
0x140001d88  call    cs:__imp_RegSetValueExW
0x140001d8e  mov     ebx, eax
0x140001d90  test    eax, eax
0x140001d92  jnz     loc_140001F74
0x140001d98  mov     rcx, [rbp+hKey]; hKey
0x140001d9c  lea     rax, [rbp+cbData]
0x140001da0  mov     [rsp+70h+lpcbData], rax; lpcbData
0x140001da5  lea     r9, [rbp+Type]; lpType
0x140001da9  lea     rax, [rbp+var_18]
0x140001dad  mov     [rbp+cbData], 8
0x140001db4  xor     r8d, r8d; lpReserved
0x140001db7  mov     [rsp+70h+lpData], rax; lpData
0x140001dbc  lea     rdx, aNotbefore; "NotBefore"
0x140001dc3  call    cs:__imp_RegQueryValueExW
0x140001dc9  mov     rbx, [rbp+lpFileTime2]
0x140001dcd  test    eax, eax
0x140001dcf  jnz     short loc_140001DEE
0x140001dd1  cmp     [rbp+Type], 0Bh
0x140001dd5  jnz     short loc_140001DEE
0x140001dd7  cmp     [rbp+cbData], 8
0x140001ddb  jnz     short loc_140001DEE
0x140001ddd  mov     rdx, rbx; lpFileTime2
0x140001de0  lea     rcx, [rbp+var_18]; lpFileTime1
0x140001de4  call    cs:__imp_CompareFileTime
0x140001dea  test    eax, eax
0x140001dec  jz      short loc_140001E4F
0x140001dee  mov     edi, 1
0x140001df3  mov     rcx, cs:WPP_GLOBAL_Control
0x140001dfa  lea     rax, WPP_GLOBAL_Control
0x140001e01  cmp     rcx, rax
0x140001e04  jz      short loc_140001E1E
0x140001e06  test    dword ptr [rcx+1Ch], 1000h
0x140001e0d  jz      short loc_140001E1E
0x140001e0f  mov     rcx, [rcx+10h]
0x140001e13  lea     edx, [rdi+13h]
0x140001e16  mov     r9, rsi
0x140001e19  call    WPP_SF_S
0x140001e1e  mov     rcx, [rbp+hKey]; hKey
0x140001e22  lea     rdx, aNotbefore; "NotBefore"
0x140001e29  mov     dword ptr [rsp+70h+lpcbData], 8; cbData
0x140001e31  mov     r9d, 0Bh; dwType
0x140001e37  xor     r8d, r8d; Reserved
0x140001e3a  mov     [rsp+70h+lpData], rbx; lpData
0x140001e3f  call    cs:__imp_RegSetValueExW
0x140001e45  mov     ebx, eax
0x140001e47  test    eax, eax
0x140001e49  jnz     loc_140001F74
0x140001e4f  mov     rcx, [rbp+hKey]; hKey
0x140001e53  lea     rax, [rbp+cbData]
0x140001e57  mov     [rsp+70h+lpcbData], rax; lpcbData
0x140001e5c  lea     r9, [rbp+Type]; lpType
0x140001e60  lea     rax, [rbp+var_10]
0x140001e64  mov     [rbp+cbData], 8
0x140001e6b  xor     r8d, r8d; lpReserved
0x140001e6e  mov     [rsp+70h+lpData], rax; lpData
0x140001e73  lea     rdx, aNotafter; "NotAfter"
0x140001e7a  call    cs:__imp_RegQueryValueExW
0x140001e80  mov     r14, [rbp+arg_28]
0x140001e84  mov     ebx, eax
0x140001e86  test    eax, eax
0x140001e88  jnz     short loc_140001EA7
0x140001e8a  cmp     [rbp+Type], 0Bh
0x140001e8e  jnz     short loc_140001EA7
0x140001e90  cmp     [rbp+cbData], 8
0x140001e94  jnz     short loc_140001EA7
0x140001e96  mov     rdx, r14; lpFileTime2
0x140001e99  lea     rcx, [rbp+var_10]; lpFileTime1
0x140001e9d  call    cs:__imp_CompareFileTime
0x140001ea3  test    eax, eax
0x140001ea5  jz      short loc_140001F04
0x140001ea7  mov     edi, 1
0x140001eac  mov     rcx, cs:WPP_GLOBAL_Control
0x140001eb3  lea     rax, WPP_GLOBAL_Control
0x140001eba  cmp     rcx, rax
0x140001ebd  jz      short loc_140001ED7
0x140001ebf  test    dword ptr [rcx+1Ch], 1000h
0x140001ec6  jz      short loc_140001ED7
0x140001ec8  mov     rcx, [rcx+10h]
0x140001ecc  lea     edx, [rdi+14h]
0x140001ecf  mov     r9, rsi
0x140001ed2  call    WPP_SF_S
0x140001ed7  mov     rcx, [rbp+hKey]; hKey
0x140001edb  lea     rdx, aNotafter; "NotAfter"
0x140001ee2  mov     dword ptr [rsp+70h+lpcbData], 8; cbData
0x140001eea  mov     r9d, 0Bh; dwType
0x140001ef0  xor     r8d, r8d; Reserved
0x140001ef3  mov     [rsp+70h+lpData], r14; lpData
0x140001ef8  call    cs:__imp_RegSetValueExW
0x140001efe  mov     ebx, eax
0x140001f00  test    eax, eax
0x140001f02  jnz     short loc_140001F74
0x140001f04  test    edi, edi
0x140001f06  jz      short loc_140001F74
0x140001f08  mov     rcx, [rbp+hKey]; hKey
0x140001f0c  call    cs:__imp_RegCloseKey
0x140001f12  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x140001f1b  lea     rcx, FileName; "\\\\.\\AppID"
0x140001f22  mov     dword ptr [rsp+70h+lpcbData], 0; dwFlagsAndAttributes
0x140001f2a  xor     r9d, r9d; lpSecurityAttributes
0x140001f2d  xor     r8d, r8d; dwShareMode
0x140001f30  mov     dword ptr [rsp+70h+lpData], 3; dwCreationDisposition
0x140001f38  mov     edx, 40000000h; dwDesiredAccess
0x140001f3d  mov     [rbp+hKey], 0
0x140001f45  call    cs:__imp_CreateFileW
0x140001f4b  mov     rdi, rax
0x140001f4e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140001f52  jnz     short loc_140001F5E
0x140001f54  call    cs:__imp_GetLastError
0x140001f5a  mov     ebx, eax
0x140001f5c  jmp     short loc_140001F74
0x140001f5e  mov     rdx, rsi
0x140001f61  mov     rcx, rdi; hDevice
0x140001f64  call    AiUpdateDriverCertDataFromRegistry
0x140001f69  mov     ebx, eax
0x140001f6b  mov     rcx, rdi; hObject
0x140001f6e  call    cs:__imp_CloseHandle
0x140001f74  mov     rcx, [rbp+hKey]; hKey
0x140001f78  test    rcx, rcx
0x140001f7b  jz      short loc_140001F83
0x140001f7d  call    cs:__imp_RegCloseKey
0x140001f83  lea     r11, [rsp+70h+var_s0]
0x140001f88  mov     eax, ebx
0x140001f8a  mov     rbx, [r11+20h]
0x140001f8e  mov     rsi, [r11+28h]
0x140001f92  mov     rsp, r11
0x140001f95  pop     r14
0x140001f97  pop     rdi
0x140001f98  pop     rbp
0x140001f99  retn
```
