# BioIsoSrvPresenceMonitorUpdate

- ea: `0x140014720`
- end: `0x140014902`
- name: `BioIsoSrvPresenceMonitorUpdate`
- size: `482`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14000791c`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x140012974`
- `0x140014720`
- `0x140014908`
- `0x14001bd40`
- `0x140045560`
- `0x140059830`
- `0x140085010`

## string_xrefs

- `0x14001479b`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400147e4`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140014847`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400148bc`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140014745`: `PresenceMonitorUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvPresenceMonitorUpdate(int *a1, bool *a2)
{
  int BiometricUnit; // eax
  unsigned int v6; // ebx
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // [rsp+20h] [rbp-188h] BYREF
  std::_Ref_count_base *v10[2]; // [rsp+28h] [rbp-180h] BYREF
  _QWORD v11[42]; // [rsp+40h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v11,
    (__int64)"PresenceMonitorUpdate");
  v11[0] = &BioIsoProvider::PresenceMonitorUpdate::`vftable';
  BioIsoProvider::PresenceMonitorUpdate::StartActivity((BioIsoProvider::PresenceMonitorUpdate *)v11);
  if ( a1 && a2 )
  {
    if ( HardwareManager::ContainsHandle((unsigned __int64)a1) )
    {
      *(_OWORD *)v10 = 0;
      BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v10);
      v6 = BiometricUnit;
      if ( BiometricUnit >= 0 )
      {
        LOBYTE(v9) = 0;
        v7 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)v10[0] + 5) + 8LL))(*((_QWORD *)v10[0] + 5), &v9);
        v8 = v7;
        if ( v7 >= 0 )
        {
          *a2 = (_BYTE)v9 != 0;
          wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v11, 0);
          if ( v10[1] )
            std::_Ref_count_base::_Decref(v10[1]);
          BioIsoProvider::PresenceMonitorUpdate::~PresenceMonitorUpdate((BioIsoProvider::PresenceMonitorUpdate *)v11);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8DE,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
            (const char *)(unsigned int)v7,
            v9);
          if ( v10[1] )
            std::_Ref_count_base::_Decref(v10[1]);
          BioIsoProvider::PresenceMonitorUpdate::~PresenceMonitorUpdate((BioIsoProvider::PresenceMonitorUpdate *)v11);
          return v8;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8DA,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
          (const char *)(unsigned int)BiometricUnit,
          v9);
        if ( v10[1] )
          std::_Ref_count_base::_Decref(v10[1]);
        BioIsoProvider::PresenceMonitorUpdate::~PresenceMonitorUpdate((BioIsoProvider::PresenceMonitorUpdate *)v11);
        return v6;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8D4,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)0x80070057LL,
        v9);
      BioIsoProvider::PresenceMonitorUpdate::~PresenceMonitorUpdate((BioIsoProvider::PresenceMonitorUpdate *)v11);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D3,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v9);
    BioIsoProvider::PresenceMonitorUpdate::~PresenceMonitorUpdate((BioIsoProvider::PresenceMonitorUpdate *)v11);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x140014720  mov     [rsp+arg_10], rbx
0x140014725  push    rdi
0x140014726  sub     rsp, 1A0h
0x14001472d  mov     rax, cs:__security_cookie
0x140014734  xor     rax, rsp
0x140014737  mov     [rsp+1A8h+var_18], rax
0x14001473f  mov     rdi, rdx
0x140014742  mov     rbx, rcx
0x140014745  lea     rdx, aPresencemonito; "PresenceMonitorUpdate"
0x14001474c  lea     rcx, [rsp+1A8h+var_168]
0x140014751  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140014756  lea     rax, ??_7PresenceMonitorUpdate@BioIsoProvider@@6B@; const BioIsoProvider::PresenceMonitorUpdate::`vftable'
0x14001475d  mov     [rsp+1A8h+var_168], rax
0x140014762  lea     rcx, [rsp+1A8h+var_168]; this
0x140014767  call    ?StartActivity@PresenceMonitorUpdate@BioIsoProvider@@QEAAXXZ; BioIsoProvider::PresenceMonitorUpdate::StartActivity(void)
0x14001476c  nop
0x14001476d  test    rbx, rbx
0x140014770  jz      loc_1400148AC
0x140014776  test    rdi, rdi
0x140014779  jz      loc_1400148AC
0x14001477f  mov     rcx, rbx; void *
0x140014782  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x140014787  test    al, al
0x140014789  jnz     short loc_1400147BE
0x14001478b  mov     rcx, [rsp+1A8h]; this
0x140014793  mov     ebx, 80070057h
0x140014798  mov     r9d, ebx; char *
0x14001479b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400147a2  mov     edx, 8D4h; void *
0x1400147a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400147ac  nop
0x1400147ad  lea     rcx, [rsp+1A8h+var_168]; this
0x1400147b2  call    ??1PresenceMonitorUpdate@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorUpdate::~PresenceMonitorUpdate(void)
0x1400147b7  mov     eax, ebx
0x1400147b9  jmp     loc_1400148E0
0x1400147be  xorps   xmm0, xmm0
0x1400147c1  movdqu  xmmword ptr [rsp+1A8h+var_180], xmm0
0x1400147c7  lea     rdx, [rsp+1A8h+var_180]
0x1400147cc  mov     ecx, [rbx]
0x1400147ce  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x1400147d3  mov     ebx, eax
0x1400147d5  test    eax, eax
0x1400147d7  jns     short loc_140014817
0x1400147d9  mov     rcx, [rsp+1A8h]; this
0x1400147e1  mov     r9d, eax; char *
0x1400147e4  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400147eb  mov     edx, 8DAh; void *
0x1400147f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400147f5  nop
0x1400147f6  mov     rcx, [rsp+1A8h+var_180+8]; this
0x1400147fb  test    rcx, rcx
0x1400147fe  jz      short loc_140014806
0x140014800  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140014805  nop
0x140014806  lea     rcx, [rsp+1A8h+var_168]; this
0x14001480b  call    ??1PresenceMonitorUpdate@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorUpdate::~PresenceMonitorUpdate(void)
0x140014810  mov     eax, ebx
0x140014812  jmp     loc_1400148E0
0x140014817  mov     byte ptr [rsp+1A8h+var_188], 0; int
0x14001481c  mov     rax, [rsp+1A8h+var_180]
0x140014821  mov     rcx, [rax+28h]
0x140014825  mov     rax, [rcx]
0x140014828  lea     rdx, [rsp+1A8h+var_188]
0x14001482d  mov     rax, [rax+8]
0x140014831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014836  mov     ebx, eax
0x140014838  test    eax, eax
0x14001483a  jns     short loc_140014877
0x14001483c  mov     rcx, [rsp+1A8h]; this
0x140014844  mov     r9d, eax; char *
0x140014847  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14001484e  mov     edx, 8DEh; void *
0x140014853  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014858  nop
0x140014859  mov     rcx, [rsp+1A8h+var_180+8]; this
0x14001485e  test    rcx, rcx
0x140014861  jz      short loc_140014869
0x140014863  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140014868  nop
0x140014869  lea     rcx, [rsp+1A8h+var_168]; this
0x14001486e  call    ??1PresenceMonitorUpdate@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorUpdate::~PresenceMonitorUpdate(void)
0x140014873  mov     eax, ebx
0x140014875  jmp     short loc_1400148E0
0x140014877  cmp     byte ptr [rsp+1A8h+var_188], 0
0x14001487c  setnz   al
0x14001487f  mov     [rdi], al
0x140014881  xor     edx, edx
0x140014883  lea     rcx, [rsp+1A8h+var_168]
0x140014888  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14001488d  nop
0x14001488e  mov     rcx, [rsp+1A8h+var_180+8]; this
0x140014893  test    rcx, rcx
0x140014896  jz      short loc_14001489E
0x140014898  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001489d  nop
0x14001489e  lea     rcx, [rsp+1A8h+var_168]; this
0x1400148a3  call    ??1PresenceMonitorUpdate@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorUpdate::~PresenceMonitorUpdate(void)
0x1400148a8  xor     eax, eax
0x1400148aa  jmp     short loc_1400148E0
0x1400148ac  mov     rcx, [rsp+1A8h]; this
0x1400148b4  mov     ebx, 80004003h
0x1400148b9  mov     r9d, ebx; char *
0x1400148bc  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400148c3  mov     edx, 8D3h; void *
0x1400148c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400148cd  nop
0x1400148ce  lea     rcx, [rsp+1A8h+var_168]; this
0x1400148d3  call    ??1PresenceMonitorUpdate@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorUpdate::~PresenceMonitorUpdate(void)
0x1400148d8  mov     eax, ebx
0x1400148da  jmp     short loc_1400148E0
0x1400148dc  mov     eax, [rsp+1A8h+var_184]
0x1400148e0  mov     rcx, [rsp+1A8h+var_18]
0x1400148e8  xor     rcx, rsp; StackCookie
0x1400148eb  call    __security_check_cookie
0x1400148f0  mov     rbx, [rsp+1A8h+arg_10]
0x1400148f8  add     rsp, 1A0h
0x1400148ff  pop     rdi
0x140014900  retn
```
