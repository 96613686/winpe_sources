# KamNcbEnabled

- ea: `0x180016350`
- end: `0x18001649d`
- name: `KamNcbEnabled`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800159b8`

## callees

- `0x180016350`
- `0x180016d98`
- `0x18001bfb8`
- `0x18001c500`
- `0x18001d09c`
- `0x180020350`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800163f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800163f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016455`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016455`

## pseudocode

```c
char KamNcbEnabled()
{
  unsigned int Integer2; // eax
  unsigned int v2; // ebx
  PVOID *v3; // rcx
  bool v4; // bl
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids);
  }
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( (unsigned __int8)IsOSServerSku() )
  {
    RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Server", 0, 0x20019u, &hKey);
    Integer2 = GetInteger2(hKey, L"ClientExperienceEnabled", 0);
    v2 = Integer2;
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, Integer2);
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      RegCloseKey(hKey);
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    v4 = v2 != 0;
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 && *((_BYTE *)v3 + 25) >= 6u )
      WPP_SF_c(v3[2], 13, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids);
    return v4;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids);
    }
    return 1;
  }
}

```

## disassembly

```asm
0x180016350  mov     [rsp+arg_8], rbx
0x180016355  push    rbp
0x180016356  sub     rsp, 30h
0x18001635a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016361  lea     rbp, WPP_GLOBAL_Control
0x180016368  cmp     rcx, rbp
0x18001636b  jz      short loc_18001638E
0x18001636d  test    byte ptr [rcx+1Ch], 1
0x180016371  jz      short loc_18001638E
0x180016373  cmp     byte ptr [rcx+19h], 6
0x180016377  jb      short loc_18001638E
0x180016379  mov     rcx, [rcx+10h]
0x18001637d  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x180016384  mov     edx, 0Ah
0x180016389  call    WPP_SF_
0x18001638e  mov     [rsp+38h+hKey], 0FFFFFFFFFFFFFFFFh
0x180016397  call    IsOSServerSku
0x18001639c  test    al, al
0x18001639e  jnz     short loc_1800163D4
0x1800163a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163a7  cmp     rcx, rbp
0x1800163aa  jz      short loc_1800163CD
0x1800163ac  test    byte ptr [rcx+1Ch], 1
0x1800163b0  jz      short loc_1800163CD
0x1800163b2  cmp     byte ptr [rcx+19h], 6
0x1800163b6  jb      short loc_1800163CD
0x1800163b8  mov     rcx, [rcx+10h]
0x1800163bc  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x1800163c3  mov     edx, 0Bh
0x1800163c8  call    WPP_SF_
0x1800163cd  mov     al, 1
0x1800163cf  jmp     loc_180016492
0x1800163d4  lea     rax, [rsp+38h+hKey]
0x1800163d9  mov     r9d, 20019h; samDesired
0x1800163df  xor     r8d, r8d; ulOptions
0x1800163e2  mov     [rsp+38h+phkResult], rax; phkResult
0x1800163e7  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800163ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800163f5  call    cs:__imp_RegOpenKeyExW
0x1800163fb  mov     rcx, [rsp+38h+hKey]
0x180016400  lea     rdx, aClientexperien; "ClientExperienceEnabled"
0x180016407  xor     r8d, r8d
0x18001640a  call    GetInteger2
0x18001640f  mov     ebx, eax
0x180016411  mov     rcx, cs:WPP_GLOBAL_Control
0x180016418  cmp     rcx, rbp
0x18001641b  jz      short loc_180016448
0x18001641d  test    byte ptr [rcx+1Ch], 1
0x180016421  jz      short loc_180016448
0x180016423  cmp     byte ptr [rcx+19h], 5
0x180016427  jb      short loc_180016448
0x180016429  mov     rcx, [rcx+10h]
0x18001642d  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x180016434  mov     edx, 0Ch
0x180016439  mov     r9d, eax
0x18001643c  call    WPP_SF_d
0x180016441  mov     rcx, cs:WPP_GLOBAL_Control
0x180016448  cmp     [rsp+38h+hKey], 0FFFFFFFFFFFFFFFFh
0x18001644e  jz      short loc_180016462
0x180016450  mov     rcx, [rsp+38h+hKey]; hKey
0x180016455  call    cs:__imp_RegCloseKey
0x18001645b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016462  test    ebx, ebx
0x180016464  setnz   bl
0x180016467  cmp     rcx, rbp
0x18001646a  jz      short loc_180016490
0x18001646c  test    byte ptr [rcx+1Ch], 1
0x180016470  jz      short loc_180016490
0x180016472  cmp     byte ptr [rcx+19h], 6
0x180016476  jb      short loc_180016490
0x180016478  mov     rcx, [rcx+10h]
0x18001647c  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x180016483  mov     edx, 0Dh
0x180016488  mov     r9b, bl
0x18001648b  call    WPP_SF_c
0x180016490  mov     al, bl
0x180016492  mov     rbx, [rsp+38h+arg_8]
0x180016497  add     rsp, 30h
0x18001649b  pop     rbp
0x18001649c  retn
```
