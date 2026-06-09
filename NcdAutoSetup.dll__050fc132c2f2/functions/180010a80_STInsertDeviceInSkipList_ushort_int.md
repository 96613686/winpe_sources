# STInsertDeviceInSkipList(ushort *,int)

- ea: `0x180010a80`
- end: `0x180010c1f`
- name: `?STInsertDeviceInSkipList@@YAJPEAGH@Z`
- size: `415`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800094c8`

## callees

- `0x18000a644`
- `0x18000a66c`
- `0x180010a80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010b37`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010b37`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010bb2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010bb2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010af6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010af6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010bc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010c06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010bc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010c06`

## pseudocode

```c
__int64 __fastcall STInsertDeviceInSkipList(LPCWSTR lpValueName, int a2)
{
  LSTATUS v4; // ebx
  HKEY v5; // rdi
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD Data; // [rsp+80h] [rbp+40h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  Data = 1;
  hKey = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\NcdAutoSetup\\DeviceSetting\\SkipList",
         0,
         0x2001Fu,
         &hKey);
  if ( !v4 )
  {
    v5 = hKey;
    if ( a2 )
    {
      Type = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        ++Data;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_16;
      v7 = 85;
    }
    else
    {
      Data = -1;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      {
LABEL_16:
        Type = Data;
        v4 = RegSetValueExW(v5, lpValueName, 0, 4u, (const BYTE *)&Type, 4u);
        if ( v5 )
          RegCloseKey(v5);
        goto LABEL_18;
      }
      v7 = 86;
    }
    WPP_SF_S(v6[2], v7, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids, lpValueName);
    goto LABEL_16;
  }
LABEL_18:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  if ( v4 > 0 )
    return (unsigned __int16)v4 | 0x80070000;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180010a80  mov     [rsp-28h+arg_0], rbx
0x180010a85  push    rbp
0x180010a86  push    rsi
0x180010a87  push    rdi
0x180010a88  push    r14
0x180010a8a  push    r15
0x180010a8c  mov     rbp, rsp
0x180010a8f  sub     rsp, 40h
0x180010a93  mov     r14d, edx
0x180010a96  mov     rsi, rcx
0x180010a99  mov     rcx, cs:WPP_GLOBAL_Control
0x180010aa0  lea     r15, WPP_GLOBAL_Control
0x180010aa7  cmp     rcx, r15
0x180010aaa  jz      short loc_180010AC7
0x180010aac  test    byte ptr [rcx+1Ch], 20h
0x180010ab0  jz      short loc_180010AC7
0x180010ab2  mov     rcx, [rcx+10h]
0x180010ab6  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x180010abd  mov     edx, 54h ; 'T'
0x180010ac2  call    WPP_SF_
0x180010ac7  lea     rax, [rbp+hKey]
0x180010acb  mov     [rbp+Data], 1
0x180010ad2  mov     r9d, 2001Fh; samDesired
0x180010ad8  mov     [rsp+40h+phkResult], rax; phkResult
0x180010add  xor     r8d, r8d; ulOptions
0x180010ae0  mov     [rbp+hKey], 0
0x180010ae8  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180010aef  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010af6  call    cs:__imp_RegOpenKeyExW
0x180010afc  mov     ebx, eax
0x180010afe  test    eax, eax
0x180010b00  jnz     loc_180010BC8
0x180010b06  mov     rdi, [rbp+hKey]
0x180010b0a  lea     ebx, [rax+4]
0x180010b0d  test    r14d, r14d
0x180010b10  jz      short loc_180010B62
0x180010b12  mov     [rbp+Type], eax
0x180010b15  lea     r9, [rbp+Type]; lpType
0x180010b19  lea     rax, [rbp+cbData]
0x180010b1d  mov     [rbp+cbData], ebx
0x180010b20  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180010b25  xor     r8d, r8d; lpReserved
0x180010b28  lea     rax, [rbp+Data]
0x180010b2c  mov     rdx, rsi; lpValueName
0x180010b2f  mov     rcx, rdi; hKey
0x180010b32  mov     [rsp+40h+phkResult], rax; lpData
0x180010b37  call    cs:__imp_RegQueryValueExW
0x180010b3d  test    eax, eax
0x180010b3f  jnz     short loc_180010B49
0x180010b41  cmp     [rbp+Type], ebx
0x180010b44  jnz     short loc_180010B49
0x180010b46  inc     [rbp+Data]
0x180010b49  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b50  cmp     rcx, r15
0x180010b53  jz      short loc_180010B93
0x180010b55  test    byte ptr [rcx+1Ch], 8
0x180010b59  jz      short loc_180010B93
0x180010b5b  mov     edx, 55h ; 'U'
0x180010b60  jmp     short loc_180010B80
0x180010b62  mov     [rbp+Data], 0FFFFFFFFh
0x180010b69  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b70  cmp     rcx, r15
0x180010b73  jz      short loc_180010B93
0x180010b75  test    byte ptr [rcx+1Ch], 8
0x180010b79  jz      short loc_180010B93
0x180010b7b  mov     edx, 56h ; 'V'
0x180010b80  mov     rcx, [rcx+10h]
0x180010b84  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x180010b8b  mov     r9, rsi
0x180010b8e  call    WPP_SF_S
0x180010b93  mov     eax, [rbp+Data]
0x180010b96  mov     r9d, ebx; dwType
0x180010b99  mov     [rbp+Type], eax
0x180010b9c  xor     r8d, r8d; Reserved
0x180010b9f  lea     rax, [rbp+Type]
0x180010ba3  mov     dword ptr [rsp+40h+lpcbData], ebx; cbData
0x180010ba7  mov     rdx, rsi; lpValueName
0x180010baa  mov     [rsp+40h+phkResult], rax; lpData
0x180010baf  mov     rcx, rdi; hKey
0x180010bb2  call    cs:__imp_RegSetValueExW
0x180010bb8  mov     ebx, eax
0x180010bba  test    rdi, rdi
0x180010bbd  jz      short loc_180010BCA
0x180010bbf  mov     rcx, rdi; hKey
0x180010bc2  call    cs:__imp_RegCloseKey
0x180010bc8  xor     edi, edi
0x180010bca  mov     rcx, cs:WPP_GLOBAL_Control
0x180010bd1  cmp     rcx, r15
0x180010bd4  jz      short loc_180010BF1
0x180010bd6  test    byte ptr [rcx+1Ch], 20h
0x180010bda  jz      short loc_180010BF1
0x180010bdc  mov     rcx, [rcx+10h]
0x180010be0  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x180010be7  mov     edx, 57h ; 'W'
0x180010bec  call    WPP_SF_
0x180010bf1  test    ebx, ebx
0x180010bf3  jle     short loc_180010BFE
0x180010bf5  movzx   ebx, bx
0x180010bf8  or      ebx, 80070000h
0x180010bfe  test    rdi, rdi
0x180010c01  jz      short loc_180010C0C
0x180010c03  mov     rcx, rdi; hKey
0x180010c06  call    cs:__imp_RegCloseKey
0x180010c0c  mov     eax, ebx
0x180010c0e  mov     rbx, [rsp+40h+arg_0]
0x180010c13  add     rsp, 40h
0x180010c17  pop     r15
0x180010c19  pop     r14
0x180010c1b  pop     rdi
0x180010c1c  pop     rsi
0x180010c1d  pop     rbp
0x180010c1e  retn
```
