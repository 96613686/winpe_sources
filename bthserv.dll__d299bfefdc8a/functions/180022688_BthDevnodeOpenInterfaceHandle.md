# BthDevnodeOpenInterfaceHandle

- ea: `0x180022688`
- end: `0x1800228f3`
- name: `BthDevnodeOpenInterfaceHandle`
- size: `619`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18002103c`
- `0x1800237e8`
- `0x180024004`
- `0x18002b154`

## callees

- `0x180001790`
- `0x180002470`
- `0x18000247c`
- `0x1800024ac`
- `0x180022688`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002283f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002283f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022890`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022881`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022881`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800226cd`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800226cd`
- `DEVOBJ!DevObjGetClassDevs` at `0x180022721`
- `DEVOBJ!DevObjGetClassDevs` at `0x180022721`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800228c5`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800228c5`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180022759`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180022759`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800227ad`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180022835`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800227ad`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180022835`

## pseudocode

```c
__int64 __fastcall BthDevnodeOpenInterfaceHandle(__int64 a1, DWORD a2, _QWORD *a3)
{
  __int64 DeviceInfoList; // rbp
  signed int LastError; // eax
  signed int v7; // ebx
  signed int v8; // eax
  signed int v9; // eax
  unsigned int v10; // esi
  WCHAR *v11; // rdi
  signed int v12; // eax
  HANDLE FileW; // rsi
  signed int v14; // eax
  size_t Size; // [rsp+40h] [rbp-58h] BYREF
  _OWORD v17[2]; // [rsp+48h] [rbp-50h] BYREF

  *a3 = -1;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( DeviceInfoList != -1 )
    goto LABEL_37;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_37:
    if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_BTHPORT_DEVICE_INTERFACE, 0, 18, 0, 0)
      || (memset(v17, 0, sizeof(v17)),
          LODWORD(v17[0]) = 32,
          !(unsigned int)DevObjEnumDeviceInterfaces(DeviceInfoList, 0, &GUID_BTHPORT_DEVICE_INTERFACE, 0, v17)) )
    {
      v8 = GetLastError();
      v7 = v8;
      if ( v8 > 0 )
        v7 = (unsigned __int16)v8 | 0x80070000;
      if ( v7 >= 0 )
        v7 = -2147467259;
      goto LABEL_32;
    }
    LODWORD(Size) = 0;
    if ( (unsigned int)DevObjGetDeviceInterfaceDetail(DeviceInfoList, v17, 0, 0, &Size, 0) )
      goto LABEL_31;
    v9 = GetLastError();
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    if ( v9 != -2147024774 || (v10 = Size) == 0 )
    {
LABEL_31:
      v7 = -2147418113;
LABEL_32:
      if ( DeviceInfoList != -1 )
        DevObjDestroyDeviceInfoList(DeviceInfoList);
      return (unsigned int)v7;
    }
    v11 = (WCHAR *)o_malloc_0((unsigned int)Size);
    v7 = v11 == 0 ? 0x8007000E : 0;
    if ( !v11 )
      goto LABEL_32;
    memset_0(v11, 0, v10);
    *(_DWORD *)v11 = 8;
    if ( (unsigned int)DevObjGetDeviceInterfaceDetail(DeviceInfoList, v17, v11, v10, 0, 0) )
    {
      FileW = CreateFileW(v11 + 2, 0xC0000000, 3u, 0, 3u, a2, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        v14 = GetLastError();
        v7 = v14;
        if ( v14 > 0 )
          v7 = (unsigned __int16)v14 | 0x80070000;
        if ( v7 < 0 )
          goto LABEL_30;
      }
      else
      {
        v7 = 0;
      }
      *a3 = FileW;
    }
    else
    {
      v12 = GetLastError();
      v7 = v12;
      if ( v12 > 0 )
        v7 = (unsigned __int16)v12 | 0x80070000;
      if ( v7 >= 0 )
        v7 = -2147467259;
    }
LABEL_30:
    free(v11);
    goto LABEL_32;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180022688  mov     [rsp+arg_0], rbx
0x18002268d  mov     [rsp+arg_18], rbp
0x180022692  push    rsi
0x180022693  push    rdi
0x180022694  push    r13
0x180022696  push    r14
0x180022698  push    r15
0x18002269a  sub     rsp, 70h
0x18002269e  mov     rax, cs:__security_cookie
0x1800226a5  xor     rax, rsp
0x1800226a8  mov     [rsp+98h+var_30], rax
0x1800226ad  mov     r14, r8
0x1800226b0  mov     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x1800226b7  mov     r15d, edx
0x1800226ba  mov     qword ptr [rsp+98h+dwCreationDisposition], 0
0x1800226c3  xor     r8d, r8d
0x1800226c6  xor     edx, edx
0x1800226c8  xor     r9d, r9d
0x1800226cb  xor     ecx, ecx
0x1800226cd  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800226d3  mov     rbp, rax
0x1800226d6  mov     r13d, 80070000h
0x1800226dc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800226e0  jnz     short loc_1800226FC
0x1800226e2  call    cs:__imp_GetLastError
0x1800226e8  mov     ebx, eax
0x1800226ea  test    eax, eax
0x1800226ec  jle     short loc_1800226F4
0x1800226ee  movzx   ebx, ax
0x1800226f1  or      ebx, r13d
0x1800226f4  test    ebx, ebx
0x1800226f6  js      loc_1800228CB
0x1800226fc  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], 0
0x180022705  lea     rdx, GUID_BTHPORT_DEVICE_INTERFACE
0x18002270c  mov     r9d, 12h
0x180022712  mov     qword ptr [rsp+98h+dwCreationDisposition], 0
0x18002271b  xor     r8d, r8d
0x18002271e  mov     rcx, rbp
0x180022721  call    cs:__imp_DevObjGetClassDevs
0x180022727  test    eax, eax
0x180022729  jz      short loc_180022763
0x18002272b  xorps   xmm0, xmm0
0x18002272e  lea     rax, [rsp+98h+var_50]
0x180022733  movups  [rsp+98h+var_50], xmm0
0x180022738  xor     r9d, r9d
0x18002273b  mov     dword ptr [rsp+98h+var_50], 20h ; ' '
0x180022743  lea     r8, GUID_BTHPORT_DEVICE_INTERFACE
0x18002274a  mov     qword ptr [rsp+98h+dwCreationDisposition], rax
0x18002274f  xor     edx, edx
0x180022751  mov     rcx, rbp
0x180022754  movups  [rsp+98h+var_40], xmm0
0x180022759  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18002275f  test    eax, eax
0x180022761  jnz     short loc_180022784
0x180022763  call    cs:__imp_GetLastError
0x180022769  mov     ebx, eax
0x18002276b  test    eax, eax
0x18002276d  jle     short loc_180022775
0x18002276f  movzx   ebx, ax
0x180022772  or      ebx, r13d
0x180022775  test    ebx, ebx
0x180022777  mov     eax, 80004005h
0x18002277c  cmovns  ebx, eax
0x18002277f  jmp     loc_1800228BC
0x180022784  lea     rax, [rsp+98h+Size]
0x180022789  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], 0
0x180022792  xor     r9d, r9d
0x180022795  mov     qword ptr [rsp+98h+dwCreationDisposition], rax
0x18002279a  xor     r8d, r8d
0x18002279d  mov     dword ptr [rsp+98h+Size], 0
0x1800227a5  lea     rdx, [rsp+98h+var_50]
0x1800227aa  mov     rcx, rbp
0x1800227ad  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1800227b3  test    eax, eax
0x1800227b5  jnz     loc_1800228B7
0x1800227bb  call    cs:__imp_GetLastError
0x1800227c1  test    eax, eax
0x1800227c3  jle     short loc_1800227CB
0x1800227c5  movzx   eax, ax
0x1800227c8  or      eax, r13d
0x1800227cb  cmp     eax, 8007007Ah
0x1800227d0  jnz     loc_1800228B7
0x1800227d6  mov     esi, dword ptr [rsp+98h+Size]
0x1800227da  test    esi, esi
0x1800227dc  jz      loc_1800228B7
0x1800227e2  mov     ecx, esi; Size
0x1800227e4  call    _o_malloc_0
0x1800227e9  mov     rdi, rax
0x1800227ec  neg     rax
0x1800227ef  sbb     ebx, ebx
0x1800227f1  not     ebx
0x1800227f3  and     ebx, 8007000Eh
0x1800227f9  test    rdi, rdi
0x1800227fc  jz      loc_1800228BC
0x180022802  mov     r8d, esi; Size
0x180022805  xor     edx, edx; Val
0x180022807  mov     rcx, rdi; void *
0x18002280a  call    memset_0
0x18002280f  mov     r9d, esi
0x180022812  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], 0
0x18002281b  mov     r8, rdi
0x18002281e  mov     dword ptr [rdi], 8
0x180022824  lea     rdx, [rsp+98h+var_50]
0x180022829  mov     qword ptr [rsp+98h+dwCreationDisposition], 0
0x180022832  mov     rcx, rbp
0x180022835  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18002283b  test    eax, eax
0x18002283d  jnz     short loc_18002285C
0x18002283f  call    cs:__imp_GetLastError
0x180022845  mov     ebx, eax
0x180022847  test    eax, eax
0x180022849  jle     short loc_180022851
0x18002284b  movzx   ebx, ax
0x18002284e  or      ebx, r13d
0x180022851  test    ebx, ebx
0x180022853  js      short loc_1800228AD
0x180022855  mov     ebx, 80004005h
0x18002285a  jmp     short loc_1800228AD
0x18002285c  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x180022865  lea     rcx, [rdi+4]; lpFileName
0x180022869  mov     r8d, 3; dwShareMode
0x18002286f  mov     [rsp+98h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x180022874  xor     r9d, r9d; lpSecurityAttributes
0x180022877  mov     [rsp+98h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002287c  mov     edx, 0C0000000h; dwDesiredAccess
0x180022881  call    cs:__imp_CreateFileW
0x180022887  mov     rsi, rax
0x18002288a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002288e  jnz     short loc_1800228A8
0x180022890  call    cs:__imp_GetLastError
0x180022896  mov     ebx, eax
0x180022898  test    eax, eax
0x18002289a  jle     short loc_1800228A2
0x18002289c  movzx   ebx, ax
0x18002289f  or      ebx, r13d
0x1800228a2  test    ebx, ebx
0x1800228a4  jns     short loc_1800228AA
0x1800228a6  jmp     short loc_1800228AD
0x1800228a8  xor     ebx, ebx
0x1800228aa  mov     [r14], rsi
0x1800228ad  mov     rcx, rdi; Block
0x1800228b0  call    free
0x1800228b5  jmp     short loc_1800228BC
0x1800228b7  mov     ebx, 8000FFFFh
0x1800228bc  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x1800228c0  jz      short loc_1800228CB
0x1800228c2  mov     rcx, rbp
0x1800228c5  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1800228cb  mov     eax, ebx
0x1800228cd  mov     rcx, [rsp+98h+var_30]
0x1800228d2  xor     rcx, rsp; StackCookie
0x1800228d5  call    __security_check_cookie
0x1800228da  lea     r11, [rsp+98h+var_28]
0x1800228df  mov     rbx, [r11+30h]
0x1800228e3  mov     rbp, [r11+48h]
0x1800228e7  mov     rsp, r11
0x1800228ea  pop     r15
0x1800228ec  pop     r14
0x1800228ee  pop     r13
0x1800228f0  pop     rdi
0x1800228f1  pop     rsi
0x1800228f2  retn
```
