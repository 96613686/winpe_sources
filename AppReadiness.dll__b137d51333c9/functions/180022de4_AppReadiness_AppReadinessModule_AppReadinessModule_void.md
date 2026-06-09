# AppReadiness::AppReadinessModule::AppReadinessModule(void)

- ea: `0x180022de4`
- end: `0x180022f51`
- name: `??0AppReadinessModule@AppReadiness@@QEAA@XZ`
- size: `365`
- prototype: `__int64 __fastcall(AppReadiness::AppReadinessModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180038820`

## callees

- `0x180022de4`
- `0x180027a4c`
- `0x18003ecb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180022e38`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180022e38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e48`
- `combase!__imp_CoGetSharedServiceId` at `0x180022ea6`
- `combase!__imp_CoGetSharedServiceId` at `0x180022ea6`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180022ef9`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180022ef9`

## string_xrefs

- `0x180022e6a`: `onecoreuap\shell\AppReadiness\Src\Core\Module.h`
- `0x180022eb8`: `onecoreuap\shell\AppReadiness\Src\Core\Module.h`
- `0x180022f0b`: `onecoreuap\shell\AppReadiness\Src\Core\Module.h`
- `0x180022e76`: `AppReadiness::AppReadinessModule::AppReadinessModule`
- `0x180022ec4`: `AppReadiness::AppReadinessModule::AppReadinessModule`
- `0x180022f17`: `AppReadiness::AppReadinessModule::AppReadinessModule`
- `0x180022e7d`: `ResultFromWin32Handle(CreateEventEx(nullptr, nullptr, CREATE_EVENT_MANUAL_RESET, EVENT_MODIFY_STATE | SYNCHRONIZE), m_outstandingObjects.GetAddressOf())`
- `0x180022ecb`: `CoGetSharedServiceId(&m_serviceId)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
AppReadiness::AppReadinessModule *__fastcall AppReadiness::AppReadinessModule::AppReadinessModule(
        AppReadiness::AppReadinessModule *this)
{
  HANDLE Event; // rax
  signed int LastError; // eax
  bool v4; // sf
  int SharedServiceId; // eax
  int v6; // eax
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF

  Microsoft::WRL::Details::ModuleBase::module_ = this;
  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = &AppReadiness::AppReadinessModule::`vftable';
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 2) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  *((_QWORD *)this + 4) = 0;
  Event = CreateEventExW(0, 0, 1u, 0x100002u);
  *((_QWORD *)this + 3) = Event;
  if ( Event == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v4 = LastError < 0;
    if ( LastError <= 0 )
      goto LABEL_6;
    LastError = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    LastError = 0;
  }
  v4 = LastError < 0;
LABEL_6:
  if ( v4 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      LastError,
      "ResultFromWin32Handle(CreateEventEx(nullptr, nullptr, CREATE_EVENT_MANUAL_RESET, EVENT_MODIFY_STATE | SYNCHRONIZE)"
      ", m_outstandingObjects.GetAddressOf())",
      "AppReadiness::AppReadinessModule::AppReadinessModule",
      "onecoreuap\\shell\\AppReadiness\\Src\\Core\\Module.h",
      17);
    throw (Windows::HResultException *)pExceptionObject;
  }
  SharedServiceId = CoGetSharedServiceId((char *)this + 36);
  if ( SharedServiceId < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      SharedServiceId,
      "CoGetSharedServiceId(&m_serviceId)",
      "AppReadiness::AppReadinessModule::AppReadinessModule",
      "onecoreuap\\shell\\AppReadiness\\Src\\Core\\Module.h",
      18);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v6 = CoRegisterServerShutdownDelay(*((_QWORD *)this + 3), 10);
  if ( v6 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v6,
      "CoRegisterServerShutdownDelay(m_outstandingObjects.Get(), c_MaxWaitForObjects)",
      "AppReadiness::AppReadinessModule::AppReadinessModule",
      "onecoreuap\\shell\\AppReadiness\\Src\\Core\\Module.h",
      23);
    throw (Windows::HResultException *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180022de4  mov     [rsp+arg_8], rbx
0x180022de9  mov     [rsp+arg_0], rcx
0x180022dee  push    rdi
0x180022def  sub     rsp, 60h
0x180022df3  mov     rbx, rcx
0x180022df6  mov     cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA, rcx; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180022dfd  mov     qword ptr [rcx+8], 0
0x180022e05  lea     rax, ??_7AppReadinessModule@AppReadiness@@6B@; const AppReadiness::AppReadinessModule::`vftable'
0x180022e0c  mov     [rcx], rax
0x180022e0f  mov     qword ptr [rcx+18h], 0
0x180022e17  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180022e1e  mov     [rcx+10h], rax
0x180022e22  mov     qword ptr [rcx+20h], 0
0x180022e2a  xor     edx, edx; lpName
0x180022e2c  xor     ecx, ecx; lpEventAttributes
0x180022e2e  mov     r9d, 100002h; dwDesiredAccess
0x180022e34  lea     r8d, [rdx+1]; dwFlags
0x180022e38  call    cs:__imp_CreateEventExW
0x180022e3e  mov     [rbx+18h], rax
0x180022e42  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022e46  jnz     short loc_180022E5C
0x180022e48  call    cs:__imp_GetLastError
0x180022e4e  test    eax, eax
0x180022e50  jle     short loc_180022E60
0x180022e52  movzx   eax, ax
0x180022e55  or      eax, 80070000h
0x180022e5a  jmp     short loc_180022E5E
0x180022e5c  xor     eax, eax
0x180022e5e  test    eax, eax
0x180022e60  jns     short loc_180022EA2
0x180022e62  mov     [rsp+68h+var_40], 11h; int
0x180022e6a  lea     rcx, aOnecoreuapShel_24; "onecoreuap\\shell\\AppReadiness\\Src\\C"...
0x180022e71  mov     [rsp+68h+var_48], rcx; char *
0x180022e76  lea     r9, aAppreadinessAp_1; "AppReadiness::AppReadinessModule::AppRe"...
0x180022e7d  lea     r8, aResultfromwin3_9; "ResultFromWin32Handle(CreateEventEx(nul"...
0x180022e84  mov     edx, eax; int
0x180022e86  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180022e8b  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180022e90  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180022e97  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180022e9c  call    _CxxThrowException_0
0x180022ea2  lea     rcx, [rbx+24h]
0x180022ea6  call    cs:__imp_CoGetSharedServiceId
0x180022eac  test    eax, eax
0x180022eae  jns     short loc_180022EF0
0x180022eb0  mov     [rsp+68h+var_40], 12h; int
0x180022eb8  lea     rcx, aOnecoreuapShel_24; "onecoreuap\\shell\\AppReadiness\\Src\\C"...
0x180022ebf  mov     [rsp+68h+var_48], rcx; char *
0x180022ec4  lea     r9, aAppreadinessAp_1; "AppReadiness::AppReadinessModule::AppRe"...
0x180022ecb  lea     r8, aCogetsharedser; "CoGetSharedServiceId(&m_serviceId)"
0x180022ed2  mov     edx, eax; int
0x180022ed4  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180022ed9  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180022ede  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180022ee5  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180022eea  call    _CxxThrowException_0
0x180022ef0  mov     edx, 0Ah
0x180022ef5  mov     rcx, [rbx+18h]
0x180022ef9  call    cs:__imp_CoRegisterServerShutdownDelay
0x180022eff  test    eax, eax
0x180022f01  jns     short loc_180022F43
0x180022f03  mov     [rsp+68h+var_40], 17h; int
0x180022f0b  lea     rcx, aOnecoreuapShel_24; "onecoreuap\\shell\\AppReadiness\\Src\\C"...
0x180022f12  mov     [rsp+68h+var_48], rcx; char *
0x180022f17  lea     r9, aAppreadinessAp_1; "AppReadiness::AppReadinessModule::AppRe"...
0x180022f1e  lea     r8, aCoregisterserv; "CoRegisterServerShutdownDelay(m_outstan"...
0x180022f25  mov     edx, eax; int
0x180022f27  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180022f2c  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180022f31  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180022f38  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180022f3d  call    _CxxThrowException_0
0x180022f43  mov     rax, rbx
0x180022f46  mov     rbx, [rsp+68h+arg_8]
0x180022f4b  add     rsp, 60h
0x180022f4f  pop     rdi
0x180022f50  retn
```
