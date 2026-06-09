# OpenExtensionKey

- ea: `0x14007b584`
- end: `0x14007b814`
- name: `OpenExtensionKey`
- size: `656`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14007e100`
- `0x14007fc2c`

## callees

- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004e68`
- `0x1400708c4`
- `0x14007b584`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14007b675`
- `ADVAPI32!RegCloseKey` at `0x14007b675`
- `KERNEL32!GetLastError` at `0x14007b62d`
- `KERNEL32!GetLastError` at `0x14007b7b1`
- `KERNEL32!GetLastError` at `0x14007b62d`
- `KERNEL32!GetLastError` at `0x14007b7b1`

## string_xrefs

- `0x14007b71b`: `UnassociatedExtensionData`

## pseudocode

```c
__int64 __fastcall OpenExtensionKey(unsigned int a1, int a2, HKEY *a3)
{
  __int64 result; // rax
  HKEY v7; // rax
  DWORD LastError; // eax
  DWORD v9; // ebx
  int v10; // eax
  int v11; // eax
  unsigned int v12; // ebx
  HKEY v13; // rax
  DWORD v14; // eax
  unsigned __int16 v15[264]; // [rsp+30h] [rbp-238h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a2 != 1 )
        return 31;
      v7 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\TAPIDevices", 1, 0x20019u);
      if ( !v7 )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, LastError);
        }
        return v9;
      }
      RegCloseKey(v7);
      v10 = StringCchPrintfW(v15, 0x104u, L"%s\\%08lx", L"Software\\Microsoft\\Fax\\TAPIDevices", a1);
      v9 = v10;
      if ( v10 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            89,
            &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
            (unsigned int)v10);
        }
        if ( (v9 & 0x1FFF0000) == 0x70000 )
          return (unsigned __int16)v9;
        return v9;
      }
LABEL_31:
      v9 = 0;
      v13 = OpenRegistryKey(HKEY_LOCAL_MACHINE, v15, 1, 0x2001Fu);
      *a3 = v13;
      if ( !v13 )
      {
        v14 = GetLastError();
        v9 = v14;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, a1, v14);
        }
      }
      return v9;
    }
    v11 = StringCchPrintfW(
            v15,
            0x104u,
            L"%s\\%010d\\%s",
            L"Software\\Microsoft\\Fax\\Devices",
            a1,
            L"{F10A5326-0261-4715-B367-2970427BBD99}");
  }
  else
  {
    v11 = StringCchPrintfW(v15, 0x104u, L"%s\\%s", L"Software\\Microsoft\\Fax\\Devices", L"UnassociatedExtensionData");
  }
  v12 = v11;
  if ( v11 >= 0 )
    goto LABEL_31;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      87,
      &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
      (unsigned int)v11);
  }
  result = (unsigned __int16)v12;
  if ( (v12 & 0x1FFF0000) != 0x70000 )
    return v12;
  return result;
}

```

## disassembly

```asm
0x14007b584  mov     [rsp+arg_8], rbx
0x14007b589  mov     [rsp+arg_18], rsi
0x14007b58e  push    rdi
0x14007b58f  push    r14
0x14007b591  push    r15
0x14007b593  sub     rsp, 250h
0x14007b59a  mov     rax, cs:__security_cookie
0x14007b5a1  xor     rax, rsp
0x14007b5a4  mov     [rsp+268h+var_28], rax
0x14007b5ac  mov     rsi, r8
0x14007b5af  mov     ebx, edx
0x14007b5b1  mov     edi, ecx
0x14007b5b3  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b5ba  lea     r14, WPP_GLOBAL_Control
0x14007b5c1  lea     r15, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007b5c8  cmp     rcx, r14
0x14007b5cb  jz      short loc_14007B5EA
0x14007b5cd  test    byte ptr [rcx+1Ch], 2
0x14007b5d1  jz      short loc_14007B5EA
0x14007b5d3  cmp     byte ptr [rcx+19h], 5
0x14007b5d7  jb      short loc_14007B5EA
0x14007b5d9  mov     rcx, [rcx+10h]
0x14007b5dd  mov     edx, 56h ; 'V'
0x14007b5e2  mov     r8, r15
0x14007b5e5  call    WPP_SF_
0x14007b5ea  test    edi, edi
0x14007b5ec  jz      loc_14007B71B
0x14007b5f2  test    ebx, ebx
0x14007b5f4  jz      loc_14007B6EC
0x14007b5fa  cmp     ebx, 1
0x14007b5fd  jz      short loc_14007B609
0x14007b5ff  mov     eax, 1Fh
0x14007b604  jmp     loc_14007B7EB
0x14007b609  mov     r9d, 20019h
0x14007b60f  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Fax\\TAPIDevices"
0x14007b616  mov     r8d, 1
0x14007b61c  mov     rcx, 0FFFFFFFF80000002h
0x14007b623  call    OpenRegistryKey
0x14007b628  test    rax, rax
0x14007b62b  jnz     short loc_14007B672
0x14007b62d  call    cs:__imp_GetLastError
0x14007b633  mov     ebx, eax
0x14007b635  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b63c  cmp     rcx, r14
0x14007b63f  jz      loc_14007B7E9
0x14007b645  test    byte ptr [rcx+1Ch], 2
0x14007b649  jz      loc_14007B7E9
0x14007b64f  cmp     byte ptr [rcx+19h], 2
0x14007b653  jb      loc_14007B7E9
0x14007b659  mov     rcx, [rcx+10h]
0x14007b65d  mov     edx, 58h ; 'X'
0x14007b662  mov     r9d, eax
0x14007b665  mov     r8, r15
0x14007b668  call    WPP_SF_d
0x14007b66d  jmp     loc_14007B7E9
0x14007b672  mov     rcx, rax; hKey
0x14007b675  call    cs:__imp_RegCloseKey
0x14007b67b  lea     r9, aSoftwareMicros_7; "Software\\Microsoft\\Fax\\TAPIDevices"
0x14007b682  mov     dword ptr [rsp+268h+var_248], edi
0x14007b686  lea     r8, aS08lx; "%s\\%08lx"
0x14007b68d  mov     edx, 104h; unsigned __int64
0x14007b692  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x14007b697  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007b69c  mov     ebx, eax
0x14007b69e  test    eax, eax
0x14007b6a0  jns     loc_14007B78C
0x14007b6a6  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b6ad  cmp     rcx, r14
0x14007b6b0  jz      short loc_14007B6D2
0x14007b6b2  test    byte ptr [rcx+1Ch], 2
0x14007b6b6  jz      short loc_14007B6D2
0x14007b6b8  cmp     byte ptr [rcx+19h], 2
0x14007b6bc  jb      short loc_14007B6D2
0x14007b6be  mov     rcx, [rcx+10h]
0x14007b6c2  mov     edx, 59h ; 'Y'
0x14007b6c7  mov     r9d, eax
0x14007b6ca  mov     r8, r15
0x14007b6cd  call    WPP_SF_d
0x14007b6d2  mov     eax, ebx
0x14007b6d4  and     eax, 1FFF0000h
0x14007b6d9  cmp     eax, 70000h
0x14007b6de  jnz     loc_14007B7E9
0x14007b6e4  movzx   ebx, bx
0x14007b6e7  jmp     loc_14007B7E9
0x14007b6ec  lea     rax, aF10a5326026147; "{F10A5326-0261-4715-B367-2970427BBD99}"
0x14007b6f3  mov     edx, 104h; unsigned __int64
0x14007b6f8  mov     [rsp+268h+var_240], rax
0x14007b6fd  lea     r9, aSoftwareMicros_12; "Software\\Microsoft\\Fax\\Devices"
0x14007b704  lea     r8, aS010dS; "%s\\%010d\\%s"
0x14007b70b  mov     dword ptr [rsp+268h+var_248], edi
0x14007b70f  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x14007b714  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007b719  jmp     short loc_14007B744
0x14007b71b  lea     rax, aUnassociatedex; "UnassociatedExtensionData"
0x14007b722  mov     edx, 104h; unsigned __int64
0x14007b727  lea     r9, aSoftwareMicros_12; "Software\\Microsoft\\Fax\\Devices"
0x14007b72e  mov     [rsp+268h+var_248], rax
0x14007b733  lea     r8, aSS_0; "%s\\%s"
0x14007b73a  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x14007b73f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007b744  mov     ebx, eax
0x14007b746  test    eax, eax
0x14007b748  jns     short loc_14007B78C
0x14007b74a  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b751  cmp     rcx, r14
0x14007b754  jz      short loc_14007B776
0x14007b756  test    byte ptr [rcx+1Ch], 2
0x14007b75a  jz      short loc_14007B776
0x14007b75c  cmp     byte ptr [rcx+19h], 2
0x14007b760  jb      short loc_14007B776
0x14007b762  mov     rcx, [rcx+10h]
0x14007b766  mov     edx, 57h ; 'W'
0x14007b76b  mov     r9d, eax
0x14007b76e  mov     r8, r15
0x14007b771  call    WPP_SF_d
0x14007b776  mov     ecx, ebx
0x14007b778  movzx   eax, bx
0x14007b77b  and     ecx, 1FFF0000h
0x14007b781  cmp     ecx, 70000h
0x14007b787  cmovnz  eax, ebx
0x14007b78a  jmp     short loc_14007B7EB
0x14007b78c  xor     ebx, ebx
0x14007b78e  lea     rdx, [rsp+268h+var_238]
0x14007b793  mov     r9d, 2001Fh
0x14007b799  mov     rcx, 0FFFFFFFF80000002h
0x14007b7a0  lea     r8d, [rbx+1]
0x14007b7a4  call    OpenRegistryKey
0x14007b7a9  mov     [rsi], rax
0x14007b7ac  test    rax, rax
0x14007b7af  jnz     short loc_14007B7E9
0x14007b7b1  call    cs:__imp_GetLastError
0x14007b7b7  mov     ebx, eax
0x14007b7b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b7c0  cmp     rcx, r14
0x14007b7c3  jz      short loc_14007B7E9
0x14007b7c5  test    byte ptr [rcx+1Ch], 2
0x14007b7c9  jz      short loc_14007B7E9
0x14007b7cb  cmp     byte ptr [rcx+19h], 2
0x14007b7cf  jb      short loc_14007B7E9
0x14007b7d1  mov     rcx, [rcx+10h]
0x14007b7d5  mov     edx, 5Ah ; 'Z'
0x14007b7da  mov     r9d, edi
0x14007b7dd  mov     dword ptr [rsp+268h+var_248], eax
0x14007b7e1  mov     r8, r15
0x14007b7e4  call    WPP_SF_dd
0x14007b7e9  mov     eax, ebx
0x14007b7eb  mov     rcx, [rsp+268h+var_28]
0x14007b7f3  xor     rcx, rsp; StackCookie
0x14007b7f6  call    __security_check_cookie
0x14007b7fb  lea     r11, [rsp+268h+var_18]
0x14007b803  mov     rbx, [r11+28h]
0x14007b807  mov     rsi, [r11+38h]
0x14007b80b  mov     rsp, r11
0x14007b80e  pop     r15
0x14007b810  pop     r14
0x14007b812  pop     rdi
0x14007b813  retn
```
