# CCbsClassFactory::CreateWorker(ICbsWorker * *)

- ea: `0x1400094f4`
- end: `0x140009689`
- name: `?CreateWorker@CCbsClassFactory@@QEAAJPEAPEAUICbsWorker@@@Z`
- size: `405`
- prototype: `__int64 __fastcall(CCbsClassFactory *__hidden this, struct ICbsWorker **)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x140009364`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140006d44`
- `0x140008c80`
- `0x140008ef4`
- `0x140009084`
- `0x14000914c`
- `0x1400091d8`
- `0x1400094f4`
- `0x14002b010`

## pseudocode

```c
__int64 __fastcall CCbsClassFactory::CreateWorker(CCbsClassFactory *this, struct ICbsWorker **a2)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rdx
  struct ICbsWorker *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdx
  int v13; // [rsp+20h] [rbp-40h]
  int v14[2]; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v15[24]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v16; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  MonitoredCritSecLocker::MonitoredCritSecLocker((MonitoredCritSecLocker *)v15, (CCbsClassFactory *)((char *)this + 24));
  if ( a2 )
  {
    v8 = (struct ICbsWorker *)*((_QWORD *)this + 8);
    if ( !v8 )
    {
      v16 = 0;
      if ( !Windows::AutoNewPtr<CCbsWorker>::Allocate<>(&v16) )
      {
        v9 = v16;
        if ( v16 )
          (**(void (__fastcall ***)(__int64, __int64))v16)(v16, 1);
LABEL_12:
        v5 = -2147024882;
        LODWORD(v16) = -2147024882;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogPartial<>(v9, 3, "Failed to allocate new CBS worker.");
          *(_QWORD *)v14 = &v16;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v11,
            3,
            (__int64)": {}",
            (__int64)v14);
        }
        v7 = 56;
        goto LABEL_15;
      }
      v10 = v16;
      if ( v16 )
        v10 = *(int *)(*(_QWORD *)(v16 + 8) + 4LL) + v16 + 8;
      Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
        (char *)this + 64,
        v10);
      v8 = (struct ICbsWorker *)*((_QWORD *)this + 8);
      if ( !v8 )
        goto LABEL_12;
    }
    *a2 = v8;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 8LL))(*((_QWORD *)this + 8));
    v5 = 0;
    goto LABEL_17;
  }
  v5 = -2147467261;
  LODWORD(v16) = -2147467261;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogPartial<>(v4, 3, "No worker result specified");
    *(_QWORD *)v14 = &v16;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v6,
      3,
      (__int64)": {}",
      (__int64)v14);
  }
  v7 = 52;
LABEL_15:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecore\\base\\cbs\\tiworker\\tiworkerclassfactory.cpp",
    (const char *)v5,
    v13);
LABEL_17:
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v15);
  return v5;
}

```

## disassembly

```asm
0x1400094f4  mov     [rsp-8+arg_10], rbx
0x1400094f9  mov     [rsp-8+arg_18], rdi
0x1400094fe  push    rbp
0x1400094ff  mov     rbp, rsp
0x140009502  sub     rsp, 60h
0x140009506  mov     rax, cs:__security_cookie
0x14000950d  xor     rax, rsp
0x140009510  mov     [rbp+var_8], rax
0x140009514  mov     rdi, rdx
0x140009517  mov     rbx, rcx
0x14000951a  lea     rdx, [rcx+18h]; struct AutoMonitoredCritSec *
0x14000951e  lea     rcx, [rbp+var_28]; this
0x140009522  call    ??0MonitoredCritSecLocker@@QEAA@AEAVAutoMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(AutoMonitoredCritSec &,bool)
0x140009527  test    rdi, rdi
0x14000952a  jnz     short loc_140009581
0x14000952c  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, rdi; LogAdapter::Logger * LogAdapter::g_Logger
0x140009533  mov     ebx, 80004003h
0x140009538  mov     dword ptr [rbp+var_10], ebx
0x14000953b  jz      short loc_140009577
0x14000953d  mov     edi, 3
0x140009542  lea     r8, aNoWorkerResult; "No worker result specified"
0x140009549  mov     edx, edi
0x14000954b  call    ??$LogPartial@$$V@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogPartial<>(LogAdapter::LogLevel,char const * const)
0x140009550  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009557  lea     rax, [rbp+var_10]
0x14000955b  mov     qword ptr [rbp+var_30], rax
0x14000955f  lea     r9, asc_140030534; ": {}"
0x140009566  lea     rax, [rbp+var_30]
0x14000956a  mov     r8d, edi
0x14000956d  mov     qword ptr [rsp+60h+var_40], rax
0x140009572  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140009577  mov     edx, 34h ; '4'
0x14000957c  jmp     loc_140009636
0x140009581  mov     rax, [rbx+40h]
0x140009585  test    rax, rax
0x140009588  jnz     loc_14000964B
0x14000958e  lea     rcx, [rbp+var_10]
0x140009592  mov     [rbp+var_10], rax
0x140009596  call    ??$Allocate@$$V@?$AutoNewPtr@VCCbsWorker@@@Windows@@QEAAPEAVCCbsWorker@@XZ; Windows::AutoNewPtr<CCbsWorker>::Allocate<>(void)
0x14000959b  test    rax, rax
0x14000959e  jnz     short loc_1400095BB
0x1400095a0  mov     rcx, [rbp+var_10]
0x1400095a4  test    rcx, rcx
0x1400095a7  jz      short loc_1400095E5
0x1400095a9  mov     rax, [rcx]
0x1400095ac  mov     edx, 1
0x1400095b1  mov     rax, [rax]
0x1400095b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095b9  jmp     short loc_1400095E5
0x1400095bb  mov     rdx, [rbp+var_10]
0x1400095bf  test    rdx, rdx
0x1400095c2  jz      short loc_1400095D3
0x1400095c4  mov     rax, [rdx+8]
0x1400095c8  add     rdx, 8
0x1400095cc  movsxd  rcx, dword ptr [rax+4]
0x1400095d0  add     rdx, rcx
0x1400095d3  lea     rcx, [rbx+40h]
0x1400095d7  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x1400095dc  mov     rax, [rbx+40h]
0x1400095e0  test    rax, rax
0x1400095e3  jnz     short loc_14000964B
0x1400095e5  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, 0; LogAdapter::Logger * LogAdapter::g_Logger
0x1400095ed  mov     ebx, 8007000Eh
0x1400095f2  mov     dword ptr [rbp+var_10], ebx
0x1400095f5  jz      short loc_140009631
0x1400095f7  mov     edi, 3
0x1400095fc  lea     r8, aFailedToAlloca_0; "Failed to allocate new CBS worker."
0x140009603  mov     edx, edi
0x140009605  call    ??$LogPartial@$$V@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogPartial<>(LogAdapter::LogLevel,char const * const)
0x14000960a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009611  lea     rax, [rbp+var_10]
0x140009615  mov     qword ptr [rbp+var_30], rax
0x140009619  lea     r9, asc_140030534; ": {}"
0x140009620  lea     rax, [rbp+var_30]
0x140009624  mov     r8d, edi
0x140009627  mov     qword ptr [rsp+60h+var_40], rax; int
0x14000962c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140009631  mov     edx, 38h ; '8'; void *
0x140009636  mov     rcx, [rbp+8]; this
0x14000963a  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\tiworker\\tiworkerc"...
0x140009641  mov     r9d, ebx; char *
0x140009644  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009649  jmp     short loc_140009660
0x14000964b  mov     [rdi], rax
0x14000964e  mov     rcx, [rbx+40h]
0x140009652  mov     rax, [rcx]
0x140009655  mov     rax, [rax+8]
0x140009659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000965e  xor     ebx, ebx
0x140009660  lea     rcx, [rbp+var_28]; this
0x140009664  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x140009669  mov     eax, ebx
0x14000966b  mov     rcx, [rbp+var_8]
0x14000966f  xor     rcx, rsp; StackCookie
0x140009672  call    __security_check_cookie
0x140009677  lea     r11, [rsp+60h+var_s0]
0x14000967c  mov     rbx, [r11+20h]
0x140009680  mov     rdi, [r11+28h]
0x140009684  mov     rsp, r11
0x140009687  pop     rbp
0x140009688  retn
```
