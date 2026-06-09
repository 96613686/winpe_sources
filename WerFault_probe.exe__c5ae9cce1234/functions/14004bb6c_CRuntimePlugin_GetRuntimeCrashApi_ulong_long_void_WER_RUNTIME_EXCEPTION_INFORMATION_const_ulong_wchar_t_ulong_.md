# CRuntimePlugin::GetRuntimeCrashApi(ulong *,long (**)(void *,_WER_RUNTIME_EXCEPTION_INFORMATION * const,ulong,wchar_t *,ulong *,wchar_t *,ulong *),long (**)(void *,_WER_RUNTIME_EXCEPTION_INFORMATION * const,int *,wchar_t *,ulong *,int *),tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *,void * *)

- ea: `0x14004bb6c`
- end: `0x14004c256`
- name: `?GetRuntimeCrashApi@CRuntimePlugin@@AEAAJPEAKPEAP6AJPEAXQEAU_WER_RUNTIME_EXCEPTION_INFORMATION@@KPEA_W030@ZPEAP6AJ12PEAH305@ZPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEAPEAX@Z`
- size: `1770`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004c260`

## callees

- `0x140002470`
- `0x140002728`
- `0x1400030a8`
- `0x140003307`
- `0x140004198`
- `0x14000d28c`
- `0x14001444c`
- `0x140014474`
- `0x140014678`
- `0x140015b40`
- `0x14001d1b8`
- `0x14002ea98`
- `0x14004b7bc`
- `0x14004bb6c`
- `0x14005b770`
- `0x14005b7e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004bfe8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004c026`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004bfe8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004c026`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004c1cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004c1cc`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004bdcc`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004be80`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004bdcc`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004be80`
- `ntdll!DbgPrintEx` at `0x14004bc79`
- `ntdll!DbgPrintEx` at `0x14004bc79`

## string_xrefs

- `0x14004bc6b`: `WER/CrashAPI/%u:%u: ERROR Invalid args in call to WerpGetRuntimeDllsListStart.\n`

## pseudocode

```c
__int64 __fastcall CRuntimePlugin::GetRuntimeCrashApi(
        __int64 a1,
        __int64 a2,
        FARPROC *a3,
        FARPROC *a4,
        HMODULE *a5,
        _QWORD *a6)
{
  __int64 v6; // r12
  LPCVOID v7; // r15
  void *v8; // rbx
  int HeaderFromProcess; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  LPCVOID v12; // rcx
  DWORD CurrentProcessId_0; // eax
  unsigned int v14; // edx
  int v15; // ebx
  SIZE_T v16; // rbx
  _QWORD *v17; // rax
  _QWORD *v18; // r12
  SIZE_T v19; // r9
  __int64 v20; // rbx
  __int64 v21; // rdx
  CUserModeHangReport *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r8
  WCHAR *v25; // r9
  WCHAR *v26; // rcx
  int v27; // r11d
  __int64 v28; // rax
  WCHAR v29; // r10
  char v30; // al
  CUserModeHangReport *v31; // rcx
  __int64 v32; // rdx
  int lpNumberOfBytesRead; // [rsp+20h] [rbp-13E8h]
  int v35; // [rsp+40h] [rbp-13C8h]
  unsigned int v36; // [rsp+44h] [rbp-13C4h]
  SIZE_T NumberOfBytesRead; // [rsp+48h] [rbp-13C0h] BYREF
  int v38; // [rsp+50h] [rbp-13B8h]
  WCHAR *v39; // [rsp+58h] [rbp-13B0h]
  __int64 v40; // [rsp+60h] [rbp-13A8h]
  __int64 v41; // [rsp+68h] [rbp-13A0h]
  unsigned int v42; // [rsp+70h] [rbp-1398h]
  int v43; // [rsp+74h] [rbp-1394h]
  __int64 v44; // [rsp+78h] [rbp-1390h]
  WCHAR *v45; // [rsp+80h] [rbp-1388h]
  __int64 v46; // [rsp+88h] [rbp-1380h]
  __int64 v47; // [rsp+90h] [rbp-1378h]
  HMODULE *v48; // [rsp+98h] [rbp-1370h]
  FARPROC *v49; // [rsp+A0h] [rbp-1368h]
  FARPROC *v50; // [rsp+A8h] [rbp-1360h]
  __int64 v51; // [rsp+B0h] [rbp-1358h]
  _QWORD *v52; // [rsp+B8h] [rbp-1350h]
  LPCVOID v53; // [rsp+C0h] [rbp-1348h]
  _QWORD *v54; // [rsp+C8h] [rbp-1340h]
  _BYTE v55[2296]; // [rsp+D0h] [rbp-1338h] BYREF
  LPCVOID lpBaseAddress; // [rsp+9C8h] [rbp-A40h]
  __int128 Buffer; // [rsp+A40h] [rbp-9C8h] BYREF
  __int64 v58; // [rsp+A50h] [rbp-9B8h]
  WCHAR Src[1208]; // [rsp+A60h] [rbp-9A8h] BYREF

  v49 = a4;
  v50 = a3;
  v51 = a2;
  v6 = a1;
  v41 = a1;
  v48 = a5;
  v52 = a6;
  v44 = 0;
  v7 = 0;
  v8 = *(void **)(a1 + 760);
  memset_0(v55, 0, 0x968u);
  if ( !v8 )
  {
    CurrentProcessId_0 = GetCurrentProcessId_0();
    DbgPrintEx(
      0x96u,
      0,
      "WER/CrashAPI/%u:%u: ERROR Invalid args in call to WerpGetRuntimeDllsListStart.\n",
      CurrentProcessId_0,
      5548);
    HeaderFromProcess = -2147024809;
    goto LABEL_7;
  }
  memset_0(Src, 0, 0x968u);
  memcpy_0(v55, Src, 0x968u);
  HeaderFromProcess = WerpGetHeaderFromProcess(v8, v55);
  if ( HeaderFromProcess < 0 )
  {
LABEL_7:
    v12 = 0;
    goto LABEL_8;
  }
  v12 = lpBaseAddress;
  if ( !lpBaseAddress )
  {
    HeaderFromProcess = -2147023728;
    goto LABEL_7;
  }
  v7 = lpBaseAddress;
  HeaderFromProcess = 0;
LABEL_8:
  if ( (int)(HeaderFromProcess + 0x80000000) >= 0 && HeaderFromProcess != -2147023728 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids,
        (unsigned int)HeaderFromProcess);
    }
    return (unsigned int)HeaderFromProcess;
  }
  if ( v12 )
  {
    v14 = 0;
    v15 = 0;
    v35 = 0;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids,
        v7,
        lpNumberOfBytesRead);
      v14 = 0;
    }
    while ( 1 )
    {
      if ( v15 )
        return v15 == 0 ? 0x80004005 : 0;
      if ( !v7 )
        return v15 == 0 ? 0x80004005 : 0;
      v36 = v14 + 1;
      v42 = v14 + 1;
      if ( v14 >= 0x10 )
        return v15 == 0 ? 0x80004005 : 0;
      Buffer = 0;
      v58 = 0;
      v38 = 0;
      NumberOfBytesRead = 0;
      if ( !ReadProcessMemory(*(HANDLE *)(v6 + 760), v7, &Buffer, 0x18u, &NumberOfBytesRead) || NumberOfBytesRead != 24 )
      {
        GetLastError();
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
        }
        return v15 == 0 ? 0x80004005 : 0;
      }
      v38 = DWORD2(Buffer);
      if ( (unsigned int)(DWORD2(Buffer) - 24) > 0x208 )
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids,
            DWORD2(Buffer));
        }
        return v15 == 0 ? 0x80004005 : 0;
      }
      NumberOfBytesRead = 0;
      v16 = DWORD2(Buffer);
      v17 = operator new[](DWORD2(Buffer), (const struct std::nothrow_t *)&std::nothrow);
      v18 = v17;
      v54 = v17;
      if ( !v17 )
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
        }
        v15 = v35;
        return v15 == 0 ? 0x80004005 : 0;
      }
      v19 = v16;
      v20 = v41;
      if ( !ReadProcessMemory(*(HANDLE *)(v41 + 760), v7, v17, v19, &NumberOfBytesRead) )
      {
        v7 = 0;
        v53 = 0;
        goto LABEL_75;
      }
      v7 = (LPCVOID)*v18;
      v53 = v7;
      if ( v7 == (LPCVOID)-24LL )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v23 = (unsigned int)((_DWORD)v7 + 50);
          goto LABEL_40;
        }
        goto LABEL_75;
      }
      Src[0] = 0;
      v24 = 2147483646;
      v47 = 2147483646;
      v25 = (WCHAR *)(v18 + 3);
      v45 = (WCHAR *)(v18 + 3);
      v21 = 260;
      v46 = 260;
      v26 = Src;
      v39 = Src;
      v27 = 0;
      v28 = 0;
      v40 = 0;
      while ( v21 )
      {
        if ( !v24 )
          goto LABEL_48;
        v29 = *v25;
        if ( *v25 == (_WORD)v44 )
          goto LABEL_48;
        v45 = ++v25;
        *v26++ = v29;
        v39 = v26;
        v46 = --v21;
        v47 = --v24;
        v40 = ++v28;
      }
      v39 = --v26;
      v40 = v28 - 1;
      v27 = -2147024774;
LABEL_48:
      *v26 = 0;
      if ( v27 < 0 )
        break;
      if ( RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\Windows Error Reporting\\RuntimeExceptionHelperModules",
             Src,
             0x10u,
             0,
             0,
             0) )
      {
        if ( RegGetValueW(
               HKEY_CURRENT_USER,
               L"Software\\Microsoft\\Windows\\Windows Error Reporting\\RuntimeExceptionHelperModules",
               Src,
               0x10u,
               0,
               0,
               0) )
        {
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v23 = 28;
LABEL_40:
            WPP_SF_(*((_QWORD *)v22 + 2), v23, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
          }
LABEL_75:
          v15 = v35;
          goto LABEL_76;
        }
        v30 = 1;
        *(_DWORD *)(v20 + 2808) = 1;
      }
      else
      {
        v30 = 2;
      }
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)&WPP_f577d8521c9b39ef05153804ed8add08_Traceguids,
          (unsigned int)Src,
          v30);
      }
      if ( (int)CRuntimePlugin::AskModuleToClaimCrash(v20, Src, v18[2], v51, v50, v49, v48) < 0 )
      {
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        {
          goto LABEL_75;
        }
        v32 = 32;
LABEL_67:
        WPP_SF_S(*((_QWORD *)v31 + 2), v32, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids, Src);
        goto LABEL_75;
      }
      if ( *(_DWORD *)(v20 + 2808) )
      {
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        {
          goto LABEL_75;
        }
        v32 = 31;
        goto LABEL_67;
      }
      v15 = 1;
      v35 = 1;
      v43 = 1;
      *v52 = v18[2];
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids, Src);
      }
LABEL_76:
      operator delete(v18, (const struct std::nothrow_t *)v21);
      v14 = v36;
      v6 = v41;
    }
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v23 = 27;
      goto LABEL_40;
    }
    goto LABEL_75;
  }
  if ( HeaderFromProcess != -2147023728 )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, 0x80000000LL, v10, v11);
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
  }
  return (unsigned int)-2147023728;
}

```

## disassembly

```asm
0x14004bb6c  push    rbx
0x14004bb6e  push    rsi
0x14004bb6f  push    rdi
0x14004bb70  push    r12
0x14004bb72  push    r15
0x14004bb74  mov     eax, 13E0h
0x14004bb79  call    _alloca_probe
0x14004bb7e  sub     rsp, rax
0x14004bb81  mov     rax, cs:__security_cookie
0x14004bb88  xor     rax, rsp
0x14004bb8b  mov     [rsp+1408h+var_38], rax
0x14004bb93  mov     [rsp+1408h+var_1368], r9
0x14004bb9b  mov     [rsp+1408h+var_1360], r8
0x14004bba3  mov     [rsp+1408h+var_1358], rdx
0x14004bbab  mov     r12, rcx
0x14004bbae  mov     [rsp+1408h+var_13A0], rcx
0x14004bbb3  mov     rax, [rsp+1408h+arg_20]
0x14004bbbb  mov     [rsp+1408h+var_1370], rax
0x14004bbc3  mov     rax, [rsp+1408h+arg_28]
0x14004bbcb  mov     [rsp+1408h+var_1350], rax
0x14004bbd3  xor     edi, edi
0x14004bbd5  mov     [rsp+1408h+var_1390], rdi
0x14004bbda  mov     r15d, edi
0x14004bbdd  mov     rbx, [rcx+2F8h]
0x14004bbe4  mov     esi, 968h
0x14004bbe9  mov     r8d, esi; Size
0x14004bbec  xor     edx, edx; Val
0x14004bbee  lea     rcx, [rsp+1408h+var_1338]; void *
0x14004bbf6  call    memset_0
0x14004bbfb  test    rbx, rbx
0x14004bbfe  jz      short loc_14004BC5B
0x14004bc00  mov     r8d, esi; Size
0x14004bc03  xor     edx, edx; Val
0x14004bc05  lea     rcx, [rsp+1408h+Src]; void *
0x14004bc0d  call    memset_0
0x14004bc12  lea     rcx, [rsp+1408h+var_1338]; void *
0x14004bc1a  lea     rdx, [rsp+1408h+Src]; Src
0x14004bc22  mov     r8d, esi; Size
0x14004bc25  call    memcpy_0
0x14004bc2a  lea     rdx, [rsp+1408h+var_1338]; lpBuffer
0x14004bc32  mov     rcx, rbx; hProcess
0x14004bc35  call    WerpGetHeaderFromProcess
0x14004bc3a  mov     ebx, eax
0x14004bc3c  test    eax, eax
0x14004bc3e  js      short loc_14004BC84
0x14004bc40  mov     rcx, [rsp+1408h+lpBaseAddress]
0x14004bc48  test    rcx, rcx
0x14004bc4b  jnz     short loc_14004BC54
0x14004bc4d  mov     ebx, 80070490h
0x14004bc52  jmp     short loc_14004BC84
0x14004bc54  mov     r15, rcx
0x14004bc57  mov     ebx, edi
0x14004bc59  jmp     short loc_14004BC87
0x14004bc5b  call    GetCurrentProcessId_0
0x14004bc60  mov     r9d, eax
0x14004bc63  mov     dword ptr [rsp+1408h+lpNumberOfBytesRead], 15ACh
0x14004bc6b  lea     r8, aWerCrashapiUUE_3; "WER/CrashAPI/%u:%u: ERROR Invalid args "...
0x14004bc72  xor     edx, edx; Level
0x14004bc74  mov     ecx, 96h; ComponentId
0x14004bc79  call    cs:__imp_DbgPrintEx
0x14004bc7f  mov     ebx, 80070057h
0x14004bc84  mov     rcx, rdi
0x14004bc87  mov     edx, 80000000h
0x14004bc8c  lea     eax, [rbx+rdx]
0x14004bc8f  test    edx, eax
0x14004bc91  jnz     short loc_14004BCD9
0x14004bc93  cmp     ebx, 80070490h
0x14004bc99  jz      short loc_14004BCD9
0x14004bc9b  lea     rsi, WPP_GLOBAL_Control
0x14004bca2  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bca9  cmp     rcx, rsi
0x14004bcac  jz      loc_14004C235
0x14004bcb2  test    byte ptr [rcx+1Ch], 1
0x14004bcb6  jz      loc_14004C235
0x14004bcbc  mov     edx, 15h
0x14004bcc1  mov     r9d, ebx
0x14004bcc4  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x14004bccb  mov     rcx, [rcx+10h]
0x14004bccf  call    WPP_SF_d
0x14004bcd4  jmp     loc_14004C235
0x14004bcd9  test    rcx, rcx
0x14004bcdc  jnz     short loc_14004BD23
0x14004bcde  cmp     ebx, 80070490h
0x14004bce4  jz      short loc_14004BCEB
0x14004bce6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14004bceb  lea     rsi, WPP_GLOBAL_Control
0x14004bcf2  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bcf9  cmp     rcx, rsi
0x14004bcfc  jz      short loc_14004BD19
0x14004bcfe  test    byte ptr [rcx+1Ch], 4
0x14004bd02  jz      short loc_14004BD19
0x14004bd04  mov     edx, 16h
0x14004bd09  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x14004bd10  mov     rcx, [rcx+10h]
0x14004bd14  call    WPP_SF_
0x14004bd19  mov     ebx, 80070490h
0x14004bd1e  jmp     loc_14004C235
0x14004bd23  mov     edx, edi
0x14004bd25  mov     [rsp+1408h+var_13C4], edx
0x14004bd29  mov     ebx, edi
0x14004bd2b  mov     [rsp+1408h+var_13C8], ebx
0x14004bd2f  lea     rsi, WPP_GLOBAL_Control
0x14004bd36  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bd3d  lea     rdi, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x14004bd44  cmp     rcx, rsi
0x14004bd47  jz      short loc_14004BD65
0x14004bd49  test    byte ptr [rcx+1Ch], 8
0x14004bd4d  jz      short loc_14004BD65
0x14004bd4f  mov     edx, 17h
0x14004bd54  mov     r9, r15
0x14004bd57  mov     r8, rdi
0x14004bd5a  mov     rcx, [rcx+10h]
0x14004bd5e  call    WPP_SF_q
0x14004bd63  mov     edx, ebx
0x14004bd65  xor     ecx, ecx
0x14004bd67  test    ebx, ebx
0x14004bd69  jnz     loc_14004BE50
0x14004bd6f  test    r15, r15
0x14004bd72  jz      loc_14004BE50
0x14004bd78  mov     eax, edx
0x14004bd7a  inc     edx
0x14004bd7c  mov     [rsp+1408h+var_13C4], edx
0x14004bd80  mov     [rsp+1408h+var_1398], edx
0x14004bd84  cmp     eax, 10h
0x14004bd87  jnb     loc_14004BE50
0x14004bd8d  xorps   xmm0, xmm0
0x14004bd90  xor     eax, eax
0x14004bd92  movups  [rsp+1408h+Buffer], xmm0
0x14004bd9a  mov     [rsp+1408h+var_9B8], rax
0x14004bda2  mov     [rsp+1408h+var_13B8], ecx
0x14004bda6  mov     [rsp+1408h+NumberOfBytesRead], rcx
0x14004bdab  lea     rax, [rsp+1408h+NumberOfBytesRead]
0x14004bdb0  mov     [rsp+1408h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x14004bdb5  lea     r9d, [rcx+18h]; nSize
0x14004bdb9  lea     r8, [rsp+1408h+Buffer]; lpBuffer
0x14004bdc1  mov     rdx, r15; lpBaseAddress
0x14004bdc4  mov     rcx, [r12+2F8h]; hProcess
0x14004bdcc  call    cs:__imp_ReadProcessMemory
0x14004bdd2  xor     ecx, ecx
0x14004bdd4  test    eax, eax
0x14004bdd6  jz      loc_14004C1CC
0x14004bddc  cmp     [rsp+1408h+NumberOfBytesRead], 18h
0x14004bde2  jnz     loc_14004C1CC
0x14004bde8  mov     r9d, dword ptr [rsp+1408h+Buffer+8]
0x14004bdf0  mov     [rsp+1408h+var_13B8], r9d
0x14004bdf5  lea     eax, [r9-18h]
0x14004bdf9  cmp     eax, 208h
0x14004bdfe  ja      loc_14004C19C
0x14004be04  mov     [rsp+1408h+NumberOfBytesRead], rcx
0x14004be09  mov     ebx, r9d
0x14004be0c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14004be13  mov     ecx, r9d; unsigned __int64
0x14004be16  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14004be1b  mov     r12, rax
0x14004be1e  mov     [rsp+1408h+var_1340], rax
0x14004be26  test    rax, rax
0x14004be29  jnz     short loc_14004BE61
0x14004be2b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004be32  cmp     rcx, rsi
0x14004be35  jz      short loc_14004BE4C
0x14004be37  test    byte ptr [rcx+1Ch], 1
0x14004be3b  jz      short loc_14004BE4C
0x14004be3d  lea     edx, [rax+19h]
0x14004be40  mov     r8, rdi
0x14004be43  mov     rcx, [rcx+10h]
0x14004be47  call    WPP_SF_
0x14004be4c  mov     ebx, [rsp+1408h+var_13C8]
0x14004be50  neg     ebx
0x14004be52  sbb     ebx, ebx
0x14004be54  not     ebx
0x14004be56  and     ebx, 80004005h
0x14004be5c  jmp     loc_14004C235
0x14004be61  lea     rax, [rsp+1408h+NumberOfBytesRead]
0x14004be66  mov     [rsp+1408h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x14004be6b  mov     r9, rbx; nSize
0x14004be6e  mov     r8, r12; lpBuffer
0x14004be71  mov     rdx, r15; lpBaseAddress
0x14004be74  mov     rbx, [rsp+1408h+var_13A0]
0x14004be79  mov     rcx, [rbx+2F8h]; hProcess
0x14004be80  call    cs:__imp_ReadProcessMemory
0x14004be86  xor     r10d, r10d
0x14004be89  test    eax, eax
0x14004be8b  jz      loc_14004C177
0x14004be91  mov     r15, [r12]
0x14004be95  mov     [rsp+1408h+var_1348], r15
0x14004be9d  lea     rax, [r15+18h]
0x14004bea1  test    rax, rax
0x14004bea4  jnz     short loc_14004BED4
0x14004bea6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bead  cmp     rcx, rsi
0x14004beb0  jz      loc_14004C182
0x14004beb6  test    byte ptr [rcx+1Ch], 1
0x14004beba  jz      loc_14004C182
0x14004bec0  lea     edx, [rax+1Ah]
0x14004bec3  mov     r8, rdi
0x14004bec6  mov     rcx, [rcx+10h]
0x14004beca  call    WPP_SF_
0x14004becf  jmp     loc_14004C182
0x14004bed4  mov     [rsp+1408h+Src], r10w
0x14004bedd  mov     r8d, 7FFFFFFEh
0x14004bee3  mov     [rsp+1408h+var_1378], r8
0x14004beeb  lea     r9, [r12+18h]
0x14004bef0  mov     [rsp+1408h+var_1388], r9
0x14004bef8  mov     edx, 104h
0x14004befd  mov     [rsp+1408h+var_1380], rdx
0x14004bf05  lea     rcx, [rsp+1408h+Src]
0x14004bf0d  mov     [rsp+1408h+var_13B0], rcx
0x14004bf12  mov     r11d, r10d
0x14004bf15  mov     rax, r10
0x14004bf18  mov     [rsp+1408h+var_13A8], rax
0x14004bf1d  test    rdx, rdx
0x14004bf20  jz      short loc_14004BF77
0x14004bf22  test    r8, r8
0x14004bf25  jz      short loc_14004BF72
0x14004bf27  movzx   r10d, word ptr [r9]
0x14004bf2b  cmp     r10w, word ptr [rsp+1408h+var_1390]
0x14004bf31  jz      short loc_14004BF6F
0x14004bf33  add     r9, 2
0x14004bf37  mov     [rsp+1408h+var_1388], r9
0x14004bf3f  mov     [rcx], r10w
0x14004bf43  add     rcx, 2
0x14004bf47  mov     [rsp+1408h+var_13B0], rcx
0x14004bf4c  dec     rdx
0x14004bf4f  mov     [rsp+1408h+var_1380], rdx
0x14004bf57  dec     r8
0x14004bf5a  mov     [rsp+1408h+var_1378], r8
0x14004bf62  inc     rax
0x14004bf65  mov     [rsp+1408h+var_13A8], rax
0x14004bf6a  xor     r10d, r10d
0x14004bf6d  jmp     short loc_14004BF1D
0x14004bf6f  xor     r10d, r10d
0x14004bf72  test    rdx, rdx
0x14004bf75  jnz     short loc_14004BF8E
0x14004bf77  sub     rcx, 2
0x14004bf7b  mov     [rsp+1408h+var_13B0], rcx
0x14004bf80  dec     rax
0x14004bf83  mov     [rsp+1408h+var_13A8], rax
0x14004bf88  mov     r11d, 8007007Ah
0x14004bf8e  mov     eax, r10d
0x14004bf91  mov     [rcx], ax
0x14004bf94  test    r11d, r11d
0x14004bf97  jns     short loc_14004BFBD
0x14004bf99  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bfa0  cmp     rcx, rsi
0x14004bfa3  jz      loc_14004C182
0x14004bfa9  test    byte ptr [rcx+1Ch], 1
0x14004bfad  jz      loc_14004C182
0x14004bfb3  mov     edx, 1Bh
0x14004bfb8  jmp     loc_14004BEC3
0x14004bfbd  mov     [rsp+1408h+pcbData], r10; pcbData
0x14004bfc2  mov     [rsp+1408h+pvData], r10; pvData
0x14004bfc7  mov     [rsp+1408h+lpNumberOfBytesRead], r10; pdwType
0x14004bfcc  mov     r9d, 10h; dwFlags
0x14004bfd2  lea     r8, [rsp+1408h+Src]; lpValue
0x14004bfda  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\Windows E"...
0x14004bfe1  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14004bfe8  call    cs:__imp_RegGetValueW
0x14004bfee  xor     r10d, r10d
0x14004bff1  test    eax, eax
0x14004bff3  jnz     short loc_14004BFFB
0x14004bff5  lea     eax, [r10+2]
0x14004bff9  jmp     short loc_14004C03F
0x14004bffb  mov     [rsp+1408h+pcbData], r10; pcbData
0x14004c000  mov     [rsp+1408h+pvData], r10; pvData
0x14004c005  mov     [rsp+1408h+lpNumberOfBytesRead], r10; pdwType
0x14004c00a  mov     r9d, 10h; dwFlags
0x14004c010  lea     r8, [rsp+1408h+Src]; lpValue
0x14004c018  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\Windows E"...
0x14004c01f  mov     rcx, 0FFFFFFFF80000001h; hkey
0x14004c026  call    cs:__imp_RegGetValueW
0x14004c02c  test    eax, eax
0x14004c02e  jnz     loc_14004C15B
0x14004c034  mov     eax, 1
0x14004c039  mov     [rbx+0AF8h], eax
0x14004c03f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c046  cmp     rcx, rsi
0x14004c049  jz      short loc_14004C06E
0x14004c04b  test    byte ptr [rcx+1Ch], 8
0x14004c04f  jz      short loc_14004C06E
0x14004c051  mov     edx, 1Dh
0x14004c056  mov     dword ptr [rsp+1408h+lpNumberOfBytesRead], eax
0x14004c05a  lea     r9, [rsp+1408h+Src]
0x14004c062  mov     r8, rdi
0x14004c065  mov     rcx, [rcx+10h]
0x14004c069  call    WPP_SF_Sd
0x14004c06e  mov     rax, [rsp+1408h+var_1370]
0x14004c076  mov     [rsp+1408h+pcbData], rax
0x14004c07b  mov     rax, [rsp+1408h+var_1368]
0x14004c083  mov     [rsp+1408h+pvData], rax
0x14004c088  mov     rax, [rsp+1408h+var_1360]
0x14004c090  mov     [rsp+1408h+lpNumberOfBytesRead], rax
0x14004c095  mov     r9, [rsp+1408h+var_1358]
0x14004c09d  mov     r8, [r12+10h]
0x14004c0a2  lea     rdx, [rsp+1408h+Src]
0x14004c0aa  mov     rcx, rbx
0x14004c0ad  call    ?AskModuleToClaimCrash@CRuntimePlugin@@AEAAJPEB_WPEAXPEAKPEAP6AJ1QEAU_WER_RUNTIME_EXCEPTION_INFORMATION@@KPEA_W242@ZPEAP6AJ13PEAH426@ZPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@@Z; CRuntimePlugin::AskModuleToClaimCrash(wchar_t const *,void *,ulong *,long (**)(void *,_WER_RUNTIME_EXCEPTION_INFORMATION * const,ulong,wchar_t *,ulong *,wchar_t *,ulong *),long (**)(void *,_WER_RUNTIME_EXCEPTION_INFORMATION * const,int *,wchar_t *,ulong *,int *),tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *)
0x14004c0b2  xor     r10d, r10d
0x14004c0b5  test    eax, eax
0x14004c0b7  js      loc_14004C142
0x14004c0bd  cmp     [rbx+0AF8h], r10d
  ... truncated ...
```
