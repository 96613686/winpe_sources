# Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::~IsolationEnvironment1(void)

- ea: `0x180054504`
- end: `0x1800545e9`
- name: `??1IsolationEnvironment1@Preview@IsolationEnvironment@AI@Windows@@UEAA@XZ`
- size: `229`
- prototype: `void __fastcall(Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1 *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004fe90`

## callees

- `0x18001045c`
- `0x180012ad0`
- `0x180054504`
- `0x18005469c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054571`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054571`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005454e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005454e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054538`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054538`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005457e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054596`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005457e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054596`

## pseudocode

```c
void __fastcall Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::~IsolationEnvironment1(
        Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1 *this)
{
  RTL_SRWLOCK *v2; // rbx
  int v3; // edi
  DWORD CurrentThreadId; // ebp
  __int64 v5; // rcx

  *(_QWORD *)this = &Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::`vftable';
  *((_QWORD *)this + 1) = &Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'};
  v2 = 0;
  v3 = dword_1800B9160;
  CurrentThreadId = GetCurrentThreadId();
  if ( v3 != CurrentThreadId )
  {
    v2 = &g_lock;
    AcquireSRWLockExclusive(&g_lock);
    dword_1800B9160 = CurrentThreadId;
  }
  Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::Cleanup_DropsLock(this);
  if ( v2 )
  {
    LODWORD(v2[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v2);
  }
  WindowsDeleteString(*((HSTRING *)this + 22));
  *((_QWORD *)this + 22) = 0;
  WindowsDeleteString(*((HSTRING *)this + 21));
  *((_QWORD *)this + 21) = 0;
  std::wstring::~wstring((char **)this + 17);
  std::wstring::~wstring((char **)this + 13);
  std::wstring::~wstring((char **)this + 9);
  std::wstring::~wstring((char **)this + 5);
  v5 = *((_QWORD *)this + 4);
  if ( v5 < 0 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(2 * v5);
}

```

## disassembly

```asm
0x180054504  push    rbx
0x180054506  push    rbp
0x180054507  push    rsi
0x180054508  push    rdi
0x180054509  sub     rsp, 28h
0x18005450d  mov     rsi, rcx
0x180054510  lea     rax, ??_7IsolationEnvironment1@Preview@IsolationEnvironment@AI@Windows@@6B@; const Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::`vftable'
0x180054517  mov     [rcx], rax
0x18005451a  lea     rax, ??_7IsolationEnvironment1@Preview@IsolationEnvironment@AI@Windows@@6BIWeakReferenceSource@@@; const Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::`vftable'{for `IWeakReferenceSource'}
0x180054521  mov     [rcx+8], rax
0x180054525  lea     rax, ??_7IsolationEnvironment1@Preview@IsolationEnvironment@AI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'}
0x18005452c  mov     [rcx+10h], rax
0x180054530  xor     ebx, ebx
0x180054532  mov     edi, cs:dword_1800B9160
0x180054538  call    cs:__imp_GetCurrentThreadId
0x18005453e  mov     ebp, eax
0x180054540  cmp     edi, eax
0x180054542  jz      short loc_18005455A
0x180054544  lea     rbx, ?g_lock@@3Vchecked_srwlock@@A; checked_srwlock g_lock
0x18005454b  mov     rcx, rbx; SRWLock
0x18005454e  call    cs:__imp_AcquireSRWLockExclusive
0x180054554  mov     cs:dword_1800B9160, ebp
0x18005455a  mov     rcx, rsi; this
0x18005455d  call    ?Cleanup_DropsLock@IsolationEnvironment1@Preview@IsolationEnvironment@AI@Windows@@AEAAJXZ; Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::Cleanup_DropsLock(void)
0x180054562  test    rbx, rbx
0x180054565  jz      short loc_180054577
0x180054567  mov     dword ptr [rbx+8], 0
0x18005456e  mov     rcx, rbx; SRWLock
0x180054571  call    cs:__imp_ReleaseSRWLockExclusive
0x180054577  mov     rcx, [rsi+0B0h]; string
0x18005457e  call    cs:__imp_WindowsDeleteString
0x180054584  mov     qword ptr [rsi+0B0h], 0
0x18005458f  mov     rcx, [rsi+0A8h]; string
0x180054596  call    cs:__imp_WindowsDeleteString
0x18005459c  mov     qword ptr [rsi+0A8h], 0
0x1800545a7  lea     rcx, [rsi+88h]
0x1800545ae  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800545b3  lea     rcx, [rsi+68h]
0x1800545b7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800545bc  lea     rcx, [rsi+48h]
0x1800545c0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800545c5  lea     rcx, [rsi+28h]
0x1800545c9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800545ce  mov     rcx, [rsi+20h]
0x1800545d2  test    rcx, rcx
0x1800545d5  jns     short loc_1800545E0
0x1800545d7  add     rcx, rcx
0x1800545da  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800545df  nop
0x1800545e0  add     rsp, 28h
0x1800545e4  pop     rdi
0x1800545e5  pop     rsi
0x1800545e6  pop     rbp
0x1800545e7  pop     rbx
0x1800545e8  retn
```
