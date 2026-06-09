# IsDeviceInSkipList(ushort *)

- ea: `0x18000ef74`
- end: `0x18000f0d4`
- name: `?IsDeviceInSkipList@@YAHPEAG@Z`
- size: `352`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000fe40`

## callees

- `0x18000a644`
- `0x18000ef74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f01f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f01f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000efde`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000efde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f087`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f0be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f087`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f0be`

## pseudocode

```c
__int64 __fastcall IsDeviceInSkipList(LPCWSTR lpValueName)
{
  unsigned int v2; // edi
  HKEY v3; // rbx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  DWORD Type; // [rsp+68h] [rbp+10h] BYREF
  int Data; // [rsp+70h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  v2 = 0;
  Data = 0;
  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\NcdAutoSetup\\DeviceSetting\\SkipList",
         0,
         0x20019u,
         &hKey) )
  {
    goto LABEL_18;
  }
  v3 = hKey;
  Type = 0;
  cbData = 4;
  if ( RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
    goto LABEL_15;
  v2 = 1;
  if ( Data == -1 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v5 = 89;
LABEL_14:
      WPP_SF_(v4[2], v5, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
LABEL_15:
      v4 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v5 = 90;
      goto LABEL_14;
    }
  }
  if ( v3 )
  {
    RegCloseKey(v3);
LABEL_18:
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_(v4[2], 91, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  return v2;
}

```

## disassembly

```asm
0x18000ef74  mov     [rsp+arg_0], rbx
0x18000ef79  push    rsi
0x18000ef7a  push    rdi
0x18000ef7b  push    r14
0x18000ef7d  sub     rsp, 40h
0x18000ef81  mov     rsi, rcx
0x18000ef84  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef8b  lea     r14, WPP_GLOBAL_Control
0x18000ef92  cmp     rcx, r14
0x18000ef95  jz      short loc_18000EFB2
0x18000ef97  test    byte ptr [rcx+1Ch], 20h
0x18000ef9b  jz      short loc_18000EFB2
0x18000ef9d  mov     rcx, [rcx+10h]
0x18000efa1  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000efa8  mov     edx, 58h ; 'X'
0x18000efad  call    WPP_SF_
0x18000efb2  xor     edi, edi
0x18000efb4  lea     rax, [rsp+58h+hKey]
0x18000efb9  mov     r9d, 20019h; samDesired
0x18000efbf  mov     [rsp+58h+Data], edi
0x18000efc3  xor     r8d, r8d; ulOptions
0x18000efc6  mov     [rsp+58h+hKey], rdi
0x18000efcb  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000efd2  mov     [rsp+58h+phkResult], rax; phkResult
0x18000efd7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000efde  call    cs:__imp_RegOpenKeyExW
0x18000efe4  test    eax, eax
0x18000efe6  jnz     loc_18000F08D
0x18000efec  mov     rbx, [rsp+58h+hKey]
0x18000eff1  lea     rax, [rsp+58h+cbData]
0x18000eff6  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000effb  lea     r9, [rsp+58h+Type]; lpType
0x18000f000  lea     rax, [rsp+58h+Data]
0x18000f005  mov     [rsp+58h+Type], edi
0x18000f009  xor     r8d, r8d; lpReserved
0x18000f00c  mov     [rsp+58h+phkResult], rax; lpData
0x18000f011  mov     rdx, rsi; lpValueName
0x18000f014  mov     [rsp+58h+cbData], 4
0x18000f01c  mov     rcx, rbx; hKey
0x18000f01f  call    cs:__imp_RegQueryValueExW
0x18000f025  test    eax, eax
0x18000f027  jnz     short loc_18000F078
0x18000f029  cmp     [rsp+58h+Type], 4
0x18000f02e  jnz     short loc_18000F078
0x18000f030  cmp     [rsp+58h+Data], 0FFFFFFFFh
0x18000f035  lea     edi, [rax+1]
0x18000f038  jnz     short loc_18000F051
0x18000f03a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f041  cmp     rcx, r14
0x18000f044  jz      short loc_18000F07F
0x18000f046  test    byte ptr [rcx+1Ch], 8
0x18000f04a  jz      short loc_18000F07F
0x18000f04c  lea     edx, [rax+59h]
0x18000f04f  jmp     short loc_18000F068
0x18000f051  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f058  cmp     rcx, r14
0x18000f05b  jz      short loc_18000F07F
0x18000f05d  test    byte ptr [rcx+1Ch], 8
0x18000f061  jz      short loc_18000F07F
0x18000f063  mov     edx, 5Ah ; 'Z'
0x18000f068  mov     rcx, [rcx+10h]
0x18000f06c  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000f073  call    WPP_SF_
0x18000f078  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f07f  test    rbx, rbx
0x18000f082  jz      short loc_18000F096
0x18000f084  mov     rcx, rbx; hKey
0x18000f087  call    cs:__imp_RegCloseKey
0x18000f08d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f094  xor     ebx, ebx
0x18000f096  cmp     rcx, r14
0x18000f099  jz      short loc_18000F0B6
0x18000f09b  test    byte ptr [rcx+1Ch], 20h
0x18000f09f  jz      short loc_18000F0B6
0x18000f0a1  mov     rcx, [rcx+10h]
0x18000f0a5  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000f0ac  mov     edx, 5Bh ; '['
0x18000f0b1  call    WPP_SF_
0x18000f0b6  test    rbx, rbx
0x18000f0b9  jz      short loc_18000F0C4
0x18000f0bb  mov     rcx, rbx; hKey
0x18000f0be  call    cs:__imp_RegCloseKey
0x18000f0c4  mov     rbx, [rsp+58h+arg_0]
0x18000f0c9  mov     eax, edi
0x18000f0cb  add     rsp, 40h
0x18000f0cf  pop     r14
0x18000f0d1  pop     rdi
0x18000f0d2  pop     rsi
0x18000f0d3  retn
```
