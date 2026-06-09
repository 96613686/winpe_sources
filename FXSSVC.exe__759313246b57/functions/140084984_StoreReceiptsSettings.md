# StoreReceiptsSettings

- ea: `0x140084984`
- end: `0x140084dfe`
- name: `StoreReceiptsSettings`
- size: `1146`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140021750`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140074004`
- `0x140074f18`
- `0x140075070`
- `0x140084004`
- `0x140084984`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140084dc7`
- `ADVAPI32!RegCloseKey` at `0x140084dd6`
- `ADVAPI32!RegCloseKey` at `0x140084dc7`
- `ADVAPI32!RegCloseKey` at `0x140084dd6`
- `ADVAPI32!RegCreateKeyExW` at `0x140084a8c`
- `ADVAPI32!RegCreateKeyExW` at `0x140084a8c`
- `KERNEL32!GetLastError` at `0x140084a04`
- `KERNEL32!GetLastError` at `0x140084ae8`
- `KERNEL32!GetLastError` at `0x140084b40`
- `KERNEL32!GetLastError` at `0x140084ba8`
- `KERNEL32!GetLastError` at `0x140084c00`
- `KERNEL32!GetLastError` at `0x140084c6d`
- `KERNEL32!GetLastError` at `0x140084cd3`
- `KERNEL32!GetLastError` at `0x140084d39`
- `KERNEL32!GetLastError` at `0x140084d80`
- `KERNEL32!GetLastError` at `0x140084a04`
- `KERNEL32!GetLastError` at `0x140084ae8`
- `KERNEL32!GetLastError` at `0x140084b40`
- `KERNEL32!GetLastError` at `0x140084ba8`
- `KERNEL32!GetLastError` at `0x140084c00`
- `KERNEL32!GetLastError` at `0x140084c6d`
- `KERNEL32!GetLastError` at `0x140084cd3`
- `KERNEL32!GetLastError` at `0x140084d39`
- `KERNEL32!GetLastError` at `0x140084d80`

## pseudocode

```c
__int64 __fastcall StoreReceiptsSettings(__int64 a1)
{
  HKEY v2; // rbp
  DWORD LastError; // eax
  DWORD v4; // ebx
  DWORD v5; // eax
  CMapDeviceId *v6; // rcx
  __int64 v7; // rdx
  const BYTE *v8; // rsi
  const BYTE *v9; // r9
  const BYTE *v10; // r9
  HKEY hKey; // [rsp+88h] [rbp+10h] BYREF

  hKey = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, LastError);
    }
    return v4;
  }
  v5 = RegCreateKeyExW(v2, L"Receipts", 0, 0, 0, 0x2000000u, 0, &hKey, 0);
  v4 = v5;
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    v7 = 42;
  }
  else if ( (unsigned int)SetRegistryDword(hKey, L"UseForMsRoute", *(_DWORD *)(a1 + 64)) )
  {
    if ( (unsigned int)SetRegistryDword(hKey, L"Type", *(_DWORD *)(a1 + 4)) )
    {
      if ( (*(_BYTE *)(a1 + 4) & 1) == 0 && !*(_DWORD *)(a1 + 64) )
        goto LABEL_65;
      if ( (unsigned int)SetRegistryDword(hKey, L"Port", *(_DWORD *)(a1 + 32)) )
      {
        if ( (unsigned int)SetRegistryDword(hKey, L"SMTPAuth", *(_DWORD *)(a1 + 8)) )
        {
          v8 = (const BYTE *)&Class;
          v9 = (const BYTE *)&Class;
          if ( *(_QWORD *)(a1 + 24) )
            v9 = *(const BYTE **)(a1 + 24);
          if ( (unsigned int)SetRegistryStringValue(hKey, 1u, L"Server", v9) )
          {
            v10 = (const BYTE *)&Class;
            if ( *(_QWORD *)(a1 + 40) )
              v10 = *(const BYTE **)(a1 + 40);
            if ( (unsigned int)SetRegistryStringValue(hKey, 1u, L"From", v10) )
            {
              if ( *(_QWORD *)(a1 + 48) )
                v8 = *(const BYTE **)(a1 + 48);
              if ( (unsigned int)SetRegistryStringValue(hKey, 1u, L"User", v8) )
              {
                if ( !*(_QWORD *)(a1 + 56) )
                  goto LABEL_65;
                if ( (unsigned int)SetRegistrySecureString(hKey) )
                  goto LABEL_65;
                v5 = GetLastError();
                v4 = v5;
                v6 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_65;
                }
                v7 = 50;
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
                  goto LABEL_65;
                }
                v7 = 49;
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
                goto LABEL_65;
              }
              v7 = 48;
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
              goto LABEL_65;
            }
            v7 = 47;
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
            goto LABEL_65;
          }
          v7 = 46;
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
          goto LABEL_65;
        }
        v7 = 45;
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
        goto LABEL_65;
      }
      v7 = 44;
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
      goto LABEL_65;
    }
    v7 = 43;
  }
  WPP_SF_d(*((_QWORD *)v6 + 2), v7, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v5);
LABEL_65:
  if ( hKey )
    RegCloseKey(hKey);
  RegCloseKey(v2);
  return v4;
}

```

## disassembly

```asm
0x140084984  mov     rax, rsp
0x140084987  mov     [rax+8], rbx
0x14008498b  mov     [rax+18h], rbp
0x14008498f  push    rsi
0x140084990  push    rdi
0x140084991  push    r12
0x140084993  push    r13
0x140084995  push    r14
0x140084997  sub     rsp, 50h
0x14008499b  mov     rdi, rcx
0x14008499e  mov     qword ptr [rax+10h], 0
0x1400849a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400849ad  lea     r12, WPP_GLOBAL_Control
0x1400849b4  lea     r13, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x1400849bb  mov     r14b, 2
0x1400849be  cmp     rcx, r12
0x1400849c1  jz      short loc_1400849E0
0x1400849c3  test    [rcx+1Ch], r14b
0x1400849c7  jz      short loc_1400849E0
0x1400849c9  cmp     byte ptr [rcx+19h], 5
0x1400849cd  jb      short loc_1400849E0
0x1400849cf  mov     rcx, [rcx+10h]
0x1400849d3  mov     edx, 28h ; '('
0x1400849d8  mov     r8, r13
0x1400849db  call    WPP_SF_
0x1400849e0  mov     r9d, 20006h
0x1400849e6  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Fax"
0x1400849ed  xor     r8d, r8d
0x1400849f0  mov     rcx, 0FFFFFFFF80000002h
0x1400849f7  call    OpenRegistryKey
0x1400849fc  mov     rbp, rax
0x1400849ff  test    rax, rax
0x140084a02  jnz     short loc_140084A4D
0x140084a04  call    cs:__imp_GetLastError
0x140084a0b  nop     dword ptr [rax+rax+00h]
0x140084a10  mov     ebx, eax
0x140084a12  mov     rcx, cs:WPP_GLOBAL_Control
0x140084a19  cmp     rcx, r12
0x140084a1c  jz      loc_140084DE2
0x140084a22  test    [rcx+1Ch], r14b
0x140084a26  jz      loc_140084DE2
0x140084a2c  cmp     [rcx+19h], r14b
0x140084a30  jb      loc_140084DE2
0x140084a36  mov     rcx, [rcx+10h]
0x140084a3a  lea     edx, [rbp+29h]
0x140084a3d  mov     r9d, eax
0x140084a40  mov     r8, r13
0x140084a43  call    WPP_SF_d
0x140084a48  jmp     loc_140084DE2
0x140084a4d  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x140084a56  lea     rax, [rsp+78h+hKey]
0x140084a5e  mov     [rsp+78h+phkResult], rax; phkResult
0x140084a63  lea     rdx, aReceipts; "Receipts"
0x140084a6a  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140084a73  xor     r9d, r9d; lpClass
0x140084a76  mov     [rsp+78h+samDesired], 2000000h; samDesired
0x140084a7e  xor     r8d, r8d; Reserved
0x140084a81  mov     rcx, rbp; hKey
0x140084a84  mov     [rsp+78h+dwOptions], 0; int
0x140084a8c  call    cs:__imp_RegCreateKeyExW
0x140084a93  nop     dword ptr [rax+rax+00h]
0x140084a98  mov     ebx, eax
0x140084a9a  test    eax, eax
0x140084a9c  jz      short loc_140084ACC
0x140084a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140084aa5  cmp     rcx, r12
0x140084aa8  jz      loc_140084DBA
0x140084aae  test    [rcx+1Ch], r14b
0x140084ab2  jz      loc_140084DBA
0x140084ab8  cmp     [rcx+19h], r14b
0x140084abc  jb      loc_140084DBA
0x140084ac2  mov     edx, 2Ah ; '*'
0x140084ac7  jmp     loc_140084DAB
0x140084acc  mov     r8d, [rdi+40h]
0x140084ad0  lea     rdx, aUseformsroute; "UseForMsRoute"
0x140084ad7  mov     rcx, [rsp+78h+hKey]
0x140084adf  call    SetRegistryDword
0x140084ae4  test    eax, eax
0x140084ae6  jnz     short loc_140084B24
0x140084ae8  call    cs:__imp_GetLastError
0x140084aef  nop     dword ptr [rax+rax+00h]
0x140084af4  mov     ebx, eax
0x140084af6  mov     rcx, cs:WPP_GLOBAL_Control
0x140084afd  cmp     rcx, r12
0x140084b00  jz      loc_140084DBA
0x140084b06  test    [rcx+1Ch], r14b
0x140084b0a  jz      loc_140084DBA
0x140084b10  cmp     [rcx+19h], r14b
0x140084b14  jb      loc_140084DBA
0x140084b1a  mov     edx, 2Bh ; '+'
0x140084b1f  jmp     loc_140084DAB
0x140084b24  mov     r8d, [rdi+4]
0x140084b28  lea     rdx, aType; "Type"
0x140084b2f  mov     rcx, [rsp+78h+hKey]
0x140084b37  call    SetRegistryDword
0x140084b3c  test    eax, eax
0x140084b3e  jnz     short loc_140084B7C
0x140084b40  call    cs:__imp_GetLastError
0x140084b47  nop     dword ptr [rax+rax+00h]
0x140084b4c  mov     ebx, eax
0x140084b4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140084b55  cmp     rcx, r12
0x140084b58  jz      loc_140084DBA
0x140084b5e  test    [rcx+1Ch], r14b
0x140084b62  jz      loc_140084DBA
0x140084b68  cmp     [rcx+19h], r14b
0x140084b6c  jb      loc_140084DBA
0x140084b72  mov     edx, 2Ch ; ','
0x140084b77  jmp     loc_140084DAB
0x140084b7c  test    byte ptr [rdi+4], 1
0x140084b80  jnz     short loc_140084B8C
0x140084b82  cmp     dword ptr [rdi+40h], 0
0x140084b86  jz      loc_140084DBA
0x140084b8c  mov     r8d, [rdi+20h]
0x140084b90  lea     rdx, aPort; "Port"
0x140084b97  mov     rcx, [rsp+78h+hKey]
0x140084b9f  call    SetRegistryDword
0x140084ba4  test    eax, eax
0x140084ba6  jnz     short loc_140084BE4
0x140084ba8  call    cs:__imp_GetLastError
0x140084baf  nop     dword ptr [rax+rax+00h]
0x140084bb4  mov     ebx, eax
0x140084bb6  mov     rcx, cs:WPP_GLOBAL_Control
0x140084bbd  cmp     rcx, r12
0x140084bc0  jz      loc_140084DBA
0x140084bc6  test    [rcx+1Ch], r14b
0x140084bca  jz      loc_140084DBA
0x140084bd0  cmp     [rcx+19h], r14b
0x140084bd4  jb      loc_140084DBA
0x140084bda  mov     edx, 2Dh ; '-'
0x140084bdf  jmp     loc_140084DAB
0x140084be4  mov     r8d, [rdi+8]
0x140084be8  lea     rdx, aSmtpauth; "SMTPAuth"
0x140084bef  mov     rcx, [rsp+78h+hKey]
0x140084bf7  call    SetRegistryDword
0x140084bfc  test    eax, eax
0x140084bfe  jnz     short loc_140084C3C
0x140084c00  call    cs:__imp_GetLastError
0x140084c07  nop     dword ptr [rax+rax+00h]
0x140084c0c  mov     ebx, eax
0x140084c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140084c15  cmp     rcx, r12
0x140084c18  jz      loc_140084DBA
0x140084c1e  test    [rcx+1Ch], r14b
0x140084c22  jz      loc_140084DBA
0x140084c28  cmp     [rcx+19h], r14b
0x140084c2c  jb      loc_140084DBA
0x140084c32  mov     edx, 2Eh ; '.'
0x140084c37  jmp     loc_140084DAB
0x140084c3c  cmp     qword ptr [rdi+18h], 0
0x140084c41  lea     rsi, Class
0x140084c48  mov     rcx, [rsp+78h+hKey]; HKEY
0x140084c50  lea     r8, aServer; "Server"
0x140084c57  mov     r9, rsi
0x140084c5a  mov     edx, 1; unsigned int
0x140084c5f  cmovnz  r9, [rdi+18h]; unsigned __int16 *
0x140084c64  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x140084c69  test    eax, eax
0x140084c6b  jnz     short loc_140084CA9
0x140084c6d  call    cs:__imp_GetLastError
0x140084c74  nop     dword ptr [rax+rax+00h]
0x140084c79  mov     ebx, eax
0x140084c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140084c82  cmp     rcx, r12
0x140084c85  jz      loc_140084DBA
0x140084c8b  test    [rcx+1Ch], r14b
0x140084c8f  jz      loc_140084DBA
0x140084c95  cmp     [rcx+19h], r14b
0x140084c99  jb      loc_140084DBA
0x140084c9f  mov     edx, 2Fh ; '/'
0x140084ca4  jmp     loc_140084DAB
0x140084ca9  cmp     qword ptr [rdi+28h], 0
0x140084cae  lea     r8, aFrom; "From"
0x140084cb5  mov     rcx, [rsp+78h+hKey]; HKEY
0x140084cbd  mov     r9, rsi
0x140084cc0  cmovnz  r9, [rdi+28h]; unsigned __int16 *
0x140084cc5  mov     edx, 1; unsigned int
0x140084cca  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x140084ccf  test    eax, eax
0x140084cd1  jnz     short loc_140084D0F
0x140084cd3  call    cs:__imp_GetLastError
0x140084cda  nop     dword ptr [rax+rax+00h]
0x140084cdf  mov     ebx, eax
0x140084ce1  mov     rcx, cs:WPP_GLOBAL_Control
0x140084ce8  cmp     rcx, r12
0x140084ceb  jz      loc_140084DBA
0x140084cf1  test    [rcx+1Ch], r14b
0x140084cf5  jz      loc_140084DBA
0x140084cfb  cmp     [rcx+19h], r14b
0x140084cff  jb      loc_140084DBA
0x140084d05  mov     edx, 30h ; '0'
0x140084d0a  jmp     loc_140084DAB
0x140084d0f  cmp     qword ptr [rdi+30h], 0
0x140084d14  lea     r8, aUser; "User"
0x140084d1b  mov     rcx, [rsp+78h+hKey]; HKEY
0x140084d23  mov     edx, 1; unsigned int
0x140084d28  cmovnz  rsi, [rdi+30h]
0x140084d2d  mov     r9, rsi; unsigned __int16 *
0x140084d30  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x140084d35  test    eax, eax
0x140084d37  jnz     short loc_140084D66
0x140084d39  call    cs:__imp_GetLastError
0x140084d40  nop     dword ptr [rax+rax+00h]
0x140084d45  mov     ebx, eax
0x140084d47  mov     rcx, cs:WPP_GLOBAL_Control
0x140084d4e  cmp     rcx, r12
0x140084d51  jz      short loc_140084DBA
0x140084d53  test    [rcx+1Ch], r14b
0x140084d57  jz      short loc_140084DBA
0x140084d59  cmp     [rcx+19h], r14b
0x140084d5d  jb      short loc_140084DBA
0x140084d5f  mov     edx, 31h ; '1'
0x140084d64  jmp     short loc_140084DAB
0x140084d66  mov     r8, [rdi+38h]
0x140084d6a  test    r8, r8
0x140084d6d  jz      short loc_140084DBA
0x140084d6f  mov     rcx, [rsp+78h+hKey]
0x140084d77  call    SetRegistrySecureString
0x140084d7c  test    eax, eax
0x140084d7e  jnz     short loc_140084DBA
0x140084d80  call    cs:__imp_GetLastError
0x140084d87  nop     dword ptr [rax+rax+00h]
0x140084d8c  mov     ebx, eax
0x140084d8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140084d95  cmp     rcx, r12
0x140084d98  jz      short loc_140084DBA
0x140084d9a  test    [rcx+1Ch], r14b
0x140084d9e  jz      short loc_140084DBA
0x140084da0  cmp     [rcx+19h], r14b
0x140084da4  jb      short loc_140084DBA
0x140084da6  mov     edx, 32h ; '2'
0x140084dab  mov     rcx, [rcx+10h]
0x140084daf  mov     r9d, eax
0x140084db2  mov     r8, r13
0x140084db5  call    WPP_SF_d
0x140084dba  mov     rcx, [rsp+78h+hKey]; hKey
0x140084dc2  test    rcx, rcx
0x140084dc5  jz      short loc_140084DD3
0x140084dc7  call    cs:__imp_RegCloseKey
0x140084dce  nop     dword ptr [rax+rax+00h]
0x140084dd3  mov     rcx, rbp; hKey
0x140084dd6  call    cs:__imp_RegCloseKey
0x140084ddd  nop     dword ptr [rax+rax+00h]
0x140084de2  lea     r11, [rsp+78h+var_28]
0x140084de7  mov     eax, ebx
0x140084de9  mov     rbx, [r11+30h]
0x140084ded  mov     rbp, [r11+40h]
0x140084df1  mov     rsp, r11
0x140084df4  pop     r14
0x140084df6  pop     r13
0x140084df8  pop     r12
0x140084dfa  pop     rdi
0x140084dfb  pop     rsi
0x140084dfc  retn
```
