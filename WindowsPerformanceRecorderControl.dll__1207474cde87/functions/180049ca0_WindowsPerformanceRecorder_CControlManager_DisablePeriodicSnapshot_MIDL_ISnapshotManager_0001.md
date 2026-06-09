# WindowsPerformanceRecorder::CControlManager::DisablePeriodicSnapshot(__MIDL_ISnapshotManager_0001)

- ea: `0x180049ca0`
- end: `0x18004a0c1`
- name: `?DisablePeriodicSnapshot@CControlManager@WindowsPerformanceRecorder@@UEAAJW4__MIDL_ISnapshotManager_0001@@@Z`
- size: `1057`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x18000829c`
- `0x180009a84`
- `0x180009b40`
- `0x18001a92c`
- `0x18001c8bc`
- `0x18001e6e0`
- `0x1800248d8`
- `0x180040a04`
- `0x180049ca0`
- `0x18004ece0`
- `0x18004ed10`
- `0x18008c010`

## import_xrefs

- `api-ms-win-eventing-controller-l1-1-0!TraceSetInformation` at `0x180049f36`
- `api-ms-win-eventing-controller-l1-1-0!TraceSetInformation` at `0x180049f36`
- `OLEAUT32!__imp_SysFreeString` at `0x180049db5`
- `OLEAUT32!__imp_SysFreeString` at `0x180049e67`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a004`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a03b`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a070`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a08c`
- `OLEAUT32!__imp_SysFreeString` at `0x180049db5`
- `OLEAUT32!__imp_SysFreeString` at `0x180049e67`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a004`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a03b`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a070`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a08c`

## string_xrefs

- `0x180049d6e`: `COMGUARD`
- `0x180049e0f`: `COMGUARD`
- `0x180049fb4`: `COMGUARD`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::DisablePeriodicSnapshot(__int64 a1, int a2)
{
  unsigned int v4; // ebx
  signed int v5; // eax
  struct WindowsPerformanceRecorder::CWPRControl *v7; // rbx
  signed int v8; // eax
  unsigned int v9; // edi
  WindowsPerformanceRecorder::CETWProperties *v10; // r15
  WindowsPerformanceRecorder::CETWProperties *v11; // rax
  __int64 v12; // rax
  _QWORD *i; // rdi
  __int64 v14; // rax
  signed int v15; // r12d
  __int64 v16; // r9
  unsigned int v17; // eax
  const char *v18; // [rsp+28h] [rbp-C0h]
  struct IProfileCollection *v19; // [rsp+50h] [rbp-98h] BYREF
  unsigned int v20; // [rsp+58h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-88h] BYREF
  struct WindowsPerformanceRecorder::CWPRControl *v22; // [rsp+68h] [rbp-80h] BYREF
  int v23; // [rsp+70h] [rbp-78h] BYREF
  WindowsPerformanceRecorder::CETWProperties *v24; // [rsp+78h] [rbp-70h]
  __int64 TraceInformation; // [rsp+80h] [rbp-68h] BYREF
  TRACEHANDLE SessionHandle; // [rsp+88h] [rbp-60h]
  __int64 (__fastcall *v27)(TRACEHANDLE, __int128 *, _QWORD, __int64, _QWORD); // [rsp+90h] [rbp-58h]
  __int64 v28; // [rsp+98h] [rbp-50h]
  __int64 v29; // [rsp+A0h] [rbp-48h]
  ATL::CAtlException *v30; // [rsp+A8h] [rbp-40h] BYREF
  __int128 v31; // [rsp+B0h] [rbp-38h] BYREF

  v29 = -2;
  bstrString = 0;
  v19 = 0;
  v31 = 0;
  v22 = 0;
  if ( (int)WindowsPerformanceRecorder::CWPRControl::GetInstance(&v22) < 0
    || (v27 = (__int64 (__fastcall *)(TRACEHANDLE, __int128 *, _QWORD, __int64, _QWORD))Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)((char *)v22 + 32)) == 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
    SysFreeString(bstrString);
    return 50;
  }
  if ( a2 != 1 )
  {
    v4 = -2147024809;
LABEL_9:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
    SysFreeString(bstrString);
    return v4;
  }
  v31 = HeapSnapGuid;
  v5 = WindowsPerformanceRecorder::CControlManager::QueryRunningProfile(
         (WindowsPerformanceRecorder::CControlManager *)(a1 - 208),
         1,
         &bstrString,
         0,
         &v19);
  v4 = v5;
  if ( v5 < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      "DisablePeriodicSnapshot",
      (const char *)0x1E5,
      v5,
      "COMGUARD",
      v18);
    goto LABEL_9;
  }
  if ( (*(_BYTE *)(a1 + 360) & 2) != 0 )
  {
    v4 = -984076288;
    goto LABEL_9;
  }
  try
  {
    v22 = 0;
    v24 = (WindowsPerformanceRecorder::CETWProperties *)operator new(0x1A8u);
    v7 = (struct WindowsPerformanceRecorder::CWPRControl *)WindowsPerformanceRecorder::CETWProperties::CETWProperties(v24);
    v22 = v7;
    v8 = WindowsPerformanceRecorder::CETWProperties::Initialize(
           v7,
           v19,
           (struct WindowsPerformanceRecorder::CControlManager *)(a1 - 208),
           (*(_DWORD *)(a1 + 360) & 0x10) != 0);
  }
  catch ( ATL::CAtlException *v30 )
  {
    v20 = *(_DWORD *)v30;
    if ( v22 )
      (**(void (__fastcall ***)(struct WindowsPerformanceRecorder::CWPRControl *, __int64))v22)(v22, 1);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
    SysFreeString(bstrString);
    return v20;
  }
  v9 = v8;
  if ( v8 < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      "DisablePeriodicSnapshot",
      (const char *)0x1F0,
      v8,
      "COMGUARD",
      v18);
    if ( v7 )
      (**(void (__fastcall ***)(struct WindowsPerformanceRecorder::CWPRControl *, __int64))v7)(v7, 1);
    v22 = 0;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
    SysFreeString(bstrString);
    return v9;
  }
  v10 = (WindowsPerformanceRecorder::CETWProperties *)*((_QWORD *)v7 + 1);
  v11 = (WindowsPerformanceRecorder::CETWProperties *)*((_QWORD *)v7 + 2);
  v24 = v11;
LABEL_15:
  if ( v10 == v11 )
  {
    if ( v7 )
      (**(void (__fastcall ***)(struct WindowsPerformanceRecorder::CWPRControl *, __int64))v7)(v7, 1);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
    SysFreeString(bstrString);
    return 0;
  }
  v12 = *(_QWORD *)v10;
  v28 = v12;
  for ( i = *(_QWORD **)(v12 + 24); ; i += 33 )
  {
    if ( i == *(_QWORD **)(v12 + 32) )
    {
      v10 = (WindowsPerformanceRecorder::CETWProperties *)((char *)v10 + 8);
      v11 = v24;
      goto LABEL_15;
    }
    v14 = *i - v31;
    if ( *i == (_QWORD)v31 )
      v14 = i[1] - *((_QWORD *)&v31 + 1);
    if ( v14 )
      goto LABEL_23;
    SessionHandle = *(_QWORD *)(*(_QWORD *)(a1 + 184) + 8LL);
    v20 = 0;
    v23 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, TRACEHANDLE, unsigned int *, int *))(*(_QWORD *)a1 + 80LL))(
            a1,
            SessionHandle,
            &v20,
            &v23);
    if ( v15 < 0 )
      break;
    TraceInformation = 0;
    TraceSetInformation(SessionHandle, TracePeriodicCaptureStateListInfo, &TraceInformation, 8u);
    v18 = 0;
    LOBYTE(v16) = 4;
    v17 = v27(SessionHandle, &v31, 0, v16, 0);
    if ( v17 )
    {
      v15 = ATL::AtlHresultFromWin32(v17);
      goto LABEL_27;
    }
LABEL_23:
    v12 = v28;
  }
  WindowsPerformanceRecorder::TraceHR(
    (WindowsPerformanceRecorder *)2,
    "DisablePeriodicSnapshot",
    (const char *)0x202,
    v15,
    "COMGUARD",
    v18);
LABEL_27:
  if ( v7 )
    (**(void (__fastcall ***)(struct WindowsPerformanceRecorder::CWPRControl *, __int64))v7)(v7, 1);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
  SysFreeString(bstrString);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180049ca0  mov     r11, rsp
0x180049ca3  push    r12
0x180049ca5  push    r13
0x180049ca7  push    r15
0x180049ca9  sub     rsp, 0D0h
0x180049cb0  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x180049cb8  mov     [r11+10h], rbx
0x180049cbc  mov     [r11+18h], rdi
0x180049cc0  mov     rax, cs:__security_cookie
0x180049cc7  xor     rax, rsp
0x180049cca  mov     [rsp+0E8h+var_28], rax
0x180049cd2  mov     ebx, edx
0x180049cd4  mov     r13, rcx
0x180049cd7  mov     [rsp+0E8h+bstrString], 0
0x180049ce0  mov     [rsp+0E8h+var_98], 0
0x180049ce9  xorps   xmm0, xmm0
0x180049cec  movups  xmmword ptr [r11-38h], xmm0
0x180049cf1  mov     qword ptr [r11-80h], 0
0x180049cf9  lea     rcx, [r11-80h]; struct WindowsPerformanceRecorder::CWPRControl **
0x180049cfd  call    ?GetInstance@CWPRControl@WindowsPerformanceRecorder@@SAJPEAPEAV12@@Z; WindowsPerformanceRecorder::CWPRControl::GetInstance(WindowsPerformanceRecorder::CWPRControl * *)
0x180049d02  test    eax, eax
0x180049d04  js      loc_18004A07C
0x180049d0a  mov     rcx, [rsp+0E8h+var_80]
0x180049d0f  add     rcx, 20h ; ' '
0x180049d13  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x180049d18  mov     [rsp+0E8h+var_58], rax
0x180049d20  test    rax, rax
0x180049d23  jz      loc_18004A07C
0x180049d29  cmp     ebx, 1
0x180049d2c  jz      short loc_180049D35
0x180049d2e  mov     ebx, 80070057h
0x180049d33  jmp     short loc_180049DA5
0x180049d35  movups  xmm0, cs:HeapSnapGuid
0x180049d3c  movdqu  [rsp+0E8h+var_38], xmm0
0x180049d45  lea     rdi, [r13-0D0h]
0x180049d4c  lea     rax, [rsp+0E8h+var_98]
0x180049d51  mov     [rsp+0E8h+Format], rax; struct IProfileCollection **
0x180049d56  xor     r9d, r9d; unsigned __int16 **
0x180049d59  lea     r8, [rsp+0E8h+bstrString]; unsigned __int16 **
0x180049d5e  mov     dl, 1; bool
0x180049d60  mov     rcx, rdi; this
0x180049d63  call    ?QueryRunningProfile@CControlManager@WindowsPerformanceRecorder@@AEAAJ_NPEAPEAG1PEAPEAUIProfileCollection@@@Z; WindowsPerformanceRecorder::CControlManager::QueryRunningProfile(bool,ushort * *,ushort * *,IProfileCollection * *)
0x180049d68  mov     ebx, eax
0x180049d6a  test    eax, eax
0x180049d6c  jns     short loc_180049D96
0x180049d6e  lea     rax, aComguard; "COMGUARD"
0x180049d75  mov     [rsp+0E8h+Format], rax; Format
0x180049d7a  mov     r9d, ebx; unsigned int
0x180049d7d  mov     r8d, 1E5h; char *
0x180049d83  lea     rdx, aDisableperiodi; "DisablePeriodicSnapshot"
0x180049d8a  mov     ecx, 2; this
0x180049d8f  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180049d94  jmp     short loc_180049DA5
0x180049d96  test    byte ptr [r13+168h], 2
0x180049d9e  jz      short loc_180049DC2
0x180049da0  mov     ebx, 0C5583000h
0x180049da5  lea     rcx, [rsp+0E8h+var_98]
0x180049daa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180049daf  nop
0x180049db0  mov     rcx, [rsp+0E8h+bstrString]; bstrString
0x180049db5  call    cs:__imp_SysFreeString
0x180049dbb  mov     eax, ebx
0x180049dbd  jmp     loc_18004A097
0x180049dc2  mov     [rsp+0E8h+var_80], 0
0x180049dcb  mov     ecx, 1A8h; Size
0x180049dd0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180049dd5  mov     [rsp+0E8h+var_70], rax
0x180049dda  mov     rcx, rax; this
0x180049ddd  call    ??0CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CETWProperties(void)
0x180049de2  mov     rbx, rax
0x180049de5  mov     [rsp+0E8h+var_80], rax
0x180049dea  mov     r9d, [r13+168h]
0x180049df1  shr     r9d, 4
0x180049df5  and     r9b, 1; bool
0x180049df9  mov     r8, rdi; struct WindowsPerformanceRecorder::CControlManager *
0x180049dfc  mov     rdx, [rsp+0E8h+var_98]; struct IProfileCollection *
0x180049e01  mov     rcx, rax; this
0x180049e04  call    ?Initialize@CETWProperties@WindowsPerformanceRecorder@@QEAAJPEAUIProfileCollection@@PEAVCControlManager@2@_N@Z; WindowsPerformanceRecorder::CETWProperties::Initialize(IProfileCollection *,WindowsPerformanceRecorder::CControlManager *,bool)
0x180049e09  mov     edi, eax
0x180049e0b  test    eax, eax
0x180049e0d  jns     short loc_180049E74
0x180049e0f  lea     rax, aComguard; "COMGUARD"
0x180049e16  mov     [rsp+0E8h+Format], rax; Format
0x180049e1b  mov     r9d, edi; unsigned int
0x180049e1e  mov     r8d, 1F0h; char *
0x180049e24  lea     rdx, aDisableperiodi; "DisablePeriodicSnapshot"
0x180049e2b  mov     ecx, 2; this
0x180049e30  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180049e35  nop
0x180049e36  test    rbx, rbx
0x180049e39  jz      short loc_180049E4E
0x180049e3b  mov     rax, [rbx]
0x180049e3e  mov     edx, 1
0x180049e43  mov     rcx, rbx
0x180049e46  mov     rax, [rax]
0x180049e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e4e  mov     [rsp+0E8h+var_80], 0
0x180049e57  lea     rcx, [rsp+0E8h+var_98]
0x180049e5c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180049e61  nop
0x180049e62  mov     rcx, [rsp+0E8h+bstrString]; bstrString
0x180049e67  call    cs:__imp_SysFreeString
0x180049e6d  mov     eax, edi
0x180049e6f  jmp     loc_18004A097
0x180049e74  mov     r15, [rbx+8]
0x180049e78  mov     rax, [rbx+10h]
0x180049e7c  mov     [rsp+0E8h+var_70], rax
0x180049e81  cmp     r15, rax
0x180049e84  jz      loc_18004A012
0x180049e8a  mov     rax, [r15]
0x180049e8d  mov     [rsp+0E8h+var_50], rax
0x180049e95  mov     rdi, [rax+18h]
0x180049e99  cmp     rdi, [rax+20h]
0x180049e9d  jz      loc_180049F9A
0x180049ea3  mov     rax, [rdi]
0x180049ea6  sub     rax, qword ptr [rsp+0E8h+var_38]
0x180049eae  jnz     short loc_180049EBC
0x180049eb0  mov     rax, [rdi+8]
0x180049eb4  sub     rax, qword ptr [rsp+0E8h+var_38+8]
0x180049ebc  test    rax, rax
0x180049ebf  jnz     loc_180049F86
0x180049ec5  mov     rax, [r13+0B8h]
0x180049ecc  mov     rcx, [rax+8]
0x180049ed0  mov     [rsp+0E8h+SessionHandle], rcx
0x180049ed8  mov     [rsp+0E8h+var_90], 0
0x180049ee0  mov     [rsp+0E8h+var_78], 0
0x180049ee8  mov     rax, [r13+0]
0x180049eec  lea     r9, [rsp+0E8h+var_78]
0x180049ef1  lea     r8, [rsp+0E8h+var_90]
0x180049ef6  mov     rdx, rcx
0x180049ef9  mov     rcx, r13
0x180049efc  mov     rax, [rax+50h]
0x180049f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f05  mov     r12d, eax
0x180049f08  test    eax, eax
0x180049f0a  js      loc_180049FB4
0x180049f10  mov     [rsp+0E8h+TraceInformation], 0
0x180049f1c  mov     r9d, 8; InformationLength
0x180049f22  lea     r8, [rsp+0E8h+TraceInformation]; TraceInformation
0x180049f2a  lea     edx, [r9+8]; InformationClass
0x180049f2e  mov     rcx, [rsp+0E8h+SessionHandle]; SessionHandle
0x180049f36  call    cs:__imp_TraceSetInformation
0x180049f3c  mov     [rsp+0E8h+var_B0], 0
0x180049f45  mov     [rsp+0E8h+var_B8], 0
0x180049f4d  mov     [rsp+0E8h+var_C0], 0
0x180049f56  mov     [rsp+0E8h+Format], 0
0x180049f5f  mov     r9b, 4
0x180049f62  xor     r8d, r8d
0x180049f65  lea     rdx, [rsp+0E8h+var_38]
0x180049f6d  mov     rcx, [rsp+0E8h+SessionHandle]
0x180049f75  mov     rax, [rsp+0E8h+var_58]
0x180049f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f82  test    eax, eax
0x180049f84  jnz     short loc_180049FA8
0x180049f86  add     rdi, 108h
0x180049f8d  mov     rax, [rsp+0E8h+var_50]
0x180049f95  jmp     loc_180049E99
0x180049f9a  add     r15, 8
0x180049f9e  mov     rax, [rsp+0E8h+var_70]
0x180049fa3  jmp     loc_180049E81
0x180049fa8  mov     ecx, eax; unsigned int
0x180049faa  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180049faf  mov     r12d, eax
0x180049fb2  jmp     short loc_180049FDB
0x180049fb4  lea     rax, aComguard; "COMGUARD"
0x180049fbb  mov     [rsp+0E8h+Format], rax; Format
0x180049fc0  mov     r9d, r12d; unsigned int
0x180049fc3  mov     r8d, 202h; char *
0x180049fc9  lea     rdx, aDisableperiodi; "DisablePeriodicSnapshot"
0x180049fd0  mov     ecx, 2; this
0x180049fd5  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180049fda  nop
0x180049fdb  test    rbx, rbx
0x180049fde  jz      short loc_180049FF4
0x180049fe0  mov     rax, [rbx]
0x180049fe3  mov     edx, 1
0x180049fe8  mov     rcx, rbx
0x180049feb  mov     rax, [rax]
0x180049fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ff3  nop
0x180049ff4  lea     rcx, [rsp+0E8h+var_98]
0x180049ff9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180049ffe  nop
0x180049fff  mov     rcx, [rsp+0E8h+bstrString]; bstrString
0x18004a004  call    cs:__imp_SysFreeString
0x18004a00a  mov     eax, r12d
0x18004a00d  jmp     loc_18004A097
0x18004a012  test    rbx, rbx
0x18004a015  jz      short loc_18004A02B
0x18004a017  mov     rax, [rbx]
0x18004a01a  mov     edx, 1
0x18004a01f  mov     rcx, rbx
0x18004a022  mov     rax, [rax]
0x18004a025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a02a  nop
0x18004a02b  lea     rcx, [rsp+0E8h+var_98]
0x18004a030  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004a035  nop
0x18004a036  mov     rcx, [rsp+0E8h+bstrString]; bstrString
0x18004a03b  call    cs:__imp_SysFreeString
0x18004a041  xor     eax, eax
0x18004a043  jmp     short loc_18004A097
0x18004a045  mov     rcx, [rsp+0E8h+var_80]
0x18004a04a  test    rcx, rcx
0x18004a04d  jz      short loc_18004A060
0x18004a04f  mov     rax, [rcx]
0x18004a052  mov     edx, 1
0x18004a057  mov     rax, [rax]
0x18004a05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a05f  nop
0x18004a060  lea     rcx, [rsp+0E8h+var_98]
0x18004a065  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004a06a  nop
0x18004a06b  mov     rcx, [rsp+0E8h+bstrString]; bstrString
0x18004a070  call    cs:__imp_SysFreeString
0x18004a076  mov     eax, [rsp+0E8h+var_90]
0x18004a07a  jmp     short loc_18004A097
0x18004a07c  lea     rcx, [rsp+0E8h+var_98]
0x18004a081  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004a086  nop
0x18004a087  mov     rcx, [rsp+0E8h+bstrString]; bstrString
0x18004a08c  call    cs:__imp_SysFreeString
0x18004a092  mov     eax, 32h ; '2'
0x18004a097  mov     rcx, [rsp+0E8h+var_28]
0x18004a09f  xor     rcx, rsp; StackCookie
0x18004a0a2  call    __security_check_cookie
0x18004a0a7  lea     r11, [rsp+0E8h+var_18]
0x18004a0af  mov     rbx, [r11+28h]
0x18004a0b3  mov     rdi, [r11+30h]
0x18004a0b7  mov     rsp, r11
0x18004a0ba  pop     r15
0x18004a0bc  pop     r13
0x18004a0be  pop     r12
0x18004a0c0  retn
```
