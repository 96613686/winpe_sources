# ReadSecurityDescriptorFromRegistry

- ea: `0x180002d10`
- end: `0x180002f75`
- name: `ReadSecurityDescriptorFromRegistry`
- size: `613`
- prototype: `unsigned int __fastcall(const WCHAR *, const WCHAR *, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002200`
- `0x18000be70`

## callees

- `0x180002d10`
- `0x180002f80`
- `0x180008ff0`
- `0x180009130`
- `0x180009850`
- `0x18000a19a`
- `0x1800118a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002dd4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002dd4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002e2b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002e2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002ed0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002ed0`

## pseudocode

```c
unsigned int __fastcall ReadSecurityDescriptorFromRegistry(const WCHAR *a1, const WCHAR *a2, __int64 a3, __int64 a4)
{
  PVOID *v7; // rcx
  unsigned int result; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  unsigned int valid; // eax
  DWORD Type; // [rsp+30h] [rbp-FF8h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-FF4h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-FF0h] BYREF
  WCHAR Data[2008]; // [rsp+40h] [rbp-FE8h] BYREF

  hKey = 0;
  Type = 0;
  memset_0(Data, 0, 0xFA4u);
  cbData = 4002;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 && a2 && a4 )
  {
    result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a1, 0, 0x20019u, &hKey);
    v9 = result;
    if ( result )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return result;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_34;
      v10 = 23;
      v11 = result;
LABEL_32:
      WPP_SF_L(v7[2], v10, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v11);
      goto LABEL_33;
    }
    v12 = RegQueryValueExW(hKey, a2, 0, &Type, (LPBYTE)Data, &cbData);
    v9 = v12;
    if ( v12 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_25;
      v14 = 24;
      v15 = v12;
    }
    else
    {
      v15 = Type;
      if ( Type != 1 || ((unsigned __int8)cbData & (unsigned __int8)Type) != 0 )
      {
        v9 = 13;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_25;
        v14 = 25;
      }
      else
      {
        valid = ConvertSDDLToValidSecurityDescriptor(Data);
        v9 = valid;
        if ( !valid )
          goto LABEL_25;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_25;
        v14 = 26;
        v15 = valid;
      }
    }
    WPP_SF_L(v13[2], v14, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v15);
LABEL_25:
    if ( !RegCloseKey(hKey) )
    {
LABEL_33:
      v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_34:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
        WPP_SF_L(v7[2], 28, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v9);
      return v9;
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_34;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
      goto LABEL_33;
    }
    return v9;
  }
  v9 = 87;
  if ( v7 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v7 + 28) & 4) == 0 )
      goto LABEL_34;
    v10 = 22;
    v11 = 87;
    goto LABEL_32;
  }
  return v9;
}

```

## disassembly

```asm
0x180002d10  push    rbx
0x180002d12  push    rbp
0x180002d13  push    rsi
0x180002d14  push    rdi
0x180002d15  push    r14
0x180002d17  mov     eax, 1000h
0x180002d1c  call    _alloca_probe
0x180002d21  sub     rsp, rax
0x180002d24  mov     rax, cs:__security_cookie
0x180002d2b  xor     rax, rsp
0x180002d2e  mov     [rsp+1028h+var_38], rax
0x180002d36  xor     eax, eax
0x180002d38  mov     esi, r8d
0x180002d3b  mov     rbp, rdx
0x180002d3e  mov     [rsp+1028h+hKey], rax
0x180002d43  mov     rbx, rcx
0x180002d46  mov     [rsp+1028h+Type], eax
0x180002d4a  xor     edx, edx; Val
0x180002d4c  lea     rcx, [rsp+1028h+Data]; void *
0x180002d51  mov     r8d, 0FA4h; Size
0x180002d57  mov     rdi, r9
0x180002d5a  call    memset_0
0x180002d5f  mov     [rsp+1028h+cbData], 0FA2h
0x180002d67  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d6e  lea     r14, WPP_GLOBAL_Control
0x180002d75  cmp     rcx, r14
0x180002d78  jz      short loc_180002D9C
0x180002d7a  test    byte ptr [rcx+1Ch], 8
0x180002d7e  jz      short loc_180002D9C
0x180002d80  mov     rcx, [rcx+10h]
0x180002d84  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180002d8b  mov     edx, 15h
0x180002d90  call    WPP_SF_
0x180002d95  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d9c  test    rbx, rbx
0x180002d9f  jz      loc_180002F03
0x180002da5  test    rbp, rbp
0x180002da8  jz      loc_180002F03
0x180002dae  test    rdi, rdi
0x180002db1  jz      loc_180002F03
0x180002db7  lea     rax, [rsp+1028h+hKey]
0x180002dbc  mov     r9d, 20019h; samDesired
0x180002dc2  xor     r8d, r8d; ulOptions
0x180002dc5  mov     [rsp+1028h+phkResult], rax; phkResult
0x180002dca  mov     rdx, rbx; lpSubKey
0x180002dcd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002dd4  call    cs:__imp_RegOpenKeyExW
0x180002dda  mov     ebx, eax
0x180002ddc  test    eax, eax
0x180002dde  jz      short loc_180002E07
0x180002de0  mov     rcx, cs:WPP_GLOBAL_Control
0x180002de7  cmp     rcx, r14
0x180002dea  jz      loc_180002F57
0x180002df0  test    byte ptr [rcx+1Ch], 4
0x180002df4  jz      loc_180002F32
0x180002dfa  mov     edx, 17h
0x180002dff  mov     r9d, eax
0x180002e02  jmp     loc_180002F1B
0x180002e07  mov     rcx, [rsp+1028h+hKey]; hKey
0x180002e0c  lea     rax, [rsp+1028h+cbData]
0x180002e11  mov     [rsp+1028h+lpcbData], rax; lpcbData
0x180002e16  lea     r9, [rsp+1028h+Type]; lpType
0x180002e1b  lea     rax, [rsp+1028h+Data]
0x180002e20  xor     r8d, r8d; lpReserved
0x180002e23  mov     rdx, rbp; lpValueName
0x180002e26  mov     [rsp+1028h+phkResult], rax; lpData
0x180002e2b  call    cs:__imp_RegQueryValueExW
0x180002e31  mov     ebx, eax
0x180002e33  test    eax, eax
0x180002e35  jz      short loc_180002E57
0x180002e37  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e3e  cmp     rcx, r14
0x180002e41  jz      loc_180002ECB
0x180002e47  test    byte ptr [rcx+1Ch], 4
0x180002e4b  jz      short loc_180002ECB
0x180002e4d  mov     edx, 18h
0x180002e52  mov     r9d, eax
0x180002e55  jmp     short loc_180002EBB
0x180002e57  mov     r9d, [rsp+1028h+Type]
0x180002e5c  cmp     r9d, 1
0x180002e60  jnz     short loc_180002E9F
0x180002e62  mov     eax, [rsp+1028h+cbData]
0x180002e66  test    r9b, al
0x180002e69  jnz     short loc_180002E9F
0x180002e6b  mov     r9, rdi
0x180002e6e  lea     rcx, [rsp+1028h+Data]; StringSecurityDescriptor
0x180002e73  xor     r8d, r8d
0x180002e76  mov     edx, esi
0x180002e78  call    ConvertSDDLToValidSecurityDescriptor
0x180002e7d  mov     ebx, eax
0x180002e7f  test    eax, eax
0x180002e81  jz      short loc_180002ECB
0x180002e83  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e8a  cmp     rcx, r14
0x180002e8d  jz      short loc_180002ECB
0x180002e8f  test    byte ptr [rcx+1Ch], 4
0x180002e93  jz      short loc_180002ECB
0x180002e95  mov     edx, 1Ah
0x180002e9a  mov     r9d, eax
0x180002e9d  jmp     short loc_180002EBB
0x180002e9f  mov     ebx, 0Dh
0x180002ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x180002eab  cmp     rcx, r14
0x180002eae  jz      short loc_180002ECB
0x180002eb0  test    byte ptr [rcx+1Ch], 4
0x180002eb4  jz      short loc_180002ECB
0x180002eb6  mov     edx, 19h
0x180002ebb  mov     rcx, [rcx+10h]
0x180002ebf  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180002ec6  call    WPP_SF_L
0x180002ecb  mov     rcx, [rsp+1028h+hKey]; hKey
0x180002ed0  call    cs:__imp_RegCloseKey
0x180002ed6  test    eax, eax
0x180002ed8  jz      short loc_180002F2B
0x180002eda  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ee1  cmp     rcx, r14
0x180002ee4  jz      short loc_180002F55
0x180002ee6  test    byte ptr [rcx+1Ch], 4
0x180002eea  jz      short loc_180002F32
0x180002eec  mov     rcx, [rcx+10h]
0x180002ef0  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180002ef7  mov     edx, 1Bh
0x180002efc  call    WPP_SF_
0x180002f01  jmp     short loc_180002F2B
0x180002f03  mov     ebx, 57h ; 'W'
0x180002f08  cmp     rcx, r14
0x180002f0b  jz      short loc_180002F55
0x180002f0d  test    byte ptr [rcx+1Ch], 4
0x180002f11  jz      short loc_180002F32
0x180002f13  mov     edx, 16h
0x180002f18  mov     r9d, ebx
0x180002f1b  mov     rcx, [rcx+10h]
0x180002f1f  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180002f26  call    WPP_SF_L
0x180002f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f32  cmp     rcx, r14
0x180002f35  jz      short loc_180002F55
0x180002f37  test    byte ptr [rcx+1Ch], 8
0x180002f3b  jz      short loc_180002F55
0x180002f3d  mov     rcx, [rcx+10h]
0x180002f41  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180002f48  mov     edx, 1Ch
0x180002f4d  mov     r9d, ebx
0x180002f50  call    WPP_SF_L
0x180002f55  mov     eax, ebx
0x180002f57  mov     rcx, [rsp+1028h+var_38]
0x180002f5f  xor     rcx, rsp; StackCookie
0x180002f62  call    __security_check_cookie
0x180002f67  add     rsp, 1000h
0x180002f6e  pop     r14
0x180002f70  pop     rdi
0x180002f71  pop     rsi
0x180002f72  pop     rbp
0x180002f73  pop     rbx
0x180002f74  retn
```
