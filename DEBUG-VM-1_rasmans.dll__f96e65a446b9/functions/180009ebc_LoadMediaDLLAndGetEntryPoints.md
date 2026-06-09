# LoadMediaDLLAndGetEntryPoints

- ea: `0x180009ebc`
- end: `0x18000a45d`
- name: `LoadMediaDLLAndGetEntryPoints`
- size: `1441`
- prototype: `__int64 __fastcall(char *String1)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180009348`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180009ebc`
- `0x18000c00c`

## import_xrefs

- `msvcrt!_stricmp` at `0x18000a17c`
- `msvcrt!_stricmp` at `0x18000a17c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a37a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a37a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a151`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a194`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a214`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a234`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a254`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a274`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a294`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a2b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a2d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a2f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a310`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a32c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a348`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a364`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a151`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a194`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a214`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a234`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a254`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a274`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a294`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a2b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a2d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a2f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a310`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a32c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a348`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a364`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000a0b8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000a0b8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a403`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a403`

## string_xrefs

- `0x180009f3a`: `PortOpen`
- `0x180009fc5`: `PortCompressionSetInfo`
- `0x18000a065`: `PortReceiveComplete`
- `0x18000a0a1`: `PortSetIoCompletionPort`
- `0x18000a18a`: `PortOpenExternal`
- `0x18000a1ea`: `RemovePort`
- `0x18000a2aa`: `SetCommSettings`
- `0x18000a28a`: `UnloadRastapiDll`
- `0x18000a2ca`: `DeviceGetDevConfigEx`
- `0x18000a33e`: `UpdateTapiService`

## pseudocode

```c
__int64 __fastcall LoadMediaDLLAndGetEntryPoints(char *String1)
{
  HMODULE Library; // rax
  HMODULE v3; // rdi
  DWORD LastError; // eax
  DWORD v5; // ebx
  struct _LIST_ENTRY *v6; // rcx
  __int64 v7; // rdx
  unsigned __int16 i; // r14
  const CHAR *v9; // r15
  FARPROC ProcAddress; // rax
  DWORD v11; // eax
  DWORD v12; // eax
  LPCSTR lpProcName; // [rsp+30h] [rbp-D0h]
  __int16 v15; // [rsp+38h] [rbp-C8h]
  const char *v16; // [rsp+40h] [rbp-C0h]
  __int16 v17; // [rsp+48h] [rbp-B8h]
  const char *v18; // [rsp+50h] [rbp-B0h]
  __int16 v19; // [rsp+58h] [rbp-A8h]
  const char *v20; // [rsp+60h] [rbp-A0h]
  __int16 v21; // [rsp+68h] [rbp-98h]
  const char *v22; // [rsp+70h] [rbp-90h]
  __int16 v23; // [rsp+78h] [rbp-88h]
  const char *v24; // [rsp+80h] [rbp-80h]
  __int16 v25; // [rsp+88h] [rbp-78h]
  const char *v26; // [rsp+90h] [rbp-70h]
  __int16 v27; // [rsp+98h] [rbp-68h]
  const char *v28; // [rsp+A0h] [rbp-60h]
  __int16 v29; // [rsp+A8h] [rbp-58h]
  const char *v30; // [rsp+B0h] [rbp-50h]
  __int16 v31; // [rsp+B8h] [rbp-48h]
  const char *v32; // [rsp+C0h] [rbp-40h]
  __int16 v33; // [rsp+C8h] [rbp-38h]
  const char *v34; // [rsp+D0h] [rbp-30h]
  __int16 v35; // [rsp+D8h] [rbp-28h]
  const char *v36; // [rsp+E0h] [rbp-20h]
  __int16 v37; // [rsp+E8h] [rbp-18h]
  const char *v38; // [rsp+F0h] [rbp-10h]
  __int16 v39; // [rsp+F8h] [rbp-8h]
  const char *v40; // [rsp+100h] [rbp+0h]
  __int16 v41; // [rsp+108h] [rbp+8h]
  const char *v42; // [rsp+110h] [rbp+10h]
  __int16 v43; // [rsp+118h] [rbp+18h]
  const char *v44; // [rsp+120h] [rbp+20h]
  __int16 v45; // [rsp+128h] [rbp+28h]
  const char *v46; // [rsp+130h] [rbp+30h]
  __int16 v47; // [rsp+138h] [rbp+38h]
  const char *v48; // [rsp+140h] [rbp+40h]
  __int16 v49; // [rsp+148h] [rbp+48h]
  const char *v50; // [rsp+150h] [rbp+50h]
  __int16 v51; // [rsp+158h] [rbp+58h]
  const char *v52; // [rsp+160h] [rbp+60h]
  __int16 v53; // [rsp+168h] [rbp+68h]

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 133, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids);
  }
  v27 = 6;
  lpProcName = "PortEnum";
  v15 = 0;
  v16 = "PortOpen";
  v17 = 1;
  v18 = "PortClose";
  v19 = 2;
  v20 = "PortGetInfo";
  v21 = 3;
  v22 = "PortSetInfo";
  v23 = 4;
  v24 = "PortDisconnect";
  v25 = 5;
  v26 = "PortConnect";
  v28 = "PortGetPortState";
  v29 = 7;
  v30 = "PortCompressionSetInfo";
  v31 = 8;
  v32 = "PortChangeCallback";
  v33 = 9;
  v34 = "PortGetStatistics";
  v35 = 10;
  v36 = "PortClearStatistics";
  v37 = 11;
  v38 = "PortSend";
  v39 = 12;
  v40 = "PortTestSignalState";
  v41 = 13;
  v42 = "PortReceive";
  v43 = 14;
  v44 = "PortInit";
  v45 = 15;
  v46 = "PortReceiveComplete";
  v47 = 16;
  v48 = "PortSetFraming";
  v49 = 17;
  v50 = "PortGetIOHandle";
  v51 = 18;
  v52 = "PortSetIoCompletionPort";
  v53 = 19;
  Library = LoadLibraryExA(String1, 0, 0x1000u);
  v3 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v5;
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_12;
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 134, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, LastError);
    }
    v6 = WPP_GLOBAL_Control;
LABEL_12:
    if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v6[1].Blink) & 0x2000) != 0
      && BYTE1(v6[1].Blink) >= 6u )
    {
      v7 = 135;
LABEL_51:
      WPP_SF_d(v6[1].Flink, v7, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, v5);
      return v5;
    }
    return v5;
  }
  *((_QWORD *)String1 + 23) = Library;
  for ( i = 0; i < 0x14u; ++i )
  {
    v9 = (&lpProcName)[2 * i];
    ProcAddress = GetProcAddress(v3, v9);
    *(_QWORD *)&String1[8 * i + 16] = ProcAddress;
    if ( !ProcAddress )
    {
      v12 = GetLastError();
      v5 = v12;
      if ( !v12 )
        goto LABEL_47;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control[1].Flink,
          136,
          (unsigned int)WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids,
          (_DWORD)v9,
          v12);
      }
      goto LABEL_46;
    }
  }
  v5 = 0;
  if ( !_stricmp(String1, "rastapi") )
  {
    RastapiPortOpen = (__int64)GetProcAddress(v3, "PortOpenExternal");
    if ( !RastapiPortOpen )
      goto LABEL_36;
    RastapiAddPorts = (__int64)GetProcAddress(v3, "AddPorts");
    if ( !RastapiAddPorts )
      goto LABEL_36;
    RastapiGetConnectInfo = (__int64)GetProcAddress(v3, "GetConnectInfo");
    if ( !RastapiGetConnectInfo )
      goto LABEL_36;
    RastapiRemovePort = (__int64)GetProcAddress(v3, "RemovePort");
    if ( !RastapiRemovePort )
      goto LABEL_36;
    RastapiEnableDeviceForDialIn = (__int64)GetProcAddress(v3, "EnableDeviceForDialIn");
    if ( !RastapiEnableDeviceForDialIn )
      goto LABEL_36;
    RastapiGetCalledIdInfo = (__int64)GetProcAddress(v3, "RastapiGetCalledID");
    if ( !RastapiGetCalledIdInfo )
      goto LABEL_36;
    RastapiSetCalledIdInfo = (__int64)GetProcAddress(v3, "RastapiSetCalledID");
    if ( !RastapiSetCalledIdInfo )
      goto LABEL_36;
    RastapiGetZeroDeviceInfo = (__int64)GetProcAddress(v3, "GetZeroDeviceInfo");
    if ( !RastapiGetZeroDeviceInfo )
      goto LABEL_36;
    RastapiUnload = (__int64)GetProcAddress(v3, "UnloadRastapiDll");
    if ( !RastapiUnload
      || (RastapiSetCommSettings = (__int64)GetProcAddress(v3, "SetCommSettings")) == 0
      || (RastapiGetDevConfigEx = (__int64)GetProcAddress(v3, "DeviceGetDevConfigEx")) == 0
      || (RastapiIsPulseDial = (__int64)GetProcAddress(v3, "RasTapiIsPulseDial")) == 0
      || (RastapiRefreshDevices = (__int64)GetProcAddress(v3, "RefreshDevices")) == 0
      || (RastapiInitializeDriverIoctl = (__int64)GetProcAddress(v3, "InitializeDriverIoControl")) == 0
      || (RastapiUpdateTapiService = (__int64)GetProcAddress(v3, "UpdateTapiService")) == 0
      || (RastapiCheckRasmanDependency = GetProcAddress(v3, "CheckRasmanDependency")) == 0 )
    {
LABEL_36:
      v11 = GetLastError();
      v5 = v11;
      if ( v11 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 137, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, v11);
        }
LABEL_46:
        FreeLibrary(*((HMODULE *)String1 + 23));
        *((_QWORD *)String1 + 23) = 0;
        *String1 = 0;
      }
    }
  }
LABEL_47:
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    v7 = 138;
    goto LABEL_51;
  }
  return v5;
}

```

## disassembly

```asm
0x180009ebc  push    rbp
0x180009ebe  push    rbx
0x180009ebf  push    rsi
0x180009ec0  push    rdi
0x180009ec1  push    r12
0x180009ec3  push    r13
0x180009ec5  push    r14
0x180009ec7  push    r15
0x180009ec9  lea     rbp, [rsp-78h]
0x180009ece  sub     rsp, 178h
0x180009ed5  mov     rsi, rcx
0x180009ed8  mov     rcx, cs:WPP_GLOBAL_Control
0x180009edf  lea     r13, WPP_GLOBAL_Control
0x180009ee6  lea     r14, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x180009eed  mov     r15d, 6
0x180009ef3  mov     r12d, 2000h
0x180009ef9  cmp     rcx, r13
0x180009efc  jz      short loc_180009F1A
0x180009efe  test    [rcx+1Ch], r12d
0x180009f02  jz      short loc_180009F1A
0x180009f04  cmp     [rcx+19h], r15b
0x180009f08  jb      short loc_180009F1A
0x180009f0a  mov     rcx, [rcx+10h]
0x180009f0e  lea     edx, [r15+7Fh]
0x180009f12  mov     r8, r14
0x180009f15  call    WPP_SF_
0x180009f1a  lea     rax, aPortenum; "PortEnum"
0x180009f21  mov     [rbp+0B0h+var_118], r15w
0x180009f26  mov     [rsp+1B0h+lpProcName], rax
0x180009f2b  mov     r8d, 1000h; dwFlags
0x180009f31  xor     eax, eax
0x180009f33  mov     [rsp+1B0h+var_178], ax
0x180009f38  xor     edx, edx; hFile
0x180009f3a  lea     rax, aPortopen; "PortOpen"
0x180009f41  mov     [rsp+1B0h+var_170], rax
0x180009f46  mov     eax, 1
0x180009f4b  mov     [rsp+1B0h+var_168], ax
0x180009f50  lea     rax, aPortclose; "PortClose"
0x180009f57  mov     [rsp+1B0h+var_160], rax
0x180009f5c  mov     eax, 2
0x180009f61  mov     [rsp+1B0h+var_158], ax
0x180009f66  lea     rax, aPortgetinfo; "PortGetInfo"
0x180009f6d  mov     [rsp+1B0h+var_150], rax
0x180009f72  mov     eax, 3
0x180009f77  mov     [rsp+1B0h+var_148], ax
0x180009f7c  lea     rax, aPortsetinfo; "PortSetInfo"
0x180009f83  mov     [rsp+1B0h+var_140], rax
0x180009f88  mov     eax, 4
0x180009f8d  mov     [rsp+1B0h+var_138], ax
0x180009f92  lea     rax, aPortdisconnect_3; "PortDisconnect"
0x180009f99  mov     [rbp+0B0h+var_130], rax
0x180009f9d  mov     eax, 5
0x180009fa2  mov     [rbp+0B0h+var_128], ax
0x180009fa6  lea     rax, aPortconnect; "PortConnect"
0x180009fad  mov     [rbp+0B0h+var_120], rax
0x180009fb1  lea     rax, aPortgetportsta; "PortGetPortState"
0x180009fb8  mov     [rbp+0B0h+var_110], rax
0x180009fbc  mov     eax, 7
0x180009fc1  mov     [rbp+0B0h+var_108], ax
0x180009fc5  lea     rax, aPortcompressio; "PortCompressionSetInfo"
0x180009fcc  mov     [rbp+0B0h+var_100], rax
0x180009fd0  mov     eax, 8
0x180009fd5  mov     [rbp+0B0h+var_F8], ax
0x180009fd9  lea     rax, aPortchangecall; "PortChangeCallback"
0x180009fe0  mov     [rbp+0B0h+var_F0], rax
0x180009fe4  mov     eax, 9
0x180009fe9  mov     [rbp+0B0h+var_E8], ax
0x180009fed  lea     rax, aPortgetstatist; "PortGetStatistics"
0x180009ff4  mov     [rbp+0B0h+var_E0], rax
0x180009ff8  mov     eax, 0Ah
0x180009ffd  mov     [rbp+0B0h+var_D8], ax
0x18000a001  lea     rax, aPortclearstati; "PortClearStatistics"
0x18000a008  mov     [rbp+0B0h+var_D0], rax
0x18000a00c  mov     eax, 0Bh
0x18000a011  mov     [rbp+0B0h+var_C8], ax
0x18000a015  lea     rax, aPortsend; "PortSend"
0x18000a01c  mov     [rbp+0B0h+var_C0], rax
0x18000a020  mov     eax, 0Ch
0x18000a025  mov     [rbp+0B0h+var_B8], ax
0x18000a029  lea     rax, aPorttestsignal; "PortTestSignalState"
0x18000a030  mov     [rbp+0B0h+var_B0], rax
0x18000a034  mov     eax, 0Dh
0x18000a039  mov     [rbp+0B0h+var_A8], ax
0x18000a03d  lea     rax, aPortreceive; "PortReceive"
0x18000a044  mov     [rbp+0B0h+var_A0], rax
0x18000a048  mov     eax, 0Eh
0x18000a04d  mov     [rbp+0B0h+var_98], ax
0x18000a051  lea     rax, aPortinit; "PortInit"
0x18000a058  mov     [rbp+0B0h+var_90], rax
0x18000a05c  mov     eax, 0Fh
0x18000a061  mov     [rbp+0B0h+var_88], ax
0x18000a065  lea     rax, aPortreceivecom; "PortReceiveComplete"
0x18000a06c  mov     [rbp+0B0h+var_80], rax
0x18000a070  mov     eax, 10h
0x18000a075  mov     [rbp+0B0h+var_78], ax
0x18000a079  lea     rax, aPortsetframing; "PortSetFraming"
0x18000a080  mov     [rbp+0B0h+var_70], rax
0x18000a084  mov     eax, 11h
0x18000a089  mov     [rbp+0B0h+var_68], ax
0x18000a08d  lea     rax, aPortgetiohandl; "PortGetIOHandle"
0x18000a094  mov     [rbp+0B0h+var_60], rax
0x18000a098  mov     eax, 12h
0x18000a09d  mov     [rbp+0B0h+var_58], ax
0x18000a0a1  lea     rax, aPortsetiocompl; "PortSetIoCompletionPort"
0x18000a0a8  mov     [rbp+0B0h+var_50], rax
0x18000a0ac  mov     eax, 13h
0x18000a0b1  mov     [rbp+0B0h+var_48], ax
0x18000a0b5  mov     rcx, rsi; lpLibFileName
0x18000a0b8  call    cs:__imp_LoadLibraryExA
0x18000a0be  mov     rdi, rax
0x18000a0c1  test    rax, rax
0x18000a0c4  jnz     short loc_18000A133
0x18000a0c6  call    cs:__imp_GetLastError
0x18000a0cc  mov     ebx, eax
0x18000a0ce  test    eax, eax
0x18000a0d0  jz      short loc_18000A102
0x18000a0d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0d9  cmp     rcx, r13
0x18000a0dc  jz      loc_18000A447
0x18000a0e2  test    [rcx+1Ch], r12d
0x18000a0e6  jz      short loc_18000A109
0x18000a0e8  cmp     byte ptr [rcx+19h], 2
0x18000a0ec  jb      short loc_18000A109
0x18000a0ee  mov     rcx, [rcx+10h]
0x18000a0f2  mov     edx, 86h
0x18000a0f7  mov     r9d, eax
0x18000a0fa  mov     r8, r14
0x18000a0fd  call    WPP_SF_d
0x18000a102  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a109  cmp     rcx, r13
0x18000a10c  jz      loc_18000A447
0x18000a112  test    [rcx+1Ch], r12d
0x18000a116  jz      loc_18000A447
0x18000a11c  cmp     [rcx+19h], r15b
0x18000a120  jb      loc_18000A447
0x18000a126  mov     edx, 87h
0x18000a12b  mov     r8, r14
0x18000a12e  jmp     loc_18000A43B
0x18000a133  mov     [rsi+0B8h], rdi
0x18000a13a  xor     r14d, r14d
0x18000a13d  movzx   ebx, r14w
0x18000a141  mov     rcx, rdi; hModule
0x18000a144  mov     eax, ebx
0x18000a146  add     rax, rax
0x18000a149  mov     r15, [rsp+rax*8+1B0h+lpProcName]
0x18000a14e  mov     rdx, r15; lpProcName
0x18000a151  call    cs:__imp_GetProcAddress
0x18000a157  mov     [rsi+rbx*8+10h], rax
0x18000a15c  test    rax, rax
0x18000a15f  jz      loc_18000A3BC
0x18000a165  inc     r14w
0x18000a169  cmp     r14w, 14h
0x18000a16e  jb      short loc_18000A13D
0x18000a170  lea     rdx, String2; "rastapi"
0x18000a177  mov     rcx, rsi; String1
0x18000a17a  xor     ebx, ebx
0x18000a17c  call    cs:__imp__stricmp
0x18000a182  test    eax, eax
0x18000a184  jnz     loc_18000A417
0x18000a18a  lea     rdx, aPortopenextern; "PortOpenExternal"
0x18000a191  mov     rcx, rdi; hModule
0x18000a194  call    cs:__imp_GetProcAddress
0x18000a19a  mov     cs:RastapiPortOpen, rax
0x18000a1a1  test    rax, rax
0x18000a1a4  jz      loc_18000A37A
0x18000a1aa  lea     rdx, aAddports; "AddPorts"
0x18000a1b1  mov     rcx, rdi; hModule
0x18000a1b4  call    cs:__imp_GetProcAddress
0x18000a1ba  mov     cs:RastapiAddPorts, rax
0x18000a1c1  test    rax, rax
0x18000a1c4  jz      loc_18000A37A
0x18000a1ca  lea     rdx, aGetconnectinfo; "GetConnectInfo"
0x18000a1d1  mov     rcx, rdi; hModule
0x18000a1d4  call    cs:__imp_GetProcAddress
0x18000a1da  mov     cs:RastapiGetConnectInfo, rax
0x18000a1e1  test    rax, rax
0x18000a1e4  jz      loc_18000A37A
0x18000a1ea  lea     rdx, aRemoveport; "RemovePort"
0x18000a1f1  mov     rcx, rdi; hModule
0x18000a1f4  call    cs:__imp_GetProcAddress
0x18000a1fa  mov     cs:RastapiRemovePort, rax
0x18000a201  test    rax, rax
0x18000a204  jz      loc_18000A37A
0x18000a20a  lea     rdx, aEnabledevicefo; "EnableDeviceForDialIn"
0x18000a211  mov     rcx, rdi; hModule
0x18000a214  call    cs:__imp_GetProcAddress
0x18000a21a  mov     cs:RastapiEnableDeviceForDialIn, rax
0x18000a221  test    rax, rax
0x18000a224  jz      loc_18000A37A
0x18000a22a  lea     rdx, aRastapigetcall; "RastapiGetCalledID"
0x18000a231  mov     rcx, rdi; hModule
0x18000a234  call    cs:__imp_GetProcAddress
0x18000a23a  mov     cs:RastapiGetCalledIdInfo, rax
0x18000a241  test    rax, rax
0x18000a244  jz      loc_18000A37A
0x18000a24a  lea     rdx, aRastapisetcall; "RastapiSetCalledID"
0x18000a251  mov     rcx, rdi; hModule
0x18000a254  call    cs:__imp_GetProcAddress
0x18000a25a  mov     cs:RastapiSetCalledIdInfo, rax
0x18000a261  test    rax, rax
0x18000a264  jz      loc_18000A37A
0x18000a26a  lea     rdx, aGetzerodevicei; "GetZeroDeviceInfo"
0x18000a271  mov     rcx, rdi; hModule
0x18000a274  call    cs:__imp_GetProcAddress
0x18000a27a  mov     cs:RastapiGetZeroDeviceInfo, rax
0x18000a281  test    rax, rax
0x18000a284  jz      loc_18000A37A
0x18000a28a  lea     rdx, aUnloadrastapid; "UnloadRastapiDll"
0x18000a291  mov     rcx, rdi; hModule
0x18000a294  call    cs:__imp_GetProcAddress
0x18000a29a  mov     cs:RastapiUnload, rax
0x18000a2a1  test    rax, rax
0x18000a2a4  jz      loc_18000A37A
0x18000a2aa  lea     rdx, aSetcommsetting; "SetCommSettings"
0x18000a2b1  mov     rcx, rdi; hModule
0x18000a2b4  call    cs:__imp_GetProcAddress
0x18000a2ba  mov     cs:RastapiSetCommSettings, rax
0x18000a2c1  test    rax, rax
0x18000a2c4  jz      loc_18000A37A
0x18000a2ca  lea     rdx, aDevicegetdevco_0; "DeviceGetDevConfigEx"
0x18000a2d1  mov     rcx, rdi; hModule
0x18000a2d4  call    cs:__imp_GetProcAddress
0x18000a2da  mov     cs:RastapiGetDevConfigEx, rax
0x18000a2e1  test    rax, rax
0x18000a2e4  jz      loc_18000A37A
0x18000a2ea  lea     rdx, aRastapiispulse; "RasTapiIsPulseDial"
0x18000a2f1  mov     rcx, rdi; hModule
0x18000a2f4  call    cs:__imp_GetProcAddress
0x18000a2fa  mov     cs:RastapiIsPulseDial, rax
0x18000a301  test    rax, rax
0x18000a304  jz      short loc_18000A37A
0x18000a306  lea     rdx, aRefreshdevices; "RefreshDevices"
0x18000a30d  mov     rcx, rdi; hModule
0x18000a310  call    cs:__imp_GetProcAddress
0x18000a316  mov     cs:RastapiRefreshDevices, rax
0x18000a31d  test    rax, rax
0x18000a320  jz      short loc_18000A37A
0x18000a322  lea     rdx, aInitializedriv; "InitializeDriverIoControl"
0x18000a329  mov     rcx, rdi; hModule
0x18000a32c  call    cs:__imp_GetProcAddress
0x18000a332  mov     cs:RastapiInitializeDriverIoctl, rax
0x18000a339  test    rax, rax
0x18000a33c  jz      short loc_18000A37A
0x18000a33e  lea     rdx, aUpdatetapiserv; "UpdateTapiService"
0x18000a345  mov     rcx, rdi; hModule
0x18000a348  call    cs:__imp_GetProcAddress
0x18000a34e  mov     cs:RastapiUpdateTapiService, rax
0x18000a355  test    rax, rax
0x18000a358  jz      short loc_18000A37A
0x18000a35a  lea     rdx, aCheckrasmandep; "CheckRasmanDependency"
0x18000a361  mov     rcx, rdi; hModule
0x18000a364  call    cs:__imp_GetProcAddress
0x18000a36a  mov     cs:RastapiCheckRasmanDependency, rax
0x18000a371  test    rax, rax
0x18000a374  jnz     loc_18000A417
0x18000a37a  call    cs:__imp_GetLastError
0x18000a380  mov     ebx, eax
0x18000a382  test    eax, eax
0x18000a384  jz      loc_18000A417
0x18000a38a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a391  cmp     rcx, r13
0x18000a394  jz      short loc_18000A3FC
0x18000a396  test    [rcx+1Ch], r12d
0x18000a39a  jz      short loc_18000A3FC
0x18000a39c  cmp     byte ptr [rcx+19h], 2
0x18000a3a0  jb      short loc_18000A3FC
0x18000a3a2  mov     rcx, [rcx+10h]
0x18000a3a6  lea     r8, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x18000a3ad  mov     edx, 89h
0x18000a3b2  mov     r9d, eax
0x18000a3b5  call    WPP_SF_d
0x18000a3ba  jmp     short loc_18000A3FC
0x18000a3bc  call    cs:__imp_GetLastError
0x18000a3c2  mov     ebx, eax
0x18000a3c4  test    eax, eax
0x18000a3c6  jz      short loc_18000A417
0x18000a3c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3cf  cmp     rcx, r13
0x18000a3d2  jz      short loc_18000A3FC
0x18000a3d4  test    [rcx+1Ch], r12d
0x18000a3d8  jz      short loc_18000A3FC
0x18000a3da  cmp     byte ptr [rcx+19h], 2
0x18000a3de  jb      short loc_18000A3FC
0x18000a3e0  mov     rcx, [rcx+10h]
0x18000a3e4  lea     r8, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x18000a3eb  mov     edx, 88h
0x18000a3f0  mov     [rsp+1B0h+var_190], eax
0x18000a3f4  mov     r9, r15
0x18000a3f7  call    WPP_SF_sd
0x18000a3fc  mov     rcx, [rsi+0B8h]; hLibModule
0x18000a403  call    cs:__imp_FreeLibrary
0x18000a409  mov     qword ptr [rsi+0B8h], 0
0x18000a414  mov     byte ptr [rsi], 0
0x18000a417  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a41e  cmp     rcx, r13
0x18000a421  jz      short loc_18000A447
0x18000a423  test    [rcx+1Ch], r12d
0x18000a427  jz      short loc_18000A447
0x18000a429  cmp     byte ptr [rcx+19h], 6
0x18000a42d  jb      short loc_18000A447
  ... truncated ...
```
