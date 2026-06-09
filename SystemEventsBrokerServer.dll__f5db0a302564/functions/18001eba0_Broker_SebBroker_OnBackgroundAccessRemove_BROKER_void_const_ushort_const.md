# Broker::SebBroker::OnBackgroundAccessRemove(_BROKER *,void * const,ushort const *)

- ea: `0x18001eba0`
- end: `0x18001ecca`
- name: `?OnBackgroundAccessRemove@SebBroker@Broker@@CAKPEAU_BROKER@@QEAXPEBG@Z`
- size: `298`
- prototype: `__int64 __fastcall(struct _BROKER *, void *const, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002680`
- `0x1800030e0`
- `0x180005a50`
- `0x1800076a0`
- `0x1800095f0`
- `0x18000f370`
- `0x18001cf50`
- `0x18001eba0`
- `0x18001ecd0`

## pseudocode

```c
__int64 __fastcall Broker::SebBroker::OnBackgroundAccessRemove(
        struct _BROKER *a1,
        void *const a2,
        unsigned __int16 *a3)
{
  unsigned int v6; // ebx
  Broker::SebBroker *v7; // rdi
  Broker::SebBroker *v9; // [rsp+28h] [rbp-A0h] BYREF
  std::_Ref_count_base *v10; // [rsp+30h] [rbp-98h]
  Broker::Win32Error *v11; // [rsp+38h] [rbp-90h] BYREF
  char *v12[12]; // [rsp+40h] [rbp-88h] BYREF

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
  Broker::SebBroker::GetInstance(&v9);
  if ( a1 )
  {
    v7 = v9;
    if ( v9 )
    {
      v6 = 0;
      if ( *((struct _BROKER **)v9 + 17) == a1 )
      {
        try
        {
          Broker::ApplicationIdentity::ApplicationIdentity(v12, a2, a3);
          Broker::SebBroker::OnBackgroundAccessStateChange(v7, (const struct Broker::ApplicationIdentity *)v12, 0);
          Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v12);
        }
        catch ( Broker::Win32Error *v11 )
        {
          v6 = *((_DWORD *)v11 + 8);
        }
        catch ( ... )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
          v6 = 1359;
        }
      }
      else
      {
        v6 = 5;
      }
    }
    else
    {
      v6 = 21;
    }
  }
  else
  {
    v6 = 87;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v6);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  return v6;
}

```

## disassembly

```asm
0x18001eba0  mov     [rsp+arg_0], rbx
0x18001eba5  mov     [rsp+arg_18], rsi
0x18001ebaa  push    rdi
0x18001ebab  push    r14
0x18001ebad  push    r15
0x18001ebaf  sub     rsp, 0B0h
0x18001ebb6  mov     rax, cs:__security_cookie
0x18001ebbd  xor     rax, rsp
0x18001ebc0  mov     [rsp+0C8h+var_28], rax
0x18001ebc8  mov     r15, r8
0x18001ebcb  mov     r14, rdx
0x18001ebce  mov     rsi, rcx
0x18001ebd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ebd8  test    byte ptr [rcx+1Ch], 1
0x18001ebdc  jz      short loc_18001EBF9
0x18001ebde  cmp     byte ptr [rcx+19h], 4
0x18001ebe2  jb      short loc_18001EBF9
0x18001ebe4  mov     edx, 4Ch ; 'L'
0x18001ebe9  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18001ebf0  mov     rcx, [rcx+10h]
0x18001ebf4  call    WPP_SF_
0x18001ebf9  lea     rcx, [rsp+0C8h+var_A0]
0x18001ebfe  call    ?GetInstance@SebBroker@Broker@@SA?AV?$shared_ptr@VSebBroker@Broker@@@std@@XZ; Broker::SebBroker::GetInstance(void)
0x18001ec03  nop
0x18001ec04  test    rsi, rsi
0x18001ec07  jnz     short loc_18001EC0E
0x18001ec09  lea     ebx, [rsi+57h]
0x18001ec0c  jmp     short loc_18001EC64
0x18001ec0e  mov     rdi, [rsp+0C8h+var_A0]
0x18001ec13  test    rdi, rdi
0x18001ec16  jnz     short loc_18001EC1D
0x18001ec18  lea     ebx, [rdi+15h]
0x18001ec1b  jmp     short loc_18001EC64
0x18001ec1d  xor     ebx, ebx
0x18001ec1f  cmp     [rdi+88h], rsi
0x18001ec26  jz      short loc_18001EC2F
0x18001ec28  mov     ebx, 5
0x18001ec2d  jmp     short loc_18001EC64
0x18001ec2f  mov     r8, r15; unsigned __int16 *
0x18001ec32  mov     rdx, r14; void *
0x18001ec35  lea     rcx, [rsp+0C8h+var_88]; this
0x18001ec3a  call    ??0ApplicationIdentity@Broker@@QEAA@PEAXQEBG@Z; Broker::ApplicationIdentity::ApplicationIdentity(void *,ushort const * const)
0x18001ec3f  nop
0x18001ec40  xor     r8d, r8d; bool
0x18001ec43  lea     rdx, [rsp+0C8h+var_88]; struct Broker::ApplicationIdentity *
0x18001ec48  mov     rcx, rdi; this
0x18001ec4b  call    ?OnBackgroundAccessStateChange@SebBroker@Broker@@AEAAXAEBUApplicationIdentity@2@_N@Z; Broker::SebBroker::OnBackgroundAccessStateChange(Broker::ApplicationIdentity const &,bool)
0x18001ec50  nop
0x18001ec51  lea     rcx, [rsp+0C8h+var_88]; this
0x18001ec56  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x18001ec5b  nop
0x18001ec5c  jmp     short loc_18001EC64
0x18001ec5e  jmp     short $+2
0x18001ec60  mov     ebx, [rsp+0C8h+var_A8]
0x18001ec64  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec6b  test    byte ptr [rcx+1Ch], 1
0x18001ec6f  jz      short loc_18001EC90
0x18001ec71  cmp     byte ptr [rcx+19h], 4
0x18001ec75  jb      short loc_18001EC90
0x18001ec77  mov     edx, 4Eh ; 'N'
0x18001ec7c  mov     r9d, ebx
0x18001ec7f  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18001ec86  mov     rcx, [rcx+10h]
0x18001ec8a  call    WPP_SF_d
0x18001ec8f  nop
0x18001ec90  mov     rcx, [rsp+0C8h+var_98]; this
0x18001ec95  test    rcx, rcx
0x18001ec98  jz      short loc_18001EC9F
0x18001ec9a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ec9f  mov     eax, ebx
0x18001eca1  mov     rcx, [rsp+0C8h+var_28]
0x18001eca9  xor     rcx, rsp; StackCookie
0x18001ecac  call    __security_check_cookie
0x18001ecb1  lea     r11, [rsp+0C8h+var_18]
0x18001ecb9  mov     rbx, [r11+20h]
0x18001ecbd  mov     rsi, [r11+38h]
0x18001ecc1  mov     rsp, r11
0x18001ecc4  pop     r15
0x18001ecc6  pop     r14
0x18001ecc8  pop     rdi
0x18001ecc9  retn
```
