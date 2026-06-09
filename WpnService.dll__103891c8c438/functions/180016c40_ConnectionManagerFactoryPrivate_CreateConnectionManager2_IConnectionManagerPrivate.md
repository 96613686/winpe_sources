# ConnectionManagerFactoryPrivate::CreateConnectionManager2(IConnectionManagerPrivate * *)

- ea: `0x180016c40`
- end: `0x180016d9c`
- name: `?CreateConnectionManager2@ConnectionManagerFactoryPrivate@@UEAAJPEAPEAUIConnectionManagerPrivate@@@Z`
- size: `348`
- prototype: `__int64 __fastcall(ConnectionManagerFactoryPrivate *__hidden this, struct IConnectionManagerPrivate **)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1800074f0`
- `0x180007d60`
- `0x180007e20`
- `0x180008ba0`
- `0x18000a2a0`
- `0x180016c40`
- `0x180016da4`
- `0x1800202bc`
- `0x180023c54`
- `0x180026200`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016ca1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016ca1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016cdb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016d44`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016cdb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016d44`

## pseudocode

```c
__int64 __fastcall ConnectionManagerFactoryPrivate::CreateConnectionManager2(
        ConnectionManagerFactoryPrivate *this,
        struct IConnectionManagerPrivate **a2)
{
  __int64 result; // rax
  struct IConnectionManagerPrivate *v4; // rax
  __int64 v5; // rcx
  const char *v6; // r9
  _QWORD v7[2]; // [rsp+20h] [rbp-178h] BYREF
  _QWORD v8[42]; // [rsp+30h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v8,
    "WnsMuxMakeCM");
  v8[0] = &WnsCPLog::WnsMuxMakeCM::`vftable';
  WnsCPLog::WnsMuxMakeCM::StartActivity((WnsCPLog::WnsMuxMakeCM *)v8);
  *a2 = 0;
  AcquireSRWLockExclusive(&ConnectionManagerFactoryPrivate::s_muxLock);
  v7[1] = &ConnectionManagerFactoryPrivate::s_muxLock;
  if ( ConnectionManagerFactoryPrivate::s_theMux )
  {
    try
    {
      Microsoft::WRL::Details::Make<WpnConnectionManager,Wns::ConnectionMultiplexer * &>(v7);
      ++ConnectionManagerFactoryPrivate::s_muxRefCount;
      v4 = (struct IConnectionManagerPrivate *)v7[0];
      v7[0] = 0;
      *a2 = v4;
      wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v8, 0);
      v5 = v7[0];
      if ( v7[0] )
      {
        v7[0] = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      }
      ReleaseSRWLockExclusive(&ConnectionManagerFactoryPrivate::s_muxLock);
      v8[0] = &WnsCPLog::WnsMuxMakeCM::`vftable';
      wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v8);
      wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v8);
      result = 0;
    }
    catch ( ... )
    {
      LODWORD(v7[0]) = wil::details::in1diag3::Return_CaughtException(
                         retaddr,
                         (void *)0x3C,
                         (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionmanagerfactory.cpp",
                         v6);
      WnsCPLog::WnsMuxMakeCM::~WnsMuxMakeCM((WnsCPLog::WnsMuxMakeCM *)v8);
      return LODWORD(v7[0]);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionmanagerfactory.cpp",
      (const char *)0x80004003LL,
      v7[0]);
    ReleaseSRWLockExclusive(&ConnectionManagerFactoryPrivate::s_muxLock);
    WnsCPLog::WnsMuxMakeCM::~WnsMuxMakeCM((WnsCPLog::WnsMuxMakeCM *)v8);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x180016c40  mov     [rsp+arg_0], rbx
0x180016c45  mov     [rsp+arg_10], rsi
0x180016c4a  push    r14
0x180016c4c  sub     rsp, 190h
0x180016c53  mov     rax, cs:__security_cookie
0x180016c5a  xor     rax, rsp
0x180016c5d  mov     [rsp+198h+var_18], rax
0x180016c65  mov     rbx, rdx
0x180016c68  lea     rdx, aWnsmuxmakecm; "WnsMuxMakeCM"
0x180016c6f  lea     rcx, [rsp+198h+var_168]
0x180016c74  call    ??0?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180016c79  lea     r14, ??_7WnsMuxMakeCM@WnsCPLog@@6B@; const WnsCPLog::WnsMuxMakeCM::`vftable'
0x180016c80  mov     [rsp+198h+var_168], r14
0x180016c85  lea     rcx, [rsp+198h+var_168]; this
0x180016c8a  call    ?StartActivity@WnsMuxMakeCM@WnsCPLog@@QEAAXXZ; WnsCPLog::WnsMuxMakeCM::StartActivity(void)
0x180016c8f  nop
0x180016c90  mov     qword ptr [rbx], 0
0x180016c97  lea     rsi, ?s_muxLock@ConnectionManagerFactoryPrivate@@0Vsrwlock@wil@@A; wil::srwlock ConnectionManagerFactoryPrivate::s_muxLock
0x180016c9e  mov     rcx, rsi; SRWLock
0x180016ca1  call    cs:__imp_AcquireSRWLockExclusive
0x180016ca7  mov     [rsp+198h+var_170], rsi
0x180016cac  cmp     cs:?s_theMux@ConnectionManagerFactoryPrivate@@0PEAVConnectionMultiplexer@Wns@@EA, 0; Wns::ConnectionMultiplexer * ConnectionManagerFactoryPrivate::s_theMux
0x180016cb4  jnz     short loc_180016CF3
0x180016cb6  mov     rcx, [rsp+198h]; this
0x180016cbe  mov     ebx, 80004003h
0x180016cc3  mov     r9d, ebx; char *
0x180016cc6  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180016ccd  mov     edx, 33h ; '3'; void *
0x180016cd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016cd7  nop
0x180016cd8  mov     rcx, rsi; SRWLock
0x180016cdb  call    cs:__imp_ReleaseSRWLockExclusive
0x180016ce1  nop
0x180016ce2  lea     rcx, [rsp+198h+var_168]; this
0x180016ce7  call    ??1WnsMuxMakeCM@WnsCPLog@@QEAA@XZ; WnsCPLog::WnsMuxMakeCM::~WnsMuxMakeCM(void)
0x180016cec  mov     eax, ebx
0x180016cee  jmp     loc_180016D76
0x180016cf3  lea     rcx, [rsp+198h+var_178]
0x180016cf8  call    ??$Make@VWpnConnectionManager@@AEAPEAVConnectionMultiplexer@Wns@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWpnConnectionManager@@@12@AEAPEAVConnectionMultiplexer@Wns@@@Z; Microsoft::WRL::Details::Make<WpnConnectionManager,Wns::ConnectionMultiplexer * &>(Wns::ConnectionMultiplexer * &)
0x180016cfd  inc     cs:?s_muxRefCount@ConnectionManagerFactoryPrivate@@0IA; uint ConnectionManagerFactoryPrivate::s_muxRefCount
0x180016d03  mov     rax, [rsp+198h+var_178]
0x180016d08  mov     [rsp+198h+var_178], 0
0x180016d11  mov     [rbx], rax
0x180016d14  xor     edx, edx
0x180016d16  lea     rcx, [rsp+198h+var_168]
0x180016d1b  call    ?Stop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180016d20  nop
0x180016d21  mov     rcx, [rsp+198h+var_178]
0x180016d26  test    rcx, rcx
0x180016d29  jz      short loc_180016D41
0x180016d2b  mov     [rsp+198h+var_178], 0
0x180016d34  mov     rax, [rcx]
0x180016d37  mov     rax, [rax+10h]
0x180016d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d40  nop
0x180016d41  mov     rcx, rsi; SRWLock
0x180016d44  call    cs:__imp_ReleaseSRWLockExclusive
0x180016d4a  nop
0x180016d4b  mov     [rsp+198h+var_168], r14
0x180016d50  lea     rcx, [rsp+198h+var_168]
0x180016d55  call    ?Destroy@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180016d5a  lea     rcx, [rsp+198h+var_168]
0x180016d5f  call    ??1?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180016d64  xor     eax, eax
0x180016d66  jmp     short loc_180016D76
0x180016d68  lea     rcx, [rsp+198h+var_168]; this
0x180016d6d  call    ??1WnsMuxMakeCM@WnsCPLog@@QEAA@XZ; WnsCPLog::WnsMuxMakeCM::~WnsMuxMakeCM(void)
0x180016d72  mov     eax, dword ptr [rsp+198h+var_178]
0x180016d76  mov     rcx, [rsp+198h+var_18]
0x180016d7e  xor     rcx, rsp; StackCookie
0x180016d81  call    __security_check_cookie
0x180016d86  lea     r11, [rsp+198h+var_8]
0x180016d8e  mov     rbx, [r11+10h]
0x180016d92  mov     rsi, [r11+20h]
0x180016d96  mov     rsp, r11
0x180016d99  pop     r14
0x180016d9b  retn
```
