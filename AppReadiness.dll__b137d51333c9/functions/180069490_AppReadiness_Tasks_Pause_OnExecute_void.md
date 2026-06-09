# AppReadiness::Tasks::Pause::OnExecute(void)

- ea: `0x180069490`
- end: `0x180069623`
- name: `?OnExecute@Pause@Tasks@AppReadiness@@MEAAXXZ`
- size: `403`
- prototype: `void __fastcall(AppReadiness::Tasks::Pause *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002958`
- `0x1800148b0`
- `0x1800203d8`
- `0x180027a4c`
- `0x18003e210`
- `0x18003ecb4`
- `0x180069490`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800694d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800694d5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180069514`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180069514`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800694c6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800694c6`

## string_xrefs

- `0x1800694f5`: `Windows.System.Threading.ThreadPoolTimer`
- `0x180069539`: `Windows::Foundation::GetActivationFactory(HStringReference(RuntimeClass_Windows_System_Threading_ThreadPoolTimer).Get(), threadpool.GetAddressOf())`
- `0x180069526`: `onecoreuap\shell\appreadiness\src\tasks\pause.cpp`
- `0x1800695ad`: `onecoreuap\shell\appreadiness\src\tasks\pause.cpp`
- `0x180069532`: `AppReadiness::Tasks::Pause::OnExecute`
- `0x1800695b9`: `AppReadiness::Tasks::Pause::OnExecute`
- `0x1800695c0`: `threadpool->CreatePeriodicTimer(this, c_PulseTimeSpan, &timer)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall AppReadiness::Tasks::Pause::OnExecute(struct _FILETIME *this)
{
  int ActivationFactory; // eax
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, unsigned __int64, __int64, __int64 *); // rbx
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // [rsp+30h] [rbp-19h] BYREF
  __int64 v8; // [rsp+38h] [rbp-11h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-9h] BYREF
  HSTRING_HEADER pExceptionObject; // [rsp+48h] [rbp-1h] BYREF
  __int64 v11; // [rsp+60h] [rbp+17h]

  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &this[7]);
  GetSystemTimeAsFileTime(this + 31);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v7 = 0;
  v11 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &pExceptionObject,
    L"Windows.System.Threading.ThreadPoolTimer",
    0x29u,
    0x28u);
  ActivationFactory = RoGetActivationFactory(v11, &GUID_1a8a9d02_e482_461b_b8c7_8efad1cce590, &v7);
  if ( ActivationFactory < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&pExceptionObject,
      ActivationFactory,
      "Windows::Foundation::GetActivationFactory(HStringReference(RuntimeClass_Windows_System_Threading_ThreadPoolTimer)."
      "Get(), threadpool.GetAddressOf())",
      "AppReadiness::Tasks::Pause::OnExecute",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\pause.cpp",
      49);
    throw (Windows::HResultException *)&pExceptionObject;
  }
  v8 = 0;
  v3 = v7;
  v4 = *(__int64 (__fastcall **)(__int64, unsigned __int64, __int64, __int64 *))(*(_QWORD *)v7 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
  v5 = v4(v3, (unsigned __int64)&this[29] & -(__int64)(this != (struct _FILETIME *)32), 20000000, &v8);
  if ( v5 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&pExceptionObject,
      v5,
      "threadpool->CreatePeriodicTimer(this, c_PulseTimeSpan, &timer)",
      "AppReadiness::Tasks::Pause::OnExecute",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\pause.cpp",
      51);
    throw (Windows::HResultException *)&pExceptionObject;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
  v6 = v7;
  if ( v7 )
  {
    v7 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
}

```

## disassembly

```asm
0x180069490  push    rbp
0x180069492  push    rbx
0x180069493  push    rsi
0x180069494  push    rdi
0x180069495  lea     rbp, [rsp-3Fh]
0x18006949a  sub     rsp, 88h
0x1800694a1  mov     rax, cs:__security_cookie
0x1800694a8  xor     rax, rsp
0x1800694ab  mov     [rbp+57h+var_30], rax
0x1800694af  mov     rsi, rcx
0x1800694b2  lea     rdx, [rcx+38h]
0x1800694b6  lea     rcx, [rbp+57h+SRWLock]
0x1800694ba  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800694bf  lea     rcx, [rsi+0F8h]; lpSystemTimeAsFileTime
0x1800694c6  call    cs:__imp_GetSystemTimeAsFileTime
0x1800694cc  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800694d0  test    rcx, rcx
0x1800694d3  jz      short loc_1800694DB
0x1800694d5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800694db  mov     [rbp+57h+var_70], 0
0x1800694e3  mov     [rbp+57h+var_40], 0
0x1800694eb  mov     r9d, 28h ; '('; unsigned int
0x1800694f1  lea     r8d, [r9+1]; unsigned int
0x1800694f5  lea     rdx, ?RuntimeClass_Windows_System_Threading_ThreadPoolTimer@@3QBGB; "Windows.System.Threading.ThreadPoolTime"...
0x1800694fc  lea     rcx, [rbp+57h+pExceptionObject]; hstringHeader
0x180069500  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180069505  lea     r8, [rbp+57h+var_70]
0x180069509  lea     rdx, _GUID_1a8a9d02_e482_461b_b8c7_8efad1cce590
0x180069510  mov     rcx, [rbp+57h+var_40]
0x180069514  call    cs:__imp_RoGetActivationFactory
0x18006951a  test    eax, eax
0x18006951c  jns     short loc_18006955C
0x18006951e  mov     [rsp+0A0h+var_78], 31h ; '1'; int
0x180069526  lea     rcx, aOnecoreuapShel_26; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x18006952d  mov     [rsp+0A0h+var_80], rcx; char *
0x180069532  lea     r9, aAppreadinessTa_29; "AppReadiness::Tasks::Pause::OnExecute"
0x180069539  lea     r8, aWindowsFoundat_12; "Windows::Foundation::GetActivationFacto"...
0x180069540  mov     edx, eax; int
0x180069542  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180069546  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18006954b  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180069552  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180069556  call    _CxxThrowException_0
0x18006955c  mov     [rbp+57h+var_68], 0
0x180069564  mov     rdi, [rbp+57h+var_70]
0x180069568  mov     rax, [rdi]
0x18006956b  mov     rbx, [rax+30h]
0x18006956f  lea     rcx, [rbp+57h+var_68]
0x180069573  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180069578  lea     rdx, [rsi-20h]
0x18006957c  lea     r8, [rsi+0E8h]
0x180069583  neg     rdx
0x180069586  sbb     rdx, rdx
0x180069589  and     rdx, r8
0x18006958c  lea     r9, [rbp+57h+var_68]
0x180069590  mov     r8d, 1312D00h
0x180069596  mov     rcx, rdi
0x180069599  mov     rax, rbx
0x18006959c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800695a1  test    eax, eax
0x1800695a3  jns     short loc_1800695E3
0x1800695a5  mov     [rsp+0A0h+var_78], 33h ; '3'; int
0x1800695ad  lea     rcx, aOnecoreuapShel_26; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x1800695b4  mov     [rsp+0A0h+var_80], rcx; char *
0x1800695b9  lea     r9, aAppreadinessTa_29; "AppReadiness::Tasks::Pause::OnExecute"
0x1800695c0  lea     r8, aThreadpoolCrea; "threadpool->CreatePeriodicTimer(this, c"...
0x1800695c7  mov     edx, eax; int
0x1800695c9  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800695cd  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800695d2  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800695d9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800695dd  call    _CxxThrowException_0
0x1800695e3  lea     rcx, [rbp+57h+var_68]
0x1800695e7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800695ec  nop
0x1800695ed  mov     rcx, [rbp+57h+var_70]
0x1800695f1  test    rcx, rcx
0x1800695f4  jz      short loc_18006960B
0x1800695f6  mov     [rbp+57h+var_70], 0
0x1800695fe  mov     rax, [rcx]
0x180069601  mov     rax, [rax+10h]
0x180069605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006960a  nop
0x18006960b  mov     rcx, [rbp+57h+var_30]
0x18006960f  xor     rcx, rsp; StackCookie
0x180069612  call    __security_check_cookie
0x180069617  add     rsp, 88h
0x18006961e  pop     rdi
0x18006961f  pop     rsi
0x180069620  pop     rbx
0x180069621  pop     rbp
0x180069622  retn
```
