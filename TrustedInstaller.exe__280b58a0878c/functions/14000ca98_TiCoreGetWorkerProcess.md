# TiCoreGetWorkerProcess

- ea: `0x14000ca98`
- end: `0x14000cd76`
- name: `TiCoreGetWorkerProcess`
- size: `734`
- prototype: `__int64 __fastcall(char, void **)`
- caller_count: `17`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000a3f8`
- `0x14000ca08`
- `0x14000cf8c`
- `0x14000d020`
- `0x14000d4d0`
- `0x14000d5c8`
- `0x14000dca8`
- `0x140012540`
- `0x1400127c8`
- `0x140014334`
- `0x140014d60`
- `0x14001503c`
- `0x140015644`
- `0x140015ad8`
- `0x140015b90`
- `0x1400160e4`
- `0x140016180`

## callees

- `0x140002070`
- `0x1400023e0`
- `0x140006344`
- `0x14000695c`
- `0x14000ca98`
- `0x140017658`
- `0x140020924`
- `0x140020ae8`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000cbba`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000cbba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000cbe2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000cbe2`

## string_xrefs

- `0x14000cb96`: `Failed to create CBS worker, crashed?`
- `0x14000cba2`: `Unable to create CBS worker - waiting for a second and trying again`
- `0x14000cb42`: `TI: It looks like TiWorker crashed, attempting to restart it. TI probably cannot autostop or be stopped due to an incorrect instance count.`

## pseudocode

```c
__int64 __fastcall TiCoreGetWorkerProcess(char a1, void **a2)
{
  const struct _GUID *v4; // rdx
  CCbsInprocIStream *v5; // rcx
  int v6; // ebx
  int v7; // eax
  char *v8; // rcx
  unsigned int i; // r14d
  HRESULT Instance; // eax
  int v11; // eax
  _QWORD *v12; // rax
  _QWORD *v13; // r8
  __int64 v14; // rax
  CCbsInprocIStream *v15; // rcx
  char *v16; // rcx
  _QWORD v18[3]; // [rsp+30h] [rbp-38h] BYREF
  struct IUnknown *ppv; // [rsp+48h] [rbp-20h] BYREF

  MonitoredCritSecLocker::MonitoredCritSecLocker((MonitoredCritSecLocker *)v18, (struct MonitoredCritSec *)&vTiLock, 1);
  ppv = 0;
  v18[0] = &TiCoreLocker::`vftable';
  if ( !a2 )
  {
    v6 = -2147024809;
    CBSWdsLogLight(0x4000000, 2147942487LL, 1, "No CBS worker result specified");
    goto LABEL_22;
  }
  if ( vpCbsWorkerStream )
  {
    v7 = CCbsInprocIStream::UnmarshalObject(v5, v4, a2);
    v6 = v7;
    if ( v7 >= 0 )
      goto LABEL_22;
    CBSWdsLogLight(0x4000000, (unsigned int)v7, 1, "Unable to unmarshall worker stream");
    if ( !a1 )
      goto LABEL_22;
    CBSWdsLogLight(
      0x4000000,
      0,
      0,
      "TI: It looks like TiWorker crashed, attempting to restart it. TI probably cannot autostop or be stopped due to an "
      "incorrect instance count.");
    if ( vpCbsWorkerStream )
    {
      v8 = (char *)vpCbsWorkerStream + *(int *)(*((_QWORD *)vpCbsWorkerStream + 1) + 4LL) + 8;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8);
      vpCbsWorkerStream = 0;
    }
  }
  for ( i = 0; ; ++i )
  {
    Instance = CoCreateInstance(&CLSID_CbsWorker, 0, 0x15u, &GUID_a70dbecc_3734_4b22_b2d1_648c0e43e177, (LPVOID *)&ppv);
    v6 = Instance;
    if ( Instance >= 0 )
      break;
    if ( i >= 0xA )
    {
      CBSWdsLogLight(0x4000000, (unsigned int)Instance, 1, "Failed to create CBS worker, crashed?");
      goto LABEL_22;
    }
    CBSWdsLogLight(
      0x4000000,
      (unsigned int)Instance,
      1,
      "Unable to create CBS worker - waiting for a second and trying again");
    Sleep(0x3E8u);
  }
  _InterlockedExchange(&vfTiWorkerShuttingDown, 0);
  v11 = ((__int64 (__fastcall *)(struct IUnknown *, char *, _QWORD))ppv->lpVtbl[1].QueryInterface)(
          ppv,
          (char *)&off_14003F050 + *(int *)&(*off_14003F050)[4],
          (unsigned int)vbEnsureNoStartupProcessing);
  v6 = v11;
  if ( v11 >= 0 )
  {
    v12 = operator new(0x30u);
    v13 = v12;
    if ( v12 )
    {
      v12[1] = CCbsInprocIStream::`vbtable';
      *v12 = &CCbsIUnknownImpl<IUnknown,>::`vftable'{for `CCbsIUnknownImpl<IUnknown,>'};
      v12[5] = &CCbsIUnknownImpl<IUnknown,>::`vftable'{for `IUnknown'};
      *((_DWORD *)v12 + 9) = 8;
      *v12 = &CCbsInprocIStream::`vftable'{for `CCbsIUnknownImpl<IUnknown,>'};
      v14 = v12[1];
      *((_DWORD *)v13 + 4) = 1;
      *(_QWORD *)((char *)v13 + *(int *)(v14 + 4) + 8) = &CCbsInprocIStream::`vftable'{for `IUnknown'};
      v15 = (CCbsInprocIStream *)*(int *)(v13[1] + 4LL);
      *(_DWORD *)((char *)v13 + (_QWORD)v15 + 4) = 0;
      v13[3] = 0;
      vpCbsWorkerStream = (struct CCbsInprocIStream *)v13;
      v6 = CCbsInprocIStream::MarshalObject(v15, (const struct _GUID *)8, ppv);
      if ( v6 >= 0 )
      {
        *a2 = ppv;
LABEL_24:
        ppv = 0;
        goto LABEL_25;
      }
      if ( vpCbsWorkerStream )
      {
        v16 = (char *)vpCbsWorkerStream + *(int *)(*((_QWORD *)vpCbsWorkerStream + 1) + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 16LL))(v16);
        vpCbsWorkerStream = 0;
      }
      CBSWdsLogLight(0x4000000, (unsigned int)v6, 1, "Failed to marshall worker process");
    }
    else
    {
      vpCbsWorkerStream = 0;
      v6 = -2147024882;
      CBSWdsLogLight(0x4000000, 2147942414LL, 1, "Failed to allocate worker stream");
    }
  }
  else
  {
    CBSWdsLogLight(0x4000000, (unsigned int)v11, 1, "Failed to initialize TiWorker.");
  }
LABEL_22:
  if ( ppv )
  {
    ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
    goto LABEL_24;
  }
LABEL_25:
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v18);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000ca98  push    rbp
0x14000ca9a  push    rbx
0x14000ca9b  push    rsi
0x14000ca9c  push    rdi
0x14000ca9d  push    r12
0x14000ca9f  push    r14
0x14000caa1  mov     rbp, rsp
0x14000caa4  sub     rsp, 68h
0x14000caa8  mov     rax, cs:__security_cookie
0x14000caaf  xor     rax, rsp
0x14000cab2  mov     [rbp+var_18], rax
0x14000cab6  mov     rsi, rdx
0x14000cab9  mov     r14b, cl
0x14000cabc  mov     r12d, 1
0x14000cac2  lea     rdx, vTiLock; struct MonitoredCritSec *
0x14000cac9  mov     r8b, r12b; bool
0x14000cacc  lea     rcx, [rbp+var_38]; this
0x14000cad0  call    ??0MonitoredCritSecLocker@@QEAA@AEAUMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(MonitoredCritSec &,bool)
0x14000cad5  mov     [rbp+var_20], 0
0x14000cadd  lea     rax, ??_7TiCoreLocker@@6B@; const TiCoreLocker::`vftable'
0x14000cae4  mov     [rbp+var_38], rax
0x14000cae8  test    rsi, rsi
0x14000caeb  jnz     short loc_14000CB03
0x14000caed  mov     ebx, 80070057h
0x14000caf2  lea     r9, aNoCbsWorkerRes; "No CBS worker result specified"
0x14000caf9  mov     ecx, 4000000h
0x14000cafe  jmp     loc_14000CD2B
0x14000cb03  mov     rax, cs:?vpCbsWorkerStream@@3PEAVCCbsInprocIStream@@EA; CCbsInprocIStream * vpCbsWorkerStream
0x14000cb0a  mov     edi, 4000000h
0x14000cb0f  test    rax, rax
0x14000cb12  jz      short loc_14000CB87
0x14000cb14  mov     r8, rsi; void **
0x14000cb17  call    ?UnmarshalObject@CCbsInprocIStream@@QEAAJAEBU_GUID@@PEAPEAX@Z; CCbsInprocIStream::UnmarshalObject(_GUID const &,void * *)
0x14000cb1c  mov     ebx, eax
0x14000cb1e  test    eax, eax
0x14000cb20  jns     loc_14000CD35
0x14000cb26  lea     r9, aUnableToUnmars; "Unable to unmarshall worker stream"
0x14000cb2d  mov     r8d, r12d
0x14000cb30  mov     edx, eax
0x14000cb32  mov     ecx, edi
0x14000cb34  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000cb39  test    r14b, r14b
0x14000cb3c  jz      loc_14000CD35
0x14000cb42  lea     r9, aTiItLooksLikeT; "TI: It looks like TiWorker crashed, att"...
0x14000cb49  xor     r8d, r8d
0x14000cb4c  xor     edx, edx
0x14000cb4e  mov     ecx, edi
0x14000cb50  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000cb55  mov     rdx, cs:?vpCbsWorkerStream@@3PEAVCCbsInprocIStream@@EA; CCbsInprocIStream * vpCbsWorkerStream
0x14000cb5c  test    rdx, rdx
0x14000cb5f  jz      short loc_14000CB87
0x14000cb61  mov     rax, [rdx+8]
0x14000cb65  add     rdx, 8
0x14000cb69  movsxd  rcx, dword ptr [rax+4]
0x14000cb6d  add     rcx, rdx
0x14000cb70  mov     rax, [rcx]
0x14000cb73  mov     rax, [rax+10h]
0x14000cb77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cb7c  mov     cs:?vpCbsWorkerStream@@3PEAVCCbsInprocIStream@@EA, 0; CCbsInprocIStream * vpCbsWorkerStream
0x14000cb87  xor     r14d, r14d
0x14000cb8a  jmp     short loc_14000CBC3
0x14000cb8c  cmp     r14d, 0Ah
0x14000cb90  jb      short loc_14000CBA2
0x14000cb92  test    ebx, ebx
0x14000cb94  jns     short loc_14000CBB5
0x14000cb96  lea     r9, aFailedToCreate_0; "Failed to create CBS worker, crashed?"
0x14000cb9d  jmp     loc_14000CD29
0x14000cba2  lea     r9, aUnableToCreate; "Unable to create CBS worker - waiting f"...
0x14000cba9  mov     r8d, r12d
0x14000cbac  mov     edx, ebx
0x14000cbae  mov     ecx, edi
0x14000cbb0  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000cbb5  mov     ecx, 3E8h; dwMilliseconds
0x14000cbba  call    cs:__imp_Sleep
0x14000cbc0  add     r14d, r12d
0x14000cbc3  lea     rax, [rbp+var_20]
0x14000cbc7  mov     r8d, 15h; dwClsContext
0x14000cbcd  lea     r9, _GUID_a70dbecc_3734_4b22_b2d1_648c0e43e177; riid
0x14000cbd4  mov     [rsp+68h+ppv], rax; ppv
0x14000cbd9  xor     edx, edx; pUnkOuter
0x14000cbdb  lea     rcx, CLSID_CbsWorker; rclsid
0x14000cbe2  call    cs:__imp_CoCreateInstance
0x14000cbe8  mov     ebx, eax
0x14000cbea  test    eax, eax
0x14000cbec  js      short loc_14000CB8C
0x14000cbee  xor     eax, eax
0x14000cbf0  xchg    eax, cs:?vfTiWorkerShuttingDown@@3JA; long vfTiWorkerShuttingDown
0x14000cbf6  mov     rax, cs:off_14003F050
0x14000cbfd  mov     rcx, [rbp+var_20]
0x14000cc01  mov     r8d, cs:?vbEnsureNoStartupProcessing@@3HA; int vbEnsureNoStartupProcessing
0x14000cc08  movsxd  rdx, dword ptr [rax+4]
0x14000cc0c  lea     rax, off_14003F050
0x14000cc13  mov     r9, [rcx]
0x14000cc16  add     rdx, rax
0x14000cc19  mov     rax, [r9+18h]
0x14000cc1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc22  mov     ebx, eax
0x14000cc24  test    eax, eax
0x14000cc26  jns     short loc_14000CC38
0x14000cc28  lea     r9, aFailedToInitia_0; "Failed to initialize TiWorker."
0x14000cc2f  mov     edx, eax
0x14000cc31  mov     ecx, edi
0x14000cc33  jmp     loc_14000CD2D
0x14000cc38  mov     ecx, 30h ; '0'; Size
0x14000cc3d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000cc42  mov     r8, rax
0x14000cc45  test    rax, rax
0x14000cc48  jz      loc_14000CD12
0x14000cc4e  lea     rax, ??_8CCbsInprocIStream@@7B@; const CCbsInprocIStream::`vbtable'
0x14000cc55  mov     [r8+8], rax
0x14000cc59  lea     rax, ??_7?$CCbsIUnknownImpl@UIUnknown@@$$V@@6B0@@; const CCbsIUnknownImpl<IUnknown,>::`vftable'{for `CCbsIUnknownImpl<IUnknown,>'}
0x14000cc60  mov     [r8], rax
0x14000cc63  lea     rax, ??_7?$CCbsIUnknownImpl@UIUnknown@@$$V@@6BIUnknown@@@; const CCbsIUnknownImpl<IUnknown,>::`vftable'{for `IUnknown'}
0x14000cc6a  mov     [r8+28h], rax
0x14000cc6e  lea     rax, ??_7CCbsInprocIStream@@6B?$CCbsIUnknownImpl@UIUnknown@@$$V@@@; const CCbsInprocIStream::`vftable'{for `CCbsIUnknownImpl<IUnknown,>'}
0x14000cc75  movsxd  rcx, cs:dword_14003272C
0x14000cc7c  lea     edx, [rcx-18h]; struct _GUID *
0x14000cc7f  mov     [rcx+r8+4], edx
0x14000cc84  mov     [r8], rax
0x14000cc87  mov     rax, [r8+8]
0x14000cc8b  mov     [r8+10h], r12d
0x14000cc8f  movsxd  rcx, dword ptr [rax+4]
0x14000cc93  lea     rax, ??_7CCbsInprocIStream@@6BIUnknown@@@; const CCbsInprocIStream::`vftable'{for `IUnknown'}
0x14000cc9a  mov     [rcx+r8+8], rax
0x14000cc9f  mov     rax, [r8+8]
0x14000cca3  movsxd  rcx, dword ptr [rax+4]; this
0x14000cca7  mov     dword ptr [rcx+r8+4], 0
0x14000ccb0  mov     qword ptr [r8+18h], 0
0x14000ccb8  mov     cs:?vpCbsWorkerStream@@3PEAVCCbsInprocIStream@@EA, r8; CCbsInprocIStream * vpCbsWorkerStream
0x14000ccbf  mov     r8, [rbp+var_20]; struct IUnknown *
0x14000ccc3  call    ?MarshalObject@CCbsInprocIStream@@QEAAJAEBU_GUID@@PEAUIUnknown@@@Z; CCbsInprocIStream::MarshalObject(_GUID const &,IUnknown *)
0x14000ccc8  mov     ebx, eax
0x14000ccca  test    eax, eax
0x14000cccc  jns     short loc_14000CD09
0x14000ccce  mov     rdx, cs:?vpCbsWorkerStream@@3PEAVCCbsInprocIStream@@EA; CCbsInprocIStream * vpCbsWorkerStream
0x14000ccd5  test    rdx, rdx
0x14000ccd8  jz      short loc_14000CD00
0x14000ccda  mov     rax, [rdx+8]
0x14000ccde  add     rdx, 8
0x14000cce2  movsxd  rcx, dword ptr [rax+4]
0x14000cce6  add     rcx, rdx
0x14000cce9  mov     rax, [rcx]
0x14000ccec  mov     rax, [rax+10h]
0x14000ccf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ccf5  mov     cs:?vpCbsWorkerStream@@3PEAVCCbsInprocIStream@@EA, 0; CCbsInprocIStream * vpCbsWorkerStream
0x14000cd00  lea     r9, aFailedToMarsha; "Failed to marshall worker process"
0x14000cd07  jmp     short loc_14000CD29
0x14000cd09  mov     rax, [rbp+var_20]
0x14000cd0d  mov     [rsi], rax
0x14000cd10  jmp     short loc_14000CD4A
0x14000cd12  mov     cs:?vpCbsWorkerStream@@3PEAVCCbsInprocIStream@@EA, 0; CCbsInprocIStream * vpCbsWorkerStream
0x14000cd1d  lea     r9, aFailedToAlloca_12; "Failed to allocate worker stream"
0x14000cd24  mov     ebx, 8007000Eh
0x14000cd29  mov     ecx, edi
0x14000cd2b  mov     edx, ebx
0x14000cd2d  mov     r8d, r12d
0x14000cd30  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000cd35  mov     rcx, [rbp+var_20]
0x14000cd39  test    rcx, rcx
0x14000cd3c  jz      short loc_14000CD52
0x14000cd3e  mov     rax, [rcx]
0x14000cd41  mov     rax, [rax+10h]
0x14000cd45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cd4a  mov     [rbp+var_20], 0
0x14000cd52  lea     rcx, [rbp+var_38]; this
0x14000cd56  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x14000cd5b  mov     eax, ebx
0x14000cd5d  mov     rcx, [rbp+var_18]
0x14000cd61  xor     rcx, rsp; StackCookie
0x14000cd64  call    __security_check_cookie
0x14000cd69  add     rsp, 68h
0x14000cd6d  pop     r14
0x14000cd6f  pop     r12
0x14000cd71  pop     rdi
0x14000cd72  pop     rsi
0x14000cd73  pop     rbx
0x14000cd74  pop     rbp
0x14000cd75  retn
```
