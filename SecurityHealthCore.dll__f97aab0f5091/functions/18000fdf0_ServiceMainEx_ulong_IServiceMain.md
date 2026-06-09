# ServiceMainEx(ulong,IServiceMain *)

- ea: `0x18000fdf0`
- end: `0x1800100e3`
- name: `?ServiceMainEx@@YAKKPEAVIServiceMain@@@Z`
- size: `755`
- prototype: `unsigned int(unsigned int, struct IServiceMain *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004ae0`
- `0x180004b40`
- `0x18000d7fc`
- `0x18000e9bc`
- `0x18000f12c`
- `0x18000f2ec`
- `0x18000f3d0`
- `0x18000fad8`
- `0x18000fdf0`
- `0x1800da4ac`
- `0x1800da58c`
- `0x1800e1a1c`
- `0x1800e1a88`
- `0x1800e7010`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x18000fe7b`
- `KERNEL32!DebugBreak` at `0x18000fe7b`
- `ntdll!NtQuerySystemInformation` at `0x18000fe65`
- `ntdll!NtQuerySystemInformation` at `0x18000fe65`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000fed9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000fee7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000fed9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000fee7`

## pseudocode

```c
__int64 __fastcall ServiceMainEx(__int64 a1, struct IServiceMain *a2)
{
  char v3; // al
  const unsigned __int16 *v4; // rdx
  bool v5; // di
  struct SC_HANDLE__ **v6; // rdx
  unsigned int v7; // r8d
  const unsigned __int16 *v8; // r9
  int v9; // eax
  SC_HANDLE v10; // rbx
  SC_HANDLE v11; // rax
  int v12; // r9d
  int Event; // eax
  int v14; // r9d
  int v15; // eax
  ShieldProviderService *v16; // rcx
  int v17; // eax
  ShieldProviderService *v18; // rcx
  PVOID *v19; // rdx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  PVOID *v22; // rdx
  CommonUtil::CMpCriticalSection *v23; // rbx
  const unsigned __int16 *v25; // [rsp+20h] [rbp-10h]
  const unsigned __int16 *v26; // [rsp+20h] [rbp-10h]
  const unsigned __int16 *v27; // [rsp+20h] [rbp-10h]
  const struct _SECURITY_ATTRIBUTES *v28; // [rsp+28h] [rbp-8h]
  const struct _SECURITY_ATTRIBUTES *v29; // [rsp+28h] [rbp-8h]
  SC_HANDLE SystemInformation; // [rsp+68h] [rbp+38h] BYREF
  unsigned int v31; // [rsp+70h] [rbp+40h] BYREF

  v3 = (*(__int64 (__fastcall **)(struct IServiceMain *))(*(_QWORD *)a2 + 8LL))(a2);
  LOBYTE(g_fDevMode) = v3 & 1;
  LOBYTE(g_fDefaultBits) = (v3 & 2) != 0;
  g_dwPlatformEndValue = 0;
  if ( (v3 & 1) != 0 && ShieldProvider::GetMiscFlagIfApplicable((ShieldProvider *)L"DebugBreak", v4) )
  {
    LOWORD(SystemInformation) = 0;
    if ( !NtQuerySystemInformation(SystemKernelDebuggerInformation, &SystemInformation, 2u, 0)
      && (_BYTE)SystemInformation
      && !BYTE1(SystemInformation) )
    {
      DebugBreak();
    }
  }
  g_fLifetimeManagementEnabled = ShieldProvider::GetMiscFlagIfApplicable(
                                   (ShieldProvider *)L"EnableLifetimeManagement",
                                   v4);
  v5 = 0;
  SystemInformation = 0;
  v9 = CommonUtil::HrOpenSCManager((CommonUtil *)&SystemInformation, v6, v7, v8, v25);
  v10 = SystemInformation;
  if ( v9 >= 0 )
  {
    SystemInformation = 0;
    v5 = CommonUtil::HrOpenService(
           (CommonUtil *)&SystemInformation,
           (struct SC_HANDLE__ **)v10,
           (struct SC_HANDLE__ *)&stru_1800F5328,
           (const unsigned __int16 *)4,
           (unsigned int)v26) >= 0;
    if ( SystemInformation )
      CloseServiceHandle(SystemInformation);
  }
  if ( v10 )
    CloseServiceHandle(v10);
  g_fIsWscSvcPresent = v5;
  EnableRedirectionTrustIfNotAlreadyEnabled();
  v11 = (SC_HANDLE)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  SystemInformation = v11;
  if ( v11 )
  {
    *((_DWORD *)v11 + 3) = 252844334;
    *((_QWORD *)v11 + 5) = 0;
    *((_QWORD *)v11 + 6) = 0;
    *((_BYTE *)v11 + 56) = 0;
    *((_QWORD *)v11 + 8) = 0;
    *((_QWORD *)v11 + 9) = 0;
    *((_QWORD *)v11 + 10) = 0;
    g_pSvc = (CommonUtil::CMpCriticalSection *)v11;
    Event = CommonUtil::UtilCreateEvent(
              (CommonUtil *)&ShieldProvider::g_ahServiceStoppingEvent,
              (void **)1,
              0,
              v12,
              v26,
              v28);
    if ( Event < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          75,
          WPP_1292026083673c63ad0c6a1f8884c5b9_Traceguids,
          (unsigned int)Event);
      goto LABEL_32;
    }
    v15 = CommonUtil::UtilCreateEvent((CommonUtil *)&ShieldProvider::g_ahWscEvent, (void **)1, 1, v14, v27, v29);
    if ( v15 < 0 )
    {
      v22 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          74,
          WPP_1292026083673c63ad0c6a1f8884c5b9_Traceguids,
          (unsigned int)v15);
      goto LABEL_28;
    }
    v17 = ShieldProviderService::Initialize(v16, a2);
    if ( v17 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      v19 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_24;
      v21 = 73;
    }
    else
    {
      v17 = ShieldProviderService::ServiceMain(v18);
      if ( v17 >= 0 )
        goto LABEL_24;
      v20 = WPP_GLOBAL_Control;
      v19 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_24;
      v21 = 72;
    }
    WPP_SF_d(v20[2], v21, WPP_1292026083673c63ad0c6a1f8884c5b9_Traceguids, (unsigned int)v17);
LABEL_24:
    CommonUtil::UtilCloseHandle(ShieldProvider::g_ahWscEvent, v19);
    ShieldProvider::g_ahWscEvent = 0;
LABEL_28:
    CommonUtil::UtilCloseHandle((CommonUtil *)ShieldProvider::g_ahServiceStoppingEvent, v22);
    ShieldProvider::g_ahServiceStoppingEvent = 0;
LABEL_32:
    v23 = g_pSvc;
    if ( g_pSvc )
    {
      ShieldProviderService::~ShieldProviderService(g_pSvc);
      operator delete(v23, (const struct std::nothrow_t *)0x58);
    }
    g_pSvc = 0;
    goto LABEL_38;
  }
  g_pSvc = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_1292026083673c63ad0c6a1f8884c5b9_Traceguids, 2147942414LL);
LABEL_38:
  v31 = 0;
  _InterlockedExchange((volatile __int32 *)&v31, g_dwPlatformEndValue);
  return v31;
}

```

## disassembly

```asm
0x18000fdf0  mov     [rsp-28h+arg_0], rbx
0x18000fdf5  push    rbp
0x18000fdf6  push    rsi
0x18000fdf7  push    rdi
0x18000fdf8  push    r14
0x18000fdfa  push    r15
0x18000fdfc  mov     rbp, rsp
0x18000fdff  sub     rsp, 30h
0x18000fe03  mov     rax, [rdx]
0x18000fe06  mov     rcx, rdx
0x18000fe09  mov     rsi, rdx
0x18000fe0c  mov     rax, [rax+8]
0x18000fe10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe15  mov     eax, eax
0x18000fe17  mov     r15d, 1
0x18000fe1d  mov     cl, al
0x18000fe1f  xor     r14d, r14d
0x18000fe22  shr     al, 1
0x18000fe24  and     cl, r15b
0x18000fe27  and     al, r15b
0x18000fe2a  mov     cs:?g_fDevMode@@3_NA, cl; bool g_fDevMode
0x18000fe30  mov     cs:?g_fDefaultBits@@3_NA, al; bool g_fDefaultBits
0x18000fe36  mov     cs:?g_dwPlatformEndValue@@3KA, r14d; ulong g_dwPlatformEndValue
0x18000fe3d  test    cl, cl
0x18000fe3f  jz      short loc_18000FE81
0x18000fe41  lea     rcx, aDebugbreak; "DebugBreak"
0x18000fe48  call    ?GetMiscFlagIfApplicable@ShieldProvider@@YA_NPEBG@Z; ShieldProvider::GetMiscFlagIfApplicable(ushort const *)
0x18000fe4d  test    al, al
0x18000fe4f  jz      short loc_18000FE81
0x18000fe51  xor     r9d, r9d; ReturnLength
0x18000fe54  mov     word ptr [rbp+SystemInformation], r14w
0x18000fe59  lea     r8d, [r15+1]; SystemInformationLength
0x18000fe5d  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x18000fe61  lea     ecx, [r15+22h]; SystemInformationClass
0x18000fe65  call    cs:__imp_NtQuerySystemInformation
0x18000fe6b  test    eax, eax
0x18000fe6d  jnz     short loc_18000FE81
0x18000fe6f  cmp     byte ptr [rbp+SystemInformation], r14b
0x18000fe73  jz      short loc_18000FE81
0x18000fe75  cmp     byte ptr [rbp+SystemInformation+1], r14b
0x18000fe79  jnz     short loc_18000FE81
0x18000fe7b  call    cs:__imp_DebugBreak
0x18000fe81  lea     rcx, aEnablelifetime; "EnableLifetimeManagement"
0x18000fe88  call    ?GetMiscFlagIfApplicable@ShieldProvider@@YA_NPEBG@Z; ShieldProvider::GetMiscFlagIfApplicable(ushort const *)
0x18000fe8d  lea     rcx, [rbp+SystemInformation]; this
0x18000fe91  mov     cs:?g_fLifetimeManagementEnabled@@3_NA, al; bool g_fLifetimeManagementEnabled
0x18000fe97  mov     dil, r14b
0x18000fe9a  mov     [rbp+SystemInformation], r14
0x18000fe9e  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEBG1@Z; CommonUtil::HrOpenSCManager(SC_HANDLE__ * *,ulong,ushort const *,ushort const *)
0x18000fea3  mov     rbx, [rbp+SystemInformation]
0x18000fea7  test    eax, eax
0x18000fea9  js      short loc_18000FEDF
0x18000feab  mov     r9d, 4; unsigned __int16 *
0x18000feb1  mov     [rbp+SystemInformation], r14
0x18000feb5  lea     r8, stru_1800F5328; struct SC_HANDLE__ *
0x18000febc  mov     rdx, rbx; struct SC_HANDLE__ **
0x18000febf  lea     rcx, [rbp+SystemInformation]; this
0x18000fec3  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEBGK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,ushort const *,ulong)
0x18000fec8  mov     rcx, [rbp+SystemInformation]; hSCObject
0x18000fecc  mov     edi, eax
0x18000fece  shr     edi, 1Fh
0x18000fed1  xor     dil, r15b
0x18000fed4  test    rcx, rcx
0x18000fed7  jz      short loc_18000FEDF
0x18000fed9  call    cs:__imp_CloseServiceHandle
0x18000fedf  test    rbx, rbx
0x18000fee2  jz      short loc_18000FEED
0x18000fee4  mov     rcx, rbx; hSCObject
0x18000fee7  call    cs:__imp_CloseServiceHandle
0x18000feed  mov     cs:?g_fIsWscSvcPresent@@3_NA, dil; bool g_fIsWscSvcPresent
0x18000fef4  call    ?EnableRedirectionTrustIfNotAlreadyEnabled@@YAXXZ; EnableRedirectionTrustIfNotAlreadyEnabled(void)
0x18000fef9  mov     edi, 58h ; 'X'
0x18000fefe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ff05  mov     ecx, edi; unsigned __int64
0x18000ff07  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ff0c  mov     [rbp+SystemInformation], rax
0x18000ff10  test    rax, rax
0x18000ff13  jz      loc_180010087
0x18000ff19  mov     dword ptr [rax+0Ch], 0F12192Eh
0x18000ff20  lea     rcx, ?g_ahServiceStoppingEvent@ShieldProvider@@3PEAXEA; this
0x18000ff27  mov     [rax+28h], r14
0x18000ff2b  xor     r8d, r8d; int
0x18000ff2e  mov     [rax+30h], r14
0x18000ff32  mov     edx, r15d; void **
0x18000ff35  mov     [rax+38h], r14b
0x18000ff39  mov     [rax+40h], r14
0x18000ff3d  mov     [rax+48h], r14
0x18000ff41  mov     [rax+50h], r14
0x18000ff45  mov     cs:?g_pSvc@@3PEAVShieldProviderService@@EA, rax; ShieldProviderService * g_pSvc
0x18000ff4c  call    ?UtilCreateEvent@CommonUtil@@YAJPEAPEAXHHPEBGPEBU_SECURITY_ATTRIBUTES@@@Z; CommonUtil::UtilCreateEvent(void * *,int,int,ushort const *,_SECURITY_ATTRIBUTES const *)
0x18000ff51  test    eax, eax
0x18000ff53  js      loc_18001002E
0x18000ff59  mov     r8d, r15d; int
0x18000ff5c  lea     rcx, ?g_ahWscEvent@ShieldProvider@@3PEAXEA; this
0x18000ff63  mov     edx, r15d; void **
0x18000ff66  call    ?UtilCreateEvent@CommonUtil@@YAJPEAPEAXHHPEBGPEBU_SECURITY_ATTRIBUTES@@@Z; CommonUtil::UtilCreateEvent(void * *,int,int,ushort const *,_SECURITY_ATTRIBUTES const *)
0x18000ff6b  test    eax, eax
0x18000ff6d  js      short loc_18000FFE8
0x18000ff6f  mov     rdx, rsi; struct IServiceMain *
0x18000ff72  call    ?Initialize@ShieldProviderService@@QEAAJPEAVIServiceMain@@@Z; ShieldProviderService::Initialize(IServiceMain *)
0x18000ff77  test    eax, eax
0x18000ff79  js      short loc_18000FFA2
0x18000ff7b  call    ?ServiceMain@ShieldProviderService@@QEAAJXZ; ShieldProviderService::ServiceMain(void)
0x18000ff80  test    eax, eax
0x18000ff82  jns     short loc_18000FFD3
0x18000ff84  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff8b  lea     rdx, WPP_GLOBAL_Control
0x18000ff92  cmp     rcx, rdx
0x18000ff95  jz      short loc_18000FFD3
0x18000ff97  test    [rcx+1Ch], r15b
0x18000ff9b  jz      short loc_18000FFD3
0x18000ff9d  lea     edx, [rdi-10h]
0x18000ffa0  jmp     short loc_18000FFC0
0x18000ffa2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ffa9  lea     rdx, WPP_GLOBAL_Control
0x18000ffb0  cmp     rcx, rdx
0x18000ffb3  jz      short loc_18000FFD3
0x18000ffb5  test    [rcx+1Ch], r15b
0x18000ffb9  jz      short loc_18000FFD3
0x18000ffbb  mov     edx, 49h ; 'I'
0x18000ffc0  mov     rcx, [rcx+10h]
0x18000ffc4  lea     r8, WPP_1292026083673c63ad0c6a1f8884c5b9_Traceguids
0x18000ffcb  mov     r9d, eax
0x18000ffce  call    WPP_SF_d
0x18000ffd3  mov     rcx, cs:?g_ahWscEvent@ShieldProvider@@3PEAXEA; this
0x18000ffda  call    ?UtilCloseHandle@CommonUtil@@YAXPEAX@Z; CommonUtil::UtilCloseHandle(void *)
0x18000ffdf  mov     cs:?g_ahWscEvent@ShieldProvider@@3PEAXEA, r14; void * ShieldProvider::g_ahWscEvent
0x18000ffe6  jmp     short loc_180010019
0x18000ffe8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ffef  lea     rdx, WPP_GLOBAL_Control
0x18000fff6  cmp     rcx, rdx
0x18000fff9  jz      short loc_180010019
0x18000fffb  test    [rcx+1Ch], r15b
0x18000ffff  jz      short loc_180010019
0x180010001  mov     rcx, [rcx+10h]
0x180010005  lea     r8, WPP_1292026083673c63ad0c6a1f8884c5b9_Traceguids
0x18001000c  mov     edx, 4Ah ; 'J'
0x180010011  mov     r9d, eax
0x180010014  call    WPP_SF_d
0x180010019  mov     rcx, cs:?g_ahServiceStoppingEvent@ShieldProvider@@3PEAXEA; this
0x180010020  call    ?UtilCloseHandle@CommonUtil@@YAXPEAX@Z; CommonUtil::UtilCloseHandle(void *)
0x180010025  mov     cs:?g_ahServiceStoppingEvent@ShieldProvider@@3PEAXEA, r14; void * ShieldProvider::g_ahServiceStoppingEvent
0x18001002c  jmp     short loc_18001005F
0x18001002e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010035  lea     rdx, WPP_GLOBAL_Control
0x18001003c  cmp     rcx, rdx
0x18001003f  jz      short loc_18001005F
0x180010041  test    [rcx+1Ch], r15b
0x180010045  jz      short loc_18001005F
0x180010047  mov     rcx, [rcx+10h]
0x18001004b  lea     r8, WPP_1292026083673c63ad0c6a1f8884c5b9_Traceguids
0x180010052  mov     edx, 4Bh ; 'K'
0x180010057  mov     r9d, eax
0x18001005a  call    WPP_SF_d
0x18001005f  mov     rbx, cs:?g_pSvc@@3PEAVShieldProviderService@@EA; ShieldProviderService * g_pSvc
0x180010066  test    rbx, rbx
0x180010069  jz      short loc_18001007E
0x18001006b  mov     rcx, rbx; this
0x18001006e  call    ??1ShieldProviderService@@QEAA@XZ; ShieldProviderService::~ShieldProviderService(void)
0x180010073  mov     rdx, rdi; struct std::nothrow_t *
0x180010076  mov     rcx, rbx; void *
0x180010079  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001007e  mov     cs:?g_pSvc@@3PEAVShieldProviderService@@EA, r14; ShieldProviderService * g_pSvc
0x180010085  jmp     short loc_1800100C2
0x180010087  mov     cs:?g_pSvc@@3PEAVShieldProviderService@@EA, r14; ShieldProviderService * g_pSvc
0x18001008e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010095  lea     rdx, WPP_GLOBAL_Control
0x18001009c  cmp     rcx, rdx
0x18001009f  jz      short loc_1800100C2
0x1800100a1  test    [rcx+1Ch], r15b
0x1800100a5  jz      short loc_1800100C2
0x1800100a7  mov     rcx, [rcx+10h]
0x1800100ab  lea     r8, WPP_1292026083673c63ad0c6a1f8884c5b9_Traceguids
0x1800100b2  mov     edx, 4Ch ; 'L'
0x1800100b7  mov     r9d, 8007000Eh
0x1800100bd  call    WPP_SF_d
0x1800100c2  mov     eax, cs:?g_dwPlatformEndValue@@3KA; ulong g_dwPlatformEndValue
0x1800100c8  mov     rbx, [rsp+30h+arg_0]
0x1800100cd  mov     [rbp+arg_10], r14d
0x1800100d1  xchg    eax, [rbp+arg_10]
0x1800100d4  mov     eax, [rbp+arg_10]
0x1800100d7  add     rsp, 30h
0x1800100db  pop     r15
0x1800100dd  pop     r14
0x1800100df  pop     rdi
0x1800100e0  pop     rsi
0x1800100e1  pop     rbp
0x1800100e2  retn
```
