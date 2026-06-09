# CServicesManager::OnTimerCallback(void *)

- ea: `0x140037190`
- end: `0x140037596`
- name: `?OnTimerCallback@CServicesManager@@EEAAXPEAX@Z`
- size: `1030`
- prototype: `void __fastcall(CServicesManager *__hidden this, void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callees

- `0x14000c778`
- `0x14000cf40`
- `0x14000d054`
- `0x140024a20`
- `0x14002ed50`
- `0x140036284`
- `0x140037190`
- `0x14003759c`
- `0x14003895c`
- `0x1400940c0`
- `0x1400dfd00`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14003751b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003751b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003723d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003723d`

## pseudocode

```c
void __fastcall CServicesManager::OnTimerCallback(CServicesManager *this, char *a2, __int64 a3)
{
  int v5; // edx
  char v6; // bp
  __int64 v7; // rsi
  int v8; // edx
  int v9; // eax
  PDEVICE_OBJECT v10; // rcx
  int v11; // r9d
  unsigned __int64 CurrentTime; // rax
  int v13; // r8d
  PDEVICE_OBJECT v14; // rcx
  int v15; // r9d
  KIRQL v16; // dl
  int v17; // edx
  __int64 v18; // [rsp+28h] [rbp-60h]
  __int128 v19; // [rsp+40h] [rbp-48h] BYREF
  __int64 v20; // [rsp+50h] [rbp-38h]

  if ( (unsigned int)Feature_54699885__private_IsEnabledDeviceUsageNoInline(this, a2, a3) )
  {
    CServicesManager::OnTimerCallback_WDFLocks(this, a2);
    return;
  }
  v19 = 0;
  v20 = 0;
  v6 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v5) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      1,
      224,
      (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
  }
  v7 = *((_QWORD *)this + 17);
  *(_BYTE *)(v7 + 8) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v7);
  *(_BYTE *)(v7 + 16) = 1;
  if ( (char *)this + 128 == a2 )
  {
    *((_BYTE *)this + 132) = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v8) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        1,
        225,
        (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
    }
    goto LABEL_25;
  }
  if ( (char *)this + 124 == a2 )
  {
    v9 = *((_DWORD *)this + 26);
    *((_BYTE *)this + 133) = 0;
    if ( v9 )
    {
      if ( *((_BYTE *)this + 53) )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_25;
        v10 = WPP_GLOBAL_Control;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
          goto LABEL_25;
        v11 = 226;
LABEL_19:
        LOBYTE(v8) = 5;
        WPP_RECORDER_SF_d(
          v10->DeviceExtension,
          v8,
          1,
          v11,
          (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
          v9);
LABEL_25:
        v19 = *((_OWORD *)this + 6);
        v20 = *((_QWORD *)this + 14);
        *((_BYTE *)this + 54) = 1;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v8) = 5;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v8,
            1,
            232,
            (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
        }
        CAdapter::IndicateStatus(*((CAdapter **)this + 1), *((_DWORD *)this + 6), 1073938470, 0, &v19, 0x18u);
        goto LABEL_50;
      }
      CurrentTime = CSystem::get_CurrentTime();
      if ( CServicesManager::CheckForExpiredDevicesAndServices(this, CurrentTime) )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_25;
        v10 = WPP_GLOBAL_Control;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
          goto LABEL_25;
        v9 = *((_DWORD *)this + 26);
        v11 = 227;
        goto LABEL_19;
      }
      v8 = *((_DWORD *)this + 28);
      if ( v8 || *((_DWORD *)this + 29) )
      {
        v6 = 1;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v8) = 5;
          WPP_RECORDER_SF_Ld(
            WPP_GLOBAL_Control->DeviceExtension,
            v8,
            v13,
            228,
            (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
            *((_DWORD *)this + 28),
            *((_DWORD *)this + 29));
        }
        goto LABEL_50;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v14 = WPP_GLOBAL_Control;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          v15 = 229;
LABEL_36:
          LOBYTE(v8) = 5;
          WPP_RECORDER_SF_(v14->DeviceExtension, v8, 1, v15, (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
        }
      }
    }
    else
    {
      if ( *((_DWORD *)this + 24) )
      {
        v6 = 1;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v8) = 5;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v8,
            1,
            230,
            (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
            *((_DWORD *)this + 24));
        }
        goto LABEL_50;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v14 = WPP_GLOBAL_Control;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          v15 = 231;
          goto LABEL_36;
        }
      }
    }
  }
LABEL_50:
  v16 = *(_BYTE *)(v7 + 8);
  *(_BYTE *)(v7 + 16) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)v7, v16);
  if ( v6 )
    CServicesManager::StartDeviceExpiryNotificationTimer(this);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v18) = 0;
    LOBYTE(v17) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v17,
      1,
      233,
      (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
      v18);
  }
}

```

## disassembly

```asm
0x140037190  mov     [rsp+arg_8], rbx
0x140037195  mov     [rsp+arg_10], rbp
0x14003719a  push    rsi
0x14003719b  push    rdi
0x14003719c  push    r12
0x14003719e  push    r13
0x1400371a0  push    r14
0x1400371a2  sub     rsp, 60h
0x1400371a6  mov     rax, cs:__security_cookie
0x1400371ad  xor     rax, rsp
0x1400371b0  mov     [rsp+88h+var_30], rax
0x1400371b5  mov     rdi, rdx
0x1400371b8  mov     rbx, rcx
0x1400371bb  call    Feature_54699885__private_IsEnabledDeviceUsageNoInline
0x1400371c0  xor     r14d, r14d
0x1400371c3  test    eax, eax
0x1400371c5  jz      short loc_1400371D7
0x1400371c7  mov     rdx, rdi; void *
0x1400371ca  mov     rcx, rbx; this
0x1400371cd  call    ?OnTimerCallback_WDFLocks@CServicesManager@@AEAAXPEAX@Z; CServicesManager::OnTimerCallback_WDFLocks(void *)
0x1400371d2  jmp     loc_14003756F
0x1400371d7  xorps   xmm0, xmm0
0x1400371da  xor     eax, eax
0x1400371dc  movups  [rsp+88h+var_48], xmm0
0x1400371e1  mov     [rsp+88h+var_38], rax
0x1400371e6  mov     bpl, r14b
0x1400371e9  lea     r12, WPP_RECORDER_INITIALIZED
0x1400371f0  mov     r13d, 1
0x1400371f6  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400371fd  lea     rax, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x140037204  jz      short loc_140037233
0x140037206  mov     rcx, cs:WPP_GLOBAL_Control
0x14003720d  cmp     byte ptr [rcx+29h], 5
0x140037211  jnb     short loc_14003721A
0x140037213  cmp     [rcx+48h], r14w
0x140037218  jz      short loc_140037233
0x14003721a  mov     rcx, [rcx+40h]
0x14003721e  mov     r9d, 0E0h
0x140037224  mov     r8d, r13d
0x140037227  mov     [rsp+88h+var_68], rax
0x14003722c  mov     dl, 5
0x14003722e  call    WPP_RECORDER_SF_
0x140037233  mov     rsi, [rbx+88h]
0x14003723a  mov     rcx, rsi; SpinLock
0x14003723d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140037244  nop     dword ptr [rax+rax+00h]
0x140037249  mov     [rsi+8], al
0x14003724c  lea     rax, [rbx+80h]
0x140037253  mov     [rsi+10h], r13b
0x140037257  cmp     rax, rdi
0x14003725a  jnz     short loc_1400372AD
0x14003725c  mov     [rbx+84h], r14b
0x140037263  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14003726a  jz      loc_140037355
0x140037270  mov     rcx, cs:WPP_GLOBAL_Control
0x140037277  cmp     byte ptr [rcx+29h], 5
0x14003727b  jnb     short loc_140037288
0x14003727d  cmp     [rcx+48h], r14w
0x140037282  jz      loc_140037355
0x140037288  mov     rcx, [rcx+40h]
0x14003728c  lea     rdi, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x140037293  mov     r9d, 0E1h
0x140037299  mov     [rsp+88h+var_68], rdi
0x14003729e  mov     r8d, r13d
0x1400372a1  mov     dl, 5
0x1400372a3  call    WPP_RECORDER_SF_
0x1400372a8  jmp     loc_14003735C
0x1400372ad  lea     rax, [rbx+7Ch]
0x1400372b1  cmp     rax, rdi
0x1400372b4  jnz     loc_14003750A
0x1400372ba  mov     eax, [rbx+68h]
0x1400372bd  mov     [rbx+85h], r14b
0x1400372c4  test    eax, eax
0x1400372c6  jz      loc_140037495
0x1400372cc  cmp     [rbx+35h], r14b
0x1400372d0  jz      short loc_140037315
0x1400372d2  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400372d9  jz      short loc_140037355
0x1400372db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400372e2  cmp     byte ptr [rcx+29h], 5
0x1400372e6  jnb     short loc_1400372EF
0x1400372e8  cmp     [rcx+48h], r14w
0x1400372ed  jz      short loc_140037355
0x1400372ef  mov     r9d, 0E2h
0x1400372f5  mov     rcx, [rcx+40h]
0x1400372f9  lea     rdi, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x140037300  mov     dword ptr [rsp+88h+var_60], eax
0x140037304  mov     r8d, r13d
0x140037307  mov     dl, 5
0x140037309  mov     [rsp+88h+var_68], rdi
0x14003730e  call    WPP_RECORDER_SF_d
0x140037313  jmp     short loc_14003735C
0x140037315  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x14003731a  mov     rdx, rax; unsigned __int64
0x14003731d  mov     rcx, rbx; this
0x140037320  call    ?CheckForExpiredDevicesAndServices@CServicesManager@@QEAAK_K@Z; CServicesManager::CheckForExpiredDevicesAndServices(unsigned __int64)
0x140037325  test    eax, eax
0x140037327  jz      loc_1400373EC
0x14003732d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140037334  jz      short loc_140037355
0x140037336  mov     rcx, cs:WPP_GLOBAL_Control
0x14003733d  cmp     byte ptr [rcx+29h], 5
0x140037341  jnb     short loc_14003734A
0x140037343  cmp     [rcx+48h], r14w
0x140037348  jz      short loc_140037355
0x14003734a  mov     eax, [rbx+68h]
0x14003734d  mov     r9d, 0E3h
0x140037353  jmp     short loc_1400372F5
0x140037355  lea     rdi, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x14003735c  mov     eax, [rbx+60h]
0x14003735f  mov     dword ptr [rsp+88h+var_48], eax
0x140037363  mov     eax, [rbx+64h]
0x140037366  mov     dword ptr [rsp+88h+var_48+4], eax
0x14003736a  mov     eax, [rbx+68h]
0x14003736d  mov     dword ptr [rsp+88h+var_48+8], eax
0x140037371  mov     eax, [rbx+6Ch]
0x140037374  mov     dword ptr [rsp+88h+var_48+0Ch], eax
0x140037378  mov     eax, [rbx+70h]
0x14003737b  mov     dword ptr [rsp+88h+var_38], eax
0x14003737f  mov     eax, [rbx+74h]
0x140037382  mov     dword ptr [rsp+88h+var_38+4], eax
0x140037386  mov     [rbx+36h], r13b
0x14003738a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140037391  jz      short loc_1400373C0
0x140037393  mov     rcx, cs:WPP_GLOBAL_Control
0x14003739a  cmp     byte ptr [rcx+29h], 5
0x14003739e  jnb     short loc_1400373A7
0x1400373a0  cmp     [rcx+48h], r14w
0x1400373a5  jz      short loc_1400373C0
0x1400373a7  mov     rcx, [rcx+40h]
0x1400373ab  mov     r9d, 0E8h
0x1400373b1  mov     r8d, r13d
0x1400373b4  mov     [rsp+88h+var_68], rdi
0x1400373b9  mov     dl, 5
0x1400373bb  call    WPP_RECORDER_SF_
0x1400373c0  mov     edx, [rbx+18h]; unsigned int
0x1400373c3  lea     rax, [rsp+88h+var_48]
0x1400373c8  mov     rcx, [rbx+8]; this
0x1400373cc  xor     r9d, r9d; void *
0x1400373cf  mov     dword ptr [rsp+88h+var_60], 18h; unsigned int
0x1400373d7  mov     r8d, 40030026h; int
0x1400373dd  mov     [rsp+88h+var_68], rax; void *
0x1400373e2  call    ?IndicateStatus@CAdapter@@QEAAXKHPEAX0K@Z; CAdapter::IndicateStatus(ulong,int,void *,void *,ulong)
0x1400373e7  jmp     loc_140037511
0x1400373ec  mov     edx, [rbx+70h]
0x1400373ef  test    edx, edx
0x1400373f1  jnz     short loc_140037443
0x1400373f3  cmp     [rbx+74h], r14d
0x1400373f7  jnz     short loc_140037443
0x1400373f9  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140037400  jz      loc_14003750A
0x140037406  mov     rcx, cs:WPP_GLOBAL_Control
0x14003740d  cmp     byte ptr [rcx+29h], 5
0x140037411  jnb     short loc_14003741E
0x140037413  cmp     [rcx+48h], r14w
0x140037418  jz      loc_14003750A
0x14003741e  mov     r9d, 0E5h
0x140037424  mov     rcx, [rcx+40h]
0x140037428  lea     rdi, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x14003742f  mov     r8d, r13d
0x140037432  mov     [rsp+88h+var_68], rdi
0x140037437  mov     dl, 5
0x140037439  call    WPP_RECORDER_SF_
0x14003743e  jmp     loc_140037511
0x140037443  mov     bpl, r13b
0x140037446  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14003744d  jz      loc_14003750A
0x140037453  mov     rcx, cs:WPP_GLOBAL_Control
0x14003745a  cmp     byte ptr [rcx+29h], 5
0x14003745e  jnb     short loc_14003746B
0x140037460  cmp     [rcx+48h], r14w
0x140037465  jz      loc_14003750A
0x14003746b  mov     eax, [rbx+74h]
0x14003746e  lea     rdi, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x140037475  mov     rcx, [rcx+40h]
0x140037479  mov     r9d, 0E4h
0x14003747f  mov     [rsp+88h+var_58], eax
0x140037483  mov     dword ptr [rsp+88h+var_60], edx
0x140037487  mov     dl, 5
0x140037489  mov     [rsp+88h+var_68], rdi
0x14003748e  call    WPP_RECORDER_SF_Ld
0x140037493  jmp     short loc_140037511
0x140037495  mov     eax, [rbx+60h]
0x140037498  test    eax, eax
0x14003749a  jz      short loc_1400374E2
0x14003749c  mov     bpl, r13b
0x14003749f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400374a6  jz      short loc_14003750A
0x1400374a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400374af  cmp     byte ptr [rcx+29h], 5
0x1400374b3  jnb     short loc_1400374BC
0x1400374b5  cmp     [rcx+48h], r14w
0x1400374ba  jz      short loc_14003750A
0x1400374bc  mov     rcx, [rcx+40h]
0x1400374c0  lea     rdi, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x1400374c7  mov     dword ptr [rsp+88h+var_60], eax
0x1400374cb  mov     r9d, 0E6h
0x1400374d1  mov     r8d, r13d
0x1400374d4  mov     [rsp+88h+var_68], rdi
0x1400374d9  mov     dl, 5
0x1400374db  call    WPP_RECORDER_SF_d
0x1400374e0  jmp     short loc_140037511
0x1400374e2  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400374e9  jz      short loc_14003750A
0x1400374eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400374f2  cmp     byte ptr [rcx+29h], 5
0x1400374f6  jnb     short loc_1400374FF
0x1400374f8  cmp     [rcx+48h], r14w
0x1400374fd  jz      short loc_14003750A
0x1400374ff  mov     r9d, 0E7h
0x140037505  jmp     loc_140037424
0x14003750a  lea     rdi, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x140037511  mov     dl, [rsi+8]; NewIrql
0x140037514  mov     rcx, rsi; SpinLock
0x140037517  mov     [rsi+10h], r14b
0x14003751b  call    cs:__imp_KeReleaseSpinLock
0x140037522  nop     dword ptr [rax+rax+00h]
0x140037527  test    bpl, bpl
0x14003752a  jz      short loc_140037534
0x14003752c  mov     rcx, rbx; this
0x14003752f  call    ?StartDeviceExpiryNotificationTimer@CServicesManager@@QEAAXXZ; CServicesManager::StartDeviceExpiryNotificationTimer(void)
0x140037534  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14003753b  jz      short loc_14003756F
0x14003753d  mov     rcx, cs:WPP_GLOBAL_Control
0x140037544  cmp     byte ptr [rcx+29h], 5
0x140037548  jnb     short loc_140037551
0x14003754a  cmp     [rcx+48h], r14w
0x14003754f  jz      short loc_14003756F
0x140037551  mov     rcx, [rcx+40h]
0x140037555  mov     r9d, 0E9h
0x14003755b  mov     dword ptr [rsp+88h+var_60], r14d
0x140037560  mov     r8d, r13d
0x140037563  mov     dl, 5
0x140037565  mov     [rsp+88h+var_68], rdi
0x14003756a  call    WPP_RECORDER_SF_d
0x14003756f  mov     rcx, [rsp+88h+var_30]
0x140037574  xor     rcx, rsp; StackCookie
0x140037577  call    __security_check_cookie
0x14003757c  lea     r11, [rsp+88h+var_28]
0x140037581  mov     rbx, [r11+38h]
0x140037585  mov     rbp, [r11+40h]
0x140037589  mov     rsp, r11
0x14003758c  pop     r14
0x14003758e  pop     r13
0x140037590  pop     r12
0x140037592  pop     rdi
0x140037593  pop     rsi
0x140037594  retn
```
