# WorkTracker::SignalWorkStarting(ulong,ulong *)

- ea: `0x18000a4fc`
- end: `0x18000a605`
- name: `?SignalWorkStarting@WorkTracker@@AEAAXKPEAK@Z`
- size: `265`
- prototype: `void(WorkTracker *__hidden this, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006070`

## callees

- `0x180003edc`
- `0x18000a4fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a5f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a5f8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000a5aa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000a5e9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000a5aa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000a5e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a595`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a595`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a56f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a56f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a5d8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a5d8`

## pseudocode

```c
void __fastcall WorkTracker::SignalWorkStarting(WorkTracker *this, int a2, BYTE *a3)
{
  HKEY *phkResult; // rax
  DWORD cbData; // [rsp+70h] [rbp+18h] BYREF
  int v6; // [rsp+74h] [rbp+1Ch]
  int Data; // [rsp+78h] [rbp+20h] BYREF
  DWORD Type; // [rsp+80h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+30h] BYREF

  Data = a2;
  v6 = HIDWORD(this);
  *(_DWORD *)a3 = 0;
  cbData = 4;
  Type = 4;
  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Poom\\Indexing", 0, 0, 0, 3u, 0, phkResult, 0);
  if ( RegQueryValueExW(hKey, L"RunCookie", 0, &Type, a3, &cbData) )
  {
    RegDeleteValueW(hKey, L"RunCookie");
    *(_DWORD *)a3 = 0;
  }
  RegSetValueExW(hKey, L"WorkStatus", 0, Type, (const BYTE *)&Data, cbData);
  RegDeleteValueW(hKey, L"WorkResult");
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18000a4fc  mov     [rsp-10h+Data], edx
0x18000a500  mov     qword ptr [rsp-10h+cbData], rcx
0x18000a505  push    rbp
0x18000a506  push    rbx
0x18000a507  mov     rbp, rsp
0x18000a50a  sub     rsp, 58h
0x18000a50e  mov     eax, 4
0x18000a513  mov     dword ptr [r8], 0
0x18000a51a  lea     rcx, [rbp+hKey]
0x18000a51e  mov     [rbp+cbData], eax
0x18000a521  mov     [rbp+Type], eax
0x18000a524  mov     rbx, r8
0x18000a527  mov     [rbp+hKey], 0
0x18000a52f  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18000a534  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18000a53d  lea     rdx, SubKey; "Software\\Microsoft\\Poom\\Indexing"
0x18000a544  mov     [rsp+58h+phkResult], rax; phkResult
0x18000a549  xor     r9d, r9d; lpClass
0x18000a54c  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000a555  xor     r8d, r8d; Reserved
0x18000a558  mov     [rsp+58h+samDesired], 3; samDesired
0x18000a560  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000a567  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000a56f  call    cs:__imp_RegCreateKeyExW
0x18000a575  mov     rcx, [rbp+hKey]; hKey
0x18000a579  lea     rax, [rbp+cbData]
0x18000a57d  mov     qword ptr [rsp+58h+samDesired], rax; lpcbData
0x18000a582  lea     r9, [rbp+Type]; lpType
0x18000a586  xor     r8d, r8d; lpReserved
0x18000a589  mov     qword ptr [rsp+58h+dwOptions], rbx; lpData
0x18000a58e  lea     rdx, aRuncookie; "RunCookie"
0x18000a595  call    cs:__imp_RegQueryValueExW
0x18000a59b  test    eax, eax
0x18000a59d  jz      short loc_18000A5B6
0x18000a59f  mov     rcx, [rbp+hKey]; hKey
0x18000a5a3  lea     rdx, aRuncookie; "RunCookie"
0x18000a5aa  call    cs:__imp_RegDeleteValueW
0x18000a5b0  mov     dword ptr [rbx], 0
0x18000a5b6  mov     eax, [rbp+cbData]
0x18000a5b9  lea     rdx, aWorkstatus; "WorkStatus"
0x18000a5c0  mov     r9d, [rbp+Type]; dwType
0x18000a5c4  xor     r8d, r8d; Reserved
0x18000a5c7  mov     rcx, [rbp+hKey]; hKey
0x18000a5cb  mov     [rsp+58h+samDesired], eax; cbData
0x18000a5cf  lea     rax, [rbp+Data]
0x18000a5d3  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18000a5d8  call    cs:__imp_RegSetValueExW
0x18000a5de  mov     rcx, [rbp+hKey]; hKey
0x18000a5e2  lea     rdx, aWorkresult; "WorkResult"
0x18000a5e9  call    cs:__imp_RegDeleteValueW
0x18000a5ef  mov     rcx, [rbp+hKey]; hKey
0x18000a5f3  test    rcx, rcx
0x18000a5f6  jz      short loc_18000A5FE
0x18000a5f8  call    cs:__imp_RegCloseKey
0x18000a5fe  add     rsp, 58h
0x18000a602  pop     rbx
0x18000a603  pop     rbp
0x18000a604  retn
```
