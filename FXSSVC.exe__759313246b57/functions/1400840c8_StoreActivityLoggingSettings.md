# StoreActivityLoggingSettings

- ea: `0x1400840c8`
- end: `0x140084349`
- name: `StoreActivityLoggingSettings`
- size: `641`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001ee40`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140074004`
- `0x140074f18`
- `0x140075070`
- `0x1400840c8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14008431d`
- `ADVAPI32!RegCloseKey` at `0x14008432c`
- `ADVAPI32!RegCloseKey` at `0x14008431d`
- `ADVAPI32!RegCloseKey` at `0x14008432c`
- `ADVAPI32!RegCreateKeyExW` at `0x1400841b9`
- `ADVAPI32!RegCreateKeyExW` at `0x1400841b9`
- `KERNEL32!GetLastError` at `0x14008413c`
- `KERNEL32!GetLastError` at `0x140084215`
- `KERNEL32!GetLastError` at `0x14008426d`
- `KERNEL32!GetLastError` at `0x1400842d6`
- `KERNEL32!GetLastError` at `0x14008413c`
- `KERNEL32!GetLastError` at `0x140084215`
- `KERNEL32!GetLastError` at `0x14008426d`
- `KERNEL32!GetLastError` at `0x1400842d6`

## string_xrefs

- `0x1400841fd`: `LogIncoming`

## pseudocode

```c
__int64 __fastcall StoreActivityLoggingSettings(__int64 a1)
{
  HKEY v2; // rsi
  DWORD LastError; // eax
  DWORD v4; // ebx
  DWORD v5; // eax
  CMapDeviceId *v6; // rcx
  __int64 v7; // rdx
  const BYTE *v8; // r9
  HKEY hKey; // [rsp+98h] [rbp+10h] BYREF

  hKey = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  v2 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax", 0, 0x20006u);
  if ( !v2 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, LastError);
    }
    return v4;
  }
  v5 = RegCreateKeyExW(v2, L"ActivityLogging", 0, 0, 0, 0x2000000u, 0, &hKey, 0);
  v4 = v5;
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_35;
    }
    v7 = 67;
  }
  else if ( (unsigned int)SetRegistryDword(hKey, L"LogIncoming", *(_DWORD *)(a1 + 4)) )
  {
    if ( (unsigned int)SetRegistryDword(hKey, L"LogOutgoing", *(_DWORD *)(a1 + 8)) )
    {
      if ( !*(_DWORD *)(a1 + 4) && !*(_DWORD *)(a1 + 8) )
        goto LABEL_35;
      v8 = *(const BYTE **)(a1 + 16);
      if ( !v8 )
        goto LABEL_35;
      if ( !*(_WORD *)v8 )
        goto LABEL_35;
      if ( (unsigned int)SetRegistryStringValue(hKey, 1u, L"DBFile", v8) )
        goto LABEL_35;
      v5 = GetLastError();
      v4 = v5;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_35;
      }
      v7 = 70;
    }
    else
    {
      v5 = GetLastError();
      v4 = v5;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_35;
      }
      v7 = 69;
    }
  }
  else
  {
    v5 = GetLastError();
    v4 = v5;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_35;
    }
    v7 = 68;
  }
  WPP_SF_d(*((_QWORD *)v6 + 2), v7, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v5);
LABEL_35:
  if ( hKey )
    RegCloseKey(hKey);
  RegCloseKey(v2);
  return v4;
}

```

## disassembly

```asm
0x1400840c8  mov     rax, rsp
0x1400840cb  push    rbx
0x1400840cc  push    rsi
0x1400840cd  push    rdi
0x1400840ce  push    r12
0x1400840d0  push    r14
0x1400840d2  push    r15
0x1400840d4  sub     rsp, 58h
0x1400840d8  xor     r14d, r14d
0x1400840db  mov     rdi, rcx
0x1400840de  mov     [rax+10h], r14
0x1400840e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400840e9  lea     r15, WPP_GLOBAL_Control
0x1400840f0  lea     r12, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x1400840f7  cmp     rcx, r15
0x1400840fa  jz      short loc_140084118
0x1400840fc  test    byte ptr [rcx+1Ch], 2
0x140084100  jz      short loc_140084118
0x140084102  cmp     byte ptr [rcx+19h], 5
0x140084106  jb      short loc_140084118
0x140084108  mov     rcx, [rcx+10h]
0x14008410c  lea     edx, [r14+41h]
0x140084110  mov     r8, r12
0x140084113  call    WPP_SF_
0x140084118  mov     r9d, 20006h
0x14008411e  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Fax"
0x140084125  xor     r8d, r8d
0x140084128  mov     rcx, 0FFFFFFFF80000002h
0x14008412f  call    OpenRegistryKey
0x140084134  mov     rsi, rax
0x140084137  test    rax, rax
0x14008413a  jnz     short loc_140084185
0x14008413c  call    cs:__imp_GetLastError
0x140084143  nop     dword ptr [rax+rax+00h]
0x140084148  mov     ebx, eax
0x14008414a  mov     rcx, cs:WPP_GLOBAL_Control
0x140084151  cmp     rcx, r15
0x140084154  jz      loc_140084338
0x14008415a  test    byte ptr [rcx+1Ch], 2
0x14008415e  jz      loc_140084338
0x140084164  cmp     byte ptr [rcx+19h], 2
0x140084168  jb      loc_140084338
0x14008416e  mov     rcx, [rcx+10h]
0x140084172  lea     edx, [rsi+42h]
0x140084175  mov     r9d, eax
0x140084178  mov     r8, r12
0x14008417b  call    WPP_SF_d
0x140084180  jmp     loc_140084338
0x140084185  mov     [rsp+88h+lpdwDisposition], r14; lpdwDisposition
0x14008418a  lea     rax, [rsp+88h+hKey]
0x140084192  mov     [rsp+88h+phkResult], rax; phkResult
0x140084197  lea     rdx, aActivityloggin; "ActivityLogging"
0x14008419e  mov     [rsp+88h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1400841a3  xor     r9d, r9d; lpClass
0x1400841a6  mov     [rsp+88h+samDesired], 2000000h; samDesired
0x1400841ae  xor     r8d, r8d; Reserved
0x1400841b1  mov     rcx, rsi; hKey
0x1400841b4  mov     [rsp+88h+dwOptions], r14d; int
0x1400841b9  call    cs:__imp_RegCreateKeyExW
0x1400841c0  nop     dword ptr [rax+rax+00h]
0x1400841c5  mov     ebx, eax
0x1400841c7  test    eax, eax
0x1400841c9  jz      short loc_1400841F9
0x1400841cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400841d2  cmp     rcx, r15
0x1400841d5  jz      loc_140084310
0x1400841db  test    byte ptr [rcx+1Ch], 2
0x1400841df  jz      loc_140084310
0x1400841e5  cmp     byte ptr [rcx+19h], 2
0x1400841e9  jb      loc_140084310
0x1400841ef  mov     edx, 43h ; 'C'
0x1400841f4  jmp     loc_140084301
0x1400841f9  mov     r8d, [rdi+4]
0x1400841fd  lea     rdx, aLogincoming; "LogIncoming"
0x140084204  mov     rcx, [rsp+88h+hKey]
0x14008420c  call    SetRegistryDword
0x140084211  test    eax, eax
0x140084213  jnz     short loc_140084251
0x140084215  call    cs:__imp_GetLastError
0x14008421c  nop     dword ptr [rax+rax+00h]
0x140084221  mov     ebx, eax
0x140084223  mov     rcx, cs:WPP_GLOBAL_Control
0x14008422a  cmp     rcx, r15
0x14008422d  jz      loc_140084310
0x140084233  test    byte ptr [rcx+1Ch], 2
0x140084237  jz      loc_140084310
0x14008423d  cmp     byte ptr [rcx+19h], 2
0x140084241  jb      loc_140084310
0x140084247  mov     edx, 44h ; 'D'
0x14008424c  jmp     loc_140084301
0x140084251  mov     r8d, [rdi+8]
0x140084255  lea     rdx, aLogoutgoing; "LogOutgoing"
0x14008425c  mov     rcx, [rsp+88h+hKey]
0x140084264  call    SetRegistryDword
0x140084269  test    eax, eax
0x14008426b  jnz     short loc_14008429E
0x14008426d  call    cs:__imp_GetLastError
0x140084274  nop     dword ptr [rax+rax+00h]
0x140084279  mov     ebx, eax
0x14008427b  mov     rcx, cs:WPP_GLOBAL_Control
0x140084282  cmp     rcx, r15
0x140084285  jz      loc_140084310
0x14008428b  test    byte ptr [rcx+1Ch], 2
0x14008428f  jz      short loc_140084310
0x140084291  cmp     byte ptr [rcx+19h], 2
0x140084295  jb      short loc_140084310
0x140084297  mov     edx, 45h ; 'E'
0x14008429c  jmp     short loc_140084301
0x14008429e  cmp     [rdi+4], r14d
0x1400842a2  jnz     short loc_1400842AA
0x1400842a4  cmp     [rdi+8], r14d
0x1400842a8  jz      short loc_140084310
0x1400842aa  mov     r9, [rdi+10h]; unsigned __int16 *
0x1400842ae  test    r9, r9
0x1400842b1  jz      short loc_140084310
0x1400842b3  cmp     [r9], r14w
0x1400842b7  jz      short loc_140084310
0x1400842b9  mov     rcx, [rsp+88h+hKey]; HKEY
0x1400842c1  lea     r8, aDbfile; "DBFile"
0x1400842c8  mov     edx, 1; unsigned int
0x1400842cd  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x1400842d2  test    eax, eax
0x1400842d4  jnz     short loc_140084310
0x1400842d6  call    cs:__imp_GetLastError
0x1400842dd  nop     dword ptr [rax+rax+00h]
0x1400842e2  mov     ebx, eax
0x1400842e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400842eb  cmp     rcx, r15
0x1400842ee  jz      short loc_140084310
0x1400842f0  test    byte ptr [rcx+1Ch], 2
0x1400842f4  jz      short loc_140084310
0x1400842f6  cmp     byte ptr [rcx+19h], 2
0x1400842fa  jb      short loc_140084310
0x1400842fc  mov     edx, 46h ; 'F'
0x140084301  mov     rcx, [rcx+10h]
0x140084305  mov     r9d, eax
0x140084308  mov     r8, r12
0x14008430b  call    WPP_SF_d
0x140084310  mov     rcx, [rsp+88h+hKey]; hKey
0x140084318  test    rcx, rcx
0x14008431b  jz      short loc_140084329
0x14008431d  call    cs:__imp_RegCloseKey
0x140084324  nop     dword ptr [rax+rax+00h]
0x140084329  mov     rcx, rsi; hKey
0x14008432c  call    cs:__imp_RegCloseKey
0x140084333  nop     dword ptr [rax+rax+00h]
0x140084338  mov     eax, ebx
0x14008433a  add     rsp, 58h
0x14008433e  pop     r15
0x140084340  pop     r14
0x140084342  pop     r12
0x140084344  pop     rdi
0x140084345  pop     rsi
0x140084346  pop     rbx
0x140084347  retn
```
