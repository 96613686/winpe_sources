# CElevatedDataCollection::SpawnDataCollector(utl::unique_ptr<IFaultrepElevatedDataCollection,tlx::release_delete> *,int,ushort)

- ea: `0x14005a240`
- end: `0x14005a972`
- name: `?SpawnDataCollector@CElevatedDataCollection@@IEAAJPEAV?$unique_ptr@UIFaultrepElevatedDataCollection@@Urelease_delete@tlx@@@utl@@HG@Z`
- size: `1842`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140059cb4`

## callees

- `0x140002470`
- `0x140002494`
- `0x1400030a8`
- `0x1400032ef`
- `0x1400032fb`
- `0x140004323`
- `0x14000432f`
- `0x140014474`
- `0x1400144b4`
- `0x140015b40`
- `0x14002c114`
- `0x14005a240`
- `0x14005b30c`
- `0x14005b770`
- `0x14005b7e8`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14005a41e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14005a41e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14005a8da`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14005a8da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005a93f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005a93f`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x14005a824`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x14005a824`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14005a3b0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14005a6fe`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14005a3b0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14005a6fe`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14005a91e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14005a92c`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14005a91e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14005a92c`
- `ntdll!RtlNtStatusToDosError` at `0x14005a4e7`
- `ntdll!RtlNtStatusToDosError` at `0x14005a4e7`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14005a59a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14005a59a`

## string_xrefs

- `0x14005a4ca`: `\WindowsErrorReportingServicePort`

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
      WPP_SF_d(*((_QWORD *)v14 + 2), v15, &WPP_b503122a8e753e2116c8130bd5de03da_Traceguids, (unsigned int)v13);
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
      WPP_SF_d(*((_QWORD *)v21 + 2), v22, &WPP_b503122a8e753e2116c8130bd5de03da_Traceguids, (unsigned int)v13);
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
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_b503122a8e753e2116c8130bd5de03da_Traceguids);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_b503122a8e753e2116c8130bd5de03da_Traceguids, 2147942414LL);
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
0x14005a240  mov     [rsp-8+arg_0], rbx
0x14005a245  push    rbp
0x14005a246  push    rsi
0x14005a247  push    rdi
0x14005a248  push    r12
0x14005a24a  push    r13
0x14005a24c  push    r14
0x14005a24e  push    r15
0x14005a250  lea     rbp, [rsp-1050h]
0x14005a258  mov     eax, 1150h
0x14005a25d  call    _alloca_probe
0x14005a262  sub     rsp, rax
0x14005a265  mov     rax, cs:__security_cookie
0x14005a26c  xor     rax, rsp
0x14005a26f  mov     [rbp+1080h+var_40], rax
0x14005a276  mov     r14d, r8d
0x14005a279  lea     rcx, [rbp+1080h+var_5C0+2]; void *
0x14005a280  mov     r13, rdx
0x14005a283  xorps   xmm0, xmm0
0x14005a286  mov     ebx, 576h
0x14005a28b  xor     r12d, r12d
0x14005a28e  mov     r8d, ebx; Size
0x14005a291  mov     word ptr [rbp+1080h+var_5C0], r12w
0x14005a299  xor     edx, edx; Val
0x14005a29b  movzx   r15d, r9w
0x14005a29f  movups  xmmword ptr [rsp+1180h+Handles], xmm0
0x14005a2a4  call    memset_0
0x14005a2a9  mov     r8d, ebx; Size
0x14005a2ac  mov     [rbp+1080h+var_B40], r12w
0x14005a2b4  xor     edx, edx; Val
0x14005a2b6  lea     rcx, [rbp+1080h+var_B3E]; void *
0x14005a2bd  call    memset_0
0x14005a2c2  mov     rcx, [r13+0]
0x14005a2c6  xorps   xmm0, xmm0
0x14005a2c9  xor     eax, eax
0x14005a2cb  mov     [r13+0], r12
0x14005a2cf  mov     qword ptr [rsp+1180h+FileMappingAttributes.bInheritHandle], rax
0x14005a2d4  mov     edi, r12d
0x14005a2d7  mov     esi, r12d
0x14005a2da  movups  xmmword ptr [rsp+1180h+FileMappingAttributes.nLength], xmm0
0x14005a2df  movups  xmmword ptr [rsp+1180h+Buffer.BaseAddress], xmm0
0x14005a2e4  movups  xmmword ptr [rsp+1180h+Buffer.AllocationProtect], xmm0
0x14005a2e9  movups  xmmword ptr [rbp+1080h+Buffer.State], xmm0
0x14005a2ed  test    rcx, rcx
0x14005a2f0  jz      short loc_14005A2FE
0x14005a2f2  mov     rax, [rcx]
0x14005a2f5  mov     rax, [rax+10h]
0x14005a2f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a2fe  xor     eax, eax
0x14005a300  mov     [rsp+1180h+lpName], r12; lpName
0x14005a305  xorps   xmm0, xmm0
0x14005a308  mov     qword ptr [rsp+1180h+FileMappingAttributes.bInheritHandle], rax
0x14005a30d  movups  xmmword ptr [rsp+1180h+FileMappingAttributes.nLength], xmm0
0x14005a312  xor     r9d, r9d; dwMaximumSizeHigh
0x14005a315  mov     [rsp+1180h+FileMappingAttributes.nLength], 18h
0x14005a31d  lea     r8d, [rax+4]; flProtect
0x14005a321  mov     [rsp+1180h+FileMappingAttributes.lpSecurityDescriptor], r12
0x14005a326  lea     rdx, [rsp+1180h+FileMappingAttributes]; lpFileMappingAttributes
0x14005a32b  mov     [rsp+1180h+FileMappingAttributes.bInheritHandle], 1
0x14005a333  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x14005a337  mov     [rsp+1180h+dwMaximumSizeLow], 20h ; ' '; dwMaximumSizeLow
0x14005a33f  call    CreateFileMappingW_0
0x14005a344  mov     r12, rax
0x14005a347  mov     [rsp+1180h+hObject], rax
0x14005a34c  inc     rax
0x14005a34f  mov     [rsp+1180h+var_1138], rax
0x14005a354  cmp     rax, 1
0x14005a358  ja      short loc_14005A39E
0x14005a35a  xor     ebx, ebx
0x14005a35c  call    GetLastError_0
0x14005a361  mov     r14d, eax
0x14005a364  test    eax, eax
0x14005a366  jle     short loc_14005A373
0x14005a368  movzx   r14d, ax
0x14005a36c  or      r14d, 80070000h
0x14005a373  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a37a  lea     rax, WPP_GLOBAL_Control
0x14005a381  cmp     rcx, rax
0x14005a384  jz      loc_14005A7AF
0x14005a38a  test    byte ptr [rcx+1Ch], 1
0x14005a38e  jz      loc_14005A7AF
0x14005a394  mov     edx, 23h ; '#'
0x14005a399  jmp     loc_14005A79C
0x14005a39e  xor     r9d, r9d; dwFileOffsetLow
0x14005a3a1  mov     qword ptr [rsp+1180h+dwMaximumSizeLow], rsi; dwNumberOfBytesToMap
0x14005a3a6  xor     r8d, r8d; dwFileOffsetHigh
0x14005a3a9  mov     rcx, r12; hFileMappingObject
0x14005a3ac  lea     edx, [r9+2]; dwDesiredAccess
0x14005a3b0  call    cs:__imp_MapViewOfFile
0x14005a3b6  mov     rbx, rax
0x14005a3b9  test    rax, rax
0x14005a3bc  jnz     short loc_14005A400
0x14005a3be  call    GetLastError_0
0x14005a3c3  mov     r14d, eax
0x14005a3c6  test    eax, eax
0x14005a3c8  jle     short loc_14005A3D5
0x14005a3ca  movzx   r14d, ax
0x14005a3ce  or      r14d, 80070000h
0x14005a3d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a3dc  lea     rax, WPP_GLOBAL_Control
0x14005a3e3  cmp     rcx, rax
0x14005a3e6  jz      loc_14005A7AF
0x14005a3ec  test    byte ptr [rcx+1Ch], 1
0x14005a3f0  jz      loc_14005A7AF
0x14005a3f6  mov     edx, 24h ; '$'
0x14005a3fb  jmp     loc_14005A79C
0x14005a400  xorps   xmm0, xmm0
0x14005a403  xor     r9d, r9d; lpName
0x14005a406  movups  xmmword ptr [rax], xmm0
0x14005a409  xor     r8d, r8d; bInitialState
0x14005a40c  xor     ecx, ecx; lpEventAttributes
0x14005a40e  movups  [rbp+1080h+var_10E8], xmm0
0x14005a412  lea     edx, [r9+1]; bManualReset
0x14005a416  movups  [rbp+1080h+var_10D8], xmm0
0x14005a41a  movups  xmmword ptr [rax+10h], xmm0
0x14005a41e  call    cs:__imp_CreateEventW
0x14005a424  mov     [rbx], rax
0x14005a427  mov     rax, [rbx]
0x14005a42a  test    rax, rax
0x14005a42d  jnz     short loc_14005A471
0x14005a42f  call    GetLastError_0
0x14005a434  mov     r14d, eax
0x14005a437  test    eax, eax
0x14005a439  jle     short loc_14005A446
0x14005a43b  movzx   r14d, ax
0x14005a43f  or      r14d, 80070000h
0x14005a446  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a44d  lea     rax, WPP_GLOBAL_Control
0x14005a454  cmp     rcx, rax
0x14005a457  jz      loc_14005A7AF
0x14005a45d  test    byte ptr [rcx+1Ch], 1
0x14005a461  jz      loc_14005A7AF
0x14005a467  mov     edx, 25h ; '%'
0x14005a46c  jmp     loc_14005A79C
0x14005a471  mov     dword ptr [rbx+8], 80004005h
0x14005a478  test    r14d, r14d
0x14005a47b  jz      loc_14005A896
0x14005a481  mov     r14d, 578h
0x14005a487  lea     rcx, [rbp+1080h+Src]; void *
0x14005a48b  mov     r8d, r14d; Size
0x14005a48e  xor     edx, edx; Val
0x14005a490  call    memset_0
0x14005a495  lea     rcx, [rbp+1080h+var_5C0]; void *
0x14005a49c  mov     r8d, r14d; Size
0x14005a49f  lea     rdx, [rbp+1080h+Src]; Src
0x14005a4a3  call    memcpy_0
0x14005a4a8  lea     r8, [rbp+1080h+var_B40]; struct _WERSVC_MSG *
0x14005a4af  mov     [rbp+1080h+var_5C0], 5780550h
0x14005a4b9  lea     rdx, [rbp+1080h+var_5C0]; struct _WERSVC_MSG *
0x14005a4c0  mov     [rbp+1080h+var_598], 0D0000002h
0x14005a4ca  lea     rcx, aWindowserrorre; "\\WindowsErrorReportingServicePort"
0x14005a4d1  mov     [rbp+1080h+var_590], r15w
0x14005a4d9  mov     [rbp+1080h+var_588], r12
0x14005a4e0  call    ?WersvcSendMessage@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z; WersvcSendMessage(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)
0x14005a4e5  mov     ecx, eax; Status
0x14005a4e7  call    cs:__imp_RtlNtStatusToDosError
0x14005a4ed  mov     r14d, eax
0x14005a4f0  mov     r15d, 80070000h
0x14005a4f6  test    eax, eax
0x14005a4f8  jle     short loc_14005A501
0x14005a4fa  movzx   r14d, ax
0x14005a4fe  or      r14d, r15d
0x14005a501  test    r14d, r14d
0x14005a504  jns     short loc_14005A531
0x14005a506  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a50d  lea     rax, WPP_GLOBAL_Control
0x14005a514  cmp     rcx, rax
0x14005a517  jz      loc_14005A8CD
0x14005a51d  test    byte ptr [rcx+1Ch], 1
0x14005a521  jz      loc_14005A8CD
0x14005a527  mov     edx, 26h ; '&'
0x14005a52c  jmp     loc_14005A8BA
0x14005a531  cmp     [rbp+1080h+var_B18], 0D0000000h
0x14005a53b  jz      short loc_14005A574
0x14005a53d  mov     r14d, [rbp+1080h+var_B14]
0x14005a544  bts     r14d, 1Ch
0x14005a549  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a550  lea     rax, WPP_GLOBAL_Control
0x14005a557  cmp     rcx, rax
0x14005a55a  jz      loc_14005A7AF
0x14005a560  test    byte ptr [rcx+1Ch], 1
0x14005a564  jz      loc_14005A7AF
0x14005a56a  mov     edx, 27h ; '''
0x14005a56f  jmp     loc_14005A79C
0x14005a574  mov     rax, [rbx]
0x14005a577  lea     rdx, [rsp+1180h+Handles]; lpHandles
0x14005a57c  xor     r8d, r8d; bWaitAll
0x14005a57f  mov     [rsp+1180h+Handles], rax
0x14005a584  mov     rax, [rbp+1080h+var_B00]
0x14005a58b  mov     r9d, 2710h; dwMilliseconds
0x14005a591  mov     [rsp+1180h+Handles+8], rax
0x14005a596  lea     ecx, [r8+2]; nCount
0x14005a59a  call    cs:__imp_WaitForMultipleObjects
0x14005a5a0  mov     r12d, eax
0x14005a5a3  test    eax, eax
0x14005a5a5  jz      loc_14005A6B5
0x14005a5ab  cmp     eax, 1
0x14005a5ae  jz      loc_14005A684
0x14005a5b4  cmp     eax, 102h
0x14005a5b9  jz      loc_14005A653
0x14005a5bf  cmp     eax, 0FFFFFFFFh
0x14005a5c2  jz      short loc_14005A615
0x14005a5c4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14005a5c9  mov     r8d, 80004005h
0x14005a5cf  mov     r14d, r8d
0x14005a5d2  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a5d9  lea     rax, WPP_GLOBAL_Control
0x14005a5e0  cmp     rcx, rax
0x14005a5e3  jz      loc_14005A8CD
0x14005a5e9  test    byte ptr [rcx+1Ch], 1
0x14005a5ed  jz      loc_14005A8CD
0x14005a5f3  mov     rcx, [rcx+10h]
0x14005a5f7  mov     edx, 2Ch ; ','
0x14005a5fc  mov     [rsp+1180h+dwMaximumSizeLow], r8d
0x14005a601  mov     r9d, r12d
0x14005a604  lea     r8, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids
0x14005a60b  call    WPP_SF_Dd
0x14005a610  jmp     loc_14005A8CD
0x14005a615  call    GetLastError_0
0x14005a61a  mov     r14d, eax
0x14005a61d  test    eax, eax
0x14005a61f  jle     short loc_14005A628
0x14005a621  movzx   r14d, ax
0x14005a625  or      r14d, r15d
0x14005a628  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a62f  lea     rax, WPP_GLOBAL_Control
0x14005a636  cmp     rcx, rax
0x14005a639  jz      loc_14005A7AF
0x14005a63f  test    byte ptr [rcx+1Ch], 1
0x14005a643  jz      loc_14005A7AF
0x14005a649  mov     edx, 2Bh ; '+'
0x14005a64e  jmp     loc_14005A79C
0x14005a653  mov     r14d, 8007041Dh
0x14005a659  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a660  lea     rax, WPP_GLOBAL_Control
0x14005a667  cmp     rcx, rax
0x14005a66a  jz      loc_14005A8CD
0x14005a670  test    byte ptr [rcx+1Ch], 1
0x14005a674  jz      loc_14005A8CD
0x14005a67a  mov     edx, 2Ah ; '*'
0x14005a67f  jmp     loc_14005A8BA
0x14005a684  mov     r14d, 8007042Bh
0x14005a68a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a691  lea     rax, WPP_GLOBAL_Control
0x14005a698  cmp     rcx, rax
0x14005a69b  jz      loc_14005A8CD
0x14005a6a1  test    byte ptr [rcx+1Ch], 1
0x14005a6a5  jz      loc_14005A8CD
0x14005a6ab  mov     edx, 29h ; ')'
0x14005a6b0  jmp     loc_14005A8BA
0x14005a6b5  mov     eax, [rbx+8]
0x14005a6b8  test    eax, eax
0x14005a6ba  jns     short loc_14005A6EB
0x14005a6bc  mov     r14d, [rbx+8]
0x14005a6c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a6c7  lea     rax, WPP_GLOBAL_Control
0x14005a6ce  cmp     rcx, rax
0x14005a6d1  jz      loc_14005A7AF
0x14005a6d7  test    byte ptr [rcx+1Ch], 1
0x14005a6db  jz      loc_14005A7AF
0x14005a6e1  mov     edx, 2Dh ; '-'
0x14005a6e6  jmp     loc_14005A79C
0x14005a6eb  mov     rcx, [rbx+18h]; hFileMappingObject
0x14005a6ef  xor     r9d, r9d; dwFileOffsetLow
0x14005a6f2  xor     r8d, r8d; dwFileOffsetHigh
0x14005a6f5  mov     qword ptr [rsp+1180h+dwMaximumSizeLow], rsi; dwNumberOfBytesToMap
0x14005a6fa  lea     edx, [r9+4]; dwDesiredAccess
0x14005a6fe  call    cs:__imp_MapViewOfFile
0x14005a704  mov     rsi, rax
0x14005a707  test    rax, rax
0x14005a70a  jnz     short loc_14005A73F
0x14005a70c  call    GetLastError_0
0x14005a711  mov     r14d, eax
0x14005a714  test    eax, eax
0x14005a716  jle     short loc_14005A71F
0x14005a718  movzx   r14d, ax
0x14005a71c  or      r14d, r15d
0x14005a71f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a726  lea     rax, WPP_GLOBAL_Control
0x14005a72d  cmp     rcx, rax
0x14005a730  jz      short loc_14005A7AF
0x14005a732  test    byte ptr [rcx+1Ch], 1
0x14005a736  jz      short loc_14005A7AF
0x14005a738  mov     edx, 2Eh ; '.'
0x14005a73d  jmp     short loc_14005A79C
0x14005a73f  xorps   xmm0, xmm0
0x14005a742  lea     rdx, [rsp+1180h+Buffer]; lpBuffer
0x14005a747  mov     r12d, 30h ; '0'
0x14005a74d  mov     rcx, rsi; lpAddress
0x14005a750  mov     r8d, r12d; dwLength
0x14005a753  movups  xmmword ptr [rsp+1180h+Buffer.BaseAddress], xmm0
0x14005a758  movups  xmmword ptr [rsp+1180h+Buffer.AllocationProtect], xmm0
0x14005a75d  movups  xmmword ptr [rbp+1080h+Buffer.State], xmm0
0x14005a761  call    VirtualQuery_0
0x14005a766  test    rax, rax
0x14005a769  jnz     short loc_14005A7C6
0x14005a76b  call    GetLastError_0
0x14005a770  mov     r14d, eax
0x14005a773  test    eax, eax
0x14005a775  jle     short loc_14005A77E
  ... truncated ...
```
