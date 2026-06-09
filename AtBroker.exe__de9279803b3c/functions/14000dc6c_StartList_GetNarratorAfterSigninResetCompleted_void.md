# StartList::GetNarratorAfterSigninResetCompleted(void)

- ea: `0x14000dc6c`
- end: `0x14000ddaa`
- name: `?GetNarratorAfterSigninResetCompleted@StartList@@SA_NXZ`
- size: `318`
- prototype: `char(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140009264`

## callees

- `0x14000ab98`
- `0x14000dc6c`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x14000dcdf`
- `ADVAPI32!RegQueryValueExW` at `0x14000dcdf`
- `ADVAPI32!RegOpenKeyExW` at `0x14000dc9c`
- `ADVAPI32!RegOpenKeyExW` at `0x14000dc9c`
- `ADVAPI32!RegCloseKey` at `0x14000dd2f`
- `ADVAPI32!RegCloseKey` at `0x14000dd4f`
- `ADVAPI32!RegCloseKey` at `0x14000dd98`
- `ADVAPI32!RegCloseKey` at `0x14000dd2f`
- `ADVAPI32!RegCloseKey` at `0x14000dd4f`
- `ADVAPI32!RegCloseKey` at `0x14000dd98`

## string_xrefs

- `0x14000dcd3`: `NarratorAfterSigninResetCompleted`
- `0x14000dc8e`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`

## pseudocode

```c
char StartList::GetNarratorAfterSigninResetCompleted(void)
{
  unsigned int v0; // eax
  __int64 v1; // r9
  LSTATUS v2; // eax
  HKEY v3; // rcx
  char v4; // bl
  int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_CURRENT_USER, StartList::_accessibilityKeyString, 0, 0x2001Fu, &hKey);
  v1 = v0;
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      LODWORD(v1) = v0 | 0x10000000;
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v1);
    }
    v3 = hKey;
    if ( !hKey )
      return 1;
LABEL_18:
    RegCloseKey(v3);
    return 1;
  }
  Data = 0;
  cbData = 4;
  v2 = RegQueryValueExW(hKey, L"NarratorAfterSigninResetCompleted", 0, 0, (LPBYTE)&Data, &cbData);
  if ( v2 )
  {
    if ( v2 != 2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids,
          v2 | 0x10000000u);
      v3 = hKey;
      if ( !hKey )
        return 1;
      goto LABEL_18;
    }
    goto LABEL_10;
  }
  v4 = 1;
  if ( Data != 1 )
LABEL_10:
    v4 = 0;
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x14000dc6c  push    rbx
0x14000dc6e  sub     rsp, 30h
0x14000dc72  mov     [rsp+38h+hKey], 0
0x14000dc7b  lea     rax, [rsp+38h+hKey]
0x14000dc80  mov     [rsp+38h+phkResult], rax; phkResult
0x14000dc85  mov     r9d, 2001Fh; samDesired
0x14000dc8b  xor     r8d, r8d; ulOptions
0x14000dc8e  lea     rdx, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14000dc95  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000dc9c  call    cs:__imp_RegOpenKeyExW
0x14000dca2  mov     r9d, eax
0x14000dca5  test    eax, eax
0x14000dca7  jnz     loc_14000DD5A
0x14000dcad  mov     [rsp+38h+Data], eax
0x14000dcb1  mov     [rsp+38h+cbData], 4
0x14000dcb9  lea     rax, [rsp+38h+cbData]
0x14000dcbe  mov     [rsp+38h+lpcbData], rax; lpcbData
0x14000dcc3  lea     rax, [rsp+38h+Data]
0x14000dcc8  mov     [rsp+38h+phkResult], rax; lpData
0x14000dccd  xor     r9d, r9d; lpType
0x14000dcd0  xor     r8d, r8d; lpReserved
0x14000dcd3  lea     rdx, aNarratorafters; "NarratorAfterSigninResetCompleted"
0x14000dcda  mov     rcx, [rsp+38h+hKey]; hKey
0x14000dcdf  call    cs:__imp_RegQueryValueExW
0x14000dce5  test    eax, eax
0x14000dce7  jz      short loc_14000DD38
0x14000dce9  cmp     eax, 2
0x14000dcec  jz      short loc_14000DD43
0x14000dcee  lea     rcx, WPP_GLOBAL_Control
0x14000dcf5  mov     r10, cs:WPP_GLOBAL_Control
0x14000dcfc  cmp     r10, rcx
0x14000dcff  jz      short loc_14000DD25
0x14000dd01  test    byte ptr [r10+1Ch], 8
0x14000dd06  jz      short loc_14000DD25
0x14000dd08  bts     eax, 1Ch
0x14000dd0c  mov     edx, 32h ; '2'
0x14000dd11  mov     r9d, eax
0x14000dd14  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14000dd1b  mov     rcx, [r10+10h]
0x14000dd1f  call    WPP_SF_D
0x14000dd24  nop
0x14000dd25  mov     rcx, [rsp+38h+hKey]; hKey
0x14000dd2a  test    rcx, rcx
0x14000dd2d  jz      short loc_14000DD9F
0x14000dd2f  call    cs:__imp_RegCloseKey
0x14000dd35  nop
0x14000dd36  jmp     short loc_14000DD9F
0x14000dd38  mov     ebx, 1
0x14000dd3d  cmp     [rsp+38h+Data], ebx
0x14000dd41  jz      short loc_14000DD45
0x14000dd43  xor     bl, bl
0x14000dd45  mov     rcx, [rsp+38h+hKey]; hKey
0x14000dd4a  test    rcx, rcx
0x14000dd4d  jz      short loc_14000DD56
0x14000dd4f  call    cs:__imp_RegCloseKey
0x14000dd55  nop
0x14000dd56  mov     al, bl
0x14000dd58  jmp     short loc_14000DDA4
0x14000dd5a  lea     rcx, WPP_GLOBAL_Control
0x14000dd61  mov     rax, cs:WPP_GLOBAL_Control
0x14000dd68  cmp     rax, rcx
0x14000dd6b  jz      short loc_14000DD8E
0x14000dd6d  test    byte ptr [rax+1Ch], 8
0x14000dd71  jz      short loc_14000DD8E
0x14000dd73  bts     r9d, 1Ch
0x14000dd78  mov     edx, 33h ; '3'
0x14000dd7d  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14000dd84  mov     rcx, [rax+10h]
0x14000dd88  call    WPP_SF_D
0x14000dd8d  nop
0x14000dd8e  mov     rcx, [rsp+38h+hKey]; hKey
0x14000dd93  test    rcx, rcx
0x14000dd96  jz      short loc_14000DD9F
0x14000dd98  call    cs:__imp_RegCloseKey
0x14000dd9e  nop
0x14000dd9f  mov     eax, 1
0x14000dda4  add     rsp, 30h
0x14000dda8  pop     rbx
0x14000dda9  retn
```
