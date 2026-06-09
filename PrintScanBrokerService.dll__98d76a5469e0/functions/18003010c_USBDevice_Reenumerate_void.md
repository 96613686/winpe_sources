# USBDevice::Reenumerate(void)

- ea: `0x18003010c`
- end: `0x18003042a`
- name: `?Reenumerate@USBDevice@@QEAAXXZ`
- size: `798`
- prototype: `void __fastcall(USBDevice *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180012d38`

## callees

- `0x180002d40`
- `0x180003a0c`
- `0x18000f760`
- `0x18001255c`
- `0x18001cfd4`
- `0x18002b28c`
- `0x18003010c`
- `0x180030514`
- `0x18003055c`
- `0x1800305a0`
- `0x1800306d8`

## import_xrefs

- `SETUPAPI!CM_Get_Parent` at `0x180030253`
- `SETUPAPI!CM_Get_Parent` at `0x180030253`
- `SETUPAPI!CM_Get_DevNode_Registry_PropertyW` at `0x1800301dd`
- `SETUPAPI!CM_Get_DevNode_Registry_PropertyW` at `0x1800301dd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030319`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030319`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800303c4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800303c4`

## string_xrefs

- `0x18003018a`: `onecoreuap\printscan\print\printscanbroker\class\usbdevice.cpp`
- `0x180030174`: `GetDevInstFromPath (%ws) failed`
- `0x180030338`: `CreateFile (%ws) failed`
- `0x1800302cd`: `FormatGuidPathFromDevInst (%ws) failed`
- `0x1800301ea`: `CM_Get_DevNode_Registry_Property(CM_DRP_ADDRESS) returned 0x%x\n`

## pseudocode

```c
void __fastcall USBDevice::Reenumerate(USBDevice *this)
{
  const char *v1; // rdi
  const unsigned __int16 *v2; // rdx
  DEVINST DevInstFromPath; // ebx
  const char *v4; // rdx
  const char *v5; // rsi
  CONFIGRET DevNode_Registry_PropertyW; // eax
  char v7; // al
  const char *v8; // rsi
  CONFIGRET Parent; // eax
  USBDevice *v10; // rcx
  const struct _GUID *v11; // r8
  const char *v12; // rbx
  int v13; // eax
  char *FileW; // rbx
  BOOL v15; // eax
  int pulLength; // [rsp+20h] [rbp-E0h]
  unsigned int Buffer; // [rsp+40h] [rbp-C0h] BYREF
  DEVNODE pdnDevInst; // [rsp+44h] [rbp-BCh] BYREF
  ULONG v19[2]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD BytesReturned; // [rsp+50h] [rbp-B0h] BYREF
  __int64 InBuffer; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v1 = (char *)this + 8;
  if ( *((_QWORD *)this + 4) <= 7u )
    v2 = (const unsigned __int16 *)((char *)this + 8);
  else
    v2 = *(const unsigned __int16 **)v1;
  DevInstFromPath = USBDevice::_GetDevInstFromPath(this, v2);
  if ( *((_QWORD *)v1 + 3) <= 7u )
    v4 = v1;
  else
    v4 = *(const char **)v1;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x12,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\usbdevice.cpp",
    (const char *)0x8007000ELL,
    DevInstFromPath == 0,
    (bool)"GetDevInstFromPath (%ws) failed",
    v4);
  Buffer = 0;
  if ( *((_QWORD *)v1 + 3) <= 7u )
    v5 = v1;
  else
    v5 = *(const char **)v1;
  v19[0] = 4;
  DevNode_Registry_PropertyW = CM_Get_DevNode_Registry_PropertyW(DevInstFromPath, 0x1Du, 0, &Buffer, v19, 0);
  if ( DevNode_Registry_PropertyW )
  {
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "USBDevice::_GetConnectionIndex",
      L"CM_Get_DevNode_Registry_Property(CM_DRP_ADDRESS) returned 0x%x\n",
      DevNode_Registry_PropertyW);
    v7 = 0;
  }
  else
  {
    v7 = 1;
  }
  wil::details::in1diag3::Throw_HrIfFalseMsg(
    retaddr,
    (void *)0x16,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\usbdevice.cpp",
    (const char *)0x80004005LL,
    v7,
    (bool)"GetConnectionIndex (%ws) failed",
    v5);
  pdnDevInst = 0;
  if ( *((_QWORD *)v1 + 3) <= 7u )
    v8 = v1;
  else
    v8 = *(const char **)v1;
  Parent = CM_Get_Parent(&pdnDevInst, DevInstFromPath, 0);
  wil::details::in1diag3::Throw_HrIfFalseMsg(
    retaddr,
    (void *)0x1A,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\usbdevice.cpp",
    (const char *)0x80004005LL,
    Parent == 0,
    (bool)"CM_Get_Parent (%ws) failed",
    v8);
  memset_0(FileName, 0, 0x208u);
  if ( *((_QWORD *)v1 + 3) <= 7u )
    v12 = v1;
  else
    v12 = *(const char **)v1;
  v13 = USBDevice::_FormatGuidPathFromDevInst(v10, pdnDevInst, v11, FileName, pulLength);
  wil::details::in1diag3::Throw_HrIfFalseMsg(
    retaddr,
    (void *)0x1E,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\usbdevice.cpp",
    (const char *)0x80004005LL,
    v13 != 0,
    (bool)"FormatGuidPathFromDevInst (%ws) failed",
    v12);
  FileW = (char *)CreateFileW(FileName, 0xC0000000, 3u, 0, 3u, 0, 0);
  *(_QWORD *)v19 = FileW;
  wil::details::in1diag3::Throw_IfHandleInvalidMsg(
    retaddr,
    (void *)0x22,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\usbdevice.cpp",
    FileW,
    "CreateFile (%ws) failed",
    (const char *)FileName);
  PrintScanBrokerTelemetry::WriteDbgTraceInfo(
    "USBDevice::Reenumerate",
    L"Trying IOCTL_USB_HUB_CYCLE_PORT on %d",
    Buffer);
  BytesReturned = 0;
  InBuffer = Buffer;
  if ( *((_QWORD *)v1 + 3) > 7u )
    v1 = *(const char **)v1;
  v15 = DeviceIoControl(FileW, 0x220444u, &InBuffer, 8u, &InBuffer, 8u, &BytesReturned, 0);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x2A,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\usbdevice.cpp",
    (const char *)!v15,
    (bool)"IPP Mode Switch - IOCTL_USB_HUB_CYCLE_PORT (%ws) failed",
    v1);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v19);
}

```

## disassembly

```asm
0x18003010c  mov     [rsp-8+arg_8], rbx
0x180030111  mov     [rsp-8+arg_10], rsi
0x180030116  push    rbp
0x180030117  push    rdi
0x180030118  push    r15
0x18003011a  lea     rbp, [rsp-180h]
0x180030122  sub     rsp, 280h
0x180030129  mov     rax, cs:__security_cookie
0x180030130  xor     rax, rsp
0x180030133  mov     [rbp+190h+var_20], rax
0x18003013a  lea     rdi, [rcx+8]
0x18003013e  cmp     qword ptr [rdi+18h], 7
0x180030143  jbe     short loc_18003014A
0x180030145  mov     rdx, [rdi]
0x180030148  jmp     short loc_18003014D
0x18003014a  mov     rdx, rdi; unsigned __int16 *
0x18003014d  call    ?_GetDevInstFromPath@USBDevice@@AEAAKPEBG@Z; USBDevice::_GetDevInstFromPath(ushort const *)
0x180030152  mov     ebx, eax
0x180030154  cmp     qword ptr [rdi+18h], 7
0x180030159  jbe     short loc_180030160
0x18003015b  mov     rdx, [rdi]
0x18003015e  jmp     short loc_180030163
0x180030160  mov     rdx, rdi
0x180030163  test    ebx, ebx
0x180030165  setz    al
0x180030168  mov     rcx, [rbp+198h]; this
0x18003016f  mov     [rsp+290h+hTemplateFile], rdx; char *
0x180030174  lea     rdx, aGetdevinstfrom; "GetDevInstFromPath (%ws) failed"
0x18003017b  mov     qword ptr [rsp+290h+ulFlags], rdx; bool
0x180030180  mov     byte ptr [rsp+290h+pulLength], al; char
0x180030184  mov     r9d, 8007000Eh; char *
0x18003018a  lea     r15, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\printscan"...
0x180030191  mov     r8, r15; unsigned int
0x180030194  mov     edx, 12h; void *
0x180030199  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18003019e  mov     [rsp+290h+Buffer], 0
0x1800301a6  cmp     qword ptr [rdi+18h], 7
0x1800301ab  jbe     short loc_1800301B2
0x1800301ad  mov     rsi, [rdi]
0x1800301b0  jmp     short loc_1800301B5
0x1800301b2  mov     rsi, rdi
0x1800301b5  mov     [rsp+290h+var_248], 4
0x1800301bd  mov     [rsp+290h+ulFlags], 0; ulFlags
0x1800301c5  lea     rax, [rsp+290h+var_248]
0x1800301ca  mov     [rsp+290h+pulLength], rax; pulLength
0x1800301cf  lea     r9, [rsp+290h+Buffer]; Buffer
0x1800301d4  xor     r8d, r8d; pulRegDataType
0x1800301d7  lea     edx, [r8+1Dh]; ulProperty
0x1800301db  mov     ecx, ebx; dnDevInst
0x1800301dd  call    cs:__imp_CM_Get_DevNode_Registry_PropertyW
0x1800301e3  test    eax, eax
0x1800301e5  jz      short loc_180030201
0x1800301e7  mov     r8d, eax
0x1800301ea  lea     rdx, aCmGetDevnodeRe; "CM_Get_DevNode_Registry_Property(CM_DRP"...
0x1800301f1  lea     rcx, aUsbdeviceGetco; "USBDevice::_GetConnectionIndex"
0x1800301f8  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800301fd  xor     al, al
0x1800301ff  jmp     short loc_180030203
0x180030201  mov     al, 1
0x180030203  mov     rcx, [rbp+198h]; this
0x18003020a  mov     [rsp+290h+hTemplateFile], rsi; char *
0x18003020f  lea     rdx, aGetconnectioni; "GetConnectionIndex (%ws) failed"
0x180030216  mov     qword ptr [rsp+290h+ulFlags], rdx; bool
0x18003021b  mov     byte ptr [rsp+290h+pulLength], al; char
0x18003021f  mov     r9d, 80004005h; char *
0x180030225  mov     r8, r15; unsigned int
0x180030228  mov     edx, 16h; void *
0x18003022d  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x180030232  mov     [rsp+290h+pdnDevInst], 0
0x18003023a  cmp     qword ptr [rdi+18h], 7
0x18003023f  jbe     short loc_180030246
0x180030241  mov     rsi, [rdi]
0x180030244  jmp     short loc_180030249
0x180030246  mov     rsi, rdi
0x180030249  xor     r8d, r8d; ulFlags
0x18003024c  mov     edx, ebx; dnDevInst
0x18003024e  lea     rcx, [rsp+290h+pdnDevInst]; pdnDevInst
0x180030253  call    cs:__imp_CM_Get_Parent
0x180030259  test    eax, eax
0x18003025b  setz    al
0x18003025e  mov     rcx, [rbp+198h]; this
0x180030265  mov     [rsp+290h+hTemplateFile], rsi; char *
0x18003026a  lea     rdx, aCmGetParentWsF; "CM_Get_Parent (%ws) failed"
0x180030271  mov     qword ptr [rsp+290h+ulFlags], rdx; bool
0x180030276  mov     byte ptr [rsp+290h+pulLength], al; int
0x18003027a  mov     r9d, 80004005h; char *
0x180030280  mov     r8, r15; unsigned int
0x180030283  mov     edx, 1Ah; void *
0x180030288  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x18003028d  xor     edx, edx; Val
0x18003028f  mov     r8d, 208h; Size
0x180030295  lea     rcx, [rsp+290h+FileName]; void *
0x18003029a  call    memset_0
0x18003029f  cmp     qword ptr [rdi+18h], 7
0x1800302a4  jbe     short loc_1800302AB
0x1800302a6  mov     rbx, [rdi]
0x1800302a9  jmp     short loc_1800302AE
0x1800302ab  mov     rbx, rdi
0x1800302ae  lea     r9, [rsp+290h+FileName]; unsigned __int16 *
0x1800302b3  mov     edx, [rsp+290h+pdnDevInst]; unsigned int
0x1800302b7  call    ?_FormatGuidPathFromDevInst@USBDevice@@AEAAHKPEBU_GUID@@PEAGH@Z; USBDevice::_FormatGuidPathFromDevInst(ulong,_GUID const *,ushort *,int)
0x1800302bc  test    eax, eax
0x1800302be  setnz   al
0x1800302c1  mov     rcx, [rbp+198h]; this
0x1800302c8  mov     [rsp+290h+hTemplateFile], rbx; char *
0x1800302cd  lea     rdx, aFormatguidpath; "FormatGuidPathFromDevInst (%ws) failed"
0x1800302d4  mov     qword ptr [rsp+290h+ulFlags], rdx; bool
0x1800302d9  mov     byte ptr [rsp+290h+pulLength], al; char
0x1800302dd  mov     r9d, 80004005h; char *
0x1800302e3  mov     r8, r15; unsigned int
0x1800302e6  mov     edx, 1Eh; void *
0x1800302eb  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800302f0  mov     [rsp+290h+hTemplateFile], 0; hTemplateFile
0x1800302f9  mov     [rsp+290h+ulFlags], 0; dwFlagsAndAttributes
0x180030301  mov     r8d, 3; dwShareMode
0x180030307  mov     dword ptr [rsp+290h+pulLength], r8d; dwCreationDisposition
0x18003030c  xor     r9d, r9d; lpSecurityAttributes
0x18003030f  mov     edx, 0C0000000h; dwDesiredAccess
0x180030314  lea     rcx, [rsp+290h+FileName]; lpFileName
0x180030319  call    cs:__imp_CreateFileW
0x18003031f  mov     rbx, rax
0x180030322  mov     qword ptr [rsp+290h+var_248], rax
0x180030327  mov     rcx, [rbp+198h]; this
0x18003032e  lea     rax, [rsp+290h+FileName]
0x180030333  mov     qword ptr [rsp+290h+ulFlags], rax; char *
0x180030338  lea     rax, aCreatefileWsFa; "CreateFile (%ws) failed"
0x18003033f  mov     [rsp+290h+pulLength], rax; void *
0x180030344  mov     r9, rbx; char *
0x180030347  mov     r8, r15; unsigned int
0x18003034a  mov     edx, 22h ; '"'; void *
0x18003034f  call    ?Throw_IfHandleInvalidMsg@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_IfHandleInvalidMsg(void *,uint,char const *,void *,char const *,...)
0x180030354  mov     r8d, [rsp+290h+Buffer]
0x180030359  lea     rdx, aTryingIoctlUsb; "Trying IOCTL_USB_HUB_CYCLE_PORT on %d"
0x180030360  lea     rcx, aUsbdeviceReenu; "USBDevice::Reenumerate"
0x180030367  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18003036c  mov     [rsp+290h+BytesReturned], 0
0x180030374  mov     [rsp+290h+InBuffer], 0
0x18003037d  mov     eax, [rsp+290h+Buffer]
0x180030381  mov     dword ptr [rsp+290h+InBuffer], eax
0x180030385  cmp     qword ptr [rdi+18h], 7
0x18003038a  jbe     short loc_18003038F
0x18003038c  mov     rdi, [rdi]
0x18003038f  mov     [rsp+290h+lpOverlapped], 0; lpOverlapped
0x180030398  lea     rax, [rsp+290h+BytesReturned]
0x18003039d  mov     [rsp+290h+hTemplateFile], rax; lpBytesReturned
0x1800303a2  mov     r9d, 8; nInBufferSize
0x1800303a8  mov     [rsp+290h+ulFlags], r9d; nOutBufferSize
0x1800303ad  lea     rax, [rsp+290h+InBuffer]
0x1800303b2  mov     [rsp+290h+pulLength], rax; lpOutBuffer
0x1800303b7  lea     r8, [rsp+290h+InBuffer]; lpInBuffer
0x1800303bc  mov     edx, 220444h; dwIoControlCode
0x1800303c1  mov     rcx, rbx; hDevice
0x1800303c4  call    cs:__imp_DeviceIoControl
0x1800303ca  test    eax, eax
0x1800303cc  setz    al
0x1800303cf  mov     rcx, [rbp+198h]; this
0x1800303d6  mov     qword ptr [rsp+290h+ulFlags], rdi; char *
0x1800303db  lea     rdx, aIppModeSwitchI; "IPP Mode Switch - IOCTL_USB_HUB_CYCLE_P"...
0x1800303e2  mov     [rsp+290h+pulLength], rdx; bool
0x1800303e7  movzx   r9d, al; char *
0x1800303eb  mov     r8, r15; unsigned int
0x1800303ee  mov     edx, 2Ah ; '*'; void *
0x1800303f3  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800303f8  nop
0x1800303f9  lea     rcx, [rsp+290h+var_248]
0x1800303fe  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180030403  mov     rcx, [rbp+190h+var_20]
0x18003040a  xor     rcx, rsp; StackCookie
0x18003040d  call    __security_check_cookie
0x180030412  lea     r11, [rsp+290h+var_10]
0x18003041a  mov     rbx, [r11+28h]
0x18003041e  mov     rsi, [r11+30h]
0x180030422  mov     rsp, r11
0x180030425  pop     r15
0x180030427  pop     rdi
0x180030428  pop     rbp
0x180030429  retn
```
