# CElevatedDataCollection::SpawnDataCollector(utl::unique_ptr<IFaultrepElevatedDataCollection,tlx::release_delete> *,int,ushort)

- ea: `0x14005e058`
- end: `0x14005e7cb`
- name: `?SpawnDataCollector@CElevatedDataCollection@@IEAAJPEAV?$unique_ptr@UIFaultrepElevatedDataCollection@@Urelease_delete@tlx@@@utl@@HG@Z`
- size: `1907`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14005daac`

## callees

- `0x140002490`
- `0x1400024b4`
- `0x1400030f8`
- `0x14000333f`
- `0x14000334b`
- `0x140004373`
- `0x14000437f`
- `0x140014f14`
- `0x140014f58`
- `0x1400166ec`
- `0x14002de94`
- `0x14005e058`
- `0x14005f0ac`
- `0x14005f510`
- `0x14005f588`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14005e23c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14005e23c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14005e71a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14005e71a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005e791`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005e791`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x14005e65e`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x14005e65e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14005e1c8`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14005e52e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14005e1c8`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14005e52e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14005e764`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14005e778`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14005e764`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14005e778`
- `ntdll!RtlNtStatusToDosError` at `0x14005e30b`
- `ntdll!RtlNtStatusToDosError` at `0x14005e30b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14005e3c4`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14005e3c4`

## string_xrefs

- `0x14005e2ee`: `\WindowsErrorReportingServicePort`

## pseudocode

```c
__int64 __fastcall CElevatedDataCollection::SpawnDataCollector(__int64 a1, LPVOID *a2, int a3, __int16 a4)
{
  LPVOID v7; // rcx
  IStream *v8; // rdi
  const void *v9; // rsi
  HANDLE v10; // r12
  const void *v11; // rbx
  signed int LastError_0; // eax
  int v13; // r14d
  CUserModeHangReport *v14; // rcx
  __int64 v15; // rdx
  _OWORD *v16; // rax
  signed int v17; // eax
  signed int v18; // eax
  NTSTATUS v19; // eax
  signed int v20; // eax
  CUserModeHangReport *v21; // rcx
  __int64 v22; // rdx
  DWORD v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  signed int v28; // eax
  const void *v29; // rax
  signed int v30; // eax
  signed int v31; // eax
  int RegionSize; // r14d
  IStream *v33; // rax
  LPVOID v34; // rcx
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v37; // [rsp+48h] [rbp-B8h]
  HANDLE hObject; // [rsp+50h] [rbp-B0h]
  HANDLE Handles[2]; // [rsp+58h] [rbp-A8h] BYREF
  _MEMORY_BASIC_INFORMATION Buffer; // [rsp+68h] [rbp-98h] BYREF
  __int128 v41; // [rsp+98h] [rbp-68h]
  __int128 v42; // [rsp+A8h] [rbp-58h]
  _BYTE Src[1408]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v44; // [rsp+640h] [rbp+540h] BYREF
  _BYTE v45[38]; // [rsp+642h] [rbp+542h] BYREF
  int v46; // [rsp+668h] [rbp+568h]
  int v47; // [rsp+66Ch] [rbp+56Ch]
  void *v48; // [rsp+680h] [rbp+580h]
  _DWORD v49[12]; // [rsp+BC0h] [rbp+AC0h] BYREF
  __int16 v50; // [rsp+BF0h] [rbp+AF0h]
  HANDLE v51; // [rsp+BF8h] [rbp+AF8h]

  LOWORD(v49[0]) = 0;
  *(_OWORD *)Handles = 0;
  memset_0((char *)v49 + 2, 0, 0x576u);
  v44 = 0;
  memset_0(v45, 0, 0x576u);
  v7 = *a2;
  *a2 = 0;
  v8 = 0;
  v9 = 0;
  memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
  memset(&Buffer, 0, sizeof(Buffer));
  if ( v7 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
  *(&FileMappingAttributes.bInheritHandle + 1) = 0;
  *(&FileMappingAttributes.nLength + 1) = 0;
  FileMappingAttributes.nLength = 24;
  FileMappingAttributes.lpSecurityDescriptor = 0;
  FileMappingAttributes.bInheritHandle = 1;
  v10 = CreateFileMappingW_0((HANDLE)0xFFFFFFFFFFFFFFFFLL, &FileMappingAttributes, 4u, 0, 0x20u, 0);
  hObject = v10;
  v37 = (unsigned __int64)v10 + 1;
  if ( (unsigned __int64)v10 + 1 <= 1 )
  {
    v11 = 0;
    LastError_0 = GetLastError_0();
    v13 = LastError_0;
    if ( LastError_0 > 0 )
      v13 = (unsigned __int16)LastError_0 | 0x80070000;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 35;
LABEL_66:
      WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids, (unsigned int)v13);
      goto LABEL_67;
    }
    goto LABEL_67;
  }
  v16 = MapViewOfFile(v10, 2u, 0, 0, 0);
  v11 = v16;
  if ( !v16 )
  {
    v17 = GetLastError_0();
    v13 = v17;
    if ( v17 > 0 )
      v13 = (unsigned __int16)v17 | 0x80070000;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 36;
      goto LABEL_66;
    }
LABEL_67:
    if ( v13 >= 0 || !v11 )
      goto LABEL_88;
    goto LABEL_86;
  }
  *v16 = 0;
  v41 = 0;
  v42 = 0;
  v16[1] = 0;
  *(_QWORD *)v16 = CreateEventW(0, 1, 0, 0);
  if ( !*(_QWORD *)v11 )
  {
    v18 = GetLastError_0();
    v13 = v18;
    if ( v18 > 0 )
      v13 = (unsigned __int16)v18 | 0x80070000;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 37;
      goto LABEL_66;
    }
    goto LABEL_67;
  }
  *((_DWORD *)v11 + 2) = -2147467259;
  if ( !a3 )
  {
    v13 = -2147467263;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v22 = 40;
      goto LABEL_85;
    }
    goto LABEL_86;
  }
  memset_0(Src, 0, 0x578u);
  memcpy_0(v49, Src, 0x578u);
  v49[0] = 91751760;
  v49[10] = -805306366;
  v50 = a4;
  v51 = v10;
  v19 = WersvcSendMessage(L"\\WindowsErrorReportingServicePort", (struct _WERSVC_MSG *)v49, (struct _WERSVC_MSG *)&v44);
  v20 = RtlNtStatusToDosError(v19);
  v13 = v20;
  if ( v20 > 0 )
    v13 = (unsigned __int16)v20 | 0x80070000;
  if ( v13 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v22 = 38;
LABEL_85:
      WPP_SF_d(*((_QWORD *)v21 + 2), v22, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids, (unsigned int)v13);
      goto LABEL_86;
    }
    goto LABEL_86;
  }
  if ( v46 != -805306368 )
  {
    v13 = v47 | 0x10000000;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 39;
      goto LABEL_66;
    }
    goto LABEL_67;
  }
  Handles[0] = *(HANDLE *)v11;
  Handles[1] = v48;
  v23 = WaitForMultipleObjects(2u, Handles, 0, 0x2710u);
  if ( v23 )
  {
    switch ( v23 )
    {
      case 1u:
        v13 = -2147023829;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v22 = 41;
          goto LABEL_85;
        }
        break;
      case 0x102u:
        v13 = -2147023843;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v22 = 42;
          goto LABEL_85;
        }
        break;
      case 0xFFFFFFFF:
        v28 = GetLastError_0();
        v13 = v28;
        if ( v28 > 0 )
          v13 = (unsigned __int16)v28 | 0x80070000;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v15 = 43;
          goto LABEL_66;
        }
        goto LABEL_67;
      default:
        MicrosoftTelemetryAssertTriggeredNoArgs(v25, v24, v26, v27);
        v13 = -2147467259;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids);
        }
        break;
    }
LABEL_86:
    if ( *((_QWORD *)v11 + 2) )
      SetEvent(*((HANDLE *)v11 + 2));
LABEL_88:
    if ( !v8 )
      goto LABEL_90;
    goto LABEL_89;
  }
  if ( *((int *)v11 + 2) < 0 )
  {
    v13 = *((_DWORD *)v11 + 2);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 45;
      goto LABEL_66;
    }
    goto LABEL_67;
  }
  v29 = MapViewOfFile(*((HANDLE *)v11 + 3), 4u, 0, 0, 0);
  v9 = v29;
  if ( !v29 )
  {
    v30 = GetLastError_0();
    v13 = v30;
    if ( v30 > 0 )
      v13 = (unsigned __int16)v30 | 0x80070000;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 46;
      goto LABEL_66;
    }
    goto LABEL_67;
  }
  memset(&Buffer, 0, sizeof(Buffer));
  if ( !VirtualQuery_0(v29, &Buffer, 0x30u) )
  {
    v31 = GetLastError_0();
    v13 = v31;
    if ( v31 > 0 )
      v13 = (unsigned __int16)v31 | 0x80070000;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 47;
      goto LABEL_66;
    }
    goto LABEL_67;
  }
  RegionSize = Buffer.RegionSize;
  v33 = (IStream *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v33;
  if ( !v33 )
  {
    v13 = -2147024882;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids, 2147942414LL);
    }
    v8 = 0;
    goto LABEL_86;
  }
  *((_QWORD *)v33 + 1) = v9;
  *(_QWORD *)v33 = &MEMORY_STREAM::`vftable';
  *((_DWORD *)v33 + 5) = 0;
  *((_WORD *)v33 + 12) = 0;
  *((_DWORD *)v33 + 4) = RegionSize;
  v34 = *a2;
  *a2 = 0;
  if ( v34 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
  v13 = CoUnmarshalInterface(v8, &GUID_f61082c5_ed37_4a0e_a1b1_08ee41314935, a2);
  if ( v13 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v22 = 49;
      goto LABEL_85;
    }
    goto LABEL_86;
  }
  v13 = 0;
LABEL_89:
  MstmFree(v8);
LABEL_90:
  if ( v11 )
  {
    if ( *((_QWORD *)v11 + 2) )
      CloseHandle_0(*((HANDLE *)v11 + 2));
    if ( *((_QWORD *)v11 + 3) )
      CloseHandle_0(*((HANDLE *)v11 + 3));
  }
  if ( v9 )
    UnmapViewOfFile(v9);
  if ( v11 )
    UnmapViewOfFile(v11);
  if ( v37 > 1 )
    CloseHandle(hObject);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14005e058  mov     [rsp-8+arg_0], rbx
0x14005e05d  push    rbp
0x14005e05e  push    rsi
0x14005e05f  push    rdi
0x14005e060  push    r12
0x14005e062  push    r13
0x14005e064  push    r14
0x14005e066  push    r15
0x14005e068  lea     rbp, [rsp-1050h]
0x14005e070  mov     eax, 1150h
0x14005e075  call    _alloca_probe
0x14005e07a  sub     rsp, rax
0x14005e07d  mov     rax, cs:__security_cookie
0x14005e084  xor     rax, rsp
0x14005e087  mov     [rbp+1080h+var_40], rax
0x14005e08e  mov     r14d, r8d
0x14005e091  lea     rcx, [rbp+1080h+var_5C0+2]; void *
0x14005e098  mov     r13, rdx
0x14005e09b  xorps   xmm0, xmm0
0x14005e09e  mov     ebx, 576h
0x14005e0a3  xor     r12d, r12d
0x14005e0a6  mov     r8d, ebx; Size
0x14005e0a9  mov     word ptr [rbp+1080h+var_5C0], r12w
0x14005e0b1  xor     edx, edx; Val
0x14005e0b3  movzx   r15d, r9w
0x14005e0b7  movups  xmmword ptr [rsp+1180h+Handles], xmm0
0x14005e0bc  call    memset_0
0x14005e0c1  mov     r8d, ebx; Size
0x14005e0c4  mov     [rbp+1080h+var_B40], r12w
0x14005e0cc  xor     edx, edx; Val
0x14005e0ce  lea     rcx, [rbp+1080h+var_B3E]; void *
0x14005e0d5  call    memset_0
0x14005e0da  mov     rcx, [r13+0]
0x14005e0de  xorps   xmm0, xmm0
0x14005e0e1  xor     eax, eax
0x14005e0e3  mov     [r13+0], r12
0x14005e0e7  mov     qword ptr [rsp+1180h+FileMappingAttributes.bInheritHandle], rax
0x14005e0ec  mov     edi, r12d
0x14005e0ef  mov     esi, r12d
0x14005e0f2  movups  xmmword ptr [rsp+1180h+FileMappingAttributes.nLength], xmm0
0x14005e0f7  movups  xmmword ptr [rsp+1180h+Buffer.BaseAddress], xmm0
0x14005e0fc  movups  xmmword ptr [rsp+1180h+Buffer.AllocationProtect], xmm0
0x14005e101  movups  xmmword ptr [rbp+1080h+Buffer.State], xmm0
0x14005e105  test    rcx, rcx
0x14005e108  jz      short loc_14005E116
0x14005e10a  mov     rax, [rcx]
0x14005e10d  mov     rax, [rax+10h]
0x14005e111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005e116  xor     eax, eax
0x14005e118  mov     [rsp+1180h+lpName], r12; lpName
0x14005e11d  xorps   xmm0, xmm0
0x14005e120  mov     qword ptr [rsp+1180h+FileMappingAttributes.bInheritHandle], rax
0x14005e125  movups  xmmword ptr [rsp+1180h+FileMappingAttributes.nLength], xmm0
0x14005e12a  xor     r9d, r9d; dwMaximumSizeHigh
0x14005e12d  mov     [rsp+1180h+FileMappingAttributes.nLength], 18h
0x14005e135  lea     r8d, [rax+4]; flProtect
0x14005e139  mov     [rsp+1180h+FileMappingAttributes.lpSecurityDescriptor], r12
0x14005e13e  lea     rdx, [rsp+1180h+FileMappingAttributes]; lpFileMappingAttributes
0x14005e143  mov     [rsp+1180h+FileMappingAttributes.bInheritHandle], 1
0x14005e14b  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x14005e14f  mov     [rsp+1180h+dwMaximumSizeLow], 20h ; ' '; dwMaximumSizeLow
0x14005e157  call    CreateFileMappingW_0
0x14005e15c  mov     r12, rax
0x14005e15f  mov     [rsp+1180h+hObject], rax
0x14005e164  inc     rax
0x14005e167  mov     [rsp+1180h+var_1138], rax
0x14005e16c  cmp     rax, 1
0x14005e170  ja      short loc_14005E1B6
0x14005e172  xor     ebx, ebx
0x14005e174  call    GetLastError_0
0x14005e179  mov     r14d, eax
0x14005e17c  test    eax, eax
0x14005e17e  jle     short loc_14005E18B
0x14005e180  movzx   r14d, ax
0x14005e184  or      r14d, 80070000h
0x14005e18b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e192  lea     rax, WPP_GLOBAL_Control
0x14005e199  cmp     rcx, rax
0x14005e19c  jz      loc_14005E5E5
0x14005e1a2  test    byte ptr [rcx+1Ch], 1
0x14005e1a6  jz      loc_14005E5E5
0x14005e1ac  mov     edx, 23h ; '#'
0x14005e1b1  jmp     loc_14005E5D2
0x14005e1b6  xor     r9d, r9d; dwFileOffsetLow
0x14005e1b9  mov     qword ptr [rsp+1180h+dwMaximumSizeLow], rsi; dwNumberOfBytesToMap
0x14005e1be  xor     r8d, r8d; dwFileOffsetHigh
0x14005e1c1  mov     rcx, r12; hFileMappingObject
0x14005e1c4  lea     edx, [r9+2]; dwDesiredAccess
0x14005e1c8  call    cs:__imp_MapViewOfFile
0x14005e1cf  nop     dword ptr [rax+rax+00h]
0x14005e1d4  mov     rbx, rax
0x14005e1d7  test    rax, rax
0x14005e1da  jnz     short loc_14005E21E
0x14005e1dc  call    GetLastError_0
0x14005e1e1  mov     r14d, eax
0x14005e1e4  test    eax, eax
0x14005e1e6  jle     short loc_14005E1F3
0x14005e1e8  movzx   r14d, ax
0x14005e1ec  or      r14d, 80070000h
0x14005e1f3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e1fa  lea     rax, WPP_GLOBAL_Control
0x14005e201  cmp     rcx, rax
0x14005e204  jz      loc_14005E5E5
0x14005e20a  test    byte ptr [rcx+1Ch], 1
0x14005e20e  jz      loc_14005E5E5
0x14005e214  mov     edx, 24h ; '$'
0x14005e219  jmp     loc_14005E5D2
0x14005e21e  xorps   xmm0, xmm0
0x14005e221  xor     r9d, r9d; lpName
0x14005e224  movups  xmmword ptr [rax], xmm0
0x14005e227  xor     r8d, r8d; bInitialState
0x14005e22a  xor     ecx, ecx; lpEventAttributes
0x14005e22c  movups  [rbp+1080h+var_10E8], xmm0
0x14005e230  lea     edx, [r9+1]; bManualReset
0x14005e234  movups  [rbp+1080h+var_10D8], xmm0
0x14005e238  movups  xmmword ptr [rax+10h], xmm0
0x14005e23c  call    cs:__imp_CreateEventW
0x14005e243  nop     dword ptr [rax+rax+00h]
0x14005e248  mov     [rbx], rax
0x14005e24b  mov     rax, [rbx]
0x14005e24e  test    rax, rax
0x14005e251  jnz     short loc_14005E295
0x14005e253  call    GetLastError_0
0x14005e258  mov     r14d, eax
0x14005e25b  test    eax, eax
0x14005e25d  jle     short loc_14005E26A
0x14005e25f  movzx   r14d, ax
0x14005e263  or      r14d, 80070000h
0x14005e26a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e271  lea     rax, WPP_GLOBAL_Control
0x14005e278  cmp     rcx, rax
0x14005e27b  jz      loc_14005E5E5
0x14005e281  test    byte ptr [rcx+1Ch], 1
0x14005e285  jz      loc_14005E5E5
0x14005e28b  mov     edx, 25h ; '%'
0x14005e290  jmp     loc_14005E5D2
0x14005e295  mov     dword ptr [rbx+8], 80004005h
0x14005e29c  test    r14d, r14d
0x14005e29f  jz      loc_14005E6D6
0x14005e2a5  mov     r14d, 578h
0x14005e2ab  lea     rcx, [rbp+1080h+Src]; void *
0x14005e2af  mov     r8d, r14d; Size
0x14005e2b2  xor     edx, edx; Val
0x14005e2b4  call    memset_0
0x14005e2b9  lea     rcx, [rbp+1080h+var_5C0]; void *
0x14005e2c0  mov     r8d, r14d; Size
0x14005e2c3  lea     rdx, [rbp+1080h+Src]; Src
0x14005e2c7  call    memcpy_0
0x14005e2cc  lea     r8, [rbp+1080h+var_B40]; struct _WERSVC_MSG *
0x14005e2d3  mov     [rbp+1080h+var_5C0], 5780550h
0x14005e2dd  lea     rdx, [rbp+1080h+var_5C0]; struct _WERSVC_MSG *
0x14005e2e4  mov     [rbp+1080h+var_598], 0D0000002h
0x14005e2ee  lea     rcx, aWindowserrorre; "\\WindowsErrorReportingServicePort"
0x14005e2f5  mov     [rbp+1080h+var_590], r15w
0x14005e2fd  mov     [rbp+1080h+var_588], r12
0x14005e304  call    ?WersvcSendMessage@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z; WersvcSendMessage(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)
0x14005e309  mov     ecx, eax; Status
0x14005e30b  call    cs:__imp_RtlNtStatusToDosError
0x14005e312  nop     dword ptr [rax+rax+00h]
0x14005e317  mov     r14d, eax
0x14005e31a  mov     r15d, 80070000h
0x14005e320  test    eax, eax
0x14005e322  jle     short loc_14005E32B
0x14005e324  movzx   r14d, ax
0x14005e328  or      r14d, r15d
0x14005e32b  test    r14d, r14d
0x14005e32e  jns     short loc_14005E35B
0x14005e330  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e337  lea     rax, WPP_GLOBAL_Control
0x14005e33e  cmp     rcx, rax
0x14005e341  jz      loc_14005E70D
0x14005e347  test    byte ptr [rcx+1Ch], 1
0x14005e34b  jz      loc_14005E70D
0x14005e351  mov     edx, 26h ; '&'
0x14005e356  jmp     loc_14005E6FA
0x14005e35b  cmp     [rbp+1080h+var_B18], 0D0000000h
0x14005e365  jz      short loc_14005E39E
0x14005e367  mov     r14d, [rbp+1080h+var_B14]
0x14005e36e  bts     r14d, 1Ch
0x14005e373  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e37a  lea     rax, WPP_GLOBAL_Control
0x14005e381  cmp     rcx, rax
0x14005e384  jz      loc_14005E5E5
0x14005e38a  test    byte ptr [rcx+1Ch], 1
0x14005e38e  jz      loc_14005E5E5
0x14005e394  mov     edx, 27h ; '''
0x14005e399  jmp     loc_14005E5D2
0x14005e39e  mov     rax, [rbx]
0x14005e3a1  lea     rdx, [rsp+1180h+Handles]; lpHandles
0x14005e3a6  xor     r8d, r8d; bWaitAll
0x14005e3a9  mov     [rsp+1180h+Handles], rax
0x14005e3ae  mov     rax, [rbp+1080h+var_B00]
0x14005e3b5  mov     r9d, 2710h; dwMilliseconds
0x14005e3bb  mov     [rsp+1180h+Handles+8], rax
0x14005e3c0  lea     ecx, [r8+2]; nCount
0x14005e3c4  call    cs:__imp_WaitForMultipleObjects
0x14005e3cb  nop     dword ptr [rax+rax+00h]
0x14005e3d0  mov     r12d, eax
0x14005e3d3  test    eax, eax
0x14005e3d5  jz      loc_14005E4E5
0x14005e3db  cmp     eax, 1
0x14005e3de  jz      loc_14005E4B4
0x14005e3e4  cmp     eax, 102h
0x14005e3e9  jz      loc_14005E483
0x14005e3ef  cmp     eax, 0FFFFFFFFh
0x14005e3f2  jz      short loc_14005E445
0x14005e3f4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14005e3f9  mov     r8d, 80004005h
0x14005e3ff  mov     r14d, r8d
0x14005e402  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e409  lea     rax, WPP_GLOBAL_Control
0x14005e410  cmp     rcx, rax
0x14005e413  jz      loc_14005E70D
0x14005e419  test    byte ptr [rcx+1Ch], 1
0x14005e41d  jz      loc_14005E70D
0x14005e423  mov     rcx, [rcx+10h]
0x14005e427  mov     edx, 2Ch ; ','
0x14005e42c  mov     [rsp+1180h+dwMaximumSizeLow], r8d
0x14005e431  mov     r9d, r12d
0x14005e434  lea     r8, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids
0x14005e43b  call    WPP_SF_Dd
0x14005e440  jmp     loc_14005E70D
0x14005e445  call    GetLastError_0
0x14005e44a  mov     r14d, eax
0x14005e44d  test    eax, eax
0x14005e44f  jle     short loc_14005E458
0x14005e451  movzx   r14d, ax
0x14005e455  or      r14d, r15d
0x14005e458  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e45f  lea     rax, WPP_GLOBAL_Control
0x14005e466  cmp     rcx, rax
0x14005e469  jz      loc_14005E5E5
0x14005e46f  test    byte ptr [rcx+1Ch], 1
0x14005e473  jz      loc_14005E5E5
0x14005e479  mov     edx, 2Bh ; '+'
0x14005e47e  jmp     loc_14005E5D2
0x14005e483  mov     r14d, 8007041Dh
0x14005e489  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e490  lea     rax, WPP_GLOBAL_Control
0x14005e497  cmp     rcx, rax
0x14005e49a  jz      loc_14005E70D
0x14005e4a0  test    byte ptr [rcx+1Ch], 1
0x14005e4a4  jz      loc_14005E70D
0x14005e4aa  mov     edx, 2Ah ; '*'
0x14005e4af  jmp     loc_14005E6FA
0x14005e4b4  mov     r14d, 8007042Bh
0x14005e4ba  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e4c1  lea     rax, WPP_GLOBAL_Control
0x14005e4c8  cmp     rcx, rax
0x14005e4cb  jz      loc_14005E70D
0x14005e4d1  test    byte ptr [rcx+1Ch], 1
0x14005e4d5  jz      loc_14005E70D
0x14005e4db  mov     edx, 29h ; ')'
0x14005e4e0  jmp     loc_14005E6FA
0x14005e4e5  mov     eax, [rbx+8]
0x14005e4e8  test    eax, eax
0x14005e4ea  jns     short loc_14005E51B
0x14005e4ec  mov     r14d, [rbx+8]
0x14005e4f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e4f7  lea     rax, WPP_GLOBAL_Control
0x14005e4fe  cmp     rcx, rax
0x14005e501  jz      loc_14005E5E5
0x14005e507  test    byte ptr [rcx+1Ch], 1
0x14005e50b  jz      loc_14005E5E5
0x14005e511  mov     edx, 2Dh ; '-'
0x14005e516  jmp     loc_14005E5D2
0x14005e51b  mov     rcx, [rbx+18h]; hFileMappingObject
0x14005e51f  xor     r9d, r9d; dwFileOffsetLow
0x14005e522  xor     r8d, r8d; dwFileOffsetHigh
0x14005e525  mov     qword ptr [rsp+1180h+dwMaximumSizeLow], rsi; dwNumberOfBytesToMap
0x14005e52a  lea     edx, [r9+4]; dwDesiredAccess
0x14005e52e  call    cs:__imp_MapViewOfFile
0x14005e535  nop     dword ptr [rax+rax+00h]
0x14005e53a  mov     rsi, rax
0x14005e53d  test    rax, rax
0x14005e540  jnz     short loc_14005E575
0x14005e542  call    GetLastError_0
0x14005e547  mov     r14d, eax
0x14005e54a  test    eax, eax
0x14005e54c  jle     short loc_14005E555
0x14005e54e  movzx   r14d, ax
0x14005e552  or      r14d, r15d
0x14005e555  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e55c  lea     rax, WPP_GLOBAL_Control
0x14005e563  cmp     rcx, rax
0x14005e566  jz      short loc_14005E5E5
0x14005e568  test    byte ptr [rcx+1Ch], 1
0x14005e56c  jz      short loc_14005E5E5
0x14005e56e  mov     edx, 2Eh ; '.'
0x14005e573  jmp     short loc_14005E5D2
0x14005e575  xorps   xmm0, xmm0
0x14005e578  lea     rdx, [rsp+1180h+Buffer]; lpBuffer
0x14005e57d  mov     r12d, 30h ; '0'
0x14005e583  mov     rcx, rsi; lpAddress
0x14005e586  mov     r8d, r12d; dwLength
0x14005e589  movups  xmmword ptr [rsp+1180h+Buffer.BaseAddress], xmm0
0x14005e58e  movups  xmmword ptr [rsp+1180h+Buffer.AllocationProtect], xmm0
0x14005e593  movups  xmmword ptr [rbp+1080h+Buffer.State], xmm0
0x14005e597  call    VirtualQuery_0
0x14005e59c  test    rax, rax
  ... truncated ...
```
