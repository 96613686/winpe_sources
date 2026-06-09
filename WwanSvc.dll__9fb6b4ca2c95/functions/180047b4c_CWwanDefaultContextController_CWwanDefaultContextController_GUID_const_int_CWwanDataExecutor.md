# CWwanDefaultContextController::CWwanDefaultContextController(_GUID const &,int,CWwanDataExecutor *)

- ea: `0x180047b4c`
- end: `0x180047dd1`
- name: `??0CWwanDefaultContextController@@QEAA@AEBU_GUID@@HPEAVCWwanDataExecutor@@@Z`
- size: `645`
- prototype: `CWwanDefaultContextController *__fastcall(CWwanDefaultContextController *__hidden this, const struct _GUID *, int, struct CWwanDataExecutor *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026848`

## callees

- `0x18001150c`
- `0x180011a1c`
- `0x180012300`
- `0x180014b5c`
- `0x180014f1c`
- `0x180045eb8`
- `0x1800471bc`
- `0x180047720`
- `0x180047b4c`
- `0x180048660`
- `0x180050504`
- `0x1800b65ac`
- `0x1800c5d28`

## import_xrefs

- `WwanPrfl!WwanProfileInit` at `0x180047c0b`
- `WwanPrfl!WwanProfileInit` at `0x180047c15`
- `WwanPrfl!WwanProfileInit` at `0x180047c0b`
- `WwanPrfl!WwanProfileInit` at `0x180047c15`
- `MobileNetworking!CreateReadWriteLock` at `0x180047c5b`
- `MobileNetworking!CreateReadWriteLock` at `0x180047c5b`
- `MobileNetworking!DeleteReadWriteLock` at `0x180047caa`
- `MobileNetworking!DeleteReadWriteLock` at `0x180047caa`

## string_xrefs

- `0x180047cd3`: `Timer Creation Completed`
- `0x180047c68`: `WwanCreateRwLock Failed [%u]`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CWwanDefaultContextController *__fastcall CWwanDefaultContextController::CWwanDefaultContextController(
        CWwanDefaultContextController *this,
        const struct _GUID *a2,
        int a3,
        struct CWwanDataExecutor *a4)
{
  int v7; // ecx
  unsigned int v8; // eax
  unsigned int Timer; // esi
  CWwanDefaultContextController *v10; // rcx
  unsigned int v11; // eax
  void (*v13)(void *, void *); // [rsp+20h] [rbp-58h]
  StateSeparation *v14[9]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v15; // [rsp+88h] [rbp+10h] BYREF
  int v16; // [rsp+98h] [rbp+20h] BYREF

  CWWANContextControllerBase::CWWANContextControllerBase(this, a3, a4);
  *(_QWORD *)this = &CWwanDefaultContextController::`vftable';
  CWwanContextLifeCycle::CWwanContextLifeCycle((CWwanDefaultContextController *)((char *)this + 8200), this);
  *((_QWORD *)this + 2165) = 0;
  *(_QWORD *)((char *)this + 17332) = 0;
  *(_QWORD *)((char *)this + 17340) = 0;
  *(_QWORD *)((char *)this + 17348) = 0;
  *((_DWORD *)this + 4339) = 1;
  *((_DWORD *)this + 4340) = 1;
  *((_QWORD *)this + 2171) = 0;
  *((_QWORD *)this + 2172) = 0;
  *((_QWORD *)this + 2173) = 1;
  *((_DWORD *)this + 4348) = 0;
  *((_DWORD *)this + 4349) = 1;
  *((_QWORD *)this + 2175) = 1;
  *((_DWORD *)this + 4352) = 27;
  *((struct _GUID *)this + 396) = *a2;
  WwanProfileInit((char *)this + 11000);
  WwanProfileInit((char *)this + 16);
  *((_DWORD *)this + 4341) = 0;
  CWWANContextControllerBase::FillIntfGuidStrInCIS(this, (const struct _GUID *)this + 396);
  v7 = *(_DWORD *)(*((_QWORD *)this + 1) + 12588LL);
  if ( v7 != 4 && v7 != 1 )
    CWWANContextControllerBase::SendConnectionIStreamCreatedEvent(this, 2u);
  *((_DWORD *)this + 2046) = 0;
  v8 = CreateReadWriteLock((char *)this + 8072);
  if ( v8 )
  {
    WwanLog::Error(
      "CWwanDefaultContextController::CWwanDefaultContextController",
      0,
      L"WwanCreateRwLock Failed [%u]",
      v8);
  }
  else
  {
    Timer = WwanTimerCreateTimer(
              (void **)this + 1022,
              g_hTimerContext,
              (CWwanDefaultContextController *)((char *)this + 8072),
              (char *)this + 6336,
              (void (*)(void *, void *))CWwanDefaultContextController::_TimerExpirationCallBack);
    if ( Timer )
    {
      DeleteReadWriteLock((char *)this + 8072);
      WwanLog::Error(
        "CWwanDefaultContextController::CWwanDefaultContextController",
        0,
        L"Timer Creation Failed [%d]",
        Timer);
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    else
    {
      *((_DWORD *)this + 2046) = 1;
      WwanLog::Info("CWwanDefaultContextController::CWwanDefaultContextController", 0, L"Timer Creation Completed");
    }
  }
  v15 = 0;
  v16 = 6;
  std::make_unique<StateSeparation,enum _REG_ROOT_PATH,0>(v14, &v16);
  if ( !StateSeparation::GetDWORD(v14[0], L"WwanSvc\\GroupPolicy", L"DisableWwanAutoConnect", &v15) )
  {
    v11 = v15;
    *((_DWORD *)this + 4337) = v15 == 1;
    LODWORD(v13) = v11;
    WwanLog::Info(
      "CWwanDefaultContextController::CWwanDefaultContextController",
      0,
      L" group policy reg [%s] is present with data %d",
      L"DisableWwanAutoConnect",
      v13);
  }
  if ( CWwanDefaultContextController::IsCAMChinaCTAPolicySet(v10) )
  {
    *((_DWORD *)this + 4342) = 1;
    WwanLog::Info(
      "CWwanDefaultContextController::CWwanDefaultContextController",
      0,
      L" auto-connect is defaulted to disabled for China CTA region");
  }
  LODWORD(v13) = *((_DWORD *)a4 + 3148);
  WwanLog::Info(
    "CWwanDefaultContextController::CWwanDefaultContextController",
    (const struct _GUID *)this + 396,
    L"Int Constructed (idx %d DSDx type %d)",
    *((unsigned int *)a4 + 3143),
    v13);
  std::unique_ptr<StateSeparation>::~unique_ptr<StateSeparation>(v14);
  return this;
}

```

## disassembly

```asm
0x180047b4c  mov     [rsp+arg_0], rcx
0x180047b51  push    rbx
0x180047b52  push    rbp
0x180047b53  push    rsi
0x180047b54  push    rdi
0x180047b55  push    r12
0x180047b57  push    r14
0x180047b59  push    r15
0x180047b5b  sub     rsp, 40h
0x180047b5f  mov     r14, r9
0x180047b62  mov     eax, r8d
0x180047b65  mov     rbx, rdx
0x180047b68  mov     rdi, rcx
0x180047b6b  mov     r8, r9; struct CWwanDataExecutor *
0x180047b6e  mov     edx, eax; int
0x180047b70  call    ??0CWWANContextControllerBase@@QEAA@HPEAVCWwanDataExecutor@@@Z; CWWANContextControllerBase::CWWANContextControllerBase(int,CWwanDataExecutor *)
0x180047b75  nop
0x180047b76  lea     rax, ??_7CWwanDefaultContextController@@6B@; const CWwanDefaultContextController::`vftable'
0x180047b7d  mov     [rdi], rax
0x180047b80  lea     rcx, [rdi+2008h]; this
0x180047b87  mov     rdx, rdi; struct CWWANContextControllerBase *
0x180047b8a  call    ??0CWwanContextLifeCycle@@QEAA@PEAVCWWANContextControllerBase@@@Z; CWwanContextLifeCycle::CWwanContextLifeCycle(CWWANContextControllerBase *)
0x180047b8f  nop
0x180047b90  xor     r15d, r15d
0x180047b93  mov     [rdi+43A8h], r15
0x180047b9a  mov     [rdi+43B4h], r15
0x180047ba1  mov     [rdi+43BCh], r15
0x180047ba8  mov     [rdi+43C4h], r15
0x180047baf  lea     r12d, [r15+1]
0x180047bb3  mov     [rdi+43CCh], r12d
0x180047bba  mov     [rdi+43D0h], r12d
0x180047bc1  mov     [rdi+43D8h], r15
0x180047bc8  mov     [rdi+43E0h], r15
0x180047bcf  mov     [rdi+43E8h], r12
0x180047bd6  mov     [rdi+43F0h], r15d
0x180047bdd  mov     [rdi+43F4h], r12d
0x180047be4  mov     [rdi+43F8h], r12
0x180047beb  mov     dword ptr [rdi+4400h], 1Bh
0x180047bf5  lea     rbp, [rdi+18C0h]
0x180047bfc  movups  xmm0, xmmword ptr [rbx]
0x180047bff  movdqu  xmmword ptr [rbp+0], xmm0
0x180047c04  lea     rcx, [rdi+2AF8h]
0x180047c0b  call    cs:__imp_WwanProfileInit
0x180047c11  lea     rcx, [rdi+10h]
0x180047c15  call    cs:__imp_WwanProfileInit
0x180047c1b  mov     [rdi+43D4h], r15d
0x180047c22  mov     rdx, rbp; struct _GUID *
0x180047c25  mov     rcx, rdi; this
0x180047c28  call    ?FillIntfGuidStrInCIS@CWWANContextControllerBase@@IEAAXAEBU_GUID@@@Z; CWWANContextControllerBase::FillIntfGuidStrInCIS(_GUID const &)
0x180047c2d  mov     rax, [rdi+8]
0x180047c31  mov     ecx, [rax+312Ch]
0x180047c37  cmp     ecx, 4
0x180047c3a  jz      short loc_180047C4D
0x180047c3c  cmp     ecx, r12d
0x180047c3f  jz      short loc_180047C4D
0x180047c41  lea     edx, [r15+2]; unsigned int
0x180047c45  mov     rcx, rdi; this
0x180047c48  call    ?SendConnectionIStreamCreatedEvent@CWWANContextControllerBase@@IEAAXK@Z; CWWANContextControllerBase::SendConnectionIStreamCreatedEvent(ulong)
0x180047c4d  lea     rbx, [rdi+1F88h]
0x180047c54  mov     [rbx+70h], r15d
0x180047c58  mov     rcx, rbx
0x180047c5b  call    cs:__imp_CreateReadWriteLock
0x180047c61  test    eax, eax
0x180047c63  jz      short loc_180047C7F
0x180047c65  mov     r9d, eax
0x180047c68  lea     r8, aWwancreaterwlo; "WwanCreateRwLock Failed [%u]"
0x180047c6f  xor     edx, edx; struct _GUID *
0x180047c71  lea     rcx, aCwwandefaultco_6; "CWwanDefaultContextController::CWwanDef"...
0x180047c78  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180047c7d  jmp     short loc_180047CE8
0x180047c7f  lea     rcx, [rbx+68h]; void **
0x180047c83  lea     rax, ?_TimerExpirationCallBack@CWwanDefaultContextController@@SAXPEAX0@Z; CWwanDefaultContextController::_TimerExpirationCallBack(void *,void *)
0x180047c8a  mov     [rsp+78h+var_58], rax; void (*)(void *, void *)
0x180047c8f  mov     r9, rbp; void *
0x180047c92  mov     r8, rbx; struct _READ_WRITE_LOCK *
0x180047c95  mov     rdx, cs:g_hTimerContext; void *
0x180047c9c  call    ?WwanTimerCreateTimer@@YAKPEAPEAXPEAXPEAU_READ_WRITE_LOCK@@1P6AX11@Z@Z; WwanTimerCreateTimer(void * *,void *,_READ_WRITE_LOCK *,void *,void (*)(void *,void *))
0x180047ca1  mov     esi, eax
0x180047ca3  test    eax, eax
0x180047ca5  jz      short loc_180047CCF
0x180047ca7  mov     rcx, rbx
0x180047caa  call    cs:__imp_DeleteReadWriteLock
0x180047cb0  mov     r9d, esi
0x180047cb3  lea     r8, aTimerCreationF; "Timer Creation Failed [%d]"
0x180047cba  xor     edx, edx; struct _GUID *
0x180047cbc  lea     rcx, aCwwandefaultco_6; "CWwanDefaultContextController::CWwanDef"...
0x180047cc3  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180047cc8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180047ccd  jmp     short loc_180047CE8
0x180047ccf  mov     [rbx+70h], r12d
0x180047cd3  lea     r8, aTimerCreationC; "Timer Creation Completed"
0x180047cda  xor     edx, edx; struct _GUID *
0x180047cdc  lea     rcx, aCwwandefaultco_6; "CWwanDefaultContextController::CWwanDef"...
0x180047ce3  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180047ce8  mov     [rsp+78h+arg_8], r15d
0x180047cf0  mov     [rsp+78h+arg_18], 6
0x180047cfb  lea     rdx, [rsp+78h+arg_18]
0x180047d03  lea     rcx, [rsp+78h+var_48]
0x180047d08  call    ??$make_unique@VStateSeparation@@W4_REG_ROOT_PATH@@$0A@@std@@YA?AV?$unique_ptr@VStateSeparation@@U?$default_delete@VStateSeparation@@@std@@@0@$$QEAW4_REG_ROOT_PATH@@@Z; std::make_unique<StateSeparation,_REG_ROOT_PATH,0>(_REG_ROOT_PATH &&)
0x180047d0d  lea     r9, [rsp+78h+arg_8]; unsigned int *
0x180047d15  lea     r8, aDisablewwanaut; "DisableWwanAutoConnect"
0x180047d1c  lea     rdx, aWwansvcGrouppo; "WwanSvc\\GroupPolicy"
0x180047d23  mov     rcx, [rsp+78h+var_48]; this
0x180047d28  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x180047d2d  test    eax, eax
0x180047d2f  jnz     short loc_180047D67
0x180047d31  mov     ecx, r15d
0x180047d34  mov     eax, [rsp+78h+arg_8]
0x180047d3b  cmp     eax, r12d
0x180047d3e  setz    cl
0x180047d41  mov     [rdi+43C4h], ecx
0x180047d47  mov     dword ptr [rsp+78h+var_58], eax
0x180047d4b  lea     r9, aDisablewwanaut; "DisableWwanAutoConnect"
0x180047d52  lea     r8, aGroupPolicyReg; " group policy reg [%s] is present with "...
0x180047d59  xor     edx, edx; struct _GUID *
0x180047d5b  lea     rcx, aCwwandefaultco_6; "CWwanDefaultContextController::CWwanDef"...
0x180047d62  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180047d67  call    ?IsCAMChinaCTAPolicySet@CWwanDefaultContextController@@AEAA_NXZ; CWwanDefaultContextController::IsCAMChinaCTAPolicySet(void)
0x180047d6c  test    al, al
0x180047d6e  jz      short loc_180047D8C
0x180047d70  mov     [rdi+43D8h], r12d
0x180047d77  lea     r8, aAutoConnectIsD; " auto-connect is defaulted to disabled "...
0x180047d7e  xor     edx, edx; struct _GUID *
0x180047d80  lea     rcx, aCwwandefaultco_6; "CWwanDefaultContextController::CWwanDef"...
0x180047d87  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180047d8c  mov     eax, [r14+3130h]
0x180047d93  mov     dword ptr [rsp+78h+var_58], eax
0x180047d97  mov     r9d, [r14+311Ch]
0x180047d9e  lea     r8, aIntConstructed; "Int Constructed (idx %d DSDx type %d)"
0x180047da5  mov     rdx, rbp; struct _GUID *
0x180047da8  lea     rcx, aCwwandefaultco_6; "CWwanDefaultContextController::CWwanDef"...
0x180047daf  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180047db4  lea     rcx, [rsp+78h+var_48]
0x180047db9  call    ??1?$unique_ptr@VStateSeparation@@U?$default_delete@VStateSeparation@@@std@@@std@@QEAA@XZ; std::unique_ptr<StateSeparation>::~unique_ptr<StateSeparation>(void)
0x180047dbe  nop
0x180047dbf  mov     rax, rdi
0x180047dc2  add     rsp, 40h
0x180047dc6  pop     r15
0x180047dc8  pop     r14
0x180047dca  pop     r12
0x180047dcc  pop     rdi
0x180047dcd  pop     rsi
0x180047dce  pop     rbp
0x180047dcf  pop     rbx
0x180047dd0  retn
```
