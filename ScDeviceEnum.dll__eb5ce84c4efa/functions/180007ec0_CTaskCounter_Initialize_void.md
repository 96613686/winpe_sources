# CTaskCounter::Initialize(void)

- ea: `0x180007ec0`
- end: `0x180008069`
- name: `?Initialize@CTaskCounter@@SAJXZ`
- size: `425`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180006670`

## callees

- `0x1800076b8`
- `0x1800079a0`
- `0x180007af0`
- `0x180007b18`
- `0x180007ec0`
- `0x180008070`
- `0x180008274`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ff7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180007f6c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180007f6c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007fd4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007fd4`

## string_xrefs

- `0x180007eeb`: `CTaskCounter::Initialize`

## pseudocode

```c
__int64 CTaskCounter::Initialize(void)
{
  struct CTaskCounter *v0; // rax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rbx
  signed int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rbx
  struct CTaskCounter *v5; // rax
  struct CTaskCounter *v6; // rax
  PTP_TIMER ThreadpoolTimer; // rbx
  signed int LastError; // eax
  CTaskCounter *v9; // rax
  char v11; // [rsp+20h] [rbp-60h] BYREF
  __int16 v12; // [rsp+21h] [rbp-5Fh]
  char v13; // [rsp+24h] [rbp-5Ch] BYREF
  __int16 v14; // [rsp+25h] [rbp-5Bh]
  unsigned int v15; // [rsp+28h] [rbp-58h] BYREF
  int v16; // [rsp+2Ch] [rbp-54h] BYREF
  _QWORD *v17; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v18[3]; // [rsp+38h] [rbp-48h] BYREF
  char v19[32]; // [rsp+50h] [rbp-30h] BYREF

  v15 = 0;
  v16 = 0;
  strcpy(v19, "CTaskCounter::Initialize");
  v18[0] = v19;
  v18[1] = &v16;
  v18[2] = &v15;
  lambda_87e2e97d065fe741d2023e899a671b47_::operator()(v18);
  v16 = 1;
  v17 = v18;
  v0 = CTaskCounter::Instance();
  *((_DWORD *)v0 + 12) = 3;
  *((_QWORD *)v0 + 7) = 0;
  *((_QWORD *)v0 + 8) = 0;
  *((_QWORD *)v0 + 9) = 0;
  *((_QWORD *)v0 + 10) = 0;
  *((_QWORD *)v0 + 11) = 0;
  *((_QWORD *)v0 + 12) = 0;
  *((_DWORD *)v0 + 26) = 0;
  *((_DWORD *)v0 + 27) = 1;
  *((_DWORD *)v0 + 28) = 72;
  v14 = 256;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)CTaskCounter::Instance() + 15) = ThreadpoolCleanupGroup;
  if ( *((_QWORD *)CTaskCounter::Instance() + 15) )
  {
    v12 = 258;
    v4 = *((_QWORD *)CTaskCounter::Instance() + 15);
    v5 = CTaskCounter::Instance();
    *((_QWORD *)v5 + 8) = v4;
    *((_QWORD *)v5 + 9) = 0;
    v6 = CTaskCounter::Instance();
    ThreadpoolTimer = CreateThreadpoolTimer(
                        (PTP_TIMER_CALLBACK)CTaskCounter::_IdleStopCallback,
                        0,
                        (PTP_CALLBACK_ENVIRON)((char *)v6 + 48));
    *((_QWORD *)CTaskCounter::Instance() + 16) = ThreadpoolTimer;
    if ( *((_QWORD *)CTaskCounter::Instance() + 16) )
    {
      v9 = CTaskCounter::Instance();
      CTaskCounter::_StartTimer(v9);
      HIBYTE(v14) = 0;
      HIBYTE(v12) = 0;
      v3 = v15;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      v15 = v3;
    }
    wil::details::ScopeExitFnGuard__lambda_9f007dc2373c375adaf9b2bd25c52df1___::operator()(&v11);
  }
  else
  {
    v2 = GetLastError();
    v3 = v2;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    v15 = v3;
  }
  wil::details::ScopeExitFnGuard__lambda_349182dd85bd6507f6866e4526050a91___::operator()(&v13);
  WppTraceUnwinder__lambda_87e2e97d065fe741d2023e899a671b47____::_WppTraceUnwinder__lambda_87e2e97d065fe741d2023e899a671b47____(&v17);
  return v3;
}

```

## disassembly

```asm
0x180007ec0  mov     [rsp-8+arg_0], rbx
0x180007ec5  mov     [rsp-8+arg_8], rdi
0x180007eca  push    rbp
0x180007ecb  mov     rbp, rsp
0x180007ece  sub     rsp, 80h
0x180007ed5  mov     rax, cs:__security_cookie
0x180007edc  xor     rax, rsp
0x180007edf  mov     [rbp+var_10], rax
0x180007ee3  xor     edi, edi
0x180007ee5  mov     [rbp+var_58], edi
0x180007ee8  mov     [rbp+var_54], edi
0x180007eeb  movups  xmm0, xmmword ptr cs:aCtaskcounterIn_0; "CTaskCounter::Initialize"
0x180007ef2  movups  xmmword ptr [rbp+var_30], xmm0
0x180007ef6  movups  xmm1, xmmword ptr cs:aCtaskcounterIn_0+9; "ter::Initialize"
0x180007efd  movups  xmmword ptr [rbp+var_30+9], xmm1
0x180007f01  lea     rax, [rbp+var_30]
0x180007f05  mov     [rbp+var_48], rax
0x180007f09  lea     rax, [rbp+var_54]
0x180007f0d  mov     [rbp+var_40], rax
0x180007f11  lea     rax, [rbp+var_58]
0x180007f15  mov     [rbp+var_38], rax
0x180007f19  lea     rcx, [rbp+var_48]
0x180007f1d  call    _lambda_87e2e97d065fe741d2023e899a671b47___operator__
0x180007f22  mov     [rbp+var_54], 1
0x180007f29  lea     rax, [rbp+var_48]
0x180007f2d  mov     [rbp+var_50], rax
0x180007f31  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007f36  mov     dword ptr [rax+30h], 3
0x180007f3d  mov     [rax+38h], rdi
0x180007f41  mov     [rax+40h], rdi
0x180007f45  mov     [rax+48h], rdi
0x180007f49  mov     [rax+50h], rdi
0x180007f4d  mov     [rax+58h], rdi
0x180007f51  mov     [rax+60h], rdi
0x180007f55  mov     [rax+68h], edi
0x180007f58  mov     dword ptr [rax+6Ch], 1
0x180007f5f  mov     dword ptr [rax+70h], 48h ; 'H'
0x180007f66  mov     [rbp+var_5B], 100h
0x180007f6c  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180007f72  mov     rbx, rax
0x180007f75  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007f7a  mov     [rax+78h], rbx
0x180007f7e  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007f83  cmp     [rax+78h], rdi
0x180007f87  jnz     short loc_180007FA6
0x180007f89  call    cs:__imp_GetLastError
0x180007f8f  mov     ebx, eax
0x180007f91  test    eax, eax
0x180007f93  jle     short loc_180007F9E
0x180007f95  movzx   ebx, ax
0x180007f98  or      ebx, 80070000h
0x180007f9e  mov     [rbp+var_58], ebx
0x180007fa1  jmp     loc_180008033
0x180007fa6  mov     [rbp+var_5F], 102h
0x180007fac  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007fb1  mov     rbx, [rax+78h]
0x180007fb5  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007fba  mov     [rax+40h], rbx
0x180007fbe  mov     [rax+48h], rdi
0x180007fc2  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007fc7  lea     r8, [rax+30h]; pcbe
0x180007fcb  xor     edx, edx; pv
0x180007fcd  lea     rcx, ?_IdleStopCallback@CTaskCounter@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180007fd4  call    cs:__imp_CreateThreadpoolTimer
0x180007fda  mov     rbx, rax
0x180007fdd  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007fe2  mov     [rax+80h], rbx
0x180007fe9  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007fee  cmp     [rax+80h], rdi
0x180007ff5  jnz     short loc_180008011
0x180007ff7  call    cs:__imp_GetLastError
0x180007ffd  mov     ebx, eax
0x180007fff  test    eax, eax
0x180008001  jle     short loc_18000800C
0x180008003  movzx   ebx, ax
0x180008006  or      ebx, 80070000h
0x18000800c  mov     [rbp+var_58], ebx
0x18000800f  jmp     short loc_180008029
0x180008011  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180008016  mov     rcx, rax; this
0x180008019  call    ?_StartTimer@CTaskCounter@@AEAAXXZ; CTaskCounter::_StartTimer(void)
0x18000801e  mov     byte ptr [rbp+var_5B+1], dil
0x180008022  mov     byte ptr [rbp+var_5F+1], dil
0x180008026  mov     ebx, [rbp+var_58]
0x180008029  lea     rcx, [rbp+var_60]
0x18000802d  call    wil__details__ScopeExitFnGuard__lambda_9f007dc2373c375adaf9b2bd25c52df1_____operator__
0x180008032  nop
0x180008033  lea     rcx, [rbp+var_5C]
0x180008037  call    wil__details__ScopeExitFnGuard__lambda_349182dd85bd6507f6866e4526050a91_____operator__
0x18000803c  nop
0x18000803d  lea     rcx, [rbp+var_50]
0x180008041  call    WppTraceUnwinder__lambda_87e2e97d065fe741d2023e899a671b47_______WppTraceUnwinder__lambda_87e2e97d065fe741d2023e899a671b47____
0x180008046  mov     eax, ebx
0x180008048  mov     rcx, [rbp+var_10]
0x18000804c  xor     rcx, rsp; StackCookie
0x18000804f  call    __security_check_cookie
0x180008054  lea     r11, [rsp+80h+var_s0]
0x18000805c  mov     rbx, [r11+10h]
0x180008060  mov     rdi, [r11+18h]
0x180008064  mov     rsp, r11
0x180008067  pop     rbp
0x180008068  retn
```
