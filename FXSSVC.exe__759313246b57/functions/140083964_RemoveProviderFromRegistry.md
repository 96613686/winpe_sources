# RemoveProviderFromRegistry

- ea: `0x140083964`
- end: `0x140083ac3`
- name: `RemoveProviderFromRegistry`
- size: `351`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140023120`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x140083964`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140083a70`
- `ADVAPI32!RegCloseKey` at `0x140083a70`
- `ADVAPI32!RegOpenKeyExW` at `0x1400839d4`
- `ADVAPI32!RegOpenKeyExW` at `0x1400839d4`
- `ADVAPI32!RegDeleteKeyExW` at `0x140083a25`
- `ADVAPI32!RegDeleteKeyExW` at `0x140083a25`

## pseudocode

```c
__int64 __fastcall RemoveProviderFromRegistry(LPCWSTR lpSubKey)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  CMapDeviceId *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  LSTATUS v7; // eax
  unsigned int v8; // eax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Device Providers", 0, 0x10000u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 118;
      v6 = v2;
LABEL_20:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v6);
    }
  }
  else
  {
    v7 = RegDeleteKeyExW(hKey, lpSubKey, 0, 0);
    v3 = v7;
    if ( v7
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        119,
        (unsigned int)&WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
        (_DWORD)lpSubKey,
        v7);
    }
    v8 = RegCloseKey(hKey);
    if ( v8 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 120;
        v6 = v8;
        goto LABEL_20;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140083964  mov     [rsp+arg_0], rbx
0x140083969  mov     [rsp+arg_10], rbp
0x14008396e  push    rdi
0x14008396f  sub     rsp, 30h
0x140083973  mov     rdi, rcx
0x140083976  mov     [rsp+38h+hKey], 0
0x14008397f  mov     rcx, cs:WPP_GLOBAL_Control
0x140083986  lea     rbp, WPP_GLOBAL_Control
0x14008398d  cmp     rcx, rbp
0x140083990  jz      short loc_1400839B3
0x140083992  test    byte ptr [rcx+1Ch], 2
0x140083996  jz      short loc_1400839B3
0x140083998  cmp     byte ptr [rcx+19h], 5
0x14008399c  jb      short loc_1400839B3
0x14008399e  mov     rcx, [rcx+10h]
0x1400839a2  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x1400839a9  mov     edx, 75h ; 'u'
0x1400839ae  call    WPP_SF_
0x1400839b3  lea     rax, [rsp+38h+hKey]
0x1400839b8  mov     r9d, 10000h; samDesired
0x1400839be  xor     r8d, r8d; ulOptions
0x1400839c1  mov     [rsp+38h+phkResult], rax; phkResult
0x1400839c6  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Fax\\Device Provid"...
0x1400839cd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400839d4  call    cs:__imp_RegOpenKeyExW
0x1400839db  nop     dword ptr [rax+rax+00h]
0x1400839e0  mov     ebx, eax
0x1400839e2  test    eax, eax
0x1400839e4  jz      short loc_140083A17
0x1400839e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400839ed  cmp     rcx, rbp
0x1400839f0  jz      loc_140083AB0
0x1400839f6  test    byte ptr [rcx+1Ch], 2
0x1400839fa  jz      loc_140083AB0
0x140083a00  cmp     byte ptr [rcx+19h], 2
0x140083a04  jb      loc_140083AB0
0x140083a0a  mov     edx, 76h ; 'v'
0x140083a0f  mov     r9d, eax
0x140083a12  jmp     loc_140083AA0
0x140083a17  mov     rcx, [rsp+38h+hKey]; hKey
0x140083a1c  xor     r9d, r9d; Reserved
0x140083a1f  xor     r8d, r8d; samDesired
0x140083a22  mov     rdx, rdi; lpSubKey
0x140083a25  call    cs:__imp_RegDeleteKeyExW
0x140083a2c  nop     dword ptr [rax+rax+00h]
0x140083a31  mov     ebx, eax
0x140083a33  test    eax, eax
0x140083a35  jz      short loc_140083A6B
0x140083a37  mov     rcx, cs:WPP_GLOBAL_Control
0x140083a3e  cmp     rcx, rbp
0x140083a41  jz      short loc_140083A6B
0x140083a43  test    byte ptr [rcx+1Ch], 2
0x140083a47  jz      short loc_140083A6B
0x140083a49  cmp     byte ptr [rcx+19h], 2
0x140083a4d  jb      short loc_140083A6B
0x140083a4f  mov     rcx, [rcx+10h]
0x140083a53  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140083a5a  mov     edx, 77h ; 'w'
0x140083a5f  mov     dword ptr [rsp+38h+phkResult], eax
0x140083a63  mov     r9, rdi
0x140083a66  call    WPP_SF_Sd
0x140083a6b  mov     rcx, [rsp+38h+hKey]; hKey
0x140083a70  call    cs:__imp_RegCloseKey
0x140083a77  nop     dword ptr [rax+rax+00h]
0x140083a7c  test    eax, eax
0x140083a7e  jz      short loc_140083AB0
0x140083a80  mov     rcx, cs:WPP_GLOBAL_Control
0x140083a87  cmp     rcx, rbp
0x140083a8a  jz      short loc_140083AB0
0x140083a8c  test    byte ptr [rcx+1Ch], 2
0x140083a90  jz      short loc_140083AB0
0x140083a92  cmp     byte ptr [rcx+19h], 2
0x140083a96  jb      short loc_140083AB0
0x140083a98  mov     edx, 78h ; 'x'
0x140083a9d  mov     r9d, eax
0x140083aa0  mov     rcx, [rcx+10h]
0x140083aa4  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140083aab  call    WPP_SF_d
0x140083ab0  mov     rbp, [rsp+38h+arg_10]
0x140083ab5  mov     eax, ebx
0x140083ab7  mov     rbx, [rsp+38h+arg_0]
0x140083abc  add     rsp, 30h
0x140083ac0  pop     rdi
0x140083ac1  retn
```
