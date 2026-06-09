# Broker::BrokerBase::StartRpcServer(ushort const *,long (*)(void *,void *))

- ea: `0x180010b84`
- end: `0x180010c4e`
- name: `?StartRpcServer@BrokerBase@Broker@@QEAAXPEBGP6AJPEAX1@Z@Z`
- size: `202`
- prototype: `void __fastcall(Broker::BrokerBase *__hidden this, const unsigned __int16 *, int (*)(void *, void *))`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800109f0`

## callees

- `0x180005b50`
- `0x180010b84`
- `0x180010d68`
- `0x180014218`
- `0x180015b14`
- `0x1800165da`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Broker::BrokerBase::StartRpcServer(
        Broker::BrokerBase *this,
        const unsigned __int16 *a2,
        int (*a3)(void *, void *))
{
  Broker::RpcServerRegistration *v6; // rax
  const unsigned __int16 *v7; // rdx
  struct _GUID *v8; // r8
  Broker::RpcServerRegistration *v9; // rax
  void **pExceptionObject; // [rsp+50h] [rbp-38h] BYREF
  __int128 v11; // [rsp+58h] [rbp-30h]
  int v12; // [rsp+68h] [rbp-20h]
  int v13; // [rsp+70h] [rbp-18h]

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
      *((_QWORD *)this + 1));
  if ( a2 || a3 )
  {
    v11 = 0;
    v12 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v13 = 50;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  v6 = (Broker::RpcServerRegistration *)operator new(0x20u);
  v9 = Broker::RpcServerRegistration::RpcServerRegistration(v6, v7, v8, *((struct _GUID **)this + 1));
  std::shared_ptr<Broker::RpcServerRegistration>::reset<Broker::RpcServerRegistration,0>((char *)this + 288, v9);
}

```

## disassembly

```asm
0x180010b84  mov     [rsp+arg_0], rbx
0x180010b89  mov     [rsp+arg_10], rsi
0x180010b8e  push    rdi
0x180010b8f  sub     rsp, 80h
0x180010b96  mov     rdi, r8
0x180010b99  mov     rsi, rdx
0x180010b9c  mov     rbx, rcx
0x180010b9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ba6  test    dword ptr [rcx+1Ch], 800h
0x180010bad  jz      short loc_180010BCE
0x180010baf  cmp     byte ptr [rcx+19h], 5
0x180010bb3  jb      short loc_180010BCE
0x180010bb5  mov     edx, 19h
0x180010bba  mov     r9, [rbx+8]
0x180010bbe  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x180010bc5  mov     rcx, [rcx+10h]
0x180010bc9  call    WPP_SF__guid_
0x180010bce  test    rsi, rsi
0x180010bd1  jnz     short loc_180010C18
0x180010bd3  test    rdi, rdi
0x180010bd6  jnz     short loc_180010C18
0x180010bd8  lea     ecx, [rsi+20h]; Size
0x180010bdb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010be0  mov     [rsp+88h+arg_8], rax
0x180010be8  mov     r9, [rbx+8]; struct _GUID *
0x180010bec  mov     rcx, rax; this
0x180010bef  call    ??0RpcServerRegistration@Broker@@QEAA@PEAXPEBU_GUID@@1PEBG22KP6AJ00@Z_N@Z; Broker::RpcServerRegistration::RpcServerRegistration(void *,_GUID const *,_GUID const *,ushort const *,ushort const *,ushort const *,ulong,long (*)(void *,void *),bool)
0x180010bf4  nop
0x180010bf5  lea     rcx, [rbx+120h]
0x180010bfc  mov     rdx, rax
0x180010bff  lea     r11, [rsp+88h+var_8]
0x180010c07  mov     rbx, [r11+10h]
0x180010c0b  mov     rsi, [r11+20h]
0x180010c0f  mov     rsp, r11
0x180010c12  pop     rdi
0x180010c13  jmp     ??$reset@VRpcServerRegistration@Broker@@$0A@@?$shared_ptr@VRpcServerRegistration@Broker@@@std@@QEAAXPEAVRpcServerRegistration@Broker@@@Z; std::shared_ptr<Broker::RpcServerRegistration>::reset<Broker::RpcServerRegistration,0>(Broker::RpcServerRegistration *)
0x180010c18  xorps   xmm0, xmm0
0x180010c1b  movups  [rsp+88h+var_30], xmm0
0x180010c20  mov     [rsp+88h+var_20], 1
0x180010c28  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180010c2f  mov     [rsp+88h+pExceptionObject], rax
0x180010c34  mov     [rsp+88h+var_18], 32h ; '2'
0x180010c3c  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180010c43  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180010c48  call    _CxxThrowException_0
```
