# BrFindBrokeredEvent2

- ea: `0x180009ee0`
- end: `0x18000a0c2`
- name: `BrFindBrokeredEvent2`
- size: `482`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180004ae0`
- `0x180004d70`
- `0x1800058e0`
- `0x180005b50`
- `0x180006b30`
- `0x180009e94`
- `0x180009ee0`
- `0x18000a0d0`
- `0x18000a18c`
- `0x180015af0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BrFindBrokeredEvent2(const void *a1, __int64 a2, void *a3, const unsigned __int16 *a4, _QWORD *a5)
{
  unsigned int v7; // ebx
  __int64 v8; // r14
  __int64 v9; // rdi
  __int64 v11; // [rsp+28h] [rbp-D0h] BYREF
  std::_Ref_count_base *v12; // [rsp+30h] [rbp-C8h]
  __int64 v13; // [rsp+38h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+40h] [rbp-B8h] BYREF
  std::_Ref_count_base *v15; // [rsp+48h] [rbp-B0h]
  _BYTE v16[96]; // [rsp+60h] [rbp-98h] BYREF

  v13 = a2;
  if ( !a1 || !a5 || !a3 && a4 || (v7 = 0, a3) && !a4 )
  {
    v7 = 87;
LABEL_26:
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids, v7);
    return v7;
  }
  Broker::BrokerBase::GetInstance(&v14, a1);
  v8 = v14;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
      *(_QWORD *)(v14 + 8));
  Broker::BrokeredEventTable::Find(v8 + 208, &v11, &v13);
  if ( a3 && a4 )
  {
    Broker::ApplicationIdentity::ApplicationIdentity((Broker::ApplicationIdentity *)v16, a3, a4);
    v9 = v11;
    if ( Broker::ApplicationIdentity::operator!=((__int64)v16, *(_QWORD *)(v11 + 48)) )
    {
      v7 = 5;
      Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v16);
      if ( v12 )
        std::_Ref_count_base::_Decref(v12);
      if ( v15 )
        std::_Ref_count_base::_Decref(v15);
      goto LABEL_26;
    }
    Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v16);
  }
  else
  {
    v9 = v11;
  }
  *a5 = *(_QWORD *)(v9 + 16);
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  return v7;
}

```

## disassembly

```asm
0x180009ee0  push    rbx
0x180009ee2  push    rsi
0x180009ee3  push    rdi
0x180009ee4  push    r14
0x180009ee6  push    r15
0x180009ee8  sub     rsp, 0D0h
0x180009eef  mov     rax, cs:__security_cookie
0x180009ef6  xor     rax, rsp
0x180009ef9  mov     [rsp+0F8h+var_38], rax
0x180009f01  mov     rsi, r9
0x180009f04  mov     rdi, r8
0x180009f07  mov     [rsp+0F8h+var_C0], rdx
0x180009f0c  mov     r15, [rsp+0F8h+arg_20]
0x180009f14  test    rcx, rcx
0x180009f17  jz      loc_18000A01E
0x180009f1d  test    r15, r15
0x180009f20  jz      loc_18000A01E
0x180009f26  test    r8, r8
0x180009f29  jz      loc_18000A05D
0x180009f2f  xor     ebx, ebx
0x180009f31  test    rdi, rdi
0x180009f34  jnz     loc_18000A025
0x180009f3a  mov     rdx, rcx
0x180009f3d  lea     rcx, [rsp+0F8h+var_B8]
0x180009f42  call    ?GetInstance@BrokerBase@Broker@@SA?AV?$shared_ptr@VBrokerBase@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokerBase::GetInstance(_GUID const &)
0x180009f47  nop
0x180009f48  mov     r14, [rsp+0F8h+var_B8]
0x180009f4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f54  test    dword ptr [rcx+1Ch], 800h
0x180009f5b  jz      short loc_180009F7C
0x180009f5d  cmp     byte ptr [rcx+19h], 5
0x180009f61  jb      short loc_180009F7C
0x180009f63  mov     edx, 23h ; '#'
0x180009f68  mov     r9, [r14+8]
0x180009f6c  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x180009f73  mov     rcx, [rcx+10h]
0x180009f77  call    WPP_SF__guid_
0x180009f7c  lea     rcx, [r14+0D0h]
0x180009f83  lea     r8, [rsp+0F8h+var_C0]
0x180009f88  lea     rdx, [rsp+0F8h+var_D0]
0x180009f8d  call    ?Find@BrokeredEventTable@Broker@@QEAA?AV?$shared_ptr@VBrokerEvent@Broker@@@std@@AEBU_CBROKERED_EVENT_ID@@@Z; Broker::BrokeredEventTable::Find(_CBROKERED_EVENT_ID const &)
0x180009f92  nop
0x180009f93  test    rdi, rdi
0x180009f96  jz      loc_18000A067
0x180009f9c  test    rsi, rsi
0x180009f9f  jz      loc_18000A067
0x180009fa5  mov     r8, rsi; unsigned __int16 *
0x180009fa8  mov     rdx, rdi; void *
0x180009fab  lea     rcx, [rsp+0F8h+var_98]; this
0x180009fb0  call    ??0ApplicationIdentity@Broker@@QEAA@PEAXQEBG@Z; Broker::ApplicationIdentity::ApplicationIdentity(void *,ushort const * const)
0x180009fb5  mov     rdi, [rsp+0F8h+var_D0]
0x180009fba  mov     rdx, [rdi+30h]
0x180009fbe  lea     rcx, [rsp+0F8h+var_98]
0x180009fc3  call    ??9ApplicationIdentity@Broker@@QEBA_NAEBU01@@Z; Broker::ApplicationIdentity::operator!=(Broker::ApplicationIdentity const &)
0x180009fc8  lea     rcx, [rsp+0F8h+var_98]; this
0x180009fcd  test    al, al
0x180009fcf  jnz     short loc_18000A030
0x180009fd1  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x180009fd6  mov     rax, [rdi+10h]
0x180009fda  mov     [r15], rax
0x180009fdd  mov     rcx, [rsp+0F8h+var_C8]; this
0x180009fe2  test    rcx, rcx
0x180009fe5  jz      short loc_180009FED
0x180009fe7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180009fec  nop
0x180009fed  mov     rcx, [rsp+0F8h+var_B0]; this
0x180009ff2  test    rcx, rcx
0x180009ff5  jz      short loc_180009FFD
0x180009ff7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180009ffc  nop
0x180009ffd  mov     eax, ebx
0x180009fff  mov     rcx, [rsp+0F8h+var_38]
0x18000a007  xor     rcx, rsp; StackCookie
0x18000a00a  call    __security_check_cookie
0x18000a00f  add     rsp, 0D0h
0x18000a016  pop     r15
0x18000a018  pop     r14
0x18000a01a  pop     rdi
0x18000a01b  pop     rsi
0x18000a01c  pop     rbx
0x18000a01d  retn
0x18000a01e  mov     ebx, 57h ; 'W'
0x18000a023  jmp     short loc_18000A087
0x18000a025  test    rsi, rsi
0x18000a028  jnz     loc_180009F3A
0x18000a02e  jmp     short loc_18000A01E
0x18000a030  mov     ebx, 5
0x18000a035  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x18000a03a  nop
0x18000a03b  mov     rcx, [rsp+0F8h+var_C8]; this
0x18000a040  test    rcx, rcx
0x18000a043  jz      short loc_18000A04B
0x18000a045  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a04a  nop
0x18000a04b  mov     rcx, [rsp+0F8h+var_B0]; this
0x18000a050  test    rcx, rcx
0x18000a053  jz      short loc_18000A05B
0x18000a055  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a05a  nop
0x18000a05b  jmp     short loc_18000A087
0x18000a05d  test    rsi, rsi
0x18000a060  jnz     short loc_18000A01E
0x18000a062  jmp     loc_180009F2F
0x18000a067  mov     rdi, [rsp+0F8h+var_D0]
0x18000a06c  jmp     loc_180009FD6
0x18000a071  jmp     short $+2
0x18000a073  mov     ebx, [rsp+0F8h+var_D8]
0x18000a077  jmp     short loc_18000A087
0x18000a079  jmp     short loc_18000A073
0x18000a07b  mov     ebx, [rsp+0F8h+var_D8]
0x18000a07f  test    ebx, ebx
0x18000a081  jz      loc_180009FFD
0x18000a087  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a08e  test    dword ptr [rcx+1Ch], 800h
0x18000a095  jz      loc_180009FFD
0x18000a09b  cmp     byte ptr [rcx+19h], 2
0x18000a09f  jb      loc_180009FFD
0x18000a0a5  mov     edx, 18h
0x18000a0aa  mov     r9d, ebx
0x18000a0ad  lea     r8, WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids
0x18000a0b4  mov     rcx, [rcx+10h]
0x18000a0b8  call    WPP_SF_d
0x18000a0bd  jmp     loc_180009FFD
```
