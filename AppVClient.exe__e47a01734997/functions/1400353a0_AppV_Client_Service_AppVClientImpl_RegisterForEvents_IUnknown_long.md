# AppV::Client::Service::AppVClientImpl::RegisterForEvents(IUnknown *,long)

- ea: `0x1400353a0`
- end: `0x1400355bc`
- name: `?RegisterForEvents@AppVClientImpl@Service@Client@AppV@@UEAAJPEAUIUnknown@@J@Z`
- size: `540`
- prototype: `int(AppV::Client::Service::AppVClientImpl *__hidden this, struct IUnknown *, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x140004280`
- `0x140008224`
- `0x1400233dc`
- `0x140028e00`
- `0x1400353a0`
- `0x1400355c4`
- `0x1400383a0`
- `0x14003a198`
- `0x14003a24c`
- `0x14006a010`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x14003540b`
- `ADVAPI32!EventActivityIdControl` at `0x140035591`
- `ADVAPI32!EventActivityIdControl` at `0x14003540b`
- `ADVAPI32!EventActivityIdControl` at `0x140035591`
- `KERNEL32!GetCurrentThreadId` at `0x1400354f1`
- `KERNEL32!GetCurrentThreadId` at `0x1400354f1`
- `KERNEL32!LeaveCriticalSection` at `0x140035552`
- `KERNEL32!LeaveCriticalSection` at `0x140035552`
- `KERNEL32!EnterCriticalSection` at `0x1400354db`
- `KERNEL32!EnterCriticalSection` at `0x1400354db`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppV::Client::Service::AppVClientImpl::RegisterForEvents(
        AppV::Client::Service::AppVClientImpl *this,
        struct IUnknown *a2,
        int a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // ebx
  int v10; // eax
  int v11; // eax
  BOOL v12; // edi
  struct IAppVClientEventSink *v13; // rcx
  struct IAppVClientEventSink *v14; // r14
  __int64 v15; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  _BYTE v19[8]; // [rsp+20h] [rbp-60h] BYREF
  struct IAppVClientEventSink *v20; // [rsp+28h] [rbp-58h] BYREF
  _BYTE v21[16]; // [rsp+30h] [rbp-50h] BYREF
  int v22; // [rsp+40h] [rbp-40h]
  unsigned __int64 v23; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v24[4]; // [rsp+50h] [rbp-30h] BYREF
  GUID ActivityId; // [rsp+54h] [rbp-2Ch] BYREF

  AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>((__int64)v24);
  AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(
    (AppV::Client::Service::SmartComMethodLogger *)v21,
    L"RegisterForEvents");
  if ( !a2 )
  {
    v8 = -2147024809;
    v22 = -2147024809;
LABEL_3:
    AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)v21,
      v6,
      v7);
    if ( v24[0] )
      EventActivityIdControl(2u, &ActivityId);
    return v8;
  }
  v19[0] = 0;
  v23 = 0;
  v10 = AppV::Client::Service::AppVClientImpl::APICaller::Initialize(
          (AppV::Client::Service::AppVClientImpl::APICaller *)v19,
          0,
          &v23);
  v8 = v10;
  if ( v10 < 0 )
  {
    v22 = v10;
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v19);
    goto LABEL_3;
  }
  v20 = 0;
  v11 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IAppVClientEventSink **))a2->lpVtbl->QueryInterface)(
          a2,
          &IID_IAppVClientEventSink,
          &v20);
  v8 = v11;
  if ( v11 < 0 )
  {
    v22 = v11;
    if ( v20 )
      (*(void (__fastcall **)(struct IAppVClientEventSink *))(*(_QWORD *)v20 + 16LL))(v20);
LABEL_11:
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v19);
    goto LABEL_3;
  }
  if ( (AppV::Client::Service::AppVClientImpl::RegisterSubscriber(v20, a3) & 0x8000000000LL) == 0 )
  {
    v8 = -2147467259;
    v22 = -2147467259;
    if ( v20 )
      (*(void (__fastcall **)(struct IAppVClientEventSink *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_11;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( ++*((_DWORD *)this + 26) == 1 )
    *((_DWORD *)this + 27) = GetCurrentThreadId();
  v12 = 0;
  v13 = (struct IAppVClientEventSink *)*((_QWORD *)this + 14);
  if ( v13 && v20 != v13 )
    v12 = (AppV::Client::Service::AppVClientImpl::UnregisterSubscriber(v13) & 0x8000000000LL) == 0;
  v14 = v20;
  v20 = 0;
  v15 = *((_QWORD *)this + 14);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  *((_QWORD *)this + 14) = v14;
  v22 = v12;
  if ( (*((_DWORD *)this + 26))-- == 1 )
    *((_DWORD *)this + 27) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( v20 )
    (*(void (__fastcall **)(struct IAppVClientEventSink *))(*(_QWORD *)v20 + 16LL))(v20);
  AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v19);
  AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
    (AppV::Client::Service::SmartComMethodLogger *)v21,
    v17,
    v18);
  if ( v24[0] )
    EventActivityIdControl(2u, &ActivityId);
  return v12;
}

```

## disassembly

```asm
0x1400353a0  mov     [rsp-28h+arg_18], rbx
0x1400353a5  push    rbp
0x1400353a6  push    rsi
0x1400353a7  push    rdi
0x1400353a8  push    r12
0x1400353aa  push    r14
0x1400353ac  mov     rbp, rsp
0x1400353af  sub     rsp, 80h
0x1400353b6  mov     rax, cs:__security_cookie
0x1400353bd  xor     rax, rsp
0x1400353c0  mov     [rbp+var_8], rax
0x1400353c4  mov     r14d, r8d
0x1400353c7  mov     rdi, rdx
0x1400353ca  mov     rsi, rcx
0x1400353cd  lea     rcx, [rbp+var_30]
0x1400353d1  call    ??0?$ScopedActivity@VUserModeActivityIdControl@ETW@AppV@@@ETW@AppV@@QEAA@XZ; AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>(void)
0x1400353d6  lea     rdx, aRegisterforeve; "RegisterForEvents"
0x1400353dd  lea     rcx, [rbp+var_50]; this
0x1400353e1  call    ??0SmartComMethodLogger@Service@Client@AppV@@QEAA@PEB_W@Z; AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(wchar_t const *)
0x1400353e6  test    rdi, rdi
0x1400353e9  jnz     short loc_140035418
0x1400353eb  mov     ebx, 80070057h
0x1400353f0  mov     [rbp+var_40], ebx
0x1400353f3  lea     rcx, [rbp+var_50]; this
0x1400353f7  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x1400353fc  cmp     [rbp+var_30], 0
0x140035400  jz      short loc_140035411
0x140035402  lea     rdx, [rbp+ActivityId]; ActivityId
0x140035406  mov     ecx, 2; ControlCode
0x14003540b  call    cs:__imp_EventActivityIdControl
0x140035411  mov     eax, ebx
0x140035413  jmp     loc_140035599
0x140035418  mov     [rbp+var_60], 0
0x14003541c  mov     [rbp+var_38], 0
0x140035424  lea     r8, [rbp+var_38]; unsigned __int64 *
0x140035428  xor     edx, edx; bool
0x14003542a  lea     rcx, [rbp+var_60]; this
0x14003542e  call    ?Initialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJ_NAEA_K@Z; AppV::Client::Service::AppVClientImpl::APICaller::Initialize(bool,unsigned __int64 &)
0x140035433  mov     ebx, eax
0x140035435  test    eax, eax
0x140035437  jns     short loc_140035448
0x140035439  mov     [rbp+var_40], eax
0x14003543c  lea     rcx, [rbp+var_60]; this
0x140035440  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140035445  nop
0x140035446  jmp     short loc_1400353F3
0x140035448  mov     [rbp+var_58], 0
0x140035450  mov     rax, [rdi]
0x140035453  lea     r8, [rbp+var_58]
0x140035457  lea     rdx, IID_IAppVClientEventSink
0x14003545e  mov     rcx, rdi
0x140035461  mov     rax, [rax]
0x140035464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035469  mov     ebx, eax
0x14003546b  test    eax, eax
0x14003546d  jns     short loc_140035497
0x14003546f  mov     [rbp+var_40], eax
0x140035472  mov     rcx, [rbp+var_58]
0x140035476  test    rcx, rcx
0x140035479  jz      short loc_140035488
0x14003547b  mov     rdx, [rcx]
0x14003547e  mov     rax, [rdx+10h]
0x140035482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035487  nop
0x140035488  lea     rcx, [rbp+var_60]; this
0x14003548c  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140035491  nop
0x140035492  jmp     loc_1400353F3
0x140035497  mov     edx, r14d; int
0x14003549a  mov     rcx, [rbp+var_58]; struct IAppVClientEventSink *
0x14003549e  call    ?RegisterSubscriber@AppVClientImpl@Service@Client@AppV@@CA_KPEAUIAppVClientEventSink@@J@Z; AppV::Client::Service::AppVClientImpl::RegisterSubscriber(IAppVClientEventSink *,long)
0x1400354a3  bt      rax, 27h ; '''
0x1400354a8  jb      short loc_1400354D7
0x1400354aa  mov     ebx, 80004005h
0x1400354af  mov     [rbp+var_40], ebx
0x1400354b2  mov     rcx, [rbp+var_58]
0x1400354b6  test    rcx, rcx
0x1400354b9  jz      short loc_1400354C8
0x1400354bb  mov     rax, [rcx]
0x1400354be  mov     rax, [rax+10h]
0x1400354c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400354c7  nop
0x1400354c8  lea     rcx, [rbp+var_60]; this
0x1400354cc  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x1400354d1  nop
0x1400354d2  jmp     loc_1400353F3
0x1400354d7  lea     rcx, [rsi+40h]; lpCriticalSection
0x1400354db  call    cs:__imp_EnterCriticalSection
0x1400354e1  mov     r14d, 1
0x1400354e7  add     [rsi+68h], r14d
0x1400354eb  cmp     [rsi+68h], r14d
0x1400354ef  jnz     short loc_1400354FA
0x1400354f1  call    cs:__imp_GetCurrentThreadId
0x1400354f7  mov     [rsi+6Ch], eax
0x1400354fa  xor     edi, edi
0x1400354fc  mov     rcx, [rsi+70h]; struct IAppVClientEventSink *
0x140035500  test    rcx, rcx
0x140035503  jz      short loc_140035519
0x140035505  cmp     [rbp+var_58], rcx
0x140035509  jz      short loc_140035519
0x14003550b  call    ?UnregisterSubscriber@AppVClientImpl@Service@Client@AppV@@CA_KPEAUIAppVClientEventSink@@@Z; AppV::Client::Service::AppVClientImpl::UnregisterSubscriber(IAppVClientEventSink *)
0x140035510  bt      rax, 27h ; '''
0x140035515  cmovnb  edi, r14d
0x140035519  mov     r14, [rbp+var_58]
0x14003551d  mov     [rbp+var_58], 0
0x140035525  mov     rcx, [rsi+70h]
0x140035529  test    rcx, rcx
0x14003552c  jz      short loc_14003553A
0x14003552e  mov     rax, [rcx]
0x140035531  mov     rax, [rax+10h]
0x140035535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003553a  mov     [rsi+70h], r14
0x14003553e  mov     [rbp+var_40], edi
0x140035541  sub     dword ptr [rsi+68h], 1
0x140035545  jnz     short loc_14003554E
0x140035547  mov     dword ptr [rsi+6Ch], 0
0x14003554e  lea     rcx, [rsi+40h]; lpCriticalSection
0x140035552  call    cs:__imp_LeaveCriticalSection
0x140035558  nop
0x140035559  mov     rcx, [rbp+var_58]
0x14003555d  test    rcx, rcx
0x140035560  jz      short loc_14003556F
0x140035562  mov     rax, [rcx]
0x140035565  mov     rax, [rax+10h]
0x140035569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003556e  nop
0x14003556f  lea     rcx, [rbp+var_60]; this
0x140035573  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140035578  nop
0x140035579  lea     rcx, [rbp+var_50]; this
0x14003557d  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x140035582  cmp     [rbp+var_30], 0
0x140035586  jz      short loc_140035597
0x140035588  lea     rdx, [rbp+ActivityId]; ActivityId
0x14003558c  mov     ecx, 2; ControlCode
0x140035591  call    cs:__imp_EventActivityIdControl
0x140035597  mov     eax, edi
0x140035599  mov     rcx, [rbp+var_8]
0x14003559d  xor     rcx, rsp; StackCookie
0x1400355a0  call    __security_check_cookie
0x1400355a5  mov     rbx, [rsp+80h+arg_18]
0x1400355ad  add     rsp, 80h
0x1400355b4  pop     r14
0x1400355b6  pop     r12
0x1400355b8  pop     rdi
0x1400355b9  pop     rsi
0x1400355ba  pop     rbp
0x1400355bb  retn
```
