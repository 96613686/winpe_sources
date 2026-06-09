# ConnectionPointContainer::Notify(std::function<void (Microsoft::WRL::ComPtr<IUIRadioManagerNotifySink> const &)> const &)

- ea: `0x180002c10`
- end: `0x180002eac`
- name: `?Notify@ConnectionPointContainer@@QEAAJAEBV?$function@$$A6AXAEBV?$ComPtr@UIUIRadioManagerNotifySink@@@WRL@Microsoft@@@Z@std@@@Z`
- size: `668`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001f350`

## callees

- `0x180002c10`
- `0x180002ec0`
- `0x18000d2a0`
- `0x180017ff0`
- `0x180018094`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ea1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ea1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002db4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002db4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180002e3a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180002e3a`

## pseudocode

```c
__int64 __fastcall ConnectionPointContainer::Notify(LPCRITICAL_SECTION lpCriticalSection, __int64 a2)
{
  __int64 v2; // rbx
  LPCRITICAL_SECTION v3; // rdi
  unsigned int **v4; // rsi
  unsigned int **OwningThread; // r14
  __int64 v6; // rcx
  unsigned int *v8; // r13
  __int64 (__fastcall ***v9)(_QWORD, _BYTE *); // rcx
  _BYTE *v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // [rsp+28h] [rbp-C0h]
  struct _RTL_CRITICAL_SECTION *v13; // [rsp+30h] [rbp-B8h]
  unsigned int **v15; // [rsp+38h] [rbp-B0h]
  __int64 v19; // [rsp+50h] [rbp-98h] BYREF
  _BYTE v20[56]; // [rsp+58h] [rbp-90h] BYREF
  _BYTE *v21; // [rsp+90h] [rbp-58h]
  _QWORD *v22; // [rsp+A0h] [rbp-48h]
  __int64 v23; // [rsp+A8h] [rbp-40h] BYREF

  v2 = a2;
  v12 = a2;
  v3 = lpCriticalSection;
  EnterCriticalSection(lpCriticalSection);
  v13 = v3;
  v4 = *(unsigned int ***)&v3[1].LockCount;
  OwningThread = (unsigned int **)v3[1].OwningThread;
  v15 = OwningThread;
  while ( 2 )
  {
    if ( v4 != OwningThread )
    {
      v23 = 0;
      if ( (***((int (__fastcall ****)(_QWORD, GUID *, __int64 *))*v4 + 1))(
             *((_QWORD *)*v4 + 1),
             &GUID_b453e674_f489_41c5_9955_983c9fc264b2,
             &v23) < 0 )
        goto LABEL_4;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_2ce43deefc5a38284e7a25a8a4237130_Traceguids, **v4);
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        v8 = *v4;
        v19 = v23;
        if ( v23 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
        v21 = 0;
        v9 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(v2 + 56);
        if ( v9 )
          v21 = (_BYTE *)(**v9)(v9, v20);
        EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 6));
        v22 = v8 + 6;
        if ( *((_BYTE *)v8 + 288) )
        {
          if ( v8 != (unsigned int *)-24LL )
            LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 6));
        }
        else
        {
          if ( v8[4] == 1 )
            std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__ConnectionPointContainer::Notify_::_10_::_lambda_1___(
              v8 + 42,
              &v19);
          else
            std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__ConnectionPointContainer::Notify_::_10_::_lambda_1___(
              v8 + 62,
              &v19);
          if ( v8 != (unsigned int *)-24LL )
            LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 6));
          _InterlockedIncrement64((volatile signed __int64 *)v8 + 19);
          SubmitThreadpoolWork(*((PTP_WORK *)v8 + 18));
        }
        if ( v21 )
        {
          v10 = v20;
          LOBYTE(v10) = v21 != v20;
          (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v21 + 32LL))(v21, v10);
          v21 = 0;
        }
        v11 = v19;
        if ( v19 )
        {
          v19 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', 0) )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_2ce43deefc5a38284e7a25a8a4237130_Traceguids, **v4);
          v3 = v13;
          OwningThread = v15;
          v2 = a2;
          v12 = a2;
          __eh34_try_continuation(0, &std::exception `RTTI Type Descriptor', &loc_180002E76);
LABEL_4:
          v6 = v23;
          if ( v23 )
          {
            v23 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
          }
          v4 += 2;
          continue;
        }
      }
      v2 = v12;
      goto LABEL_4;
    }
    break;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, WPP_2ce43deefc5a38284e7a25a8a4237130_Traceguids, 0);
  if ( v3 )
    LeaveCriticalSection(v3);
  return 0;
}

```

## disassembly

```asm
0x180002c10  mov     [rsp+arg_10], rbx
0x180002c15  mov     [rsp+arg_18], rsi
0x180002c1a  push    rdi
0x180002c1b  push    r12
0x180002c1d  push    r13
0x180002c1f  push    r14
0x180002c21  push    r15
0x180002c23  sub     rsp, 0C0h
0x180002c2a  mov     rax, cs:__security_cookie
0x180002c31  xor     rax, rsp
0x180002c34  mov     [rsp+0E8h+var_38], rax
0x180002c3c  mov     rbx, rdx
0x180002c3f  mov     [rsp+0E8h+var_C0], rdx
0x180002c44  mov     rdi, rcx
0x180002c47  mov     [rsp+0E8h+var_A8], rdx
0x180002c4c  call    cs:__imp_EnterCriticalSection
0x180002c52  mov     [rsp+0E8h+var_B8], rdi
0x180002c57  mov     rsi, [rdi+30h]
0x180002c5b  mov     r14, [rdi+38h]
0x180002c5f  mov     [rsp+0E8h+var_B0], r14
0x180002c64  xor     r15d, r15d
0x180002c67  lea     r12, WPP_GLOBAL_Control
0x180002c6e  mov     [rsp+0E8h+var_C8], rsi
0x180002c73  cmp     rsi, r14
0x180002c76  jz      short loc_180002CD2
0x180002c78  mov     [rsp+0E8h+var_40], r15
0x180002c80  mov     rax, [rsi]
0x180002c83  mov     rcx, [rax+8]
0x180002c87  mov     rax, [rcx]
0x180002c8a  lea     r8, [rsp+0E8h+var_40]
0x180002c92  lea     rdx, _GUID_b453e674_f489_41c5_9955_983c9fc264b2
0x180002c99  mov     rax, [rax]
0x180002c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ca1  nop
0x180002ca2  test    eax, eax
0x180002ca4  jns     loc_180002D35
0x180002caa  mov     rcx, [rsp+0E8h+var_40]
0x180002cb2  test    rcx, rcx
0x180002cb5  jz      short loc_180002CCC
0x180002cb7  mov     [rsp+0E8h+var_40], r15
0x180002cbf  mov     rax, [rcx]
0x180002cc2  mov     rax, [rax+10h]
0x180002cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ccb  nop
0x180002ccc  add     rsi, 10h
0x180002cd0  jmp     short loc_180002C6E
0x180002cd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cd9  cmp     rcx, r12
0x180002cdc  jz      short loc_180002CFD
0x180002cde  test    byte ptr [rcx+1Ch], 4
0x180002ce2  jz      short loc_180002CFD
0x180002ce4  mov     edx, 12h
0x180002ce9  xor     r9d, r9d
0x180002cec  lea     r8, WPP_2ce43deefc5a38284e7a25a8a4237130_Traceguids
0x180002cf3  mov     rcx, [rcx+10h]
0x180002cf7  call    WPP_SF_d
0x180002cfc  nop
0x180002cfd  test    rdi, rdi
0x180002d00  jnz     loc_180002E9E
0x180002d06  xor     eax, eax
0x180002d08  mov     rcx, [rsp+0E8h+var_38]
0x180002d10  xor     rcx, rsp; StackCookie
0x180002d13  call    __security_check_cookie
0x180002d18  lea     r11, [rsp+0E8h+var_28]
0x180002d20  mov     rbx, [r11+40h]
0x180002d24  mov     rsi, [r11+48h]
0x180002d28  mov     rsp, r11
0x180002d2b  pop     r15
0x180002d2d  pop     r14
0x180002d2f  pop     r13
0x180002d31  pop     r12
0x180002d33  pop     rdi
0x180002d34  retn
0x180002d35  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d3c  cmp     rcx, r12
0x180002d3f  jz      short loc_180002D62
0x180002d41  test    byte ptr [rcx+1Ch], 4
0x180002d45  jz      short loc_180002D62
0x180002d47  mov     r9, [rsi]
0x180002d4a  mov     edx, 10h
0x180002d4f  mov     r9d, [r9]
0x180002d52  lea     r8, WPP_2ce43deefc5a38284e7a25a8a4237130_Traceguids
0x180002d59  mov     rcx, [rcx+10h]
0x180002d5d  call    WPP_SF_d
0x180002d62  mov     r13, [rsi]
0x180002d65  mov     rcx, [rsp+0E8h+var_40]
0x180002d6d  mov     [rsp+0E8h+var_98], rcx
0x180002d72  test    rcx, rcx
0x180002d75  jz      short loc_180002D84
0x180002d77  mov     rax, [rcx]
0x180002d7a  mov     rax, [rax+8]
0x180002d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d83  nop
0x180002d84  mov     [rsp+0E8h+var_58], r15
0x180002d8c  mov     rcx, [rbx+38h]
0x180002d90  test    rcx, rcx
0x180002d93  jz      short loc_180002DAD
0x180002d95  mov     rax, [rcx]
0x180002d98  lea     rdx, [rsp+0E8h+var_90]
0x180002d9d  mov     rax, [rax]
0x180002da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002da5  mov     [rsp+0E8h+var_58], rax
0x180002dad  lea     rbx, [r13+18h]
0x180002db1  mov     rcx, rbx; lpCriticalSection
0x180002db4  call    cs:__imp_EnterCriticalSection
0x180002dba  mov     [rsp+0E8h+var_48], rbx
0x180002dc2  lea     rcx, [r13+0A8h]
0x180002dc9  cmp     byte ptr [rcx+78h], 0
0x180002dcd  jz      short loc_180002E4D
0x180002dcf  test    rbx, rbx
0x180002dd2  jnz     short loc_180002E42
0x180002dd4  mov     rcx, [rsp+0E8h+var_58]
0x180002ddc  test    rcx, rcx
0x180002ddf  jz      short loc_180002E00
0x180002de1  mov     rax, [rcx]
0x180002de4  lea     rdx, [rsp+0E8h+var_90]
0x180002de9  cmp     rcx, rdx
0x180002dec  setnz   dl
0x180002def  mov     rax, [rax+20h]
0x180002df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002df8  mov     [rsp+0E8h+var_58], r15
0x180002e00  mov     rcx, [rsp+0E8h+var_98]
0x180002e05  test    rcx, rcx
0x180002e08  jz      short loc_180002E1C
0x180002e0a  mov     [rsp+0E8h+var_98], r15
0x180002e0f  mov     rax, [rcx]
0x180002e12  mov     rax, [rax+10h]
0x180002e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e1b  nop
0x180002e1c  mov     rbx, [rsp+0E8h+var_C0]
0x180002e21  jmp     loc_180002CAA
0x180002e26  test    rbx, rbx
0x180002e29  jnz     short loc_180002E6B
0x180002e2b  lock inc qword ptr [r13+98h]
0x180002e33  mov     rcx, [r13+90h]; pwk
0x180002e3a  call    cs:__imp_SubmitThreadpoolWork
0x180002e40  jmp     short loc_180002DD4
0x180002e42  mov     rcx, rbx; lpCriticalSection
0x180002e45  call    cs:__imp_LeaveCriticalSection
0x180002e4b  jmp     short loc_180002DD4
0x180002e4d  lea     rdx, [rsp+0E8h+var_98]
0x180002e52  cmp     dword ptr [r13+10h], 1
0x180002e57  jnz     short loc_180002E60
0x180002e59  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__ConnectionPointContainer__Notify____10____lambda_1___
0x180002e5e  jmp     short loc_180002E26
0x180002e60  add     rcx, 50h ; 'P'
0x180002e64  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__ConnectionPointContainer__Notify____10____lambda_1___
0x180002e69  jmp     short loc_180002E26
0x180002e6b  mov     rcx, rbx; lpCriticalSection
0x180002e6e  call    cs:__imp_LeaveCriticalSection
0x180002e74  jmp     short loc_180002E2B
0x180002e76  xor     r15d, r15d
0x180002e79  lea     r12, WPP_GLOBAL_Control
0x180002e80  mov     rdi, [rsp+0E8h+var_B8]
0x180002e85  mov     rsi, [rsp+0E8h+var_C8]
0x180002e8a  mov     r14, [rsp+0E8h+var_B0]
0x180002e8f  mov     rbx, [rsp+0E8h+var_A8]
0x180002e94  mov     [rsp+0E8h+var_C0], rbx
0x180002e99  jmp     loc_180002CAA
0x180002e9e  mov     rcx, rdi; lpCriticalSection
0x180002ea1  call    cs:__imp_LeaveCriticalSection
0x180002ea7  jmp     loc_180002D06
```
