# MobileDeviceCenterMatchingPlugin(int *,void *,_DB *,ulong,ulong,ushort const *,void *)

- ea: `0x18000e210`
- end: `0x18000e421`
- name: `?MobileDeviceCenterMatchingPlugin@@YAHPEAHPEAXPEAU_DB@@KKPEBG1@Z`
- size: `529`
- prototype: `__int64 __fastcall(int *, void *, struct _DB *, unsigned int, unsigned int, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001cf0`
- `0x18000e210`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000e3c8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000e3c8`
- `KERNEL32!SystemTimeToFileTime` at `0x18000e3b2`
- `KERNEL32!SystemTimeToFileTime` at `0x18000e3b2`
- `KERNEL32!GetSystemTime` at `0x18000e3a2`
- `KERNEL32!GetSystemTime` at `0x18000e3a2`
- `ADVAPI32!RegEnumKeyW` at `0x18000e35a`
- `ADVAPI32!RegEnumKeyW` at `0x18000e35a`
- `ADVAPI32!RegQueryValueExW` at `0x18000e302`
- `ADVAPI32!RegQueryValueExW` at `0x18000e302`
- `ADVAPI32!RegCloseKey` at `0x18000e30f`
- `ADVAPI32!RegCloseKey` at `0x18000e370`
- `ADVAPI32!RegCloseKey` at `0x18000e381`
- `ADVAPI32!RegCloseKey` at `0x18000e30f`
- `ADVAPI32!RegCloseKey` at `0x18000e370`
- `ADVAPI32!RegCloseKey` at `0x18000e381`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e26f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e2c4`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e26f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e2c4`

## pseudocode

```c
__int64 __fastcall MobileDeviceCenterMatchingPlugin(
        int *a1,
        void *a2,
        struct _DB *a3,
        __int64 a4,
        unsigned int a5,
        const unsigned __int16 *a6)
{
  unsigned __int64 v6; // rdi
  DWORD v8; // esi
  DWORD i; // edx
  LSTATUS v10; // ebx
  DWORD v11; // r8d
  unsigned __int64 v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // rsi
  int v15; // eax
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-C4h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  struct _SYSTEMTIME Data; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  v6 = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  *a1 = 0;
  if ( !RegOpenKeyExW(
          HKEY_CLASSES_ROOT,
          L"Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\SyncMgr\\HandlerInstances",
          0,
          8u,
          &hKey) )
  {
    v8 = 0;
    for ( i = 0; !RegEnumKeyW(hKey, i, SubKey, 0x104u); i = v8 )
    {
      cbData = 0;
      Type = 0;
      phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      Data = 0;
      if ( RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &phkResult) )
      {
        if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
          RegCloseKey(phkResult);
        break;
      }
      cbData = 16;
      v10 = RegQueryValueExW(phkResult, L"SyncTime", 0, &Type, (LPBYTE)&Data, &cbData);
      RegCloseKey(phkResult);
      if ( v10 || Type != 3 )
        break;
      v11 = cbData;
      v12 = 0;
      ++v8;
      while ( (--v11 & 0x80000000) == 0 )
        v12 = *((unsigned __int8 *)&Data.wYear + v11) + (v12 << 8);
      if ( v12 <= v6 )
        v12 = v6;
      v6 = v12;
    }
  }
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  if ( v6 )
  {
    phkResult = 0;
    Data = 0;
    GetSystemTime(&Data);
    SystemTimeToFileTime(&Data, (LPFILETIME)&phkResult);
    if ( !a6
      || (v13 = HIDWORD(phkResult), v14 = (unsigned int)phkResult, v15 = _o__wtoi(a6), v15 <= 0)
      || ((v14 | (v13 << 32)) - v6) / 0xC92A69C000LL <= v15 )
    {
      *a1 = 1;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000e210  push    rbp
0x18000e212  push    rbx
0x18000e213  push    rsi
0x18000e214  push    rdi
0x18000e215  push    r14
0x18000e217  push    r15
0x18000e219  lea     rbp, [rsp-188h]
0x18000e221  sub     rsp, 288h
0x18000e228  mov     rax, cs:__security_cookie
0x18000e22f  xor     rax, rsp
0x18000e232  mov     [rbp+1B0h+var_40], rax
0x18000e239  mov     r14, [rbp+1B0h+arg_28]
0x18000e240  lea     rax, [rsp+2B0h+hKey]
0x18000e245  xor     edi, edi
0x18000e247  mov     [rsp+2B0h+hKey], 0FFFFFFFFFFFFFFFFh
0x18000e250  mov     r15, rcx
0x18000e253  mov     [rcx], edi
0x18000e255  xor     r8d, r8d; ulOptions
0x18000e258  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18000e25d  lea     rdx, SubKey; "Local Settings\\Software\\Microsoft\\Wi"...
0x18000e264  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000e26b  lea     r9d, [rdi+8]; samDesired
0x18000e26f  call    cs:__imp_RegOpenKeyExW
0x18000e275  test    eax, eax
0x18000e277  jnz     loc_18000E376
0x18000e27d  xor     esi, esi
0x18000e27f  xor     edx, edx
0x18000e281  jmp     loc_18000E34A
0x18000e286  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18000e28b  lea     rax, [rsp+2B0h+var_280]
0x18000e290  xorps   xmm0, xmm0
0x18000e293  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18000e298  mov     r9d, 20019h; samDesired
0x18000e29e  mov     [rsp+2B0h+cbData], 0
0x18000e2a6  xor     r8d, r8d; ulOptions
0x18000e2a9  mov     [rsp+2B0h+Type], 0
0x18000e2b1  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x18000e2b6  mov     [rsp+2B0h+var_280], 0FFFFFFFFFFFFFFFFh
0x18000e2bf  movups  xmmword ptr [rsp+2B0h+Data.wYear], xmm0
0x18000e2c4  call    cs:__imp_RegOpenKeyExW
0x18000e2ca  mov     rcx, [rsp+2B0h+var_280]; hKey
0x18000e2cf  test    eax, eax
0x18000e2d1  jnz     loc_18000E36A
0x18000e2d7  lea     rax, [rsp+2B0h+cbData]
0x18000e2dc  mov     [rsp+2B0h+cbData], 10h
0x18000e2e4  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18000e2e9  lea     r9, [rsp+2B0h+Type]; lpType
0x18000e2ee  lea     rax, [rsp+2B0h+Data]
0x18000e2f3  xor     r8d, r8d; lpReserved
0x18000e2f6  lea     rdx, ValueName; "SyncTime"
0x18000e2fd  mov     [rsp+2B0h+phkResult], rax; lpData
0x18000e302  call    cs:__imp_RegQueryValueExW
0x18000e308  mov     rcx, [rsp+2B0h+var_280]; hKey
0x18000e30d  mov     ebx, eax
0x18000e30f  call    cs:__imp_RegCloseKey
0x18000e315  test    ebx, ebx
0x18000e317  jnz     short loc_18000E376
0x18000e319  cmp     [rsp+2B0h+Type], 3
0x18000e31e  jnz     short loc_18000E376
0x18000e320  mov     r8d, [rsp+2B0h+cbData]
0x18000e325  xor     edx, edx
0x18000e327  inc     esi
0x18000e329  jmp     short loc_18000E338
0x18000e32b  movzx   ecx, byte ptr [rsp+r8+2B0h+Data.wYear]
0x18000e331  shl     rdx, 8
0x18000e335  add     rdx, rcx
0x18000e338  sub     r8d, 1
0x18000e33c  jns     short loc_18000E32B
0x18000e33e  cmp     rdx, rdi
0x18000e341  cmovbe  rdx, rdi
0x18000e345  mov     rdi, rdx
0x18000e348  mov     edx, esi; dwIndex
0x18000e34a  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18000e34f  lea     r8, [rsp+2B0h+SubKey]; lpName
0x18000e354  mov     r9d, 104h; cchName
0x18000e35a  call    cs:__imp_RegEnumKeyW
0x18000e360  test    eax, eax
0x18000e362  jz      loc_18000E286
0x18000e368  jmp     short loc_18000E376
0x18000e36a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e36e  jz      short loc_18000E376
0x18000e370  call    cs:__imp_RegCloseKey
0x18000e376  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18000e37b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e37f  jz      short loc_18000E387
0x18000e381  call    cs:__imp_RegCloseKey
0x18000e387  test    rdi, rdi
0x18000e38a  jz      short loc_18000E3FD
0x18000e38c  xorps   xmm0, xmm0
0x18000e38f  mov     [rsp+2B0h+var_280], 0
0x18000e398  lea     rcx, [rsp+2B0h+Data]; lpSystemTime
0x18000e39d  movups  xmmword ptr [rsp+2B0h+Data.wYear], xmm0
0x18000e3a2  call    cs:__imp_GetSystemTime
0x18000e3a8  lea     rdx, [rsp+2B0h+var_280]; lpFileTime
0x18000e3ad  lea     rcx, [rsp+2B0h+Data]; lpSystemTime
0x18000e3b2  call    cs:__imp_SystemTimeToFileTime
0x18000e3b8  test    r14, r14
0x18000e3bb  jz      short loc_18000E3F6
0x18000e3bd  mov     ebx, dword ptr [rsp+2B0h+var_280+4]
0x18000e3c1  mov     rcx, r14
0x18000e3c4  mov     esi, dword ptr [rsp+2B0h+var_280]
0x18000e3c8  call    cs:__imp__o__wtoi
0x18000e3ce  movsxd  rcx, eax
0x18000e3d1  test    eax, eax
0x18000e3d3  jle     short loc_18000E3F6
0x18000e3d5  shl     rbx, 20h
0x18000e3d9  xor     edx, edx
0x18000e3db  or      rbx, rsi
0x18000e3de  mov     r8, 0C92A69C000h
0x18000e3e8  sub     rbx, rdi
0x18000e3eb  mov     rax, rbx
0x18000e3ee  div     r8
0x18000e3f1  cmp     rax, rcx
0x18000e3f4  ja      short loc_18000E3FD
0x18000e3f6  mov     dword ptr [r15], 1
0x18000e3fd  mov     eax, 1
0x18000e402  mov     rcx, [rbp+1B0h+var_40]
0x18000e409  xor     rcx, rsp; StackCookie
0x18000e40c  call    __security_check_cookie
0x18000e411  add     rsp, 288h
0x18000e418  pop     r15
0x18000e41a  pop     r14
0x18000e41c  pop     rdi
0x18000e41d  pop     rsi
0x18000e41e  pop     rbx
0x18000e41f  pop     rbp
0x18000e420  retn
```
