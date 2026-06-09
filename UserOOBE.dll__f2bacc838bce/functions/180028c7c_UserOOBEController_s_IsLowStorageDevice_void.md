# UserOOBEController::s_IsLowStorageDevice(void)

- ea: `0x180028c7c`
- end: `0x180028de1`
- name: `?s_IsLowStorageDevice@UserOOBEController@@CA_NXZ`
- size: `357`
- prototype: `char __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180029b68`

## callees

- `0x18000a5a4`
- `0x18000d738`
- `0x18001e7b4`
- `0x180025f4c`
- `0x180025f94`
- `0x180028c7c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028cec`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028cec`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180028d73`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180028d73`

## string_xrefs

- `0x180028d12`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180028db9`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180028cf7`: `Failed to open the physical disk.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall UserOOBEController::s_IsLowStorageDevice(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  void *v5; // rbx
  bool v6; // bl
  unsigned int Error; // eax
  const char *dwFlagsAndAttributesa; // [rsp+28h] [rbp-20h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD BytesReturned; // [rsp+50h] [rbp+8h] BYREF
  __int64 OutBuffer; // [rsp+58h] [rbp+10h] BYREF
  char *FileW; // [rsp+60h] [rbp+18h] BYREF

  BytesReturned = 0;
  if ( (int)SHRegGetBOOLWithREGSAM(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\TestHooks",
              L"TestLowStorageDevice",
              a4,
              (int *)&BytesReturned) >= 0
    && BytesReturned )
  {
    return 1;
  }
  FileW = (char *)CreateFileW(L"\\\\.\\PhysicalDrive0", 0x80000000, 1u, 0, 3u, 0, 0);
  v5 = FileW;
  if ( wil::details::in1diag3::Log_GetLastErrorIfMsg(
         retaddr,
         (void *)0x44D,
         (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
         (const char *)(FileW + 1 == 0),
         (bool)"Failed to open the physical disk.",
         dwFlagsAndAttributesa) )
  {
    goto LABEL_8;
  }
  BytesReturned = 0;
  OutBuffer = 0;
  if ( !DeviceIoControl(v5, 0x7405Cu, 0, 0, &OutBuffer, 8u, &BytesReturned, 0) )
  {
    Error = ResultFromKnownLastError();
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x45C,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)Error,
      (int)"Failed to call DeviceIoControl with IOCTL_DISK_GET_LENGTH_INFO.",
      dwFlagsAndAttributes);
LABEL_8:
    v6 = 0;
    goto LABEL_9;
  }
  v6 = OutBuffer / 1000000000 <= 32;
LABEL_9:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
  return v6;
}

```

## disassembly

```asm
0x180028c7c  push    rbx
0x180028c7e  sub     rsp, 40h
0x180028c82  lea     rax, [rsp+48h+BytesReturned]
0x180028c87  mov     [rsp+48h+BytesReturned], 0
0x180028c8f  lea     r8, aTestlowstorage; "TestLowStorageDevice"
0x180028c96  mov     qword ptr [rsp+48h+dwCreationDisposition], rax; int *
0x180028c9b  lea     rdx, aSoftwareMicros_31; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180028ca2  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180028ca9  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x180028cae  test    eax, eax
0x180028cb0  js      short loc_180028CC0
0x180028cb2  cmp     [rsp+48h+BytesReturned], 0
0x180028cb7  jz      short loc_180028CC0
0x180028cb9  mov     al, 1
0x180028cbb  jmp     loc_180028DDB
0x180028cc0  xor     r9d, r9d; lpSecurityAttributes
0x180028cc3  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180028ccc  mov     dword ptr [rsp+48h+dwFlagsAndAttributes], 0; char *
0x180028cd4  lea     rcx, FileName; "\\\\.\\PhysicalDrive0"
0x180028cdb  mov     edx, 80000000h; dwDesiredAccess
0x180028ce0  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180028ce8  lea     r8d, [r9+1]; dwShareMode
0x180028cec  call    cs:__imp_CreateFileW
0x180028cf2  mov     rcx, [rsp+48h]; this
0x180028cf7  lea     rdx, aFailedToOpenTh; "Failed to open the physical disk."
0x180028cfe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028d02  mov     [rsp+48h+arg_10], rax
0x180028d07  mov     rbx, rax
0x180028d0a  mov     qword ptr [rsp+48h+dwCreationDisposition], rdx; bool
0x180028d0f  setz    al
0x180028d12  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180028d19  movzx   r9d, al; char *
0x180028d1d  mov     edx, 44Dh; void *
0x180028d22  call    ?Log_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180028d27  test    al, al
0x180028d29  jnz     loc_180028DCD
0x180028d2f  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180028d38  lea     rax, [rsp+48h+BytesReturned]
0x180028d3d  mov     [rsp+48h+hTemplateFile], rax; lpBytesReturned
0x180028d42  xor     r9d, r9d; nInBufferSize
0x180028d45  lea     rax, [rsp+48h+OutBuffer]
0x180028d4a  mov     dword ptr [rsp+48h+dwFlagsAndAttributes], 8; char *
0x180028d52  xor     r8d, r8d; lpInBuffer
0x180028d55  mov     qword ptr [rsp+48h+dwCreationDisposition], rax; lpOutBuffer
0x180028d5a  mov     edx, 7405Ch; dwIoControlCode
0x180028d5f  mov     [rsp+48h+BytesReturned], 0
0x180028d67  mov     rcx, rbx; hDevice
0x180028d6a  mov     [rsp+48h+OutBuffer], 0
0x180028d73  call    cs:__imp_DeviceIoControl
0x180028d79  test    eax, eax
0x180028d7b  jz      short loc_180028DA3
0x180028d7d  mov     rax, 112E0BE826D694B3h
0x180028d87  imul    [rsp+48h+OutBuffer]
0x180028d8c  sar     rdx, 1Ah
0x180028d90  mov     rax, rdx
0x180028d93  shr     rax, 3Fh
0x180028d97  add     rdx, rax
0x180028d9a  cmp     rdx, 20h ; ' '
0x180028d9e  setle   bl
0x180028da1  jmp     short loc_180028DCF
0x180028da3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180028da8  mov     rcx, [rsp+48h]; this
0x180028dad  lea     rdx, aFailedToCallDe; "Failed to call DeviceIoControl with IOC"...
0x180028db4  mov     qword ptr [rsp+48h+dwCreationDisposition], rdx; int
0x180028db9  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180028dc0  mov     edx, 45Ch; void *
0x180028dc5  mov     r9d, eax; char *
0x180028dc8  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180028dcd  xor     ebx, ebx
0x180028dcf  lea     rcx, [rsp+48h+arg_10]
0x180028dd4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180028dd9  mov     al, bl
0x180028ddb  add     rsp, 40h
0x180028ddf  pop     rbx
0x180028de0  retn
```
