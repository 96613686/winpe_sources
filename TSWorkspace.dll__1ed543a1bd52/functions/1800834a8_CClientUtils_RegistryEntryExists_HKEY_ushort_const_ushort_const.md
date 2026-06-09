# CClientUtils::RegistryEntryExists(HKEY__ *,ushort const *,ushort const *)

- ea: `0x1800834a8`
- end: `0x180083668`
- name: `?RegistryEntryExists@CClientUtils@@KAHPEAUHKEY__@@PEBG1@Z`
- size: `448`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180083670`
- `0x1800836a0`
- `0x180083820`

## callees

- `0x18000b1d8`
- `0x1800824b4`
- `0x1800834a8`
- `0x180084594`
- `0x180084634`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800835f8`
- `ADVAPI32!RegCloseKey` at `0x1800835f8`
- `ADVAPI32!RegOpenKeyExW` at `0x18008350f`
- `ADVAPI32!RegOpenKeyExW` at `0x18008350f`
- `KERNEL32!RegEnumValueW` at `0x1800835b5`
- `KERNEL32!RegEnumValueW` at `0x1800835b5`

## pseudocode

```c
__int64 __fastcall CClientUtils::RegistryEntryExists(HKEY hKey, const unsigned __int16 *a2, char *a3)
{
  LSTATUS v5; // eax
  DWORD v6; // ebx
  char v7; // di
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v9; // r8d
  WCHAR *v10; // rax
  int v11; // r8d
  int v12; // edx
  LSTATUS v13; // edi
  unsigned int v14; // eax
  __int64 v15; // r8
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[272]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ValueName[272]; // [rsp+270h] [rbp+170h] BYREF

  hKeya = 0;
  cchValueName = 0;
  CClientUtils::MakeSubKey(SubKey, (unsigned int)a2, a2);
  v5 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &hKeya);
  v6 = 0;
  v7 = v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSl(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v9, CurrentThreadActivityIdPrefix, (__int64)SubKey, v7);
    }
  }
  else
  {
    while ( 1 )
    {
      cchValueName = 265;
      if ( RegEnumValueW(hKeya, v6, ValueName, &cchValueName, 0, 0, 0, 0) )
        break;
      v10 = ValueName;
      do
      {
        v11 = *(WCHAR *)((char *)v10 + a3 - (char *)ValueName);
        v12 = *v10 - v11;
        if ( v12 )
          break;
        ++v10;
      }
      while ( v11 );
      if ( !v12 )
      {
        v6 = 1;
        goto LABEL_14;
      }
      ++v6;
    }
    v6 = 0;
LABEL_14:
    v13 = RegCloseKey(hKeya);
    if ( v13
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v15, v14, v13);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800834a8  mov     [rsp-8+arg_10], rbx
0x1800834ad  push    rbp
0x1800834ae  push    rsi
0x1800834af  push    rdi
0x1800834b0  lea     rbp, [rsp-3A0h]
0x1800834b8  sub     rsp, 4A0h
0x1800834bf  mov     rax, cs:__security_cookie
0x1800834c6  xor     rax, rsp
0x1800834c9  mov     [rbp+3B0h+var_20], rax
0x1800834d0  mov     rsi, r8
0x1800834d3  mov     [rsp+4B0h+hKey], 0
0x1800834dc  mov     rbx, rcx
0x1800834df  mov     [rsp+4B0h+cchValueName], 0
0x1800834e7  mov     r8, rdx; unsigned __int16 *
0x1800834ea  lea     rcx, [rsp+4B0h+SubKey]; unsigned __int16 *
0x1800834ef  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x1800834f4  lea     rax, [rsp+4B0h+hKey]
0x1800834f9  mov     r9d, 20019h; samDesired
0x1800834ff  xor     r8d, r8d; ulOptions
0x180083502  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180083507  lea     rdx, [rsp+4B0h+SubKey]; lpSubKey
0x18008350c  mov     rcx, rbx; hKey
0x18008350f  call    cs:__imp_RegOpenKeyExW
0x180083515  xor     ebx, ebx
0x180083517  mov     edi, eax
0x180083519  test    eax, eax
0x18008351b  jz      short loc_180083576
0x18008351d  mov     rcx, cs:WPP_GLOBAL_Control
0x180083524  lea     rdx, WPP_GLOBAL_Control
0x18008352b  cmp     rcx, rdx
0x18008352e  jz      loc_180083644
0x180083534  test    byte ptr [rcx+1Ch], 1
0x180083538  jz      loc_180083644
0x18008353e  cmp     byte ptr [rcx+19h], 4
0x180083542  jb      loc_180083644
0x180083548  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18008354d  lea     rcx, [rsp+4B0h+SubKey]
0x180083552  mov     dword ptr [rsp+4B0h+lpType], edi
0x180083556  mov     [rsp+4B0h+phkResult], rcx
0x18008355b  lea     edx, [rbx+0Ah]
0x18008355e  mov     rcx, cs:WPP_GLOBAL_Control
0x180083565  mov     r9d, eax
0x180083568  mov     rcx, [rcx+10h]
0x18008356c  call    WPP_SF_DSl
0x180083571  jmp     loc_180083644
0x180083576  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18008357b  lea     r9, [rsp+4B0h+cchValueName]; lpcchValueName
0x180083580  mov     [rsp+4B0h+lpcbData], 0; lpcbData
0x180083589  lea     r8, [rbp+3B0h+ValueName]; lpValueName
0x180083590  mov     [rsp+4B0h+lpData], 0; lpData
0x180083599  mov     edx, ebx; dwIndex
0x18008359b  mov     [rsp+4B0h+lpType], 0; lpType
0x1800835a4  mov     [rsp+4B0h+phkResult], 0; lpReserved
0x1800835ad  mov     [rsp+4B0h+cchValueName], 109h
0x1800835b5  call    cs:__imp_RegEnumValueW
0x1800835bb  test    eax, eax
0x1800835bd  jnz     short loc_1800835F1
0x1800835bf  lea     rax, [rbp+3B0h+ValueName]
0x1800835c6  mov     rcx, rsi
0x1800835c9  sub     rcx, rax
0x1800835cc  movzx   edx, word ptr [rax]
0x1800835cf  movzx   r8d, word ptr [rax+rcx]
0x1800835d4  sub     edx, r8d
0x1800835d7  jnz     short loc_1800835E2
0x1800835d9  add     rax, 2
0x1800835dd  test    r8d, r8d
0x1800835e0  jnz     short loc_1800835CC
0x1800835e2  test    edx, edx
0x1800835e4  jz      short loc_1800835EA
0x1800835e6  inc     ebx
0x1800835e8  jmp     short loc_180083576
0x1800835ea  mov     ebx, 1
0x1800835ef  jmp     short loc_1800835F3
0x1800835f1  xor     ebx, ebx
0x1800835f3  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800835f8  call    cs:__imp_RegCloseKey
0x1800835fe  mov     edi, eax
0x180083600  test    eax, eax
0x180083602  jz      short loc_180083644
0x180083604  mov     rcx, cs:WPP_GLOBAL_Control
0x18008360b  lea     rdx, WPP_GLOBAL_Control
0x180083612  cmp     rcx, rdx
0x180083615  jz      short loc_180083644
0x180083617  test    byte ptr [rcx+1Ch], 1
0x18008361b  jz      short loc_180083644
0x18008361d  cmp     byte ptr [rcx+19h], 2
0x180083621  jb      short loc_180083644
0x180083623  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180083628  mov     rcx, cs:WPP_GLOBAL_Control
0x18008362f  mov     edx, 0Bh
0x180083634  mov     r9d, eax
0x180083637  mov     dword ptr [rsp+4B0h+phkResult], edi
0x18008363b  mov     rcx, [rcx+10h]
0x18008363f  call    WPP_SF_Dl
0x180083644  mov     eax, ebx
0x180083646  mov     rcx, [rbp+3B0h+var_20]
0x18008364d  xor     rcx, rsp; StackCookie
0x180083650  call    __security_check_cookie
0x180083655  mov     rbx, [rsp+4B0h+arg_10]
0x18008365d  add     rsp, 4A0h
0x180083664  pop     rdi
0x180083665  pop     rsi
0x180083666  pop     rbp
0x180083667  retn
```
