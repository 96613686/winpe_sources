# BrFindBrokeredEvent

- ea: `0x180009bb0`
- end: `0x180009d95`
- name: `BrFindBrokeredEvent`
- size: `485`
- prototype: `__int64 __fastcall(__int64, __int64, void *, const unsigned __int16 *, _QWORD *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180004ae0`
- `0x180004d70`
- `0x1800058e0`
- `0x180005b50`
- `0x180006b30`
- `0x180009bb0`
- `0x180009d9c`
- `0x180009e94`
- `0x18000a0d0`
- `0x180015af0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BrFindBrokeredEvent(const void *a1, __int64 a2, void *a3, const unsigned __int16 *a4, _QWORD *a5)
{
  unsigned int v8; // ebx
  __int64 v9; // r14
  __int64 v10; // rdi
  __int64 v12; // [rsp+28h] [rbp-C0h] BYREF
  std::_Ref_count_base *v13; // [rsp+30h] [rbp-B8h]
  __int64 v14; // [rsp+38h] [rbp-B0h] BYREF
  std::_Ref_count_base *v15; // [rsp+40h] [rbp-A8h]
  _BYTE v16[96]; // [rsp+50h] [rbp-98h] BYREF

  if ( !a1 || !a5 || !a3 && a4 || (v8 = 0, a3) && !a4 )
  {
    v8 = 87;
LABEL_17:
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids, v8);
    return v8;
  }
  Broker::BrokerBase::GetInstance(&v14, a1);
  v9 = v14;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
      *(_QWORD *)(v14 + 8));
  Broker::BrokeredEventTable::Find(v9 + 208, &v12, a2);
  if ( a3 && a4 )
  {
    Broker::ApplicationIdentity::ApplicationIdentity((Broker::ApplicationIdentity *)v16, a3, a4);
    v10 = v12;
    if ( Broker::ApplicationIdentity::operator!=((__int64)v16, *(_QWORD *)(v12 + 48)) )
    {
      v8 = 5;
      Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v16);
      if ( v13 )
        std::_Ref_count_base::_Decref(v13);
      if ( v15 )
        std::_Ref_count_base::_Decref(v15);
      goto LABEL_17;
    }
    Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v16);
  }
  else
  {
    v10 = v12;
  }
  *a5 = *(_QWORD *)(v10 + 16);
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  return v8;
}

```

## disassembly

```asm
0x180009bb0  mov     [rsp+arg_0], rbx
0x180009bb5  push    rsi
0x180009bb6  push    rdi
0x180009bb7  push    r12
0x180009bb9  push    r14
0x180009bbb  push    r15
0x180009bbd  sub     rsp, 0C0h
0x180009bc4  mov     rax, cs:__security_cookie
0x180009bcb  xor     rax, rsp
0x180009bce  mov     [rsp+0E8h+var_38], rax
0x180009bd6  mov     rsi, r9
0x180009bd9  mov     rdi, r8
0x180009bdc  mov     r12, rdx
0x180009bdf  mov     r15, [rsp+0E8h+arg_20]
0x180009be7  test    rcx, rcx
0x180009bea  jz      loc_180009CC8
0x180009bf0  test    r15, r15
0x180009bf3  jz      loc_180009CC8
0x180009bf9  test    r8, r8
0x180009bfc  jnz     short loc_180009C07
0x180009bfe  test    r9, r9
0x180009c01  jnz     loc_180009CC8
0x180009c07  xor     ebx, ebx
0x180009c09  test    rdi, rdi
0x180009c0c  jnz     loc_180009D3C
0x180009c12  mov     rdx, rcx
0x180009c15  lea     rcx, [rsp+0E8h+var_B0]
0x180009c1a  call    ?GetInstance@BrokerBase@Broker@@SA?AV?$shared_ptr@VBrokerBase@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokerBase::GetInstance(_GUID const &)
0x180009c1f  nop
0x180009c20  mov     r14, [rsp+0E8h+var_B0]
0x180009c25  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c2c  test    dword ptr [rcx+1Ch], 800h
0x180009c33  jz      short loc_180009C54
0x180009c35  cmp     byte ptr [rcx+19h], 5
0x180009c39  jb      short loc_180009C54
0x180009c3b  mov     edx, 22h ; '"'
0x180009c40  mov     r9, [r14+8]
0x180009c44  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x180009c4b  mov     rcx, [rcx+10h]
0x180009c4f  call    WPP_SF__guid_
0x180009c54  lea     rcx, [r14+0D0h]
0x180009c5b  mov     r8, r12
0x180009c5e  lea     rdx, [rsp+0E8h+var_C0]
0x180009c63  call    ?Find@BrokeredEventTable@Broker@@QEAA?AV?$shared_ptr@VBrokerEvent@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokeredEventTable::Find(_GUID const &)
0x180009c68  nop
0x180009c69  test    rdi, rdi
0x180009c6c  jnz     loc_180009CFD
0x180009c72  mov     rdi, [rsp+0E8h+var_C0]
0x180009c77  mov     rax, [rdi+10h]
0x180009c7b  mov     [r15], rax
0x180009c7e  mov     rcx, [rsp+0E8h+var_B8]; this
0x180009c83  test    rcx, rcx
0x180009c86  jz      short loc_180009C8E
0x180009c88  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180009c8d  nop
0x180009c8e  mov     rcx, [rsp+0E8h+var_A8]; this
0x180009c93  test    rcx, rcx
0x180009c96  jz      short loc_180009C9E
0x180009c98  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180009c9d  nop
0x180009c9e  mov     eax, ebx
0x180009ca0  mov     rcx, [rsp+0E8h+var_38]
0x180009ca8  xor     rcx, rsp; StackCookie
0x180009cab  call    __security_check_cookie
0x180009cb0  mov     rbx, [rsp+0E8h+arg_0]
0x180009cb8  add     rsp, 0C0h
0x180009cbf  pop     r15
0x180009cc1  pop     r14
0x180009cc3  pop     r12
0x180009cc5  pop     rdi
0x180009cc6  pop     rsi
0x180009cc7  retn
0x180009cc8  mov     ebx, 57h ; 'W'
0x180009ccd  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cd4  test    dword ptr [rcx+1Ch], 800h
0x180009cdb  jz      short loc_180009C9E
0x180009cdd  cmp     byte ptr [rcx+19h], 2
0x180009ce1  jb      short loc_180009C9E
0x180009ce3  mov     edx, 17h
0x180009ce8  mov     r9d, ebx
0x180009ceb  lea     r8, WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids
0x180009cf2  mov     rcx, [rcx+10h]
0x180009cf6  call    WPP_SF_d
0x180009cfb  jmp     short loc_180009C9E
0x180009cfd  test    rsi, rsi
0x180009d00  jz      loc_180009C72
0x180009d06  mov     r8, rsi; unsigned __int16 *
0x180009d09  mov     rdx, rdi; void *
0x180009d0c  lea     rcx, [rsp+0E8h+var_98]; this
0x180009d11  call    ??0ApplicationIdentity@Broker@@QEAA@PEAXQEBG@Z; Broker::ApplicationIdentity::ApplicationIdentity(void *,ushort const * const)
0x180009d16  mov     rdi, [rsp+0E8h+var_C0]
0x180009d1b  mov     rdx, [rdi+30h]
0x180009d1f  lea     rcx, [rsp+0E8h+var_98]
0x180009d24  call    ??9ApplicationIdentity@Broker@@QEBA_NAEBU01@@Z; Broker::ApplicationIdentity::operator!=(Broker::ApplicationIdentity const &)
0x180009d29  lea     rcx, [rsp+0E8h+var_98]; this
0x180009d2e  test    al, al
0x180009d30  jnz     short loc_180009D47
0x180009d32  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x180009d37  jmp     loc_180009C77
0x180009d3c  test    rsi, rsi
0x180009d3f  jnz     loc_180009C12
0x180009d45  jmp     short loc_180009CC8
0x180009d47  mov     ebx, 5
0x180009d4c  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x180009d51  nop
0x180009d52  mov     rcx, [rsp+0E8h+var_B8]; this
0x180009d57  test    rcx, rcx
0x180009d5a  jz      short loc_180009D62
0x180009d5c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180009d61  nop
0x180009d62  mov     rcx, [rsp+0E8h+var_A8]; this
0x180009d67  test    rcx, rcx
0x180009d6a  jz      short loc_180009D72
0x180009d6c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180009d71  nop
0x180009d72  jmp     loc_180009CCD
0x180009d77  jmp     short $+2
0x180009d79  mov     ebx, [rsp+0E8h+var_C8]
0x180009d7d  jmp     loc_180009CCD
0x180009d82  jmp     short loc_180009D79
0x180009d84  mov     ebx, [rsp+0E8h+var_C8]
0x180009d88  test    ebx, ebx
0x180009d8a  jnz     loc_180009CCD
0x180009d90  jmp     loc_180009C9E
```
