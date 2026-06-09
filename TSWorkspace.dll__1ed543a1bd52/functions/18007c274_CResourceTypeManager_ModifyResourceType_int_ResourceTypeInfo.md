# CResourceTypeManager::ModifyResourceType(int,ResourceTypeInfo &)

- ea: `0x18007c274`
- end: `0x18007c4e6`
- name: `?ModifyResourceType@CResourceTypeManager@@SAJHAEAUResourceTypeInfo@@@Z`
- size: `626`
- prototype: `__int64 __fastcall(int, struct ResourceTypeInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180073d80`

## callees

- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec94`
- `0x18000ece0`
- `0x18007c274`
- `0x18007c4ec`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18007c4be`
- `ADVAPI32!RegCloseKey` at `0x18007c4ce`
- `ADVAPI32!RegCloseKey` at `0x18007c4be`
- `ADVAPI32!RegCloseKey` at `0x18007c4ce`
- `ADVAPI32!RegOpenKeyExW` at `0x18007c3c1`
- `ADVAPI32!RegOpenKeyExW` at `0x18007c3c1`
- `ADVAPI32!RegSetValueExW` at `0x18007c466`
- `ADVAPI32!RegSetValueExW` at `0x18007c466`

## string_xrefs

- `0x18007c36a`: `OpenTopLevelRegKey failed`

## pseudocode

```c
__int64 __fastcall CResourceTypeManager::ModifyResourceType(int a1, struct ResourceTypeInfo *a2)
{
  bool v2; // zf
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v5; // rdx
  int v6; // ebx
  unsigned int v7; // eax
  const WCHAR *v8; // rax
  unsigned int v9; // esi
  unsigned int v10; // eax
  __int64 v11; // rdx
  const BYTE *v12; // rax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp+18h] BYREF

  v2 = *((_QWORD *)a2 + 2) == 0;
  hKey = 0;
  phkResult = 0;
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 26;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      WPP_a72faf600b5a37edaf0216851c61dae8_Traceguids,
      CurrentThreadActivityIdPrefix,
      -2147024809);
LABEL_7:
    v6 = -2147024809;
    goto LABEL_38;
  }
  if ( !*((_QWORD *)a2 + 6) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 27;
    goto LABEL_6;
  }
  v6 = CResourceTypeManager::OpenTopLevelRegKey(a1, 0x2001Fu, &hKey);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        (unsigned int)WPP_a72faf600b5a37edaf0216851c61dae8_Traceguids,
        v7,
        (__int64)"OpenTopLevelRegKey failed",
        v6);
    }
    goto LABEL_38;
  }
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  v6 = RegOpenKeyExW(hKey, v8, 0, 0x2001Fu, &phkResult);
  if ( !v6 )
  {
    v12 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)a2 + 32);
    v6 = RegSetValueExW(phkResult, L"Launcher", 0, 1u, v12, 2 * *((_DWORD *)a2 + 12) + 2);
    if ( !v6 )
    {
      v6 = 0;
      goto LABEL_38;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_27;
    }
    if ( v6 > 0 )
      v9 = (unsigned __int16)v6 | 0x80070000;
    else
      v9 = v6;
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 30;
    goto LABEL_26;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    if ( v6 > 0 )
      v9 = (unsigned __int16)v6 | 0x80070000;
    else
      v9 = v6;
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 29;
LABEL_26:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_a72faf600b5a37edaf0216851c61dae8_Traceguids, v10, v9);
  }
LABEL_27:
  if ( v6 > 0 )
    v6 = (unsigned __int16)v6 | 0x80070000;
LABEL_38:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007c274  mov     rax, rsp
0x18007c277  mov     [rax+8], rbx
0x18007c27b  mov     [rax+20h], rsi
0x18007c27f  push    rdi
0x18007c280  sub     rsp, 30h
0x18007c284  cmp     qword ptr [rdx+10h], 0
0x18007c289  mov     rdi, rdx
0x18007c28c  mov     qword ptr [rax+10h], 0
0x18007c294  mov     qword ptr [rax+18h], 0
0x18007c29c  jnz     short loc_18007C2F3
0x18007c29e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c2a5  lea     rax, WPP_GLOBAL_Control
0x18007c2ac  cmp     rcx, rax
0x18007c2af  jz      short loc_18007C2E9
0x18007c2b1  test    byte ptr [rcx+1Ch], 8
0x18007c2b5  jz      short loc_18007C2E9
0x18007c2b7  cmp     byte ptr [rcx+19h], 2
0x18007c2bb  jb      short loc_18007C2E9
0x18007c2bd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007c2c2  mov     edx, 1Ah
0x18007c2c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c2ce  lea     r8, WPP_a72faf600b5a37edaf0216851c61dae8_Traceguids
0x18007c2d5  mov     r9d, eax
0x18007c2d8  mov     dword ptr [rsp+38h+phkResult], 80070057h
0x18007c2e0  mov     rcx, [rcx+10h]
0x18007c2e4  call    WPP_SF_Dd
0x18007c2e9  mov     ebx, 80070057h
0x18007c2ee  jmp     loc_18007C4B4
0x18007c2f3  cmp     qword ptr [rdx+30h], 0
0x18007c2f8  jnz     short loc_18007C325
0x18007c2fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c301  lea     rax, WPP_GLOBAL_Control
0x18007c308  cmp     rcx, rax
0x18007c30b  jz      short loc_18007C2E9
0x18007c30d  test    byte ptr [rcx+1Ch], 8
0x18007c311  jz      short loc_18007C2E9
0x18007c313  cmp     byte ptr [rcx+19h], 2
0x18007c317  jb      short loc_18007C2E9
0x18007c319  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007c31e  mov     edx, 1Bh
0x18007c323  jmp     short loc_18007C2C7
0x18007c325  lea     r8, [rsp+38h+hKey]; HKEY *
0x18007c32a  mov     edx, 2001Fh; unsigned int
0x18007c32f  call    ?OpenTopLevelRegKey@CResourceTypeManager@@KAJHKPEAPEAUHKEY__@@@Z; CResourceTypeManager::OpenTopLevelRegKey(int,ulong,HKEY__ * *)
0x18007c334  mov     ebx, eax
0x18007c336  test    eax, eax
0x18007c338  jns     short loc_18007C39E
0x18007c33a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c341  lea     rax, WPP_GLOBAL_Control
0x18007c348  cmp     rcx, rax
0x18007c34b  jz      loc_18007C4B4
0x18007c351  test    byte ptr [rcx+1Ch], 8
0x18007c355  jz      loc_18007C4B4
0x18007c35b  cmp     byte ptr [rcx+19h], 2
0x18007c35f  jb      loc_18007C4B4
0x18007c365  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007c36a  lea     rcx, aOpentoplevelre; "OpenTopLevelRegKey failed"
0x18007c371  mov     [rsp+38h+cbData], ebx
0x18007c375  mov     [rsp+38h+phkResult], rcx
0x18007c37a  lea     r8, WPP_a72faf600b5a37edaf0216851c61dae8_Traceguids
0x18007c381  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c388  mov     edx, 1Ch
0x18007c38d  mov     r9d, eax
0x18007c390  mov     rcx, [rcx+10h]
0x18007c394  call    WPP_SF_DsD
0x18007c399  jmp     loc_18007C4B4
0x18007c39e  mov     rcx, rdi
0x18007c3a1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c3a6  lea     rcx, [rsp+38h+arg_10]
0x18007c3ab  mov     r9d, 2001Fh; samDesired
0x18007c3b1  mov     [rsp+38h+phkResult], rcx; phkResult
0x18007c3b6  xor     r8d, r8d; ulOptions
0x18007c3b9  mov     rcx, [rsp+38h+hKey]; hKey
0x18007c3be  mov     rdx, rax; lpSubKey
0x18007c3c1  call    cs:__imp_RegOpenKeyExW
0x18007c3c7  mov     ebx, eax
0x18007c3c9  test    eax, eax
0x18007c3cb  jz      short loc_18007C435
0x18007c3cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c3d4  lea     rax, WPP_GLOBAL_Control
0x18007c3db  mov     edi, 80070000h
0x18007c3e0  cmp     rcx, rax
0x18007c3e3  jz      short loc_18007C426
0x18007c3e5  test    byte ptr [rcx+1Ch], 8
0x18007c3e9  jz      short loc_18007C426
0x18007c3eb  cmp     byte ptr [rcx+19h], 2
0x18007c3ef  jb      short loc_18007C426
0x18007c3f1  test    ebx, ebx
0x18007c3f3  jg      short loc_18007C3F9
0x18007c3f5  mov     esi, ebx
0x18007c3f7  jmp     short loc_18007C3FE
0x18007c3f9  movzx   esi, bx
0x18007c3fc  or      esi, edi
0x18007c3fe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007c403  mov     edx, 1Dh
0x18007c408  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c40f  lea     r8, WPP_a72faf600b5a37edaf0216851c61dae8_Traceguids
0x18007c416  mov     r9d, eax
0x18007c419  mov     dword ptr [rsp+38h+phkResult], esi
0x18007c41d  mov     rcx, [rcx+10h]
0x18007c421  call    WPP_SF_Dd
0x18007c426  test    ebx, ebx
0x18007c428  jle     loc_18007C4B4
0x18007c42e  movzx   ebx, bx
0x18007c431  or      ebx, edi
0x18007c433  jmp     short loc_18007C4B4
0x18007c435  lea     rcx, [rdi+20h]
0x18007c439  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c43e  mov     ecx, [rdi+30h]
0x18007c441  lea     rdx, aLauncher; "Launcher"
0x18007c448  mov     r9d, 1; dwType
0x18007c44e  xor     r8d, r8d; Reserved
0x18007c451  lea     ecx, ds:2[rcx*2]
0x18007c458  mov     [rsp+38h+cbData], ecx; cbData
0x18007c45c  mov     rcx, [rsp+38h+arg_10]; hKey
0x18007c461  mov     [rsp+38h+phkResult], rax; lpData
0x18007c466  call    cs:__imp_RegSetValueExW
0x18007c46c  mov     ebx, eax
0x18007c46e  test    eax, eax
0x18007c470  jz      short loc_18007C4B2
0x18007c472  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c479  lea     rax, WPP_GLOBAL_Control
0x18007c480  mov     edi, 80070000h
0x18007c485  cmp     rcx, rax
0x18007c488  jz      short loc_18007C426
0x18007c48a  test    byte ptr [rcx+1Ch], 8
0x18007c48e  jz      short loc_18007C426
0x18007c490  cmp     byte ptr [rcx+19h], 2
0x18007c494  jb      short loc_18007C426
0x18007c496  test    ebx, ebx
0x18007c498  jg      short loc_18007C49E
0x18007c49a  mov     esi, ebx
0x18007c49c  jmp     short loc_18007C4A3
0x18007c49e  movzx   esi, bx
0x18007c4a1  or      esi, edi
0x18007c4a3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007c4a8  mov     edx, 1Eh
0x18007c4ad  jmp     loc_18007C408
0x18007c4b2  xor     ebx, ebx
0x18007c4b4  mov     rcx, [rsp+38h+hKey]; hKey
0x18007c4b9  test    rcx, rcx
0x18007c4bc  jz      short loc_18007C4C4
0x18007c4be  call    cs:__imp_RegCloseKey
0x18007c4c4  mov     rcx, [rsp+38h+arg_10]; hKey
0x18007c4c9  test    rcx, rcx
0x18007c4cc  jz      short loc_18007C4D4
0x18007c4ce  call    cs:__imp_RegCloseKey
0x18007c4d4  mov     rsi, [rsp+38h+arg_18]
0x18007c4d9  mov     eax, ebx
0x18007c4db  mov     rbx, [rsp+38h+arg_0]
0x18007c4e0  add     rsp, 30h
0x18007c4e4  pop     rdi
0x18007c4e5  retn
```
