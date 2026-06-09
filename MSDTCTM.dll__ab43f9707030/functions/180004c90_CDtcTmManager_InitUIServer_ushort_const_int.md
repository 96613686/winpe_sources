# CDtcTmManager::InitUIServer(ushort const *,int)

- ea: `0x180004c90`
- end: `0x180005217`
- name: `?InitUIServer@CDtcTmManager@@QEAAJPEBGH@Z`
- size: `1415`
- prototype: `__int64 __fastcall(CDtcTmManager *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007668`

## callees

- `0x180004c90`
- `0x1800063b0`
- `0x18000a420`
- `0x18000edd0`
- `0x1800140d4`
- `0x180015230`
- `0x18001a210`
- `0x180022068`
- `0x1800223d0`
- `0x1800240b0`
- `0x1800240f0`
- `0x1800824f0`
- `0x180082584`
- `0x1800856d4`
- `0x1800b83e2`
- `0x1800bd010`

## import_xrefs

- `ole32!ComPs_NdrDllGetClassObject` at `0x180004e69`
- `ole32!ComPs_NdrDllGetClassObject` at `0x180004eac`
- `ole32!ComPs_NdrDllGetClassObject` at `0x180004f03`
- `ole32!ComPs_NdrDllGetClassObject` at `0x180004e69`
- `ole32!ComPs_NdrDllGetClassObject` at `0x180004eac`
- `ole32!ComPs_NdrDllGetClassObject` at `0x180004f03`

## string_xrefs

- `0x180004cdb`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180004dd7`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180004dbb`: `Created the instance !!`
- `0x180004cbb`: `Entering UI Server init, calling CoCreateInstance on UIS`
- `0x180004ff1`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x18000509e`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDtcTmManager::InitUIServer(CDtcTmManager *this, const unsigned __int16 *a2)
{
  CFTm *v4; // rax
  CFTm *v5; // rdi
  int v6; // ebx
  _QWORD *v7; // rdi
  __int64 result; // rax
  __int64 ****v9; // rcx
  __int64 **v10; // rcx
  unsigned int v11; // edx
  int v12; // ebx
  int v13; // eax
  unsigned int v14; // edx
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int v17; // ebx
  int v18; // ebx
  struct IDtcTrace *v19; // rdx
  struct IDtcTrace *v20; // rdx
  CDtcTmManager *v21; // rcx
  char *v22; // [rsp+20h] [rbp-78h]
  char *v23; // [rsp+20h] [rbp-78h]
  unsigned __int16 *v24; // [rsp+28h] [rbp-70h]
  int v25; // [rsp+30h] [rbp-68h]
  __int64 v26; // [rsp+50h] [rbp-48h] BYREF
  _QWORD v27[3]; // [rsp+58h] [rbp-40h] BYREF
  __int64 v28; // [rsp+B8h] [rbp+20h] BYREF

  v26 = 0;
  v27[0] = 0;
  TraceStringInline(
    3,
    6,
    L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
    2224,
    L"CDtcTmManager::InitUIServer",
    0,
    L"Entering UI Server init, calling CoCreateInstance on UIS");
  v28 = 0;
  if ( memcmp_0(&CLSID_DTCUIS, &CLSID_DTCTM, 0x10u) )
  {
    if ( (int)UisDllGetClassObject(&CLSID_DTCUIS, &IID_IClassFactory, &v28) < 0
      && (int)ComPs_NdrDllGetClassObject(
                &CLSID_DTCUIS,
                &IID_IClassFactory,
                &v28,
                &TcpCm_aProxyFileList,
                &TcpCm_CLSID_PSFactoryBuffer,
                TcpCm_gPFactory) < 0
      && (int)ComPs_NdrDllGetClassObject(
                &CLSID_DTCUIS,
                &IID_IClassFactory,
                &v28,
                &Sm_aProxyFileList,
                &Sm_CLSID_PSFactoryBuffer,
                Sm_gPFactory) < 0 )
    {
      v9 = TipConn_aProxyFileList[1];
      v10 = *v9 ? **v9 : 0LL;
      if ( (int)ComPs_NdrDllGetClassObject(
                  &CLSID_DTCUIS,
                  &IID_IClassFactory,
                  &v28,
                  &TipConn_aProxyFileList,
                  v10,
                  TipConn_gPFactory) < 0
        && (int)XaTmDllGetClassObject(&CLSID_DTCUIS, &IID_IClassFactory, &v28) < 0
        && (int)MapGwTxDllGetClassObject(&CLSID_DTCUIS, &IID_IClassFactory, &v28) < 0
        && (int)MapTxDllGetClassObject(&CLSID_DTCUIS, &IID_IClassFactory, &v28) < 0 )
      {
        v6 = -2147221231;
        goto LABEL_23;
      }
    }
LABEL_9:
    v7 = (_QWORD *)((char *)this + 24);
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, char *))(*(_QWORD *)v28 + 24LL))(
           v28,
           0,
           &IID_IUnknown,
           (char *)this + 24);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    goto LABEL_10;
  }
  v4 = (CFTm *)operator new(0x48u);
  v27[1] = v4;
  if ( v4 )
    v5 = CFTm::CFTm(v4);
  else
    v5 = 0;
  if ( !v5 )
  {
    v6 = -2147024882;
    v7 = (_QWORD *)((char *)this + 24);
    goto LABEL_10;
  }
  v6 = (**(__int64 (__fastcall ***)(CFTm *, GUID *, __int64 *))v5)(v5, &IID_IClassFactory, &v28);
  if ( v6 >= 0 )
    goto LABEL_9;
  operator delete(v5);
LABEL_23:
  v7 = (_QWORD *)((char *)this + 24);
LABEL_10:
  TraceStringInline(
    3,
    4,
    L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
    2228,
    L"CDtcTmManager::InitUIServer",
    0,
    L"Created the instance !!");
  if ( v6 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 71) + 152LL))(*((_QWORD *)this + 71), v27);
    if ( v12 >= 0 )
    {
      v15 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v7)(*v7, &IID_IDacUISInit, &v26);
      if ( v15 )
      {
        if ( z_pTrace )
        {
          v16 = (*(__int64 (__fastcall **)(struct IDtcTrace *, __int64, __int64, _QWORD, int, _DWORD, _QWORD, _QWORD))(*(_QWORD *)z_pTrace + 24LL))(
                  z_pTrace,
                  1,
                  1,
                  0,
                  -1073737705,
                  0,
                  0,
                  0);
          if ( v16 < 0 )
            TraceFile(v16, "failed in z_pTrace->Trace", "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp", 0x961u);
        }
        else
        {
          DtcWriteToEventLoggerW(1u, v14, 0xC0001017, 0, 0, v24, v25);
        }
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 16LL))(*v7);
        *v7 = 0;
        return v15;
      }
      else
      {
        LODWORD(v22) = (_DWORD)z_fService;
        v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, const unsigned __int16 *))(*(_QWORD *)v26 + 24LL))(
                v26,
                *((_QWORD *)this + 71),
                v27[0],
                a2);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        if ( v17 )
        {
          locprint(1u, 0xC0001015, 0, 0, v22);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 16LL))(*v7);
          *v7 = 0;
          return v17;
        }
        else
        {
          v18 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IDtcTrace **))*v7)(*v7, &IID_IDtcTrace, &z_pTrace);
          if ( v18 >= 0 )
          {
            locprint(0x100u, 0x40001004u, 0, 0, v22);
            locprint(0x100u, 0x4000D022u, 0, 0, v23);
            (*(void (__fastcall **)(struct IDtcTrace *))(*(_QWORD *)z_pTrace + 8LL))(z_pTrace);
            (*(void (__fastcall **)(struct IDtcTrace *))(*(_QWORD *)z_pTrace + 8LL))(z_pTrace);
            result = CDtcTmManager::ConnectCmToTracer(this, v19);
            if ( !(_DWORD)result )
              return CDtcTmManager::ConnectLogToTracer(v21, v20);
          }
          else
          {
            locprint(1u, 0xC0001017, 0, 0, v22);
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 16LL))(*v7);
            *v7 = 0;
            return (unsigned int)v18;
          }
        }
      }
    }
    else
    {
      if ( z_pTrace )
      {
        v13 = (*(__int64 (__fastcall **)(struct IDtcTrace *, __int64, __int64, _QWORD, int, _DWORD, _QWORD, _QWORD))(*(_QWORD *)z_pTrace + 24LL))(
                z_pTrace,
                1,
                1,
                0,
                -1073737704,
                0,
                0,
                0);
        if ( v13 < 0 )
          TraceFile(v13, "failed in z_pTrace->Trace", "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp", 0x961u);
      }
      else
      {
        DtcWriteToEventLoggerW(1u, v11, 0xC0001018, 0, 0, v24, v25);
      }
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 16LL))(*v7);
      *v7 = 0;
      return (unsigned int)v12;
    }
  }
  else
  {
    locprint(1u, 0xC0001016, 0, 0, v22);
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x180004c90  mov     r11, rsp
0x180004c93  mov     [r11+8], rbx
0x180004c97  mov     [r11+10h], rbp
0x180004c9b  push    rsi
0x180004c9c  push    rdi
0x180004c9d  push    r12
0x180004c9f  push    r14
0x180004ca1  push    r15
0x180004ca3  sub     rsp, 70h
0x180004ca7  mov     ebp, r8d
0x180004caa  mov     r14, rdx
0x180004cad  mov     rsi, rcx
0x180004cb0  xor     r15d, r15d
0x180004cb3  mov     [r11-48h], r15
0x180004cb7  mov     [r11-40h], r15
0x180004cbb  lea     rax, aEnteringUiServ; "Entering UI Server init, calling CoCrea"...
0x180004cc2  mov     [r11-68h], rax
0x180004cc6  mov     [r11-70h], r15
0x180004cca  lea     r12, aCdtctmmanagerI_4; "CDtcTmManager::InitUIServer"
0x180004cd1  mov     [r11-78h], r12
0x180004cd5  mov     r9d, 8B0h
0x180004cdb  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x180004ce2  mov     edx, 6
0x180004ce7  mov     ecx, 3
0x180004cec  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180004cf1  mov     [rsp+98h+arg_18], r15
0x180004cf9  mov     r8d, 10h; Size
0x180004cff  lea     rdx, CLSID_DTCTM; Buf2
0x180004d06  lea     rcx, CLSID_DTCUIS; Buf1
0x180004d0d  call    memcmp_0
0x180004d12  test    eax, eax
0x180004d14  jnz     loc_180004E11
0x180004d1a  mov     ecx, 48h ; 'H'; Size
0x180004d1f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004d24  mov     [rsp+98h+var_38], rax
0x180004d29  test    rax, rax
0x180004d2c  jz      short loc_180004D3B
0x180004d2e  mov     rcx, rax; this
0x180004d31  call    ??0CFTm@@QEAA@XZ; CFTm::CFTm(void)
0x180004d36  mov     rdi, rax
0x180004d39  jmp     short loc_180004D3E
0x180004d3b  mov     rdi, r15
0x180004d3e  test    rdi, rdi
0x180004d41  jnz     short loc_180004D4E
0x180004d43  mov     ebx, 8007000Eh
0x180004d48  lea     rdi, [rsi+18h]
0x180004d4c  jmp     short loc_180004DBB
0x180004d4e  mov     rax, [rdi]
0x180004d51  lea     r8, [rsp+98h+arg_18]
0x180004d59  lea     rdx, IID_IClassFactory
0x180004d60  mov     rcx, rdi
0x180004d63  mov     rax, [rax]
0x180004d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d6b  mov     ebx, eax
0x180004d6d  test    eax, eax
0x180004d6f  jns     short loc_180004D79
0x180004d71  mov     rcx, rdi; Block
0x180004d74  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004d79  test    ebx, ebx
0x180004d7b  js      loc_180004F7F
0x180004d81  lea     rdi, [rsi+18h]
0x180004d85  mov     rcx, [rsp+98h+arg_18]
0x180004d8d  mov     rax, [rcx]
0x180004d90  mov     r9, rdi
0x180004d93  lea     r8, IID_IUnknown
0x180004d9a  xor     edx, edx
0x180004d9c  mov     rax, [rax+18h]
0x180004da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004da5  mov     ebx, eax
0x180004da7  mov     rcx, [rsp+98h+arg_18]
0x180004daf  mov     rax, [rcx]
0x180004db2  mov     rax, [rax+10h]
0x180004db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dbb  lea     rax, aCreatedTheInst; "Created the instance !!"
0x180004dc2  mov     qword ptr [rsp+98h+var_68], rax; int
0x180004dc7  mov     [rsp+98h+var_70], r15; unsigned __int16 *
0x180004dcc  mov     [rsp+98h+var_78], r12; char *
0x180004dd1  mov     r9d, 8B4h
0x180004dd7  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x180004dde  mov     edx, 4
0x180004de3  mov     ecx, 3
0x180004de8  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180004ded  test    ebx, ebx
0x180004def  jns     loc_180004F88
0x180004df5  xor     r9d, r9d; void *
0x180004df8  xor     r8d, r8d; unsigned int
0x180004dfb  mov     edx, 0C0001016h; unsigned int
0x180004e00  mov     ecx, 1; unsigned int
0x180004e05  call    ?locprint@@YAXKKKPEAXPEAD@Z; locprint(ulong,ulong,ulong,void *,char *)
0x180004e0a  mov     eax, ebx
0x180004e0c  jmp     loc_1800051FE
0x180004e11  lea     r8, [rsp+98h+arg_18]
0x180004e19  lea     rdx, IID_IClassFactory
0x180004e20  lea     rcx, CLSID_DTCUIS
0x180004e27  call    UisDllGetClassObject
0x180004e2c  test    eax, eax
0x180004e2e  jns     loc_180004D81
0x180004e34  lea     rax, TcpCm_gPFactory
0x180004e3b  mov     [rsp+98h+var_70], rax
0x180004e40  lea     rax, TcpCm_CLSID_PSFactoryBuffer
0x180004e47  mov     [rsp+98h+var_78], rax
0x180004e4c  lea     r9, TcpCm_aProxyFileList
0x180004e53  lea     r8, [rsp+98h+arg_18]
0x180004e5b  lea     rdx, IID_IClassFactory
0x180004e62  lea     rcx, CLSID_DTCUIS
0x180004e69  call    cs:__imp_ComPs_NdrDllGetClassObject
0x180004e6f  test    eax, eax
0x180004e71  jns     loc_180004D81
0x180004e77  lea     rax, Sm_gPFactory
0x180004e7e  mov     [rsp+98h+var_70], rax
0x180004e83  lea     rax, Sm_CLSID_PSFactoryBuffer
0x180004e8a  mov     [rsp+98h+var_78], rax
0x180004e8f  lea     r9, Sm_aProxyFileList
0x180004e96  lea     r8, [rsp+98h+arg_18]
0x180004e9e  lea     rdx, IID_IClassFactory
0x180004ea5  lea     rcx, CLSID_DTCUIS
0x180004eac  call    cs:__imp_ComPs_NdrDllGetClassObject
0x180004eb2  test    eax, eax
0x180004eb4  jns     loc_180004D81
0x180004eba  mov     rax, cs:TipConn_aProxyFileList
0x180004ec1  mov     rcx, [rax+8]
0x180004ec5  mov     rax, [rcx]
0x180004ec8  test    rax, rax
0x180004ecb  jz      short loc_180004ED2
0x180004ecd  mov     rcx, [rax]
0x180004ed0  jmp     short loc_180004ED5
0x180004ed2  mov     rcx, r15
0x180004ed5  lea     rax, TipConn_gPFactory
0x180004edc  mov     [rsp+98h+var_70], rax
0x180004ee1  mov     [rsp+98h+var_78], rcx
0x180004ee6  lea     r9, TipConn_aProxyFileList
0x180004eed  lea     r8, [rsp+98h+arg_18]
0x180004ef5  lea     rdx, IID_IClassFactory
0x180004efc  lea     rcx, CLSID_DTCUIS
0x180004f03  call    cs:__imp_ComPs_NdrDllGetClassObject
0x180004f09  test    eax, eax
0x180004f0b  jns     loc_180004D81
0x180004f11  lea     r8, [rsp+98h+arg_18]
0x180004f19  lea     rdx, IID_IClassFactory
0x180004f20  lea     rcx, CLSID_DTCUIS
0x180004f27  call    XaTmDllGetClassObject
0x180004f2c  test    eax, eax
0x180004f2e  jns     loc_180004D81
0x180004f34  lea     r8, [rsp+98h+arg_18]
0x180004f3c  lea     rdx, IID_IClassFactory
0x180004f43  lea     rcx, CLSID_DTCUIS
0x180004f4a  call    MapGwTxDllGetClassObject
0x180004f4f  test    eax, eax
0x180004f51  jns     loc_180004D81
0x180004f57  lea     r8, [rsp+98h+arg_18]
0x180004f5f  lea     rdx, IID_IClassFactory
0x180004f66  lea     rcx, CLSID_DTCUIS
0x180004f6d  call    MapTxDllGetClassObject
0x180004f72  test    eax, eax
0x180004f74  jns     loc_180004D81
0x180004f7a  mov     ebx, 80040111h
0x180004f7f  lea     rdi, [rsi+18h]
0x180004f83  jmp     loc_180004DBB
0x180004f88  mov     rcx, [rsi+238h]
0x180004f8f  mov     rax, [rcx]
0x180004f92  lea     rdx, [rsp+98h+var_40]
0x180004f97  mov     rax, [rax+98h]
0x180004f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fa3  mov     ebx, eax
0x180004fa5  test    eax, eax
0x180004fa7  jns     loc_180005036
0x180004fad  mov     rcx, cs:?z_pTrace@@3PEAUIDtcTrace@@EA; IDtcTrace * z_pTrace
0x180004fb4  xor     r9d, r9d; unsigned int
0x180004fb7  test    rcx, rcx
0x180004fba  jz      short loc_180005008
0x180004fbc  mov     rdx, [rcx]
0x180004fbf  mov     rax, [rdx+18h]
0x180004fc3  mov     [rsp+98h+var_60], r15
0x180004fc8  mov     qword ptr [rsp+98h+var_68], r15
0x180004fcd  mov     dword ptr [rsp+98h+var_70], r15d
0x180004fd2  mov     dword ptr [rsp+98h+var_78], 0C0001018h
0x180004fda  mov     edx, 1
0x180004fdf  mov     r8d, edx
0x180004fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fe7  test    eax, eax
0x180004fe9  jns     short loc_18000501D
0x180004feb  mov     r9d, 961h; unsigned int
0x180004ff1  lea     r8, aComComplusDtcD_7; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x180004ff8  lea     rdx, aFailedInZPtrac; "failed in z_pTrace->Trace"
0x180004fff  mov     ecx, eax; int
0x180005001  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180005006  jmp     short loc_18000501D
0x180005008  mov     [rsp+98h+var_78], r15; void *
0x18000500d  mov     ecx, 1; unsigned int
0x180005012  mov     r8d, 0C0001018h; unsigned int
0x180005018  call    ?DtcWriteToEventLoggerW@@YAJKKKKPEAXPEAGH@Z; DtcWriteToEventLoggerW(ulong,ulong,ulong,ulong,void *,ushort *,int)
0x18000501d  mov     rcx, [rdi]
0x180005020  mov     rax, [rcx]
0x180005023  mov     rax, [rax+10h]
0x180005027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000502c  mov     [rdi], r15
0x18000502f  mov     eax, ebx
0x180005031  jmp     loc_1800051FE
0x180005036  mov     rcx, [rdi]
0x180005039  mov     rax, [rcx]
0x18000503c  lea     r8, [rsp+98h+var_48]
0x180005041  lea     rdx, IID_IDacUISInit
0x180005048  mov     rax, [rax]
0x18000504b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005050  mov     ebx, eax
0x180005052  test    eax, eax
0x180005054  jz      loc_1800050E3
0x18000505a  mov     rcx, cs:?z_pTrace@@3PEAUIDtcTrace@@EA; IDtcTrace * z_pTrace
0x180005061  xor     r9d, r9d; unsigned int
0x180005064  test    rcx, rcx
0x180005067  jz      short loc_1800050B5
0x180005069  mov     rdx, [rcx]
0x18000506c  mov     rax, [rdx+18h]
0x180005070  mov     [rsp+98h+var_60], r15
0x180005075  mov     qword ptr [rsp+98h+var_68], r15
0x18000507a  mov     dword ptr [rsp+98h+var_70], r15d
0x18000507f  mov     dword ptr [rsp+98h+var_78], 0C0001017h
0x180005087  mov     edx, 1
0x18000508c  mov     r8d, edx
0x18000508f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005094  test    eax, eax
0x180005096  jns     short loc_1800050CA
0x180005098  mov     r9d, 961h; unsigned int
0x18000509e  lea     r8, aComComplusDtcD_7; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x1800050a5  lea     rdx, aFailedInZPtrac; "failed in z_pTrace->Trace"
0x1800050ac  mov     ecx, eax; int
0x1800050ae  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x1800050b3  jmp     short loc_1800050CA
0x1800050b5  mov     [rsp+98h+var_78], r15; void *
0x1800050ba  mov     ecx, 1; unsigned int
0x1800050bf  mov     r8d, 0C0001017h; unsigned int
0x1800050c5  call    ?DtcWriteToEventLoggerW@@YAJKKKKPEAXPEAGH@Z; DtcWriteToEventLoggerW(ulong,ulong,ulong,ulong,void *,ushort *,int)
0x1800050ca  mov     rcx, [rdi]
0x1800050cd  mov     rax, [rcx]
0x1800050d0  mov     rax, [rax+10h]
0x1800050d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050d9  mov     [rdi], r15
0x1800050dc  mov     eax, ebx
0x1800050de  jmp     loc_1800051FE
0x1800050e3  mov     rcx, [rsp+98h+var_48]
0x1800050e8  mov     rax, [rcx]
0x1800050eb  mov     dword ptr [rsp+98h+var_70], ebp
0x1800050ef  mov     edx, cs:?z_fService@@3HA; int z_fService
0x1800050f5  mov     dword ptr [rsp+98h+var_78], edx; char *
0x1800050f9  mov     r9, r14
0x1800050fc  mov     r8, [rsp+98h+var_40]
0x180005101  mov     rdx, [rsi+238h]
0x180005108  mov     rax, [rax+18h]
0x18000510c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005111  mov     ebx, eax
0x180005113  mov     rcx, [rsp+98h+var_48]
0x180005118  mov     rdx, [rcx]
0x18000511b  mov     rax, [rdx+10h]
0x18000511f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005124  test    ebx, ebx
0x180005126  jz      short loc_180005156
0x180005128  xor     r9d, r9d; void *
0x18000512b  xor     r8d, r8d; unsigned int
0x18000512e  mov     edx, 0C0001015h; unsigned int
0x180005133  mov     ecx, 1; unsigned int
0x180005138  call    ?locprint@@YAXKKKPEAXPEAD@Z; locprint(ulong,ulong,ulong,void *,char *)
0x18000513d  mov     rcx, [rdi]
0x180005140  mov     rax, [rcx]
0x180005143  mov     rax, [rax+10h]
0x180005147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000514c  mov     [rdi], r15
0x18000514f  mov     eax, ebx
0x180005151  jmp     loc_1800051FE
0x180005156  mov     rcx, [rdi]
0x180005159  mov     rax, [rcx]
0x18000515c  lea     r8, ?z_pTrace@@3PEAUIDtcTrace@@EA; IDtcTrace * z_pTrace
0x180005163  lea     rdx, IID_IDtcTrace
0x18000516a  mov     rax, [rax]
0x18000516d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005172  mov     ebx, eax
0x180005174  xor     r9d, r9d; void *
0x180005177  xor     r8d, r8d; unsigned int
0x18000517a  test    eax, eax
0x18000517c  jns     short loc_1800051A3
0x18000517e  mov     edx, 0C0001017h; unsigned int
0x180005183  mov     ecx, 1; unsigned int
0x180005188  call    ?locprint@@YAXKKKPEAXPEAD@Z; locprint(ulong,ulong,ulong,void *,char *)
0x18000518d  mov     rcx, [rdi]
0x180005190  mov     rdx, [rcx]
0x180005193  mov     rax, [rdx+10h]
0x180005197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000519c  mov     [rdi], r15
0x18000519f  mov     eax, ebx
0x1800051a1  jmp     short loc_1800051FE
0x1800051a3  mov     edx, 40001004h; unsigned int
0x1800051a8  mov     ecx, 100h; unsigned int
0x1800051ad  call    ?locprint@@YAXKKKPEAXPEAD@Z; locprint(ulong,ulong,ulong,void *,char *)
0x1800051b2  xor     r9d, r9d; void *
0x1800051b5  xor     r8d, r8d; unsigned int
0x1800051b8  mov     edx, 4000D022h; unsigned int
0x1800051bd  mov     ecx, 100h; unsigned int
0x1800051c2  call    ?locprint@@YAXKKKPEAXPEAD@Z; locprint(ulong,ulong,ulong,void *,char *)
0x1800051c7  mov     rcx, cs:?z_pTrace@@3PEAUIDtcTrace@@EA; IDtcTrace * z_pTrace
0x1800051ce  mov     rax, [rcx]
0x1800051d1  mov     rax, [rax+8]
  ... truncated ...
```
