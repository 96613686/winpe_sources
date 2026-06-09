# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180009804`
- end: `0x18000994b`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009804`
- `0x180009cc4`

## callees

- `0x180004410`
- `0x180007c50`
- `0x180009804`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800098e6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800098e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009865`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009865`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009882`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800098fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000991c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009882`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800098fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000991c`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  HKEY v3; // rcx
  LSTATUS v5; // eax
  HKEY v6; // rcx
  DWORD v7; // ebx
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v3 = *this;
  phkResult = 0;
  v5 = RegOpenKeyExW(v3, a2, 0, 0x2001Fu, &phkResult);
  v6 = 0;
  v7 = v5;
  if ( !v5 )
  {
    v6 = phkResult;
    hKey[0] = phkResult;
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(v6, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v8 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      v6 = hKey[0];
      v7 = v8;
      if ( v8 )
        goto LABEL_8;
    }
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
    v9 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
    v6 = hKey[0];
    v7 = v9;
  }
LABEL_8:
  if ( v6 )
    RegCloseKey(v6);
  return v7;
}

```

## disassembly

```asm
0x180009804  mov     [rsp-8+arg_10], rbx
0x180009809  mov     [rsp-8+arg_18], rsi
0x18000980e  push    rbp
0x18000980f  push    rdi
0x180009810  push    r14
0x180009812  lea     rbp, [rsp-180h]
0x18000981a  sub     rsp, 280h
0x180009821  mov     rax, cs:__security_cookie
0x180009828  xor     rax, rsp
0x18000982b  mov     [rbp+190h+var_20], rax
0x180009832  xor     r14d, r14d
0x180009835  lea     rax, [rsp+290h+var_230]
0x18000983a  mov     rdi, rcx
0x18000983d  mov     [rsp+290h+hKey], r14
0x180009842  mov     rcx, [rcx]; hKey
0x180009845  mov     r9d, 2001Fh; samDesired
0x18000984b  xor     r8d, r8d; ulOptions
0x18000984e  mov     [rsp+290h+var_240], r14
0x180009853  mov     [rsp+290h+var_238], r14
0x180009858  mov     rsi, rdx
0x18000985b  mov     [rsp+290h+var_230], r14
0x180009860  mov     [rsp+290h+phkResult], rax; phkResult
0x180009865  call    cs:__imp_RegOpenKeyExW
0x18000986b  mov     rcx, [rsp+290h+hKey]; hKey
0x180009870  mov     ebx, eax
0x180009872  test    eax, eax
0x180009874  jnz     loc_180009917
0x18000987a  mov     ebx, r14d
0x18000987d  test    rcx, rcx
0x180009880  jz      short loc_18000988A
0x180009882  call    cs:__imp_RegCloseKey
0x180009888  mov     ebx, eax
0x18000988a  mov     rcx, [rsp+290h+var_230]
0x18000988f  mov     [rsp+290h+hKey], rcx
0x180009894  test    ebx, ebx
0x180009896  jnz     short loc_180009917
0x180009898  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x18000989d  jmp     short loc_1800098B9
0x18000989f  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800098a4  lea     rcx, [rsp+290h+hKey]; this
0x1800098a9  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800098ae  mov     rcx, [rsp+290h+hKey]; hKey
0x1800098b3  mov     ebx, eax
0x1800098b5  test    eax, eax
0x1800098b7  jnz     short loc_180009917
0x1800098b9  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800098be  mov     [rsp+290h+cchName], 100h
0x1800098c6  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800098cb  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800098d0  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x1800098d5  lea     r8, [rsp+290h+Name]; lpName
0x1800098da  mov     [rsp+290h+lpClass], r14; lpClass
0x1800098df  xor     edx, edx; dwIndex
0x1800098e1  mov     [rsp+290h+phkResult], r14; lpReserved
0x1800098e6  call    cs:__imp_RegEnumKeyExW
0x1800098ec  test    eax, eax
0x1800098ee  jz      short loc_18000989F
0x1800098f0  mov     rcx, [rsp+290h+hKey]; hKey
0x1800098f5  test    rcx, rcx
0x1800098f8  jz      short loc_180009905
0x1800098fa  call    cs:__imp_RegCloseKey
0x180009900  mov     [rsp+290h+hKey], r14
0x180009905  mov     rdx, rsi; unsigned __int16 *
0x180009908  mov     rcx, rdi; this
0x18000990b  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180009910  mov     rcx, [rsp+290h+hKey]; hKey
0x180009915  mov     ebx, eax
0x180009917  test    rcx, rcx
0x18000991a  jz      short loc_180009922
0x18000991c  call    cs:__imp_RegCloseKey
0x180009922  mov     eax, ebx
0x180009924  mov     rcx, [rbp+190h+var_20]
0x18000992b  xor     rcx, rsp; StackCookie
0x18000992e  call    __security_check_cookie
0x180009933  lea     r11, [rsp+290h+var_10]
0x18000993b  mov     rbx, [r11+30h]
0x18000993f  mov     rsi, [r11+38h]
0x180009943  mov     rsp, r11
0x180009946  pop     r14
0x180009948  pop     rdi
0x180009949  pop     rbp
0x18000994a  retn
```
