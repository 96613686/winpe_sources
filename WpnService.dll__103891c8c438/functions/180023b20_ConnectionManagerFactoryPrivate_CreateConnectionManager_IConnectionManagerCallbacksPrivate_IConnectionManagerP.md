# ConnectionManagerFactoryPrivate::CreateConnectionManager(IConnectionManagerCallbacksPrivate *,IConnectionManagerPrivate * *)

- ea: `0x180023b20`
- end: `0x180023c4c`
- name: `?CreateConnectionManager@ConnectionManagerFactoryPrivate@@UEAAJPEAUIConnectionManagerCallbacksPrivate@@PEAPEAUIConnectionManagerPrivate@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(ConnectionManagerFactoryPrivate *__hidden this, struct IConnectionManagerCallbacksPrivate *, struct IConnectionManagerPrivate **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000a2a0`
- `0x1800202bc`
- `0x180023948`
- `0x180023b20`
- `0x180023c54`
- `0x180026200`
- `0x18002cdfc`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023b63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023b63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023b9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023c08`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023b9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023c08`

## pseudocode

```c
__int64 __fastcall ConnectionManagerFactoryPrivate::CreateConnectionManager(
        ConnectionManagerFactoryPrivate *this,
        struct IConnectionManagerCallbacksPrivate *a2,
        struct IConnectionManagerPrivate **a3)
{
  WpnConnectionManager *v4; // r8
  __int64 result; // rax
  struct IConnectionManagerPrivate *v6; // rax
  struct IConnectionManagerPrivate *v7; // rcx
  const char *v8; // r9
  struct IConnectionManagerPrivate *v9; // [rsp+20h] [rbp-188h] BYREF
  struct IConnectionManagerCallbacksPrivate *v10[3]; // [rsp+28h] [rbp-180h] BYREF
  _BYTE v11[336]; // [rsp+40h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v10[0] = a2;
  WnsCPLog::WnsMuxMakeCM::Start<>((WnsCPLog::WnsMuxMakeCM *)v11);
  *a3 = 0;
  AcquireSRWLockExclusive(&ConnectionManagerFactoryPrivate::s_muxLock);
  v10[1] = (struct IConnectionManagerCallbacksPrivate *)&ConnectionManagerFactoryPrivate::s_muxLock;
  if ( ConnectionManagerFactoryPrivate::s_theMux )
  {
    try
    {
      Microsoft::WRL::Details::Make<WpnConnectionManager,IConnectionManagerCallbacksPrivate * &,Wns::ConnectionMultiplexer * &>(
        &v9,
        v10,
        v4);
      ++ConnectionManagerFactoryPrivate::s_muxRefCount;
      v6 = v9;
      v9 = 0;
      *a3 = v6;
      wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v11, 0);
      v7 = v9;
      if ( v9 )
      {
        v9 = 0;
        (*(void (__fastcall **)(struct IConnectionManagerPrivate *))(*(_QWORD *)v7 + 16LL))(v7);
      }
      ReleaseSRWLockExclusive(&ConnectionManagerFactoryPrivate::s_muxLock);
      WnsCPLog::WnsMuxMakeCM::~WnsMuxMakeCM((WnsCPLog::WnsMuxMakeCM *)v11);
      result = 0;
    }
    catch ( ... )
    {
      LODWORD(v9) = wil::details::in1diag3::Return_CaughtException(
                      retaddr,
                      (void *)0x24,
                      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionmanagerfactory.cpp",
                      v8);
      WnsCPLog::WnsMuxMakeCM::~WnsMuxMakeCM((WnsCPLog::WnsMuxMakeCM *)v11);
      return (unsigned int)v9;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionmanagerfactory.cpp",
      (const char *)0x80004003LL,
      (int)v9);
    ReleaseSRWLockExclusive(&ConnectionManagerFactoryPrivate::s_muxLock);
    WnsCPLog::WnsMuxMakeCM::~WnsMuxMakeCM((WnsCPLog::WnsMuxMakeCM *)v11);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x180023b20  mov     [rsp+arg_0], rbx
0x180023b25  push    rsi
0x180023b26  sub     rsp, 1A0h
0x180023b2d  mov     rax, cs:__security_cookie
0x180023b34  xor     rax, rsp
0x180023b37  mov     [rsp+1A8h+var_18], rax
0x180023b3f  mov     rbx, r8
0x180023b42  mov     [rsp+1A8h+var_180], rdx
0x180023b47  lea     rcx, [rsp+1A8h+var_168]; this
0x180023b4c  call    ??$Start@$$V@WnsMuxMakeCM@WnsCPLog@@SA?AV01@XZ; WnsCPLog::WnsMuxMakeCM::Start<>(void)
0x180023b51  nop
0x180023b52  mov     qword ptr [rbx], 0
0x180023b59  lea     rsi, ?s_muxLock@ConnectionManagerFactoryPrivate@@0Vsrwlock@wil@@A; wil::srwlock ConnectionManagerFactoryPrivate::s_muxLock
0x180023b60  mov     rcx, rsi; SRWLock
0x180023b63  call    cs:__imp_AcquireSRWLockExclusive
0x180023b69  mov     [rsp+1A8h+var_178], rsi
0x180023b6e  cmp     cs:?s_theMux@ConnectionManagerFactoryPrivate@@0PEAVConnectionMultiplexer@Wns@@EA, 0; Wns::ConnectionMultiplexer * ConnectionManagerFactoryPrivate::s_theMux
0x180023b76  jnz     short loc_180023BB2
0x180023b78  mov     rcx, [rsp+1A8h]; this
0x180023b80  mov     ebx, 80004003h
0x180023b85  mov     r9d, ebx; char *
0x180023b88  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180023b8f  mov     edx, 1Bh; void *
0x180023b94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023b99  nop
0x180023b9a  mov     rcx, rsi; SRWLock
0x180023b9d  call    cs:__imp_ReleaseSRWLockExclusive
0x180023ba3  nop
0x180023ba4  lea     rcx, [rsp+1A8h+var_168]; this
0x180023ba9  call    ??1WnsMuxMakeCM@WnsCPLog@@QEAA@XZ; WnsCPLog::WnsMuxMakeCM::~WnsMuxMakeCM(void)
0x180023bae  mov     eax, ebx
0x180023bb0  jmp     short loc_180023C2B
0x180023bb2  lea     rdx, [rsp+1A8h+var_180]
0x180023bb7  lea     rcx, [rsp+1A8h+var_188]
0x180023bbc  call    ??$Make@VWpnConnectionManager@@AEAPEAUIConnectionManagerCallbacksPrivate@@AEAPEAVConnectionMultiplexer@Wns@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWpnConnectionManager@@@12@AEAPEAUIConnectionManagerCallbacksPrivate@@AEAPEAVConnectionMultiplexer@Wns@@@Z; Microsoft::WRL::Details::Make<WpnConnectionManager,IConnectionManagerCallbacksPrivate * &,Wns::ConnectionMultiplexer * &>(IConnectionManagerCallbacksPrivate * &,Wns::ConnectionMultiplexer * &)
0x180023bc1  inc     cs:?s_muxRefCount@ConnectionManagerFactoryPrivate@@0IA; uint ConnectionManagerFactoryPrivate::s_muxRefCount
0x180023bc7  mov     rax, [rsp+1A8h+var_188]
0x180023bcc  mov     [rsp+1A8h+var_188], 0
0x180023bd5  mov     [rbx], rax
0x180023bd8  xor     edx, edx
0x180023bda  lea     rcx, [rsp+1A8h+var_168]
0x180023bdf  call    ?Stop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180023be4  nop
0x180023be5  mov     rcx, [rsp+1A8h+var_188]
0x180023bea  test    rcx, rcx
0x180023bed  jz      short loc_180023C05
0x180023bef  mov     [rsp+1A8h+var_188], 0
0x180023bf8  mov     rax, [rcx]
0x180023bfb  mov     rax, [rax+10h]
0x180023bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c04  nop
0x180023c05  mov     rcx, rsi; SRWLock
0x180023c08  call    cs:__imp_ReleaseSRWLockExclusive
0x180023c0e  nop
0x180023c0f  lea     rcx, [rsp+1A8h+var_168]; this
0x180023c14  call    ??1WnsMuxMakeCM@WnsCPLog@@QEAA@XZ; WnsCPLog::WnsMuxMakeCM::~WnsMuxMakeCM(void)
0x180023c19  xor     eax, eax
0x180023c1b  jmp     short loc_180023C2B
0x180023c1d  lea     rcx, [rsp+1A8h+var_168]; this
0x180023c22  call    ??1WnsMuxMakeCM@WnsCPLog@@QEAA@XZ; WnsCPLog::WnsMuxMakeCM::~WnsMuxMakeCM(void)
0x180023c27  mov     eax, dword ptr [rsp+1A8h+var_188]
0x180023c2b  mov     rcx, [rsp+1A8h+var_18]
0x180023c33  xor     rcx, rsp; StackCookie
0x180023c36  call    __security_check_cookie
0x180023c3b  mov     rbx, [rsp+1A8h+arg_0]
0x180023c43  add     rsp, 1A0h
0x180023c4a  pop     rsi
0x180023c4b  retn
```
