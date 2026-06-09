# Broker::TimeBroker::OnSystemTimeChange(__int64)

- ea: `0x180005760`
- end: `0x180005b01`
- name: `?OnSystemTimeChange@TimeBroker@Broker@@QEAAX_J@Z`
- size: `929`
- prototype: `void __fastcall(Broker::TimeBroker *__hidden this, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e820`

## callees

- `0x180003800`
- `0x180003840`
- `0x180005760`
- `0x180005b30`
- `0x180005b90`
- `0x180005d10`
- `0x180009fc0`
- `0x180013978`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x18000593d`
- `ntdll!RtlPublishWnfStateData` at `0x18000593d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800057fc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800057fc`
- `BrokerLib!BrLockBroker` at `0x1800057e4`
- `BrokerLib!BrLockBroker` at `0x1800057e4`
- `BrokerLib!BrBufferFree` at `0x1800059a9`
- `BrokerLib!BrBufferFree` at `0x1800059a9`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180005897`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180005897`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x180005848`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x180005848`

## pseudocode

```c
void __fastcall Broker::TimeBroker::OnSystemTimeChange(Broker::TimeBroker *this, __int64 a2)
{
  std::_Ref_count_base *v3; // rbx
  struct _FILETIME *v4; // rdi
  int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // ebx
  unsigned int i; // ebx
  unsigned int BrokeredEventInfo2; // eax
  unsigned int v10; // edi
  __int64 *v11; // rdx
  __int64 v12; // rax
  std::_Ref_count_base *v13; // rdi
  int v14; // eax
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
  __int64 v32; // [rsp+128h] [rbp+10h] BYREF
  int v33; // [rsp+130h] [rbp+18h] BYREF
  __int64 v34; // [rsp+138h] [rbp+20h] BYREF

  v32 = a2;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, a2);
  if ( *((_QWORD *)this + 24) )
  {
    v31 = 0;
    v34 = 0;
    v33 = 0;
    v3 = *(&Broker::TimeBroker::Instance + 1);
    if ( *(&Broker::TimeBroker::Instance + 1) )
    {
      _InterlockedIncrement((volatile signed __int32 *)*(&Broker::TimeBroker::Instance + 1) + 2);
      v3 = *(&Broker::TimeBroker::Instance + 1);
    }
    v4 = (struct _FILETIME *)Broker::TimeBroker::Instance;
    SystemTimeAsFileTime = (struct _FILETIME)Broker::TimeBroker::Instance;
    v16 = v3;
    v5 = BrLockBroker(*((_QWORD *)Broker::TimeBroker::Instance + 24));
    if ( v5 )
    {
      v20 = 0;
      v21 = 1;
      pExceptionObject = &Broker::Win32Error::`vftable';
      v22 = v5;
      throw (Broker::Win32Error *)&pExceptionObject;
    }
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v4[25] = SystemTimeAsFileTime;
    if ( v3 )
      std::_Ref_count_base::_Decref(v3);
    v6 = BrQueryBrokeredEvents2(*((_QWORD *)this + 24), 0, 0, 0xFFFFFFFFLL, &v31, &v34);
    v7 = v6;
    if ( v6 )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v6);
      v24 = 0;
      v25 = 1;
      v23 = &Broker::Win32Error::`vftable';
      v26 = v7;
      throw (Broker::Win32Error *)&v23;
    }
    for ( i = 0; i < v31; ++i )
    {
      SystemTimeAsFileTime = 0;
      BrokeredEventInfo2 = BrGetBrokeredEventInfo2(
                             *((_QWORD *)this + 24),
                             *(_QWORD *)(v34 + 8LL * i),
                             0,
                             0,
                             &SystemTimeAsFileTime);
      v10 = BrokeredEventInfo2;
      if ( BrokeredEventInfo2 )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            32,
            &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids,
            BrokeredEventInfo2);
        v28 = 0;
        v29 = 1;
        v27 = &Broker::Win32Error::`vftable';
        v30 = v10;
        throw (Broker::Win32Error *)&v27;
      }
      v11 = (__int64 *)SystemTimeAsFileTime;
      v12 = *(_QWORD *)(*(_QWORD *)&SystemTimeAsFileTime + 8LL);
      if ( v12 )
        _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
      v17 = *v11;
      v18 = (std::_Ref_count_base *)v11[1];
      v13 = v18;
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v17 + 32LL))(v17, v32, *((_QWORD *)this + 25));
      if ( v13 )
        std::_Ref_count_base::_Decref(v13);
    }
    Broker::TimeBroker::RegenerateTimerWheels(this);
    if ( v34 )
      BrBufferFree();
    Broker::TimeBroker::BrokerLock::~BrokerLock((Broker::TimeBroker::BrokerLock *)&v33);
  }
  v14 = RtlPublishWnfStateData(WNF_TB_SYSTEM_TIME_CHANGED, 0, &v32, 8, 0);
  if ( v14 < 0 )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids,
        (unsigned int)v14);
  }
  else if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
  }
}

```

## disassembly

```asm
0x180005760  mov     [rsp+arg_8], rdx
0x180005765  push    rbx
0x180005766  push    rsi
0x180005767  push    rdi
0x180005768  push    r14
0x18000576a  sub     rsp, 0F8h
0x180005771  mov     r9, rdx
0x180005774  mov     rsi, rcx
0x180005777  mov     rcx, cs:WPP_GLOBAL_Control
0x18000577e  test    dword ptr [rcx+1Ch], 100h
0x180005785  jnz     loc_180005968
0x18000578b  xor     r14d, r14d
0x18000578e  cmp     [rsi+0C0h], r14
0x180005795  jz      loc_180005921
0x18000579b  mov     [rsp+118h+arg_0], r14d
0x1800057a3  mov     [rsp+118h+arg_18], r14
0x1800057ab  mov     [rsp+118h+arg_10], r14d
0x1800057b3  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x1800057ba  test    rbx, rbx
0x1800057bd  jz      short loc_1800057CA
0x1800057bf  lock inc dword ptr [rbx+8]
0x1800057c3  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x1800057ca  mov     rdi, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x1800057d1  mov     qword ptr [rsp+118h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x1800057d6  mov     [rsp+118h+var_E0], rbx
0x1800057db  xor     edx, edx
0x1800057dd  mov     rcx, [rdi+0C0h]
0x1800057e4  call    cs:__imp_BrLockBroker
0x1800057ea  test    eax, eax
0x1800057ec  jnz     loc_1800059B5
0x1800057f2  mov     qword ptr [rsp+118h+SystemTimeAsFileTime.dwLowDateTime], r14
0x1800057f7  lea     rcx, [rsp+118h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800057fc  call    cs:__imp_GetSystemTimeAsFileTime
0x180005802  mov     rax, qword ptr [rsp+118h+SystemTimeAsFileTime.dwLowDateTime]
0x180005807  mov     [rdi+0C8h], rax
0x18000580e  test    rbx, rbx
0x180005811  jz      short loc_18000581C
0x180005813  mov     rcx, rbx; this
0x180005816  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000581b  nop
0x18000581c  lea     rax, [rsp+118h+arg_18]
0x180005824  mov     [rsp+118h+var_F0], rax
0x180005829  lea     rax, [rsp+118h+arg_0]
0x180005831  mov     [rsp+118h+var_F8], rax
0x180005836  mov     r9d, 0FFFFFFFFh
0x18000583c  xor     r8d, r8d
0x18000583f  xor     edx, edx
0x180005841  mov     rcx, [rsi+0C0h]
0x180005848  call    cs:__imp_BrQueryBrokeredEvents2
0x18000584e  mov     ebx, eax
0x180005850  test    eax, eax
0x180005852  jnz     loc_1800059E7
0x180005858  mov     ebx, r14d
0x18000585b  nop     dword ptr [rax+rax+00h]
0x180005860  cmp     ebx, [rsp+118h+arg_0]
0x180005867  jnb     loc_1800058FA
0x18000586d  mov     qword ptr [rsp+118h+SystemTimeAsFileTime.dwLowDateTime], r14
0x180005872  mov     eax, ebx
0x180005874  lea     rcx, [rsp+118h+SystemTimeAsFileTime]
0x180005879  mov     [rsp+118h+var_F8], rcx
0x18000587e  xor     r9d, r9d
0x180005881  xor     r8d, r8d
0x180005884  mov     rdx, [rsp+118h+arg_18]
0x18000588c  mov     rdx, [rdx+rax*8]
0x180005890  mov     rcx, [rsi+0C0h]
0x180005897  call    cs:__imp_BrGetBrokeredEventInfo2
0x18000589d  mov     edi, eax
0x18000589f  test    eax, eax
0x1800058a1  jnz     loc_180005A4F
0x1800058a7  mov     rdx, qword ptr [rsp+118h+SystemTimeAsFileTime.dwLowDateTime]
0x1800058ac  mov     rax, [rdx+8]
0x1800058b0  test    rax, rax
0x1800058b3  jz      short loc_1800058B9
0x1800058b5  lock inc dword ptr [rax+8]
0x1800058b9  mov     rcx, [rdx]
0x1800058bc  mov     [rsp+118h+var_D8], rcx
0x1800058c1  mov     rdi, [rdx+8]
0x1800058c5  mov     [rsp+118h+var_D0], rdi
0x1800058ca  mov     rax, [rcx]
0x1800058cd  mov     r8, [rsi+0C8h]
0x1800058d4  mov     rdx, [rsp+118h+arg_8]
0x1800058dc  mov     rax, [rax+20h]
0x1800058e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058e5  nop
0x1800058e6  test    rdi, rdi
0x1800058e9  jz      short loc_1800058F3
0x1800058eb  mov     rcx, rdi; this
0x1800058ee  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800058f3  inc     ebx
0x1800058f5  jmp     loc_180005860
0x1800058fa  mov     rcx, rsi; this
0x1800058fd  call    ?RegenerateTimerWheels@TimeBroker@Broker@@AEAAXXZ; Broker::TimeBroker::RegenerateTimerWheels(void)
0x180005902  mov     rcx, [rsp+118h+arg_18]
0x18000590a  test    rcx, rcx
0x18000590d  jnz     loc_1800059A9
0x180005913  lea     rcx, [rsp+118h+arg_10]; this
0x18000591b  call    ??1BrokerLock@TimeBroker@Broker@@QEAA@XZ; Broker::TimeBroker::BrokerLock::~BrokerLock(void)
0x180005920  nop
0x180005921  mov     [rsp+118h+var_F8], r14
0x180005926  mov     r9d, 8
0x18000592c  lea     r8, [rsp+118h+arg_8]
0x180005934  xor     edx, edx
0x180005936  mov     rcx, cs:WNF_TB_SYSTEM_TIME_CHANGED
0x18000593d  call    cs:__imp_RtlPublishWnfStateData
0x180005943  test    eax, eax
0x180005945  js      loc_180005AC6
0x18000594b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005952  test    dword ptr [rcx+1Ch], 100h
0x180005959  jnz     short loc_18000598C
0x18000595b  add     rsp, 0F8h
0x180005962  pop     r14
0x180005964  pop     rdi
0x180005965  pop     rsi
0x180005966  pop     rbx
0x180005967  retn
0x180005968  cmp     byte ptr [rcx+19h], 4
0x18000596c  jb      loc_18000578B
0x180005972  mov     edx, 1Eh
0x180005977  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18000597e  mov     rcx, [rcx+10h]
0x180005982  call    WPP_SF_i
0x180005987  jmp     loc_18000578B
0x18000598c  cmp     byte ptr [rcx+19h], 4
0x180005990  jb      short loc_18000595B
0x180005992  mov     edx, 23h ; '#'
0x180005997  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18000599e  mov     rcx, [rcx+10h]
0x1800059a2  call    WPP_SF_
0x1800059a7  jmp     short loc_18000595B
0x1800059a9  call    cs:__imp_BrBufferFree
0x1800059af  nop
0x1800059b0  jmp     loc_180005913
0x1800059b5  xorps   xmm0, xmm0
0x1800059b8  movups  [rsp+118h+var_C0], xmm0
0x1800059bd  mov     [rsp+118h+var_B0], 1
0x1800059c5  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x1800059cc  mov     [rsp+118h+pExceptionObject], rcx
0x1800059d1  mov     [rsp+118h+var_A8], eax
0x1800059d5  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x1800059dc  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x1800059e1  call    _CxxThrowException_0
0x1800059e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059ee  test    dword ptr [rcx+1Ch], 100h
0x1800059f5  jz      short loc_180005A15
0x1800059f7  cmp     byte ptr [rcx+19h], 2
0x1800059fb  jb      short loc_180005A15
0x1800059fd  mov     edx, 1Fh
0x180005a02  mov     r9d, ebx
0x180005a05  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180005a0c  mov     rcx, [rcx+10h]
0x180005a10  call    WPP_SF_d
0x180005a15  xorps   xmm0, xmm0
0x180005a18  movups  [rsp+118h+var_98], xmm0
0x180005a20  mov     [rsp+118h+var_88], 1
0x180005a2b  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180005a32  mov     [rsp+118h+var_A0], rcx
0x180005a37  mov     [rsp+118h+var_80], ebx
0x180005a3e  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180005a45  lea     rcx, [rsp+118h+var_A0]; pExceptionObject
0x180005a4a  call    _CxxThrowException_0
0x180005a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a56  test    dword ptr [rcx+1Ch], 100h
0x180005a5d  jz      short loc_180005A7D
0x180005a5f  cmp     byte ptr [rcx+19h], 2
0x180005a63  jb      short loc_180005A7D
0x180005a65  mov     edx, 20h ; ' '
0x180005a6a  mov     r9d, edi
0x180005a6d  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180005a74  mov     rcx, [rcx+10h]
0x180005a78  call    WPP_SF_d
0x180005a7d  xorps   xmm0, xmm0
0x180005a80  movups  [rsp+118h+var_70], xmm0
0x180005a88  mov     [rsp+118h+var_60], 1
0x180005a93  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180005a9a  mov     [rsp+118h+var_78], rcx
0x180005aa2  mov     [rsp+118h+var_58], edi
0x180005aa9  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180005ab0  lea     rcx, [rsp+118h+var_78]; pExceptionObject
0x180005ab8  call    _CxxThrowException_0
0x180005abe  xor     r14d, r14d
0x180005ac1  jmp     loc_180005921
0x180005ac6  mov     rcx, cs:WPP_GLOBAL_Control
0x180005acd  test    dword ptr [rcx+1Ch], 100h
0x180005ad4  jz      loc_18000595B
0x180005ada  cmp     byte ptr [rcx+19h], 2
0x180005ade  jb      loc_18000595B
0x180005ae4  mov     edx, 22h ; '"'
0x180005ae9  mov     r9d, eax
0x180005aec  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180005af3  mov     rcx, [rcx+10h]
0x180005af7  call    WPP_SF_d
0x180005afc  jmp     loc_18000595B
```
