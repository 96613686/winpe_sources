# AppV::Client::Service::AppVClientImpl::SetEventFilter(long)

- ea: `0x140036f10`
- end: `0x140037081`
- name: `?SetEventFilter@AppVClientImpl@Service@Client@AppV@@UEAAJJ@Z`
- size: `369`
- prototype: `int(AppV::Client::Service::AppVClientImpl *__hidden this, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x140004280`
- `0x140008224`
- `0x1400233dc`
- `0x140028e00`
- `0x1400355c4`
- `0x140036f10`
- `0x14003a198`
- `0x14003a24c`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x140036fb6`
- `ADVAPI32!EventActivityIdControl` at `0x140037051`
- `ADVAPI32!EventActivityIdControl` at `0x140036fb6`
- `ADVAPI32!EventActivityIdControl` at `0x140037051`
- `KERNEL32!GetCurrentThreadId` at `0x140036f73`
- `KERNEL32!GetCurrentThreadId` at `0x140036f73`
- `KERNEL32!LeaveCriticalSection` at `0x140036f98`
- `KERNEL32!LeaveCriticalSection` at `0x140037033`
- `KERNEL32!LeaveCriticalSection` at `0x140036f98`
- `KERNEL32!LeaveCriticalSection` at `0x140037033`
- `KERNEL32!EnterCriticalSection` at `0x140036f60`
- `KERNEL32!EnterCriticalSection` at `0x140036f60`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppV::Client::Service::AppVClientImpl::SetEventFilter(
        AppV::Client::Service::AppVClientImpl *this,
        int a2)
{
  DWORD *v4; // rdi
  unsigned int v5; // esi
  bool v6; // zf
  __int64 v7; // rdx
  __int64 v8; // r8
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  _BYTE v13[8]; // [rsp+20h] [rbp-60h] BYREF
  unsigned __int64 v14; // [rsp+28h] [rbp-58h] BYREF
  _BYTE v15[16]; // [rsp+30h] [rbp-50h] BYREF
  int v16; // [rsp+40h] [rbp-40h]
  _BYTE v17[4]; // [rsp+48h] [rbp-38h] BYREF
  GUID ActivityId; // [rsp+4Ch] [rbp-34h] BYREF

  AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>((__int64)v17);
  AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(
    (AppV::Client::Service::SmartComMethodLogger *)v15,
    L"SetEventFilter");
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  ++*((_DWORD *)this + 26);
  v4 = (DWORD *)((char *)this + 108);
  if ( *((_DWORD *)this + 26) == 1 )
    *v4 = GetCurrentThreadId();
  if ( !*((_QWORD *)this + 14) )
  {
    v5 = -2147418113;
    v16 = -2147418113;
LABEL_5:
    v6 = (*((_DWORD *)this + 26))-- == 1;
    if ( v6 )
      *v4 = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)v15,
      v7,
      v8);
    if ( v17[0] )
      EventActivityIdControl(2u, &ActivityId);
    return v5;
  }
  v13[0] = 0;
  v14 = 0;
  v10 = AppV::Client::Service::AppVClientImpl::APICaller::Initialize(
          (AppV::Client::Service::AppVClientImpl::APICaller *)v13,
          0,
          &v14);
  v5 = v10;
  if ( v10 < 0 )
  {
    v16 = v10;
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v13);
    goto LABEL_5;
  }
  if ( (AppV::Client::Service::AppVClientImpl::RegisterSubscriber(*((struct IAppVClientEventSink **)this + 14), a2)
      & 0x8000000000LL) == 0 )
  {
    v5 = -2147467259;
    v16 = -2147467259;
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v13);
    goto LABEL_5;
  }
  v16 = 0;
  AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v13);
  v6 = (*((_DWORD *)this + 26))-- == 1;
  if ( v6 )
    *v4 = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
    (AppV::Client::Service::SmartComMethodLogger *)v15,
    v11,
    v12);
  if ( v17[0] )
    EventActivityIdControl(2u, &ActivityId);
  return 0;
}

```

## disassembly

```asm
0x140036f10  mov     [rsp-28h+arg_10], rbx
0x140036f15  mov     [rsp-28h+arg_18], rsi
0x140036f1a  push    rbp
0x140036f1b  push    rdi
0x140036f1c  push    r12
0x140036f1e  push    r14
0x140036f20  push    r15
0x140036f22  mov     rbp, rsp
0x140036f25  sub     rsp, 80h
0x140036f2c  mov     rax, cs:__security_cookie
0x140036f33  xor     rax, rsp
0x140036f36  mov     [rbp+var_10], rax
0x140036f3a  mov     r15d, edx
0x140036f3d  mov     r14, rcx
0x140036f40  lea     rcx, [rbp+var_38]
0x140036f44  call    ??0?$ScopedActivity@VUserModeActivityIdControl@ETW@AppV@@@ETW@AppV@@QEAA@XZ; AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>(void)
0x140036f49  lea     rdx, aSeteventfilter; "SetEventFilter"
0x140036f50  lea     rcx, [rbp+var_50]; this
0x140036f54  call    ??0SmartComMethodLogger@Service@Client@AppV@@QEAA@PEB_W@Z; AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(wchar_t const *)
0x140036f59  lea     rbx, [r14+40h]
0x140036f5d  mov     rcx, rbx; lpCriticalSection
0x140036f60  call    cs:__imp_EnterCriticalSection
0x140036f66  inc     dword ptr [rbx+28h]
0x140036f69  lea     rdi, [rbx+2Ch]
0x140036f6d  cmp     dword ptr [rbx+28h], 1
0x140036f71  jnz     short loc_140036F7B
0x140036f73  call    cs:__imp_GetCurrentThreadId
0x140036f79  mov     [rdi], eax
0x140036f7b  xor     r12d, r12d
0x140036f7e  cmp     [r14+70h], r12
0x140036f82  jnz     short loc_140036FC3
0x140036f84  mov     esi, 8000FFFFh
0x140036f89  mov     [rbp+var_40], esi
0x140036f8c  sub     dword ptr [rbx+28h], 1
0x140036f90  jnz     short loc_140036F95
0x140036f92  mov     [rdi], r12d
0x140036f95  mov     rcx, rbx; lpCriticalSection
0x140036f98  call    cs:__imp_LeaveCriticalSection
0x140036f9e  lea     rcx, [rbp+var_50]; this
0x140036fa2  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x140036fa7  cmp     [rbp+var_38], r12b
0x140036fab  jz      short loc_140036FBC
0x140036fad  lea     rdx, [rbp+ActivityId]; ActivityId
0x140036fb1  mov     ecx, 2; ControlCode
0x140036fb6  call    cs:__imp_EventActivityIdControl
0x140036fbc  mov     eax, esi
0x140036fbe  jmp     loc_140037059
0x140036fc3  mov     [rbp+var_60], r12b
0x140036fc7  mov     [rbp+var_58], r12
0x140036fcb  lea     r8, [rbp+var_58]; unsigned __int64 *
0x140036fcf  xor     edx, edx; bool
0x140036fd1  lea     rcx, [rbp+var_60]; this
0x140036fd5  call    ?Initialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJ_NAEA_K@Z; AppV::Client::Service::AppVClientImpl::APICaller::Initialize(bool,unsigned __int64 &)
0x140036fda  mov     esi, eax
0x140036fdc  test    eax, eax
0x140036fde  jns     short loc_140036FEF
0x140036fe0  mov     [rbp+var_40], eax
0x140036fe3  lea     rcx, [rbp+var_60]; this
0x140036fe7  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140036fec  nop
0x140036fed  jmp     short loc_140036F8C
0x140036fef  mov     edx, r15d; int
0x140036ff2  mov     rcx, [r14+70h]; struct IAppVClientEventSink *
0x140036ff6  call    ?RegisterSubscriber@AppVClientImpl@Service@Client@AppV@@CA_KPEAUIAppVClientEventSink@@J@Z; AppV::Client::Service::AppVClientImpl::RegisterSubscriber(IAppVClientEventSink *,long)
0x140036ffb  bt      rax, 27h ; '''
0x140037000  jb      short loc_140037019
0x140037002  mov     esi, 80004005h
0x140037007  mov     [rbp+var_40], esi
0x14003700a  lea     rcx, [rbp+var_60]; this
0x14003700e  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140037013  nop
0x140037014  jmp     loc_140036F8C
0x140037019  mov     [rbp+var_40], r12d
0x14003701d  lea     rcx, [rbp+var_60]; this
0x140037021  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140037026  nop
0x140037027  sub     dword ptr [rbx+28h], 1
0x14003702b  jnz     short loc_140037030
0x14003702d  mov     [rdi], r12d
0x140037030  mov     rcx, rbx; lpCriticalSection
0x140037033  call    cs:__imp_LeaveCriticalSection
0x140037039  lea     rcx, [rbp+var_50]; this
0x14003703d  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x140037042  cmp     [rbp+var_38], r12b
0x140037046  jz      short loc_140037057
0x140037048  lea     rdx, [rbp+ActivityId]; ActivityId
0x14003704c  mov     ecx, 2; ControlCode
0x140037051  call    cs:__imp_EventActivityIdControl
0x140037057  xor     eax, eax
0x140037059  mov     rcx, [rbp+var_10]
0x14003705d  xor     rcx, rsp; StackCookie
0x140037060  call    __security_check_cookie
0x140037065  lea     r11, [rsp+80h+var_s0]
0x14003706d  mov     rbx, [r11+40h]
0x140037071  mov     rsi, [r11+48h]
0x140037075  mov     rsp, r11
0x140037078  pop     r15
0x14003707a  pop     r14
0x14003707c  pop     r12
0x14003707e  pop     rdi
0x14003707f  pop     rbp
0x140037080  retn
```
