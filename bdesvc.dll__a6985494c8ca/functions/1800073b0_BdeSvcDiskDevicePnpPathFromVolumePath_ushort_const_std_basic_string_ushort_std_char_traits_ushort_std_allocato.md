# BdeSvcDiskDevicePnpPathFromVolumePath(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800073b0`
- end: `0x180007d07`
- name: `?BdeSvcDiskDevicePnpPathFromVolumePath@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `2391`
- prototype: `__int64 __fastcall(const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180006940`

## callees

- `0x180006260`
- `0x1800073b0`
- `0x180009f30`
- `0x180009f60`
- `0x18000f7e0`
- `0x18002cac4`
- `0x18002f5f4`
- `0x180034070`
- `0x1800484bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007a8e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007bce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007c6a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007a8e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007bce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007c6a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007599`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800078cd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007599`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800078cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000747b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000776f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ae8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000747b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000776f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ae8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c49`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007461`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800079ff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007461`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800079ff`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007522`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007622`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007ad8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007522`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007622`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007ad8`
- `DEVOBJ!DevObjGetClassDevs` at `0x18000775c`
- `DEVOBJ!DevObjGetClassDevs` at `0x18000775c`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180007815`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180007815`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18000789b`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180007952`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18000789b`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180007952`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180007a76`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180007a76`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800076d4`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800076d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BdeSvcDiskDevicePnpPathFromVolumePath(const WCHAR *a1, __int64 a2)
{
  const WCHAR *v2; // r15
  unsigned int v3; // r12d
  HANDLE FileW; // r14
  signed int LastError; // eax
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  __int64 v8; // rsi
  _DWORD *v9; // r13
  signed int v10; // eax
  _QWORD *v11; // rcx
  int v12; // edx
  __int64 DeviceInfoList; // rax
  __int64 v14; // rbx
  signed int v15; // eax
  WCHAR *v16; // rsi
  signed int v17; // eax
  signed int v18; // eax
  __int64 v19; // rax
  int DeviceInterfaceDetail; // ebx
  DWORD v21; // eax
  WCHAR *v22; // rax
  WCHAR *v23; // rbx
  const WCHAR *v24; // r12
  signed int v25; // eax
  HANDLE v26; // rax
  signed int v27; // eax
  signed int v28; // eax
  char dwCreationDisposition; // [rsp+20h] [rbp-1E8h]
  __int64 hObject; // [rsp+40h] [rbp-1C8h]
  WCHAR *v32; // [rsp+48h] [rbp-1C0h]
  int v33; // [rsp+50h] [rbp-1B8h]
  int i; // [rsp+54h] [rbp-1B4h]
  __int64 v35; // [rsp+58h] [rbp-1B0h]
  _BYTE *v36; // [rsp+60h] [rbp-1A8h]
  DWORD BytesReturned; // [rsp+88h] [rbp-180h] BYREF
  unsigned int Size; // [rsp+8Ch] [rbp-17Ch] BYREF
  DWORD Size_4; // [rsp+90h] [rbp-178h] BYREF
  __int64 v42; // [rsp+98h] [rbp-170h] BYREF
  int v43; // [rsp+A0h] [rbp-168h]
  _OWORD v44[2]; // [rsp+A8h] [rbp-160h] BYREF
  _BYTE OutBuffer[256]; // [rsp+D0h] [rbp-138h] BYREF

  v2 = a1;
  v3 = 0;
  BytesReturned = 0;
  v42 = 0;
  v43 = 0;
  Size_4 = 256;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
  FileW = CreateFileW(v2, 0, 1u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        150,
        (unsigned int)WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
        (_DWORD)v2,
        v6);
      goto LABEL_94;
    }
    goto LABEL_95;
  }
  v8 = -1;
  hObject = -1;
  v9 = OutBuffer;
  v36 = OutBuffer;
  if ( !DeviceIoControl(FileW, 0x560000u, 0, 0, OutBuffer, Size_4, &BytesReturned, 0) )
  {
    if ( GetLastError() != 234 )
    {
      v6 = -2147418113;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_LSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v2, 255);
      goto LABEL_89;
    }
    v9 = malloc(BytesReturned);
    v36 = v9;
    if ( !v9 )
    {
      v6 = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
      goto LABEL_89;
    }
    Size_4 = BytesReturned;
    if ( !DeviceIoControl(FileW, 0x560000u, 0, 0, v9, BytesReturned, &BytesReturned, 0) )
    {
      v10 = GetLastError();
      v6 = v10;
      if ( v10 > 0 )
        v6 = (unsigned __int16)v10 | 0x80070000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_89;
      v12 = 153;
      dwCreationDisposition = v6;
LABEL_25:
      WPP_SF_SD(
        v11[2],
        v12,
        (unsigned int)WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
        (_DWORD)v2,
        dwCreationDisposition);
      goto LABEL_89;
    }
  }
  if ( *v9 != 1 )
  {
    v6 = -2147024846;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_89;
    v12 = 154;
    dwCreationDisposition = 50;
    goto LABEL_25;
  }
  v33 = v9[2];
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v14 = DeviceInfoList;
  v35 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    v15 = GetLastError();
    v6 = v15;
    if ( v15 > 0 )
      v6 = (unsigned __int16)v15 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v6);
    goto LABEL_89;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_DISK, 0, 18, 0, 0) )
  {
    v16 = 0;
    v17 = GetLastError();
    v6 = v17;
    if ( v17 > 0 )
      v6 = (unsigned __int16)v17 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v6);
    goto LABEL_73;
  }
  for ( i = 0; ; ++i )
  {
    Size = 0;
    memset(v44, 0, sizeof(v44));
    LODWORD(v44[0]) = 32;
    if ( !(unsigned int)DevObjEnumDeviceInterfaces(v14, 0, &GUID_DEVINTERFACE_DISK, v3, v44) )
    {
      v18 = GetLastError();
      v6 = v18;
      if ( v18 > 0 )
        v6 = (unsigned __int16)v18 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v6);
      goto LABEL_49;
    }
    DeviceInterfaceDetail = DevObjGetDeviceInterfaceDetail(v14, v44, 0, 0, &Size, 0);
    v21 = GetLastError();
    if ( DeviceInterfaceDetail || v21 != 122 )
    {
      v6 = -2147418113;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
        v19 = -1;
        v16 = 0;
        goto LABEL_74;
      }
LABEL_49:
      v19 = -1;
      v16 = 0;
      goto LABEL_74;
    }
    v22 = (WCHAR *)malloc(Size);
    v23 = v22;
    v32 = v22;
    if ( !v22 )
    {
      v6 = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
LABEL_56:
      v19 = -1;
      v16 = v32;
      goto LABEL_74;
    }
    v24 = v22 + 2;
    v22[2] = 0;
    *(_DWORD *)v22 = 8;
    if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(v35, v44, v22, Size, 0, 0) )
    {
      v25 = GetLastError();
      v6 = v25;
      if ( v25 > 0 )
        v6 = (unsigned __int16)v25 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 160, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v6);
        v19 = -1;
        v16 = v32;
        goto LABEL_74;
      }
      goto LABEL_56;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v24);
    v26 = CreateFileW(v24, 0, 1u, 0, 3u, 0, 0);
    hObject = (__int64)v26;
    if ( v26 == (HANDLE)-1LL )
    {
      v27 = GetLastError();
      v6 = v27;
      if ( v27 > 0 )
        v6 = (unsigned __int16)v27 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          162,
          (unsigned int)WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
          (_DWORD)v24,
          v6);
      goto LABEL_72;
    }
    if ( !DeviceIoControl(v26, 0x2D1080u, 0, 0, &v42, 0xCu, &Size_4, 0) )
    {
      v28 = GetLastError();
      v6 = v28;
      if ( v28 > 0 )
        v6 = (unsigned __int16)v28 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          163,
          (unsigned int)WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
          (_DWORD)v24,
          v6);
      goto LABEL_72;
    }
    CloseHandle((HANDLE)hObject);
    hObject = -1;
    if ( HIDWORD(v42) == v33 )
      break;
    v3 = i + 1;
    free(v23);
    v14 = v35;
  }
  do
    ++v8;
  while ( v24[v8] );
  try
  {
    std::wstring::_Assign<unsigned short>(a2, v24, v8);
    v6 = 0;
  }
  catch ( ... )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
    v6 = -2147024882;
    v19 = -1;
    v16 = v32;
    v9 = v36;
    v2 = a1;
    goto LABEL_74;
  }
LABEL_72:
  v16 = v32;
LABEL_73:
  v19 = hObject;
LABEL_74:
  hObject = v19;
  DevObjDestroyDeviceInfoList(v35);
  if ( v16 )
    free(v16);
LABEL_89:
  CloseHandle(FileW);
  if ( hObject != -1 )
    CloseHandle((HANDLE)hObject);
  if ( v9 && v9 != (_DWORD *)OutBuffer )
    free(v9);
LABEL_94:
  v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_95:
  if ( v6 == -2147024637 )
  {
    v6 = -2147023728;
    if ( v7 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v7 + 28) & 2) != 0 )
      {
        WPP_SF_S(v7[2], 165, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v2);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_99;
    }
  }
  else
  {
LABEL_99:
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
      WPP_SF_d(v7[2], 166, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x1800073b0  mov     [rsp+arg_10], rbx
0x1800073b5  mov     [rsp+arg_18], rsi
0x1800073ba  push    rdi
0x1800073bb  push    r12
0x1800073bd  push    r13
0x1800073bf  push    r14
0x1800073c1  push    r15
0x1800073c3  sub     rsp, 1E0h
0x1800073ca  mov     rax, cs:__security_cookie
0x1800073d1  xor     rax, rsp
0x1800073d4  mov     [rsp+208h+var_38], rax
0x1800073dc  mov     [rsp+208h+var_1A0], rdx
0x1800073e1  mov     r15, rcx
0x1800073e4  mov     [rsp+208h+var_188], rcx
0x1800073ec  xor     r12d, r12d
0x1800073ef  mov     [rsp+208h+BytesReturned], r12d
0x1800073f7  xor     eax, eax
0x1800073f9  mov     [rsp+208h+var_170], rax
0x180007401  mov     [rsp+208h+var_168], eax
0x180007408  mov     dword ptr [rsp+208h+Size+4], 100h
0x180007413  lea     rdi, WPP_GLOBAL_Control
0x18000741a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007421  cmp     rcx, rdi
0x180007424  jz      short loc_180007441
0x180007426  test    byte ptr [rcx+1Ch], 20h
0x18000742a  jz      short loc_180007441
0x18000742c  mov     edx, 95h
0x180007431  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180007438  mov     rcx, [rcx+10h]
0x18000743c  call    WPP_SF_
0x180007441  mov     [rsp+208h+hTemplateFile], r12; hTemplateFile
0x180007446  mov     [rsp+208h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18000744b  mov     [rsp+208h+dwCreationDisposition], 3; dwCreationDisposition
0x180007453  xor     r9d, r9d; lpSecurityAttributes
0x180007456  xor     edx, edx; dwDesiredAccess
0x180007458  mov     r8d, 1; dwShareMode
0x18000745e  mov     rcx, r15; lpFileName
0x180007461  call    cs:__imp_CreateFileW
0x180007468  nop     dword ptr [rax+rax+00h]
0x18000746d  mov     r14, rax
0x180007470  mov     [rsp+208h+var_198], rax
0x180007475  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007479  jnz     short loc_1800074D1
0x18000747b  call    cs:__imp_GetLastError
0x180007482  nop     dword ptr [rax+rax+00h]
0x180007487  mov     ebx, eax
0x180007489  test    eax, eax
0x18000748b  jle     short loc_180007496
0x18000748d  movzx   ebx, ax
0x180007490  or      ebx, 80070000h
0x180007496  mov     rcx, cs:WPP_GLOBAL_Control
0x18000749d  cmp     rcx, rdi
0x1800074a0  jz      loc_180007C7D
0x1800074a6  test    byte ptr [rcx+1Ch], 2
0x1800074aa  jz      loc_180007C7D
0x1800074b0  mov     edx, 96h
0x1800074b5  mov     [rsp+208h+dwCreationDisposition], ebx
0x1800074b9  mov     r9, r15
0x1800074bc  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x1800074c3  mov     rcx, [rcx+10h]
0x1800074c7  call    WPP_SF_SD
0x1800074cc  jmp     loc_180007C76
0x1800074d1  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800074d8  mov     [rsp+208h+hObject], rsi
0x1800074dd  lea     r13, [rsp+208h+OutBuffer]
0x1800074e5  mov     [rsp+208h+var_1A8], r13
0x1800074ea  mov     [rsp+208h+lpOverlapped], r12; lpOverlapped
0x1800074ef  lea     rax, [rsp+208h+BytesReturned]
0x1800074f7  mov     [rsp+208h+hTemplateFile], rax; lpBytesReturned
0x1800074fc  mov     eax, dword ptr [rsp+208h+Size+4]
0x180007503  mov     [rsp+208h+dwFlagsAndAttributes], eax; nOutBufferSize
0x180007507  lea     rax, [rsp+208h+OutBuffer]
0x18000750f  mov     qword ptr [rsp+208h+dwCreationDisposition], rax; lpOutBuffer
0x180007514  xor     r9d, r9d; nInBufferSize
0x180007517  xor     r8d, r8d; lpInBuffer
0x18000751a  mov     edx, 560000h; dwIoControlCode
0x18000751f  mov     rcx, r14; hDevice
0x180007522  call    cs:__imp_DeviceIoControl
0x180007529  nop     dword ptr [rax+rax+00h]
0x18000752e  test    eax, eax
0x180007530  jnz     loc_180007688
0x180007536  call    cs:__imp_GetLastError
0x18000753d  nop     dword ptr [rax+rax+00h]
0x180007542  cmp     eax, 0EAh
0x180007547  jz      short loc_180007592
0x180007549  mov     ebx, 8000FFFFh
0x18000754e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007555  cmp     rcx, rdi
0x180007558  jz      loc_180007C2C
0x18000755e  test    byte ptr [rcx+1Ch], 2
0x180007562  jz      loc_180007C2C
0x180007568  mov     edx, 97h
0x18000756d  mov     [rsp+208h+dwFlagsAndAttributes], 8000FFFFh; char
0x180007575  mov     qword ptr [rsp+208h+dwCreationDisposition], r15; __int64
0x18000757a  mov     r9d, eax
0x18000757d  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180007584  mov     rcx, [rcx+10h]; LoggerHandle
0x180007588  call    WPP_SF_LSD
0x18000758d  jmp     loc_180007C2C
0x180007592  mov     ecx, [rsp+208h+BytesReturned]; Size
0x180007599  call    cs:__imp_malloc
0x1800075a0  nop     dword ptr [rax+rax+00h]
0x1800075a5  mov     r13, rax
0x1800075a8  mov     [rsp+208h+var_1A8], rax
0x1800075ad  test    rax, rax
0x1800075b0  jnz     short loc_1800075EB
0x1800075b2  mov     ebx, 8007000Eh
0x1800075b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075be  cmp     rcx, rdi
0x1800075c1  jz      loc_180007C2C
0x1800075c7  test    byte ptr [rcx+1Ch], 2
0x1800075cb  jz      loc_180007C2C
0x1800075d1  mov     edx, 98h
0x1800075d6  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x1800075dd  mov     rcx, [rcx+10h]
0x1800075e1  call    WPP_SF_
0x1800075e6  jmp     loc_180007C2C
0x1800075eb  mov     eax, [rsp+208h+BytesReturned]
0x1800075f2  mov     dword ptr [rsp+208h+Size+4], eax
0x1800075f9  mov     [rsp+208h+lpOverlapped], r12; lpOverlapped
0x1800075fe  lea     rcx, [rsp+208h+BytesReturned]
0x180007606  mov     [rsp+208h+hTemplateFile], rcx; lpBytesReturned
0x18000760b  mov     [rsp+208h+dwFlagsAndAttributes], eax; nOutBufferSize
0x18000760f  mov     qword ptr [rsp+208h+dwCreationDisposition], r13; lpOutBuffer
0x180007614  xor     r9d, r9d; nInBufferSize
0x180007617  xor     r8d, r8d; lpInBuffer
0x18000761a  mov     edx, 560000h; dwIoControlCode
0x18000761f  mov     rcx, r14; hDevice
0x180007622  call    cs:__imp_DeviceIoControl
0x180007629  nop     dword ptr [rax+rax+00h]
0x18000762e  test    eax, eax
0x180007630  jnz     short loc_180007688
0x180007632  call    cs:__imp_GetLastError
0x180007639  nop     dword ptr [rax+rax+00h]
0x18000763e  mov     ebx, eax
0x180007640  test    eax, eax
0x180007642  jle     short loc_18000764D
0x180007644  movzx   ebx, ax
0x180007647  or      ebx, 80070000h
0x18000764d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007654  cmp     rcx, rdi
0x180007657  jz      loc_180007C2C
0x18000765d  test    byte ptr [rcx+1Ch], 2
0x180007661  jz      loc_180007C2C
0x180007667  mov     edx, 99h
0x18000766c  mov     [rsp+208h+dwCreationDisposition], ebx
0x180007670  mov     r9, r15
0x180007673  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000767a  mov     rcx, [rcx+10h]
0x18000767e  call    WPP_SF_SD
0x180007683  jmp     loc_180007C2C
0x180007688  cmp     dword ptr [r13+0], 1
0x18000768d  jz      short loc_1800076BD
0x18000768f  mov     ebx, 80070032h
0x180007694  mov     rcx, cs:WPP_GLOBAL_Control
0x18000769b  cmp     rcx, rdi
0x18000769e  jz      loc_180007C2C
0x1800076a4  test    byte ptr [rcx+1Ch], 2
0x1800076a8  jz      loc_180007C2C
0x1800076ae  mov     edx, 9Ah
0x1800076b3  mov     [rsp+208h+dwCreationDisposition], 80070032h
0x1800076bb  jmp     short loc_180007670
0x1800076bd  mov     eax, [r13+8]
0x1800076c1  mov     [rsp+208h+var_1B8], eax
0x1800076c5  mov     qword ptr [rsp+208h+dwCreationDisposition], r12
0x1800076ca  xor     r9d, r9d
0x1800076cd  xor     r8d, r8d
0x1800076d0  xor     edx, edx
0x1800076d2  xor     ecx, ecx
0x1800076d4  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800076db  nop     dword ptr [rax+rax+00h]
0x1800076e0  mov     rbx, rax
0x1800076e3  mov     [rsp+208h+var_1B0], rax
0x1800076e8  cmp     rax, rsi
0x1800076eb  jnz     short loc_18000773F
0x1800076ed  call    cs:__imp_GetLastError
0x1800076f4  nop     dword ptr [rax+rax+00h]
0x1800076f9  mov     ebx, eax
0x1800076fb  test    eax, eax
0x1800076fd  jle     short loc_180007708
0x1800076ff  movzx   ebx, ax
0x180007702  or      ebx, 80070000h
0x180007708  mov     rcx, cs:WPP_GLOBAL_Control
0x18000770f  cmp     rcx, rdi
0x180007712  jz      loc_180007C2C
0x180007718  test    byte ptr [rcx+1Ch], 2
0x18000771c  jz      loc_180007C2C
0x180007722  mov     edx, 9Bh
0x180007727  mov     r9d, ebx
0x18000772a  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180007731  mov     rcx, [rcx+10h]
0x180007735  call    WPP_SF_d
0x18000773a  jmp     loc_180007C2C
0x18000773f  mov     qword ptr [rsp+208h+dwFlagsAndAttributes], r12
0x180007744  mov     qword ptr [rsp+208h+dwCreationDisposition], r12
0x180007749  mov     r9d, 12h
0x18000774f  xor     r8d, r8d
0x180007752  lea     rdx, GUID_DEVINTERFACE_DISK
0x180007759  mov     rcx, rax
0x18000775c  call    cs:__imp_DevObjGetClassDevs
0x180007763  nop     dword ptr [rax+rax+00h]
0x180007768  test    eax, eax
0x18000776a  jnz     short loc_1800077C1
0x18000776c  mov     rsi, r12
0x18000776f  call    cs:__imp_GetLastError
0x180007776  nop     dword ptr [rax+rax+00h]
0x18000777b  mov     ebx, eax
0x18000777d  test    eax, eax
0x18000777f  jle     short loc_18000778A
0x180007781  movzx   ebx, ax
0x180007784  or      ebx, 80070000h
0x18000778a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007791  cmp     rcx, rdi
0x180007794  jz      loc_180007A67
0x18000779a  test    byte ptr [rcx+1Ch], 2
0x18000779e  jz      loc_180007A67
0x1800077a4  mov     edx, 9Ch
0x1800077a9  mov     r9d, ebx
0x1800077ac  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x1800077b3  mov     rcx, [rcx+10h]
0x1800077b7  call    WPP_SF_d
0x1800077bc  jmp     loc_180007A67
0x1800077c1  mov     [rsp+208h+var_1B4], r12d
0x1800077c6  nop     word ptr [rax+rax+00000000h]
0x1800077d0  mov     dword ptr [rsp+208h+Size], 0
0x1800077db  xorps   xmm0, xmm0
0x1800077de  movups  [rsp+208h+var_160], xmm0
0x1800077e6  movups  [rsp+208h+var_150], xmm0
0x1800077ee  mov     dword ptr [rsp+208h+var_160], 20h ; ' '
0x1800077f9  lea     rax, [rsp+208h+var_160]
0x180007801  mov     qword ptr [rsp+208h+dwCreationDisposition], rax
0x180007806  mov     r9d, r12d
0x180007809  lea     r8, GUID_DEVINTERFACE_DISK
0x180007810  xor     edx, edx
0x180007812  mov     rcx, rbx
0x180007815  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18000781c  nop     dword ptr [rax+rax+00h]
0x180007821  test    eax, eax
0x180007823  jnz     short loc_180007874
0x180007825  call    cs:__imp_GetLastError
0x18000782c  nop     dword ptr [rax+rax+00h]
0x180007831  mov     ebx, eax
0x180007833  test    eax, eax
0x180007835  jle     short loc_180007840
0x180007837  movzx   ebx, ax
0x18000783a  or      ebx, 80070000h
0x180007840  mov     rcx, cs:WPP_GLOBAL_Control
0x180007847  cmp     rcx, rdi
0x18000784a  jz      short loc_18000786A
0x18000784c  test    byte ptr [rcx+1Ch], 2
0x180007850  jz      short loc_18000786A
0x180007852  mov     edx, 9Dh
0x180007857  mov     r9d, ebx
0x18000785a  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180007861  mov     rcx, [rcx+10h]
0x180007865  call    WPP_SF_d
0x18000786a  mov     rax, rsi
0x18000786d  xor     esi, esi
0x18000786f  jmp     loc_180007A6C
0x180007874  mov     qword ptr [rsp+208h+dwFlagsAndAttributes], 0
0x18000787d  lea     rax, [rsp+208h+Size]
0x180007885  mov     qword ptr [rsp+208h+dwCreationDisposition], rax
0x18000788a  xor     r9d, r9d
0x18000788d  xor     r8d, r8d
0x180007890  lea     rdx, [rsp+208h+var_160]
0x180007898  mov     rcx, rbx
0x18000789b  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1800078a2  nop     dword ptr [rax+rax+00h]
0x1800078a7  mov     ebx, eax
0x1800078a9  call    cs:__imp_GetLastError
0x1800078b0  nop     dword ptr [rax+rax+00h]
0x1800078b5  test    ebx, ebx
0x1800078b7  jnz     loc_180007BE4
0x1800078bd  cmp     eax, 7Ah ; 'z'
0x1800078c0  jnz     loc_180007BE4
0x1800078c6  mov     ecx, dword ptr [rsp+208h+Size]; Size
0x1800078cd  call    cs:__imp_malloc
0x1800078d4  nop     dword ptr [rax+rax+00h]
0x1800078d9  mov     rbx, rax
0x1800078dc  mov     [rsp+208h+var_1C0], rax
0x1800078e1  test    rax, rax
0x1800078e4  jnz     short loc_18000791F
0x1800078e6  mov     ebx, 8007000Eh
0x1800078eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078f2  cmp     rcx, rdi
0x1800078f5  jz      short loc_180007912
0x1800078f7  test    byte ptr [rcx+1Ch], 2
0x1800078fb  jz      short loc_180007912
0x1800078fd  mov     edx, 9Fh
0x180007902  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180007909  mov     rcx, [rcx+10h]
0x18000790d  call    WPP_SF_
0x180007912  mov     rax, rsi
0x180007915  mov     rsi, [rsp+208h+var_1C0]
0x18000791a  jmp     loc_180007A6C
0x18000791f  lea     r12, [rax+4]
0x180007923  xor     ecx, ecx
0x180007925  mov     [r12], cx
0x18000792a  mov     dword ptr [rax], 8
0x180007930  mov     qword ptr [rsp+208h+dwFlagsAndAttributes], rcx
  ... truncated ...
```
