# CCbsWorker::GetClassFactory(uint,IClassFactory * *)

- ea: `0x14000ade4`
- end: `0x14000af94`
- name: `?GetClassFactory@CCbsWorker@@UEAAJIPEAPEAUIClassFactory@@@Z`
- size: `432`
- prototype: `__int64 __fastcall(CCbsWorker *this, int, struct IClassFactory **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1400096b0`

## callees

- `0x140007758`
- `0x1400079e8`
- `0x140007eb8`
- `0x14000914c`
- `0x1400091d8`
- `0x14000ade4`
- `0x14000e328`
- `0x14002b010`

## string_xrefs

- `0x14000af69`: `Error: Not reversed from impersonation on func: %s`
- `0x14000aed7`: `TiWorker: Client requests SFP repair object.`
- `0x14000af2d`: `Failed to initialize WRP integrity check and repair.`
- `0x14000ae44`: `Unsupported hosted service type %d`

## pseudocode

```c
__int64 __fastcall CCbsWorker::GetClassFactory(CCbsWorker *this, int a2, struct IClassFactory **a3)
{
  unsigned int v6; // ebx
  const char *v7; // r9
  int v8; // edx
  int v9; // eax
  struct IClassFactory *v10; // rax
  struct IClassFactory *v11; // rcx
  struct IClassFactory *v12; // rax
  _BYTE v14[72]; // [rsp+30h] [rbp-48h] BYREF

  MonitoredCritSecLocker::MonitoredCritSecLocker((MonitoredCritSecLocker *)v14, (CCbsWorker *)((char *)this - 64));
  if ( !a3 )
  {
    v6 = -2147467261;
    v7 = "No class factory result specified";
    v8 = -2147467261;
LABEL_3:
    CBSWdsLog(0x4000000u, v8, (size_t *)1, v7);
    goto LABEL_24;
  }
  v6 = 0;
  if ( a2 == 1 )
  {
    CBSWdsLog(0x4000000u, 0, 0, "TiWorker: Client requests SFP repair object.");
    if ( vpCbsSessionClassFactory || (v9 = TiWorkerCoreInitialize(*((_DWORD *)this - 6)), v6 = v9, v9 >= 0) )
    {
      v12 = vpSFPIntegrityCheckAndRepairClassFactory;
      if ( !vpSFPIntegrityCheckAndRepairClassFactory )
      {
        v9 = TiSFPRepairInitialize();
        v6 = v9;
        if ( v9 < 0 )
        {
          v7 = "Failed to initialize WRP integrity check and repair.";
          goto LABEL_17;
        }
        v12 = vpSFPIntegrityCheckAndRepairClassFactory;
      }
      *a3 = v12;
      v11 = vpSFPIntegrityCheckAndRepairClassFactory;
      goto LABEL_23;
    }
LABEL_16:
    v7 = "Failed to initialize CBS class factory.";
    goto LABEL_17;
  }
  if ( a2 != 2 )
  {
    v6 = -2147467263;
    CBSWdsLog(0x4000000u, -2147467263, (size_t *)1, "Unsupported hosted service type %d", a2);
    goto LABEL_24;
  }
  CBSWdsLog(0x4000000u, 0, 0, "TiWorker: Client requests SxS store object.");
  if ( !vpCbsSessionClassFactory )
  {
    v9 = TiWorkerCoreInitialize(*((_DWORD *)this - 6));
    v6 = v9;
    if ( v9 < 0 )
      goto LABEL_16;
  }
  v10 = vpSxSStoreClassFactory;
  if ( !vpSxSStoreClassFactory )
  {
    v9 = TiSxsStoreInitialize();
    v6 = v9;
    if ( v9 < 0 )
    {
      v7 = "Failed to initialize SxS.";
LABEL_17:
      v8 = v9;
      goto LABEL_3;
    }
    v10 = vpSxSStoreClassFactory;
  }
  *a3 = v10;
  v11 = vpSxSStoreClassFactory;
LABEL_23:
  ((void (__fastcall *)(struct IClassFactory *))v11->lpVtbl->AddRef)(v11);
LABEL_24:
  if ( NtCurrentTeb()->IsImpersonating )
    CBSWdsLog(0x4000000u, 0, 0, "Error: Not reversed from impersonation on func: %s", "CCbsWorker::GetClassFactory");
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v14);
  return v6;
}

```

## disassembly

```asm
0x14000ade4  push    rbx
0x14000ade6  push    rsi
0x14000ade7  push    rdi
0x14000ade8  push    r14
0x14000adea  sub     rsp, 58h
0x14000adee  mov     edi, edx
0x14000adf0  mov     rsi, rcx
0x14000adf3  lea     rdx, [rcx-40h]; struct AutoMonitoredCritSec *
0x14000adf7  mov     r14, r8
0x14000adfa  lea     rcx, [rsp+78h+var_48]; this
0x14000adff  call    ??0MonitoredCritSecLocker@@QEAA@AEAVAutoMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(AutoMonitoredCritSec &,bool)
0x14000ae04  test    r14, r14
0x14000ae07  jnz     short loc_14000AE2E
0x14000ae09  mov     ebx, 80004003h
0x14000ae0e  lea     r9, aNoClassFactory; "No class factory result specified"
0x14000ae15  mov     edx, ebx
0x14000ae17  mov     edi, 4000000h
0x14000ae1c  mov     r8d, 1
0x14000ae22  mov     ecx, edi
0x14000ae24  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000ae29  jmp     loc_14000AF53
0x14000ae2e  xor     ebx, ebx
0x14000ae30  mov     eax, edi
0x14000ae32  sub     eax, 1
0x14000ae35  jz      loc_14000AED2
0x14000ae3b  cmp     eax, 1
0x14000ae3e  jz      short loc_14000AE69
0x14000ae40  mov     dword ptr [rsp+78h+var_58], edi
0x14000ae44  lea     r9, aUnsupportedHos; "Unsupported hosted service type %d"
0x14000ae4b  mov     edi, 4000000h
0x14000ae50  mov     ebx, 80004001h
0x14000ae55  mov     ecx, edi
0x14000ae57  mov     r8d, 1
0x14000ae5d  mov     edx, ebx
0x14000ae5f  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000ae64  jmp     loc_14000AF53
0x14000ae69  mov     edi, 4000000h
0x14000ae6e  lea     r9, aTiworkerClient_0; "TiWorker: Client requests SxS store obj"...
0x14000ae75  mov     ecx, edi
0x14000ae77  xor     r8d, r8d
0x14000ae7a  xor     edx, edx
0x14000ae7c  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000ae81  cmp     cs:?vpCbsSessionClassFactory@@3PEAUIClassFactory@@EA, rbx; IClassFactory * vpCbsSessionClassFactory
0x14000ae88  jnz     short loc_14000AE9F
0x14000ae8a  mov     ecx, [rsi-18h]
0x14000ae8d  lea     rdx, ?vpCbsSessionClassFactory@@3PEAUIClassFactory@@EA; IClassFactory * vpCbsSessionClassFactory
0x14000ae94  call    TiWorkerCoreInitialize
0x14000ae99  mov     ebx, eax
0x14000ae9b  test    eax, eax
0x14000ae9d  js      short loc_14000AF08
0x14000ae9f  mov     rax, cs:?vpSxSStoreClassFactory@@3PEAUIClassFactory@@EA; IClassFactory * vpSxSStoreClassFactory
0x14000aea6  test    rax, rax
0x14000aea9  jnz     short loc_14000AEC6
0x14000aeab  call    TiSxsStoreInitialize
0x14000aeb0  mov     ebx, eax
0x14000aeb2  test    eax, eax
0x14000aeb4  jns     short loc_14000AEBF
0x14000aeb6  lea     r9, aFailedToInitia_10; "Failed to initialize SxS."
0x14000aebd  jmp     short loc_14000AF0F
0x14000aebf  mov     rax, cs:?vpSxSStoreClassFactory@@3PEAUIClassFactory@@EA; IClassFactory * vpSxSStoreClassFactory
0x14000aec6  mov     [r14], rax
0x14000aec9  mov     rcx, cs:?vpSxSStoreClassFactory@@3PEAUIClassFactory@@EA; IClassFactory * vpSxSStoreClassFactory
0x14000aed0  jmp     short loc_14000AF47
0x14000aed2  mov     edi, 4000000h
0x14000aed7  lea     r9, aTiworkerClient; "TiWorker: Client requests SFP repair ob"...
0x14000aede  mov     ecx, edi
0x14000aee0  xor     r8d, r8d
0x14000aee3  xor     edx, edx
0x14000aee5  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000aeea  cmp     cs:?vpCbsSessionClassFactory@@3PEAUIClassFactory@@EA, rbx; IClassFactory * vpCbsSessionClassFactory
0x14000aef1  jnz     short loc_14000AF16
0x14000aef3  mov     ecx, [rsi-18h]
0x14000aef6  lea     rdx, ?vpCbsSessionClassFactory@@3PEAUIClassFactory@@EA; IClassFactory * vpCbsSessionClassFactory
0x14000aefd  call    TiWorkerCoreInitialize
0x14000af02  mov     ebx, eax
0x14000af04  test    eax, eax
0x14000af06  jns     short loc_14000AF16
0x14000af08  lea     r9, aFailedToInitia_8; "Failed to initialize CBS class factory."
0x14000af0f  mov     edx, eax
0x14000af11  jmp     loc_14000AE1C
0x14000af16  mov     rax, cs:?vpSFPIntegrityCheckAndRepairClassFactory@@3PEAUIClassFactory@@EA; IClassFactory * vpSFPIntegrityCheckAndRepairClassFactory
0x14000af1d  test    rax, rax
0x14000af20  jnz     short loc_14000AF3D
0x14000af22  call    TiSFPRepairInitialize
0x14000af27  mov     ebx, eax
0x14000af29  test    eax, eax
0x14000af2b  jns     short loc_14000AF36
0x14000af2d  lea     r9, aFailedToInitia_11; "Failed to initialize WRP integrity chec"...
0x14000af34  jmp     short loc_14000AF0F
0x14000af36  mov     rax, cs:?vpSFPIntegrityCheckAndRepairClassFactory@@3PEAUIClassFactory@@EA; IClassFactory * vpSFPIntegrityCheckAndRepairClassFactory
0x14000af3d  mov     [r14], rax
0x14000af40  mov     rcx, cs:?vpSFPIntegrityCheckAndRepairClassFactory@@3PEAUIClassFactory@@EA; IClassFactory * vpSFPIntegrityCheckAndRepairClassFactory
0x14000af47  mov     rax, [rcx]
0x14000af4a  mov     rax, [rax+8]
0x14000af4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000af53  mov     eax, gs:179Ch
0x14000af5b  test    eax, eax
0x14000af5d  jz      short loc_14000AF7E
0x14000af5f  lea     rax, aCcbsworkerGetc; "CCbsWorker::GetClassFactory"
0x14000af66  xor     r8d, r8d
0x14000af69  lea     r9, aErrorNotRevers; "Error: Not reversed from impersonation "...
0x14000af70  mov     [rsp+78h+var_58], rax
0x14000af75  xor     edx, edx
0x14000af77  mov     ecx, edi
0x14000af79  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000af7e  lea     rcx, [rsp+78h+var_48]; this
0x14000af83  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x14000af88  mov     eax, ebx
0x14000af8a  add     rsp, 58h
0x14000af8e  pop     r14
0x14000af90  pop     rdi
0x14000af91  pop     rsi
0x14000af92  pop     rbx
0x14000af93  retn
```
