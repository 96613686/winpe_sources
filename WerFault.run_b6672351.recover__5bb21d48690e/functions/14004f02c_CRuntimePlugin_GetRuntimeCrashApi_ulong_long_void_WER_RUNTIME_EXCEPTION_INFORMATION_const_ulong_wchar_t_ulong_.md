# CRuntimePlugin::GetRuntimeCrashApi(ulong *,long (**)(void *,_WER_RUNTIME_EXCEPTION_INFORMATION * const,ulong,wchar_t *,ulong *,wchar_t *,ulong *),long (**)(void *,_WER_RUNTIME_EXCEPTION_INFORMATION * const,int *,wchar_t *,ulong *,int *),tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *,void * *)

- ea: `0x14004f02c`
- end: `0x14004f73b`
- name: `?GetRuntimeCrashApi@CRuntimePlugin@@AEAAJPEAKPEAP6AJPEAXQEAU_WER_RUNTIME_EXCEPTION_INFORMATION@@KPEA_W030@ZPEAP6AJ12PEAH305@ZPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEAPEAX@Z`
- size: `1807`
- prototype: `__int64 __fastcall(__int64, __int64, FARPROC *, FARPROC *, HMODULE *, _QWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004f750`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400030f8`
- `0x140003357`
- `0x1400041e8`
- `0x14000d544`
- `0x140014ee4`
- `0x140014f14`
- `0x140015138`
- `0x1400166ec`
- `0x14001e428`
- `0x1400308b8`
- `0x14004ec4c`
- `0x14004f02c`
- `0x14005f510`
- `0x14005f588`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004f4ba`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004f4fe`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004f4ba`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004f4fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f6aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f6aa`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004f292`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004f34c`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004f292`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004f34c`
- `ntdll!DbgPrintEx` at `0x14004f139`
- `ntdll!DbgPrintEx` at `0x14004f139`

## string_xrefs

- `0x14004f12b`: `WER/CrashAPI/%u:%u: ERROR Invalid args in call to WerpGetRuntimeDllsListStart.\n`

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
  LPCVOID v10; // rcx
  DWORD CurrentProcessId_0; // eax
  unsigned int v12; // edx
  int v13; // ebx
  SIZE_T v14; // rbx
  _QWORD *v15; // rax
  _QWORD *v16; // r12
  SIZE_T v17; // r9
  __int64 v18; // rbx
  __int64 v19; // rdx
  CUserModeHangReport *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  WCHAR *v23; // r9
  WCHAR *v24; // rcx
  int v25; // r11d
  __int64 v26; // rax
  WCHAR v27; // r10
  char v28; // al
  CUserModeHangReport *v29; // rcx
  __int64 v30; // rdx
  int v32; // [rsp+40h] [rbp-13C8h]
  unsigned int v33; // [rsp+44h] [rbp-13C4h]
  SIZE_T NumberOfBytesRead; // [rsp+48h] [rbp-13C0h] BYREF
  int v35; // [rsp+50h] [rbp-13B8h]
  WCHAR *v36; // [rsp+58h] [rbp-13B0h]
  __int64 v37; // [rsp+60h] [rbp-13A8h]
  __int64 v38; // [rsp+68h] [rbp-13A0h]
  unsigned int v39; // [rsp+70h] [rbp-1398h]
  int v40; // [rsp+74h] [rbp-1394h]
  __int64 v41; // [rsp+78h] [rbp-1390h]
  WCHAR *v42; // [rsp+80h] [rbp-1388h]
  __int64 v43; // [rsp+88h] [rbp-1380h]
  __int64 v44; // [rsp+90h] [rbp-1378h]
  HMODULE *v45; // [rsp+98h] [rbp-1370h]
  FARPROC *v46; // [rsp+A0h] [rbp-1368h]
  FARPROC *v47; // [rsp+A8h] [rbp-1360h]
  __int64 v48; // [rsp+B0h] [rbp-1358h]
  _QWORD *v49; // [rsp+B8h] [rbp-1350h]
  LPCVOID v50; // [rsp+C0h] [rbp-1348h]
  _QWORD *v51; // [rsp+C8h] [rbp-1340h]
  _BYTE v52[2296]; // [rsp+D0h] [rbp-1338h] BYREF
  LPCVOID lpBaseAddress; // [rsp+9C8h] [rbp-A40h]
  __int128 Buffer; // [rsp+A40h] [rbp-9C8h] BYREF
  __int64 v55; // [rsp+A50h] [rbp-9B8h]
  WCHAR Src[1208]; // [rsp+A60h] [rbp-9A8h] BYREF

  v46 = a4;
  v47 = a3;
  v48 = a2;
  v6 = a1;
  v38 = a1;
  v45 = a5;
  v49 = a6;
  v41 = 0;
  v7 = 0;
  v8 = *(void **)(a1 + 760);
  memset_0(v52, 0, 0x968u);
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
  memcpy_0(v52, Src, 0x968u);
  HeaderFromProcess = WerpGetHeaderFromProcess(v8, v52);
  if ( HeaderFromProcess < 0 )
  {
LABEL_7:
    v10 = 0;
    goto LABEL_8;
  }
  v10 = lpBaseAddress;
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
        WPP_f577d8521c9b39ef05153804ed8add08_Traceguids,
        (unsigned int)HeaderFromProcess);
    }
    return (unsigned int)HeaderFromProcess;
  }
  if ( v10 )
  {
    v12 = 0;
    v13 = 0;
    v32 = 0;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids, v7);
      v12 = 0;
    }
    while ( 1 )
    {
      if ( v13 )
        return v13 == 0 ? 0x80004005 : 0;
      if ( !v7 )
        return v13 == 0 ? 0x80004005 : 0;
      v33 = v12 + 1;
      v39 = v12 + 1;
      if ( v12 >= 0x10 )
        return v13 == 0 ? 0x80004005 : 0;
      Buffer = 0;
      v55 = 0;
      v35 = 0;
      NumberOfBytesRead = 0;
      if ( !ReadProcessMemory(*(HANDLE *)(v6 + 760), v7, &Buffer, 0x18u, &NumberOfBytesRead) || NumberOfBytesRead != 24 )
      {
        GetLastError();
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
        }
        return v13 == 0 ? 0x80004005 : 0;
      }
      v35 = DWORD2(Buffer);
      if ( (unsigned int)(DWORD2(Buffer) - 24) > 0x208 )
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            WPP_f577d8521c9b39ef05153804ed8add08_Traceguids,
            DWORD2(Buffer));
        }
        return v13 == 0 ? 0x80004005 : 0;
      }
      NumberOfBytesRead = 0;
      v14 = DWORD2(Buffer);
      v15 = operator new[](DWORD2(Buffer), (const struct std::nothrow_t *)&std::nothrow);
      v16 = v15;
      v51 = v15;
      if ( !v15 )
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
        }
        v13 = v32;
        return v13 == 0 ? 0x80004005 : 0;
      }
      v17 = v14;
      v18 = v38;
      if ( !ReadProcessMemory(*(HANDLE *)(v38 + 760), v7, v15, v17, &NumberOfBytesRead) )
      {
        v7 = 0;
        v50 = 0;
        goto LABEL_75;
      }
      v7 = (LPCVOID)*v16;
      v50 = v7;
      if ( v7 == (LPCVOID)-24LL )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v21 = (unsigned int)((_DWORD)v7 + 50);
          goto LABEL_40;
        }
        goto LABEL_75;
      }
      Src[0] = 0;
      v22 = 2147483646;
      v44 = 2147483646;
      v23 = (WCHAR *)(v16 + 3);
      v42 = (WCHAR *)(v16 + 3);
      v19 = 260;
      v43 = 260;
      v24 = Src;
      v36 = Src;
      v25 = 0;
      v26 = 0;
      v37 = 0;
      while ( v19 )
      {
        if ( !v22 )
          goto LABEL_48;
        v27 = *v23;
        if ( *v23 == (_WORD)v41 )
          goto LABEL_48;
        v42 = ++v23;
        *v24++ = v27;
        v36 = v24;
        v43 = --v19;
        v44 = --v22;
        v37 = ++v26;
      }
      v36 = --v24;
      v37 = v26 - 1;
      v25 = -2147024774;
LABEL_48:
      *v24 = 0;
      if ( v25 < 0 )
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
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v21 = 28;
LABEL_40:
            WPP_SF_(*((_QWORD *)v20 + 2), v21, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
          }
LABEL_75:
          v13 = v32;
          goto LABEL_76;
        }
        v28 = 1;
        *(_DWORD *)(v18 + 2808) = 1;
      }
      else
      {
        v28 = 2;
      }
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)WPP_f577d8521c9b39ef05153804ed8add08_Traceguids,
          (unsigned int)Src,
          v28);
      }
      if ( (int)CRuntimePlugin::AskModuleToClaimCrash(v18, Src, v16[2], v48, v47, v46, v45) < 0 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        {
          goto LABEL_75;
        }
        v30 = 32;
LABEL_67:
        WPP_SF_S(*((_QWORD *)v29 + 2), v30, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids, Src);
        goto LABEL_75;
      }
      if ( *(_DWORD *)(v18 + 2808) )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        {
          goto LABEL_75;
        }
        v30 = 31;
        goto LABEL_67;
      }
      v13 = 1;
      v32 = 1;
      v40 = 1;
      *v49 = v16[2];
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids, Src);
      }
LABEL_76:
      operator delete(v16, (const struct std::nothrow_t *)v19);
      v12 = v33;
      v6 = v38;
    }
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v21 = 27;
      goto LABEL_40;
    }
    goto LABEL_75;
  }
  if ( HeaderFromProcess != -2147023728 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
  }
  return (unsigned int)-2147023728;
}

```

## disassembly

```asm
0x14004f02c  push    rbx
0x14004f02e  push    rsi
0x14004f02f  push    rdi
0x14004f030  push    r12
0x14004f032  push    r15
0x14004f034  mov     eax, 13E0h
0x14004f039  call    _alloca_probe
0x14004f03e  sub     rsp, rax
0x14004f041  mov     rax, cs:__security_cookie
0x14004f048  xor     rax, rsp
0x14004f04b  mov     [rsp+1408h+var_38], rax
0x14004f053  mov     [rsp+1408h+var_1368], r9
0x14004f05b  mov     [rsp+1408h+var_1360], r8
0x14004f063  mov     [rsp+1408h+var_1358], rdx
0x14004f06b  mov     r12, rcx
0x14004f06e  mov     [rsp+1408h+var_13A0], rcx
0x14004f073  mov     rax, [rsp+1408h+arg_20]
0x14004f07b  mov     [rsp+1408h+var_1370], rax
0x14004f083  mov     rax, [rsp+1408h+arg_28]
0x14004f08b  mov     [rsp+1408h+var_1350], rax
0x14004f093  xor     edi, edi
0x14004f095  mov     [rsp+1408h+var_1390], rdi
0x14004f09a  mov     r15d, edi
0x14004f09d  mov     rbx, [rcx+2F8h]
0x14004f0a4  mov     esi, 968h
0x14004f0a9  mov     r8d, esi; Size
0x14004f0ac  xor     edx, edx; Val
0x14004f0ae  lea     rcx, [rsp+1408h+var_1338]; void *
0x14004f0b6  call    memset_0
0x14004f0bb  test    rbx, rbx
0x14004f0be  jz      short loc_14004F11B
0x14004f0c0  mov     r8d, esi; Size
0x14004f0c3  xor     edx, edx; Val
0x14004f0c5  lea     rcx, [rsp+1408h+Src]; void *
0x14004f0cd  call    memset_0
0x14004f0d2  lea     rcx, [rsp+1408h+var_1338]; void *
0x14004f0da  lea     rdx, [rsp+1408h+Src]; Src
0x14004f0e2  mov     r8d, esi; Size
0x14004f0e5  call    memcpy_0
0x14004f0ea  lea     rdx, [rsp+1408h+var_1338]; lpBuffer
0x14004f0f2  mov     rcx, rbx; hProcess
0x14004f0f5  call    WerpGetHeaderFromProcess
0x14004f0fa  mov     ebx, eax
0x14004f0fc  test    eax, eax
0x14004f0fe  js      short loc_14004F14A
0x14004f100  mov     rcx, [rsp+1408h+lpBaseAddress]
0x14004f108  test    rcx, rcx
0x14004f10b  jnz     short loc_14004F114
0x14004f10d  mov     ebx, 80070490h
0x14004f112  jmp     short loc_14004F14A
0x14004f114  mov     r15, rcx
0x14004f117  mov     ebx, edi
0x14004f119  jmp     short loc_14004F14D
0x14004f11b  call    GetCurrentProcessId_0
0x14004f120  mov     r9d, eax
0x14004f123  mov     dword ptr [rsp+1408h+lpNumberOfBytesRead], 15ACh
0x14004f12b  lea     r8, aWerCrashapiUUE_3; "WER/CrashAPI/%u:%u: ERROR Invalid args "...
0x14004f132  xor     edx, edx; Level
0x14004f134  mov     ecx, 96h; ComponentId
0x14004f139  call    cs:__imp_DbgPrintEx
0x14004f140  nop     dword ptr [rax+rax+00h]
0x14004f145  mov     ebx, 80070057h
0x14004f14a  mov     rcx, rdi
0x14004f14d  mov     edx, 80000000h
0x14004f152  lea     eax, [rbx+rdx]
0x14004f155  test    edx, eax
0x14004f157  jnz     short loc_14004F19F
0x14004f159  cmp     ebx, 80070490h
0x14004f15f  jz      short loc_14004F19F
0x14004f161  lea     rsi, WPP_GLOBAL_Control
0x14004f168  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f16f  cmp     rcx, rsi
0x14004f172  jz      loc_14004F719
0x14004f178  test    byte ptr [rcx+1Ch], 1
0x14004f17c  jz      loc_14004F719
0x14004f182  mov     edx, 15h
0x14004f187  mov     r9d, ebx
0x14004f18a  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x14004f191  mov     rcx, [rcx+10h]
0x14004f195  call    WPP_SF_d
0x14004f19a  jmp     loc_14004F719
0x14004f19f  test    rcx, rcx
0x14004f1a2  jnz     short loc_14004F1E9
0x14004f1a4  cmp     ebx, 80070490h
0x14004f1aa  jz      short loc_14004F1B1
0x14004f1ac  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14004f1b1  lea     rsi, WPP_GLOBAL_Control
0x14004f1b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f1bf  cmp     rcx, rsi
0x14004f1c2  jz      short loc_14004F1DF
0x14004f1c4  test    byte ptr [rcx+1Ch], 4
0x14004f1c8  jz      short loc_14004F1DF
0x14004f1ca  mov     edx, 16h
0x14004f1cf  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x14004f1d6  mov     rcx, [rcx+10h]
0x14004f1da  call    WPP_SF_
0x14004f1df  mov     ebx, 80070490h
0x14004f1e4  jmp     loc_14004F719
0x14004f1e9  mov     edx, edi
0x14004f1eb  mov     [rsp+1408h+var_13C4], edx
0x14004f1ef  mov     ebx, edi
0x14004f1f1  mov     [rsp+1408h+var_13C8], ebx
0x14004f1f5  lea     rsi, WPP_GLOBAL_Control
0x14004f1fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f203  lea     rdi, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x14004f20a  cmp     rcx, rsi
0x14004f20d  jz      short loc_14004F22B
0x14004f20f  test    byte ptr [rcx+1Ch], 8
0x14004f213  jz      short loc_14004F22B
0x14004f215  mov     edx, 17h
0x14004f21a  mov     r9, r15
0x14004f21d  mov     r8, rdi
0x14004f220  mov     rcx, [rcx+10h]
0x14004f224  call    WPP_SF_q
0x14004f229  mov     edx, ebx
0x14004f22b  xor     ecx, ecx
0x14004f22d  test    ebx, ebx
0x14004f22f  jnz     loc_14004F31C
0x14004f235  test    r15, r15
0x14004f238  jz      loc_14004F31C
0x14004f23e  mov     eax, edx
0x14004f240  inc     edx
0x14004f242  mov     [rsp+1408h+var_13C4], edx
0x14004f246  mov     [rsp+1408h+var_1398], edx
0x14004f24a  cmp     eax, 10h
0x14004f24d  jnb     loc_14004F31C
0x14004f253  xorps   xmm0, xmm0
0x14004f256  xor     eax, eax
0x14004f258  movups  [rsp+1408h+Buffer], xmm0
0x14004f260  mov     [rsp+1408h+var_9B8], rax
0x14004f268  mov     [rsp+1408h+var_13B8], ecx
0x14004f26c  mov     [rsp+1408h+NumberOfBytesRead], rcx
0x14004f271  lea     rax, [rsp+1408h+NumberOfBytesRead]
0x14004f276  mov     [rsp+1408h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x14004f27b  lea     r9d, [rcx+18h]; nSize
0x14004f27f  lea     r8, [rsp+1408h+Buffer]; lpBuffer
0x14004f287  mov     rdx, r15; lpBaseAddress
0x14004f28a  mov     rcx, [r12+2F8h]; hProcess
0x14004f292  call    cs:__imp_ReadProcessMemory
0x14004f299  nop     dword ptr [rax+rax+00h]
0x14004f29e  xor     ecx, ecx
0x14004f2a0  test    eax, eax
0x14004f2a2  jz      loc_14004F6AA
0x14004f2a8  cmp     [rsp+1408h+NumberOfBytesRead], 18h
0x14004f2ae  jnz     loc_14004F6AA
0x14004f2b4  mov     r9d, dword ptr [rsp+1408h+Buffer+8]
0x14004f2bc  mov     [rsp+1408h+var_13B8], r9d
0x14004f2c1  lea     eax, [r9-18h]
0x14004f2c5  cmp     eax, 208h
0x14004f2ca  ja      loc_14004F67A
0x14004f2d0  mov     [rsp+1408h+NumberOfBytesRead], rcx
0x14004f2d5  mov     ebx, r9d
0x14004f2d8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14004f2df  mov     ecx, r9d; unsigned __int64
0x14004f2e2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14004f2e7  mov     r12, rax
0x14004f2ea  mov     [rsp+1408h+var_1340], rax
0x14004f2f2  test    rax, rax
0x14004f2f5  jnz     short loc_14004F32D
0x14004f2f7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f2fe  cmp     rcx, rsi
0x14004f301  jz      short loc_14004F318
0x14004f303  test    byte ptr [rcx+1Ch], 1
0x14004f307  jz      short loc_14004F318
0x14004f309  lea     edx, [rax+19h]
0x14004f30c  mov     r8, rdi
0x14004f30f  mov     rcx, [rcx+10h]
0x14004f313  call    WPP_SF_
0x14004f318  mov     ebx, [rsp+1408h+var_13C8]
0x14004f31c  neg     ebx
0x14004f31e  sbb     ebx, ebx
0x14004f320  not     ebx
0x14004f322  and     ebx, 80004005h
0x14004f328  jmp     loc_14004F719
0x14004f32d  lea     rax, [rsp+1408h+NumberOfBytesRead]
0x14004f332  mov     [rsp+1408h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x14004f337  mov     r9, rbx; nSize
0x14004f33a  mov     r8, r12; lpBuffer
0x14004f33d  mov     rdx, r15; lpBaseAddress
0x14004f340  mov     rbx, [rsp+1408h+var_13A0]
0x14004f345  mov     rcx, [rbx+2F8h]; hProcess
0x14004f34c  call    cs:__imp_ReadProcessMemory
0x14004f353  nop     dword ptr [rax+rax+00h]
0x14004f358  xor     r10d, r10d
0x14004f35b  test    eax, eax
0x14004f35d  jz      loc_14004F655
0x14004f363  mov     r15, [r12]
0x14004f367  mov     [rsp+1408h+var_1348], r15
0x14004f36f  lea     rax, [r15+18h]
0x14004f373  test    rax, rax
0x14004f376  jnz     short loc_14004F3A6
0x14004f378  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f37f  cmp     rcx, rsi
0x14004f382  jz      loc_14004F660
0x14004f388  test    byte ptr [rcx+1Ch], 1
0x14004f38c  jz      loc_14004F660
0x14004f392  lea     edx, [rax+1Ah]
0x14004f395  mov     r8, rdi
0x14004f398  mov     rcx, [rcx+10h]
0x14004f39c  call    WPP_SF_
0x14004f3a1  jmp     loc_14004F660
0x14004f3a6  mov     [rsp+1408h+Src], r10w
0x14004f3af  mov     r8d, 7FFFFFFEh
0x14004f3b5  mov     [rsp+1408h+var_1378], r8
0x14004f3bd  lea     r9, [r12+18h]
0x14004f3c2  mov     [rsp+1408h+var_1388], r9
0x14004f3ca  mov     edx, 104h
0x14004f3cf  mov     [rsp+1408h+var_1380], rdx
0x14004f3d7  lea     rcx, [rsp+1408h+Src]
0x14004f3df  mov     [rsp+1408h+var_13B0], rcx
0x14004f3e4  mov     r11d, r10d
0x14004f3e7  mov     rax, r10
0x14004f3ea  mov     [rsp+1408h+var_13A8], rax
0x14004f3ef  test    rdx, rdx
0x14004f3f2  jz      short loc_14004F449
0x14004f3f4  test    r8, r8
0x14004f3f7  jz      short loc_14004F444
0x14004f3f9  movzx   r10d, word ptr [r9]
0x14004f3fd  cmp     r10w, word ptr [rsp+1408h+var_1390]
0x14004f403  jz      short loc_14004F441
0x14004f405  add     r9, 2
0x14004f409  mov     [rsp+1408h+var_1388], r9
0x14004f411  mov     [rcx], r10w
0x14004f415  add     rcx, 2
0x14004f419  mov     [rsp+1408h+var_13B0], rcx
0x14004f41e  dec     rdx
0x14004f421  mov     [rsp+1408h+var_1380], rdx
0x14004f429  dec     r8
0x14004f42c  mov     [rsp+1408h+var_1378], r8
0x14004f434  inc     rax
0x14004f437  mov     [rsp+1408h+var_13A8], rax
0x14004f43c  xor     r10d, r10d
0x14004f43f  jmp     short loc_14004F3EF
0x14004f441  xor     r10d, r10d
0x14004f444  test    rdx, rdx
0x14004f447  jnz     short loc_14004F460
0x14004f449  sub     rcx, 2
0x14004f44d  mov     [rsp+1408h+var_13B0], rcx
0x14004f452  dec     rax
0x14004f455  mov     [rsp+1408h+var_13A8], rax
0x14004f45a  mov     r11d, 8007007Ah
0x14004f460  mov     eax, r10d
0x14004f463  mov     [rcx], ax
0x14004f466  test    r11d, r11d
0x14004f469  jns     short loc_14004F48F
0x14004f46b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f472  cmp     rcx, rsi
0x14004f475  jz      loc_14004F660
0x14004f47b  test    byte ptr [rcx+1Ch], 1
0x14004f47f  jz      loc_14004F660
0x14004f485  mov     edx, 1Bh
0x14004f48a  jmp     loc_14004F395
0x14004f48f  mov     [rsp+1408h+pcbData], r10; pcbData
0x14004f494  mov     [rsp+1408h+pvData], r10; pvData
0x14004f499  mov     [rsp+1408h+lpNumberOfBytesRead], r10; pdwType
0x14004f49e  mov     r9d, 10h; dwFlags
0x14004f4a4  lea     r8, [rsp+1408h+Src]; lpValue
0x14004f4ac  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\Windows E"...
0x14004f4b3  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14004f4ba  call    cs:__imp_RegGetValueW
0x14004f4c1  nop     dword ptr [rax+rax+00h]
0x14004f4c6  xor     r10d, r10d
0x14004f4c9  test    eax, eax
0x14004f4cb  jnz     short loc_14004F4D3
0x14004f4cd  lea     eax, [r10+2]
0x14004f4d1  jmp     short loc_14004F51D
0x14004f4d3  mov     [rsp+1408h+pcbData], r10; pcbData
0x14004f4d8  mov     [rsp+1408h+pvData], r10; pvData
0x14004f4dd  mov     [rsp+1408h+lpNumberOfBytesRead], r10; pdwType
0x14004f4e2  mov     r9d, 10h; dwFlags
0x14004f4e8  lea     r8, [rsp+1408h+Src]; lpValue
0x14004f4f0  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\Windows E"...
0x14004f4f7  mov     rcx, 0FFFFFFFF80000001h; hkey
0x14004f4fe  call    cs:__imp_RegGetValueW
0x14004f505  nop     dword ptr [rax+rax+00h]
0x14004f50a  test    eax, eax
0x14004f50c  jnz     loc_14004F639
0x14004f512  mov     eax, 1
0x14004f517  mov     [rbx+0AF8h], eax
0x14004f51d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f524  cmp     rcx, rsi
0x14004f527  jz      short loc_14004F54C
0x14004f529  test    byte ptr [rcx+1Ch], 8
0x14004f52d  jz      short loc_14004F54C
0x14004f52f  mov     edx, 1Dh
0x14004f534  mov     dword ptr [rsp+1408h+lpNumberOfBytesRead], eax
0x14004f538  lea     r9, [rsp+1408h+Src]
0x14004f540  mov     r8, rdi
0x14004f543  mov     rcx, [rcx+10h]
0x14004f547  call    WPP_SF_Sd
0x14004f54c  mov     rax, [rsp+1408h+var_1370]
0x14004f554  mov     [rsp+1408h+pcbData], rax
0x14004f559  mov     rax, [rsp+1408h+var_1368]
0x14004f561  mov     [rsp+1408h+pvData], rax
0x14004f566  mov     rax, [rsp+1408h+var_1360]
0x14004f56e  mov     [rsp+1408h+lpNumberOfBytesRead], rax
0x14004f573  mov     r9, [rsp+1408h+var_1358]
0x14004f57b  mov     r8, [r12+10h]
0x14004f580  lea     rdx, [rsp+1408h+Src]
0x14004f588  mov     rcx, rbx
  ... truncated ...
```
