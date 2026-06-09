# BioIsoSrvOpenEnrollAuthorizationSession

- ea: `0x140054fd0`
- end: `0x1400551b5`
- name: `BioIsoSrvOpenEnrollAuthorizationSession`
- size: `485`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x14000a420`
- `0x140012974`
- `0x14001bd40`
- `0x1400418cc`
- `0x140041b84`
- `0x140041d20`
- `0x140045170`
- `0x140054fd0`
- `0x1400597d4`
- `0x14005cf30`

## string_xrefs

- `0x140055038`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140055070`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400550a8`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140055114`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400550fa`: `onecore\ds\security\biometrics\service\trustlet\exe\authorizationcontext.cpp`
- `0x140054ffb`: `OpenEnrollAuthorizationSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvOpenEnrollAuthorizationSession(_QWORD *a1, _QWORD *a2, _DWORD *a3)
{
  _OWORD *v7; // r14
  _OWORD *v8; // rax
  void *v9; // rcx
  void *v10[2]; // [rsp+20h] [rbp-188h] BYREF
  _QWORD v11[42]; // [rsp+30h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v11,
    (__int64)"OpenEnrollAuthorizationSession");
  v11[0] = &BioIsoProvider::OpenEnrollAuthorizationSession::`vftable';
  BioIsoProvider::OpenEnrollAuthorizationSession::StartActivity((BioIsoProvider::OpenEnrollAuthorizationSession *)v11);
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        std::make_unique<EnrollAuthzContext,,0>((LARGE_INTEGER **)v10);
        v7 = v10[0];
        v8 = MIDL_user_allocate(0x10u);
        if ( v8 )
        {
          *v8 = *v7;
          *a2 = v8;
          *a3 = 16;
          v9 = v10[0];
          v10[0] = 0;
          *a1 = v9;
          HardwareManager::AddHandle(v9);
          wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v11, 0);
          std::unique_ptr<EnrollAuthzContext>::~unique_ptr<EnrollAuthzContext>(v10);
          BioIsoProvider::OpenEnrollAuthorizationSession::~OpenEnrollAuthorizationSession((BioIsoProvider::OpenEnrollAuthorizationSession *)v11);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x17,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\authorizationcontext.cpp",
            (const char *)0x8007000ELL,
            (int)v10[0]);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA8B,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
            (const char *)0x8007000ELL,
            (int)v10[0]);
          std::unique_ptr<EnrollAuthzContext>::~unique_ptr<EnrollAuthzContext>(v10);
          BioIsoProvider::OpenEnrollAuthorizationSession::~OpenEnrollAuthorizationSession((BioIsoProvider::OpenEnrollAuthorizationSession *)v11);
          return 2147942414LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA87,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
          (const char *)0x80004003LL,
          (int)v10[0]);
        BioIsoProvider::OpenEnrollAuthorizationSession::~OpenEnrollAuthorizationSession((BioIsoProvider::OpenEnrollAuthorizationSession *)v11);
        return 2147500035LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA86,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)0x80004003LL,
        (int)v10[0]);
      BioIsoProvider::OpenEnrollAuthorizationSession::~OpenEnrollAuthorizationSession((BioIsoProvider::OpenEnrollAuthorizationSession *)v11);
      return 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA85,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      (int)v10[0]);
    BioIsoProvider::OpenEnrollAuthorizationSession::~OpenEnrollAuthorizationSession((BioIsoProvider::OpenEnrollAuthorizationSession *)v11);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x140054fd0  mov     [rsp+arg_18], rbx
0x140054fd5  push    rsi
0x140054fd6  push    rdi
0x140054fd7  push    r14
0x140054fd9  sub     rsp, 190h
0x140054fe0  mov     rax, cs:__security_cookie
0x140054fe7  xor     rax, rsp
0x140054fea  mov     [rsp+1A8h+var_28], rax
0x140054ff2  mov     rdi, r8
0x140054ff5  mov     rbx, rdx
0x140054ff8  mov     rsi, rcx
0x140054ffb  lea     rdx, aOpenenrollauth; "OpenEnrollAuthorizationSession"
0x140055002  lea     rcx, [rsp+1A8h+var_178]
0x140055007  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14005500c  lea     rax, ??_7OpenEnrollAuthorizationSession@BioIsoProvider@@6B@; const BioIsoProvider::OpenEnrollAuthorizationSession::`vftable'
0x140055013  mov     [rsp+1A8h+var_178], rax
0x140055018  lea     rcx, [rsp+1A8h+var_178]; this
0x14005501d  call    ?StartActivity@OpenEnrollAuthorizationSession@BioIsoProvider@@QEAAXXZ; BioIsoProvider::OpenEnrollAuthorizationSession::StartActivity(void)
0x140055022  nop
0x140055023  test    rsi, rsi
0x140055026  jnz     short loc_14005505B
0x140055028  mov     rcx, [rsp+1A8h]; this
0x140055030  mov     ebx, 80004003h
0x140055035  mov     r9d, ebx; char *
0x140055038  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14005503f  mov     edx, 0A85h; void *
0x140055044  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140055049  nop
0x14005504a  lea     rcx, [rsp+1A8h+var_178]; this
0x14005504f  call    ??1OpenEnrollAuthorizationSession@BioIsoProvider@@QEAA@XZ; BioIsoProvider::OpenEnrollAuthorizationSession::~OpenEnrollAuthorizationSession(void)
0x140055054  mov     eax, ebx
0x140055056  jmp     loc_140055190
0x14005505b  test    rbx, rbx
0x14005505e  jnz     short loc_140055093
0x140055060  mov     rcx, [rsp+1A8h]; this
0x140055068  mov     ebx, 80004003h
0x14005506d  mov     r9d, ebx; char *
0x140055070  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140055077  mov     edx, 0A86h; void *
0x14005507c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140055081  nop
0x140055082  lea     rcx, [rsp+1A8h+var_178]; this
0x140055087  call    ??1OpenEnrollAuthorizationSession@BioIsoProvider@@QEAA@XZ; BioIsoProvider::OpenEnrollAuthorizationSession::~OpenEnrollAuthorizationSession(void)
0x14005508c  mov     eax, ebx
0x14005508e  jmp     loc_140055190
0x140055093  test    rdi, rdi
0x140055096  jnz     short loc_1400550CB
0x140055098  mov     rcx, [rsp+1A8h]; this
0x1400550a0  mov     ebx, 80004003h
0x1400550a5  mov     r9d, ebx; char *
0x1400550a8  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400550af  mov     edx, 0A87h; void *
0x1400550b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400550b9  nop
0x1400550ba  lea     rcx, [rsp+1A8h+var_178]; this
0x1400550bf  call    ??1OpenEnrollAuthorizationSession@BioIsoProvider@@QEAA@XZ; BioIsoProvider::OpenEnrollAuthorizationSession::~OpenEnrollAuthorizationSession(void)
0x1400550c4  mov     eax, ebx
0x1400550c6  jmp     loc_140055190
0x1400550cb  lea     rcx, [rsp+1A8h+var_188]
0x1400550d0  call    ??$make_unique@VEnrollAuthzContext@@$$V$0A@@std@@YA?AV?$unique_ptr@VEnrollAuthzContext@@U?$default_delete@VEnrollAuthzContext@@@std@@@0@XZ; std::make_unique<EnrollAuthzContext,,0>(void)
0x1400550d5  nop
0x1400550d6  mov     r14, [rsp+1A8h+var_188]
0x1400550db  mov     ecx, 10h; size
0x1400550e0  call    MIDL_user_allocate
0x1400550e5  test    rax, rax
0x1400550e8  jnz     short loc_14005513F
0x1400550ea  mov     rcx, [rsp+1A8h]; this
0x1400550f2  mov     ebx, 8007000Eh
0x1400550f7  mov     r9d, ebx; char *
0x1400550fa  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\biometrics\\serv"...
0x140055101  lea     edx, [rax+17h]; void *
0x140055104  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140055109  mov     rcx, [rsp+1A8h]; this
0x140055111  mov     r9d, ebx; char *
0x140055114  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14005511b  mov     edx, 0A8Bh; void *
0x140055120  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140055125  nop
0x140055126  lea     rcx, [rsp+1A8h+var_188]
0x14005512b  call    ??1?$unique_ptr@VEnrollAuthzContext@@U?$default_delete@VEnrollAuthzContext@@@std@@@std@@QEAA@XZ; std::unique_ptr<EnrollAuthzContext>::~unique_ptr<EnrollAuthzContext>(void)
0x140055130  nop
0x140055131  lea     rcx, [rsp+1A8h+var_178]; this
0x140055136  call    ??1OpenEnrollAuthorizationSession@BioIsoProvider@@QEAA@XZ; BioIsoProvider::OpenEnrollAuthorizationSession::~OpenEnrollAuthorizationSession(void)
0x14005513b  mov     eax, ebx
0x14005513d  jmp     short loc_140055190
0x14005513f  movups  xmm0, xmmword ptr [r14]
0x140055143  movdqu  xmmword ptr [rax], xmm0
0x140055147  mov     [rbx], rax
0x14005514a  mov     dword ptr [rdi], 10h
0x140055150  mov     rcx, [rsp+1A8h+var_188]; void *
0x140055155  mov     [rsp+1A8h+var_188], 0
0x14005515e  mov     [rsi], rcx
0x140055161  call    ?AddHandle@HardwareManager@@SAXQEAX@Z; HardwareManager::AddHandle(void * const)
0x140055166  xor     edx, edx
0x140055168  lea     rcx, [rsp+1A8h+var_178]
0x14005516d  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140055172  nop
0x140055173  lea     rcx, [rsp+1A8h+var_188]
0x140055178  call    ??1?$unique_ptr@VEnrollAuthzContext@@U?$default_delete@VEnrollAuthzContext@@@std@@@std@@QEAA@XZ; std::unique_ptr<EnrollAuthzContext>::~unique_ptr<EnrollAuthzContext>(void)
0x14005517d  nop
0x14005517e  lea     rcx, [rsp+1A8h+var_178]; this
0x140055183  call    ??1OpenEnrollAuthorizationSession@BioIsoProvider@@QEAA@XZ; BioIsoProvider::OpenEnrollAuthorizationSession::~OpenEnrollAuthorizationSession(void)
0x140055188  xor     eax, eax
0x14005518a  jmp     short loc_140055190
0x14005518c  mov     eax, dword ptr [rsp+1A8h+var_188]
0x140055190  mov     rcx, [rsp+1A8h+var_28]
0x140055198  xor     rcx, rsp; StackCookie
0x14005519b  call    __security_check_cookie
0x1400551a0  mov     rbx, [rsp+1A8h+arg_18]
0x1400551a8  add     rsp, 190h
0x1400551af  pop     r14
0x1400551b1  pop     rdi
0x1400551b2  pop     rsi
0x1400551b3  retn
```
