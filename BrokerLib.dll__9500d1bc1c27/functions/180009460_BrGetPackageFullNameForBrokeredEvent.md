# BrGetPackageFullNameForBrokeredEvent

- ea: `0x180009460`
- end: `0x180009603`
- name: `BrGetPackageFullNameForBrokeredEvent`
- size: `419`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180004ae0`
- `0x180004d70`
- `0x1800058e0`
- `0x180005a00`
- `0x18000800c`
- `0x180009460`
- `0x180009e94`
- `0x180015af0`
- `0x1800165aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BrGetPackageFullNameForBrokeredEvent(const void *a1, __int64 a2, unsigned int a3, char *a4)
{
  unsigned __int64 v5; // r15
  unsigned int v7; // ebx
  __int64 v8; // rsi
  const void *p_Src; // rdx
  int v12; // [rsp+20h] [rbp-B8h]
  int v13; // [rsp+20h] [rbp-B8h]
  int v14; // [rsp+20h] [rbp-B8h]
  __int64 v15; // [rsp+28h] [rbp-B0h] BYREF
  std::_Ref_count_base *v16; // [rsp+30h] [rbp-A8h]
  __int64 v17; // [rsp+38h] [rbp-A0h] BYREF
  std::_Ref_count_base *v18; // [rsp+40h] [rbp-98h]
  Broker::Win32Error *v19; // [rsp+48h] [rbp-90h] BYREF
  _BYTE v20[56]; // [rsp+50h] [rbp-88h] BYREF
  void *Src; // [rsp+88h] [rbp-50h] BYREF
  __int64 v22; // [rsp+98h] [rbp-40h]
  unsigned __int64 v23; // [rsp+A0h] [rbp-38h]

  v5 = a3;
  if ( !a1 || !a2 || (v7 = 0, !a4) )
  {
    v7 = 87;
LABEL_21:
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids, v7);
    return v7;
  }
  try
  {
    Broker::BrokerBase::GetInstance(&v17, a1);
    Broker::BrokerBase::FindEvent(v17, &v15, a2);
    Broker::ApplicationIdentity::ApplicationIdentity(
      (Broker::ApplicationIdentity *)v20,
      *(const struct Broker::ApplicationIdentity **)(v15 + 48));
  }
  catch ( Broker::NotFound )
  {
    v12 = 1168;
    v7 = v12;
    goto LABEL_21;
  }
  catch ( std::bad_alloc )
  {
    v13 = 14;
    v7 = v13;
    goto LABEL_21;
  }
  catch ( Broker::Win32Error *v19 )
  {
    v7 = *((_DWORD *)v19 + 8);
    if ( !v7 )
      return v7;
    goto LABEL_21;
  }
  catch ( ... )
  {
    v14 = 1287;
    v7 = v14;
    goto LABEL_21;
  }
  v8 = 2 * v22;
  if ( v5 < 2 * v22 + 2 )
  {
    v7 = 87;
    Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v20);
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
    goto LABEL_21;
  }
  p_Src = &Src;
  if ( v23 > 7 )
    p_Src = Src;
  memcpy_0(a4, p_Src, 2 * v22);
  *(_WORD *)&a4[v8] = 0;
  Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v20);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  return v7;
}

```

## disassembly

```asm
0x180009460  mov     [rsp+arg_0], rbx
0x180009465  mov     [rsp+arg_10], rsi
0x18000946a  push    rdi
0x18000946b  push    r14
0x18000946d  push    r15
0x18000946f  sub     rsp, 0C0h
0x180009476  mov     rax, cs:__security_cookie
0x18000947d  xor     rax, rsp
0x180009480  mov     [rsp+0D8h+var_28], rax
0x180009488  mov     r14, r9
0x18000948b  mov     r15d, r8d
0x18000948e  mov     rsi, rdx
0x180009491  xor     edi, edi
0x180009493  test    rcx, rcx
0x180009496  jz      loc_18000957D
0x18000949c  test    rdx, rdx
0x18000949f  jz      loc_18000957D
0x1800094a5  mov     ebx, edi
0x1800094a7  test    r9, r9
0x1800094aa  jz      loc_18000957D
0x1800094b0  mov     rdx, rcx
0x1800094b3  lea     rcx, [rsp+0D8h+var_A0]
0x1800094b8  call    ?GetInstance@BrokerBase@Broker@@SA?AV?$shared_ptr@VBrokerBase@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokerBase::GetInstance(_GUID const &)
0x1800094bd  nop
0x1800094be  mov     r8, rsi
0x1800094c1  lea     rdx, [rsp+0D8h+var_B0]
0x1800094c6  mov     rcx, [rsp+0D8h+var_A0]
0x1800094cb  call    ?FindEvent@BrokerBase@Broker@@QEAA?AV?$shared_ptr@VBrokerEvent@Broker@@@std@@PEAU_BROKERED_EVENT@@@Z; Broker::BrokerBase::FindEvent(_BROKERED_EVENT *)
0x1800094d0  nop
0x1800094d1  mov     rdx, [rsp+0D8h+var_B0]
0x1800094d6  mov     rdx, [rdx+30h]; struct Broker::ApplicationIdentity *
0x1800094da  lea     rcx, [rsp+0D8h+var_88]; this
0x1800094df  call    ??0ApplicationIdentity@Broker@@QEAA@AEBU01@@Z; Broker::ApplicationIdentity::ApplicationIdentity(Broker::ApplicationIdentity const &)
0x1800094e4  mov     rax, [rsp+0D8h+var_40]
0x1800094ec  lea     rsi, [rax+rax]
0x1800094f0  lea     rcx, [rsi+2]
0x1800094f4  cmp     r15, rcx
0x1800094f7  jb      loc_180009584
0x1800094fd  lea     rdx, [rsp+0D8h+Src]
0x180009505  cmp     [rsp+0D8h+var_38], 7
0x18000950e  cmova   rdx, [rsp+0D8h+Src]; Src
0x180009517  mov     r8, rsi; Size
0x18000951a  mov     rcx, r14; void *
0x18000951d  call    memcpy_0
0x180009522  mov     [rsi+r14], di
0x180009527  lea     rcx, [rsp+0D8h+var_88]; this
0x18000952c  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x180009531  nop
0x180009532  mov     rcx, [rsp+0D8h+var_A8]; this
0x180009537  test    rcx, rcx
0x18000953a  jz      short loc_180009542
0x18000953c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180009541  nop
0x180009542  mov     rcx, [rsp+0D8h+var_98]; this
0x180009547  test    rcx, rcx
0x18000954a  jz      short loc_180009552
0x18000954c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180009551  nop
0x180009552  mov     eax, ebx
0x180009554  mov     rcx, [rsp+0D8h+var_28]
0x18000955c  xor     rcx, rsp; StackCookie
0x18000955f  call    __security_check_cookie
0x180009564  lea     r11, [rsp+0D8h+var_18]
0x18000956c  mov     rbx, [r11+20h]
0x180009570  mov     rsi, [r11+30h]
0x180009574  mov     rsp, r11
0x180009577  pop     r15
0x180009579  pop     r14
0x18000957b  pop     rdi
0x18000957c  retn
0x18000957d  mov     ebx, 57h ; 'W'
0x180009582  jmp     short loc_1800095C8
0x180009584  mov     ebx, 57h ; 'W'
0x180009589  lea     rcx, [rsp+0D8h+var_88]; this
0x18000958e  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x180009593  nop
0x180009594  mov     rcx, [rsp+0D8h+var_A8]; this
0x180009599  test    rcx, rcx
0x18000959c  jz      short loc_1800095A4
0x18000959e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800095a3  nop
0x1800095a4  mov     rcx, [rsp+0D8h+var_98]; this
0x1800095a9  test    rcx, rcx
0x1800095ac  jz      short loc_1800095B4
0x1800095ae  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800095b3  nop
0x1800095b4  jmp     short loc_1800095C8
0x1800095b6  jmp     short $+2
0x1800095b8  mov     ebx, [rsp+0D8h+var_B8]
0x1800095bc  jmp     short loc_1800095C8
0x1800095be  jmp     short loc_1800095B8
0x1800095c0  mov     ebx, [rsp+0D8h+var_B8]
0x1800095c4  test    ebx, ebx
0x1800095c6  jz      short loc_180009552
0x1800095c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095cf  test    dword ptr [rcx+1Ch], 800h
0x1800095d6  jz      loc_180009552
0x1800095dc  cmp     byte ptr [rcx+19h], 2
0x1800095e0  jb      loc_180009552
0x1800095e6  mov     edx, 19h
0x1800095eb  mov     r9d, ebx
0x1800095ee  lea     r8, WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids
0x1800095f5  mov     rcx, [rcx+10h]
0x1800095f9  call    WPP_SF_d
0x1800095fe  jmp     loc_180009552
```
