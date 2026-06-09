# PimIMService::GetTrackedStoresFromRegistry(utl::vector<ulong,utl::allocator<ulong>> &)

- ea: `0x180007298`
- end: `0x180007465`
- name: `?GetTrackedStoresFromRegistry@PimIMService@@QEAAJAEAV?$vector@KV?$allocator@K@utl@@@utl@@@Z`
- size: `461`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004c14`
- `0x1800058d0`

## callees

- `0x180002da8`
- `0x180003edc`
- `0x180007298`
- `0x1800086a0`
- `0x18000c618`
- `0x18002120a`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007417`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007452`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007417`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007452`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007338`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800073ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007338`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800073ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800072e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800072e4`

## string_xrefs

- `0x180007381`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000743b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::GetTrackedStoresFromRegistry(__int64 a1, __int64 *a2)
{
  void **v2; // r14
  HKEY *phkResult; // rax
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r9
  LSTATUS v8; // eax
  __int64 v9; // rcx
  unsigned __int64 v10; // rbx
  __int64 v11; // rax
  unsigned __int64 v12; // rdi
  LSTATUS v13; // eax
  __int64 cbData; // [rsp+60h] [rbp+30h] BYREF
  DWORD Type; // [rsp+68h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF

  cbData = a1;
  v2 = (void **)(a2 + 1);
  a2[1] = *a2;
  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  v5 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Poom\\Indexing", 0, 0x20019u, phkResult);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    v7 = 1085;
    goto LABEL_25;
  }
  Type = 0;
  LODWORD(cbData) = 0;
  v8 = RegQueryValueExW(hKey, L"TrackedStores", 0, &Type, 0, (LPDWORD)&cbData);
  v6 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    v7 = 1096;
    goto LABEL_25;
  }
  if ( Type != 3 || !(_DWORD)cbData )
  {
    v7 = 1097;
    v6 = -2147418113;
    goto LABEL_25;
  }
  v10 = ((unsigned __int64)(unsigned int)cbData + 3) >> 2;
  if ( (cbData & 3) != 0 )
    Log_AssertionEvent(
      v9,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      1100);
  v11 = *a2;
  v12 = ((__int64)*v2 - *a2) >> 2;
  if ( v10 > v12 )
  {
    if ( (unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::reserve(a2, v10) )
    {
      memset_0(*v2, 0, 4 * (v10 - v12));
      v11 = *a2;
      goto LABEL_16;
    }
    v7 = 1101;
    v6 = -2147024882;
LABEL_25:
    Log_HREvent(
      v6,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v7);
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
LABEL_16:
  *v2 = (void *)(v11 + 4 * v10);
  v13 = RegQueryValueExW(hKey, L"TrackedStores", 0, &Type, (LPBYTE)*a2, (LPDWORD)&cbData);
  v6 = v13;
  if ( v13 )
  {
    if ( v13 > 0 )
      v6 = (unsigned __int16)v13 | 0x80070000;
    v7 = 1110;
    goto LABEL_25;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180007298  mov     [rsp-28h+cbData], rcx
0x18000729d  push    rbp
0x18000729e  push    rbx
0x18000729f  push    rsi
0x1800072a0  push    rdi
0x1800072a1  push    r14
0x1800072a3  mov     rbp, rsp
0x1800072a6  sub     rsp, 30h
0x1800072aa  mov     rax, [rdx]
0x1800072ad  lea     r14, [rdx+8]
0x1800072b1  lea     rcx, [rbp+hKey]
0x1800072b5  mov     [r14], rax
0x1800072b8  mov     rsi, rdx
0x1800072bb  mov     [rbp+hKey], 0
0x1800072c3  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x1800072c8  mov     r9d, 20019h; samDesired
0x1800072ce  mov     [rsp+30h+phkResult], rax; phkResult
0x1800072d3  xor     r8d, r8d; ulOptions
0x1800072d6  lea     rdx, SubKey; "Software\\Microsoft\\Poom\\Indexing"
0x1800072dd  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800072e4  call    cs:__imp_RegOpenKeyExW
0x1800072ea  mov     ebx, eax
0x1800072ec  test    eax, eax
0x1800072ee  jz      short loc_180007306
0x1800072f0  jle     short loc_1800072FB
0x1800072f2  movzx   ebx, ax
0x1800072f5  or      ebx, 80070000h
0x1800072fb  mov     r9d, 43Dh
0x180007301  jmp     loc_180007439
0x180007306  mov     rcx, [rbp+hKey]; hKey
0x18000730a  lea     rax, [rbp+cbData]
0x18000730e  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180007313  lea     r9, [rbp+Type]; lpType
0x180007317  xor     r8d, r8d; lpReserved
0x18000731a  mov     [rsp+30h+phkResult], 0; lpData
0x180007323  lea     rdx, aTrackedstores; "TrackedStores"
0x18000732a  mov     [rbp+Type], 0
0x180007331  mov     dword ptr [rbp+cbData], 0
0x180007338  call    cs:__imp_RegQueryValueExW
0x18000733e  mov     ebx, eax
0x180007340  test    eax, eax
0x180007342  jz      short loc_18000735A
0x180007344  jle     short loc_18000734F
0x180007346  movzx   ebx, ax
0x180007349  or      ebx, 80070000h
0x18000734f  mov     r9d, 448h
0x180007355  jmp     loc_180007439
0x18000735a  cmp     [rbp+Type], 3
0x18000735e  jnz     loc_18000742E
0x180007364  mov     eax, dword ptr [rbp+cbData]
0x180007367  test    eax, eax
0x180007369  jz      loc_18000742E
0x18000736f  lea     rbx, [rax+3]
0x180007373  shr     rbx, 2
0x180007377  test    al, 3
0x180007379  jz      short loc_18000738D
0x18000737b  mov     r8d, 44Ch
0x180007381  lea     rdx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180007388  call    Log_AssertionEvent
0x18000738d  mov     rax, [rsi]
0x180007390  mov     rdi, [r14]
0x180007393  sub     rdi, rax
0x180007396  sar     rdi, 2
0x18000739a  cmp     rbx, rdi
0x18000739d  jbe     short loc_1800073C5
0x18000739f  mov     rdx, rbx
0x1800073a2  mov     rcx, rsi
0x1800073a5  call    ?reserve@?$vector@KV?$allocator@K@utl@@@utl@@QEAA_N_K@Z; utl::vector<ulong,utl::allocator<ulong>>::reserve(unsigned __int64)
0x1800073aa  xor     edx, edx; Val
0x1800073ac  test    al, al
0x1800073ae  jz      short loc_180007421
0x1800073b0  mov     rcx, [r14]; void *
0x1800073b3  mov     r8, rbx
0x1800073b6  sub     r8, rdi
0x1800073b9  shl     r8, 2; Size
0x1800073bd  call    memset_0
0x1800073c2  mov     rax, [rsi]
0x1800073c5  lea     rcx, [rax+rbx*4]
0x1800073c9  xor     r8d, r8d; lpReserved
0x1800073cc  mov     [r14], rcx
0x1800073cf  lea     rax, [rbp+cbData]
0x1800073d3  mov     rcx, [rbp+hKey]; hKey
0x1800073d7  lea     r9, [rbp+Type]; lpType
0x1800073db  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800073e0  lea     rdx, aTrackedstores; "TrackedStores"
0x1800073e7  mov     rax, [rsi]
0x1800073ea  mov     [rsp+30h+phkResult], rax; lpData
0x1800073ef  call    cs:__imp_RegQueryValueExW
0x1800073f5  mov     ebx, eax
0x1800073f7  test    eax, eax
0x1800073f9  jz      short loc_18000740E
0x1800073fb  jle     short loc_180007406
0x1800073fd  movzx   ebx, ax
0x180007400  or      ebx, 80070000h
0x180007406  mov     r9d, 456h
0x18000740c  jmp     short loc_180007439
0x18000740e  mov     rcx, [rbp+hKey]; hKey
0x180007412  test    rcx, rcx
0x180007415  jz      short loc_18000741D
0x180007417  call    cs:__imp_RegCloseKey
0x18000741d  xor     eax, eax
0x18000741f  jmp     short loc_18000745A
0x180007421  mov     r9d, 44Dh
0x180007427  mov     ebx, 8007000Eh
0x18000742c  jmp     short loc_18000743B
0x18000742e  mov     r9d, 449h
0x180007434  mov     ebx, 8000FFFFh
0x180007439  xor     edx, edx
0x18000743b  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180007442  mov     ecx, ebx
0x180007444  call    Log_HREvent
0x180007449  mov     rcx, [rbp+hKey]; hKey
0x18000744d  test    rcx, rcx
0x180007450  jz      short loc_180007458
0x180007452  call    cs:__imp_RegCloseKey
0x180007458  mov     eax, ebx
0x18000745a  add     rsp, 30h
0x18000745e  pop     r14
0x180007460  pop     rdi
0x180007461  pop     rsi
0x180007462  pop     rbx
0x180007463  pop     rbp
0x180007464  retn
```
