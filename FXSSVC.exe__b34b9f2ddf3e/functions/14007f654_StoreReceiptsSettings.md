# StoreReceiptsSettings

- ea: `0x14007f654`
- end: `0x14007fa85`
- name: `StoreReceiptsSettings`
- size: `1073`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140020890`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x14006fa88`
- `0x1400708c4`
- `0x1400709fc`
- `0x14007ed5c`
- `0x14007f654`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14007fa5b`
- `ADVAPI32!RegCloseKey` at `0x14007fa64`
- `ADVAPI32!RegCloseKey` at `0x14007fa5b`
- `ADVAPI32!RegCloseKey` at `0x14007fa64`
- `ADVAPI32!RegCreateKeyExW` at `0x14007f756`
- `ADVAPI32!RegCreateKeyExW` at `0x14007f756`
- `KERNEL32!GetLastError` at `0x14007f6d4`
- `KERNEL32!GetLastError` at `0x14007f7ac`
- `KERNEL32!GetLastError` at `0x14007f7fe`
- `KERNEL32!GetLastError` at `0x14007f860`
- `KERNEL32!GetLastError` at `0x14007f8b2`
- `KERNEL32!GetLastError` at `0x14007f919`
- `KERNEL32!GetLastError` at `0x14007f979`
- `KERNEL32!GetLastError` at `0x14007f9d9`
- `KERNEL32!GetLastError` at `0x14007fa1a`
- `KERNEL32!GetLastError` at `0x14007f6d4`
- `KERNEL32!GetLastError` at `0x14007f7ac`
- `KERNEL32!GetLastError` at `0x14007f7fe`
- `KERNEL32!GetLastError` at `0x14007f860`
- `KERNEL32!GetLastError` at `0x14007f8b2`
- `KERNEL32!GetLastError` at `0x14007f919`
- `KERNEL32!GetLastError` at `0x14007f979`
- `KERNEL32!GetLastError` at `0x14007f9d9`
- `KERNEL32!GetLastError` at `0x14007fa1a`

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
  __int64 v11; // rdx
  __int64 v12; // r8
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
                v12 = *(_QWORD *)(a1 + 56);
                if ( !v12 )
                  goto LABEL_65;
                if ( (unsigned int)SetRegistrySecureString(hKey, v11, v12) )
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
0x14007f654  mov     rax, rsp
0x14007f657  mov     [rax+8], rbx
0x14007f65b  mov     [rax+18h], rbp
0x14007f65f  push    rsi
0x14007f660  push    rdi
0x14007f661  push    r12
0x14007f663  push    r13
0x14007f665  push    r14
0x14007f667  sub     rsp, 50h
0x14007f66b  mov     rdi, rcx
0x14007f66e  mov     qword ptr [rax+10h], 0
0x14007f676  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f67d  lea     r12, WPP_GLOBAL_Control
0x14007f684  lea     r13, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007f68b  mov     r14b, 2
0x14007f68e  cmp     rcx, r12
0x14007f691  jz      short loc_14007F6B0
0x14007f693  test    [rcx+1Ch], r14b
0x14007f697  jz      short loc_14007F6B0
0x14007f699  cmp     byte ptr [rcx+19h], 5
0x14007f69d  jb      short loc_14007F6B0
0x14007f69f  mov     rcx, [rcx+10h]
0x14007f6a3  mov     edx, 28h ; '('
0x14007f6a8  mov     r8, r13
0x14007f6ab  call    WPP_SF_
0x14007f6b0  mov     r9d, 20006h
0x14007f6b6  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Fax"
0x14007f6bd  xor     r8d, r8d
0x14007f6c0  mov     rcx, 0FFFFFFFF80000002h
0x14007f6c7  call    OpenRegistryKey
0x14007f6cc  mov     rbp, rax
0x14007f6cf  test    rax, rax
0x14007f6d2  jnz     short loc_14007F717
0x14007f6d4  call    cs:__imp_GetLastError
0x14007f6da  mov     ebx, eax
0x14007f6dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f6e3  cmp     rcx, r12
0x14007f6e6  jz      loc_14007FA6A
0x14007f6ec  test    [rcx+1Ch], r14b
0x14007f6f0  jz      loc_14007FA6A
0x14007f6f6  cmp     [rcx+19h], r14b
0x14007f6fa  jb      loc_14007FA6A
0x14007f700  mov     rcx, [rcx+10h]
0x14007f704  lea     edx, [rbp+29h]
0x14007f707  mov     r9d, eax
0x14007f70a  mov     r8, r13
0x14007f70d  call    WPP_SF_d
0x14007f712  jmp     loc_14007FA6A
0x14007f717  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x14007f720  lea     rax, [rsp+78h+hKey]
0x14007f728  mov     [rsp+78h+phkResult], rax; phkResult
0x14007f72d  lea     rdx, aReceipts; "Receipts"
0x14007f734  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14007f73d  xor     r9d, r9d; lpClass
0x14007f740  mov     [rsp+78h+samDesired], 2000000h; samDesired
0x14007f748  xor     r8d, r8d; Reserved
0x14007f74b  mov     rcx, rbp; hKey
0x14007f74e  mov     [rsp+78h+dwOptions], 0; int
0x14007f756  call    cs:__imp_RegCreateKeyExW
0x14007f75c  mov     ebx, eax
0x14007f75e  test    eax, eax
0x14007f760  jz      short loc_14007F790
0x14007f762  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f769  cmp     rcx, r12
0x14007f76c  jz      loc_14007FA4E
0x14007f772  test    [rcx+1Ch], r14b
0x14007f776  jz      loc_14007FA4E
0x14007f77c  cmp     [rcx+19h], r14b
0x14007f780  jb      loc_14007FA4E
0x14007f786  mov     edx, 2Ah ; '*'
0x14007f78b  jmp     loc_14007FA3F
0x14007f790  mov     r8d, [rdi+40h]
0x14007f794  lea     rdx, aUseformsroute; "UseForMsRoute"
0x14007f79b  mov     rcx, [rsp+78h+hKey]
0x14007f7a3  call    SetRegistryDword
0x14007f7a8  test    eax, eax
0x14007f7aa  jnz     short loc_14007F7E2
0x14007f7ac  call    cs:__imp_GetLastError
0x14007f7b2  mov     ebx, eax
0x14007f7b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f7bb  cmp     rcx, r12
0x14007f7be  jz      loc_14007FA4E
0x14007f7c4  test    [rcx+1Ch], r14b
0x14007f7c8  jz      loc_14007FA4E
0x14007f7ce  cmp     [rcx+19h], r14b
0x14007f7d2  jb      loc_14007FA4E
0x14007f7d8  mov     edx, 2Bh ; '+'
0x14007f7dd  jmp     loc_14007FA3F
0x14007f7e2  mov     r8d, [rdi+4]
0x14007f7e6  lea     rdx, aType; "Type"
0x14007f7ed  mov     rcx, [rsp+78h+hKey]
0x14007f7f5  call    SetRegistryDword
0x14007f7fa  test    eax, eax
0x14007f7fc  jnz     short loc_14007F834
0x14007f7fe  call    cs:__imp_GetLastError
0x14007f804  mov     ebx, eax
0x14007f806  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f80d  cmp     rcx, r12
0x14007f810  jz      loc_14007FA4E
0x14007f816  test    [rcx+1Ch], r14b
0x14007f81a  jz      loc_14007FA4E
0x14007f820  cmp     [rcx+19h], r14b
0x14007f824  jb      loc_14007FA4E
0x14007f82a  mov     edx, 2Ch ; ','
0x14007f82f  jmp     loc_14007FA3F
0x14007f834  test    byte ptr [rdi+4], 1
0x14007f838  jnz     short loc_14007F844
0x14007f83a  cmp     dword ptr [rdi+40h], 0
0x14007f83e  jz      loc_14007FA4E
0x14007f844  mov     r8d, [rdi+20h]
0x14007f848  lea     rdx, aPort; "Port"
0x14007f84f  mov     rcx, [rsp+78h+hKey]
0x14007f857  call    SetRegistryDword
0x14007f85c  test    eax, eax
0x14007f85e  jnz     short loc_14007F896
0x14007f860  call    cs:__imp_GetLastError
0x14007f866  mov     ebx, eax
0x14007f868  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f86f  cmp     rcx, r12
0x14007f872  jz      loc_14007FA4E
0x14007f878  test    [rcx+1Ch], r14b
0x14007f87c  jz      loc_14007FA4E
0x14007f882  cmp     [rcx+19h], r14b
0x14007f886  jb      loc_14007FA4E
0x14007f88c  mov     edx, 2Dh ; '-'
0x14007f891  jmp     loc_14007FA3F
0x14007f896  mov     r8d, [rdi+8]
0x14007f89a  lea     rdx, aSmtpauth; "SMTPAuth"
0x14007f8a1  mov     rcx, [rsp+78h+hKey]
0x14007f8a9  call    SetRegistryDword
0x14007f8ae  test    eax, eax
0x14007f8b0  jnz     short loc_14007F8E8
0x14007f8b2  call    cs:__imp_GetLastError
0x14007f8b8  mov     ebx, eax
0x14007f8ba  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f8c1  cmp     rcx, r12
0x14007f8c4  jz      loc_14007FA4E
0x14007f8ca  test    [rcx+1Ch], r14b
0x14007f8ce  jz      loc_14007FA4E
0x14007f8d4  cmp     [rcx+19h], r14b
0x14007f8d8  jb      loc_14007FA4E
0x14007f8de  mov     edx, 2Eh ; '.'
0x14007f8e3  jmp     loc_14007FA3F
0x14007f8e8  cmp     qword ptr [rdi+18h], 0
0x14007f8ed  lea     rsi, Class
0x14007f8f4  mov     rcx, [rsp+78h+hKey]; HKEY
0x14007f8fc  lea     r8, aServer; "Server"
0x14007f903  mov     r9, rsi
0x14007f906  mov     edx, 1; unsigned int
0x14007f90b  cmovnz  r9, [rdi+18h]; unsigned __int16 *
0x14007f910  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x14007f915  test    eax, eax
0x14007f917  jnz     short loc_14007F94F
0x14007f919  call    cs:__imp_GetLastError
0x14007f91f  mov     ebx, eax
0x14007f921  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f928  cmp     rcx, r12
0x14007f92b  jz      loc_14007FA4E
0x14007f931  test    [rcx+1Ch], r14b
0x14007f935  jz      loc_14007FA4E
0x14007f93b  cmp     [rcx+19h], r14b
0x14007f93f  jb      loc_14007FA4E
0x14007f945  mov     edx, 2Fh ; '/'
0x14007f94a  jmp     loc_14007FA3F
0x14007f94f  cmp     qword ptr [rdi+28h], 0
0x14007f954  lea     r8, aFrom; "From"
0x14007f95b  mov     rcx, [rsp+78h+hKey]; HKEY
0x14007f963  mov     r9, rsi
0x14007f966  cmovnz  r9, [rdi+28h]; unsigned __int16 *
0x14007f96b  mov     edx, 1; unsigned int
0x14007f970  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x14007f975  test    eax, eax
0x14007f977  jnz     short loc_14007F9AF
0x14007f979  call    cs:__imp_GetLastError
0x14007f97f  mov     ebx, eax
0x14007f981  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f988  cmp     rcx, r12
0x14007f98b  jz      loc_14007FA4E
0x14007f991  test    [rcx+1Ch], r14b
0x14007f995  jz      loc_14007FA4E
0x14007f99b  cmp     [rcx+19h], r14b
0x14007f99f  jb      loc_14007FA4E
0x14007f9a5  mov     edx, 30h ; '0'
0x14007f9aa  jmp     loc_14007FA3F
0x14007f9af  cmp     qword ptr [rdi+30h], 0
0x14007f9b4  lea     r8, aUser; "User"
0x14007f9bb  mov     rcx, [rsp+78h+hKey]; HKEY
0x14007f9c3  mov     edx, 1; unsigned int
0x14007f9c8  cmovnz  rsi, [rdi+30h]
0x14007f9cd  mov     r9, rsi; unsigned __int16 *
0x14007f9d0  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x14007f9d5  test    eax, eax
0x14007f9d7  jnz     short loc_14007FA00
0x14007f9d9  call    cs:__imp_GetLastError
0x14007f9df  mov     ebx, eax
0x14007f9e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f9e8  cmp     rcx, r12
0x14007f9eb  jz      short loc_14007FA4E
0x14007f9ed  test    [rcx+1Ch], r14b
0x14007f9f1  jz      short loc_14007FA4E
0x14007f9f3  cmp     [rcx+19h], r14b
0x14007f9f7  jb      short loc_14007FA4E
0x14007f9f9  mov     edx, 31h ; '1'
0x14007f9fe  jmp     short loc_14007FA3F
0x14007fa00  mov     r8, [rdi+38h]
0x14007fa04  test    r8, r8
0x14007fa07  jz      short loc_14007FA4E
0x14007fa09  mov     rcx, [rsp+78h+hKey]
0x14007fa11  call    SetRegistrySecureString
0x14007fa16  test    eax, eax
0x14007fa18  jnz     short loc_14007FA4E
0x14007fa1a  call    cs:__imp_GetLastError
0x14007fa20  mov     ebx, eax
0x14007fa22  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fa29  cmp     rcx, r12
0x14007fa2c  jz      short loc_14007FA4E
0x14007fa2e  test    [rcx+1Ch], r14b
0x14007fa32  jz      short loc_14007FA4E
0x14007fa34  cmp     [rcx+19h], r14b
0x14007fa38  jb      short loc_14007FA4E
0x14007fa3a  mov     edx, 32h ; '2'
0x14007fa3f  mov     rcx, [rcx+10h]
0x14007fa43  mov     r9d, eax
0x14007fa46  mov     r8, r13
0x14007fa49  call    WPP_SF_d
0x14007fa4e  mov     rcx, [rsp+78h+hKey]; hKey
0x14007fa56  test    rcx, rcx
0x14007fa59  jz      short loc_14007FA61
0x14007fa5b  call    cs:__imp_RegCloseKey
0x14007fa61  mov     rcx, rbp; hKey
0x14007fa64  call    cs:__imp_RegCloseKey
0x14007fa6a  lea     r11, [rsp+78h+var_28]
0x14007fa6f  mov     eax, ebx
0x14007fa71  mov     rbx, [r11+30h]
0x14007fa75  mov     rbp, [r11+40h]
0x14007fa79  mov     rsp, r11
0x14007fa7c  pop     r14
0x14007fa7e  pop     r13
0x14007fa80  pop     r12
0x14007fa82  pop     rdi
0x14007fa83  pop     rsi
0x14007fa84  retn
```
