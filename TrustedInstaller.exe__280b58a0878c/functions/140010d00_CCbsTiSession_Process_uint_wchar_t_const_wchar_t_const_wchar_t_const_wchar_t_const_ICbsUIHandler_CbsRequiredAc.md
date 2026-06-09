# CCbsTiSession::Process(uint,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,ICbsUIHandler *,_CbsRequiredAction *,wchar_t * *)

- ea: `0x140010d00`
- end: `0x14001110d`
- name: `?Process@CCbsTiSession@@UEAAJIPEB_W000PEAUICbsUIHandler@@PEAW4_CbsRequiredAction@@PEAPEA_W@Z`
- size: `1037`
- prototype: `__int64 __fastcall(CCbsTiSession *this, unsigned int, const wchar_t *, const wchar_t *, const wchar_t *, wchar_t *, struct ICbsUIHandler *, enum _CbsRequiredAction *, wchar_t **)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140002070`
- `0x1400023e0`
- `0x140006778`
- `0x140007630`
- `0x14000dca8`
- `0x14000e180`
- `0x14000e2ac`
- `0x14000ee64`
- `0x14000ee94`
- `0x140010d00`
- `0x140011e34`
- `0x14001503c`
- `0x140017658`
- `0x14001ee54`
- `0x14002b010`

## string_xrefs

- `0x14001109b`: `Failed to resume the session after servicing stack update.`
- `0x140010e69`: `Failed to create worker session.`
- `0x140010d7e`: `Invalid argument: szActionListPath.`
- `0x140010da6`: `Invalid argument: szSandboxPath.`
- `0x140010ea4`: `Failed to get directory`
- `0x140011038`: `A servicing stack update was installed on its own via IServicingProcessor::Process.  We need another download/install to get the LCU`

## pseudocode

```c
__int64 __fastcall CCbsTiSession::Process(
        CCbsTiSession *this,
        unsigned int a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        wchar_t *a6,
        struct ICbsUIHandler *a7,
        enum _CbsRequiredAction *a8,
        wchar_t **a9)
{
  wchar_t *v10; // rbx
  const char *v12; // r9
  __int64 v13; // rdx
  unsigned int v14; // edi
  char *v15; // rcx
  int v16; // eax
  CCbsTiSessionUIHandler *v17; // rax
  CCbsTiSessionUIHandler *v18; // rax
  _QWORD *v19; // r15
  int WorkerSession; // eax
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rdx
  int v24; // eax
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64); // rbx
  __int64 InitPointer; // rax
  int v27; // ecx
  __int64 v28; // rcx
  bool v30; // [rsp+50h] [rbp-61h] BYREF
  unsigned int v31; // [rsp+54h] [rbp-5Dh]
  wchar_t *v32; // [rsp+58h] [rbp-59h] BYREF
  wchar_t **v33; // [rsp+60h] [rbp-51h]
  const wchar_t *v34; // [rsp+68h] [rbp-49h]
  const wchar_t *v35; // [rsp+70h] [rbp-41h]
  const wchar_t *v36; // [rsp+78h] [rbp-39h]
  _BYTE v37[24]; // [rsp+80h] [rbp-31h] BYREF
  __int64 v38; // [rsp+98h] [rbp-19h] BYREF

  v10 = 0;
  v31 = a2;
  v35 = a3;
  v36 = a4;
  v34 = a5;
  v33 = a9;
  v38 = 0;
  v32 = 0;
  CritSecLocker::CritSecLocker((CritSecLocker *)v37, (CCbsTiSession *)((char *)this + 48), 1);
  if ( !v35 )
  {
    v12 = "Invalid argument: szActionListPath.";
LABEL_3:
    v13 = 2147500035LL;
    v14 = -2147467261;
LABEL_4:
    CBSWdsLogLight(0x4000000, v13, 1, v12);
    goto LABEL_54;
  }
  if ( !a4 )
  {
    v12 = "Invalid argument: szSandboxPath.";
    goto LABEL_3;
  }
  if ( !a5 )
  {
    v12 = "Invalid argument: szClientID.";
    goto LABEL_3;
  }
  if ( !a8 )
  {
    v12 = "Invalid argument: requiredAction.";
    goto LABEL_3;
  }
  if ( !v33 )
  {
    v12 = "Invalid argument: pszSessionID.";
    goto LABEL_3;
  }
  if ( a7 )
  {
    v15 = (char *)this + *(int *)(*((_QWORD *)this + 2) + 4LL) + 16;
    v16 = (*(__int64 (__fastcall **)(char *, struct ICbsUIHandler *))(*(_QWORD *)v15 + 128LL))(v15, a7);
    if ( v16 < 0 )
      CBSWdsLogLight(0x4000000, (unsigned int)v16, 1, "Not able to set CbsHandler");
  }
  v17 = (CCbsTiSessionUIHandler *)*((_QWORD *)this + 11);
  if ( !v17 )
  {
    v18 = (CCbsTiSessionUIHandler *)operator new(0x58u);
    if ( v18 )
    {
      v17 = CCbsTiSessionUIHandler::CCbsTiSessionUIHandler(v18);
      *((_QWORD *)this + 11) = v17;
      if ( v17 )
        goto LABEL_19;
    }
    else
    {
      *((_QWORD *)this + 11) = 0;
    }
    v14 = -2147024882;
    v12 = "Failed to allocate new Ti UIHandler";
    v13 = 2147942414LL;
    goto LABEL_4;
  }
LABEL_19:
  v19 = (_QWORD *)((char *)this + 40);
  *((_QWORD *)v17 + 5) = this;
  if ( !*((_QWORD *)this + 5) )
  {
    WorkerSession = CCbsPublicSessionClassFactory::CreateWorkerSession(
                      *((CCbsPublicSessionClassFactory **)this + 4),
                      (struct ICbsSession10 **)this + 5);
    v14 = WorkerSession;
    if ( WorkerSession < 0 )
    {
      v12 = "Failed to create worker session.";
LABEL_22:
      v13 = (unsigned int)WorkerSession;
      goto LABEL_4;
    }
    if ( a6 )
    {
      WorkerSession = DirectoryFromPath(a6, &v32);
      v14 = WorkerSession;
      if ( WorkerSession < 0 )
      {
        v12 = "Failed to get directory";
        goto LABEL_22;
      }
      v10 = v32;
    }
    v21 = (unsigned __int8)(v31 & 2) << 24;
    LODWORD(v21) = v21 | 0x100;
    if ( (v31 & 4) == 0 )
      v21 = (unsigned __int8)(v31 & 2) << 24;
    WorkerSession = (*(__int64 (__fastcall **)(_QWORD, __int64, const wchar_t *, wchar_t *, wchar_t *, _QWORD))(*(_QWORD *)*v19 + 152LL))(
                      *v19,
                      v21,
                      v34,
                      v10,
                      a6,
                      0);
    v14 = WorkerSession;
    if ( WorkerSession < 0 )
    {
      v12 = "Failed to initialize CBS session.";
      goto LABEL_22;
    }
  }
  WorkerSession = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v19 + 88LL))(*v19, (char *)this + 104);
  v14 = WorkerSession;
  if ( WorkerSession < 0 )
  {
    v12 = "Failed to get session ID.";
    goto LABEL_22;
  }
  v22 = *((_QWORD *)this + 11);
  if ( v22 )
    v23 = v22 + *(int *)(*(_QWORD *)(v22 + 8) + 4LL) + 8LL;
  else
    v23 = 0;
  v24 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v19 + 128LL))(*v19, v23);
  if ( v24 < 0 )
    CBSWdsLogLight(0x4000000, (unsigned int)v24, 1, "Not able to set CbsHandler");
  v25 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*v19;
  InitPointer = Windows::AutoComPtr<IClassFactory>::GetInitPointer(&v38);
  WorkerSession = (**v25)(v25, &GUID_be996087_7c81_465a_9bb1_39ce7350adcd, InitPointer);
  v14 = WorkerSession;
  if ( WorkerSession < 0 )
  {
    v12 = "Failed to query servicing processor";
    goto LABEL_22;
  }
  WorkerSession = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, const wchar_t *, const wchar_t *, wchar_t *, _QWORD, enum _CbsRequiredAction *, wchar_t **))(*(_QWORD *)v38 + 24LL))(
                    v38,
                    v31,
                    v35,
                    v36,
                    v34,
                    a6,
                    0,
                    a8,
                    v33);
  v14 = WorkerSession;
  if ( WorkerSession < 0 )
  {
    v12 = "Failed to call Process on TiWorker session";
    goto LABEL_22;
  }
  v27 = *(_DWORD *)(*((_QWORD *)this + 11) + 48LL);
  if ( v27 == 985091 )
  {
    Windows::AutoComPtr<ICbsServicingProcessor>::Close(&v38);
    if ( *v19 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 16LL))(*v19);
      *v19 = 0;
    }
    WaitForTiWorkerToShutdown();
    CBSWdsLogLight(
      0x4000000,
      0,
      0,
      "A servicing stack update was installed on its own via IServicingProcessor::Process.  We need another download/inst"
      "all to get the LCU");
    v14 = -2145116147;
  }
  else if ( v27 == 985139 )
  {
    Windows::AutoComPtr<ICbsServicingProcessor>::Close(&v38);
    if ( *v19 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 16LL))(*v19);
      *v19 = 0;
    }
    WaitForTiWorkerToShutdown();
    v30 = 0;
    WorkerSession = CCbsTiSession::ResumeSession(this, 0, &v30);
    v14 = WorkerSession;
    if ( WorkerSession < 0 )
    {
      v12 = "Failed to resume the session after servicing stack update.";
      goto LABEL_22;
    }
    *(_DWORD *)a8 = v30;
  }
LABEL_54:
  v28 = *((_QWORD *)this + 5);
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    *((_QWORD *)this + 5) = 0;
  }
  CritSecLocker::~CritSecLocker((CritSecLocker *)v37);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v32);
  Windows::AutoComPtr<ICbsServicingProcessor>::Close(&v38);
  return v14;
}

```

## disassembly

```asm
0x140010d00  push    rbp
0x140010d02  push    rbx
0x140010d03  push    rsi
0x140010d04  push    rdi
0x140010d05  push    r12
0x140010d07  push    r13
0x140010d09  push    r14
0x140010d0b  push    r15
0x140010d0d  lea     rbp, [rsp-7]
0x140010d12  sub     rsp, 0B8h
0x140010d19  mov     rax, cs:__security_cookie
0x140010d20  xor     rax, rsp
0x140010d23  mov     [rbp+3Fh+var_50], rax
0x140010d27  mov     rax, [rbp+3Fh+arg_40]
0x140010d2e  mov     r14, rcx
0x140010d31  mov     rsi, [rbp+3Fh+arg_20]
0x140010d35  xor     ebx, ebx
0x140010d37  mov     r12, [rbp+3Fh+arg_28]
0x140010d3b  mov     r15, r9
0x140010d3e  mov     rdi, [rbp+3Fh+arg_30]
0x140010d42  mov     r13, [rbp+3Fh+arg_38]
0x140010d49  mov     [rbp+3Fh+var_9C], edx
0x140010d4c  lea     rdx, [rcx+30h]; struct AutoCritSec *
0x140010d50  mov     [rbp+3Fh+var_80], r8
0x140010d54  lea     rcx, [rbp+3Fh+var_70]; this
0x140010d58  mov     r8b, 1; bool
0x140010d5b  mov     [rbp+3Fh+var_78], r9
0x140010d5f  mov     [rbp+3Fh+var_88], rsi
0x140010d63  mov     [rbp+3Fh+var_90], rax
0x140010d67  mov     [rbp+3Fh+var_58], 0
0x140010d6f  mov     [rbp+3Fh+var_98], rbx
0x140010d73  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x140010d78  cmp     [rbp+3Fh+var_80], rbx
0x140010d7c  jnz     short loc_140010DA1
0x140010d7e  lea     r9, aInvalidArgumen_34; "Invalid argument: szActionListPath."
0x140010d85  mov     edx, 80004003h
0x140010d8a  mov     ecx, 4000000h
0x140010d8f  mov     edi, edx
0x140010d91  mov     r8d, 1
0x140010d97  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140010d9c  jmp     loc_1400110B3
0x140010da1  test    r15, r15
0x140010da4  jnz     short loc_140010DAF
0x140010da6  lea     r9, aInvalidArgumen_9; "Invalid argument: szSandboxPath."
0x140010dad  jmp     short loc_140010D85
0x140010daf  test    rsi, rsi
0x140010db2  jnz     short loc_140010DBD
0x140010db4  lea     r9, aInvalidArgumen_20; "Invalid argument: szClientID."
0x140010dbb  jmp     short loc_140010D85
0x140010dbd  test    r13, r13
0x140010dc0  jnz     short loc_140010DCB
0x140010dc2  lea     r9, aInvalidArgumen_21; "Invalid argument: requiredAction."
0x140010dc9  jmp     short loc_140010D85
0x140010dcb  cmp     [rbp+3Fh+var_90], rbx
0x140010dcf  jnz     short loc_140010DDA
0x140010dd1  lea     r9, aInvalidArgumen_16; "Invalid argument: pszSessionID."
0x140010dd8  jmp     short loc_140010D85
0x140010dda  mov     esi, 4000000h
0x140010ddf  test    rdi, rdi
0x140010de2  jz      short loc_140010E1F
0x140010de4  mov     rax, [r14+10h]
0x140010de8  mov     rdx, rdi
0x140010deb  movsxd  rcx, dword ptr [rax+4]
0x140010def  add     rcx, 10h
0x140010df3  add     rcx, r14
0x140010df6  mov     rax, [rcx]
0x140010df9  mov     rax, [rax+80h]
0x140010e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010e05  test    eax, eax
0x140010e07  jns     short loc_140010E1F
0x140010e09  lea     r9, aNotAbleToSetCb; "Not able to set CbsHandler"
0x140010e10  mov     r8d, 1
0x140010e16  mov     edx, eax
0x140010e18  mov     ecx, esi
0x140010e1a  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140010e1f  mov     rax, [r14+58h]
0x140010e23  test    rax, rax
0x140010e26  jnz     short loc_140010E46
0x140010e28  lea     ecx, [rax+58h]; Size
0x140010e2b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140010e30  test    rax, rax
0x140010e33  jz      short loc_140010E74
0x140010e35  mov     rcx, rax; this
0x140010e38  call    ??0CCbsTiSessionUIHandler@@QEAA@XZ; CCbsTiSessionUIHandler::CCbsTiSessionUIHandler(void)
0x140010e3d  mov     [r14+58h], rax
0x140010e41  test    rax, rax
0x140010e44  jz      short loc_140010E78
0x140010e46  lea     r15, [r14+28h]
0x140010e4a  mov     [rax+28h], r14
0x140010e4e  cmp     [r15], rbx
0x140010e51  jnz     loc_140010F05
0x140010e57  mov     rcx, [r14+20h]; this
0x140010e5b  mov     rdx, r15; struct ICbsSession10 **
0x140010e5e  call    ?CreateWorkerSession@CCbsPublicSessionClassFactory@@QEAAJPEAPEAUICbsSession10@@@Z; CCbsPublicSessionClassFactory::CreateWorkerSession(ICbsSession10 * *)
0x140010e63  mov     edi, eax
0x140010e65  test    eax, eax
0x140010e67  jns     short loc_140010E8D
0x140010e69  lea     r9, aFailedToCreate_18; "Failed to create worker session."
0x140010e70  mov     edx, eax
0x140010e72  jmp     short loc_140010E86
0x140010e74  mov     [r14+58h], rbx
0x140010e78  mov     edi, 8007000Eh
0x140010e7d  lea     r9, aFailedToAlloca; "Failed to allocate new Ti UIHandler"
0x140010e84  mov     edx, edi
0x140010e86  mov     ecx, esi
0x140010e88  jmp     loc_140010D91
0x140010e8d  test    r12, r12
0x140010e90  jz      short loc_140010EB1
0x140010e92  lea     rdx, [rbp+3Fh+var_98]
0x140010e96  mov     rcx, r12; wchar_t *
0x140010e99  call    DirectoryFromPath
0x140010e9e  mov     edi, eax
0x140010ea0  test    eax, eax
0x140010ea2  jns     short loc_140010EAD
0x140010ea4  lea     r9, aFailedToGetDir; "Failed to get directory"
0x140010eab  jmp     short loc_140010E70
0x140010ead  mov     rbx, [rbp+3Fh+var_98]
0x140010eb1  mov     r8d, [rbp+3Fh+var_9C]
0x140010eb5  mov     r9, rbx
0x140010eb8  mov     rcx, [r15]
0x140010ebb  and     r8d, 2
0x140010ebf  shl     r8d, 18h
0x140010ec3  mov     edx, r8d
0x140010ec6  mov     [rsp+0F0h+var_C8], 0
0x140010ecf  bts     edx, 8
0x140010ed3  mov     [rsp+0F0h+var_D0], r12
0x140010ed8  mov     r10, [rcx]
0x140010edb  test    byte ptr [rbp+3Fh+var_9C], 4
0x140010edf  cmovz   edx, r8d
0x140010ee3  mov     r8, [rbp+3Fh+var_88]
0x140010ee7  mov     rax, [r10+98h]
0x140010eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010ef3  mov     edi, eax
0x140010ef5  test    eax, eax
0x140010ef7  jns     short loc_140010F05
0x140010ef9  lea     r9, aFailedToInitia_3; "Failed to initialize CBS session."
0x140010f00  jmp     loc_140010E70
0x140010f05  mov     rcx, [r15]
0x140010f08  lea     rdx, [r14+68h]
0x140010f0c  mov     rax, [rcx]
0x140010f0f  mov     rax, [rax+58h]
0x140010f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010f18  mov     edi, eax
0x140010f1a  test    eax, eax
0x140010f1c  jns     short loc_140010F2A
0x140010f1e  lea     r9, aFailedToGetSes; "Failed to get session ID."
0x140010f25  jmp     loc_140010E70
0x140010f2a  mov     rcx, [r15]
0x140010f2d  mov     rax, [rcx]
0x140010f30  mov     r9, [rax+80h]
0x140010f37  mov     rax, [r14+58h]
0x140010f3b  test    rax, rax
0x140010f3e  jnz     short loc_140010F44
0x140010f40  xor     edx, edx
0x140010f42  jmp     short loc_140010F53
0x140010f44  mov     rdx, [rax+8]
0x140010f48  movsxd  rdx, dword ptr [rdx+4]
0x140010f4c  add     rdx, 8
0x140010f50  add     rdx, rax
0x140010f53  mov     rax, r9
0x140010f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010f5b  test    eax, eax
0x140010f5d  jns     short loc_140010F75
0x140010f5f  lea     r9, aNotAbleToSetCb; "Not able to set CbsHandler"
0x140010f66  mov     r8d, 1
0x140010f6c  mov     edx, eax
0x140010f6e  mov     ecx, esi
0x140010f70  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140010f75  mov     rbx, [r15]
0x140010f78  lea     rcx, [rbp+3Fh+var_58]
0x140010f7c  call    ?GetInitPointer@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAPEAPEAUIClassFactory@@XZ; Windows::AutoComPtr<IClassFactory>::GetInitPointer(void)
0x140010f81  mov     rdx, [rbx]
0x140010f84  mov     r8, rax
0x140010f87  mov     rcx, rbx
0x140010f8a  mov     r9, [rdx]
0x140010f8d  lea     rdx, _GUID_be996087_7c81_465a_9bb1_39ce7350adcd
0x140010f94  mov     rax, r9
0x140010f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010f9c  mov     edi, eax
0x140010f9e  test    eax, eax
0x140010fa0  jns     short loc_140010FAE
0x140010fa2  lea     r9, aFailedToQueryS_0; "Failed to query servicing processor"
0x140010fa9  jmp     loc_140010E70
0x140010fae  mov     rcx, [rbp+3Fh+var_58]
0x140010fb2  mov     r9, [rbp+3Fh+var_90]
0x140010fb6  mov     r10, [rbp+3Fh+var_88]
0x140010fba  mov     r8, [rbp+3Fh+var_80]
0x140010fbe  mov     rax, [rcx]
0x140010fc1  mov     edx, [rbp+3Fh+var_9C]
0x140010fc4  mov     [rsp+0F0h+var_B0], r9
0x140010fc9  mov     r9, [rbp+3Fh+var_78]
0x140010fcd  mov     rax, [rax+18h]
0x140010fd1  mov     [rsp+0F0h+var_B8], r13
0x140010fd6  mov     [rsp+0F0h+var_C0], 0
0x140010fdf  mov     [rsp+0F0h+var_C8], r12
0x140010fe4  mov     [rsp+0F0h+var_D0], r10
0x140010fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010fee  mov     edi, eax
0x140010ff0  test    eax, eax
0x140010ff2  jns     short loc_140011000
0x140010ff4  lea     r9, aFailedToCallPr; "Failed to call Process on TiWorker sess"...
0x140010ffb  jmp     loc_140010E70
0x140011000  mov     rax, [r14+58h]
0x140011004  mov     ecx, [rax+30h]
0x140011007  cmp     ecx, 0F0803h
0x14001100d  jnz     short loc_140011052
0x14001100f  lea     rcx, [rbp+3Fh+var_58]
0x140011013  call    ?Close@?$AutoComPtr@UICbsServicingProcessor@@@Windows@@QEAAXXZ; Windows::AutoComPtr<ICbsServicingProcessor>::Close(void)
0x140011018  mov     rcx, [r15]
0x14001101b  test    rcx, rcx
0x14001101e  jz      short loc_140011033
0x140011020  mov     rax, [rcx]
0x140011023  mov     rax, [rax+10h]
0x140011027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001102c  mov     qword ptr [r15], 0
0x140011033  call    WaitForTiWorkerToShutdown
0x140011038  lea     r9, aAServicingStac; "A servicing stack update was installed "...
0x14001103f  xor     r8d, r8d
0x140011042  xor     edx, edx
0x140011044  mov     ecx, esi
0x140011046  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14001104b  mov     edi, 8024200Dh
0x140011050  jmp     short loc_1400110B3
0x140011052  cmp     ecx, 0F0833h
0x140011058  jnz     short loc_1400110B3
0x14001105a  lea     rcx, [rbp+3Fh+var_58]
0x14001105e  call    ?Close@?$AutoComPtr@UICbsServicingProcessor@@@Windows@@QEAAXXZ; Windows::AutoComPtr<ICbsServicingProcessor>::Close(void)
0x140011063  mov     rcx, [r15]
0x140011066  test    rcx, rcx
0x140011069  jz      short loc_14001107E
0x14001106b  mov     rax, [rcx]
0x14001106e  mov     rax, [rax+10h]
0x140011072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011077  mov     qword ptr [r15], 0
0x14001107e  call    WaitForTiWorkerToShutdown
0x140011083  lea     r8, [rbp+3Fh+var_A0]; bool *
0x140011087  mov     [rbp+3Fh+var_A0], 0
0x14001108b  xor     edx, edx; bool
0x14001108d  mov     rcx, r14; this
0x140011090  call    ?ResumeSession@CCbsTiSession@@QEAAJ_NPEA_N@Z; CCbsTiSession::ResumeSession(bool,bool *)
0x140011095  mov     edi, eax
0x140011097  test    eax, eax
0x140011099  jns     short loc_1400110A7
0x14001109b  lea     r9, aFailedToResume; "Failed to resume the session after serv"...
0x1400110a2  jmp     loc_140010E70
0x1400110a7  xor     eax, eax
0x1400110a9  cmp     [rbp+3Fh+var_A0], al
0x1400110ac  setnz   al
0x1400110af  mov     [r13+0], eax
0x1400110b3  mov     rcx, [r14+28h]
0x1400110b7  test    rcx, rcx
0x1400110ba  jz      short loc_1400110D0
0x1400110bc  mov     rax, [rcx]
0x1400110bf  mov     rax, [rax+10h]
0x1400110c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400110c8  mov     qword ptr [r14+28h], 0
0x1400110d0  lea     rcx, [rbp+3Fh+var_70]; this
0x1400110d4  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x1400110d9  lea     rcx, [rbp+3Fh+var_98]
0x1400110dd  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1400110e2  lea     rcx, [rbp+3Fh+var_58]
0x1400110e6  call    ?Close@?$AutoComPtr@UICbsServicingProcessor@@@Windows@@QEAAXXZ; Windows::AutoComPtr<ICbsServicingProcessor>::Close(void)
0x1400110eb  mov     eax, edi
0x1400110ed  mov     rcx, [rbp+3Fh+var_50]
0x1400110f1  xor     rcx, rsp; StackCookie
0x1400110f4  call    __security_check_cookie
0x1400110f9  add     rsp, 0B8h
0x140011100  pop     r15
0x140011102  pop     r14
0x140011104  pop     r13
0x140011106  pop     r12
0x140011108  pop     rdi
0x140011109  pop     rsi
0x14001110a  pop     rbx
0x14001110b  pop     rbp
0x14001110c  retn
```
