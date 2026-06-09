# CGroupPolicy::DiskForVolume(void *,_SP_DEVINFO_DATA *,ulong)

- ea: `0x18000fd14`
- end: `0x18000ff81`
- name: `?DiskForVolume@CGroupPolicy@@IEAAPEAXPEAXPEAU_SP_DEVINFO_DATA@@K@Z`
- size: `621`
- prototype: `__int64 __fastcall(CGroupPolicy *this, void *, struct _SP_DEVINFO_DATA *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800101cc`
- `0x180010d74`

## callees

- `0x180002fa0`
- `0x1800097d0`
- `0x18000fd14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fdd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fdd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fef0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fef0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000fe64`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000fe64`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000fec1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000fec1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fdf5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fdf5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fefd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ff28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fefd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ff28`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x18000fd85`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x18000fd85`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000fdc8`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000fe2e`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000fdc8`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000fe2e`

## string_xrefs

- `0x18000fe7c`: `Failed (%d) to open disk %ws\n`

## pseudocode

```c
__int64 __fastcall CGroupPolicy::DiskForVolume(CGroupPolicy *this, void *a2, struct _SP_DEVINFO_DATA *a3, int a4)
{
  __int64 FileW; // rdi
  DWORD v5; // r14d
  DWORD LastError; // eax
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v10; // rax
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v11; // rbx
  const WCHAR *DevicePath; // rsi
  DWORD v13; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  DWORD RequiredSize; // [rsp+40h] [rbp-40h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-3Ch] BYREF
  __int64 OutBuffer; // [rsp+48h] [rbp-38h] BYREF
  int v20; // [rsp+50h] [rbp-30h]
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+58h] [rbp-28h] BYREF

  FileW = -1;
  OutBuffer = 0;
  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  v20 = 0;
  v5 = 0;
  BytesReturned = 0;
  RequiredSize = 0;
  while ( 1 )
  {
    DeviceInterfaceData.cbSize = 32;
    if ( !SetupDiEnumDeviceInterfaces(a2, 0, &GUID_DEVINTERFACE_DISK, v5, &DeviceInterfaceData) )
      return FileW;
    *(_OWORD *)&a3->cbSize = 0;
    *(_OWORD *)&a3->ClassGuid.Data4[4] = 0;
    a3->cbSize = 32;
    if ( SetupDiGetDeviceInterfaceDetailW(a2, &DeviceInterfaceData, 0, 0, &RequiredSize, 0) )
      goto LABEL_19;
    LastError = GetLastError();
    if ( LastError != 122 || !RequiredSize )
    {
      GPDebugPrintX(2u, "SetupDiGetDeviceInterfaceDetail failed (%d)\n", LastError);
      return FileW;
    }
    v10 = (struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *)LocalAlloc(0x40u, RequiredSize);
    v11 = v10;
    if ( !v10 )
    {
LABEL_19:
      GPDebugPrintX(2u, "Failed to alloc memory for SetupDiGetDeviceInterfaceDetail\n");
      return FileW;
    }
    v10->cbSize = 8;
    DevicePath = v10->DevicePath;
    v10->DevicePath[0] = 0;
    if ( !SetupDiGetDeviceInterfaceDetailW(a2, &DeviceInterfaceData, v10, RequiredSize, 0, a3) )
    {
      v15 = GetLastError();
      GPDebugPrintX(2u, "SetupDiGetDeviceInterfaceDetail failed (%d)\n", v15);
LABEL_17:
      LocalFree(v11);
      return FileW;
    }
    FileW = (__int64)CreateFileW(DevicePath, 0x12019Fu, 1u, 0, 3u, 0, 0);
    if ( FileW == -1 )
    {
      v13 = GetLastError();
      GPDebugPrintX(2u, "Failed (%d) to open disk %ws\n", v13, DevicePath);
    }
    else
    {
      if ( DeviceIoControl((HANDLE)FileW, 0x2D1080u, 0, 0, &OutBuffer, 0xCu, &BytesReturned, 0) )
      {
        if ( HIDWORD(OutBuffer) == a4 )
          goto LABEL_17;
      }
      else
      {
        v14 = GetLastError();
        GPDebugPrintX(2u, "DeviceIoControl failed (%d)\n", v14);
      }
      CloseHandle((HANDLE)FileW);
      FileW = -1;
    }
    LocalFree(v11);
    ++v5;
  }
}

```

## disassembly

```asm
0x18000fd14  mov     [rsp-38h+arg_0], rbx
0x18000fd19  push    rbp
0x18000fd1a  push    rsi
0x18000fd1b  push    rdi
0x18000fd1c  push    r12
0x18000fd1e  push    r13
0x18000fd20  push    r14
0x18000fd22  push    r15
0x18000fd24  mov     rbp, rsp
0x18000fd27  sub     rsp, 80h
0x18000fd2e  mov     rax, cs:__security_cookie
0x18000fd35  xor     rax, rsp
0x18000fd38  mov     [rbp+var_8], rax
0x18000fd3c  xor     eax, eax
0x18000fd3e  xorps   xmm0, xmm0
0x18000fd41  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000fd45  mov     [rbp+OutBuffer], rax
0x18000fd49  movups  xmmword ptr [rbp+var_28.cbSize], xmm0
0x18000fd4d  mov     [rbp+var_30], eax
0x18000fd50  xor     r14d, r14d
0x18000fd53  movups  xmmword ptr [rbp+var_28.InterfaceClassGuid.Data4+4], xmm0
0x18000fd57  mov     [rbp+BytesReturned], eax
0x18000fd5a  mov     r13d, r9d
0x18000fd5d  mov     [rbp+RequiredSize], eax
0x18000fd60  mov     r12, r8
0x18000fd63  mov     r15, rdx
0x18000fd66  lea     rax, [rbp+var_28]
0x18000fd6a  mov     [rbp+var_28.cbSize], 20h ; ' '
0x18000fd71  mov     r9d, r14d; MemberIndex
0x18000fd74  mov     [rsp+80h+DeviceInterfaceData], rax; DeviceInterfaceData
0x18000fd79  lea     r8, GUID_DEVINTERFACE_DISK; InterfaceClassGuid
0x18000fd80  xor     edx, edx; DeviceInfoData
0x18000fd82  mov     rcx, r15; DeviceInfoSet
0x18000fd85  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x18000fd8b  test    eax, eax
0x18000fd8d  jz      loc_18000FF57
0x18000fd93  xorps   xmm0, xmm0
0x18000fd96  mov     [rsp+80h+DeviceInfoData], 0; DeviceInfoData
0x18000fd9f  movups  xmmword ptr [r12], xmm0
0x18000fda4  lea     rax, [rbp+RequiredSize]
0x18000fda8  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x18000fdab  movups  xmmword ptr [r12+10h], xmm0
0x18000fdb1  xor     r8d, r8d; DeviceInterfaceDetailData
0x18000fdb4  mov     dword ptr [r12], 20h ; ' '
0x18000fdbc  lea     rdx, [rbp+var_28]; DeviceInterfaceData
0x18000fdc0  mov     [rsp+80h+DeviceInterfaceData], rax; RequiredSize
0x18000fdc5  mov     rcx, r15; DeviceInfoSet
0x18000fdc8  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x18000fdce  test    eax, eax
0x18000fdd0  jnz     loc_18000FF46
0x18000fdd6  call    cs:__imp_GetLastError
0x18000fddc  cmp     eax, 7Ah ; 'z'
0x18000fddf  jnz     loc_18000FF30
0x18000fde5  mov     ecx, [rbp+RequiredSize]
0x18000fde8  test    ecx, ecx
0x18000fdea  jz      loc_18000FF30
0x18000fdf0  mov     edx, ecx; uBytes
0x18000fdf2  lea     ecx, [rax-3Ah]; uFlags
0x18000fdf5  call    cs:__imp_LocalAlloc
0x18000fdfb  mov     rbx, rax
0x18000fdfe  test    rax, rax
0x18000fe01  jz      loc_18000FF46
0x18000fe07  xor     ecx, ecx
0x18000fe09  mov     dword ptr [rax], 8
0x18000fe0f  lea     rsi, [rax+4]
0x18000fe13  mov     [rsp+80h+DeviceInfoData], r12; DeviceInfoData
0x18000fe18  mov     [rsi], cx
0x18000fe1b  lea     rdx, [rbp+var_28]; DeviceInterfaceData
0x18000fe1f  mov     r9d, [rbp+RequiredSize]; DeviceInterfaceDetailDataSize
0x18000fe23  mov     r8, rax; DeviceInterfaceDetailData
0x18000fe26  mov     [rsp+80h+DeviceInterfaceData], rcx; RequiredSize
0x18000fe2b  mov     rcx, r15; DeviceInfoSet
0x18000fe2e  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x18000fe34  test    eax, eax
0x18000fe36  jz      loc_18000FF0B
0x18000fe3c  xor     r9d, r9d; lpSecurityAttributes
0x18000fe3f  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x18000fe48  mov     dword ptr [rsp+80h+DeviceInfoData], 0; dwFlagsAndAttributes
0x18000fe50  mov     edx, 12019Fh; dwDesiredAccess
0x18000fe55  mov     rcx, rsi; lpFileName
0x18000fe58  mov     dword ptr [rsp+80h+DeviceInterfaceData], 3; dwCreationDisposition
0x18000fe60  lea     r8d, [r9+1]; dwShareMode
0x18000fe64  call    cs:__imp_CreateFileW
0x18000fe6a  mov     rdi, rax
0x18000fe6d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fe71  jnz     short loc_18000FE90
0x18000fe73  call    cs:__imp_GetLastError
0x18000fe79  mov     r9, rsi
0x18000fe7c  lea     rdx, aFailedDToOpenD; "Failed (%d) to open disk %ws\n"
0x18000fe83  mov     r8d, eax
0x18000fe86  lea     ecx, [rdi+3]; unsigned int
0x18000fe89  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000fe8e  jmp     short loc_18000FEFA
0x18000fe90  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x18000fe99  lea     rax, [rbp+BytesReturned]
0x18000fe9d  mov     [rsp+80h+hTemplateFile], rax; lpBytesReturned
0x18000fea2  xor     r9d, r9d; nInBufferSize
0x18000fea5  lea     rax, [rbp+OutBuffer]
0x18000fea9  mov     dword ptr [rsp+80h+DeviceInfoData], 0Ch; nOutBufferSize
0x18000feb1  xor     r8d, r8d; lpInBuffer
0x18000feb4  mov     [rsp+80h+DeviceInterfaceData], rax; lpOutBuffer
0x18000feb9  mov     edx, 2D1080h; dwIoControlCode
0x18000febe  mov     rcx, rdi; hDevice
0x18000fec1  call    cs:__imp_DeviceIoControl
0x18000fec7  test    eax, eax
0x18000fec9  jz      short loc_18000FED3
0x18000fecb  cmp     dword ptr [rbp+OutBuffer+4], r13d
0x18000fecf  jz      short loc_18000FF25
0x18000fed1  jmp     short loc_18000FEED
0x18000fed3  call    cs:__imp_GetLastError
0x18000fed9  lea     rdx, aDeviceiocontro; "DeviceIoControl failed (%d)\n"
0x18000fee0  mov     ecx, 2; unsigned int
0x18000fee5  mov     r8d, eax
0x18000fee8  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000feed  mov     rcx, rdi; hObject
0x18000fef0  call    cs:__imp_CloseHandle
0x18000fef6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000fefa  mov     rcx, rbx; hMem
0x18000fefd  call    cs:__imp_LocalFree
0x18000ff03  inc     r14d
0x18000ff06  jmp     loc_18000FD66
0x18000ff0b  call    cs:__imp_GetLastError
0x18000ff11  lea     rdx, aSetupdigetdevi_4; "SetupDiGetDeviceInterfaceDetail failed "...
0x18000ff18  mov     ecx, 2; unsigned int
0x18000ff1d  mov     r8d, eax
0x18000ff20  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000ff25  mov     rcx, rbx; hMem
0x18000ff28  call    cs:__imp_LocalFree
0x18000ff2e  jmp     short loc_18000FF57
0x18000ff30  mov     r8d, eax
0x18000ff33  lea     rdx, aSetupdigetdevi_4; "SetupDiGetDeviceInterfaceDetail failed "...
0x18000ff3a  mov     ecx, 2; unsigned int
0x18000ff3f  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000ff44  jmp     short loc_18000FF57
0x18000ff46  lea     rdx, aFailedToAllocM; "Failed to alloc memory for SetupDiGetDe"...
0x18000ff4d  mov     ecx, 2; unsigned int
0x18000ff52  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000ff57  mov     rax, rdi
0x18000ff5a  mov     rcx, [rbp+var_8]
0x18000ff5e  xor     rcx, rsp; StackCookie
0x18000ff61  call    __security_check_cookie
0x18000ff66  mov     rbx, [rsp+80h+arg_0]
0x18000ff6e  add     rsp, 80h
0x18000ff75  pop     r15
0x18000ff77  pop     r14
0x18000ff79  pop     r13
0x18000ff7b  pop     r12
0x18000ff7d  pop     rdi
0x18000ff7e  pop     rsi
0x18000ff7f  pop     rbp
0x18000ff80  retn
```
