# Broker::TimeBroker::OnNetworkStateChange(bool)

- ea: `0x180005400`
- end: `0x18000574f`
- name: `?OnNetworkStateChange@TimeBroker@Broker@@QEAAX_N@Z`
- size: `847`
- prototype: `void __fastcall(Broker::TimeBroker *this, unsigned __int8)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000e890`

## callees

- `0x180003800`
- `0x180003840`
- `0x180005400`
- `0x180005b30`
- `0x180005b90`
- `0x180005d10`
- `0x180013978`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000549c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000549c`
- `BrokerLib!BrLockBroker` at `0x180005484`
- `BrokerLib!BrLockBroker` at `0x180005484`
- `BrokerLib!BrBufferFree` at `0x1800055ec`
- `BrokerLib!BrBufferFree` at `0x1800055ec`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180005567`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180005567`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x180005515`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x180005515`

## pseudocode

```c
void __fastcall Broker::TimeBroker::OnNetworkStateChange(Broker::TimeBroker *this, unsigned __int8 a2)
{
  std::_Ref_count_base *v4; // rbx
  struct _FILETIME *v5; // rdi
  int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // ebx
  unsigned int i; // ebx
  unsigned int BrokeredEventInfo2; // eax
  unsigned int v11; // edi
  __int64 *v12; // rdx
  __int64 v13; // rax
  std::_Ref_count_base *v14; // rdi
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-E8h] BYREF
  std::_Ref_count_base *v16; // [rsp+38h] [rbp-E0h]
  __int64 v17; // [rsp+40h] [rbp-D8h]
  std::_Ref_count_base *v18; // [rsp+48h] [rbp-D0h]
  void **pExceptionObject; // [rsp+50h] [rbp-C8h] BYREF
  __int128 v20; // [rsp+58h] [rbp-C0h]
  int v21; // [rsp+68h] [rbp-B0h]
  int v22; // [rsp+70h] [rbp-A8h]
  void **v23; // [rsp+78h] [rbp-A0h] BYREF
  __int128 v24; // [rsp+80h] [rbp-98h]
  int v25; // [rsp+90h] [rbp-88h]
  unsigned int v26; // [rsp+98h] [rbp-80h]
  void **v27; // [rsp+A0h] [rbp-78h] BYREF
  __int128 v28; // [rsp+A8h] [rbp-70h]
  int v29; // [rsp+B8h] [rbp-60h]
  unsigned int v30; // [rsp+C0h] [rbp-58h]
  unsigned int v31; // [rsp+120h] [rbp+8h] BYREF
  int v32; // [rsp+130h] [rbp+18h] BYREF
  __int64 v33; // [rsp+138h] [rbp+20h] BYREF

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, a2);
  if ( *((_QWORD *)this + 24) )
  {
    v31 = 0;
    v33 = 0;
    v32 = 0;
    v4 = *(&Broker::TimeBroker::Instance + 1);
    if ( *(&Broker::TimeBroker::Instance + 1) )
    {
      _InterlockedIncrement((volatile signed __int32 *)*(&Broker::TimeBroker::Instance + 1) + 2);
      v4 = *(&Broker::TimeBroker::Instance + 1);
    }
    v5 = (struct _FILETIME *)Broker::TimeBroker::Instance;
    SystemTimeAsFileTime = (struct _FILETIME)Broker::TimeBroker::Instance;
    v16 = v4;
    v6 = BrLockBroker(*((_QWORD *)Broker::TimeBroker::Instance + 24));
    if ( v6 )
    {
      v20 = 0;
      v21 = 1;
      pExceptionObject = &Broker::Win32Error::`vftable';
      v22 = v6;
      throw (Broker::Win32Error *)&pExceptionObject;
    }
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v5[25] = SystemTimeAsFileTime;
    if ( v4 )
      std::_Ref_count_base::_Decref(v4);
    if ( *((_BYTE *)this + 184) != a2 )
    {
      *((_BYTE *)this + 184) = a2;
      v7 = BrQueryBrokeredEvents2(*((_QWORD *)this + 24), 0, 0, 0xFFFFFFFFLL, &v31, &v33);
      v8 = v7;
      if ( v7 )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v7);
        v24 = 0;
        v25 = 1;
        v23 = &Broker::Win32Error::`vftable';
        v26 = v8;
        throw (Broker::Win32Error *)&v23;
      }
      for ( i = 0; i < v31; ++i )
      {
        SystemTimeAsFileTime = 0;
        BrokeredEventInfo2 = BrGetBrokeredEventInfo2(
                               *((_QWORD *)this + 24),
                               *(_QWORD *)(v33 + 8LL * i),
                               0,
                               0,
                               &SystemTimeAsFileTime);
        v11 = BrokeredEventInfo2;
        if ( BrokeredEventInfo2 )
        {
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              27,
              &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids,
              BrokeredEventInfo2);
          v28 = 0;
          v29 = 1;
          v27 = &Broker::Win32Error::`vftable';
          v30 = v11;
          throw (Broker::Win32Error *)&v27;
        }
        v12 = (__int64 *)SystemTimeAsFileTime;
        v13 = *(_QWORD *)(*(_QWORD *)&SystemTimeAsFileTime + 8LL);
        if ( v13 )
          _InterlockedIncrement((volatile signed __int32 *)(v13 + 8));
        v17 = *v12;
        v18 = (std::_Ref_count_base *)v12[1];
        v14 = v18;
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 24LL))(v17, a2);
        if ( v14 )
          std::_Ref_count_base::_Decref(v14);
      }
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
      Broker::TimeBroker::RegenerateTimerWheels(this);
      if ( v33 )
        BrBufferFree();
    }
    Broker::TimeBroker::BrokerLock::~BrokerLock((Broker::TimeBroker::BrokerLock *)&v32);
  }
}

```

## disassembly

```asm
0x180005400  push    rbx
0x180005402  push    rsi
0x180005403  push    rdi
0x180005404  push    r14
0x180005406  push    r15
0x180005408  sub     rsp, 0F0h
0x18000540f  movzx   r14d, dl
0x180005413  mov     rsi, rcx
0x180005416  mov     rcx, cs:WPP_GLOBAL_Control
0x18000541d  test    dword ptr [rcx+1Ch], 100h
0x180005424  jnz     loc_1800055F7
0x18000542a  cmp     qword ptr [rsi+0C0h], 0
0x180005432  jz      loc_1800054D3
0x180005438  xor     r15d, r15d
0x18000543b  mov     [rsp+118h+arg_0], r15d
0x180005443  mov     [rsp+118h+arg_18], r15
0x18000544b  mov     [rsp+118h+arg_10], r15d
0x180005453  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18000545a  test    rbx, rbx
0x18000545d  jz      short loc_18000546A
0x18000545f  lock inc dword ptr [rbx+8]
0x180005463  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18000546a  mov     rdi, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x180005471  mov     qword ptr [rsp+118h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x180005476  mov     [rsp+118h+var_E0], rbx
0x18000547b  xor     edx, edx
0x18000547d  mov     rcx, [rdi+0C0h]
0x180005484  call    cs:__imp_BrLockBroker
0x18000548a  test    eax, eax
0x18000548c  jnz     loc_18000561E
0x180005492  mov     qword ptr [rsp+118h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180005497  lea     rcx, [rsp+118h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000549c  call    cs:__imp_GetSystemTimeAsFileTime
0x1800054a2  mov     rax, qword ptr [rsp+118h+SystemTimeAsFileTime.dwLowDateTime]
0x1800054a7  mov     [rdi+0C8h], rax
0x1800054ae  test    rbx, rbx
0x1800054b1  jz      short loc_1800054BC
0x1800054b3  mov     rcx, rbx; this
0x1800054b6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800054bb  nop
0x1800054bc  cmp     [rsi+0B8h], r14b
0x1800054c3  jnz     short loc_1800054E2
0x1800054c5  lea     rcx, [rsp+118h+arg_10]; this
0x1800054cd  call    ??1BrokerLock@TimeBroker@Broker@@QEAA@XZ; Broker::TimeBroker::BrokerLock::~BrokerLock(void)
0x1800054d2  nop
0x1800054d3  add     rsp, 0F0h
0x1800054da  pop     r15
0x1800054dc  pop     r14
0x1800054de  pop     rdi
0x1800054df  pop     rsi
0x1800054e0  pop     rbx
0x1800054e1  retn
0x1800054e2  mov     [rsi+0B8h], r14b
0x1800054e9  lea     rax, [rsp+118h+arg_18]
0x1800054f1  mov     [rsp+118h+var_F0], rax
0x1800054f6  lea     rax, [rsp+118h+arg_0]
0x1800054fe  mov     [rsp+118h+var_F8], rax
0x180005503  mov     r9d, 0FFFFFFFFh
0x180005509  xor     r8d, r8d
0x18000550c  xor     edx, edx
0x18000550e  mov     rcx, [rsi+0C0h]
0x180005515  call    cs:__imp_BrQueryBrokeredEvents2
0x18000551b  mov     ebx, eax
0x18000551d  test    eax, eax
0x18000551f  jnz     loc_180005650
0x180005525  mov     ebx, r15d
0x180005528  nop     dword ptr [rax+rax+00000000h]
0x180005530  cmp     ebx, [rsp+118h+arg_0]
0x180005537  jnb     loc_1800055BF
0x18000553d  mov     qword ptr [rsp+118h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180005542  mov     eax, ebx
0x180005544  lea     rcx, [rsp+118h+SystemTimeAsFileTime]
0x180005549  mov     [rsp+118h+var_F8], rcx
0x18000554e  xor     r9d, r9d
0x180005551  xor     r8d, r8d
0x180005554  mov     rdx, [rsp+118h+arg_18]
0x18000555c  mov     rdx, [rdx+rax*8]
0x180005560  mov     rcx, [rsi+0C0h]
0x180005567  call    cs:__imp_BrGetBrokeredEventInfo2
0x18000556d  mov     edi, eax
0x18000556f  test    eax, eax
0x180005571  jnz     loc_1800056B8
0x180005577  mov     rdx, qword ptr [rsp+118h+SystemTimeAsFileTime.dwLowDateTime]
0x18000557c  mov     rax, [rdx+8]
0x180005580  test    rax, rax
0x180005583  jz      short loc_180005589
0x180005585  lock inc dword ptr [rax+8]
0x180005589  mov     rcx, [rdx]
0x18000558c  mov     [rsp+118h+var_D8], rcx
0x180005591  mov     rdi, [rdx+8]
0x180005595  mov     [rsp+118h+var_D0], rdi
0x18000559a  mov     rax, [rcx]
0x18000559d  movzx   edx, r14b
0x1800055a1  mov     rax, [rax+18h]
0x1800055a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055aa  nop
0x1800055ab  test    rdi, rdi
0x1800055ae  jz      short loc_1800055B8
0x1800055b0  mov     rcx, rdi; this
0x1800055b3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800055b8  inc     ebx
0x1800055ba  jmp     loc_180005530
0x1800055bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055c6  test    dword ptr [rcx+1Ch], 100h
0x1800055cd  jnz     loc_180005726
0x1800055d3  mov     rcx, rsi; this
0x1800055d6  call    ?RegenerateTimerWheels@TimeBroker@Broker@@AEAAXXZ; Broker::TimeBroker::RegenerateTimerWheels(void)
0x1800055db  mov     rcx, [rsp+118h+arg_18]
0x1800055e3  test    rcx, rcx
0x1800055e6  jz      loc_1800054C5
0x1800055ec  call    cs:__imp_BrBufferFree
0x1800055f2  jmp     loc_1800054C5
0x1800055f7  cmp     byte ptr [rcx+19h], 4
0x1800055fb  jb      loc_18000542A
0x180005601  mov     r9d, r14d
0x180005604  mov     edx, 19h
0x180005609  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180005610  mov     rcx, [rcx+10h]
0x180005614  call    WPP_SF_d
0x180005619  jmp     loc_18000542A
0x18000561e  xorps   xmm0, xmm0
0x180005621  movups  [rsp+118h+var_C0], xmm0
0x180005626  mov     [rsp+118h+var_B0], 1
0x18000562e  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180005635  mov     [rsp+118h+pExceptionObject], rcx
0x18000563a  mov     [rsp+118h+var_A8], eax
0x18000563e  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180005645  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18000564a  call    _CxxThrowException_0
0x180005650  mov     rcx, cs:WPP_GLOBAL_Control
0x180005657  test    dword ptr [rcx+1Ch], 100h
0x18000565e  jz      short loc_18000567E
0x180005660  cmp     byte ptr [rcx+19h], 2
0x180005664  jb      short loc_18000567E
0x180005666  mov     edx, 1Ah
0x18000566b  mov     r9d, ebx
0x18000566e  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180005675  mov     rcx, [rcx+10h]
0x180005679  call    WPP_SF_d
0x18000567e  xorps   xmm0, xmm0
0x180005681  movups  [rsp+118h+var_98], xmm0
0x180005689  mov     [rsp+118h+var_88], 1
0x180005694  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000569b  mov     [rsp+118h+var_A0], rcx
0x1800056a0  mov     [rsp+118h+var_80], ebx
0x1800056a7  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x1800056ae  lea     rcx, [rsp+118h+var_A0]; pExceptionObject
0x1800056b3  call    _CxxThrowException_0
0x1800056b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056bf  test    dword ptr [rcx+1Ch], 100h
0x1800056c6  jz      short loc_1800056E6
0x1800056c8  cmp     byte ptr [rcx+19h], 2
0x1800056cc  jb      short loc_1800056E6
0x1800056ce  mov     edx, 1Bh
0x1800056d3  mov     r9d, edi
0x1800056d6  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x1800056dd  mov     rcx, [rcx+10h]
0x1800056e1  call    WPP_SF_d
0x1800056e6  xorps   xmm0, xmm0
0x1800056e9  movups  [rsp+118h+var_70], xmm0
0x1800056f1  mov     [rsp+118h+var_60], 1
0x1800056fc  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180005703  mov     [rsp+118h+var_78], rcx
0x18000570b  mov     [rsp+118h+var_58], edi
0x180005712  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180005719  lea     rcx, [rsp+118h+var_78]; pExceptionObject
0x180005721  call    _CxxThrowException_0
0x180005726  cmp     byte ptr [rcx+19h], 4
0x18000572a  jb      loc_1800055D3
0x180005730  mov     edx, 1Ch
0x180005735  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18000573c  mov     rcx, [rcx+10h]
0x180005740  call    WPP_SF_
0x180005745  jmp     loc_1800055D3
0x18000574a  jmp     loc_1800054D3
```
