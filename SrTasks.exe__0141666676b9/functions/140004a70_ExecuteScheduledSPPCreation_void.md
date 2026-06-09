# _ExecuteScheduledSPPCreation(void)

- ea: `0x140004a70`
- end: `0x1400050ea`
- name: `?_ExecuteScheduledSPPCreation@@YAJXZ`
- size: `1658`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140002f30`

## callees

- `0x140001b3c`
- `0x140002ae8`
- `0x140002e1c`
- `0x140002e44`
- `0x140003e70`
- `0x1400041ec`
- `0x140004410`
- `0x1400047e4`
- `0x140004a70`
- `0x1400050f0`
- `0x140006ab0`
- `0x14000e324`
- `0x14000e41c`
- `0x14000e7b0`
- `0x14000e7e8`
- `0x1400102a4`
- `0x140010744`
- `0x14001094e`
- `0x140010980`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140004b4b`
- `KERNEL32!GetLastError` at `0x140004b4b`
- `KERNEL32!GetModuleHandleW` at `0x140004b37`
- `KERNEL32!GetModuleHandleW` at `0x140004b37`
- `SRCLIENT!SRSetRestorePointW` at `0x140004e84`
- `SRCLIENT!SRSetRestorePointW` at `0x140004e84`
- `ole32!CoCreateInstance` at `0x140004bd9`
- `ole32!CoCreateInstance` at `0x140004f43`
- `ole32!CoCreateInstance` at `0x140004bd9`
- `ole32!CoCreateInstance` at `0x140004f43`

## string_xrefs

- `0x140004ad7`: `_ExecuteScheduledSPPCreation`

## pseudocode

```c
__int64 _ExecuteScheduledSPPCreation(void)
{
  unsigned int llSequenceNumber; // esi
  HMODULE ModuleHandleW; // rdi
  signed int LastError; // eax
  bool v3; // sf
  __int16 v4; // ax
  HRESULT Instance; // eax
  HRESULT v6; // ebx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // ecx
  __int16 v13; // ax
  int v14; // ecx
  signed int nStatus; // ebx
  unsigned int v16; // r8d
  WCHAR *v17; // r8
  WCHAR *szDescription; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  WCHAR *v21; // rcx
  HRESULT v22; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  unsigned int v28; // ebx
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v31; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 v32[7]; // [rsp+31h] [rbp-CFh] BYREF
  struct ISharedProtectionPoints *v33; // [rsp+38h] [rbp-C8h] BYREF
  int v34; // [rsp+40h] [rbp-C0h] BYREF
  signed int ShouldCreateScopedSnapshots; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v36; // [rsp+4Ch] [rbp-B4h]
  __int16 v37; // [rsp+4Eh] [rbp-B2h]
  LPVOID v38; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v39[2]; // [rsp+88h] [rbp-78h] BYREF
  _SMGRSTATUS pSMgrStatus; // [rsp+98h] [rbp-68h] BYREF
  _RESTOREPTINFOW pRestorePtSpec; // [rsp+B0h] [rbp-50h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&ShouldCreateScopedSnapshots,
    "_ExecuteScheduledSPPCreation",
    0x132u,
    1u);
  v39[0] = qword_140013960;
  v33 = 0;
  v39[1] = 0;
  memset_0(&pRestorePtSpec, 0, sizeof(pRestorePtSpec));
  v34 = 0;
  *(_QWORD *)&pSMgrStatus.nStatus = 0;
  HIDWORD(pSMgrStatus.llSequenceNumber) = 0;
  llSequenceNumber = 0;
  v32[0] = 1;
  v38 = 0;
  v31 = 0;
  ModuleHandleW = GetModuleHandleW(0);
  if ( !ModuleHandleW )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ShouldCreateScopedSnapshots = LastError;
    v3 = LastError < 0;
    v4 = 324;
    if ( v3 )
      goto LABEL_8;
    v36 = 324;
  }
  ShouldCreateScopedSnapshots = SxShouldCreateScopedSnapshots(&v31);
  v4 = 329;
  if ( ShouldCreateScopedSnapshots < 0 )
    goto LABEL_8;
  v36 = 329;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids);
  Instance = CoCreateInstance(&CLSID_SPP, 0, 1u, &IID_ISharedProtectionPoints, (LPVOID *)&v33);
  v6 = Instance;
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids,
        (unsigned int)Instance);
    ShouldCreateScopedSnapshots = v6;
    v4 = 337;
    goto LABEL_8;
  }
  v7 = (*(__int64 (__fastcall **)(struct ISharedProtectionPoints *))(*(_QWORD *)v33 + 240LL))(v33);
  if ( v7 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids,
      (unsigned int)v7);
  }
  v8 = (*(__int64 (__fastcall **)(struct ISharedProtectionPoints *))(*(_QWORD *)v33 + 288LL))(v33);
  if ( v8 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids,
      (unsigned int)v8);
  }
  v9 = _DeletePartialSPPGroups(v33);
  if ( v9 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids,
      (unsigned int)v9);
  }
  v10 = _DeleteOldSPPGroups(v33);
  if ( v10 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids,
      (unsigned int)v10);
  }
  v11 = (*(__int64 (__fastcall **)(struct ISharedProtectionPoints *))(*(_QWORD *)v33 + 272LL))(v33);
  if ( v11 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids,
      (unsigned int)v11);
  }
  v12 = _CheckRecentSPPCheckpoint();
  ShouldCreateScopedSnapshots = v12;
  v4 = 381;
  if ( v12 < 0 )
    goto LABEL_8;
  v36 = 381;
  if ( v12 )
  {
    v14 = CheckSREnabled(v33, &v34, 0);
    ShouldCreateScopedSnapshots = v14;
    v4 = 389;
    if ( v14 >= 0 )
    {
      v36 = 389;
      if ( v14 == 1 )
      {
        v13 = 393;
        goto LABEL_67;
      }
      nStatus = _CheckRecentSPPCheckpoint();
      ShouldCreateScopedSnapshots = nStatus;
      v4 = 400;
      if ( nStatus >= 0 )
      {
        v36 = 400;
        if ( !nStatus )
        {
          v13 = 404;
          goto LABEL_67;
        }
        ShouldCreateScopedSnapshots = CBsString::LoadStringResource((CBsString *)v39, ModuleHandleW, v16);
        v4 = 407;
        if ( ShouldCreateScopedSnapshots >= 0 )
        {
          v36 = 407;
          if ( !v34 )
            goto LABEL_64;
          v17 = (WCHAR *)v39[0];
          szDescription = pRestorePtSpec.szDescription;
          v19 = 63;
          pRestorePtSpec.dwEventType = 100;
          pRestorePtSpec.dwRestorePtType = 7;
          pRestorePtSpec.llSequenceNumber = 0;
          v20 = 64;
          do
          {
            if ( !v19 )
              break;
            if ( !*v17 )
              break;
            *szDescription++ = *v17++;
            --v19;
            --v20;
          }
          while ( v20 );
          v21 = szDescription - 1;
          if ( v20 )
            v21 = szDescription;
          v4 = 415;
          *v21 = 0;
          ShouldCreateScopedSnapshots = v20 == 0 ? 0x8007007A : 0;
          if ( !v20 )
            goto LABEL_8;
          v36 = 415;
          nStatus = 0;
          if ( !SRSetRestorePointW(&pRestorePtSpec, &pSMgrStatus) )
          {
            nStatus = pSMgrStatus.nStatus;
            if ( (int)pSMgrStatus.nStatus > 0 )
              nStatus = LOWORD(pSMgrStatus.nStatus) | 0x80070000;
          }
          llSequenceNumber = pSMgrStatus.llSequenceNumber;
          if ( nStatus >= 0 || nStatus == -2147023838 || nStatus == -2147023636 )
          {
LABEL_64:
            ShouldCreateScopedSnapshots = nStatus;
            if ( nStatus >= 0 )
            {
              v36 = 431;
              CSxFunctionTracer::LogInfo(
                (CSxFunctionTracer *)&ShouldCreateScopedSnapshots,
                L"System Restore",
                0x2014u,
                &dword_140012F54);
              v13 = 435;
              goto LABEL_67;
            }
          }
          else
          {
            LODWORD(ppv) = nStatus;
            CSxFunctionTracer::LogFailure(
              (CSxFunctionTracer *)&ShouldCreateScopedSnapshots,
              L"System Restore",
              0x2013u,
              L"0x%08x",
              ppv);
            ShouldCreateScopedSnapshots = nStatus;
          }
          v4 = 431;
        }
      }
    }
LABEL_8:
    v37 = v4;
    goto LABEL_68;
  }
  v13 = 385;
LABEL_67:
  v36 = v13;
  ShouldCreateScopedSnapshots = 0;
LABEL_68:
  v22 = CoCreateInstance(&CLSID_SrDrvWuHelper, 0, 1u, &IID_ISrDrvWuHelper, &v38);
  if ( v22 >= 0 )
  {
    v22 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v38 + 48LL))(v38, 15);
    if ( v22 >= 0 )
    {
LABEL_77:
      v23 = WPP_GLOBAL_Control;
      goto LABEL_78;
    }
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      v24 = 34;
      goto LABEL_76;
    }
  }
  else
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      v24 = 33;
LABEL_76:
      WPP_SF_d(v23[2], v24, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids, (unsigned int)v22);
      goto LABEL_77;
    }
  }
LABEL_78:
  if ( v31 )
  {
    if ( !llSequenceNumber )
      goto LABEL_85;
    v25 = WaitForRestorePointToAppear(llSequenceNumber, v32);
    if ( v25 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids,
        (unsigned int)v25);
    }
    if ( v32[0] )
    {
LABEL_85:
      v26 = _ExecuteScopeRestorePoint();
      if ( v26 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids,
          (unsigned int)v26);
      }
    }
  }
  else if ( v23 != &WPP_GLOBAL_Control && (*((_DWORD *)v23 + 7) & 0x8000000) != 0 )
  {
    WPP_SF_(v23[2], 37, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids);
  }
  if ( v33 )
  {
    v27 = PublishMaintenanceTasksSQM(v33);
    if ( v27 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids,
        (unsigned int)v27);
    }
  }
  v28 = ShouldCreateScopedSnapshots;
  if ( v38 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v38 + 16LL))(v38);
  CBsString::_Release((CBsString *)v39);
  if ( v33 )
    (*(void (__fastcall **)(struct ISharedProtectionPoints *))(*(_QWORD *)v33 + 16LL))(v33);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&ShouldCreateScopedSnapshots);
  return v28;
}

```

## disassembly

```asm
0x140004a70  push    rbp
0x140004a72  push    rbx
0x140004a73  push    rsi
0x140004a74  push    rdi
0x140004a75  push    r12
0x140004a77  push    r13
0x140004a79  push    r14
0x140004a7b  push    r15
0x140004a7d  lea     rbp, [rsp-1D8h]
0x140004a85  sub     rsp, 2D8h
0x140004a8c  mov     rax, cs:__security_cookie
0x140004a93  xor     rax, rsp
0x140004a96  mov     [rbp+210h+var_50], rax
0x140004a9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004aa4  lea     r15, WPP_GLOBAL_Control
0x140004aab  lea     r12, WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids
0x140004ab2  cmp     rcx, r15
0x140004ab5  jz      short loc_140004AD1
0x140004ab7  test    dword ptr [rcx+1Ch], 20000000h
0x140004abe  jz      short loc_140004AD1
0x140004ac0  mov     rcx, [rcx+10h]
0x140004ac4  mov     edx, 19h
0x140004ac9  mov     r8, r12
0x140004acc  call    WPP_SF_
0x140004ad1  mov     r9d, 1; unsigned __int16
0x140004ad7  lea     rdx, aExecuteschedul_0; "_ExecuteScheduledSPPCreation"
0x140004ade  mov     r8d, 132h; unsigned __int16
0x140004ae4  lea     rcx, [rsp+310h+var_2C8]; this
0x140004ae9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140004aee  lea     rax, qword_140013960
0x140004af5  xor     r14d, r14d
0x140004af8  xor     edx, edx; Val
0x140004afa  mov     [rbp+210h+var_288], rax
0x140004afe  mov     r8d, 210h; Size
0x140004b04  mov     [rsp+310h+var_2D8], r14
0x140004b09  lea     rcx, [rbp+210h+pRestorePtSpec]; void *
0x140004b0d  mov     [rbp+210h+var_280], r14
0x140004b11  call    memset_0
0x140004b16  xor     eax, eax
0x140004b18  mov     [rsp+310h+var_2D0], r14d
0x140004b1d  xor     ecx, ecx; lpModuleName
0x140004b1f  mov     qword ptr [rbp+210h+pSMgrStatus.nStatus], rax
0x140004b23  mov     dword ptr [rbp+210h+pSMgrStatus.llSequenceNumber+4], eax
0x140004b26  mov     esi, r14d
0x140004b29  mov     [rsp+310h+var_2DF], 1
0x140004b2e  mov     [rbp+210h+var_290], r14
0x140004b32  mov     [rsp+310h+var_2E0], r14b
0x140004b37  call    cs:__imp_GetModuleHandleW
0x140004b3d  mov     rdi, rax
0x140004b40  mov     r13d, 4000000h
0x140004b46  test    rax, rax
0x140004b49  jnz     short loc_140004B79
0x140004b4b  call    cs:__imp_GetLastError
0x140004b51  test    eax, eax
0x140004b53  jle     short loc_140004B5D
0x140004b55  movzx   eax, ax
0x140004b58  or      eax, 80070000h
0x140004b5d  mov     [rsp+310h+var_2C8], eax
0x140004b61  test    eax, eax
0x140004b63  mov     eax, 144h
0x140004b68  jns     short loc_140004B74
0x140004b6a  mov     [rsp+310h+var_2C2], ax
0x140004b6f  jmp     loc_140004F26
0x140004b74  mov     [rsp+310h+var_2C4], ax
0x140004b79  lea     rcx, [rsp+310h+var_2E0]; unsigned __int8 *
0x140004b7e  call    ?SxShouldCreateScopedSnapshots@@YAJPEAE@Z; SxShouldCreateScopedSnapshots(uchar *)
0x140004b83  mov     [rsp+310h+var_2C8], eax
0x140004b87  test    eax, eax
0x140004b89  mov     eax, 149h
0x140004b8e  js      short loc_140004B6A
0x140004b90  mov     [rsp+310h+var_2C4], ax
0x140004b95  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b9c  cmp     rcx, r15
0x140004b9f  jz      short loc_140004BBB
0x140004ba1  test    dword ptr [rcx+1Ch], 8000000h
0x140004ba8  jz      short loc_140004BBB
0x140004baa  mov     rcx, [rcx+10h]
0x140004bae  mov     edx, 1Ah
0x140004bb3  mov     r8, r12
0x140004bb6  call    WPP_SF_
0x140004bbb  xor     edx, edx; pUnkOuter
0x140004bbd  lea     rax, [rsp+310h+var_2D8]
0x140004bc2  lea     r9, IID_ISharedProtectionPoints; riid
0x140004bc9  mov     [rsp+310h+ppv], rax; ppv
0x140004bce  lea     rcx, CLSID_SPP; rclsid
0x140004bd5  lea     r8d, [rdx+1]; dwClsContext
0x140004bd9  call    cs:__imp_CoCreateInstance
0x140004bdf  mov     ebx, eax
0x140004be1  test    eax, eax
0x140004be3  jns     short loc_140004C1C
0x140004be5  mov     rcx, cs:WPP_GLOBAL_Control
0x140004bec  cmp     rcx, r15
0x140004bef  jz      short loc_140004C0E
0x140004bf1  test    dword ptr [rcx+1Ch], 2000000h
0x140004bf8  jz      short loc_140004C0E
0x140004bfa  mov     rcx, [rcx+10h]
0x140004bfe  mov     edx, 1Bh
0x140004c03  mov     r9d, eax
0x140004c06  mov     r8, r12
0x140004c09  call    WPP_SF_d
0x140004c0e  mov     [rsp+310h+var_2C8], ebx
0x140004c12  mov     eax, 151h
0x140004c17  jmp     loc_140004B6A
0x140004c1c  mov     rcx, [rsp+310h+var_2D8]
0x140004c21  mov     rax, [rcx]
0x140004c24  mov     rax, [rax+0F0h]
0x140004c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c30  test    eax, eax
0x140004c32  jns     short loc_140004C5D
0x140004c34  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c3b  cmp     rcx, r15
0x140004c3e  jz      short loc_140004C5D
0x140004c40  test    dword ptr [rcx+1Ch], 2000000h
0x140004c47  jz      short loc_140004C5D
0x140004c49  mov     rcx, [rcx+10h]
0x140004c4d  mov     edx, 1Ch
0x140004c52  mov     r9d, eax
0x140004c55  mov     r8, r12
0x140004c58  call    WPP_SF_d
0x140004c5d  mov     rcx, [rsp+310h+var_2D8]
0x140004c62  mov     rax, [rcx]
0x140004c65  mov     rax, [rax+120h]
0x140004c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c71  test    eax, eax
0x140004c73  jns     short loc_140004C9B
0x140004c75  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c7c  cmp     rcx, r15
0x140004c7f  jz      short loc_140004C9B
0x140004c81  test    [rcx+1Ch], r13d
0x140004c85  jz      short loc_140004C9B
0x140004c87  mov     rcx, [rcx+10h]
0x140004c8b  mov     edx, 1Dh
0x140004c90  mov     r9d, eax
0x140004c93  mov     r8, r12
0x140004c96  call    WPP_SF_d
0x140004c9b  mov     rcx, [rsp+310h+var_2D8]; struct ISharedProtectionPoints *
0x140004ca0  call    ?_DeletePartialSPPGroups@@YAJPEAUISharedProtectionPoints@@@Z; _DeletePartialSPPGroups(ISharedProtectionPoints *)
0x140004ca5  test    eax, eax
0x140004ca7  jns     short loc_140004CCF
0x140004ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x140004cb0  cmp     rcx, r15
0x140004cb3  jz      short loc_140004CCF
0x140004cb5  test    [rcx+1Ch], r13d
0x140004cb9  jz      short loc_140004CCF
0x140004cbb  mov     rcx, [rcx+10h]
0x140004cbf  mov     edx, 1Eh
0x140004cc4  mov     r9d, eax
0x140004cc7  mov     r8, r12
0x140004cca  call    WPP_SF_d
0x140004ccf  mov     rcx, [rsp+310h+var_2D8]; struct ISharedProtectionPoints *
0x140004cd4  call    ?_DeleteOldSPPGroups@@YAJPEAUISharedProtectionPoints@@@Z; _DeleteOldSPPGroups(ISharedProtectionPoints *)
0x140004cd9  test    eax, eax
0x140004cdb  jns     short loc_140004D03
0x140004cdd  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ce4  cmp     rcx, r15
0x140004ce7  jz      short loc_140004D03
0x140004ce9  test    [rcx+1Ch], r13d
0x140004ced  jz      short loc_140004D03
0x140004cef  mov     rcx, [rcx+10h]
0x140004cf3  mov     edx, 1Fh
0x140004cf8  mov     r9d, eax
0x140004cfb  mov     r8, r12
0x140004cfe  call    WPP_SF_d
0x140004d03  mov     rcx, [rsp+310h+var_2D8]
0x140004d08  mov     rax, [rcx]
0x140004d0b  mov     rax, [rax+110h]
0x140004d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004d17  test    eax, eax
0x140004d19  jns     short loc_140004D41
0x140004d1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d22  cmp     rcx, r15
0x140004d25  jz      short loc_140004D41
0x140004d27  test    [rcx+1Ch], r13d
0x140004d2b  jz      short loc_140004D41
0x140004d2d  mov     rcx, [rcx+10h]
0x140004d31  mov     edx, 20h ; ' '
0x140004d36  mov     r9d, eax
0x140004d39  mov     r8, r12
0x140004d3c  call    WPP_SF_d
0x140004d41  call    ?_CheckRecentSPPCheckpoint@@YAJXZ; _CheckRecentSPPCheckpoint(void)
0x140004d46  mov     ecx, eax
0x140004d48  mov     [rsp+310h+var_2C8], eax
0x140004d4c  test    eax, eax
0x140004d4e  mov     eax, 17Dh
0x140004d53  js      loc_140004B6A
0x140004d59  mov     [rsp+310h+var_2C4], ax
0x140004d5e  test    ecx, ecx
0x140004d60  jnz     short loc_140004D6C
0x140004d62  mov     eax, 181h
0x140004d67  jmp     loc_140004F1C
0x140004d6c  mov     rcx, [rsp+310h+var_2D8]; struct ISharedProtectionPoints *
0x140004d71  lea     rdx, [rsp+310h+var_2D0]; int *
0x140004d76  xor     r8d, r8d; unsigned int *
0x140004d79  call    ?CheckSREnabled@@YAJPEAUISharedProtectionPoints@@PEAHPEAK@Z; CheckSREnabled(ISharedProtectionPoints *,int *,ulong *)
0x140004d7e  mov     ecx, eax
0x140004d80  mov     [rsp+310h+var_2C8], eax
0x140004d84  test    eax, eax
0x140004d86  mov     eax, 185h
0x140004d8b  js      loc_140004B6A
0x140004d91  mov     [rsp+310h+var_2C4], ax
0x140004d96  cmp     ecx, 1
0x140004d99  jnz     short loc_140004DA5
0x140004d9b  mov     eax, 189h
0x140004da0  jmp     loc_140004F1C
0x140004da5  call    ?_CheckRecentSPPCheckpoint@@YAJXZ; _CheckRecentSPPCheckpoint(void)
0x140004daa  mov     ebx, eax
0x140004dac  mov     [rsp+310h+var_2C8], eax
0x140004db0  test    eax, eax
0x140004db2  mov     eax, 190h
0x140004db7  js      loc_140004B6A
0x140004dbd  mov     [rsp+310h+var_2C4], ax
0x140004dc2  test    ebx, ebx
0x140004dc4  jnz     short loc_140004DD0
0x140004dc6  mov     eax, 194h
0x140004dcb  jmp     loc_140004F1C
0x140004dd0  mov     rdx, rdi; hInstance
0x140004dd3  lea     rcx, [rbp+210h+var_288]; this
0x140004dd7  call    ?LoadStringResource@CBsString@@QEAAJPEAUHINSTANCE__@@I@Z; CBsString::LoadStringResource(HINSTANCE__ *,uint)
0x140004ddc  mov     [rsp+310h+var_2C8], eax
0x140004de0  test    eax, eax
0x140004de2  mov     eax, 197h
0x140004de7  js      loc_140004B6A
0x140004ded  mov     [rsp+310h+var_2C4], ax
0x140004df2  cmp     [rsp+310h+var_2D0], r14d
0x140004df7  jz      loc_140004EDD
0x140004dfd  mov     r8, [rbp+210h+var_288]
0x140004e01  lea     rax, [rbp+210h+pRestorePtSpec.szDescription]
0x140004e05  mov     ecx, 3Fh ; '?'
0x140004e0a  mov     [rbp+210h+pRestorePtSpec.dwEventType], 64h ; 'd'
0x140004e11  mov     [rbp+210h+pRestorePtSpec.dwRestorePtType], 7
0x140004e18  mov     [rbp+210h+pRestorePtSpec.llSequenceNumber], r14
0x140004e1c  lea     edx, [rcx+1]
0x140004e1f  test    rcx, rcx
0x140004e22  jz      short loc_140004E43
0x140004e24  movzx   r9d, word ptr [r8]
0x140004e28  test    r9w, r9w
0x140004e2c  jz      short loc_140004E43
0x140004e2e  mov     [rax], r9w
0x140004e32  add     r8, 2
0x140004e36  add     rax, 2
0x140004e3a  dec     rcx
0x140004e3d  sub     rdx, 1
0x140004e41  jnz     short loc_140004E1F
0x140004e43  lea     rcx, [rax-2]
0x140004e47  test    rdx, rdx
0x140004e4a  cmovnz  rcx, rax
0x140004e4e  mov     rax, rdx
0x140004e51  neg     rax
0x140004e54  mov     eax, 19Fh
0x140004e59  mov     [rcx], r14w
0x140004e5d  sbb     ecx, ecx
0x140004e5f  not     ecx
0x140004e61  and     ecx, 8007007Ah
0x140004e67  mov     [rsp+310h+var_2C8], ecx
0x140004e6b  test    rdx, rdx
0x140004e6e  jz      loc_140004B6A
0x140004e74  lea     rdx, [rbp+210h+pSMgrStatus]; pSMgrStatus
0x140004e78  mov     [rsp+310h+var_2C4], ax
0x140004e7d  lea     rcx, [rbp+210h+pRestorePtSpec]; pRestorePtSpec
0x140004e81  mov     ebx, r14d
0x140004e84  call    cs:__imp_SRSetRestorePointW
0x140004e8a  test    eax, eax
0x140004e8c  jnz     short loc_140004E9E
0x140004e8e  mov     ebx, [rbp+210h+pSMgrStatus.nStatus]
0x140004e91  test    ebx, ebx
0x140004e93  jle     short loc_140004E9E
0x140004e95  movzx   ebx, bx
0x140004e98  or      ebx, 80070000h
0x140004e9e  mov     esi, dword ptr [rbp+210h+pSMgrStatus.llSequenceNumber]
0x140004ea1  test    ebx, ebx
0x140004ea3  jns     short loc_140004EDD
0x140004ea5  cmp     ebx, 80070422h
0x140004eab  jz      short loc_140004EDD
0x140004ead  cmp     ebx, 800704ECh
0x140004eb3  jz      short loc_140004EDD
0x140004eb5  lea     r9, a0x08x; "0x%08x"
0x140004ebc  mov     dword ptr [rsp+310h+ppv], ebx
0x140004ec0  mov     r8d, 2013h; unsigned int
0x140004ec6  lea     rdx, c_wszEventSourceSystemRestore; "System Restore"
0x140004ecd  lea     rcx, [rsp+310h+var_2C8]; this
0x140004ed2  call    ?LogFailure@CSxFunctionTracer@@QEBAXPEBGK0ZZ; CSxFunctionTracer::LogFailure(ushort const *,ulong,ushort const *,...)
0x140004ed7  mov     [rsp+310h+var_2C8], ebx
0x140004edb  jmp     short loc_140004EE5
0x140004edd  mov     [rsp+310h+var_2C8], ebx
0x140004ee1  test    ebx, ebx
0x140004ee3  jns     short loc_140004EEF
0x140004ee5  mov     eax, 1AFh
0x140004eea  jmp     loc_140004B6A
0x140004eef  mov     eax, 1AFh
0x140004ef4  lea     r9, dword_140012F54; unsigned __int16 *
0x140004efb  mov     r8d, 2014h; unsigned int
0x140004f01  mov     [rsp+310h+var_2C4], ax
0x140004f06  lea     rdx, c_wszEventSourceSystemRestore; "System Restore"
0x140004f0d  lea     rcx, [rsp+310h+var_2C8]; this
0x140004f12  call    ?LogInfo@CSxFunctionTracer@@QEBAXPEBGK0ZZ; CSxFunctionTracer::LogInfo(ushort const *,ulong,ushort const *,...)
0x140004f17  mov     eax, 1B3h
0x140004f1c  mov     [rsp+310h+var_2C4], ax
0x140004f21  mov     [rsp+310h+var_2C8], r14d
0x140004f26  xor     edx, edx; pUnkOuter
0x140004f28  lea     rax, [rbp+210h+var_290]
  ... truncated ...
```
