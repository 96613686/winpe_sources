# DpspCheckSemUpdate

- ea: `0x180006834`
- end: `0x18000697f`
- name: `DpspCheckSemUpdate`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000f940`

## callees

- `0x180006834`
- `0x180009090`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180006927`
- `ntdll!RtlNtStatusToDosError` at `0x180006927`
- `ntdll!NtTraceControl` at `0x180006917`
- `ntdll!NtTraceControl` at `0x180006917`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006971`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006971`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006872`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006872`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800068d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800068d2`

## string_xrefs

- `0x18000685f`: `System\CurrentControlSet\Control\WDI\Config`
- `0x180006954`: `DpspCheckSemUpdate`
- `0x1800068be`: `SEMUpdate`

## pseudocode

```c
__int64 DpspCheckSemUpdate()
{
  LSTATUS v0; // eax
  bool v1; // sf
  signed int v2; // ebx
  LSTATUS v3; // eax
  NTSTATUS v4; // eax
  signed int v5; // eax
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  Data = 0;
  cbData = 4;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\WDI\\Config", 0, 0x20019u, &hKey);
  v1 = v0 < 0;
  if ( v0 > 0 )
    v1 = 1;
  if ( v1 )
    goto LABEL_4;
  if ( hKey )
  {
    v3 = RegQueryValueExW(hKey, L"SEMUpdate", 0, 0, (LPBYTE)&Data, &cbData);
    v2 = v3;
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    if ( v2 < 0 )
    {
LABEL_4:
      v2 = 0;
      goto LABEL_17;
    }
    if ( Data == 1 )
    {
      cbData = 0;
      v4 = NtTraceControl(20, 0, 0, 0, 0, &cbData);
      if ( v4 < 0 )
      {
        v5 = RtlNtStatusToDosError(v4);
        v2 = v5;
        if ( v5 > 0 )
          v2 = (unsigned __int16)v5 | 0x80070000;
      }
      else
      {
        v2 = 0;
      }
      if ( v2 < 0 )
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
          (int)L"DpspCheckSemUpdate",
          1759,
          (int)L"Error = %d",
          v2);
    }
  }
  else
  {
    v2 = -2147467259;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
      (int)L"DpspCheckSemUpdate",
      1735,
      (int)L"Error = %d",
      5);
  }
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180006834  mov     rax, rsp
0x180006837  push    rbx
0x180006838  sub     rsp, 30h
0x18000683c  mov     qword ptr [rax+18h], 0
0x180006844  mov     r9d, 20019h; samDesired
0x18000684a  mov     dword ptr [rax+10h], 0
0x180006851  xor     r8d, r8d; ulOptions
0x180006854  mov     dword ptr [rax+8], 4
0x18000685b  lea     rax, [rax+18h]
0x18000685f  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\WDI"...
0x180006866  mov     [rsp+38h+phkResult], rax; phkResult
0x18000686b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006872  call    cs:__imp_RegOpenKeyExW
0x180006878  test    eax, eax
0x18000687a  jle     short loc_180006886
0x18000687c  movzx   eax, ax
0x18000687f  or      eax, 80070000h
0x180006884  test    eax, eax
0x180006886  jns     short loc_18000688F
0x180006888  xor     ebx, ebx
0x18000688a  jmp     loc_180006967
0x18000688f  mov     rcx, [rsp+38h+hKey]; hKey
0x180006894  test    rcx, rcx
0x180006897  jnz     short loc_1800068B1
0x180006899  mov     ebx, 80004005h
0x18000689e  mov     dword ptr [rsp+38h+phkResult], 4005h
0x1800068a6  mov     r8d, 6C7h
0x1800068ac  jmp     loc_18000694D
0x1800068b1  lea     rax, [rsp+38h+cbData]
0x1800068b6  xor     r9d, r9d; lpType
0x1800068b9  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800068be  lea     rdx, ValueName; "SEMUpdate"
0x1800068c5  lea     rax, [rsp+38h+Data]
0x1800068ca  xor     r8d, r8d; lpReserved
0x1800068cd  mov     [rsp+38h+phkResult], rax; lpData
0x1800068d2  call    cs:__imp_RegQueryValueExW
0x1800068d8  mov     ebx, eax
0x1800068da  test    eax, eax
0x1800068dc  jle     short loc_1800068E7
0x1800068de  movzx   ebx, ax
0x1800068e1  or      ebx, 80070000h
0x1800068e7  test    ebx, ebx
0x1800068e9  js      short loc_180006888
0x1800068eb  cmp     [rsp+38h+Data], 1
0x1800068f0  jnz     short loc_180006967
0x1800068f2  xor     edx, edx
0x1800068f4  mov     [rsp+38h+cbData], 0
0x1800068fc  lea     rax, [rsp+38h+cbData]
0x180006901  xor     r9d, r9d
0x180006904  mov     [rsp+38h+lpcbData], rax
0x180006909  xor     r8d, r8d
0x18000690c  mov     dword ptr [rsp+38h+phkResult], 0
0x180006914  lea     ecx, [rdx+14h]
0x180006917  call    cs:__imp_NtTraceControl
0x18000691d  test    eax, eax
0x18000691f  js      short loc_180006925
0x180006921  xor     ebx, ebx
0x180006923  jmp     short loc_18000693C
0x180006925  mov     ecx, eax; Status
0x180006927  call    cs:__imp_RtlNtStatusToDosError
0x18000692d  mov     ebx, eax
0x18000692f  test    eax, eax
0x180006931  jle     short loc_18000693C
0x180006933  movzx   ebx, ax
0x180006936  or      ebx, 80070000h
0x18000693c  test    ebx, ebx
0x18000693e  jns     short loc_180006967
0x180006940  movzx   eax, bx
0x180006943  mov     r8d, 6DFh; int
0x180006949  mov     dword ptr [rsp+38h+phkResult], eax; Args
0x18000694d  lea     r9, aErrorD; "Error = %d"
0x180006954  lea     rdx, aDpspchecksemup; "DpspCheckSemUpdate"
0x18000695b  lea     rcx, aClientcoreBase_11; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180006962  call    WdipTraceError
0x180006967  mov     rcx, [rsp+38h+hKey]; hKey
0x18000696c  test    rcx, rcx
0x18000696f  jz      short loc_180006977
0x180006971  call    cs:__imp_RegCloseKey
0x180006977  mov     eax, ebx
0x180006979  add     rsp, 30h
0x18000697d  pop     rbx
0x18000697e  retn
```
