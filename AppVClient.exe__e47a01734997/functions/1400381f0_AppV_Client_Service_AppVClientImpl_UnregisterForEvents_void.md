# AppV::Client::Service::AppVClientImpl::UnregisterForEvents(void)

- ea: `0x1400381f0`
- end: `0x140038399`
- name: `?UnregisterForEvents@AppVClientImpl@Service@Client@AppV@@UEAAJXZ`
- size: `425`
- prototype: `__int64 __fastcall(AppV::Client::Service::AppVClientImpl *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x140004280`
- `0x140008224`
- `0x1400233dc`
- `0x140028e00`
- `0x1400381f0`
- `0x1400383a0`
- `0x14003a198`
- `0x14003a24c`
- `0x14006a010`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x14003828c`
- `ADVAPI32!EventActivityIdControl` at `0x1400382ee`
- `ADVAPI32!EventActivityIdControl` at `0x140038375`
- `ADVAPI32!EventActivityIdControl` at `0x14003828c`
- `ADVAPI32!EventActivityIdControl` at `0x1400382ee`
- `ADVAPI32!EventActivityIdControl` at `0x140038375`
- `KERNEL32!GetCurrentThreadId` at `0x140038249`
- `KERNEL32!GetCurrentThreadId` at `0x140038249`
- `KERNEL32!LeaveCriticalSection` at `0x14003826e`
- `KERNEL32!LeaveCriticalSection` at `0x1400382d0`
- `KERNEL32!LeaveCriticalSection` at `0x140038357`
- `KERNEL32!LeaveCriticalSection` at `0x14003826e`
- `KERNEL32!LeaveCriticalSection` at `0x1400382d0`
- `KERNEL32!LeaveCriticalSection` at `0x140038357`
- `KERNEL32!EnterCriticalSection` at `0x140038236`
- `KERNEL32!EnterCriticalSection` at `0x140038236`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppV::Client::Service::AppVClientImpl::UnregisterForEvents(
        AppV::Client::Service::AppVClientImpl *this)
{
  char *v2; // rbx
  DWORD *v3; // rdi
  unsigned int v4; // esi
  bool v5; // zf
  __int64 v6; // rdx
  __int64 v7; // r8
  int v9; // eax
  unsigned int v10; // r14d
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  _BYTE v16[8]; // [rsp+20h] [rbp-39h] BYREF
  unsigned __int64 v17; // [rsp+28h] [rbp-31h] BYREF
  _BYTE v18[16]; // [rsp+30h] [rbp-29h] BYREF
  int v19; // [rsp+40h] [rbp-19h]
  _BYTE v20[4]; // [rsp+48h] [rbp-11h] BYREF
  GUID ActivityId; // [rsp+4Ch] [rbp-Dh] BYREF

  AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>((__int64)v20);
  AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(
    (AppV::Client::Service::SmartComMethodLogger *)v18,
    L"UnregisterForEvents");
  v2 = (char *)this + 64;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  ++*((_DWORD *)this + 26);
  v3 = (DWORD *)((char *)this + 108);
  if ( *((_DWORD *)this + 26) == 1 )
    *v3 = GetCurrentThreadId();
  if ( !*((_QWORD *)this + 14) )
  {
    v4 = -2147418113;
    v19 = -2147418113;
LABEL_5:
    v5 = (*((_DWORD *)v2 + 10))-- == 1;
    if ( v5 )
      *v3 = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)v2);
    AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)v18,
      v6,
      v7);
    if ( v20[0] )
      EventActivityIdControl(2u, &ActivityId);
    return v4;
  }
  v16[0] = 0;
  v17 = 0;
  v9 = AppV::Client::Service::AppVClientImpl::APICaller::Initialize(
         (AppV::Client::Service::AppVClientImpl::APICaller *)v16,
         0,
         &v17);
  v10 = v9;
  if ( v9 >= 0 )
  {
    if ( (AppV::Client::Service::AppVClientImpl::UnregisterSubscriber(*((struct IAppVClientEventSink **)this + 14))
        & 0x8000000000LL) == 0 )
    {
      v4 = -2147467259;
      v19 = -2147467259;
      AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v16);
      goto LABEL_5;
    }
    v13 = *((_QWORD *)this + 14);
    if ( v13 )
    {
      *((_QWORD *)this + 14) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v19 = 0;
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v16);
    v5 = (*((_DWORD *)this + 26))-- == 1;
    if ( v5 )
      *v3 = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)v18,
      v14,
      v15);
    if ( v20[0] )
      EventActivityIdControl(2u, &ActivityId);
    return 0;
  }
  else
  {
    v19 = v9;
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v16);
    v5 = (*((_DWORD *)this + 26))-- == 1;
    if ( v5 )
      *v3 = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)v18,
      v11,
      v12);
    if ( v20[0] )
      EventActivityIdControl(2u, &ActivityId);
    return v10;
  }
}

```

## disassembly

```asm
0x1400381f0  push    rbp
0x1400381f2  push    rbx
0x1400381f3  push    rsi
0x1400381f4  push    rdi
0x1400381f5  push    r14
0x1400381f7  push    r15
0x1400381f9  lea     rbp, [rsp-2Fh]
0x1400381fe  sub     rsp, 88h
0x140038205  mov     rax, cs:__security_cookie
0x14003820c  xor     rax, rsp
0x14003820f  mov     [rbp+57h+var_40], rax
0x140038213  mov     rsi, rcx
0x140038216  lea     rcx, [rbp+57h+var_68]
0x14003821a  call    ??0?$ScopedActivity@VUserModeActivityIdControl@ETW@AppV@@@ETW@AppV@@QEAA@XZ; AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>(void)
0x14003821f  lea     rdx, aUnregisterfore; "UnregisterForEvents"
0x140038226  lea     rcx, [rbp+57h+var_80]; this
0x14003822a  call    ??0SmartComMethodLogger@Service@Client@AppV@@QEAA@PEB_W@Z; AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(wchar_t const *)
0x14003822f  lea     rbx, [rsi+40h]
0x140038233  mov     rcx, rbx; lpCriticalSection
0x140038236  call    cs:__imp_EnterCriticalSection
0x14003823c  inc     dword ptr [rbx+28h]
0x14003823f  lea     rdi, [rbx+2Ch]
0x140038243  cmp     dword ptr [rbx+28h], 1
0x140038247  jnz     short loc_140038251
0x140038249  call    cs:__imp_GetCurrentThreadId
0x14003824f  mov     [rdi], eax
0x140038251  xor     r15d, r15d
0x140038254  cmp     [rsi+70h], r15
0x140038258  jnz     short loc_140038299
0x14003825a  mov     esi, 8000FFFFh
0x14003825f  mov     [rbp+57h+var_70], esi
0x140038262  sub     dword ptr [rbx+28h], 1
0x140038266  jnz     short loc_14003826B
0x140038268  mov     [rdi], r15d
0x14003826b  mov     rcx, rbx; lpCriticalSection
0x14003826e  call    cs:__imp_LeaveCriticalSection
0x140038274  lea     rcx, [rbp+57h+var_80]; this
0x140038278  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x14003827d  cmp     [rbp+57h+var_68], r15b
0x140038281  jz      short loc_140038292
0x140038283  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x140038287  mov     ecx, 2; ControlCode
0x14003828c  call    cs:__imp_EventActivityIdControl
0x140038292  mov     eax, esi
0x140038294  jmp     loc_14003837D
0x140038299  mov     [rbp+57h+var_90], r15b
0x14003829d  mov     [rbp+57h+var_88], r15
0x1400382a1  lea     r8, [rbp+57h+var_88]; unsigned __int64 *
0x1400382a5  xor     edx, edx; bool
0x1400382a7  lea     rcx, [rbp+57h+var_90]; this
0x1400382ab  call    ?Initialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJ_NAEA_K@Z; AppV::Client::Service::AppVClientImpl::APICaller::Initialize(bool,unsigned __int64 &)
0x1400382b0  mov     r14d, eax
0x1400382b3  test    eax, eax
0x1400382b5  jns     short loc_1400382FC
0x1400382b7  mov     [rbp+57h+var_70], eax
0x1400382ba  lea     rcx, [rbp+57h+var_90]; this
0x1400382be  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x1400382c3  nop
0x1400382c4  sub     dword ptr [rbx+28h], 1
0x1400382c8  jnz     short loc_1400382CD
0x1400382ca  mov     [rdi], r15d
0x1400382cd  mov     rcx, rbx; lpCriticalSection
0x1400382d0  call    cs:__imp_LeaveCriticalSection
0x1400382d6  lea     rcx, [rbp+57h+var_80]; this
0x1400382da  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x1400382df  cmp     [rbp+57h+var_68], r15b
0x1400382e3  jz      short loc_1400382F4
0x1400382e5  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1400382e9  mov     ecx, 2; ControlCode
0x1400382ee  call    cs:__imp_EventActivityIdControl
0x1400382f4  mov     eax, r14d
0x1400382f7  jmp     loc_14003837D
0x1400382fc  mov     rcx, [rsi+70h]; struct IAppVClientEventSink *
0x140038300  call    ?UnregisterSubscriber@AppVClientImpl@Service@Client@AppV@@CA_KPEAUIAppVClientEventSink@@@Z; AppV::Client::Service::AppVClientImpl::UnregisterSubscriber(IAppVClientEventSink *)
0x140038305  bt      rax, 27h ; '''
0x14003830a  jb      short loc_140038323
0x14003830c  mov     esi, 80004005h
0x140038311  mov     [rbp+57h+var_70], esi
0x140038314  lea     rcx, [rbp+57h+var_90]; this
0x140038318  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x14003831d  nop
0x14003831e  jmp     loc_140038262
0x140038323  mov     rcx, [rsi+70h]
0x140038327  test    rcx, rcx
0x14003832a  jz      short loc_14003833D
0x14003832c  mov     [rsi+70h], r15
0x140038330  mov     rax, [rcx]
0x140038333  mov     rax, [rax+10h]
0x140038337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003833c  nop
0x14003833d  mov     [rbp+57h+var_70], r15d
0x140038341  lea     rcx, [rbp+57h+var_90]; this
0x140038345  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x14003834a  nop
0x14003834b  sub     dword ptr [rbx+28h], 1
0x14003834f  jnz     short loc_140038354
0x140038351  mov     [rdi], r15d
0x140038354  mov     rcx, rbx; lpCriticalSection
0x140038357  call    cs:__imp_LeaveCriticalSection
0x14003835d  lea     rcx, [rbp+57h+var_80]; this
0x140038361  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x140038366  cmp     [rbp+57h+var_68], r15b
0x14003836a  jz      short loc_14003837B
0x14003836c  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x140038370  mov     ecx, 2; ControlCode
0x140038375  call    cs:__imp_EventActivityIdControl
0x14003837b  xor     eax, eax
0x14003837d  mov     rcx, [rbp+57h+var_40]
0x140038381  xor     rcx, rsp; StackCookie
0x140038384  call    __security_check_cookie
0x140038389  add     rsp, 88h
0x140038390  pop     r15
0x140038392  pop     r14
0x140038394  pop     rdi
0x140038395  pop     rsi
0x140038396  pop     rbx
0x140038397  pop     rbp
0x140038398  retn
```
