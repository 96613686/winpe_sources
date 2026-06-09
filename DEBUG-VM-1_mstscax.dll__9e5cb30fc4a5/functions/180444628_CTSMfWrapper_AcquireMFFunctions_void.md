# CTSMfWrapper::AcquireMFFunctions(void)

- ea: `0x180444628`
- end: `0x180444e6b`
- name: `?AcquireMFFunctions@CTSMfWrapper@@AEAAJXZ`
- size: `2115`
- prototype: `__int64 __fastcall(CTSMfWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180445080`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x1800e9b1c`
- `0x180444628`
- `0x180688f3e`
- `0x180688fc0`

## import_xrefs

- `msvcrt!wcsnlen` at `0x1804446a8`
- `msvcrt!wcsnlen` at `0x1804446a8`
- `msvcrt!wcscat_s` at `0x1804446c8`
- `msvcrt!wcscat_s` at `0x1804446c8`
- `KERNEL32!LoadLibraryW` at `0x180444733`
- `KERNEL32!LoadLibraryW` at `0x180444733`
- `KERNEL32!SetErrorMode` at `0x18044465b`
- `KERNEL32!SetErrorMode` at `0x180444e37`
- `KERNEL32!SetErrorMode` at `0x18044465b`
- `KERNEL32!SetErrorMode` at `0x180444e37`
- `KERNEL32!GetLastError` at `0x180444746`
- `KERNEL32!GetLastError` at `0x180444794`
- `KERNEL32!GetLastError` at `0x18044489a`
- `KERNEL32!GetLastError` at `0x180444912`
- `KERNEL32!GetLastError` at `0x18044498a`
- `KERNEL32!GetLastError` at `0x180444a02`
- `KERNEL32!GetLastError` at `0x180444a7a`
- `KERNEL32!GetLastError` at `0x180444af2`
- `KERNEL32!GetLastError` at `0x180444b6d`
- `KERNEL32!GetLastError` at `0x180444be8`
- `KERNEL32!GetLastError` at `0x180444c63`
- `KERNEL32!GetLastError` at `0x180444cde`
- `KERNEL32!GetLastError` at `0x180444d59`
- `KERNEL32!GetLastError` at `0x180444dd4`
- `KERNEL32!GetLastError` at `0x180444746`
- `KERNEL32!GetLastError` at `0x180444794`
- `KERNEL32!GetLastError` at `0x18044489a`
- `KERNEL32!GetLastError` at `0x180444912`
- `KERNEL32!GetLastError` at `0x18044498a`
- `KERNEL32!GetLastError` at `0x180444a02`
- `KERNEL32!GetLastError` at `0x180444a7a`
- `KERNEL32!GetLastError` at `0x180444af2`
- `KERNEL32!GetLastError` at `0x180444b6d`
- `KERNEL32!GetLastError` at `0x180444be8`
- `KERNEL32!GetLastError` at `0x180444c63`
- `KERNEL32!GetLastError` at `0x180444cde`
- `KERNEL32!GetLastError` at `0x180444d59`
- `KERNEL32!GetLastError` at `0x180444dd4`
- `KERNEL32!GetProcAddress` at `0x180444874`
- `KERNEL32!GetProcAddress` at `0x180444903`
- `KERNEL32!GetProcAddress` at `0x18044497b`
- `KERNEL32!GetProcAddress` at `0x1804449f3`
- `KERNEL32!GetProcAddress` at `0x180444a6b`
- `KERNEL32!GetProcAddress` at `0x180444ae3`
- `KERNEL32!GetProcAddress` at `0x180444b5b`
- `KERNEL32!GetProcAddress` at `0x180444bd6`
- `KERNEL32!GetProcAddress` at `0x180444c51`
- `KERNEL32!GetProcAddress` at `0x180444ccc`
- `KERNEL32!GetProcAddress` at `0x180444d47`
- `KERNEL32!GetProcAddress` at `0x180444dc2`
- `KERNEL32!GetProcAddress` at `0x180444874`
- `KERNEL32!GetProcAddress` at `0x180444903`
- `KERNEL32!GetProcAddress` at `0x18044497b`
- `KERNEL32!GetProcAddress` at `0x1804449f3`
- `KERNEL32!GetProcAddress` at `0x180444a6b`
- `KERNEL32!GetProcAddress` at `0x180444ae3`
- `KERNEL32!GetProcAddress` at `0x180444b5b`
- `KERNEL32!GetProcAddress` at `0x180444bd6`
- `KERNEL32!GetProcAddress` at `0x180444c51`
- `KERNEL32!GetProcAddress` at `0x180444ccc`
- `KERNEL32!GetProcAddress` at `0x180444d47`
- `KERNEL32!GetProcAddress` at `0x180444dc2`
- `KERNEL32!GetSystemDirectoryW` at `0x18044468f`
- `KERNEL32!GetSystemDirectoryW` at `0x18044468f`

## string_xrefs

- `0x180444945`: `GetProcAddress( MFGetService ) failed.  Non-Fatal.`
- `0x180444974`: `MFCreateMediaSession`
- `0x1804448cd`: `GetProcAddress( MFCreateRemoteDesktopPlugin ) failed.  Non-Fatal.`
- `0x1804448fc`: `MFGetService`
- `0x1804446a1`: `\MF.dll`
- `0x1804446ba`: `\MF.dll`
- `0x18044486a`: `MFCreateRemoteDesktopPlugin`
- `0x180444b25`: `GetProcAddress( MFCreateTopologyNode ) failed.  Non-Fatal.`
- `0x180444b54`: `MFCreateAudioRendererActivate`
- `0x180444aad`: `GetProcAddress( MFCreateTopology ) failed.  Non-Fatal.`
- `0x180444adc`: `MFCreateTopologyNode`
- `0x180444a35`: `GetProcAddress( MFCreatePMPMediaSession ) failed.  Non-Fatal.`
- `0x180444a64`: `MFCreateTopology`
- `0x1804449bd`: `GetProcAddress( MFCreateMediaSession ) failed.  Non-Fatal.`
- `0x1804449ec`: `MFCreatePMPMediaSession`
- `0x180444d11`: `GetProcAddress( MFCreateMPEG4MediaSink ) failed.  Non-Fatal.`
- `0x180444d40`: `MFCreateFMPEG4MediaSink`
- `0x180444c96`: `GetProcAddress( MFCreatePresentationClock ) failed.  Non-Fatal.`
- `0x180444cc5`: `MFCreateMPEG4MediaSink`
- `0x180444c1b`: `GetProcAddress( MFCreateVideoRendererActivate ) failed.  Non-Fatal.`
- `0x180444c4a`: `MFCreatePresentationClock`
- `0x180444ba0`: `GetProcAddress( MFCreateAudioRendererActivate ) failed.  Non-Fatal.`
- `0x180444bcf`: `MFCreateVideoRendererActivate`
- `0x180444e07`: `GetProcAddress( MFCreateSampleGrabberSinkActivate ) failed.  Non-Fatal.`
- `0x180444d8c`: `GetProcAddress( MFCreateFMPEG4MediaSink ) failed.  Non-Fatal.`
- `0x180444dbb`: `MFCreateSampleGrabberSinkActivate`

## pseudocode

```c
__int64 __fastcall CTSMfWrapper::AcquireMFFunctions(CTSMfWrapper *this)
{
  UINT v2; // r12d
  HMODULE LibraryW; // rax
  UINT SystemDirectoryW; // eax
  signed int v5; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int LastError; // eax
  unsigned int v8; // eax
  __int64 v9; // rdx
  signed int v10; // eax
  FARPROC ProcAddress; // rax
  signed int v12; // eax
  signed int v13; // ebx
  unsigned int v14; // eax
  FARPROC v15; // rax
  signed int v16; // eax
  signed int v17; // ebx
  unsigned int v18; // eax
  FARPROC v19; // rax
  signed int v20; // eax
  signed int v21; // ebx
  unsigned int v22; // eax
  FARPROC v23; // rax
  signed int v24; // eax
  signed int v25; // ebx
  unsigned int v26; // eax
  FARPROC v27; // rax
  signed int v28; // eax
  signed int v29; // ebx
  unsigned int v30; // eax
  FARPROC v31; // rax
  signed int v32; // eax
  signed int v33; // ebx
  unsigned int v34; // eax
  FARPROC v35; // rax
  signed int v36; // eax
  signed int v37; // ebx
  unsigned int v38; // eax
  FARPROC v39; // rax
  signed int v40; // eax
  signed int v41; // ebx
  unsigned int v42; // eax
  FARPROC v43; // rax
  signed int v44; // eax
  signed int v45; // ebx
  unsigned int v46; // eax
  FARPROC v47; // rax
  signed int v48; // eax
  signed int v49; // ebx
  unsigned int v50; // eax
  FARPROC v51; // rax
  signed int v52; // eax
  signed int v53; // ebx
  unsigned int v54; // eax
  FARPROC v55; // rax
  signed int v56; // eax
  signed int v57; // ebx
  unsigned int v58; // eax
  WCHAR Buffer[264]; // [rsp+30h] [rbp-248h] BYREF

  v2 = SetErrorMode(0x8001u);
  LibraryW = (HMODULE)*((_QWORD *)this + 7);
  if ( LibraryW )
    goto LABEL_26;
  memset_0(Buffer, 0, 0x208u);
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( SystemDirectoryW )
  {
    if ( SystemDirectoryW + wcsnlen(L"\\MF.dll", 0x104u) <= 0x104 )
    {
      if ( wcscat_s(Buffer, 0x104u, L"\\MF.dll") )
      {
        v5 = -2147467259;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            CurrentThreadActivityIdPrefix);
        }
        goto LABEL_25;
      }
      LibraryW = LoadLibraryW(Buffer);
      *((_QWORD *)this + 7) = LibraryW;
      if ( !LibraryW )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = RdpWppGetCurrentThreadActivityIdPrefix();
          v9 = 23;
LABEL_23:
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids, v8, v5);
          goto LABEL_24;
        }
        goto LABEL_24;
      }
LABEL_26:
      ProcAddress = GetProcAddress(LibraryW, "MFCreateRemoteDesktopPlugin");
      *((_QWORD *)this + 10) = ProcAddress;
      if ( !ProcAddress )
      {
        v12 = GetLastError();
        v13 = v12;
        if ( v12 > 0 )
          v13 = (unsigned __int16)v12 | 0x80070000;
        if ( v13 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v14,
            (__int64)"GetProcAddress( MFCreateRemoteDesktopPlugin ) failed.  Non-Fatal.",
            v13);
        }
      }
      v15 = GetProcAddress(*((HMODULE *)this + 7), "MFGetService");
      *((_QWORD *)this + 11) = v15;
      if ( !v15 )
      {
        v16 = GetLastError();
        v17 = v16;
        if ( v16 > 0 )
          v17 = (unsigned __int16)v16 | 0x80070000;
        if ( v17 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v18 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v18,
            (__int64)"GetProcAddress( MFGetService ) failed.  Non-Fatal.",
            v17);
        }
      }
      v19 = GetProcAddress(*((HMODULE *)this + 7), "MFCreateMediaSession");
      *((_QWORD *)this + 12) = v19;
      if ( !v19 )
      {
        v20 = GetLastError();
        v21 = v20;
        if ( v20 > 0 )
          v21 = (unsigned __int16)v20 | 0x80070000;
        if ( v21 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v22 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v22,
            (__int64)"GetProcAddress( MFCreateMediaSession ) failed.  Non-Fatal.",
            v21);
        }
      }
      v23 = GetProcAddress(*((HMODULE *)this + 7), "MFCreatePMPMediaSession");
      *((_QWORD *)this + 13) = v23;
      if ( !v23 )
      {
        v24 = GetLastError();
        v25 = v24;
        if ( v24 > 0 )
          v25 = (unsigned __int16)v24 | 0x80070000;
        if ( v25 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v26 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v26,
            (__int64)"GetProcAddress( MFCreatePMPMediaSession ) failed.  Non-Fatal.",
            v25);
        }
      }
      v27 = GetProcAddress(*((HMODULE *)this + 7), "MFCreateTopology");
      *((_QWORD *)this + 14) = v27;
      if ( !v27 )
      {
        v28 = GetLastError();
        v29 = v28;
        if ( v28 > 0 )
          v29 = (unsigned __int16)v28 | 0x80070000;
        if ( v29 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v30 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v30,
            (__int64)"GetProcAddress( MFCreateTopology ) failed.  Non-Fatal.",
            v29);
        }
      }
      v31 = GetProcAddress(*((HMODULE *)this + 7), "MFCreateTopologyNode");
      *((_QWORD *)this + 15) = v31;
      if ( !v31 )
      {
        v32 = GetLastError();
        v33 = v32;
        if ( v32 > 0 )
          v33 = (unsigned __int16)v32 | 0x80070000;
        if ( v33 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v34 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v34,
            (__int64)"GetProcAddress( MFCreateTopologyNode ) failed.  Non-Fatal.",
            v33);
        }
      }
      v35 = GetProcAddress(*((HMODULE *)this + 7), "MFCreateAudioRendererActivate");
      *((_QWORD *)this + 16) = v35;
      if ( !v35 )
      {
        v36 = GetLastError();
        v37 = v36;
        if ( v36 > 0 )
          v37 = (unsigned __int16)v36 | 0x80070000;
        if ( v37 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v38 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            30,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v38,
            (__int64)"GetProcAddress( MFCreateAudioRendererActivate ) failed.  Non-Fatal.",
            v37);
        }
      }
      v39 = GetProcAddress(*((HMODULE *)this + 7), "MFCreateVideoRendererActivate");
      *((_QWORD *)this + 17) = v39;
      if ( !v39 )
      {
        v40 = GetLastError();
        v41 = v40;
        if ( v40 > 0 )
          v41 = (unsigned __int16)v40 | 0x80070000;
        if ( v41 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v42 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v42,
            (__int64)"GetProcAddress( MFCreateVideoRendererActivate ) failed.  Non-Fatal.",
            v41);
        }
      }
      v43 = GetProcAddress(*((HMODULE *)this + 7), "MFCreatePresentationClock");
      *((_QWORD *)this + 18) = v43;
      if ( !v43 )
      {
        v44 = GetLastError();
        v45 = v44;
        if ( v44 > 0 )
          v45 = (unsigned __int16)v44 | 0x80070000;
        if ( v45 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v46 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            32,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v46,
            (__int64)"GetProcAddress( MFCreatePresentationClock ) failed.  Non-Fatal.",
            v45);
        }
      }
      v47 = GetProcAddress(*((HMODULE *)this + 7), "MFCreateMPEG4MediaSink");
      *((_QWORD *)this + 19) = v47;
      if ( !v47 )
      {
        v48 = GetLastError();
        v49 = v48;
        if ( v48 > 0 )
          v49 = (unsigned __int16)v48 | 0x80070000;
        if ( v49 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v50 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v50,
            (__int64)"GetProcAddress( MFCreateMPEG4MediaSink ) failed.  Non-Fatal.",
            v49);
        }
      }
      v51 = GetProcAddress(*((HMODULE *)this + 7), "MFCreateFMPEG4MediaSink");
      *((_QWORD *)this + 20) = v51;
      if ( !v51 )
      {
        v52 = GetLastError();
        v53 = v52;
        if ( v52 > 0 )
          v53 = (unsigned __int16)v52 | 0x80070000;
        if ( v53 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v54 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            34,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v54,
            (__int64)"GetProcAddress( MFCreateFMPEG4MediaSink ) failed.  Non-Fatal.",
            v53);
        }
      }
      v55 = GetProcAddress(*((HMODULE *)this + 7), "MFCreateSampleGrabberSinkActivate");
      *((_QWORD *)this + 21) = v55;
      if ( !v55 )
      {
        v56 = GetLastError();
        v57 = v56;
        if ( v56 > 0 )
          v57 = (unsigned __int16)v56 | 0x80070000;
        if ( v57 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v58 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v58,
            (__int64)"GetProcAddress( MFCreateSampleGrabberSinkActivate ) failed.  Non-Fatal.",
            v57);
        }
      }
      v5 = 0;
      goto LABEL_123;
    }
    v5 = -2147467259;
  }
  else
  {
    v10 = GetLastError();
    v5 = v10;
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 21;
    goto LABEL_23;
  }
LABEL_24:
  if ( v5 < 0 )
  {
LABEL_25:
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 11) = 0;
    *((_QWORD *)this + 12) = 0;
    *((_QWORD *)this + 14) = 0;
    *((_QWORD *)this + 15) = 0;
    *((_QWORD *)this + 16) = 0;
    *((_QWORD *)this + 17) = 0;
    *((_QWORD *)this + 18) = 0;
    *((_QWORD *)this + 19) = 0;
    *((_QWORD *)this + 20) = 0;
    *((_QWORD *)this + 21) = 0;
  }
LABEL_123:
  SetErrorMode(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180444628  mov     [rsp+arg_8], rbx
0x18044462d  mov     [rsp+arg_10], rbp
0x180444632  push    rsi
0x180444633  push    rdi
0x180444634  push    r12
0x180444636  push    r14
0x180444638  push    r15
0x18044463a  sub     rsp, 250h
0x180444641  mov     rax, cs:__security_cookie
0x180444648  xor     rax, rsp
0x18044464b  mov     [rsp+278h+var_38], rax
0x180444653  mov     rdi, rcx
0x180444656  mov     ecx, 8001h; uMode
0x18044465b  call    cs:__imp_SetErrorMode
0x180444661  mov     r12d, eax
0x180444664  mov     rax, [rdi+38h]
0x180444668  test    rax, rax
0x18044466b  jnz     loc_18044486A
0x180444671  xor     edx, edx; Val
0x180444673  lea     rcx, [rsp+278h+Buffer]; void *
0x180444678  mov     r8d, 208h; Size
0x18044467e  call    memset_0
0x180444683  mov     esi, 104h
0x180444688  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x18044468d  mov     edx, esi; uSize
0x18044468f  call    cs:__imp_GetSystemDirectoryW
0x180444695  mov     ebx, eax
0x180444697  test    eax, eax
0x180444699  jz      loc_180444794
0x18044469f  mov     edx, esi; MaxCount
0x1804446a1  lea     rcx, aMfDll_0; "\\MF.dll"
0x1804446a8  call    cs:__imp_wcsnlen
0x1804446ae  add     rax, rbx
0x1804446b1  cmp     rax, rsi
0x1804446b4  ja      loc_18044478D
0x1804446ba  lea     r8, aMfDll_0; "\\MF.dll"
0x1804446c1  mov     edx, esi; SizeInWords
0x1804446c3  lea     rcx, [rsp+278h+Buffer]; Destination
0x1804446c8  call    cs:__imp_wcscat_s
0x1804446ce  test    eax, eax
0x1804446d0  jz      short loc_18044472E
0x1804446d2  mov     ebx, 80004005h
0x1804446d7  mov     rax, cs:WPP_GLOBAL_Control
0x1804446de  lea     rbp, WPP_GLOBAL_Control
0x1804446e5  cmp     rax, rbp
0x1804446e8  jz      loc_1804447FB
0x1804446ee  test    byte ptr [rax+1Ch], 1
0x1804446f2  jz      loc_1804447FB
0x1804446f8  mov     sil, 2
0x1804446fb  cmp     [rax+19h], sil
0x1804446ff  jb      loc_1804447FB
0x180444705  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18044470a  mov     rcx, cs:WPP_GLOBAL_Control
0x180444711  lea     r8, WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids
0x180444718  mov     edx, 16h
0x18044471d  mov     r9d, eax
0x180444720  mov     rcx, [rcx+10h]
0x180444724  call    WPP_SF_d
0x180444729  jmp     loc_1804447FB
0x18044472e  lea     rcx, [rsp+278h+Buffer]; lpLibFileName
0x180444733  call    cs:__imp_LoadLibraryW
0x180444739  mov     [rdi+38h], rax
0x18044473d  test    rax, rax
0x180444740  jnz     loc_18044486A
0x180444746  call    cs:__imp_GetLastError
0x18044474c  mov     ebx, eax
0x18044474e  test    eax, eax
0x180444750  jle     short loc_18044475B
0x180444752  movzx   ebx, ax
0x180444755  or      ebx, 80070000h
0x18044475b  mov     rax, cs:WPP_GLOBAL_Control
0x180444762  lea     rbp, WPP_GLOBAL_Control
0x180444769  cmp     rax, rbp
0x18044476c  jz      loc_1804447F3
0x180444772  test    byte ptr [rax+1Ch], 1
0x180444776  jz      short loc_1804447F3
0x180444778  mov     sil, 2
0x18044477b  cmp     [rax+19h], sil
0x18044477f  jb      short loc_1804447F3
0x180444781  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180444786  mov     edx, 17h
0x18044478b  jmp     short loc_1804447D5
0x18044478d  mov     ebx, 80004005h
0x180444792  jmp     short loc_1804447A9
0x180444794  call    cs:__imp_GetLastError
0x18044479a  mov     ebx, eax
0x18044479c  test    eax, eax
0x18044479e  jle     short loc_1804447A9
0x1804447a0  movzx   ebx, ax
0x1804447a3  or      ebx, 80070000h
0x1804447a9  mov     rax, cs:WPP_GLOBAL_Control
0x1804447b0  lea     rbp, WPP_GLOBAL_Control
0x1804447b7  cmp     rax, rbp
0x1804447ba  jz      short loc_1804447F3
0x1804447bc  test    byte ptr [rax+1Ch], 1
0x1804447c0  jz      short loc_1804447F3
0x1804447c2  mov     sil, 2
0x1804447c5  cmp     [rax+19h], sil
0x1804447c9  jb      short loc_1804447F3
0x1804447cb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804447d0  mov     edx, 15h
0x1804447d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1804447dc  lea     r8, WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids
0x1804447e3  mov     r9d, eax
0x1804447e6  mov     dword ptr [rsp+278h+var_258], ebx
0x1804447ea  mov     rcx, [rcx+10h]
0x1804447ee  call    WPP_SF_Dd
0x1804447f3  test    ebx, ebx
0x1804447f5  jns     loc_180444E34
0x1804447fb  mov     qword ptr [rdi+50h], 0
0x180444803  mov     qword ptr [rdi+58h], 0
0x18044480b  mov     qword ptr [rdi+60h], 0
0x180444813  mov     qword ptr [rdi+70h], 0
0x18044481b  mov     qword ptr [rdi+78h], 0
0x180444823  mov     qword ptr [rdi+80h], 0
0x18044482e  mov     qword ptr [rdi+88h], 0
0x180444839  mov     qword ptr [rdi+90h], 0
0x180444844  mov     qword ptr [rdi+98h], 0
0x18044484f  mov     qword ptr [rdi+0A0h], 0
0x18044485a  mov     qword ptr [rdi+0A8h], 0
0x180444865  jmp     loc_180444E34
0x18044486a  lea     rdx, aMfcreateremote_0; "MFCreateRemoteDesktopPlugin"
0x180444871  mov     rcx, rax; hModule
0x180444874  call    cs:__imp_GetProcAddress
0x18044487a  mov     [rdi+50h], rax
0x18044487e  mov     sil, 2
0x180444881  lea     r15, WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids
0x180444888  mov     r14d, 80070000h
0x18044488e  lea     rbp, WPP_GLOBAL_Control
0x180444895  test    rax, rax
0x180444898  jnz     short loc_1804448F8
0x18044489a  call    cs:__imp_GetLastError
0x1804448a0  mov     ebx, eax
0x1804448a2  test    eax, eax
0x1804448a4  jle     short loc_1804448AC
0x1804448a6  movzx   ebx, ax
0x1804448a9  or      ebx, r14d
0x1804448ac  test    ebx, ebx
0x1804448ae  jns     short loc_1804448F8
0x1804448b0  mov     rax, cs:WPP_GLOBAL_Control
0x1804448b7  cmp     rax, rbp
0x1804448ba  jz      short loc_1804448F8
0x1804448bc  test    byte ptr [rax+1Ch], 8
0x1804448c0  jz      short loc_1804448F8
0x1804448c2  cmp     [rax+19h], sil
0x1804448c6  jb      short loc_1804448F8
0x1804448c8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804448cd  lea     rcx, aGetprocaddress_8; "GetProcAddress( MFCreateRemoteDesktopPl"...
0x1804448d4  mov     [rsp+278h+var_250], ebx
0x1804448d8  mov     [rsp+278h+var_258], rcx
0x1804448dd  mov     edx, 18h
0x1804448e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1804448e9  mov     r9d, eax
0x1804448ec  mov     r8, r15
0x1804448ef  mov     rcx, [rcx+10h]
0x1804448f3  call    WPP_SF_DsD
0x1804448f8  mov     rcx, [rdi+38h]; hModule
0x1804448fc  lea     rdx, aMfgetservice; "MFGetService"
0x180444903  call    cs:__imp_GetProcAddress
0x180444909  mov     [rdi+58h], rax
0x18044490d  test    rax, rax
0x180444910  jnz     short loc_180444970
0x180444912  call    cs:__imp_GetLastError
0x180444918  mov     ebx, eax
0x18044491a  test    eax, eax
0x18044491c  jle     short loc_180444924
0x18044491e  movzx   ebx, ax
0x180444921  or      ebx, r14d
0x180444924  test    ebx, ebx
0x180444926  jns     short loc_180444970
0x180444928  mov     rax, cs:WPP_GLOBAL_Control
0x18044492f  cmp     rax, rbp
0x180444932  jz      short loc_180444970
0x180444934  test    byte ptr [rax+1Ch], 8
0x180444938  jz      short loc_180444970
0x18044493a  cmp     [rax+19h], sil
0x18044493e  jb      short loc_180444970
0x180444940  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180444945  lea     rcx, aGetprocaddress_22; "GetProcAddress( MFGetService ) failed. "...
0x18044494c  mov     [rsp+278h+var_250], ebx
0x180444950  mov     [rsp+278h+var_258], rcx
0x180444955  mov     edx, 19h
0x18044495a  mov     rcx, cs:WPP_GLOBAL_Control
0x180444961  mov     r9d, eax
0x180444964  mov     r8, r15
0x180444967  mov     rcx, [rcx+10h]
0x18044496b  call    WPP_SF_DsD
0x180444970  mov     rcx, [rdi+38h]; hModule
0x180444974  lea     rdx, aMfcreatemedias; "MFCreateMediaSession"
0x18044497b  call    cs:__imp_GetProcAddress
0x180444981  mov     [rdi+60h], rax
0x180444985  test    rax, rax
0x180444988  jnz     short loc_1804449E8
0x18044498a  call    cs:__imp_GetLastError
0x180444990  mov     ebx, eax
0x180444992  test    eax, eax
0x180444994  jle     short loc_18044499C
0x180444996  movzx   ebx, ax
0x180444999  or      ebx, r14d
0x18044499c  test    ebx, ebx
0x18044499e  jns     short loc_1804449E8
0x1804449a0  mov     rax, cs:WPP_GLOBAL_Control
0x1804449a7  cmp     rax, rbp
0x1804449aa  jz      short loc_1804449E8
0x1804449ac  test    byte ptr [rax+1Ch], 8
0x1804449b0  jz      short loc_1804449E8
0x1804449b2  cmp     [rax+19h], sil
0x1804449b6  jb      short loc_1804449E8
0x1804449b8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804449bd  lea     rcx, aGetprocaddress_12; "GetProcAddress( MFCreateMediaSession ) "...
0x1804449c4  mov     [rsp+278h+var_250], ebx
0x1804449c8  mov     [rsp+278h+var_258], rcx
0x1804449cd  mov     edx, 1Ah
0x1804449d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1804449d9  mov     r9d, eax
0x1804449dc  mov     r8, r15
0x1804449df  mov     rcx, [rcx+10h]
0x1804449e3  call    WPP_SF_DsD
0x1804449e8  mov     rcx, [rdi+38h]; hModule
0x1804449ec  lea     rdx, aMfcreatepmpmed; "MFCreatePMPMediaSession"
0x1804449f3  call    cs:__imp_GetProcAddress
0x1804449f9  mov     [rdi+68h], rax
0x1804449fd  test    rax, rax
0x180444a00  jnz     short loc_180444A60
0x180444a02  call    cs:__imp_GetLastError
0x180444a08  mov     ebx, eax
0x180444a0a  test    eax, eax
0x180444a0c  jle     short loc_180444A14
0x180444a0e  movzx   ebx, ax
0x180444a11  or      ebx, r14d
0x180444a14  test    ebx, ebx
0x180444a16  jns     short loc_180444A60
0x180444a18  mov     rax, cs:WPP_GLOBAL_Control
0x180444a1f  cmp     rax, rbp
0x180444a22  jz      short loc_180444A60
0x180444a24  test    byte ptr [rax+1Ch], 8
0x180444a28  jz      short loc_180444A60
0x180444a2a  cmp     [rax+19h], sil
0x180444a2e  jb      short loc_180444A60
0x180444a30  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180444a35  lea     rcx, aGetprocaddress_1; "GetProcAddress( MFCreatePMPMediaSession"...
0x180444a3c  mov     [rsp+278h+var_250], ebx
0x180444a40  mov     [rsp+278h+var_258], rcx
0x180444a45  mov     edx, 1Bh
0x180444a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180444a51  mov     r9d, eax
0x180444a54  mov     r8, r15
0x180444a57  mov     rcx, [rcx+10h]
0x180444a5b  call    WPP_SF_DsD
0x180444a60  mov     rcx, [rdi+38h]; hModule
0x180444a64  lea     rdx, aMfcreatetopolo_0; "MFCreateTopology"
0x180444a6b  call    cs:__imp_GetProcAddress
0x180444a71  mov     [rdi+70h], rax
0x180444a75  test    rax, rax
0x180444a78  jnz     short loc_180444AD8
0x180444a7a  call    cs:__imp_GetLastError
0x180444a80  mov     ebx, eax
0x180444a82  test    eax, eax
0x180444a84  jle     short loc_180444A8C
0x180444a86  movzx   ebx, ax
0x180444a89  or      ebx, r14d
0x180444a8c  test    ebx, ebx
0x180444a8e  jns     short loc_180444AD8
0x180444a90  mov     rax, cs:WPP_GLOBAL_Control
0x180444a97  cmp     rax, rbp
0x180444a9a  jz      short loc_180444AD8
0x180444a9c  test    byte ptr [rax+1Ch], 8
0x180444aa0  jz      short loc_180444AD8
0x180444aa2  cmp     [rax+19h], sil
0x180444aa6  jb      short loc_180444AD8
0x180444aa8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180444aad  lea     rcx, aGetprocaddress_32; "GetProcAddress( MFCreateTopology ) fail"...
0x180444ab4  mov     [rsp+278h+var_250], ebx
0x180444ab8  mov     [rsp+278h+var_258], rcx
0x180444abd  mov     edx, 1Ch
0x180444ac2  mov     rcx, cs:WPP_GLOBAL_Control
0x180444ac9  mov     r9d, eax
0x180444acc  mov     r8, r15
0x180444acf  mov     rcx, [rcx+10h]
0x180444ad3  call    WPP_SF_DsD
0x180444ad8  mov     rcx, [rdi+38h]; hModule
0x180444adc  lea     rdx, aMfcreatetopolo; "MFCreateTopologyNode"
0x180444ae3  call    cs:__imp_GetProcAddress
0x180444ae9  mov     [rdi+78h], rax
0x180444aed  test    rax, rax
0x180444af0  jnz     short loc_180444B50
0x180444af2  call    cs:__imp_GetLastError
0x180444af8  mov     ebx, eax
0x180444afa  test    eax, eax
0x180444afc  jle     short loc_180444B04
0x180444afe  movzx   ebx, ax
0x180444b01  or      ebx, r14d
0x180444b04  test    ebx, ebx
0x180444b06  jns     short loc_180444B50
0x180444b08  mov     rax, cs:WPP_GLOBAL_Control
0x180444b0f  cmp     rax, rbp
0x180444b12  jz      short loc_180444B50
0x180444b14  test    byte ptr [rax+1Ch], 8
0x180444b18  jz      short loc_180444B50
0x180444b1a  cmp     [rax+19h], sil
  ... truncated ...
```
