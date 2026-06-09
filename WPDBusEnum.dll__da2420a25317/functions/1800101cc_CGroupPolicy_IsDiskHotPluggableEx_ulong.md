# CGroupPolicy::IsDiskHotPluggableEx(ulong)

- ea: `0x1800101cc`
- end: `0x18001045c`
- name: `?IsDiskHotPluggableEx@CGroupPolicy@@IEAA?AW4TriState@1@K@Z`
- size: `656`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18000f390`

## callees

- `0x180002fa0`
- `0x1800097d0`
- `0x18000fd14`
- `0x1800101cc`
- `0x180010464`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800103fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800103fe`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180010292`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180010292`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001037c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180010391`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800103a6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800103bb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800103d0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001037c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180010391`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800103a6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800103bb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800103d0`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180010211`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180010211`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x180010309`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x180010363`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x180010309`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x180010363`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18001041f`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18001041f`

## pseudocode

```c
__int64 __fastcall CGroupPolicy::IsDiskHotPluggableEx(__int64 a1, int a2)
{
  BOOL v3; // ebx
  HDEVINFO ClassDevsW; // rax
  CGroupPolicy *v5; // rcx
  void *v6; // rdi
  void *v7; // r14
  int v8; // esi
  DWORD LastError; // eax
  CGroupPolicy *v10; // rcx
  DWORD v11; // eax
  BYTE PropertyBuffer[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-BCh] BYREF
  DWORD RequiredSize; // [rsp+48h] [rbp-B8h] BYREF
  __int128 OutBuffer; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+60h] [rbp-A0h]
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+68h] [rbp-98h] BYREF
  BYTE v19[2]; // [rsp+90h] [rbp-70h] BYREF

  v3 = 1;
  ClassDevsW = SetupDiGetClassDevsW(&GUID_DEVINTERFACE_DISK, 0, 0, 0x12u);
  v6 = ClassDevsW;
  if ( ClassDevsW == (HDEVINFO)-1LL )
    return (unsigned int)v3 + 1;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  v7 = (void *)CGroupPolicy::DiskForVolume(v5, ClassDevsW, &DeviceInfoData, a2);
  if ( v7 != (void *)-1LL )
  {
    v8 = 0;
    v17 = 0;
    BytesReturned = 0;
    OutBuffer = 0;
    if ( DeviceIoControl(v7, 0x700010u, 0, 0, &OutBuffer, 0x18u, &BytesReturned, 0) )
    {
      if ( *((_QWORD *)&OutBuffer + 1) || (_DWORD)v17 || BYTE4(v17) )
      {
        v3 = 0;
LABEL_22:
        CloseHandle(v7);
        goto LABEL_24;
      }
    }
    else
    {
      LastError = GetLastError();
      GPDebugPrintX(2, "DISK_DEVICE_STATE Failed (%d)\n", LastError);
    }
    *(_DWORD *)PropertyBuffer = 0;
    RequiredSize = 0;
    if ( SetupDiGetDeviceRegistryPropertyW(v6, &DeviceInfoData, 0x1Fu, 0, PropertyBuffer, 4u, &RequiredSize) )
    {
      v3 = *(_DWORD *)PropertyBuffer != 1 && CGroupPolicy::IsHotPluggableBus(v10, v7) != 0;
      if ( !v3 )
      {
        *(_WORD *)v19 = 0;
        if ( SetupDiGetDeviceRegistryPropertyW(v6, &DeviceInfoData, 0x16u, 0, v19, 0x100u, 0) )
        {
          if ( !lstrcmpW((LPCWSTR)v19, L"USB")
            || !lstrcmpW((LPCWSTR)v19, L"USBSTOR")
            || !lstrcmpW((LPCWSTR)v19, L"SD")
            || !lstrcmpW((LPCWSTR)v19, L"SBP2")
            || !lstrcmpW((LPCWSTR)v19, L"FLASHMEDIA") )
          {
            v3 = 1;
          }
        }
      }
    }
    else
    {
      v11 = GetLastError();
      GPDebugPrintX(2, "Failed (%d) to get removal policy\n", v11);
    }
    goto LABEL_22;
  }
  GPDebugPrintX(4, "Disk %d not found\n", a2);
  v8 = 1;
LABEL_24:
  SetupDiDestroyDeviceInfoList(v6);
  if ( v8 )
    return 0;
  return (unsigned int)v3 + 1;
}

```

## disassembly

```asm
0x1800101cc  mov     [rsp-8+arg_0], rbx
0x1800101d1  mov     [rsp-8+arg_10], rsi
0x1800101d6  push    rbp
0x1800101d7  push    rdi
0x1800101d8  push    r14
0x1800101da  lea     rbp, [rsp-0A0h]
0x1800101e2  sub     rsp, 1A0h
0x1800101e9  mov     rax, cs:__security_cookie
0x1800101f0  xor     rax, rsp
0x1800101f3  mov     [rbp+0B0h+var_20], rax
0x1800101fa  mov     esi, edx
0x1800101fc  lea     rcx, GUID_DEVINTERFACE_DISK; ClassGuid
0x180010203  mov     ebx, 1
0x180010208  xor     r8d, r8d; hwndParent
0x18001020b  xor     edx, edx; Enumerator
0x18001020d  lea     r9d, [rbx+11h]; Flags
0x180010211  call    cs:__imp_SetupDiGetClassDevsW
0x180010217  mov     rdi, rax
0x18001021a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001021e  jz      loc_18001042D
0x180010224  xorps   xmm0, xmm0
0x180010227  lea     r8, [rsp+1B0h+DeviceInfoData]; struct _SP_DEVINFO_DATA *
0x18001022c  mov     r9d, esi; unsigned int
0x18001022f  mov     rdx, rax; void *
0x180010232  movups  xmmword ptr [rsp+1B0h+DeviceInfoData.cbSize], xmm0
0x180010237  movups  xmmword ptr [rsp+1B0h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x18001023c  call    ?DiskForVolume@CGroupPolicy@@IEAAPEAXPEAXPEAU_SP_DEVINFO_DATA@@K@Z; CGroupPolicy::DiskForVolume(void *,_SP_DEVINFO_DATA *,ulong)
0x180010241  mov     r14, rax
0x180010244  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010248  jz      loc_180010406
0x18001024e  xor     eax, eax
0x180010250  xorps   xmm0, xmm0
0x180010253  mov     [rsp+1B0h+lpOverlapped], rax; lpOverlapped
0x180010258  xor     esi, esi
0x18001025a  mov     [rsp+1B0h+var_150], rax
0x18001025f  xor     r9d, r9d; nInBufferSize
0x180010262  lea     rax, [rsp+1B0h+BytesReturned]
0x180010267  mov     [rsp+1B0h+BytesReturned], esi
0x18001026b  mov     [rsp+1B0h+lpBytesReturned], rax; lpBytesReturned
0x180010270  xor     r8d, r8d; lpInBuffer
0x180010273  lea     rax, [rsp+1B0h+OutBuffer]
0x180010278  mov     [rsp+1B0h+nOutBufferSize], 18h; nOutBufferSize
0x180010280  mov     edx, 700010h; dwIoControlCode
0x180010285  mov     [rsp+1B0h+lpOutBuffer], rax; lpOutBuffer
0x18001028a  mov     rcx, r14; hDevice
0x18001028d  movups  [rsp+1B0h+OutBuffer], xmm0
0x180010292  call    cs:__imp_DeviceIoControl
0x180010298  test    eax, eax
0x18001029a  jz      short loc_1800102BC
0x18001029c  cmp     dword ptr [rsp+1B0h+OutBuffer+8], esi
0x1800102a0  jnz     short loc_1800102B5
0x1800102a2  cmp     dword ptr [rsp+1B0h+OutBuffer+0Ch], esi
0x1800102a6  jnz     short loc_1800102B5
0x1800102a8  cmp     dword ptr [rsp+1B0h+var_150], esi
0x1800102ac  jnz     short loc_1800102B5
0x1800102ae  cmp     byte ptr [rsp+1B0h+var_150+4], sil
0x1800102b3  jz      short loc_1800102D6
0x1800102b5  xor     ebx, ebx
0x1800102b7  jmp     loc_1800103FB
0x1800102bc  call    cs:__imp_GetLastError
0x1800102c2  lea     rdx, aDiskDeviceStat; "DISK_DEVICE_STATE Failed (%d)\n"
0x1800102c9  mov     ecx, 2; unsigned int
0x1800102ce  mov     r8d, eax
0x1800102d1  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x1800102d6  xor     r9d, r9d; PropertyRegDataType
0x1800102d9  mov     dword ptr [rsp+1B0h+PropertyBuffer], esi
0x1800102dd  lea     rax, [rsp+1B0h+RequiredSize]
0x1800102e2  mov     [rsp+1B0h+RequiredSize], esi
0x1800102e6  mov     [rsp+1B0h+lpBytesReturned], rax; RequiredSize
0x1800102eb  lea     rdx, [rsp+1B0h+DeviceInfoData]; DeviceInfoData
0x1800102f0  lea     rax, [rsp+1B0h+PropertyBuffer]
0x1800102f5  mov     [rsp+1B0h+nOutBufferSize], 4; PropertyBufferSize
0x1800102fd  lea     r8d, [r9+1Fh]; Property
0x180010301  mov     [rsp+1B0h+lpOutBuffer], rax; PropertyBuffer
0x180010306  mov     rcx, rdi; DeviceInfoSet
0x180010309  call    cs:__imp_SetupDiGetDeviceRegistryPropertyW
0x18001030f  test    eax, eax
0x180010311  jz      loc_1800103E1
0x180010317  cmp     dword ptr [rsp+1B0h+PropertyBuffer], ebx
0x18001031b  jz      short loc_18001032E
0x18001031d  mov     rdx, r14; void *
0x180010320  call    ?IsHotPluggableBus@CGroupPolicy@@IEAAHPEAX@Z; CGroupPolicy::IsHotPluggableBus(void *)
0x180010325  xor     ebx, ebx
0x180010327  test    eax, eax
0x180010329  setnz   bl
0x18001032c  jmp     short loc_180010330
0x18001032e  xor     ebx, ebx
0x180010330  test    ebx, ebx
0x180010332  jnz     loc_1800103FB
0x180010338  xor     eax, eax
0x18001033a  lea     r8d, [rbx+16h]; Property
0x18001033e  mov     [rsp+1B0h+lpBytesReturned], rax; RequiredSize
0x180010343  lea     rdx, [rsp+1B0h+DeviceInfoData]; DeviceInfoData
0x180010348  mov     word ptr [rbp+0B0h+var_120], ax
0x18001034c  xor     r9d, r9d; PropertyRegDataType
0x18001034f  lea     rax, [rbp+0B0h+var_120]
0x180010353  mov     [rsp+1B0h+nOutBufferSize], 100h; PropertyBufferSize
0x18001035b  mov     rcx, rdi; DeviceInfoSet
0x18001035e  mov     [rsp+1B0h+lpOutBuffer], rax; PropertyBuffer
0x180010363  call    cs:__imp_SetupDiGetDeviceRegistryPropertyW
0x180010369  test    eax, eax
0x18001036b  jz      loc_1800103FB
0x180010371  lea     rdx, aUsb; "USB"
0x180010378  lea     rcx, [rbp+0B0h+var_120]; lpString1
0x18001037c  call    cs:__imp_lstrcmpW
0x180010382  test    eax, eax
0x180010384  jz      short loc_1800103DA
0x180010386  lea     rdx, aUsbstor; "USBSTOR"
0x18001038d  lea     rcx, [rbp+0B0h+var_120]; lpString1
0x180010391  call    cs:__imp_lstrcmpW
0x180010397  test    eax, eax
0x180010399  jz      short loc_1800103DA
0x18001039b  lea     rdx, aSd; "SD"
0x1800103a2  lea     rcx, [rbp+0B0h+var_120]; lpString1
0x1800103a6  call    cs:__imp_lstrcmpW
0x1800103ac  test    eax, eax
0x1800103ae  jz      short loc_1800103DA
0x1800103b0  lea     rdx, aSbp2; "SBP2"
0x1800103b7  lea     rcx, [rbp+0B0h+var_120]; lpString1
0x1800103bb  call    cs:__imp_lstrcmpW
0x1800103c1  test    eax, eax
0x1800103c3  jz      short loc_1800103DA
0x1800103c5  lea     rdx, aFlashmedia; "FLASHMEDIA"
0x1800103cc  lea     rcx, [rbp+0B0h+var_120]; lpString1
0x1800103d0  call    cs:__imp_lstrcmpW
0x1800103d6  test    eax, eax
0x1800103d8  jnz     short loc_1800103FB
0x1800103da  mov     ebx, 1
0x1800103df  jmp     short loc_1800103FB
0x1800103e1  call    cs:__imp_GetLastError
0x1800103e7  lea     rdx, aFailedDToGetRe; "Failed (%d) to get removal policy\n"
0x1800103ee  mov     ecx, 2; unsigned int
0x1800103f3  mov     r8d, eax
0x1800103f6  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x1800103fb  mov     rcx, r14; hObject
0x1800103fe  call    cs:__imp_CloseHandle
0x180010404  jmp     short loc_18001041C
0x180010406  mov     r8d, esi
0x180010409  lea     rdx, aDiskDNotFound; "Disk %d not found\n"
0x180010410  mov     ecx, 4; unsigned int
0x180010415  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18001041a  mov     esi, ebx
0x18001041c  mov     rcx, rdi; DeviceInfoSet
0x18001041f  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180010425  test    esi, esi
0x180010427  jz      short loc_18001042D
0x180010429  xor     eax, eax
0x18001042b  jmp     short loc_180010435
0x18001042d  neg     ebx
0x18001042f  sbb     eax, eax
0x180010431  neg     eax
0x180010433  inc     eax
0x180010435  mov     rcx, [rbp+0B0h+var_20]
0x18001043c  xor     rcx, rsp; StackCookie
0x18001043f  call    __security_check_cookie
0x180010444  lea     r11, [rsp+1B0h+var_10]
0x18001044c  mov     rbx, [r11+20h]
0x180010450  mov     rsi, [r11+30h]
0x180010454  mov     rsp, r11
0x180010457  pop     r14
0x180010459  pop     rdi
0x18001045a  pop     rbp
0x18001045b  retn
```
