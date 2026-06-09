# CSqmManager::ThreadProc(void)

- ea: `0x140031790`
- end: `0x140031e90`
- name: `?ThreadProc@CSqmManager@@UEAAJXZ`
- size: `1792`
- prototype: `__int64 __fastcall(CSqmManager *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140001008`
- `0x140031790`
- `0x140031e98`
- `0x1400329a8`
- `0x140032e00`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cb9e`
- `0x14007cbd0`
- `0x14007e010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140031977`
- `KERNEL32!WaitForSingleObject` at `0x140031cb5`
- `KERNEL32!WaitForSingleObject` at `0x140031977`
- `KERNEL32!WaitForSingleObject` at `0x140031cb5`
- `KERNEL32!GetLastError` at `0x140031cd8`
- `KERNEL32!GetLastError` at `0x140031cd8`
- `KERNEL32!IsDebuggerPresent` at `0x14003181c`
- `KERNEL32!IsDebuggerPresent` at `0x1400318d8`
- `KERNEL32!IsDebuggerPresent` at `0x140031d32`
- `KERNEL32!IsDebuggerPresent` at `0x140031d9f`
- `KERNEL32!IsDebuggerPresent` at `0x140031df7`
- `KERNEL32!IsDebuggerPresent` at `0x14003181c`
- `KERNEL32!IsDebuggerPresent` at `0x1400318d8`
- `KERNEL32!IsDebuggerPresent` at `0x140031d32`
- `KERNEL32!IsDebuggerPresent` at `0x140031d9f`
- `KERNEL32!IsDebuggerPresent` at `0x140031df7`
- `KERNEL32!GetTickCount` at `0x140031876`
- `KERNEL32!GetTickCount` at `0x140031876`
- `msvcrt!rand_s` at `0x140031889`
- `msvcrt!rand_s` at `0x140031c6f`
- `msvcrt!rand_s` at `0x140031889`
- `msvcrt!rand_s` at `0x140031c6f`
- `msvcrt!srand` at `0x14003187e`
- `msvcrt!srand` at `0x14003187e`
- `ole32!CoUninitialize` at `0x140031e65`
- `ole32!CoUninitialize` at `0x140031e65`
- `ole32!CoInitializeEx` at `0x1400317d1`
- `ole32!CoInitializeEx` at `0x1400317d1`
- `ole32!CoCreateInstance` at `0x1400319df`
- `ole32!CoCreateInstance` at `0x1400319df`

## string_xrefs

- `0x1400317ec`: `CSqmManager::ThreadProc`
- `0x1400318a4`: `CSqmManager::ThreadProc`
- `0x140031cf3`: `CSqmManager::ThreadProc`
- `0x140031d6a`: `CSqmManager::ThreadProc`
- `0x140031dca`: `CSqmManager::ThreadProc`
- `0x140031943`: `CSqmManager::ThreadProc - waiting %d ms to collect telemetry data.\n`
- `0x140031c81`: `CSqmManager::ThreadProc - waiting %d ms to collect telemetry data.\n`
- `0x1400319a7`: `CSqmManager::ThreadProc - collecting telemetry now.\n`

## pseudocode

```c
__int64 __fastcall CSqmManager::ThreadProc(HANDLE *this)
{
  HRESULT v2; // eax
  signed int v3; // edi
  int v4; // r13d
  __int64 v5; // r9
  DWORD TickCount; // eax
  __int64 v7; // r9
  __int64 v8; // r8
  int v9; // esi
  __int64 v10; // rbx
  DWORD v11; // eax
  HRESULT Instance; // eax
  __int64 v13; // rbx
  signed int LastError; // eax
  int v16; // [rsp+40h] [rbp-C0h] BYREF
  struct IWmsCore *ppv; // [rsp+48h] [rbp-B8h] BYREF
  int v18; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+54h] [rbp-ACh] BYREF
  int v20; // [rsp+58h] [rbp-A8h] BYREF
  int v21; // [rsp+5Ch] [rbp-A4h] BYREF
  int v22; // [rsp+60h] [rbp-A0h] BYREF
  int v23; // [rsp+64h] [rbp-9Ch] BYREF
  int v24; // [rsp+68h] [rbp-98h] BYREF
  int v25; // [rsp+6Ch] [rbp-94h] BYREF
  int v26; // [rsp+70h] [rbp-90h] BYREF
  int v27; // [rsp+74h] [rbp-8Ch] BYREF
  int v28; // [rsp+78h] [rbp-88h] BYREF
  int v29; // [rsp+7Ch] [rbp-84h] BYREF
  int v30; // [rsp+80h] [rbp-80h] BYREF
  int v31; // [rsp+84h] [rbp-7Ch] BYREF
  int v32; // [rsp+88h] [rbp-78h] BYREF
  int v33; // [rsp+8Ch] [rbp-74h] BYREF
  int v34; // [rsp+90h] [rbp-70h] BYREF
  int v35; // [rsp+94h] [rbp-6Ch] BYREF
  int v36; // [rsp+98h] [rbp-68h] BYREF
  int v37; // [rsp+9Ch] [rbp-64h] BYREF
  _DWORD v38[24]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v39[32]; // [rsp+100h] [rbp+0h] BYREF
  int *v40; // [rsp+120h] [rbp+20h]
  __int64 v41; // [rsp+128h] [rbp+28h]
  int *v42; // [rsp+130h] [rbp+30h]
  __int64 v43; // [rsp+138h] [rbp+38h]
  int *v44; // [rsp+140h] [rbp+40h]
  __int64 v45; // [rsp+148h] [rbp+48h]
  int *v46; // [rsp+150h] [rbp+50h]
  __int64 v47; // [rsp+158h] [rbp+58h]
  int *v48; // [rsp+160h] [rbp+60h]
  __int64 v49; // [rsp+168h] [rbp+68h]
  int *v50; // [rsp+170h] [rbp+70h]
  __int64 v51; // [rsp+178h] [rbp+78h]
  int *v52; // [rsp+180h] [rbp+80h]
  __int64 v53; // [rsp+188h] [rbp+88h]
  int *v54; // [rsp+190h] [rbp+90h]
  __int64 v55; // [rsp+198h] [rbp+98h]
  int *v56; // [rsp+1A0h] [rbp+A0h]
  __int64 v57; // [rsp+1A8h] [rbp+A8h]
  int *v58; // [rsp+1B0h] [rbp+B0h]
  __int64 v59; // [rsp+1B8h] [rbp+B8h]
  int *v60; // [rsp+1C0h] [rbp+C0h]
  __int64 v61; // [rsp+1C8h] [rbp+C8h]
  int *v62; // [rsp+1D0h] [rbp+D0h]
  __int64 v63; // [rsp+1D8h] [rbp+D8h]
  int *v64; // [rsp+1E0h] [rbp+E0h]
  __int64 v65; // [rsp+1E8h] [rbp+E8h]
  int *v66; // [rsp+1F0h] [rbp+F0h]
  __int64 v67; // [rsp+1F8h] [rbp+F8h]
  int *v68; // [rsp+200h] [rbp+100h]
  __int64 v69; // [rsp+208h] [rbp+108h]
  int *v70; // [rsp+210h] [rbp+110h]
  __int64 v71; // [rsp+218h] [rbp+118h]
  int *v72; // [rsp+220h] [rbp+120h]
  __int64 v73; // [rsp+228h] [rbp+128h]
  int *v74; // [rsp+230h] [rbp+130h]
  __int64 v75; // [rsp+238h] [rbp+138h]
  int *v76; // [rsp+240h] [rbp+140h]
  __int64 v77; // [rsp+248h] [rbp+148h]
  int *v78; // [rsp+250h] [rbp+150h]
  __int64 v79; // [rsp+258h] [rbp+158h]

  v16 = 0;
  ppv = 0;
  v2 = CoInitializeEx(0, 0);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v4 = 1;
    TickCount = GetTickCount();
    srand(TickCount);
    if ( (unsigned int)rand_s(&v16) )
    {
      v3 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\sqmmanager.cpp",
        0x54u,
        L"CSqmManager::ThreadProc",
        L"CBRA",
        L"err == 0",
        -2147467259);
      if ( IsDebuggerPresent() )
      {
        v7 = 84;
LABEL_9:
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\sqmmanager.cpp",
          v7,
          L"CSqmManager::ThreadProc",
          L"CBRA",
          L"err == 0",
          -2147467259);
      }
      else
      {
        v8 = 84;
LABEL_11:
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\sqmmanager.cpp",
          v8,
          L"CSqmManager::ThreadProc",
          L"CBRA",
          L"err == 0",
          -2147467259);
      }
    }
    else
    {
      v9 = 1;
      v10 = (unsigned int)(int)((double)v16 * 7200000.0 / 4294967295.0);
      DEBUGMSG(L"CSqmManager::ThreadProc - waiting %d ms to collect telemetry data.\n", v10);
      v11 = WaitForSingleObject(this[3], v10);
      if ( v11 == 258 )
      {
        while ( 1 )
        {
          memset_0(v38, 0, 0x5Cu);
          DEBUGMSG(L"CSqmManager::ThreadProc - collecting telemetry now.\n");
          memset_0(v38, 0, 0x5Cu);
          Instance = CoCreateInstance(
                       &CLSID_EventNotificationService,
                       0,
                       4u,
                       &GUID_d5bbf19e_4292_4ad2_aff7_699fd76111e8,
                       (LPVOID *)&ppv);
          v3 = Instance;
          if ( Instance < 0 )
            break;
          if ( v9 )
          {
            CSqmManager::s_CollectStaticTelemetry(ppv);
            v9 = 0;
          }
          CSqmManager::s_GetSessionTelemetry(ppv, (struct CSqmManager::SWmsSessionTelemetryData *)v38);
          CSqmManager::s_GetStationTelemetry(ppv, (struct CSqmManager::SWmsSessionTelemetryData *)v38);
          if ( ppv )
          {
            (*(void (__fastcall **)(struct IWmsCore *))(*(_QWORD *)ppv + 16LL))(ppv);
            ppv = 0;
          }
          if ( (unsigned int)dword_1400EE280 > 5
            && (qword_1400EE290 & 0x400000000000LL) != 0
            && (qword_1400EE298 & 0x400000000000LL) == qword_1400EE298 )
          {
            v18 = v38[13];
            v19 = v38[12];
            v20 = v38[11];
            v21 = v38[10];
            v22 = v38[9];
            v23 = v38[8];
            v24 = v38[6];
            v25 = v38[5];
            v26 = v38[4];
            v27 = v38[3];
            v28 = v38[0];
            v29 = v38[21];
            v30 = v38[20];
            v31 = v38[19];
            v32 = v38[16];
            v33 = v38[15];
            v34 = v38[14];
            v35 = v38[17];
            v36 = v38[18];
            v37 = v38[22];
            v78 = &v18;
            v76 = &v19;
            v74 = &v20;
            v72 = &v21;
            v70 = &v22;
            v68 = &v23;
            v66 = &v24;
            v64 = &v25;
            v62 = &v26;
            v60 = &v27;
            v58 = &v28;
            v56 = &v29;
            v54 = &v30;
            v52 = &v31;
            v79 = 4;
            v77 = 4;
            v75 = 4;
            v73 = 4;
            v71 = 4;
            v69 = 4;
            v67 = 4;
            v65 = 4;
            v63 = 4;
            v61 = 4;
            v59 = 4;
            v57 = 4;
            v55 = 4;
            v53 = 4;
            v50 = &v32;
            v51 = 4;
            v48 = &v33;
            v49 = 4;
            v46 = &v34;
            v47 = 4;
            v44 = &v35;
            v45 = 4;
            v42 = &v36;
            v40 = &v37;
            v43 = 4;
            v41 = 4;
            tlgWriteTransfer_EventWriteTransfer(&dword_1400EE280, &dword_1400E6E8C, 0, 0, 22, v39);
          }
          if ( (unsigned int)rand_s(&v16) )
          {
            v3 = -2147467259;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\sqmmanager.cpp",
              0x8Cu,
              L"CSqmManager::ThreadProc",
              L"CBRA",
              L"err == 0",
              -2147467259);
            if ( IsDebuggerPresent() )
            {
              v7 = 140;
              goto LABEL_9;
            }
            v8 = 140;
            goto LABEL_11;
          }
          v3 = 0;
          v13 = (unsigned int)(int)((double)v16 * 7200000.0 / 4294967295.0);
          DEBUGMSG(L"CSqmManager::ThreadProc - waiting %d ms to collect telemetry data.\n", v13);
          v11 = WaitForSingleObject(this[3], v13);
          if ( v11 != 258 )
            goto LABEL_24;
        }
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\sqmmanager.cpp",
          0x62u,
          L"CSqmManager::ThreadProc",
          L"CHRA",
          L"hr",
          Instance);
        if ( IsDebuggerPresent() )
        {
          v5 = 98;
          goto LABEL_4;
        }
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\sqmmanager.cpp",
          98,
          L"CSqmManager::ThreadProc",
          L"CHRA",
          L"hr",
          v3);
      }
      else
      {
LABEL_24:
        if ( v11 )
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
          if ( v3 >= 0 )
            v3 = -2147467259;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\sqmmanager.cpp",
            0x93u,
            L"CSqmManager::ThreadProc",
            L"CBRAEx",
            L"dwWait == ((((NTSTATUS)0x00000000L) ) + 0 )",
            v3);
          if ( IsDebuggerPresent() )
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\sqmmanager.cpp",
              147,
              L"CSqmManager::ThreadProc",
              L"CBRAEx",
              L"dwWait == ((((NTSTATUS)0x00000000L) ) + 0 )",
              v3);
          else
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\sqmmanager.cpp",
              147,
              L"CSqmManager::ThreadProc",
              L"CBRAEx",
              L"dwWait == ((((NTSTATUS)0x00000000L) ) + 0 )",
              v3);
        }
      }
    }
  }
  else
  {
    v4 = 0;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\sqmmanager.cpp",
      0x4Bu,
      L"CSqmManager::ThreadProc",
      L"CHRA",
      L"hr",
      v2);
    if ( IsDebuggerPresent() )
    {
      v5 = 75;
LABEL_4:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\sqmmanager.cpp",
        v5,
        L"CSqmManager::ThreadProc",
        L"CHRA",
        L"hr",
        v3);
    }
    else
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\sqmmanager.cpp",
        75,
        L"CSqmManager::ThreadProc",
        L"CHRA",
        L"hr",
        v3);
    }
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(struct IWmsCore *))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v4 )
    CoUninitialize();
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140031790  push    rbp
0x140031792  push    rbx
0x140031793  push    rsi
0x140031794  push    rdi
0x140031795  push    r12
0x140031797  push    r13
0x140031799  push    r14
0x14003179b  push    r15
0x14003179d  lea     rbp, [rsp-178h]
0x1400317a5  sub     rsp, 278h
0x1400317ac  mov     rax, cs:__security_cookie
0x1400317b3  xor     rax, rsp
0x1400317b6  mov     [rbp+1B0h+var_50], rax
0x1400317bd  mov     r14, rcx
0x1400317c0  xor     r12d, r12d
0x1400317c3  xor     ecx, ecx; pvReserved
0x1400317c5  mov     [rsp+2B0h+var_270], r12d
0x1400317ca  xor     edx, edx; dwCoInit
0x1400317cc  mov     [rsp+2B0h+var_268], r12
0x1400317d1  call    cs:__imp_CoInitializeEx
0x1400317d7  mov     edi, eax
0x1400317d9  test    eax, eax
0x1400317db  jns     loc_140031870
0x1400317e1  mov     [rsp+2B0h+var_288], eax; int
0x1400317e5  lea     r15, aChra; "CHRA"
0x1400317ec  lea     rsi, aCsqmmanagerThr_0; "CSqmManager::ThreadProc"
0x1400317f3  mov     r9, r15; unsigned __int16 *
0x1400317f6  lea     rbx, aTermsrvWmsSrcD_30; "termsrv\\wms\\src\\devices\\wmssvc\\sqm"...
0x1400317fd  mov     r8, rsi; unsigned __int16 *
0x140031800  lea     r14, aHr; "hr"
0x140031807  mov     rcx, rbx; unsigned __int16 *
0x14003180a  lea     edx, [r12+4Bh]; unsigned int
0x14003180f  mov     [rsp+2B0h+ppv], r14; unsigned __int16 *
0x140031814  mov     r13d, r12d
0x140031817  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003181c  call    cs:__imp_IsDebuggerPresent
0x140031822  test    eax, eax
0x140031824  jz      short loc_140031857
0x140031826  lea     r9d, [r12+4Bh]
0x14003182b  mov     [rsp+2B0h+var_278], edi
0x14003182f  mov     [rsp+2B0h+var_280], r14
0x140031834  mov     qword ptr [rsp+2B0h+var_288], r15
0x140031839  mov     r8, rbx
0x14003183c  mov     [rsp+2B0h+ppv], rsi
0x140031841  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140031848  mov     ecx, 2; unsigned __int8
0x14003184d  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140031852  jmp     loc_140031E45
0x140031857  mov     dword ptr [rsp+2B0h+var_280], edi
0x14003185b  mov     r8d, 4Bh ; 'K'
0x140031861  mov     qword ptr [rsp+2B0h+var_288], r14
0x140031866  mov     [rsp+2B0h+ppv], r15
0x14003186b  jmp     loc_140031E33
0x140031870  mov     r13d, 1
0x140031876  call    cs:__imp_GetTickCount
0x14003187c  mov     ecx, eax; Seed
0x14003187e  call    cs:__imp_srand
0x140031884  lea     rcx, [rsp+2B0h+var_270]
0x140031889  call    cs:__imp_rand_s
0x14003188f  test    eax, eax
0x140031891  jz      loc_14003193F
0x140031897  mov     r14d, 80004005h
0x14003189d  lea     r12, aCbra; "CBRA"
0x1400318a4  lea     rsi, aCsqmmanagerThr_0; "CSqmManager::ThreadProc"
0x1400318ab  mov     [rsp+2B0h+var_288], r14d; int
0x1400318b0  lea     rbx, aTermsrvWmsSrcD_30; "termsrv\\wms\\src\\devices\\wmssvc\\sqm"...
0x1400318b7  mov     r9, r12; unsigned __int16 *
0x1400318ba  lea     r15, aErr0; "err == 0"
0x1400318c1  mov     r8, rsi; unsigned __int16 *
0x1400318c4  mov     rcx, rbx; unsigned __int16 *
0x1400318c7  mov     [rsp+2B0h+ppv], r15; unsigned __int16 *
0x1400318cc  lea     edx, [r13+53h]; unsigned int
0x1400318d0  mov     edi, r14d
0x1400318d3  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400318d8  call    cs:__imp_IsDebuggerPresent
0x1400318de  test    eax, eax
0x1400318e0  jz      short loc_140031910
0x1400318e2  lea     r9d, [r13+53h]
0x1400318e6  mov     [rsp+2B0h+var_278], r14d
0x1400318eb  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400318f2  mov     [rsp+2B0h+var_280], r15
0x1400318f7  mov     r8, rbx
0x1400318fa  mov     qword ptr [rsp+2B0h+var_288], r12
0x1400318ff  mov     ecx, 2; unsigned __int8
0x140031904  mov     [rsp+2B0h+ppv], rsi
0x140031909  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14003190e  jmp     short loc_140031937
0x140031910  mov     r8d, 54h ; 'T'
0x140031916  mov     dword ptr [rsp+2B0h+var_280], r14d
0x14003191b  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140031922  mov     qword ptr [rsp+2B0h+var_288], r15
0x140031927  mov     r9, rsi
0x14003192a  mov     rdx, rbx
0x14003192d  mov     [rsp+2B0h+ppv], r12
0x140031932  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140031937  xor     r12d, r12d
0x14003193a  jmp     loc_140031E45
0x14003193f  mov     eax, [rsp+2B0h+var_270]
0x140031943  lea     rcx, aCsqmmanagerThr; "CSqmManager::ThreadProc - waiting %d ms"...
0x14003194a  xorps   xmm0, xmm0
0x14003194d  mov     esi, r13d
0x140031950  cvtsi2sd xmm0, rax
0x140031955  mulsd   xmm0, cs:__real@415b774000000000
0x14003195d  divsd   xmm0, cs:__real@41efffffffe00000
0x140031965  cvttsd2si rbx, xmm0
0x14003196a  mov     edx, ebx
0x14003196c  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140031971  mov     rcx, [r14+18h]; hHandle
0x140031975  mov     edx, ebx; dwMilliseconds
0x140031977  call    cs:__imp_WaitForSingleObject
0x14003197d  cmp     eax, 102h
0x140031982  jnz     loc_140031CD0
0x140031988  mov     rbx, 400000000000h
0x140031992  mov     r15d, 4
0x140031998  xor     edx, edx; Val
0x14003199a  lea     rcx, [rbp+1B0h+var_210]; void *
0x14003199e  lea     r8d, [rdx+5Ch]; Size
0x1400319a2  call    memset_0
0x1400319a7  lea     rcx, aCsqmmanagerThr_1; "CSqmManager::ThreadProc - collecting te"...
0x1400319ae  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400319b3  xor     edx, edx; Val
0x1400319b5  lea     rcx, [rbp+1B0h+var_210]; void *
0x1400319b9  lea     r8d, [rdx+5Ch]; Size
0x1400319bd  call    memset_0
0x1400319c2  lea     rax, [rsp+2B0h+var_268]
0x1400319c7  mov     r8d, r15d; dwClsContext
0x1400319ca  lea     r9, _GUID_d5bbf19e_4292_4ad2_aff7_699fd76111e8; riid
0x1400319d1  mov     [rsp+2B0h+ppv], rax; ppv
0x1400319d6  xor     edx, edx; pUnkOuter
0x1400319d8  lea     rcx, CLSID_EventNotificationService; rclsid
0x1400319df  call    cs:__imp_CoCreateInstance
0x1400319e5  mov     edi, eax
0x1400319e7  test    eax, eax
0x1400319e9  js      loc_140031DBF
0x1400319ef  test    esi, esi
0x1400319f1  jz      short loc_140031A00
0x1400319f3  mov     rcx, [rsp+2B0h+var_268]; struct IWmsCore *
0x1400319f8  call    ?s_CollectStaticTelemetry@CSqmManager@@CAJPEAUIWmsCore@@@Z; CSqmManager::s_CollectStaticTelemetry(IWmsCore *)
0x1400319fd  mov     esi, r12d
0x140031a00  mov     rcx, [rsp+2B0h+var_268]; struct IWmsCore *
0x140031a05  lea     rdx, [rbp+1B0h+var_210]; struct CSqmManager::SWmsSessionTelemetryData *
0x140031a09  call    ?s_GetSessionTelemetry@CSqmManager@@CAJPEAUIWmsCore@@PEAUSWmsSessionTelemetryData@1@@Z; CSqmManager::s_GetSessionTelemetry(IWmsCore *,CSqmManager::SWmsSessionTelemetryData *)
0x140031a0e  mov     rcx, [rsp+2B0h+var_268]; struct IWmsCore *
0x140031a13  lea     rdx, [rbp+1B0h+var_210]; struct CSqmManager::SWmsSessionTelemetryData *
0x140031a17  call    ?s_GetStationTelemetry@CSqmManager@@CAJPEAUIWmsCore@@PEAUSWmsSessionTelemetryData@1@@Z; CSqmManager::s_GetStationTelemetry(IWmsCore *,CSqmManager::SWmsSessionTelemetryData *)
0x140031a1c  mov     rcx, [rsp+2B0h+var_268]
0x140031a21  test    rcx, rcx
0x140031a24  jz      short loc_140031A37
0x140031a26  mov     rax, [rcx]
0x140031a29  mov     rax, [rax+10h]
0x140031a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031a32  mov     [rsp+2B0h+var_268], r12
0x140031a37  mov     eax, cs:dword_1400EE280
0x140031a3d  cmp     eax, 5
0x140031a40  jbe     loc_140031C6A
0x140031a46  mov     rcx, cs:qword_1400EE298
0x140031a4d  mov     rax, cs:qword_1400EE290
0x140031a54  test    rbx, rax
0x140031a57  jz      loc_140031C6A
0x140031a5d  mov     rax, rcx
0x140031a60  and     rax, rbx
0x140031a63  cmp     rax, rcx
0x140031a66  jnz     loc_140031C6A
0x140031a6c  mov     eax, [rbp+1B0h+var_1DC]
0x140031a6f  mov     [rsp+2B0h+var_260], eax
0x140031a73  mov     eax, [rbp+1B0h+var_1E0]
0x140031a76  mov     [rsp+2B0h+var_25C], eax
0x140031a7a  mov     eax, [rbp+1B0h+var_1E4]
0x140031a7d  mov     [rsp+2B0h+var_258], eax
0x140031a81  mov     eax, [rbp+1B0h+var_1E8]
0x140031a84  mov     [rsp+2B0h+var_254], eax
0x140031a88  mov     eax, [rbp+1B0h+var_1EC]
0x140031a8b  mov     [rsp+2B0h+var_250], eax
0x140031a8f  mov     eax, [rbp+1B0h+var_1F0]
0x140031a92  mov     [rsp+2B0h+var_24C], eax
0x140031a96  mov     eax, [rbp+1B0h+var_1F8]
0x140031a99  mov     [rsp+2B0h+var_248], eax
0x140031a9d  mov     eax, [rbp+1B0h+var_1FC]
0x140031aa0  mov     [rsp+2B0h+var_244], eax
0x140031aa4  mov     eax, [rbp+1B0h+var_200]
0x140031aa7  mov     [rsp+2B0h+var_240], eax
0x140031aab  mov     eax, [rbp+1B0h+var_204]
0x140031aae  mov     [rsp+2B0h+var_23C], eax
0x140031ab2  mov     eax, [rbp+1B0h+var_210]
0x140031ab5  mov     [rsp+2B0h+var_238], eax
0x140031ab9  mov     eax, [rbp+1B0h+var_1BC]
0x140031abc  mov     [rsp+2B0h+var_234], eax
0x140031ac0  mov     eax, [rbp+1B0h+var_1C0]
0x140031ac3  mov     [rbp+1B0h+var_230], eax
0x140031ac6  mov     eax, [rbp+1B0h+var_1C4]
0x140031ac9  mov     [rbp+1B0h+var_22C], eax
0x140031acc  mov     eax, [rbp+1B0h+var_1D0]
0x140031acf  mov     [rbp+1B0h+var_228], eax
0x140031ad2  mov     eax, [rbp+1B0h+var_1D4]
0x140031ad5  mov     [rbp+1B0h+var_224], eax
0x140031ad8  mov     eax, [rbp+1B0h+var_1D8]
0x140031adb  mov     [rbp+1B0h+var_220], eax
0x140031ade  mov     eax, [rbp+1B0h+var_1CC]
0x140031ae1  mov     [rbp+1B0h+var_21C], eax
0x140031ae4  mov     eax, [rbp+1B0h+var_1C8]
0x140031ae7  mov     [rbp+1B0h+var_218], eax
0x140031aea  mov     eax, [rbp+1B0h+var_1B8]
0x140031aed  mov     [rbp+1B0h+var_214], eax
0x140031af0  lea     rax, [rsp+2B0h+var_260]
0x140031af5  mov     [rbp+1B0h+var_60], rax
0x140031afc  lea     rax, [rsp+2B0h+var_25C]
0x140031b01  mov     [rbp+1B0h+var_70], rax
0x140031b08  lea     rax, [rsp+2B0h+var_258]
0x140031b0d  mov     [rbp+1B0h+var_80], rax
0x140031b14  lea     rax, [rsp+2B0h+var_254]
0x140031b19  mov     [rbp+1B0h+var_90], rax
0x140031b20  lea     rax, [rsp+2B0h+var_250]
0x140031b25  mov     [rbp+1B0h+var_A0], rax
0x140031b2c  lea     rax, [rsp+2B0h+var_24C]
0x140031b31  mov     [rbp+1B0h+var_B0], rax
0x140031b38  lea     rax, [rsp+2B0h+var_248]
0x140031b3d  mov     [rbp+1B0h+var_C0], rax
0x140031b44  lea     rax, [rsp+2B0h+var_244]
0x140031b49  mov     [rbp+1B0h+var_D0], rax
0x140031b50  lea     rax, [rsp+2B0h+var_240]
0x140031b55  mov     [rbp+1B0h+var_E0], rax
0x140031b5c  lea     rax, [rsp+2B0h+var_23C]
0x140031b61  mov     [rbp+1B0h+var_F0], rax
0x140031b68  lea     rax, [rsp+2B0h+var_238]
0x140031b6d  mov     [rbp+1B0h+var_100], rax
0x140031b74  lea     rax, [rsp+2B0h+var_234]
0x140031b79  mov     [rbp+1B0h+var_110], rax
0x140031b80  lea     rax, [rbp+1B0h+var_230]
0x140031b84  mov     [rbp+1B0h+var_120], rax
0x140031b8b  lea     rax, [rbp+1B0h+var_22C]
0x140031b8f  mov     [rbp+1B0h+var_130], rax
0x140031b96  mov     [rbp+1B0h+var_58], r15
0x140031b9d  mov     [rbp+1B0h+var_68], r15
0x140031ba4  mov     [rbp+1B0h+var_78], r15
0x140031bab  mov     [rbp+1B0h+var_88], r15
0x140031bb2  mov     [rbp+1B0h+var_98], r15
0x140031bb9  mov     [rbp+1B0h+var_A8], r15
0x140031bc0  mov     [rbp+1B0h+var_B8], r15
0x140031bc7  mov     [rbp+1B0h+var_C8], r15
0x140031bce  mov     [rbp+1B0h+var_D8], r15
0x140031bd5  mov     [rbp+1B0h+var_E8], r15
0x140031bdc  mov     [rbp+1B0h+var_F8], r15
0x140031be3  mov     [rbp+1B0h+var_108], r15
0x140031bea  mov     [rbp+1B0h+var_118], r15
0x140031bf1  lea     rax, [rbp+1B0h+var_228]
0x140031bf5  mov     [rbp+1B0h+var_128], r15
0x140031bfc  mov     [rbp+1B0h+var_140], rax
0x140031c00  lea     rdx, dword_1400E6E8C
0x140031c07  lea     rax, [rbp+1B0h+var_224]
0x140031c0b  mov     [rbp+1B0h+var_138], r15
0x140031c0f  mov     [rbp+1B0h+var_150], rax
0x140031c13  lea     rcx, dword_1400EE280
0x140031c1a  lea     rax, [rbp+1B0h+var_220]
0x140031c1e  mov     [rbp+1B0h+var_148], r15
0x140031c22  mov     [rbp+1B0h+var_160], rax
0x140031c26  xor     r9d, r9d
0x140031c29  lea     rax, [rbp+1B0h+var_21C]
0x140031c2d  mov     [rbp+1B0h+var_158], r15
0x140031c31  mov     [rbp+1B0h+var_170], rax
0x140031c35  xor     r8d, r8d
0x140031c38  lea     rax, [rbp+1B0h+var_218]
0x140031c3c  mov     [rbp+1B0h+var_168], r15
0x140031c40  mov     [rbp+1B0h+var_180], rax
0x140031c44  lea     rax, [rbp+1B0h+var_214]
0x140031c48  mov     [rbp+1B0h+var_190], rax
0x140031c4c  lea     rax, [rbp+1B0h+var_1B0]
0x140031c50  mov     qword ptr [rsp+2B0h+var_288], rax
0x140031c55  mov     dword ptr [rsp+2B0h+ppv], 16h
0x140031c5d  mov     [rbp+1B0h+var_178], r15
0x140031c61  mov     [rbp+1B0h+var_188], r15
0x140031c65  call    _tlgWriteTransfer_EventWriteTransfer
0x140031c6a  lea     rcx, [rsp+2B0h+var_270]
0x140031c6f  call    cs:__imp_rand_s
0x140031c75  test    eax, eax
0x140031c77  jnz     loc_140031D5D
0x140031c7d  mov     eax, [rsp+2B0h+var_270]
0x140031c81  lea     rcx, aCsqmmanagerThr; "CSqmManager::ThreadProc - waiting %d ms"...
0x140031c88  xorps   xmm0, xmm0
0x140031c8b  mov     edi, r12d
0x140031c8e  cvtsi2sd xmm0, rax
0x140031c93  mulsd   xmm0, cs:__real@415b774000000000
0x140031c9b  divsd   xmm0, cs:__real@41efffffffe00000
0x140031ca3  cvttsd2si rbx, xmm0
0x140031ca8  mov     edx, ebx
0x140031caa  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140031caf  mov     rcx, [r14+18h]; hHandle
0x140031cb3  mov     edx, ebx; dwMilliseconds
0x140031cb5  call    cs:__imp_WaitForSingleObject
0x140031cbb  mov     rbx, 400000000000h
0x140031cc5  cmp     eax, 102h
0x140031cca  jz      loc_140031998
0x140031cd0  test    eax, eax
0x140031cd2  jz      loc_140031E45
0x140031cd8  call    cs:__imp_GetLastError
0x140031cde  mov     edi, eax
0x140031ce0  test    eax, eax
0x140031ce2  jle     short loc_140031CED
0x140031ce4  movzx   edi, ax
0x140031ce7  or      edi, 80070000h
0x140031ced  mov     r14d, 80004005h
  ... truncated ...
```
