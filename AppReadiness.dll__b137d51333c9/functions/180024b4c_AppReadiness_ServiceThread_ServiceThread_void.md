# AppReadiness::ServiceThread::ServiceThread(void)

- ea: `0x180024b4c`
- end: `0x180024c85`
- name: `??0ServiceThread@AppReadiness@@QEAA@XZ`
- size: `313`
- prototype: `__int64 __fastcall(AppReadiness::ServiceThread *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180034520`

## callees

- `0x180024b4c`
- `0x180027a4c`
- `0x1800369d4`
- `0x18003ecb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180024bb6`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180024c1a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180024bb6`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180024c1a`

## string_xrefs

- `0x180024bd4`: `onecoreuap\shell\appreadiness\src\core\servicethread.cpp`
- `0x180024c38`: `onecoreuap\shell\appreadiness\src\core\servicethread.cpp`
- `0x180024be7`: `ResultFromWin32Handle(CreateEventEx(nullptr, nullptr, CREATE_EVENT_MANUAL_RESET, EVENT_MODIFY_STATE|SYNCHRONIZE), m_shutdownEvent.GetAddressOf())`
- `0x180024be0`: `AppReadiness::ServiceThread::ServiceThread`
- `0x180024c44`: `AppReadiness::ServiceThread::ServiceThread`
- `0x180024c4b`: `ResultFromWin32Handle(CreateEventEx(nullptr, nullptr, CREATE_EVENT_MANUAL_RESET, EVENT_MODIFY_STATE|SYNCHRONIZE), m_startupEvent.GetAddressOf())`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
AppReadiness::ServiceThread *__fastcall AppReadiness::ServiceThread::ServiceThread(AppReadiness::ServiceThread *this)
{
  int v2; // eax
  HANDLE Event; // rax
  int v4; // eax
  HANDLE v5; // rax
  int v6; // eax
  _BYTE pExceptionObject[48]; // [rsp+30h] [rbp-38h] BYREF

  *(_QWORD *)this = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  *((_QWORD *)this + 1) = 0;
  v2 = 2;
  do
  {
    *(_QWORD *)this = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    --v2;
  }
  while ( v2 );
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 2) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  *((_QWORD *)this + 4) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  *((_QWORD *)this + 5) = 0;
  Event = CreateEventExW(0, 0, 1u, 0x100002u);
  v4 = ResultFromWin32Handle(Event, (void **)this + 1);
  if ( v4 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v4,
      "ResultFromWin32Handle(CreateEventEx(nullptr, nullptr, CREATE_EVENT_MANUAL_RESET, EVENT_MODIFY_STATE|SYNCHRONIZE), "
      "m_shutdownEvent.GetAddressOf())",
      "AppReadiness::ServiceThread::ServiceThread",
      "onecoreuap\\shell\\appreadiness\\src\\core\\servicethread.cpp",
      21);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v5 = CreateEventExW(0, 0, 1u, 0x100002u);
  v6 = ResultFromWin32Handle(v5, (void **)this + 3);
  if ( v6 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v6,
      "ResultFromWin32Handle(CreateEventEx(nullptr, nullptr, CREATE_EVENT_MANUAL_RESET, EVENT_MODIFY_STATE|SYNCHRONIZE), "
      "m_startupEvent.GetAddressOf())",
      "AppReadiness::ServiceThread::ServiceThread",
      "onecoreuap\\shell\\appreadiness\\src\\core\\servicethread.cpp",
      22);
    throw (Windows::HResultException *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180024b4c  mov     [rsp+arg_8], rbx
0x180024b51  mov     [rsp+arg_10], rsi
0x180024b56  mov     [rsp+arg_0], rcx
0x180024b5b  push    rdi
0x180024b5c  sub     rsp, 60h
0x180024b60  mov     rbx, rcx
0x180024b63  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180024b6a  mov     [rcx], rax
0x180024b6d  mov     qword ptr [rcx+8], 0
0x180024b75  mov     eax, 2
0x180024b7a  lea     rcx, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180024b81  mov     [rbx], rcx
0x180024b84  sub     eax, 1
0x180024b87  jnz     short loc_180024B81
0x180024b89  mov     qword ptr [rbx+18h], 0
0x180024b91  mov     [rbx+10h], rcx
0x180024b95  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180024b9c  mov     [rbx+20h], rax
0x180024ba0  mov     qword ptr [rbx+28h], 0
0x180024ba8  xor     edx, edx; lpName
0x180024baa  xor     ecx, ecx; lpEventAttributes
0x180024bac  mov     r9d, 100002h; dwDesiredAccess
0x180024bb2  lea     r8d, [rdx+1]; dwFlags
0x180024bb6  call    cs:__imp_CreateEventExW
0x180024bbc  lea     rdx, [rbx+8]; void **
0x180024bc0  mov     rcx, rax; void *
0x180024bc3  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x180024bc8  test    eax, eax
0x180024bca  jns     short loc_180024C0C
0x180024bcc  mov     [rsp+68h+var_40], 15h; int
0x180024bd4  lea     rcx, aOnecoreuapShel_7; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180024bdb  mov     [rsp+68h+var_48], rcx; char *
0x180024be0  lea     r9, aAppreadinessSe_1; "AppReadiness::ServiceThread::ServiceThr"...
0x180024be7  lea     r8, aResultfromwin3_2; "ResultFromWin32Handle(CreateEventEx(nul"...
0x180024bee  mov     edx, eax; int
0x180024bf0  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180024bf5  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180024bfa  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180024c01  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180024c06  call    _CxxThrowException_0
0x180024c0c  xor     edx, edx; lpName
0x180024c0e  xor     ecx, ecx; lpEventAttributes
0x180024c10  mov     r9d, 100002h; dwDesiredAccess
0x180024c16  lea     r8d, [rdx+1]; dwFlags
0x180024c1a  call    cs:__imp_CreateEventExW
0x180024c20  lea     rdx, [rbx+18h]; void **
0x180024c24  mov     rcx, rax; void *
0x180024c27  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x180024c2c  test    eax, eax
0x180024c2e  jns     short loc_180024C70
0x180024c30  mov     [rsp+68h+var_40], 16h; int
0x180024c38  lea     rcx, aOnecoreuapShel_7; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180024c3f  mov     [rsp+68h+var_48], rcx; char *
0x180024c44  lea     r9, aAppreadinessSe_1; "AppReadiness::ServiceThread::ServiceThr"...
0x180024c4b  lea     r8, aResultfromwin3_8; "ResultFromWin32Handle(CreateEventEx(nul"...
0x180024c52  mov     edx, eax; int
0x180024c54  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180024c59  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180024c5e  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180024c65  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180024c6a  call    _CxxThrowException_0
0x180024c70  mov     rax, rbx
0x180024c73  lea     r11, [rsp+68h+var_8]
0x180024c78  mov     rbx, [r11+18h]
0x180024c7c  mov     rsi, [r11+20h]
0x180024c80  mov     rsp, r11
0x180024c83  pop     rdi
0x180024c84  retn
```
