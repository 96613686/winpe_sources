# WpnConnectionManager::~WpnConnectionManager(void)

- ea: `0x1800058d4`
- end: `0x180005ada`
- name: `??1WpnConnectionManager@@EEAA@XZ`
- size: `518`
- prototype: `void __fastcall(WpnConnectionManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002e460`

## callees

- `0x1800058d4`
- `0x180005ae0`
- `0x180005df0`
- `0x180007d60`
- `0x180008ba0`
- `0x18000a2a0`
- `0x180026200`
- `0x180026cd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005a61`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005a61`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005aae`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005aae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000591d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000591d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005aa4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005aa4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005a4b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005a4b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005a6e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005a6e`

## pseudocode

```c
void __fastcall WpnConnectionManager::~WpnConnectionManager(WpnConnectionManager *this)
{
  WpnConnectionManager *v1; // rbx
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  wil *v3; // rcx
  unsigned int v4; // r15d
  struct _RTL_CRITICAL_SECTION *v6; // [rsp+30h] [rbp-198h]
  void **v7; // [rsp+40h] [rbp-188h] BYREF
  int v8; // [rsp+48h] [rbp-180h] BYREF
  char v9; // [rsp+4Ch] [rbp-17Ch]
  int v10; // [rsp+70h] [rbp-158h] BYREF
  const char *v11; // [rsp+78h] [rbp-150h]
  __int64 v12; // [rsp+80h] [rbp-148h]
  char v13; // [rsp+88h] [rbp-140h]
  int v14; // [rsp+90h] [rbp-138h]
  _BYTE v15[152]; // [rsp+98h] [rbp-130h] BYREF
  __int128 v16; // [rsp+130h] [rbp-98h]
  int v17; // [rsp+140h] [rbp-88h]
  __int64 v18; // [rsp+148h] [rbp-80h]
  int *v19; // [rsp+150h] [rbp-78h]
  __int64 v20; // [rsp+158h] [rbp-70h]
  __int64 v21; // [rsp+160h] [rbp-68h]
  void ***v22; // [rsp+168h] [rbp-60h]
  __int64 v23; // [rsp+170h] [rbp-58h]
  int v24; // [rsp+178h] [rbp-50h]
  int *v25; // [rsp+180h] [rbp-48h]
  char v26; // [rsp+188h] [rbp-40h]

  v1 = this;
  *(_QWORD *)this = &WpnConnectionManager::`vftable'{for `IConnectionManagerPrivate'};
  *((_QWORD *)this + 1) = &WpnConnectionManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IConnectionManagerPrivate2>'};
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v8 = 0;
  v9 = 0;
  v13 = 0;
  v10 = 0;
  v11 = "WnsCMDestroy";
  v12 = 0;
  v14 = 0;
  v16 = 0;
  memset_0(v15, 0, sizeof(v15));
  v17 = 1;
  v18 = 0;
  v19 = &v8;
  v20 = 0;
  v21 = 0;
  v22 = &v7;
  v23 = 0;
  v24 = 0;
  v25 = &v10;
  v26 = 0;
  v7 = &WnsCPLog::WnsCMDestroy::`vftable';
  WnsCPLog::WnsCMDestroy::StartActivity((WnsCPLog::WnsCMDestroy *)&v7, *((_QWORD *)v1 + 4));
  try
  {
    v4 = 0;
    Wns::ConnectionMultiplexer::UnregisterAndDisconnect(
      *((Wns::ConnectionMultiplexer **)v1 + 3),
      (WpnConnectionManager *)((char *)v1 + 48),
      *((_DWORD *)v1 + 10));
  }
  catch ( ... )
  {
    v4 = wil::ResultFromCaughtException(v3);
    v1 = this;
    v2 = v6;
  }
  AcquireSRWLockExclusive(&ConnectionManagerFactoryPrivate::s_muxLock);
  if ( !--ConnectionManagerFactoryPrivate::s_muxRefCount )
    SetEvent(ConnectionManagerFactoryPrivate::s_muxEvent);
  ReleaseSRWLockExclusive(&ConnectionManagerFactoryPrivate::s_muxLock);
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v7, v4);
  v7 = &WnsCPLog::WnsCMDestroy::`vftable';
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v7);
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)&v7);
  if ( v2 )
    LeaveCriticalSection(v2);
  DeleteCriticalSection(v2);
  *((_DWORD *)v1 + 5) = -1073741823;
}

```

## disassembly

```asm
0x1800058d4  push    rbx
0x1800058d6  push    rdi
0x1800058d7  push    r14
0x1800058d9  push    r15
0x1800058db  sub     rsp, 1A8h
0x1800058e2  mov     rax, cs:__security_cookie
0x1800058e9  xor     rax, rsp
0x1800058ec  mov     [rsp+1C8h+var_38], rax
0x1800058f4  mov     rbx, rcx
0x1800058f7  mov     [rsp+1C8h+var_1A0], rcx
0x1800058fc  lea     rax, ??_7WpnConnectionManager@@6BIConnectionManagerPrivate@@@; const WpnConnectionManager::`vftable'{for `IConnectionManagerPrivate'}
0x180005903  mov     [rcx], rax
0x180005906  lea     rax, ??_7WpnConnectionManager@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIConnectionManagerPrivate2@@@Details@WRL@Microsoft@@@; const WpnConnectionManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IConnectionManagerPrivate2>'}
0x18000590d  mov     [rcx+8], rax
0x180005911  lea     rdi, [rcx+40h]
0x180005915  mov     [rsp+1C8h+var_198], rdi
0x18000591a  mov     rcx, rdi; lpCriticalSection
0x18000591d  call    cs:__imp_EnterCriticalSection
0x180005923  mov     [rsp+1C8h+var_1A8], rdi
0x180005928  mov     [rsp+1C8h+var_180], 0
0x180005930  mov     [rsp+1C8h+var_17C], 0
0x180005935  mov     [rsp+1C8h+var_140], 0
0x18000593d  mov     [rsp+1C8h+var_158], 0
0x180005945  lea     rax, aWnscmdestroy; "WnsCMDestroy"
0x18000594c  mov     [rsp+1C8h+var_150], rax
0x180005951  mov     [rsp+1C8h+var_148], 0
0x18000595d  mov     [rsp+1C8h+var_138], 0
0x180005968  xorps   xmm0, xmm0
0x18000596b  movdqa  [rsp+1C8h+var_98], xmm0
0x180005974  xor     edx, edx; Val
0x180005976  mov     r8d, 98h; Size
0x18000597c  lea     rcx, [rsp+1C8h+var_130]; void *
0x180005984  call    memset_0
0x180005989  mov     [rsp+1C8h+var_88], 1
0x180005994  xor     eax, eax
0x180005996  mov     [rsp+1C8h+var_80], rax
0x18000599e  lea     rax, [rsp+1C8h+var_180]
0x1800059a3  mov     [rsp+1C8h+var_78], rax
0x1800059ab  mov     [rsp+1C8h+var_70], 0
0x1800059b7  mov     [rsp+1C8h+var_68], 0
0x1800059c3  lea     rax, [rsp+1C8h+var_188]
0x1800059c8  mov     [rsp+1C8h+var_60], rax
0x1800059d0  mov     [rsp+1C8h+var_58], 0
0x1800059dc  mov     [rsp+1C8h+var_50], 0
0x1800059e7  lea     rax, [rsp+1C8h+var_158]
0x1800059ec  mov     [rsp+1C8h+var_48], rax
0x1800059f4  mov     [rsp+1C8h+var_40], 0
0x1800059fc  lea     r14, ??_7WnsCMDestroy@WnsCPLog@@6B@; const WnsCPLog::WnsCMDestroy::`vftable'
0x180005a03  mov     [rsp+1C8h+var_188], r14
0x180005a08  mov     rdx, [rbx+20h]; unsigned __int64
0x180005a0c  lea     rcx, [rsp+1C8h+var_188]; this
0x180005a11  call    ?StartActivity@WnsCMDestroy@WnsCPLog@@QEAAX_K@Z; WnsCPLog::WnsCMDestroy::StartActivity(unsigned __int64)
0x180005a16  nop
0x180005a17  xor     r15d, r15d
0x180005a1a  lea     rdx, [rbx+30h]; struct Wns::RegistrationToken *
0x180005a1e  mov     r8d, [rbx+28h]; unsigned int
0x180005a22  mov     rcx, [rbx+18h]; this
0x180005a26  call    ?UnregisterAndDisconnect@ConnectionMultiplexer@Wns@@QEAAXAEBVRegistrationToken@2@K@Z; Wns::ConnectionMultiplexer::UnregisterAndDisconnect(Wns::RegistrationToken const &,ulong)
0x180005a2b  nop
0x180005a2c  jmp     short loc_180005A44
0x180005a2e  lea     r14, ??_7WnsCMDestroy@WnsCPLog@@6B@; const WnsCPLog::WnsCMDestroy::`vftable'
0x180005a35  mov     r15d, dword ptr [rsp+1C8h+var_1A8]
0x180005a3a  mov     rbx, [rsp+1C8h+var_1A0]
0x180005a3f  mov     rdi, [rsp+1C8h+var_198]
0x180005a44  lea     rcx, ?s_muxLock@ConnectionManagerFactoryPrivate@@0Vsrwlock@wil@@A; SRWLock
0x180005a4b  call    cs:__imp_AcquireSRWLockExclusive
0x180005a51  add     cs:?s_muxRefCount@ConnectionManagerFactoryPrivate@@0IA, 0FFFFFFFFh; uint ConnectionManagerFactoryPrivate::s_muxRefCount
0x180005a58  jnz     short loc_180005A67
0x180005a5a  mov     rcx, cs:?s_muxEvent@ConnectionManagerFactoryPrivate@@0V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; hEvent
0x180005a61  call    cs:__imp_SetEvent
0x180005a67  lea     rcx, ?s_muxLock@ConnectionManagerFactoryPrivate@@0Vsrwlock@wil@@A; SRWLock
0x180005a6e  call    cs:__imp_ReleaseSRWLockExclusive
0x180005a74  mov     edx, r15d
0x180005a77  lea     rcx, [rsp+1C8h+var_188]
0x180005a7c  call    ?Stop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180005a81  nop
0x180005a82  mov     [rsp+1C8h+var_188], r14
0x180005a87  lea     rcx, [rsp+1C8h+var_188]
0x180005a8c  call    ?Destroy@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180005a91  lea     rcx, [rsp+1C8h+var_188]
0x180005a96  call    ??1?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180005a9b  nop
0x180005a9c  test    rdi, rdi
0x180005a9f  jz      short loc_180005AAB
0x180005aa1  mov     rcx, rdi; lpCriticalSection
0x180005aa4  call    cs:__imp_LeaveCriticalSection
0x180005aaa  nop
0x180005aab  mov     rcx, rdi; lpCriticalSection
0x180005aae  call    cs:__imp_DeleteCriticalSection
0x180005ab4  nop
0x180005ab5  mov     dword ptr [rbx+14h], 0C0000001h
0x180005abc  mov     rcx, [rsp+1C8h+var_38]
0x180005ac4  xor     rcx, rsp; StackCookie
0x180005ac7  call    __security_check_cookie
0x180005acc  add     rsp, 1A8h
0x180005ad3  pop     r15
0x180005ad5  pop     r14
0x180005ad7  pop     rdi
0x180005ad8  pop     rbx
0x180005ad9  retn
```
