# ReadRegQWORDValue(__int64 *,HKEY__ *,ushort const *,ushort const *)

- ea: `0x180008fc4`
- end: `0x18000912e`
- name: `?ReadRegQWORDValue@@YAJPEA_JPEAUHKEY__@@PEBG2@Z`
- size: `362`
- prototype: `__int64 __fastcall(LPBYTE lpData, HKEY hKey, LPCWSTR lpSubKey, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ea88`

## callees

- `0x180008fc4`
- `0x18000a3c0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180009101`
- `ADVAPI32!RegCloseKey` at `0x180009101`
- `ADVAPI32!RegQueryValueExW` at `0x18000909a`
- `ADVAPI32!RegQueryValueExW` at `0x18000909a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000902b`
- `ADVAPI32!RegOpenKeyExW` at `0x18000902b`
- `KERNEL32!SetLastError` at `0x18000910f`
- `KERNEL32!SetLastError` at `0x18000910f`

## pseudocode

```c
__int64 __fastcall ReadRegQWORDValue(LPBYTE lpData, HKEY hKey, LPCWSTR lpSubKey, const unsigned __int16 *a4)
{
  int v4; // edi
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  LPCWSTR v8; // rcx
  int v9; // edx
  const WCHAR *v10; // r9
  HKEY hKeya; // [rsp+30h] [rbp-18h] BYREF
  DWORD Type; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+20h] BYREF
  int v15; // [rsp+6Ch] [rbp+24h]

  v15 = HIDWORD(a4);
  hKeya = 0;
  v4 = (int)lpSubKey;
  Type = 11;
  cbData = 8;
  if ( !lpData || !hKey || !lpSubKey )
  {
    v6 = -2147024809;
    goto LABEL_22;
  }
  v7 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x101u, &hKeya);
  if ( v7 )
  {
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    else
      v6 = v7;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_20;
    v9 = 33;
    LODWORD(v10) = v4;
    goto LABEL_19;
  }
  v6 = 0;
  v7 = RegQueryValueExW(hKeya, L"CreationTime", 0, &Type, lpData, &cbData);
  if ( !v7 )
    goto LABEL_20;
  if ( v7 > 0 )
  {
    v6 = (unsigned __int16)v7 | 0x80070000;
    if ( v7 == 2 )
      goto LABEL_20;
  }
  else
  {
    v6 = v7;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v9 = 34;
    v10 = L"CreationTime";
LABEL_19:
    WPP_SF_Sd(*((_QWORD *)v8 + 2), v9, (unsigned int)&WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids, (_DWORD)v10, v7);
  }
LABEL_20:
  if ( hKeya )
    RegCloseKey(hKeya);
LABEL_22:
  SetLastError(0);
  return v6;
}

```

## disassembly

```asm
0x180008fc4  mov     r11, rsp
0x180008fc7  mov     [r11+10h], rbx
0x180008fcb  mov     [r11+18h], rsi
0x180008fcf  mov     [r11+20h], r9
0x180008fd3  push    rdi
0x180008fd4  sub     rsp, 40h
0x180008fd8  mov     qword ptr [r11-18h], 0
0x180008fe0  mov     rdi, r8
0x180008fe3  mov     [rsp+48h+Type], 0Bh
0x180008feb  mov     rax, rdx
0x180008fee  mov     [rsp+48h+cbData], 8
0x180008ff6  mov     rsi, rcx
0x180008ff9  test    rcx, rcx
0x180008ffc  jnz     short loc_180009008
0x180008ffe  mov     ebx, 80070057h
0x180009003  jmp     loc_18000910D
0x180009008  test    rax, rax
0x18000900b  jz      short loc_180008FFE
0x18000900d  test    rdi, rdi
0x180009010  jz      short loc_180008FFE
0x180009012  lea     rcx, [rsp+48h+hKey]
0x180009017  mov     r9d, 101h; samDesired
0x18000901d  mov     [rsp+48h+phkResult], rcx; phkResult
0x180009022  xor     r8d, r8d; ulOptions
0x180009025  mov     rcx, rax; hKey
0x180009028  mov     rdx, rdi; lpSubKey
0x18000902b  call    cs:__imp_RegOpenKeyExW
0x180009032  nop     dword ptr [rax+rax+00h]
0x180009037  test    eax, eax
0x180009039  jz      short loc_180009075
0x18000903b  jg      short loc_180009041
0x18000903d  mov     ebx, eax
0x18000903f  jmp     short loc_18000904A
0x180009041  movzx   ebx, ax
0x180009044  or      ebx, 80070000h
0x18000904a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009051  lea     rdx, WPP_GLOBAL_Control
0x180009058  cmp     rcx, rdx
0x18000905b  jz      loc_1800090F7
0x180009061  test    byte ptr [rcx+1Ch], 1
0x180009065  jz      loc_1800090F7
0x18000906b  mov     edx, 21h ; '!'
0x180009070  mov     r9, rdi
0x180009073  jmp     short loc_1800090E3
0x180009075  mov     rcx, [rsp+48h+hKey]; hKey
0x18000907a  lea     rax, [rsp+48h+cbData]
0x18000907f  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180009084  lea     r9, [rsp+48h+Type]; lpType
0x180009089  xor     r8d, r8d; lpReserved
0x18000908c  mov     [rsp+48h+phkResult], rsi; lpData
0x180009091  lea     rdx, aCreationtime; "CreationTime"
0x180009098  xor     ebx, ebx
0x18000909a  call    cs:__imp_RegQueryValueExW
0x1800090a1  nop     dword ptr [rax+rax+00h]
0x1800090a6  test    eax, eax
0x1800090a8  jz      short loc_1800090F7
0x1800090aa  jg      short loc_1800090B0
0x1800090ac  mov     ebx, eax
0x1800090ae  jmp     short loc_1800090BE
0x1800090b0  movzx   ebx, ax
0x1800090b3  or      ebx, 80070000h
0x1800090b9  cmp     eax, 2
0x1800090bc  jz      short loc_1800090F7
0x1800090be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090c5  lea     rdx, WPP_GLOBAL_Control
0x1800090cc  cmp     rcx, rdx
0x1800090cf  jz      short loc_1800090F7
0x1800090d1  test    byte ptr [rcx+1Ch], 1
0x1800090d5  jz      short loc_1800090F7
0x1800090d7  mov     edx, 22h ; '"'
0x1800090dc  lea     r9, aCreationtime; "CreationTime"
0x1800090e3  mov     rcx, [rcx+10h]
0x1800090e7  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x1800090ee  mov     dword ptr [rsp+48h+phkResult], eax
0x1800090f2  call    WPP_SF_Sd
0x1800090f7  mov     rcx, [rsp+48h+hKey]; hKey
0x1800090fc  test    rcx, rcx
0x1800090ff  jz      short loc_18000910D
0x180009101  call    cs:__imp_RegCloseKey
0x180009108  nop     dword ptr [rax+rax+00h]
0x18000910d  xor     ecx, ecx; dwErrCode
0x18000910f  call    cs:__imp_SetLastError
0x180009116  nop     dword ptr [rax+rax+00h]
0x18000911b  mov     rsi, [rsp+48h+arg_10]
0x180009120  mov     eax, ebx
0x180009122  mov     rbx, [rsp+48h+arg_8]
0x180009127  add     rsp, 40h
0x18000912b  pop     rdi
0x18000912c  retn
```
