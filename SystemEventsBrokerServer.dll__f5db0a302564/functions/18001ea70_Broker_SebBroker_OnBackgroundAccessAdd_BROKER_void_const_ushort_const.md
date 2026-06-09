# Broker::SebBroker::OnBackgroundAccessAdd(_BROKER *,void * const,ushort const *)

- ea: `0x18001ea70`
- end: `0x18001eb9a`
- name: `?OnBackgroundAccessAdd@SebBroker@Broker@@CAKPEAU_BROKER@@QEAXPEBG@Z`
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
- `0x18001ea70`
- `0x18001ecd0`

## pseudocode

```c
__int64 __fastcall Broker::SebBroker::OnBackgroundAccessAdd(struct _BROKER *a1, void *const a2, unsigned __int16 *a3)
{
  unsigned int v6; // ebx
  Broker::SebBroker *v7; // rdi
  Broker::SebBroker *v9; // [rsp+28h] [rbp-A0h] BYREF
  std::_Ref_count_base *v10; // [rsp+30h] [rbp-98h]
  Broker::Win32Error *v11; // [rsp+38h] [rbp-90h] BYREF
  char *v12[12]; // [rsp+40h] [rbp-88h] BYREF

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
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
          Broker::SebBroker::OnBackgroundAccessStateChange(v7, (const struct Broker::ApplicationIdentity *)v12, 1);
          Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v12);
        }
        catch ( Broker::Win32Error *v11 )
        {
          v6 = *((_DWORD *)v11 + 8);
        }
        catch ( ... )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v6);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  return v6;
}

```

## disassembly

```asm
0x18001ea70  mov     [rsp+arg_0], rbx
0x18001ea75  mov     [rsp+arg_18], rsi
0x18001ea7a  push    rdi
0x18001ea7b  push    r14
0x18001ea7d  push    r15
0x18001ea7f  sub     rsp, 0B0h
0x18001ea86  mov     rax, cs:__security_cookie
0x18001ea8d  xor     rax, rsp
0x18001ea90  mov     [rsp+0C8h+var_28], rax
0x18001ea98  mov     r15, r8
0x18001ea9b  mov     r14, rdx
0x18001ea9e  mov     rsi, rcx
0x18001eaa1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eaa8  test    byte ptr [rcx+1Ch], 1
0x18001eaac  jz      short loc_18001EAC9
0x18001eaae  cmp     byte ptr [rcx+19h], 4
0x18001eab2  jb      short loc_18001EAC9
0x18001eab4  mov     edx, 49h ; 'I'
0x18001eab9  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18001eac0  mov     rcx, [rcx+10h]
0x18001eac4  call    WPP_SF_
0x18001eac9  lea     rcx, [rsp+0C8h+var_A0]
0x18001eace  call    ?GetInstance@SebBroker@Broker@@SA?AV?$shared_ptr@VSebBroker@Broker@@@std@@XZ; Broker::SebBroker::GetInstance(void)
0x18001ead3  nop
0x18001ead4  test    rsi, rsi
0x18001ead7  jnz     short loc_18001EADE
0x18001ead9  lea     ebx, [rsi+57h]
0x18001eadc  jmp     short loc_18001EB34
0x18001eade  mov     rdi, [rsp+0C8h+var_A0]
0x18001eae3  test    rdi, rdi
0x18001eae6  jnz     short loc_18001EAED
0x18001eae8  lea     ebx, [rdi+15h]
0x18001eaeb  jmp     short loc_18001EB34
0x18001eaed  xor     ebx, ebx
0x18001eaef  cmp     [rdi+88h], rsi
0x18001eaf6  jz      short loc_18001EAFF
0x18001eaf8  mov     ebx, 5
0x18001eafd  jmp     short loc_18001EB34
0x18001eaff  mov     r8, r15; unsigned __int16 *
0x18001eb02  mov     rdx, r14; void *
0x18001eb05  lea     rcx, [rsp+0C8h+var_88]; this
0x18001eb0a  call    ??0ApplicationIdentity@Broker@@QEAA@PEAXQEBG@Z; Broker::ApplicationIdentity::ApplicationIdentity(void *,ushort const * const)
0x18001eb0f  nop
0x18001eb10  mov     r8b, 1; bool
0x18001eb13  lea     rdx, [rsp+0C8h+var_88]; struct Broker::ApplicationIdentity *
0x18001eb18  mov     rcx, rdi; this
0x18001eb1b  call    ?OnBackgroundAccessStateChange@SebBroker@Broker@@AEAAXAEBUApplicationIdentity@2@_N@Z; Broker::SebBroker::OnBackgroundAccessStateChange(Broker::ApplicationIdentity const &,bool)
0x18001eb20  nop
0x18001eb21  lea     rcx, [rsp+0C8h+var_88]; this
0x18001eb26  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x18001eb2b  nop
0x18001eb2c  jmp     short loc_18001EB34
0x18001eb2e  jmp     short $+2
0x18001eb30  mov     ebx, [rsp+0C8h+var_A8]
0x18001eb34  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb3b  test    byte ptr [rcx+1Ch], 1
0x18001eb3f  jz      short loc_18001EB60
0x18001eb41  cmp     byte ptr [rcx+19h], 4
0x18001eb45  jb      short loc_18001EB60
0x18001eb47  mov     edx, 4Bh ; 'K'
0x18001eb4c  mov     r9d, ebx
0x18001eb4f  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18001eb56  mov     rcx, [rcx+10h]
0x18001eb5a  call    WPP_SF_d
0x18001eb5f  nop
0x18001eb60  mov     rcx, [rsp+0C8h+var_98]; this
0x18001eb65  test    rcx, rcx
0x18001eb68  jz      short loc_18001EB6F
0x18001eb6a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001eb6f  mov     eax, ebx
0x18001eb71  mov     rcx, [rsp+0C8h+var_28]
0x18001eb79  xor     rcx, rsp; StackCookie
0x18001eb7c  call    __security_check_cookie
0x18001eb81  lea     r11, [rsp+0C8h+var_18]
0x18001eb89  mov     rbx, [r11+20h]
0x18001eb8d  mov     rsi, [r11+38h]
0x18001eb91  mov     rsp, r11
0x18001eb94  pop     r15
0x18001eb96  pop     r14
0x18001eb98  pop     rdi
0x18001eb99  retn
```
