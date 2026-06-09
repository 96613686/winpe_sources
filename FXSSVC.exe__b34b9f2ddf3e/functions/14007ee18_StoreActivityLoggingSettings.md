# StoreActivityLoggingSettings

- ea: `0x14007ee18`
- end: `0x14007f06a`
- name: `StoreActivityLoggingSettings`
- size: `594`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001e140`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x14006fa88`
- `0x1400708c4`
- `0x1400709fc`
- `0x14007ee18`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14007f04b`
- `ADVAPI32!RegCloseKey` at `0x14007f054`
- `ADVAPI32!RegCloseKey` at `0x14007f04b`
- `ADVAPI32!RegCloseKey` at `0x14007f054`
- `ADVAPI32!RegCreateKeyExW` at `0x14007ef03`
- `ADVAPI32!RegCreateKeyExW` at `0x14007ef03`
- `KERNEL32!GetLastError` at `0x14007ee8c`
- `KERNEL32!GetLastError` at `0x14007ef59`
- `KERNEL32!GetLastError` at `0x14007efab`
- `KERNEL32!GetLastError` at `0x14007f00a`
- `KERNEL32!GetLastError` at `0x14007ee8c`
- `KERNEL32!GetLastError` at `0x14007ef59`
- `KERNEL32!GetLastError` at `0x14007efab`
- `KERNEL32!GetLastError` at `0x14007f00a`

## string_xrefs

- `0x14007ef41`: `LogIncoming`

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
0x14007ee18  mov     rax, rsp
0x14007ee1b  push    rbx
0x14007ee1c  push    rsi
0x14007ee1d  push    rdi
0x14007ee1e  push    r12
0x14007ee20  push    r14
0x14007ee22  push    r15
0x14007ee24  sub     rsp, 58h
0x14007ee28  xor     r14d, r14d
0x14007ee2b  mov     rdi, rcx
0x14007ee2e  mov     [rax+10h], r14
0x14007ee32  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ee39  lea     r15, WPP_GLOBAL_Control
0x14007ee40  lea     r12, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007ee47  cmp     rcx, r15
0x14007ee4a  jz      short loc_14007EE68
0x14007ee4c  test    byte ptr [rcx+1Ch], 2
0x14007ee50  jz      short loc_14007EE68
0x14007ee52  cmp     byte ptr [rcx+19h], 5
0x14007ee56  jb      short loc_14007EE68
0x14007ee58  mov     rcx, [rcx+10h]
0x14007ee5c  lea     edx, [r14+41h]
0x14007ee60  mov     r8, r12
0x14007ee63  call    WPP_SF_
0x14007ee68  mov     r9d, 20006h
0x14007ee6e  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Fax"
0x14007ee75  xor     r8d, r8d
0x14007ee78  mov     rcx, 0FFFFFFFF80000002h
0x14007ee7f  call    OpenRegistryKey
0x14007ee84  mov     rsi, rax
0x14007ee87  test    rax, rax
0x14007ee8a  jnz     short loc_14007EECF
0x14007ee8c  call    cs:__imp_GetLastError
0x14007ee92  mov     ebx, eax
0x14007ee94  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ee9b  cmp     rcx, r15
0x14007ee9e  jz      loc_14007F05A
0x14007eea4  test    byte ptr [rcx+1Ch], 2
0x14007eea8  jz      loc_14007F05A
0x14007eeae  cmp     byte ptr [rcx+19h], 2
0x14007eeb2  jb      loc_14007F05A
0x14007eeb8  mov     rcx, [rcx+10h]
0x14007eebc  lea     edx, [rsi+42h]
0x14007eebf  mov     r9d, eax
0x14007eec2  mov     r8, r12
0x14007eec5  call    WPP_SF_d
0x14007eeca  jmp     loc_14007F05A
0x14007eecf  mov     [rsp+88h+lpdwDisposition], r14; lpdwDisposition
0x14007eed4  lea     rax, [rsp+88h+hKey]
0x14007eedc  mov     [rsp+88h+phkResult], rax; phkResult
0x14007eee1  lea     rdx, aActivityloggin; "ActivityLogging"
0x14007eee8  mov     [rsp+88h+lpSecurityAttributes], r14; lpSecurityAttributes
0x14007eeed  xor     r9d, r9d; lpClass
0x14007eef0  mov     [rsp+88h+samDesired], 2000000h; samDesired
0x14007eef8  xor     r8d, r8d; Reserved
0x14007eefb  mov     rcx, rsi; hKey
0x14007eefe  mov     [rsp+88h+dwOptions], r14d; int
0x14007ef03  call    cs:__imp_RegCreateKeyExW
0x14007ef09  mov     ebx, eax
0x14007ef0b  test    eax, eax
0x14007ef0d  jz      short loc_14007EF3D
0x14007ef0f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ef16  cmp     rcx, r15
0x14007ef19  jz      loc_14007F03E
0x14007ef1f  test    byte ptr [rcx+1Ch], 2
0x14007ef23  jz      loc_14007F03E
0x14007ef29  cmp     byte ptr [rcx+19h], 2
0x14007ef2d  jb      loc_14007F03E
0x14007ef33  mov     edx, 43h ; 'C'
0x14007ef38  jmp     loc_14007F02F
0x14007ef3d  mov     r8d, [rdi+4]
0x14007ef41  lea     rdx, aLogincoming; "LogIncoming"
0x14007ef48  mov     rcx, [rsp+88h+hKey]
0x14007ef50  call    SetRegistryDword
0x14007ef55  test    eax, eax
0x14007ef57  jnz     short loc_14007EF8F
0x14007ef59  call    cs:__imp_GetLastError
0x14007ef5f  mov     ebx, eax
0x14007ef61  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ef68  cmp     rcx, r15
0x14007ef6b  jz      loc_14007F03E
0x14007ef71  test    byte ptr [rcx+1Ch], 2
0x14007ef75  jz      loc_14007F03E
0x14007ef7b  cmp     byte ptr [rcx+19h], 2
0x14007ef7f  jb      loc_14007F03E
0x14007ef85  mov     edx, 44h ; 'D'
0x14007ef8a  jmp     loc_14007F02F
0x14007ef8f  mov     r8d, [rdi+8]
0x14007ef93  lea     rdx, aLogoutgoing; "LogOutgoing"
0x14007ef9a  mov     rcx, [rsp+88h+hKey]
0x14007efa2  call    SetRegistryDword
0x14007efa7  test    eax, eax
0x14007efa9  jnz     short loc_14007EFD2
0x14007efab  call    cs:__imp_GetLastError
0x14007efb1  mov     ebx, eax
0x14007efb3  mov     rcx, cs:WPP_GLOBAL_Control
0x14007efba  cmp     rcx, r15
0x14007efbd  jz      short loc_14007F03E
0x14007efbf  test    byte ptr [rcx+1Ch], 2
0x14007efc3  jz      short loc_14007F03E
0x14007efc5  cmp     byte ptr [rcx+19h], 2
0x14007efc9  jb      short loc_14007F03E
0x14007efcb  mov     edx, 45h ; 'E'
0x14007efd0  jmp     short loc_14007F02F
0x14007efd2  cmp     [rdi+4], r14d
0x14007efd6  jnz     short loc_14007EFDE
0x14007efd8  cmp     [rdi+8], r14d
0x14007efdc  jz      short loc_14007F03E
0x14007efde  mov     r9, [rdi+10h]; unsigned __int16 *
0x14007efe2  test    r9, r9
0x14007efe5  jz      short loc_14007F03E
0x14007efe7  cmp     [r9], r14w
0x14007efeb  jz      short loc_14007F03E
0x14007efed  mov     rcx, [rsp+88h+hKey]; HKEY
0x14007eff5  lea     r8, aDbfile; "DBFile"
0x14007effc  mov     edx, 1; unsigned int
0x14007f001  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x14007f006  test    eax, eax
0x14007f008  jnz     short loc_14007F03E
0x14007f00a  call    cs:__imp_GetLastError
0x14007f010  mov     ebx, eax
0x14007f012  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f019  cmp     rcx, r15
0x14007f01c  jz      short loc_14007F03E
0x14007f01e  test    byte ptr [rcx+1Ch], 2
0x14007f022  jz      short loc_14007F03E
0x14007f024  cmp     byte ptr [rcx+19h], 2
0x14007f028  jb      short loc_14007F03E
0x14007f02a  mov     edx, 46h ; 'F'
0x14007f02f  mov     rcx, [rcx+10h]
0x14007f033  mov     r9d, eax
0x14007f036  mov     r8, r12
0x14007f039  call    WPP_SF_d
0x14007f03e  mov     rcx, [rsp+88h+hKey]; hKey
0x14007f046  test    rcx, rcx
0x14007f049  jz      short loc_14007F051
0x14007f04b  call    cs:__imp_RegCloseKey
0x14007f051  mov     rcx, rsi; hKey
0x14007f054  call    cs:__imp_RegCloseKey
0x14007f05a  mov     eax, ebx
0x14007f05c  add     rsp, 58h
0x14007f060  pop     r15
0x14007f062  pop     r14
0x14007f064  pop     r12
0x14007f066  pop     rdi
0x14007f067  pop     rsi
0x14007f068  pop     rbx
0x14007f069  retn
```
