# WorkTracker::SignalWorkFinishing(long,ulong)

- ea: `0x18000a410`
- end: `0x18000a4f5`
- name: `?SignalWorkFinishing@WorkTracker@@AEAAXJK@Z`
- size: `229`
- prototype: `void __fastcall(WorkTracker *__hidden this, int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006070`

## callees

- `0x180003edc`
- `0x18000a410`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a4ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a4ea`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000a4da`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000a4da`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a46e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a46e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a49b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a4c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a49b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a4c8`

## pseudocode

```c
void __fastcall WorkTracker::SignalWorkFinishing(WorkTracker *this, int a2, int a3)
{
  HKEY *phkResult; // rax
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  int Data; // [rsp+68h] [rbp+10h] BYREF
  int v6; // [rsp+70h] [rbp+18h] BYREF

  v6 = a3;
  Data = a2;
  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Poom\\Indexing", 0, 0, 0, 2u, 0, phkResult, 0);
  RegSetValueExW(hKey, L"WorkResult", 0, 4u, (const BYTE *)&Data, 4u);
  RegSetValueExW(hKey, L"RunCookie", 0, 4u, (const BYTE *)&v6, 4u);
  RegDeleteValueW(hKey, L"WorkStatus");
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18000a410  mov     rax, rsp
0x18000a413  mov     [rax+18h], r8d
0x18000a417  mov     [rax+10h], edx
0x18000a41a  mov     [rax+8], rcx
0x18000a41e  sub     rsp, 58h
0x18000a422  lea     rcx, [rax+8]
0x18000a426  mov     qword ptr [rax+8], 0
0x18000a42e  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18000a433  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18000a43c  lea     rdx, SubKey; "Software\\Microsoft\\Poom\\Indexing"
0x18000a443  mov     [rsp+58h+phkResult], rax; phkResult
0x18000a448  xor     r9d, r9d; lpClass
0x18000a44b  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000a454  xor     r8d, r8d; Reserved
0x18000a457  mov     [rsp+58h+samDesired], 2; samDesired
0x18000a45f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000a466  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000a46e  call    cs:__imp_RegCreateKeyExW
0x18000a474  mov     rcx, [rsp+58h+hKey]; hKey
0x18000a479  lea     rax, [rsp+58h+Data]
0x18000a47e  mov     [rsp+58h+samDesired], 4; cbData
0x18000a486  lea     rdx, aWorkresult; "WorkResult"
0x18000a48d  mov     r9d, 4; dwType
0x18000a493  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18000a498  xor     r8d, r8d; Reserved
0x18000a49b  call    cs:__imp_RegSetValueExW
0x18000a4a1  mov     rcx, [rsp+58h+hKey]; hKey
0x18000a4a6  lea     rax, [rsp+58h+arg_10]
0x18000a4ab  mov     [rsp+58h+samDesired], 4; cbData
0x18000a4b3  lea     rdx, aRuncookie; "RunCookie"
0x18000a4ba  mov     r9d, 4; dwType
0x18000a4c0  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18000a4c5  xor     r8d, r8d; Reserved
0x18000a4c8  call    cs:__imp_RegSetValueExW
0x18000a4ce  mov     rcx, [rsp+58h+hKey]; hKey
0x18000a4d3  lea     rdx, aWorkstatus; "WorkStatus"
0x18000a4da  call    cs:__imp_RegDeleteValueW
0x18000a4e0  mov     rcx, [rsp+58h+hKey]; hKey
0x18000a4e5  test    rcx, rcx
0x18000a4e8  jz      short loc_18000A4F0
0x18000a4ea  call    cs:__imp_RegCloseKey
0x18000a4f0  add     rsp, 58h
0x18000a4f4  retn
```
