# CacheSettings::CacheSettings(IUnknown *)

- ea: `0x1800c5cb4`
- end: `0x1800c5f75`
- name: `??0CacheSettings@@QEAA@PEAUIUnknown@@@Z`
- size: `705`
- prototype: `CacheSettings *__fastcall(CacheSettings *__hidden this, struct IUnknown *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c73a0`
- `0x1800c7ab0`

## callees

- `0x18000ce04`
- `0x180079770`
- `0x180089c18`
- `0x1800c5cb4`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c5d94`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c5de0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c5e27`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c5e6a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c5ead`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c5d94`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c5de0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c5e27`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c5e6a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c5ead`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5ed2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5ed2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5d5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5d5c`

## string_xrefs

- `0x1800c5d23`: `CacheSettings::TilingMethod`
- `0x1800c5d4e`: `Software\Policies\Microsoft\Windows NT\Terminal Services\Caching`

## pseudocode

```c
CacheSettings *__fastcall CacheSettings::CacheSettings(CacheSettings *this, struct IUnknown *a2)
{
  BOOL v3; // ebx
  int v4; // ebx
  int v5; // edi
  int v6; // esi
  int v7; // r14d
  int v8; // r15d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  __int64 v12; // [rsp+58h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+40h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int Data; // [rsp+B0h] [rbp+50h] BYREF
  int v16; // [rsp+B8h] [rbp+58h] BYREF

  *(_DWORD *)this = 4194368;
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 50;
  hKey = 0;
  v3 = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  v16 = 0;
  v12 = 0;
  if ( a2
    && ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IRDPCollection,
         &v12) >= 0 )
  {
    v3 = (*(int (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v12 + 40LL))(
           v12,
           L"CacheSettings::TilingMethod",
           &v16) >= 0;
  }
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\Caching",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"TileWidth", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data - 4 <= 0xFFFB )
      *(_WORD *)this = Data;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"TileHeight", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data - 4 <= 0xFFFB )
      *((_WORD *)this + 1) = Data;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"TilingMethod", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data < 3 )
      *((_DWORD *)this + 2) = Data;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"HashingMethod", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && !Data )
      *((_DWORD *)this + 3) = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"OrderedRatioBasedInsertionPercentage", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && Data <= 0x5A )
    {
      *((_DWORD *)this + 4) = Data;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v3 )
    *((_DWORD *)this + 2) = v16;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v4 = *((_DWORD *)this + 4);
    v5 = *((_DWORD *)this + 3);
    v6 = *((_DWORD *)this + 2);
    v7 = *((unsigned __int16 *)this + 1);
    v8 = *(unsigned __int16 *)this;
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_079e9475bbdc3c843102650a611d530d_Traceguids,
      CurrentThreadActivityIdPrefix,
      v8,
      v7,
      v6,
      v5,
      v4);
  }
  TCntPtr<IRdpVCMgr>::SafeRelease(&v12);
  return this;
}

```

## disassembly

```asm
0x1800c5cb4  push    rbp
0x1800c5cb6  push    rbx
0x1800c5cb7  push    rsi
0x1800c5cb8  push    rdi
0x1800c5cb9  push    r12
0x1800c5cbb  push    r14
0x1800c5cbd  push    r15
0x1800c5cbf  mov     rbp, rsp
0x1800c5cc2  sub     rsp, 60h
0x1800c5cc6  xor     edi, edi
0x1800c5cc8  mov     dword ptr [rcx], 400040h
0x1800c5cce  mov     [rcx+8], rdi
0x1800c5cd2  mov     r9, rdx
0x1800c5cd5  mov     dword ptr [rcx+10h], 32h ; '2'
0x1800c5cdc  mov     r12, rcx
0x1800c5cdf  mov     [rbp+hKey], rdi
0x1800c5ce3  mov     ebx, edi
0x1800c5ce5  mov     [rbp+Type], edi
0x1800c5ce8  lea     r15d, [rdi+1]
0x1800c5cec  mov     [rbp+cbData], edi
0x1800c5cef  mov     [rbp+Data], edi
0x1800c5cf2  mov     [rbp+arg_18], edi
0x1800c5cf5  mov     [rbp+var_8], rdi
0x1800c5cf9  test    rdx, rdx
0x1800c5cfc  jz      short loc_1800C5D3C
0x1800c5cfe  mov     rax, [rdx]
0x1800c5d01  lea     r8, [rbp+var_8]
0x1800c5d05  lea     rdx, IID_IRDPCollection
0x1800c5d0c  mov     rcx, r9
0x1800c5d0f  mov     rax, [rax]
0x1800c5d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5d17  test    eax, eax
0x1800c5d19  js      short loc_1800C5D3C
0x1800c5d1b  mov     rcx, [rbp+var_8]
0x1800c5d1f  lea     r8, [rbp+arg_18]
0x1800c5d23  lea     rdx, aCachesettingsT; "CacheSettings::TilingMethod"
0x1800c5d2a  mov     rax, [rcx]
0x1800c5d2d  mov     rax, [rax+28h]
0x1800c5d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5d36  test    eax, eax
0x1800c5d38  cmovns  ebx, r15d
0x1800c5d3c  lea     rax, [rbp+hKey]
0x1800c5d40  mov     r9d, 20019h; samDesired
0x1800c5d46  xor     r8d, r8d; ulOptions
0x1800c5d49  mov     [rsp+60h+phkResult], rax; phkResult
0x1800c5d4e  lea     rdx, aSoftwarePolici_5; "Software\\Policies\\Microsoft\\Windows "...
0x1800c5d55  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c5d5c  call    cs:__imp_RegOpenKeyExW
0x1800c5d62  test    eax, eax
0x1800c5d64  jnz     loc_1800C5EC9
0x1800c5d6a  mov     rcx, [rbp+hKey]; hKey
0x1800c5d6e  lea     esi, [rax+4]
0x1800c5d71  lea     rax, [rbp+cbData]
0x1800c5d75  mov     [rbp+cbData], esi
0x1800c5d78  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1800c5d7d  lea     r9, [rbp+Type]; lpType
0x1800c5d81  lea     rax, [rbp+Data]
0x1800c5d85  xor     r8d, r8d; lpReserved
0x1800c5d88  lea     rdx, aTilewidth; "TileWidth"
0x1800c5d8f  mov     [rsp+60h+phkResult], rax; lpData
0x1800c5d94  call    cs:__imp_RegQueryValueExW
0x1800c5d9a  mov     r14d, 0FFFBh
0x1800c5da0  test    eax, eax
0x1800c5da2  jnz     short loc_1800C5DB9
0x1800c5da4  cmp     [rbp+Type], esi
0x1800c5da7  jnz     short loc_1800C5DB9
0x1800c5da9  mov     ecx, [rbp+Data]
0x1800c5dac  lea     eax, [rcx-4]
0x1800c5daf  cmp     eax, r14d
0x1800c5db2  ja      short loc_1800C5DB9
0x1800c5db4  mov     [r12], cx
0x1800c5db9  mov     rcx, [rbp+hKey]; hKey
0x1800c5dbd  lea     rax, [rbp+cbData]
0x1800c5dc1  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1800c5dc6  lea     r9, [rbp+Type]; lpType
0x1800c5dca  lea     rax, [rbp+Data]
0x1800c5dce  mov     [rbp+cbData], esi
0x1800c5dd1  xor     r8d, r8d; lpReserved
0x1800c5dd4  mov     [rsp+60h+phkResult], rax; lpData
0x1800c5dd9  lea     rdx, aTileheight; "TileHeight"
0x1800c5de0  call    cs:__imp_RegQueryValueExW
0x1800c5de6  test    eax, eax
0x1800c5de8  jnz     short loc_1800C5E00
0x1800c5dea  cmp     [rbp+Type], esi
0x1800c5ded  jnz     short loc_1800C5E00
0x1800c5def  mov     ecx, [rbp+Data]
0x1800c5df2  lea     eax, [rcx-4]
0x1800c5df5  cmp     eax, r14d
0x1800c5df8  ja      short loc_1800C5E00
0x1800c5dfa  mov     [r12+2], cx
0x1800c5e00  mov     rcx, [rbp+hKey]; hKey
0x1800c5e04  lea     rax, [rbp+cbData]
0x1800c5e08  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1800c5e0d  lea     r9, [rbp+Type]; lpType
0x1800c5e11  lea     rax, [rbp+Data]
0x1800c5e15  mov     [rbp+cbData], esi
0x1800c5e18  xor     r8d, r8d; lpReserved
0x1800c5e1b  mov     [rsp+60h+phkResult], rax; lpData
0x1800c5e20  lea     rdx, aTilingmethod; "TilingMethod"
0x1800c5e27  call    cs:__imp_RegQueryValueExW
0x1800c5e2d  test    eax, eax
0x1800c5e2f  jnz     short loc_1800C5E43
0x1800c5e31  cmp     [rbp+Type], esi
0x1800c5e34  jnz     short loc_1800C5E43
0x1800c5e36  mov     eax, [rbp+Data]
0x1800c5e39  cmp     eax, 3
0x1800c5e3c  jnb     short loc_1800C5E43
0x1800c5e3e  mov     [r12+8], eax
0x1800c5e43  mov     rcx, [rbp+hKey]; hKey
0x1800c5e47  lea     rax, [rbp+cbData]
0x1800c5e4b  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1800c5e50  lea     r9, [rbp+Type]; lpType
0x1800c5e54  lea     rax, [rbp+Data]
0x1800c5e58  mov     [rbp+cbData], esi
0x1800c5e5b  xor     r8d, r8d; lpReserved
0x1800c5e5e  mov     [rsp+60h+phkResult], rax; lpData
0x1800c5e63  lea     rdx, aHashingmethod; "HashingMethod"
0x1800c5e6a  call    cs:__imp_RegQueryValueExW
0x1800c5e70  test    eax, eax
0x1800c5e72  jnz     short loc_1800C5E86
0x1800c5e74  cmp     [rbp+Type], esi
0x1800c5e77  jnz     short loc_1800C5E86
0x1800c5e79  mov     eax, [rbp+Data]
0x1800c5e7c  cmp     eax, r15d
0x1800c5e7f  jnb     short loc_1800C5E86
0x1800c5e81  mov     [r12+0Ch], eax
0x1800c5e86  mov     rcx, [rbp+hKey]; hKey
0x1800c5e8a  lea     rax, [rbp+cbData]
0x1800c5e8e  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1800c5e93  lea     r9, [rbp+Type]; lpType
0x1800c5e97  lea     rax, [rbp+Data]
0x1800c5e9b  mov     [rbp+cbData], esi
0x1800c5e9e  xor     r8d, r8d; lpReserved
0x1800c5ea1  mov     [rsp+60h+phkResult], rax; lpData
0x1800c5ea6  lea     rdx, aOrderedratioba; "OrderedRatioBasedInsertionPercentage"
0x1800c5ead  call    cs:__imp_RegQueryValueExW
0x1800c5eb3  test    eax, eax
0x1800c5eb5  jnz     short loc_1800C5EC9
0x1800c5eb7  cmp     [rbp+Type], esi
0x1800c5eba  jnz     short loc_1800C5EC9
0x1800c5ebc  mov     eax, [rbp+Data]
0x1800c5ebf  cmp     eax, 5Ah ; 'Z'
0x1800c5ec2  ja      short loc_1800C5EC9
0x1800c5ec4  mov     [r12+10h], eax
0x1800c5ec9  mov     rcx, [rbp+hKey]; hKey
0x1800c5ecd  test    rcx, rcx
0x1800c5ed0  jz      short loc_1800C5ED8
0x1800c5ed2  call    cs:__imp_RegCloseKey
0x1800c5ed8  test    ebx, ebx
0x1800c5eda  jz      short loc_1800C5EE4
0x1800c5edc  mov     eax, [rbp+arg_18]
0x1800c5edf  mov     [r12+8], eax
0x1800c5ee4  mov     rax, cs:WPP_GLOBAL_Control
0x1800c5eeb  lea     rcx, WPP_GLOBAL_Control
0x1800c5ef2  cmp     rax, rcx
0x1800c5ef5  jz      short loc_1800C5F5A
0x1800c5ef7  test    dword ptr [rax+1Ch], 100h
0x1800c5efe  jz      short loc_1800C5F5A
0x1800c5f00  cmp     byte ptr [rax+19h], 5
0x1800c5f04  jb      short loc_1800C5F5A
0x1800c5f06  mov     ebx, [r12+10h]
0x1800c5f0b  mov     edi, [r12+0Ch]
0x1800c5f10  mov     esi, [r12+8]
0x1800c5f15  movzx   r14d, word ptr [r12+2]
0x1800c5f1b  movzx   r15d, word ptr [r12]
0x1800c5f20  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800c5f25  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5f2c  lea     r8, WPP_079e9475bbdc3c843102650a611d530d_Traceguids
0x1800c5f33  mov     [rsp+60h+var_20], ebx
0x1800c5f37  mov     edx, 0Ah
0x1800c5f3c  mov     [rsp+60h+var_28], edi
0x1800c5f40  mov     r9d, eax
0x1800c5f43  mov     [rsp+60h+var_30], esi
0x1800c5f47  mov     rcx, [rcx+10h]
0x1800c5f4b  mov     dword ptr [rsp+60h+lpcbData], r14d
0x1800c5f50  mov     dword ptr [rsp+60h+phkResult], r15d
0x1800c5f55  call    WPP_SF_DDDDDD
0x1800c5f5a  lea     rcx, [rbp+var_8]
0x1800c5f5e  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800c5f63  mov     rax, r12
0x1800c5f66  add     rsp, 60h
0x1800c5f6a  pop     r15
0x1800c5f6c  pop     r14
0x1800c5f6e  pop     r12
0x1800c5f70  pop     rdi
0x1800c5f71  pop     rsi
0x1800c5f72  pop     rbx
0x1800c5f73  pop     rbp
0x1800c5f74  retn
```
