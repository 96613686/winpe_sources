# CleanOldDevicesFromDeviceCache

- ea: `0x14004e1cc`
- end: `0x14004e5bb`
- name: `CleanOldDevicesFromDeviceCache`
- size: `1007`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14004c3cc`

## callees

- `0x140001b8c`
- `0x140004b30`
- `0x140004b98`
- `0x140004ce4`
- `0x14004e094`
- `0x14004e1cc`
- `0x140065d14`
- `0x140065dbc`
- `0x14006fb00`
- `0x140070554`
- `0x1400708c4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14004e539`
- `ADVAPI32!RegCloseKey` at `0x14004e58d`
- `ADVAPI32!RegCloseKey` at `0x14004e539`
- `ADVAPI32!RegCloseKey` at `0x14004e58d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14004e2ee`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14004e2ee`
- `ADVAPI32!RegEnumKeyExW` at `0x14004e409`
- `ADVAPI32!RegEnumKeyExW` at `0x14004e409`
- `KERNEL32!GetLastError` at `0x14004e25f`
- `KERNEL32!GetLastError` at `0x14004e25f`
- `msvcrt!swscanf` at `0x14004e4c4`
- `msvcrt!swscanf` at `0x14004e4c4`

## string_xrefs

- `0x14004e23c`: `Software\Microsoft\Fax\Devices Cache`
- `0x14004e327`: `Software\Microsoft\Fax\Devices Cache`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CleanOldDevicesFromDeviceCache(__int64 a1)
{
  HKEY v2; // r15
  DWORD LastError; // eax
  DWORD v4; // ebx
  WCHAR *v6; // r14
  unsigned int v7; // esi
  unsigned __int64 v8; // rcx
  DWORD i; // ecx
  HKEY v10; // rax
  HKEY v11; // r13
  unsigned __int64 *RegistryBinary; // r12
  _DWORD *j; // rdi
  __int64 v14; // rax
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-94h] BYREF
  unsigned __int64 *v16; // [rsp+68h] [rbp-90h] BYREF
  HKEY v17; // [rsp+70h] [rbp-88h]
  WCHAR *v18; // [rsp+78h] [rbp-80h]
  void *Block[3]; // [rsp+80h] [rbp-78h] BYREF
  unsigned __int64 v20; // [rsp+98h] [rbp-60h]
  HKEY v21; // [rsp+A0h] [rbp-58h]
  exception *v22; // [rsp+A8h] [rbp-50h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+100h] [rbp+8h] BYREF
  DWORD cchName; // [rsp+108h] [rbp+10h] BYREF
  unsigned int v25; // [rsp+110h] [rbp+18h] BYREF
  DWORD v26; // [rsp+118h] [rbp+20h]

  v25 = 0;
  cchName = 0;
  memset(Block, 0, sizeof(Block));
  cbMaxValueLen = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
  }
  v2 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Devices Cache", 0, 0x20019u);
  v17 = v2;
  if ( v2 )
  {
    v6 = 0;
    cbMaxSubKeyLen = 0;
    v7 = RegQueryInfoKeyW(v2, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, &cbMaxValueLen, 0, 0);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          166,
          (unsigned int)&WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids,
          v7,
          (__int64)L"Software\\Microsoft\\Fax\\Devices Cache");
      }
    }
    else
    {
      v8 = 2LL * ++cbMaxSubKeyLen;
      if ( v8 > 0xFFFFFFFF )
      {
        v7 = 534;
      }
      else
      {
        v6 = (WCHAR *)pMemAlloc((unsigned int)v8);
        v18 = v6;
        if ( v6 )
        {
          v20 = a1 - 26784000000000LL;
          for ( i = 0; ; i = v26 + 1 )
          {
            v26 = i;
            cchName = cbMaxSubKeyLen;
            if ( RegEnumKeyExW(v2, i, v6, &cchName, 0, 0, 0, 0) )
              break;
            v10 = OpenRegistryKey(v2, v6, 0, 0x20019u);
            v11 = v10;
            v21 = v10;
            if ( v10 )
            {
              RegistryBinary = (unsigned __int64 *)GetRegistryBinary(v10, L"LastDetected", (DWORD *)&v16);
              v16 = RegistryBinary;
              if ( !RegistryBinary || *RegistryBinary < v20 )
              {
                if ( swscanf(v6, L"%lx", &v25) == 1 )
                {
                  try
                  {
                    std::vector<unsigned long>::push_back(Block, &v25);
                  }
                  catch ( exception *v22 )
                  {
                    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v14 = (*(__int64 (__fastcall **)(exception *))(*(_QWORD *)v22 + 8LL))(v22);
                      WPP_SF_s(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        169,
                        &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids,
                        v14);
                    }
                    SetLastError(8u);
                    pMemFree(v16);
                    RegCloseKey(v21);
                    v2 = v17;
                    v6 = v18;
                    goto LABEL_43;
                  }
                }
                else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 170, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
                }
              }
              pMemFree(RegistryBinary);
              RegCloseKey(v11);
            }
            else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v6);
            }
          }
          for ( j = Block[1]; Block[0] != j; Block[1] = j )
          {
            v25 = *--j;
            DeleteCacheEntry(v25);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
          }
          v7 = 8;
        }
      }
    }
LABEL_43:
    pMemFree(v6);
    RegCloseKey(v2);
    if ( Block[0] )
      operator delete(Block[0]);
    return v7;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        165,
        (unsigned int)&WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids,
        LastError,
        (__int64)L"Software\\Microsoft\\Fax\\Devices Cache");
    }
    return v4;
  }
}

```

## disassembly

```asm
0x14004e1cc  mov     rax, rsp
0x14004e1cf  push    rbx
0x14004e1d0  push    rsi
0x14004e1d1  push    rdi
0x14004e1d2  push    r12
0x14004e1d4  push    r13
0x14004e1d6  push    r14
0x14004e1d8  push    r15
0x14004e1da  sub     rsp, 0C0h
0x14004e1e1  mov     r12, rcx
0x14004e1e4  xor     ebx, ebx
0x14004e1e6  mov     [rax+18h], ebx
0x14004e1e9  mov     [rax+10h], ebx
0x14004e1ec  xorps   xmm0, xmm0
0x14004e1ef  movdqu  xmmword ptr [rax-78h], xmm0
0x14004e1f4  mov     [rax-68h], rbx
0x14004e1f8  mov     [rsp+0F8h+cbMaxValueLen], ebx
0x14004e1fc  lea     r13, WPP_GLOBAL_Control
0x14004e203  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e20a  mov     dil, 4
0x14004e20d  cmp     rcx, r13
0x14004e210  jz      short loc_14004E233
0x14004e212  test    [rcx+1Ch], dil
0x14004e216  jz      short loc_14004E233
0x14004e218  cmp     byte ptr [rcx+19h], 5
0x14004e21c  jb      short loc_14004E233
0x14004e21e  mov     edx, 0A4h
0x14004e223  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004e22a  mov     rcx, [rcx+10h]
0x14004e22e  call    WPP_SF_
0x14004e233  mov     r9d, 20019h
0x14004e239  xor     r8d, r8d
0x14004e23c  lea     rsi, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x14004e243  mov     rdx, rsi
0x14004e246  mov     rcx, 0FFFFFFFF80000002h
0x14004e24d  call    OpenRegistryKey
0x14004e252  mov     r15, rax
0x14004e255  mov     [rsp+0F8h+var_88], rax
0x14004e25a  test    rax, rax
0x14004e25d  jnz     short loc_14004E2A4
0x14004e25f  call    cs:__imp_GetLastError
0x14004e265  mov     ebx, eax
0x14004e267  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e26e  cmp     rcx, r13
0x14004e271  jz      short loc_14004E29D
0x14004e273  test    [rcx+1Ch], dil
0x14004e277  jz      short loc_14004E29D
0x14004e279  cmp     byte ptr [rcx+19h], 3
0x14004e27d  jb      short loc_14004E29D
0x14004e27f  mov     edx, 0A5h
0x14004e284  mov     [rsp+0F8h+lpcSubKeys], rsi
0x14004e289  mov     r9d, eax
0x14004e28c  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004e293  mov     rcx, [rcx+10h]
0x14004e297  call    WPP_SF_DS
0x14004e29c  nop
0x14004e29d  mov     eax, ebx
0x14004e29f  jmp     loc_14004E5A8
0x14004e2a4  mov     r14, rbx
0x14004e2a7  mov     [rsp+0F8h+cbMaxSubKeyLen], ebx
0x14004e2ae  mov     [rsp+0F8h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x14004e2b3  mov     [rsp+0F8h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x14004e2b8  lea     rax, [rsp+0F8h+cbMaxValueLen]
0x14004e2bd  mov     [rsp+0F8h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x14004e2c2  mov     [rsp+0F8h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x14004e2c7  mov     [rsp+0F8h+lpcValues], rbx; lpcValues
0x14004e2cc  mov     [rsp+0F8h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x14004e2d1  lea     rax, [rsp+0F8h+cbMaxSubKeyLen]
0x14004e2d9  mov     [rsp+0F8h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x14004e2de  mov     [rsp+0F8h+lpcSubKeys], rbx; lpcSubKeys
0x14004e2e3  xor     r9d, r9d; lpReserved
0x14004e2e6  xor     r8d, r8d; lpcchClass
0x14004e2e9  xor     edx, edx; lpClass
0x14004e2eb  mov     rcx, r15; hKey
0x14004e2ee  call    cs:__imp_RegQueryInfoKeyW
0x14004e2f4  mov     esi, eax
0x14004e2f6  mov     [rsp+0F8h+var_98], eax
0x14004e2fa  test    eax, eax
0x14004e2fc  jz      short loc_14004E34B
0x14004e2fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e305  cmp     rcx, r13
0x14004e308  jz      loc_14004E582
0x14004e30e  test    [rcx+1Ch], dil
0x14004e312  jz      loc_14004E582
0x14004e318  cmp     byte ptr [rcx+19h], 2
0x14004e31c  jb      loc_14004E582
0x14004e322  mov     edx, 0A6h
0x14004e327  lea     rax, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x14004e32e  mov     [rsp+0F8h+lpcSubKeys], rax
0x14004e333  mov     r9d, esi
0x14004e336  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004e33d  mov     rcx, [rcx+10h]
0x14004e341  call    WPP_SF_DS
0x14004e346  jmp     loc_14004E582
0x14004e34b  mov     eax, [rsp+0F8h+cbMaxSubKeyLen]
0x14004e352  inc     eax
0x14004e354  mov     [rsp+0F8h+cbMaxSubKeyLen], eax
0x14004e35b  mov     ecx, eax
0x14004e35d  add     rcx, rcx
0x14004e360  mov     eax, 0FFFFFFFFh
0x14004e365  cmp     rcx, rax
0x14004e368  ja      loc_14004E57D
0x14004e36e  mov     ecx, ecx; dwBytes
0x14004e370  call    pMemAlloc
0x14004e375  mov     r14, rax
0x14004e378  mov     [rsp+0F8h+var_80], rax
0x14004e37d  test    rax, rax
0x14004e380  jnz     short loc_14004E3B9
0x14004e382  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e389  cmp     rcx, r13
0x14004e38c  jz      short loc_14004E3AF
0x14004e38e  test    [rcx+1Ch], dil
0x14004e392  jz      short loc_14004E3AF
0x14004e394  cmp     byte ptr [rcx+19h], 2
0x14004e398  jb      short loc_14004E3AF
0x14004e39a  mov     edx, 0A7h
0x14004e39f  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004e3a6  mov     rcx, [rcx+10h]
0x14004e3aa  call    WPP_SF_
0x14004e3af  mov     esi, 8
0x14004e3b4  jmp     loc_14004E582
0x14004e3b9  mov     rax, 0FFFFE7A3DD31C000h
0x14004e3c3  add     rax, r12
0x14004e3c6  mov     [rsp+0F8h+var_60], rax
0x14004e3ce  mov     ecx, ebx
0x14004e3d0  mov     eax, [rsp+0F8h+cbMaxSubKeyLen]
0x14004e3d7  mov     [rsp+0F8h+arg_18], ecx
0x14004e3de  mov     [rsp+0F8h+cchName], eax
0x14004e3e5  mov     [rsp+0F8h+lpcValues], rbx; lpftLastWriteTime
0x14004e3ea  mov     [rsp+0F8h+lpcbMaxClassLen], rbx; lpcchClass
0x14004e3ef  mov     [rsp+0F8h+lpcbMaxSubKeyLen], rbx; lpClass
0x14004e3f4  mov     [rsp+0F8h+lpcSubKeys], rbx; lpReserved
0x14004e3f9  lea     r9, [rsp+0F8h+cchName]; lpcchName
0x14004e401  mov     r8, r14; lpName
0x14004e404  mov     edx, ecx; dwIndex
0x14004e406  mov     rcx, r15; hKey
0x14004e409  call    cs:__imp_RegEnumKeyExW
0x14004e40f  test    eax, eax
0x14004e411  jnz     loc_14004E54D
0x14004e417  mov     r9d, 20019h
0x14004e41d  xor     r8d, r8d
0x14004e420  mov     rdx, r14
0x14004e423  mov     rcx, r15
0x14004e426  call    OpenRegistryKey
0x14004e42b  mov     r13, rax
0x14004e42e  mov     [rsp+0F8h+var_58], rax
0x14004e436  test    rax, rax
0x14004e439  jnz     short loc_14004E483
0x14004e43b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e442  lea     rax, WPP_GLOBAL_Control
0x14004e449  cmp     rcx, rax
0x14004e44c  jz      loc_14004E53F
0x14004e452  test    [rcx+1Ch], dil
0x14004e456  jz      loc_14004E53F
0x14004e45c  cmp     byte ptr [rcx+19h], 3
0x14004e460  jb      loc_14004E53F
0x14004e466  mov     edx, 0A8h
0x14004e46b  mov     r9, r14
0x14004e46e  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004e475  mov     rcx, [rcx+10h]
0x14004e479  call    WPP_SF_S
0x14004e47e  jmp     loc_14004E53F
0x14004e483  lea     r8, [rsp+0F8h+var_90]
0x14004e488  lea     rdx, aLastdetected; "LastDetected"
0x14004e48f  mov     rcx, r13; hKey
0x14004e492  call    GetRegistryBinary
0x14004e497  mov     r12, rax
0x14004e49a  mov     [rsp+0F8h+var_90], rax
0x14004e49f  test    rax, rax
0x14004e4a2  jz      short loc_14004E4B2
0x14004e4a4  mov     rax, [rsp+0F8h+var_60]
0x14004e4ac  cmp     [r12], rax
0x14004e4b0  jnb     short loc_14004E52E
0x14004e4b2  lea     r8, [rsp+0F8h+arg_10]
0x14004e4ba  lea     rdx, aLx; "%lx"
0x14004e4c1  mov     rcx, r14; Buffer
0x14004e4c4  call    cs:__imp_swscanf
0x14004e4ca  cmp     eax, 1
0x14004e4cd  jnz     short loc_14004E4FA
0x14004e4cf  lea     rdx, [rsp+0F8h+arg_10]
0x14004e4d7  lea     rcx, [rsp+0F8h+Block]
0x14004e4df  call    ?push_back@?$vector@KV?$allocator@K@std@@@std@@QEAAXAEBK@Z; std::vector<ulong>::push_back(ulong const &)
0x14004e4e4  nop
0x14004e4e5  jmp     short loc_14004E52E
0x14004e4e7  mov     r15, [rsp+0F8h+var_88]
0x14004e4ec  mov     esi, [rsp+0F8h+var_98]
0x14004e4f0  mov     r14, [rsp+0F8h+var_80]
0x14004e4f5  jmp     loc_14004E582
0x14004e4fa  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e501  lea     rax, WPP_GLOBAL_Control
0x14004e508  cmp     rcx, rax
0x14004e50b  jz      short loc_14004E52E
0x14004e50d  test    [rcx+1Ch], dil
0x14004e511  jz      short loc_14004E52E
0x14004e513  cmp     byte ptr [rcx+19h], 3
0x14004e517  jb      short loc_14004E52E
0x14004e519  mov     edx, 0AAh
0x14004e51e  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004e525  mov     rcx, [rcx+10h]
0x14004e529  call    WPP_SF_
0x14004e52e  mov     rcx, r12; lpMem
0x14004e531  call    pMemFree
0x14004e536  mov     rcx, r13; hKey
0x14004e539  call    cs:__imp_RegCloseKey
0x14004e53f  mov     ecx, [rsp+0F8h+arg_18]
0x14004e546  inc     ecx
0x14004e548  jmp     loc_14004E3D0
0x14004e54d  mov     rdi, [rsp+0F8h+var_70]
0x14004e555  cmp     [rsp+0F8h+Block], rdi
0x14004e55d  jz      short loc_14004E57B
0x14004e55f  add     rdi, 0FFFFFFFFFFFFFFFCh
0x14004e563  mov     ecx, [rdi]
0x14004e565  mov     [rsp+0F8h+arg_10], ecx
0x14004e56c  call    DeleteCacheEntry
0x14004e571  mov     [rsp+0F8h+var_70], rdi
0x14004e579  jmp     short loc_14004E555
0x14004e57b  jmp     short loc_14004E582
0x14004e57d  mov     esi, 216h
0x14004e582  mov     rcx, r14; lpMem
0x14004e585  call    pMemFree
0x14004e58a  mov     rcx, r15; hKey
0x14004e58d  call    cs:__imp_RegCloseKey
0x14004e593  nop
0x14004e594  mov     rcx, [rsp+0F8h+Block]; Block
0x14004e59c  test    rcx, rcx
0x14004e59f  jz      short loc_14004E5A6
0x14004e5a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14004e5a6  mov     eax, esi
0x14004e5a8  add     rsp, 0C0h
0x14004e5af  pop     r15
0x14004e5b1  pop     r14
0x14004e5b3  pop     r13
0x14004e5b5  pop     r12
0x14004e5b7  pop     rdi
0x14004e5b8  pop     rsi
0x14004e5b9  pop     rbx
0x14004e5ba  retn
```
