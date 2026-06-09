# ConnectionManagerFactoryPrivate::Initialize(void)

- ea: `0x180020ee4`
- end: `0x180021040`
- name: `?Initialize@ConnectionManagerFactoryPrivate@@SAJXZ`
- size: `348`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180029914`
- `0x18002d590`

## callees

- `0x180007e20`
- `0x18000a2a0`
- `0x1800131e0`
- `0x1800132f0`
- `0x180017c70`
- `0x180020ee4`
- `0x180021048`
- `0x1800226b0`
- `0x180024830`
- `0x180026200`
- `0x180026adc`
- `0x18002d6a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020f89`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020f89`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020f35`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020f35`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020ffc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020ffc`

## pseudocode

```c
__int64 ConnectionManagerFactoryPrivate::Initialize(void)
{
  char *v0; // rbx
  HANDLE EventW; // rax
  __int64 result; // rax
  const char *v3; // [rsp+20h] [rbp-178h]
  int v4[2]; // [rsp+20h] [rbp-178h] BYREF
  RTL_SRWLOCK *v5; // [rsp+28h] [rbp-170h]
  _QWORD v6[42]; // [rsp+30h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v6,
    "WnsMuxInit");
  v6[0] = &WnsCPLog::WnsMuxInit::`vftable';
  WnsCPLog::WnsMuxInit::StartActivity((WnsCPLog::WnsMuxInit *)v6);
  AcquireSRWLockExclusive(&ConnectionManagerFactoryPrivate::s_muxLock);
  try
  {
    v5 = &ConnectionManagerFactoryPrivate::s_muxLock;
    if ( !ConnectionManagerFactoryPrivate::s_theMux )
    {
      v0 = (char *)operator new(0x1F0u);
      Wns::ClientRegistration::ClientRegistration((Wns::ClientRegistration *)v0);
      Wns::ConnectionStateMachine::ConnectionStateMachine(
        (Wns::ConnectionStateMachine *)(v0 + 40),
        (struct Wns::ConnectionMultiplexer *)v0);
      ConnectionManagerFactoryPrivate::s_theMux = (Wns::ConnectionMultiplexer *)v0;
      EventW = CreateEventW(0, 1, 0, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &ConnectionManagerFactoryPrivate::s_muxEvent,
        EventW);
      *(_QWORD *)v4 = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v4);
      if ( (((unsigned __int64)ConnectionManagerFactoryPrivate::s_muxEvent + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4C,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionmanagerfactory.cpp",
          (const char *)0x8000FFFFLL,
          v4[0]);
      ConnectionManagerFactoryPrivate::s_muxRefCount = 0;
    }
    wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v6, 0);
    ReleaseSRWLockExclusive(&ConnectionManagerFactoryPrivate::s_muxLock);
    WnsCPLog::WnsMuxInit::~WnsMuxInit((WnsCPLog::WnsMuxInit *)v6);
    result = 0;
  }
  catch ( ... )
  {
    v4[0] = wil::details::in1diag3::Return_CaughtExceptionMsg(
              retaddr,
              (void *)0x53,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionmanagerfactory.cpp",
              "Could not initialize ConnectionMultiplexer: Fatal exception",
              v3);
    WnsCPLog::WnsMuxInit::~WnsMuxInit((WnsCPLog::WnsMuxInit *)v6);
    return (unsigned int)v4[0];
  }
  return result;
}

```

## disassembly

```asm
0x180020ee4  mov     [rsp+arg_0], rbx
0x180020ee9  push    rdi
0x180020eea  sub     rsp, 190h
0x180020ef1  mov     rax, cs:__security_cookie
0x180020ef8  xor     rax, rsp
0x180020efb  mov     [rsp+198h+var_18], rax
0x180020f03  lea     rdx, aWnsmuxinit; "WnsMuxInit"
0x180020f0a  lea     rcx, [rsp+198h+var_168]
0x180020f0f  call    ??0?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180020f14  lea     rcx, ??_7WnsMuxInit@WnsCPLog@@6B@; const WnsCPLog::WnsMuxInit::`vftable'
0x180020f1b  mov     [rsp+198h+var_168], rcx
0x180020f20  lea     rcx, [rsp+198h+var_168]; this
0x180020f25  call    ?StartActivity@WnsMuxInit@WnsCPLog@@QEAAXXZ; WnsCPLog::WnsMuxInit::StartActivity(void)
0x180020f2a  nop
0x180020f2b  lea     rdi, ?s_muxLock@ConnectionManagerFactoryPrivate@@0Vsrwlock@wil@@A; wil::srwlock ConnectionManagerFactoryPrivate::s_muxLock
0x180020f32  mov     rcx, rdi; SRWLock
0x180020f35  call    cs:__imp_AcquireSRWLockExclusive
0x180020f3b  mov     [rsp+198h+var_170], rdi
0x180020f40  cmp     cs:?s_theMux@ConnectionManagerFactoryPrivate@@0PEAVConnectionMultiplexer@Wns@@EA, 0; Wns::ConnectionMultiplexer * ConnectionManagerFactoryPrivate::s_theMux
0x180020f48  jnz     loc_180020FEC
0x180020f4e  mov     ecx, 1F0h; Size
0x180020f53  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020f58  mov     rbx, rax
0x180020f5b  mov     qword ptr [rsp+198h+var_178], rax
0x180020f60  mov     rcx, rax; this
0x180020f63  call    ??0ClientRegistration@Wns@@QEAA@XZ; Wns::ClientRegistration::ClientRegistration(void)
0x180020f68  nop
0x180020f69  lea     rcx, [rbx+28h]; this
0x180020f6d  mov     rdx, rbx; struct Wns::ConnectionMultiplexer *
0x180020f70  call    ??0ConnectionStateMachine@Wns@@QEAA@PEAVConnectionMultiplexer@1@@Z; Wns::ConnectionStateMachine::ConnectionStateMachine(Wns::ConnectionMultiplexer *)
0x180020f75  nop
0x180020f76  mov     cs:?s_theMux@ConnectionManagerFactoryPrivate@@0PEAVConnectionMultiplexer@Wns@@EA, rbx; Wns::ConnectionMultiplexer * ConnectionManagerFactoryPrivate::s_theMux
0x180020f7d  xor     r9d, r9d; lpName
0x180020f80  xor     r8d, r8d; bInitialState
0x180020f83  lea     edx, [r9+1]; bManualReset
0x180020f87  xor     ecx, ecx; lpEventAttributes
0x180020f89  call    cs:__imp_CreateEventW
0x180020f8f  mov     rdx, rax
0x180020f92  lea     rcx, ?s_muxEvent@ConnectionManagerFactoryPrivate@@0V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> ConnectionManagerFactoryPrivate::s_muxEvent
0x180020f99  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180020f9e  mov     qword ptr [rsp+198h+var_178], 0; int
0x180020fa7  lea     rcx, [rsp+198h+var_178]
0x180020fac  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180020fb1  mov     rcx, [rsp+198h]; this
0x180020fb9  mov     rax, cs:?s_muxEvent@ConnectionManagerFactoryPrivate@@0V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> ConnectionManagerFactoryPrivate::s_muxEvent
0x180020fc0  inc     rax
0x180020fc3  test    rax, 0FFFFFFFFFFFFFFFEh
0x180020fc9  jnz     short loc_180020FE2
0x180020fcb  mov     r9d, 8000FFFFh; char *
0x180020fd1  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180020fd8  mov     edx, 4Ch ; 'L'; void *
0x180020fdd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180020fe2  mov     cs:?s_muxRefCount@ConnectionManagerFactoryPrivate@@0IA, 0; uint ConnectionManagerFactoryPrivate::s_muxRefCount
0x180020fec  xor     edx, edx
0x180020fee  lea     rcx, [rsp+198h+var_168]
0x180020ff3  call    ?Stop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180020ff8  nop
0x180020ff9  mov     rcx, rdi; SRWLock
0x180020ffc  call    cs:__imp_ReleaseSRWLockExclusive
0x180021002  nop
0x180021003  lea     rcx, [rsp+198h+var_168]; this
0x180021008  call    ??1WnsMuxInit@WnsCPLog@@QEAA@XZ; WnsCPLog::WnsMuxInit::~WnsMuxInit(void)
0x18002100d  xor     eax, eax
0x18002100f  jmp     short loc_18002101F
0x180021011  lea     rcx, [rsp+198h+var_168]; this
0x180021016  call    ??1WnsMuxInit@WnsCPLog@@QEAA@XZ; WnsCPLog::WnsMuxInit::~WnsMuxInit(void)
0x18002101b  mov     eax, [rsp+198h+var_178]
0x18002101f  mov     rcx, [rsp+198h+var_18]
0x180021027  xor     rcx, rsp; StackCookie
0x18002102a  call    __security_check_cookie
0x18002102f  mov     rbx, [rsp+198h+arg_0]
0x180021037  add     rsp, 190h
0x18002103e  pop     rdi
0x18002103f  retn
```
