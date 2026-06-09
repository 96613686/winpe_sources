# CResourceTypeManager::AddResourceType(int,ResourceTypeInfo &)

- ea: `0x18007b508`
- end: `0x18007b92b`
- name: `?AddResourceType@CResourceTypeManager@@SAJHAEAUResourceTypeInfo@@@Z`
- size: `1059`
- prototype: `__int64 __fastcall(int, struct ResourceTypeInfo *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180073660`

## callees

- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x1800288b8`
- `0x180048954`
- `0x18007b508`
- `0x18007bca4`
- `0x18007c4ec`
- `0x18007c6b4`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18007b8f0`
- `ADVAPI32!RegCloseKey` at `0x18007b8ff`
- `ADVAPI32!RegCloseKey` at `0x18007b8f0`
- `ADVAPI32!RegCloseKey` at `0x18007b8ff`
- `ADVAPI32!RegSetValueExW` at `0x18007b88d`
- `ADVAPI32!RegSetValueExW` at `0x18007b88d`
- `ADVAPI32!RegCreateKeyExW` at `0x18007b78b`
- `ADVAPI32!RegCreateKeyExW` at `0x18007b78b`

## string_xrefs

- `0x18007b62f`: `OpenTopLevelRegKey failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CResourceTypeManager::AddResourceType(int a1, struct ResourceTypeInfo *a2)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v5; // rdx
  int v6; // ebx
  unsigned int v7; // eax
  unsigned int v8; // eax
  const unsigned __int16 *v9; // rax
  unsigned int v10; // eax
  const WCHAR *v11; // rax
  unsigned int v12; // esi
  unsigned int v13; // eax
  __int64 v14; // rdx
  unsigned int v15; // eax
  const BYTE *v16; // rax
  DWORD dwDisposition; // [rsp+58h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-21h] BYREF
  HKEY phkResult[2]; // [rsp+68h] [rbp-19h] BYREF
  _BYTE v21[64]; // [rsp+78h] [rbp-9h] BYREF

  phkResult[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  hKey = 0;
  phkResult[0] = 0;
  dwDisposition = 0;
  if ( !*((_QWORD *)a2 + 2) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 14;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      WPP_a72faf600b5a37edaf0216851c61dae8_Traceguids,
      CurrentThreadActivityIdPrefix,
      -2147024809);
LABEL_7:
    v6 = -2147024809;
    goto LABEL_57;
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
    v5 = 15;
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
        16,
        (unsigned int)WPP_a72faf600b5a37edaf0216851c61dae8_Traceguids,
        v7,
        (__int64)"OpenTopLevelRegKey failed",
        v6);
    }
    goto LABEL_57;
  }
  if ( std::wstring::find_last_of(a2) )
  {
    v6 = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_a72faf600b5a37edaf0216851c61dae8_Traceguids, v8);
    }
    goto LABEL_57;
  }
  if ( !a1 )
  {
    ResourceTypeInfo::ResourceTypeInfo((ResourceTypeInfo *)v21);
    v9 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    if ( CResourceTypeManager::GetResourceTypeInfo(1, v9, (struct ResourceTypeInfo *)v21) >= 0 )
    {
      v6 = -2147024891;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_a72faf600b5a37edaf0216851c61dae8_Traceguids, v10);
      }
      ResourceTypeInfo::~ResourceTypeInfo((ResourceTypeInfo *)v21);
      goto LABEL_57;
    }
    ResourceTypeInfo::~ResourceTypeInfo((ResourceTypeInfo *)v21);
  }
  v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  v6 = RegCreateKeyExW(hKey, v11, 0, 0, 0, 0x2001Fu, 0, phkResult, &dwDisposition);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_40:
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      goto LABEL_57;
    }
    if ( v6 > 0 )
      v12 = (unsigned __int16)v6 | 0x80070000;
    else
      v12 = v6;
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 19;
LABEL_39:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, WPP_a72faf600b5a37edaf0216851c61dae8_Traceguids, v13, v12);
    goto LABEL_40;
  }
  if ( dwDisposition == 1 )
  {
    v16 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)a2 + 32);
    v6 = RegSetValueExW(phkResult[0], L"Launcher", 0, 2u, v16, 2 * *((_DWORD *)a2 + 12) + 2);
    if ( !v6 )
    {
      v6 = 0;
      goto LABEL_57;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_40;
    }
    if ( v6 > 0 )
      v12 = (unsigned __int16)v6 | 0x80070000;
    else
      v12 = v6;
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 21;
    goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      WPP_a72faf600b5a37edaf0216851c61dae8_Traceguids,
      v15,
      -2147024713);
  }
  v6 = -2147024713;
LABEL_57:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult[0] )
    RegCloseKey(phkResult[0]);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007b508  mov     rax, rsp
0x18007b50b  push    rbp
0x18007b50c  push    rdi
0x18007b50d  push    r14
0x18007b50f  lea     rbp, [rax-5Fh]
0x18007b513  sub     rsp, 0C0h
0x18007b51a  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFEh
0x18007b522  mov     [rax+18h], rbx
0x18007b526  mov     [rax+20h], rsi
0x18007b52a  mov     rax, cs:__security_cookie
0x18007b531  xor     rax, rsp
0x18007b534  mov     [rbp+57h+var_20], rax
0x18007b538  mov     rdi, rdx
0x18007b53b  mov     esi, ecx
0x18007b53d  mov     [rbp+57h+hKey], 0
0x18007b545  mov     [rbp+57h+var_70], 0
0x18007b54d  mov     [rbp+57h+dwDisposition], 0
0x18007b554  cmp     qword ptr [rdx+10h], 0
0x18007b559  jnz     short loc_18007B5B0
0x18007b55b  lea     rax, WPP_GLOBAL_Control
0x18007b562  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b569  cmp     rcx, rax
0x18007b56c  jz      short loc_18007B5A6
0x18007b56e  test    byte ptr [rcx+1Ch], 8
0x18007b572  jz      short loc_18007B5A6
0x18007b574  cmp     byte ptr [rcx+19h], 2
0x18007b578  jb      short loc_18007B5A6
0x18007b57a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007b57f  mov     edx, 0Eh
0x18007b584  mov     [rsp+0D0h+dwOptions], 80070057h
0x18007b58c  mov     r9d, eax
0x18007b58f  lea     r8, WPP_a72faf600b5a37edaf0216851c61dae8_Traceguids
0x18007b596  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b59d  mov     rcx, [rcx+10h]
0x18007b5a1  call    WPP_SF_Dd
0x18007b5a6  mov     ebx, 80070057h
0x18007b5ab  jmp     loc_18007B8E7
0x18007b5b0  cmp     qword ptr [rdx+30h], 0
0x18007b5b5  jnz     short loc_18007B5E2
0x18007b5b7  lea     rax, WPP_GLOBAL_Control
0x18007b5be  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b5c5  cmp     rcx, rax
0x18007b5c8  jz      short loc_18007B5A6
0x18007b5ca  test    byte ptr [rcx+1Ch], 8
0x18007b5ce  jz      short loc_18007B5A6
0x18007b5d0  cmp     byte ptr [rcx+19h], 2
0x18007b5d4  jb      short loc_18007B5A6
0x18007b5d6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007b5db  mov     edx, 0Fh
0x18007b5e0  jmp     short loc_18007B584
0x18007b5e2  lea     r8, [rbp+57h+hKey]; HKEY *
0x18007b5e6  mov     edx, 2001Fh; unsigned int
0x18007b5eb  call    ?OpenTopLevelRegKey@CResourceTypeManager@@KAJHKPEAPEAUHKEY__@@@Z; CResourceTypeManager::OpenTopLevelRegKey(int,ulong,HKEY__ * *)
0x18007b5f0  mov     ebx, eax
0x18007b5f2  test    eax, eax
0x18007b5f4  jns     short loc_18007B65A
0x18007b5f6  lea     rax, WPP_GLOBAL_Control
0x18007b5fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b604  cmp     rcx, rax
0x18007b607  jz      loc_18007B8E7
0x18007b60d  test    byte ptr [rcx+1Ch], 8
0x18007b611  jz      loc_18007B8E7
0x18007b617  cmp     byte ptr [rcx+19h], 2
0x18007b61b  jb      loc_18007B8E7
0x18007b621  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007b626  mov     edx, 10h
0x18007b62b  mov     [rsp+0D0h+samDesired], ebx
0x18007b62f  lea     rcx, aOpentoplevelre; "OpenTopLevelRegKey failed"
0x18007b636  mov     qword ptr [rsp+0D0h+dwOptions], rcx
0x18007b63b  mov     r9d, eax
0x18007b63e  lea     r8, WPP_a72faf600b5a37edaf0216851c61dae8_Traceguids
0x18007b645  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b64c  mov     rcx, [rcx+10h]
0x18007b650  call    WPP_SF_DsD
0x18007b655  jmp     loc_18007B8E7
0x18007b65a  mov     rcx, rdi
0x18007b65d  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K@Z; std::wstring::find_last_of(ushort const *,unsigned __int64)
0x18007b662  test    rax, rax
0x18007b665  jz      short loc_18007B6C0
0x18007b667  mov     ebx, 80070057h
0x18007b66c  lea     rax, WPP_GLOBAL_Control
0x18007b673  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b67a  cmp     rcx, rax
0x18007b67d  jz      loc_18007B8E7
0x18007b683  test    byte ptr [rcx+1Ch], 1
0x18007b687  jz      loc_18007B8E7
0x18007b68d  cmp     byte ptr [rcx+19h], 2
0x18007b691  jb      loc_18007B8E7
0x18007b697  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007b69c  mov     edx, 11h
0x18007b6a1  mov     r9d, eax
0x18007b6a4  lea     r8, WPP_a72faf600b5a37edaf0216851c61dae8_Traceguids
0x18007b6ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b6b2  mov     rcx, [rcx+10h]
0x18007b6b6  call    WPP_SF_D
0x18007b6bb  jmp     loc_18007B8E7
0x18007b6c0  test    esi, esi
0x18007b6c2  jnz     loc_18007B74B
0x18007b6c8  lea     rcx, [rbp+57h+var_60]; this
0x18007b6cc  call    ??0ResourceTypeInfo@@QEAA@XZ; ResourceTypeInfo::ResourceTypeInfo(void)
0x18007b6d1  nop
0x18007b6d2  mov     rcx, rdi
0x18007b6d5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007b6da  lea     r8, [rbp+57h+var_60]; struct ResourceTypeInfo *
0x18007b6de  mov     rdx, rax; unsigned __int16 *
0x18007b6e1  lea     ecx, [rsi+1]; int
0x18007b6e4  call    ?GetResourceTypeInfo@CResourceTypeManager@@SAJHPEBGAEAUResourceTypeInfo@@@Z; CResourceTypeManager::GetResourceTypeInfo(int,ushort const *,ResourceTypeInfo &)
0x18007b6e9  test    eax, eax
0x18007b6eb  js      short loc_18007B742
0x18007b6ed  mov     ebx, 80070005h
0x18007b6f2  lea     rax, WPP_GLOBAL_Control
0x18007b6f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b700  cmp     rcx, rax
0x18007b703  jz      short loc_18007B734
0x18007b705  test    byte ptr [rcx+1Ch], 1
0x18007b709  jz      short loc_18007B734
0x18007b70b  cmp     byte ptr [rcx+19h], 2
0x18007b70f  jb      short loc_18007B734
0x18007b711  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007b716  lea     edx, [rsi+12h]
0x18007b719  mov     r9d, eax
0x18007b71c  lea     r8, WPP_a72faf600b5a37edaf0216851c61dae8_Traceguids
0x18007b723  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b72a  mov     rcx, [rcx+10h]
0x18007b72e  call    WPP_SF_D
0x18007b733  nop
0x18007b734  lea     rcx, [rbp+57h+var_60]; this
0x18007b738  call    ??1ResourceTypeInfo@@QEAA@XZ; ResourceTypeInfo::~ResourceTypeInfo(void)
0x18007b73d  jmp     loc_18007B8E7
0x18007b742  lea     rcx, [rbp+57h+var_60]; this
0x18007b746  call    ??1ResourceTypeInfo@@QEAA@XZ; ResourceTypeInfo::~ResourceTypeInfo(void)
0x18007b74b  mov     rcx, rdi
0x18007b74e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007b753  lea     rcx, [rbp+57h+dwDisposition]
0x18007b757  mov     [rsp+0D0h+lpdwDisposition], rcx; lpdwDisposition
0x18007b75c  lea     rcx, [rbp+57h+var_70]
0x18007b760  mov     [rsp+0D0h+phkResult], rcx; phkResult
0x18007b765  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18007b76e  mov     [rsp+0D0h+samDesired], 2001Fh; samDesired
0x18007b776  mov     [rsp+0D0h+dwOptions], 0; dwOptions
0x18007b77e  xor     r9d, r9d; lpClass
0x18007b781  xor     r8d, r8d; Reserved
0x18007b784  mov     rdx, rax; lpSubKey
0x18007b787  mov     rcx, [rbp+57h+hKey]; hKey
0x18007b78b  call    cs:__imp_RegCreateKeyExW
0x18007b791  mov     ebx, eax
0x18007b793  test    eax, eax
0x18007b795  jz      short loc_18007B802
0x18007b797  lea     rax, WPP_GLOBAL_Control
0x18007b79e  mov     edi, 80070000h
0x18007b7a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b7aa  cmp     rcx, rax
0x18007b7ad  jz      short loc_18007B7F0
0x18007b7af  test    byte ptr [rcx+1Ch], 8
0x18007b7b3  jz      short loc_18007B7F0
0x18007b7b5  cmp     byte ptr [rcx+19h], 2
0x18007b7b9  jb      short loc_18007B7F0
0x18007b7bb  test    ebx, ebx
0x18007b7bd  jg      short loc_18007B7C3
0x18007b7bf  mov     esi, ebx
0x18007b7c1  jmp     short loc_18007B7C8
0x18007b7c3  movzx   esi, bx
0x18007b7c6  or      esi, edi
0x18007b7c8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007b7cd  mov     edx, 13h
0x18007b7d2  mov     [rsp+0D0h+dwOptions], esi
0x18007b7d6  mov     r9d, eax
0x18007b7d9  lea     r8, WPP_a72faf600b5a37edaf0216851c61dae8_Traceguids
0x18007b7e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b7e7  mov     rcx, [rcx+10h]
0x18007b7eb  call    WPP_SF_Dd
0x18007b7f0  test    ebx, ebx
0x18007b7f2  jle     loc_18007B8E7
0x18007b7f8  movzx   ebx, bx
0x18007b7fb  or      ebx, edi
0x18007b7fd  jmp     loc_18007B8E7
0x18007b802  cmp     [rbp+57h+dwDisposition], 1
0x18007b806  jz      short loc_18007B85D
0x18007b808  lea     rax, WPP_GLOBAL_Control
0x18007b80f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b816  cmp     rcx, rax
0x18007b819  jz      short loc_18007B853
0x18007b81b  test    byte ptr [rcx+1Ch], 8
0x18007b81f  jz      short loc_18007B853
0x18007b821  cmp     byte ptr [rcx+19h], 2
0x18007b825  jb      short loc_18007B853
0x18007b827  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007b82c  mov     edx, 14h
0x18007b831  mov     [rsp+0D0h+dwOptions], 800700B7h
0x18007b839  mov     r9d, eax
0x18007b83c  lea     r8, WPP_a72faf600b5a37edaf0216851c61dae8_Traceguids
0x18007b843  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b84a  mov     rcx, [rcx+10h]
0x18007b84e  call    WPP_SF_Dd
0x18007b853  mov     ebx, 800700B7h
0x18007b858  jmp     loc_18007B8E7
0x18007b85d  lea     rcx, [rdi+20h]
0x18007b861  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007b866  mov     ecx, [rdi+30h]
0x18007b869  lea     ecx, ds:2[rcx*2]
0x18007b870  mov     [rsp+0D0h+samDesired], ecx; cbData
0x18007b874  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x18007b879  mov     r9d, 2; dwType
0x18007b87f  xor     r8d, r8d; Reserved
0x18007b882  lea     rdx, aLauncher; "Launcher"
0x18007b889  mov     rcx, [rbp+57h+var_70]; hKey
0x18007b88d  call    cs:__imp_RegSetValueExW
0x18007b893  mov     ebx, eax
0x18007b895  test    eax, eax
0x18007b897  jz      short loc_18007B8E5
0x18007b899  lea     rax, WPP_GLOBAL_Control
0x18007b8a0  mov     edi, 80070000h
0x18007b8a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b8ac  cmp     rcx, rax
0x18007b8af  jz      loc_18007B7F0
0x18007b8b5  test    byte ptr [rcx+1Ch], 8
0x18007b8b9  jz      loc_18007B7F0
0x18007b8bf  cmp     byte ptr [rcx+19h], 2
0x18007b8c3  jb      loc_18007B7F0
0x18007b8c9  test    ebx, ebx
0x18007b8cb  jg      short loc_18007B8D1
0x18007b8cd  mov     esi, ebx
0x18007b8cf  jmp     short loc_18007B8D6
0x18007b8d1  movzx   esi, bx
0x18007b8d4  or      esi, edi
0x18007b8d6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007b8db  mov     edx, 15h
0x18007b8e0  jmp     loc_18007B7D2
0x18007b8e5  xor     ebx, ebx
0x18007b8e7  mov     rcx, [rbp+57h+hKey]; hKey
0x18007b8eb  test    rcx, rcx
0x18007b8ee  jz      short loc_18007B8F6
0x18007b8f0  call    cs:__imp_RegCloseKey
0x18007b8f6  mov     rcx, [rbp+57h+var_70]; hKey
0x18007b8fa  test    rcx, rcx
0x18007b8fd  jz      short loc_18007B905
0x18007b8ff  call    cs:__imp_RegCloseKey
0x18007b905  mov     eax, ebx
0x18007b907  mov     rcx, [rbp+57h+var_20]
0x18007b90b  xor     rcx, rsp; StackCookie
0x18007b90e  call    __security_check_cookie
0x18007b913  lea     r11, [rsp+0D0h+var_10]
0x18007b91b  mov     rbx, [r11+30h]
0x18007b91f  mov     rsi, [r11+38h]
0x18007b923  mov     rsp, r11
0x18007b926  pop     r14
0x18007b928  pop     rdi
0x18007b929  pop     rbp
0x18007b92a  retn
```
