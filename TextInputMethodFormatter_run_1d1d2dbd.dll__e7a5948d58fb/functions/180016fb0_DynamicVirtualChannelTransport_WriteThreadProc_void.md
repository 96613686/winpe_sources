# DynamicVirtualChannelTransport::WriteThreadProc(void *)

- ea: `0x180016fb0`
- end: `0x1800171c3`
- name: `?WriteThreadProc@DynamicVirtualChannelTransport@@SAKPEAX@Z`
- size: `531`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180002240`
- `0x180008874`
- `0x1800090f0`
- `0x1800132f0`
- `0x18001533c`
- `0x180015ce8`
- `0x180015f38`
- `0x180015fe8`
- `0x1800167f8`
- `0x180016fb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180017076`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180017076`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180017190`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180017190`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017069`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800170ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017069`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800170ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017041`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800170a4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017041`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800170a4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001701b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001701b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001714f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001714f`

## pseudocode

```c
__int64 __fastcall DynamicVirtualChannelTransport::WriteThreadProc(RTL_SRWLOCK *Parameter)
{
  DWORD v2; // edi
  PVOID Ptr; // rdx
  PVOID v4; // rcx
  RTL_SRWLOCK *v5; // rsi
  RTL_SRWLOCK *v6; // rdi
  __int64 i; // rdi
  int v8; // ecx
  int v9; // eax
  signed int LastError; // eax
  BOOL bAlertable; // [rsp+20h] [rbp-50h]
  __int128 v13; // [rsp+30h] [rbp-40h] BYREF
  __int64 v14; // [rsp+40h] [rbp-30h]
  HANDLE Handles[3]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  if ( Parameter )
  {
    Handles[0] = Parameter[15].Ptr;
    Handles[1] = Parameter[17].Ptr;
    Handles[2] = Parameter[16].Ptr;
    SetEvent(Parameter[19].Ptr);
    while ( 1 )
    {
      v2 = WaitForMultipleObjectsEx(3u, Handles, 0, 0xFFFFFFFF, 1);
      if ( !v2 )
        break;
      switch ( v2 )
      {
        case 1u:
          if ( LODWORD(Parameter[21].Ptr) == 2 )
          {
            AcquireSRWLockExclusive(Parameter + 20);
            Ptr = Parameter[13].Ptr;
            v4 = Parameter[12].Ptr;
            if ( v4 != Ptr )
            {
              std::_Destroy_range<std::allocator<std::tuple<enum DynamicVirtualChannelTransport::MarshalledCallType,unsigned int,std::shared_ptr<std::vector<char>>>>>(
                v4,
                Ptr);
              Parameter[13].Ptr = Parameter[12].Ptr;
            }
            if ( Parameter != (RTL_SRWLOCK *)-160LL )
              ReleaseSRWLockExclusive(Parameter + 20);
          }
          ResetEvent(Parameter[17].Ptr);
          break;
        case 2u:
          v13 = 0;
          v14 = 0;
          AcquireSRWLockExclusive(Parameter + 20);
          v5 = Parameter + 12;
          v6 = Parameter + 13;
          if ( &v13 != (__int128 *)&Parameter[12] )
            std::vector<std::tuple<enum DynamicVirtualChannelTransport::MarshalledCallType,unsigned int,std::shared_ptr<std::vector<char>>>>::_Assign_counted_range<std::tuple<enum DynamicVirtualChannelTransport::MarshalledCallType,unsigned int,std::shared_ptr<std::vector<char>>> *>(
              &v13,
              v5->Ptr,
              ((char *)v6->Ptr - (char *)v5->Ptr) >> 5);
          if ( v5->Ptr != v6->Ptr )
          {
            std::_Destroy_range<std::allocator<std::tuple<enum DynamicVirtualChannelTransport::MarshalledCallType,unsigned int,std::shared_ptr<std::vector<char>>>>>(
              v5->Ptr,
              v6->Ptr);
            v6->Ptr = v5->Ptr;
          }
          if ( Parameter != (RTL_SRWLOCK *)-160LL )
            ReleaseSRWLockExclusive(Parameter + 20);
          for ( i = v13; i != *((_QWORD *)&v13 + 1); i += 32 )
          {
            v8 = *(_DWORD *)(i + 24);
            if ( v8 )
            {
              if ( v8 == 1 )
                DynamicVirtualChannelTransport::DoSendData((DynamicVirtualChannelTransport *)Parameter);
            }
            else
            {
              v9 = DynamicVirtualChannelTransport::DoConnectToHost((DynamicVirtualChannelTransport *)Parameter);
              if ( v9 == -2147024663 || v9 == -2147022646 )
                DynamicVirtualChannelTransport::AttemptReconnect((DynamicVirtualChannelTransport *)Parameter);
            }
          }
          std::vector<std::tuple<enum DynamicVirtualChannelTransport::MarshalledCallType,unsigned int,std::shared_ptr<std::vector<char>>>>::~vector<std::tuple<enum DynamicVirtualChannelTransport::MarshalledCallType,unsigned int,std::shared_ptr<std::vector<char>>>>(&v13);
          break;
        case 0xFFFFFFFF:
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x240,
            (unsigned int)"mincore\\textinput\\dev\\virtualization\\DVCTransport\\DynamicVirtualChannelTransport.cpp",
            (const char *)(unsigned int)LastError,
            bAlertable);
          break;
      }
    }
  }
  else
  {
    v2 = 0;
    FailFastWithHR(-2147467261, (unsigned __int64)retaddr, 0x1FBu);
  }
  return v2;
}

```

## disassembly

```asm
0x180016fb0  mov     [rsp-18h+arg_8], rbx
0x180016fb5  mov     [rsp-18h+arg_10], rsi
0x180016fba  push    rbp
0x180016fbb  push    rdi
0x180016fbc  push    r14
0x180016fbe  mov     rbp, rsp
0x180016fc1  sub     rsp, 70h
0x180016fc5  mov     rax, cs:__security_cookie
0x180016fcc  xor     rax, rsp
0x180016fcf  mov     [rbp+var_10], rax
0x180016fd3  mov     rbx, rcx
0x180016fd6  test    rcx, rcx
0x180016fd9  jnz     short loc_180016FF6
0x180016fdb  xor     edi, edi
0x180016fdd  mov     rdx, [rbp+18h]; unsigned __int64
0x180016fe1  mov     ecx, 80004003h; int
0x180016fe6  mov     r8d, 1FBh; unsigned __int64
0x180016fec  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x180016ff1  jmp     loc_1800171A0
0x180016ff6  mov     rax, [rcx+78h]
0x180016ffa  mov     [rbp+Handles], rax
0x180016ffe  mov     rax, [rcx+88h]
0x180017005  mov     [rbp+var_20], rax
0x180017009  mov     rax, [rcx+80h]
0x180017010  mov     [rbp+var_18], rax
0x180017014  mov     rcx, [rcx+98h]; hEvent
0x18001701b  call    cs:__imp_SetEvent
0x180017021  jmp     loc_180017179
0x180017026  cmp     edi, 1
0x180017029  jnz     short loc_180017081
0x18001702b  mov     eax, [rbx+0A8h]
0x180017031  nop
0x180017032  cmp     eax, 2
0x180017035  jnz     short loc_18001706F
0x180017037  lea     rdi, [rbx+0A0h]
0x18001703e  mov     rcx, rdi; SRWLock
0x180017041  call    cs:__imp_AcquireSRWLockExclusive
0x180017047  mov     rdx, [rbx+68h]
0x18001704b  mov     rcx, [rbx+60h]
0x18001704f  cmp     rcx, rdx
0x180017052  jz      short loc_180017061
0x180017054  call    ??$_Destroy_range@V?$allocator@V?$tuple@W4MarshalledCallType@DynamicVirtualChannelTransport@@IV?$shared_ptr@V?$vector@DV?$allocator@D@std@@@std@@@std@@@std@@@std@@@std@@YAXPEAV?$tuple@W4MarshalledCallType@DynamicVirtualChannelTransport@@IV?$shared_ptr@V?$vector@DV?$allocator@D@std@@@std@@@std@@@0@QEAV10@AEAV?$allocator@V?$tuple@W4MarshalledCallType@DynamicVirtualChannelTransport@@IV?$shared_ptr@V?$vector@DV?$allocator@D@std@@@std@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::tuple<DynamicVirtualChannelTransport::MarshalledCallType,uint,std::shared_ptr<std::vector<char>>>>>(std::tuple<DynamicVirtualChannelTransport::MarshalledCallType,uint,std::shared_ptr<std::vector<char>>> *,std::tuple<DynamicVirtualChannelTransport::MarshalledCallType,uint,std::shared_ptr<std::vector<char>>> * const,std::allocator<std::tuple<DynamicVirtualChannelTransport::MarshalledCallType,uint,std::shared_ptr<std::vector<char>>>> &)
0x180017059  mov     rax, [rbx+60h]
0x18001705d  mov     [rbx+68h], rax
0x180017061  test    rdi, rdi
0x180017064  jz      short loc_18001706F
0x180017066  mov     rcx, rdi; SRWLock
0x180017069  call    cs:__imp_ReleaseSRWLockExclusive
0x18001706f  mov     rcx, [rbx+88h]; hEvent
0x180017076  call    cs:__imp_ResetEvent
0x18001707c  jmp     loc_180017179
0x180017081  cmp     edi, 2
0x180017084  jnz     loc_18001714A
0x18001708a  xorps   xmm0, xmm0
0x18001708d  movdqu  [rbp+var_40], xmm0
0x180017092  mov     [rbp+var_30], 0
0x18001709a  lea     r14, [rbx+0A0h]
0x1800170a1  mov     rcx, r14; SRWLock
0x1800170a4  call    cs:__imp_AcquireSRWLockExclusive
0x1800170aa  lea     rsi, [rbx+60h]
0x1800170ae  lea     rdi, [rsi+8]
0x1800170b2  lea     rax, [rbp+var_40]
0x1800170b6  cmp     rax, rsi
0x1800170b9  jz      short loc_1800170D1
0x1800170bb  mov     r8, [rdi]
0x1800170be  sub     r8, [rsi]
0x1800170c1  sar     r8, 5
0x1800170c5  mov     rdx, [rsi]
0x1800170c8  lea     rcx, [rbp+var_40]
0x1800170cc  call    ??$_Assign_counted_range@PEAV?$tuple@W4MarshalledCallType@DynamicVirtualChannelTransport@@IV?$shared_ptr@V?$vector@DV?$allocator@D@std@@@std@@@std@@@std@@@?$vector@V?$tuple@W4MarshalledCallType@DynamicVirtualChannelTransport@@IV?$shared_ptr@V?$vector@DV?$allocator@D@std@@@std@@@std@@@std@@V?$allocator@V?$tuple@W4MarshalledCallType@DynamicVirtualChannelTransport@@IV?$shared_ptr@V?$vector@DV?$allocator@D@std@@@std@@@std@@@std@@@2@@std@@AEAAXPEAV?$tuple@W4MarshalledCallType@DynamicVirtualChannelTransport@@IV?$shared_ptr@V?$vector@DV?$allocator@D@std@@@std@@@std@@@1@_K@Z; std::vector<std::tuple<DynamicVirtualChannelTransport::MarshalledCallType,uint,std::shared_ptr<std::vector<char>>>>::_Assign_counted_range<std::tuple<DynamicVirtualChannelTransport::MarshalledCallType,uint,std::shared_ptr<std::vector<char>>> *>(std::tuple<DynamicVirtualChannelTransport::MarshalledCallType,uint,std::shared_ptr<std::vector<char>>> *,unsigned __int64)
0x1800170d1  mov     rcx, [rsi]
0x1800170d4  cmp     rcx, [rdi]
0x1800170d7  jz      short loc_1800170E7
0x1800170d9  mov     rdx, [rdi]
0x1800170dc  call    ??$_Destroy_range@V?$allocator@V?$tuple@W4MarshalledCallType@DynamicVirtualChannelTransport@@IV?$shared_ptr@V?$vector@DV?$allocator@D@std@@@std@@@std@@@std@@@std@@@std@@YAXPEAV?$tuple@W4MarshalledCallType@DynamicVirtualChannelTransport@@IV?$shared_ptr@V?$vector@DV?$allocator@D@std@@@std@@@std@@@0@QEAV10@AEAV?$allocator@V?$tuple@W4MarshalledCallType@DynamicVirtualChannelTransport@@IV?$shared_ptr@V?$vector@DV?$allocator@D@std@@@std@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::tuple<DynamicVirtualChannelTransport::MarshalledCallType,uint,std::shared_ptr<std::vector<char>>>>>(std::tuple<DynamicVirtualChannelTransport::MarshalledCallType,uint,std::shared_ptr<std::vector<char>>> *,std::tuple<DynamicVirtualChannelTransport::MarshalledCallType,uint,std::shared_ptr<std::vector<char>>> * const,std::allocator<std::tuple<DynamicVirtualChannelTransport::MarshalledCallType,uint,std::shared_ptr<std::vector<char>>>> &)
0x1800170e1  mov     rax, [rsi]
0x1800170e4  mov     [rdi], rax
0x1800170e7  test    r14, r14
0x1800170ea  jz      short loc_1800170F5
0x1800170ec  mov     rcx, r14; SRWLock
0x1800170ef  call    cs:__imp_ReleaseSRWLockExclusive
0x1800170f5  mov     rdi, qword ptr [rbp+var_40]
0x1800170f9  jmp     short loc_180017139
0x1800170fb  mov     ecx, [rdi+18h]
0x1800170fe  test    ecx, ecx
0x180017100  jz      short loc_180017117
0x180017102  cmp     ecx, 1
0x180017105  jnz     short loc_180017135
0x180017107  mov     r8, [rdi]
0x18001710a  mov     edx, [rdi+10h]
0x18001710d  mov     rcx, rbx; this
0x180017110  call    ?DoSendData@DynamicVirtualChannelTransport@@IEAAJIAEAV?$vector@DV?$allocator@D@std@@@std@@@Z; DynamicVirtualChannelTransport::DoSendData(uint,std::vector<char> &)
0x180017115  jmp     short loc_180017135
0x180017117  mov     rcx, rbx; this
0x18001711a  call    ?DoConnectToHost@DynamicVirtualChannelTransport@@IEAAJXZ; DynamicVirtualChannelTransport::DoConnectToHost(void)
0x18001711f  cmp     eax, 800700E9h
0x180017124  jz      short loc_18001712D
0x180017126  cmp     eax, 800708CAh
0x18001712b  jnz     short loc_180017135
0x18001712d  mov     rcx, rbx; this
0x180017130  call    ?AttemptReconnect@DynamicVirtualChannelTransport@@IEAAJXZ; DynamicVirtualChannelTransport::AttemptReconnect(void)
0x180017135  add     rdi, 20h ; ' '
0x180017139  cmp     rdi, qword ptr [rbp+var_40+8]
0x18001713d  jnz     short loc_1800170FB
0x18001713f  lea     rcx, [rbp+var_40]
0x180017143  call    ??1?$vector@V?$tuple@W4MarshalledCallType@DynamicVirtualChannelTransport@@IV?$shared_ptr@V?$vector@DV?$allocator@D@std@@@std@@@std@@@std@@V?$allocator@V?$tuple@W4MarshalledCallType@DynamicVirtualChannelTransport@@IV?$shared_ptr@V?$vector@DV?$allocator@D@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::tuple<DynamicVirtualChannelTransport::MarshalledCallType,uint,std::shared_ptr<std::vector<char>>>>::~vector<std::tuple<DynamicVirtualChannelTransport::MarshalledCallType,uint,std::shared_ptr<std::vector<char>>>>(void)
0x180017148  jmp     short loc_180017179
0x18001714a  cmp     edi, 0FFFFFFFFh
0x18001714d  jnz     short loc_180017179
0x18001714f  call    cs:__imp_GetLastError
0x180017155  test    eax, eax
0x180017157  jle     short loc_180017161
0x180017159  movzx   eax, ax
0x18001715c  or      eax, 80070000h
0x180017161  mov     rcx, [rbp+18h]; this
0x180017165  mov     r9d, eax; char *
0x180017168  lea     r8, aMincoreTextinp_6; "mincore\\textinput\\dev\\virtualization"...
0x18001716f  mov     edx, 240h; void *
0x180017174  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180017179  mov     [rsp+70h+bAlertable], 1; int
0x180017181  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180017185  xor     r8d, r8d; bWaitAll
0x180017188  lea     rdx, [rbp+Handles]; lpHandles
0x18001718c  lea     ecx, [r8+3]; nCount
0x180017190  call    cs:__imp_WaitForMultipleObjectsEx
0x180017196  test    eax, eax
0x180017198  mov     edi, eax
0x18001719a  jnz     loc_180017026
0x1800171a0  mov     eax, edi
0x1800171a2  mov     rcx, [rbp+var_10]
0x1800171a6  xor     rcx, rsp; StackCookie
0x1800171a9  call    __security_check_cookie
0x1800171ae  lea     r11, [rsp+70h+var_s0]
0x1800171b3  mov     rbx, [r11+28h]
0x1800171b7  mov     rsi, [r11+30h]
0x1800171bb  mov     rsp, r11
0x1800171be  pop     r14
0x1800171c0  pop     rdi
0x1800171c1  pop     rbp
0x1800171c2  retn
```
