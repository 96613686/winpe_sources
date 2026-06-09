# A2DP_Device::A2DP_Device(_KSDEVICE *)

- ea: `0x14002ead0`
- end: `0x14002efe6`
- name: `??0A2DP_Device@@QEAA@PEAU_KSDEVICE@@@Z`
- size: `1302`
- prototype: `A2DP_Device *__fastcall(A2DP_Device *__hidden this, struct _KSDEVICE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x14003bcd0`

## callees

- `0x140003530`
- `0x14000e240`
- `0x1400126ac`
- `0x14002b8fc`
- `0x14002ead0`
- `0x1400315a0`
- `0x14003e028`
- `0x14005c8c0`

## import_xrefs

- `ntoskrnl!IoInitializeRemoveLockEx` at `0x14002ed98`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x14002ed98`
- `ntoskrnl!KeInitializeDpc` at `0x14002ed42`
- `ntoskrnl!KeInitializeDpc` at `0x14002ed72`
- `ntoskrnl!KeInitializeDpc` at `0x14002ed42`
- `ntoskrnl!KeInitializeDpc` at `0x14002ed72`
- `ntoskrnl!KeInitializeTimer` at `0x14002ed25`
- `ntoskrnl!KeInitializeTimer` at `0x14002ed55`
- `ntoskrnl!KeInitializeTimer` at `0x14002ed25`
- `ntoskrnl!KeInitializeTimer` at `0x14002ed55`
- `ntoskrnl!KeInitializeEvent` at `0x14002edd4`
- `ntoskrnl!KeInitializeEvent` at `0x14002edec`
- `ntoskrnl!KeInitializeEvent` at `0x14002ee04`
- `ntoskrnl!KeInitializeEvent` at `0x14002edd4`
- `ntoskrnl!KeInitializeEvent` at `0x14002edec`
- `ntoskrnl!KeInitializeEvent` at `0x14002ee04`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002eb40`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002eb95`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002ed12`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002eb40`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002eb95`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002ed12`

## pseudocode

```c
A2DP_Device *__fastcall A2DP_Device::A2DP_Device(A2DP_Device *this, struct _KSDEVICE *a2)
{
  int v4; // edx
  int v5; // r8d
  unsigned int RegistryDWord; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // ecx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  unsigned int v13; // ecx
  unsigned int v14; // ebx
  unsigned int v15; // eax
  unsigned int v16; // ecx
  unsigned int v17; // eax

  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_DWORD *)this + 204) = 0;
  *(_BYTE *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 88) = 0;
  *((_QWORD *)this + 89) = 0;
  *((_BYTE *)this + 732) = 0;
  *((_QWORD *)this + 92) = 0;
  *((_WORD *)this + 428) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)this + 108);
  *((_DWORD *)this + 690) = 0;
  *((_QWORD *)this + 109) = -1;
  *((_QWORD *)this + 110) = -1;
  *((_QWORD *)this + 111) = -1;
  *((_QWORD *)this + 112) = -1;
  *((_QWORD *)this + 113) = -1;
  *((_QWORD *)this + 114) = -1;
  *((_QWORD *)this + 346) = 0;
  *((_QWORD *)this + 347) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)this + 348);
  *((_QWORD *)this + 349) = 0;
  *((_QWORD *)this + 350) = 0;
  *(_QWORD *)((char *)this + 2812) = 0;
  *((_WORD *)this + 1572) = 0;
  memset((char *)this + 3288, 0, 0x40u);
  *((_DWORD *)this + 839) = 0;
  *((_QWORD *)this + 420) = 0;
  *((_WORD *)this + 1676) = 1;
  *((_BYTE *)this + 3368) = 0;
  *((_DWORD *)this + 843) = 0;
  wil::details::kernel_event_t<0>::kernel_event_t<0>((char *)this + 3376);
  *((_DWORD *)this + 850) = 1;
  *((_BYTE *)this + 3404) = 0;
  *((_BYTE *)this + 3408) = 1;
  *(_OWORD *)((char *)this + 3412) = 0;
  *(_OWORD *)((char *)this + 3428) = 0;
  *(_OWORD *)((char *)this + 3444) = 0;
  *(_QWORD *)((char *)this + 3460) = 0;
  *((_QWORD *)this + 437) = (char *)this + 3512;
  *((_QWORD *)this + 438) = (char *)this + 3512;
  *((_WORD *)this + 1756) = 0;
  *((_BYTE *)this + 3468) = 0;
  *((_QWORD *)this + 434) = 0;
  *((_QWORD *)this + 435) = 0;
  *((_BYTE *)this + 3488) = 0;
  memset((char *)this + 3528, 0, 0x48u);
  *((_WORD *)this + 1800) = 0;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
    || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
  {
    LOBYTE(v4) = 0;
  }
  if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v4,
      v5,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      19,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      (char)a2);
  }
  A2DP_Device::AddRef(this, 10, "A2DP_Device");
  KeInitializeSpinLock((PKSPIN_LOCK)this + 87);
  KeInitializeTimer((PKTIMER)((char *)this + 3016));
  KeInitializeDpc((PRKDPC)((char *)this + 3080), A2DP_Device::DiscoveryTimerDpc, this);
  KeInitializeTimer((PKTIMER)((char *)this + 3152));
  KeInitializeDpc((PRKDPC)((char *)this + 3216), A2DP_Device::ServiceReadyTimerDpc, this);
  IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)((char *)this + 824), 0x50444141u, 0, 0, 0x20u);
  *((_QWORD *)this + 46) = a2;
  *((_QWORD *)this + 47) = a2->NextDeviceObject;
  *((_QWORD *)this + 48) = a2->FunctionalDeviceObject;
  *((_QWORD *)this + 410) = 0;
  KeInitializeEvent((PRKEVENT)this + 31, NotificationEvent, 0);
  KeInitializeEvent((PRKEVENT)this + 32, NotificationEvent, 0);
  KeInitializeEvent((PRKEVENT)this + 33, NotificationEvent, 0);
  *((_WORD *)this + 408) = 0;
  *((_BYTE *)this + 818) = 0;
  A2DP_Device::InitializeStreamingState(this);
  *((_DWORD *)this + 98) = 1;
  IrpQueue::Initialize((A2DP_Device *)((char *)this + 32));
  IrpQueue::Initialize((A2DP_Device *)((char *)this + 120));
  *((_DWORD *)this + 822) = 0;
  *((_DWORD *)this + 823) = 100;
  RegistryDWord = QueryRegistryDWord(&DriverParametersRegistryPathName, L"LevelIncrement", 1u);
  if ( RegistryDWord >= 0x64 )
  {
    RegistryDWord = 100;
  }
  else if ( RegistryDWord <= 1 )
  {
    RegistryDWord = 1;
  }
  v7 = *((_DWORD *)this + 823);
  *((_DWORD *)this + 824) = RegistryDWord;
  v8 = QueryRegistryDWord(&DriverParametersRegistryPathName, L"LevelDecrement", 1u);
  v9 = v7;
  if ( v8 < v7 )
    v9 = v8;
  if ( v9 <= 1 )
  {
    v7 = 1;
  }
  else if ( v8 < v7 )
  {
    v7 = v8;
  }
  *((_DWORD *)this + 825) = v7;
  *((_DWORD *)this + 826) = 0;
  *((_DWORD *)this + 827) = 100;
  v10 = QueryRegistryDWord(&DriverParametersRegistryPathName, L"BackoffDecrement", 1u);
  if ( v10 >= 0x64 )
  {
    v10 = 100;
  }
  else if ( v10 <= 1 )
  {
    v10 = 1;
  }
  v11 = *((_DWORD *)this + 827);
  *((_DWORD *)this + 830) = v11;
  *((_DWORD *)this + 828) = v10;
  *((_DWORD *)this + 829) = 0;
  v12 = QueryRegistryDWord(&DriverParametersRegistryPathName, L"BackoffFloorIncrement", 1u);
  v13 = v11;
  if ( v12 < v11 )
    v13 = v12;
  if ( v13 <= 1 )
  {
    v11 = 1;
  }
  else if ( v12 < v11 )
  {
    v11 = v12;
  }
  *((_DWORD *)this + 831) = v11;
  v14 = *((_DWORD *)this + 830);
  v15 = QueryRegistryDWord(&DriverParametersRegistryPathName, L"BackoffFloorDecrement", 1u);
  v16 = v14;
  if ( v15 < v14 )
    v16 = v15;
  if ( v16 <= 1 )
  {
    v14 = 1;
  }
  else if ( v15 < v14 )
  {
    v14 = v15;
  }
  *((_DWORD *)this + 832) = v14;
  *((_DWORD *)this + 833) = 0;
  *((_DWORD *)this + 834) = 1000;
  v17 = QueryRegistryDWord(&DriverParametersRegistryPathName, L"StabilityIncrement", 0xAu);
  if ( v17 >= 0x3E8 )
  {
    v17 = 1000;
  }
  else if ( v17 <= 1 )
  {
    v17 = 1;
  }
  *((_DWORD *)this + 835) = v17;
  *((_BYTE *)this + 3352) = (unsigned int)QueryRegistryDWord(
                                            &DriverParametersRegistryPathName,
                                            L"CongestionBackoffEnabled",
                                            1u) != 0;
  *((_BYTE *)this + 3353) = (unsigned int)QueryRegistryDWord(
                                            &DriverParametersRegistryPathName,
                                            L"CongestionTestMode",
                                            0) != 0;
  return this;
}

```

## disassembly

```asm
0x14002ead0  push    rbx
0x14002ead2  push    rbp
0x14002ead3  push    rsi
0x14002ead4  push    rdi
0x14002ead5  push    r14
0x14002ead7  push    r15
0x14002ead9  sub     rsp, 58h
0x14002eadd  xor     ebp, ebp
0x14002eadf  mov     rdi, rcx
0x14002eae2  mov     [rcx+10h], rbp
0x14002eae6  mov     rsi, rdx
0x14002eae9  mov     [rcx+18h], rbp
0x14002eaed  mov     [rcx+170h], rbp
0x14002eaf4  mov     [rcx+178h], rbp
0x14002eafb  mov     [rcx+180h], rbp
0x14002eb02  mov     [rcx+330h], ebp
0x14002eb08  mov     [rcx], bpl
0x14002eb0b  mov     [rcx+8], rbp
0x14002eb0f  mov     [rcx+190h], rbp
0x14002eb16  mov     [rcx+2C0h], rbp
0x14002eb1d  mov     [rcx+2C8h], rbp
0x14002eb24  mov     [rcx+2DCh], bpl
0x14002eb2b  mov     [rcx+2E0h], rbp
0x14002eb32  mov     [rcx+358h], bp
0x14002eb39  add     rcx, 360h; SpinLock
0x14002eb40  call    cs:__imp_KeInitializeSpinLock
0x14002eb47  nop     dword ptr [rax+rax+00h]
0x14002eb4c  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002eb50  mov     [rdi+0AC8h], ebp
0x14002eb56  lea     rcx, [rdi+0AE0h]; SpinLock
0x14002eb5d  mov     [rdi+368h], rax
0x14002eb64  mov     [rdi+370h], rax
0x14002eb6b  mov     [rdi+378h], rax
0x14002eb72  mov     [rdi+380h], rax
0x14002eb79  mov     [rdi+388h], rax
0x14002eb80  mov     [rdi+390h], rax
0x14002eb87  mov     [rdi+0AD0h], rbp
0x14002eb8e  mov     [rdi+0AD8h], rbp
0x14002eb95  call    cs:__imp_KeInitializeSpinLock
0x14002eb9c  nop     dword ptr [rax+rax+00h]
0x14002eba1  lea     r14, [rdi+0CD8h]
0x14002eba8  mov     [rdi+0AE8h], rbp
0x14002ebaf  mov     rcx, r14; void *
0x14002ebb2  mov     [rdi+0AF0h], rbp
0x14002ebb9  xor     edx, edx; Val
0x14002ebbb  mov     [rdi+0AFCh], rbp
0x14002ebc2  lea     r8d, [rbp+40h]; Size
0x14002ebc6  mov     [rdi+0C48h], bp
0x14002ebcd  call    memset
0x14002ebd2  lea     rbx, [rdi+0D30h]
0x14002ebd9  mov     [rdi+0D1Ch], ebp
0x14002ebdf  lea     r15d, [rbp+1]
0x14002ebe3  mov     [rdi+0D20h], rbp
0x14002ebea  mov     rcx, rbx
0x14002ebed  mov     [rdi+0D18h], r15w
0x14002ebf5  mov     [rdi+0D28h], bpl
0x14002ebfc  mov     [rdi+0D2Ch], ebp
0x14002ec02  call    ??0?$kernel_event_t@$0A@@details@wil@@QEAA@_N@Z; wil::details::kernel_event_t<0>::kernel_event_t<0>(bool)
0x14002ec07  mov     [rbx+18h], r15d
0x14002ec0b  lea     rcx, [rdi+0DB8h]
0x14002ec12  mov     [rbx+1Ch], bpl
0x14002ec16  lea     r8d, [rbp+48h]; Size
0x14002ec1a  mov     [rdi+0D50h], r15b
0x14002ec21  xorps   xmm0, xmm0
0x14002ec24  movups  xmmword ptr [rdi+0D54h], xmm0
0x14002ec2b  xor     eax, eax
0x14002ec2d  xor     edx, edx; Val
0x14002ec2f  movups  xmmword ptr [rdi+0D64h], xmm0
0x14002ec36  movups  xmmword ptr [rdi+0D74h], xmm0
0x14002ec3d  mov     [rdi+0D84h], rax
0x14002ec44  mov     [rdi+0DA8h], rcx
0x14002ec4b  mov     [rdi+0DB0h], rcx
0x14002ec52  mov     [rcx], bp
0x14002ec55  lea     rcx, [rdi+0DC8h]; void *
0x14002ec5c  mov     [rdi+0D8Ch], bpl
0x14002ec63  mov     [rdi+0D90h], rbp
0x14002ec6a  mov     [rdi+0D98h], rbp
0x14002ec71  mov     [rdi+0DA0h], bpl
0x14002ec78  call    memset
0x14002ec7d  mov     [rdi+0E10h], bp
0x14002ec84  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ec8b  lea     rax, WPP_GLOBAL_Control
0x14002ec92  cmp     rcx, rax
0x14002ec95  jz      short loc_14002ECA7
0x14002ec97  mov     eax, [rcx+2Ch]
0x14002ec9a  test    al, 10h
0x14002ec9c  jz      short loc_14002ECA7
0x14002ec9e  cmp     byte ptr [rcx+29h], 4
0x14002eca2  mov     dl, r15b
0x14002eca5  jnb     short loc_14002ECAA
0x14002eca7  mov     dl, bpl
0x14002ecaa  lea     rax, WPP_RECORDER_INITIALIZED
0x14002ecb1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002ecb8  setnz   r8b
0x14002ecbc  test    dl, dl
0x14002ecbe  jnz     short loc_14002ECC5
0x14002ecc0  test    r8b, r8b
0x14002ecc3  jz      short loc_14002ECF7
0x14002ecc5  mov     r9, [rcx+40h]
0x14002ecc9  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14002ecd0  mov     rcx, [rcx+18h]
0x14002ecd4  mov     [rsp+88h+var_48], rsi
0x14002ecd9  mov     [rsp+88h+var_50], rax
0x14002ecde  mov     [rsp+88h+var_58], 13h
0x14002ece5  mov     [rsp+88h+var_60], 5
0x14002eced  mov     byte ptr [rsp+88h+RemlockSize], 4
0x14002ecf2  call    WPP_RECORDER_AND_TRACE_SF_q
0x14002ecf7  mov     edx, 0Ah; __int16
0x14002ecfc  lea     r8, aA2dpDevice; "A2DP_Device"
0x14002ed03  mov     rcx, rdi; this
0x14002ed06  call    ?AddRef@A2DP_Device@@QEAAXFPEBD@Z; A2DP_Device::AddRef(short,char const *)
0x14002ed0b  lea     rcx, [rdi+2B8h]; SpinLock
0x14002ed12  call    cs:__imp_KeInitializeSpinLock
0x14002ed19  nop     dword ptr [rax+rax+00h]
0x14002ed1e  lea     rcx, [rdi+0BC8h]; Timer
0x14002ed25  call    cs:__imp_KeInitializeTimer
0x14002ed2c  nop     dword ptr [rax+rax+00h]
0x14002ed31  lea     rcx, [rdi+0C08h]; Dpc
0x14002ed38  mov     r8, rdi; DeferredContext
0x14002ed3b  lea     rdx, ?DiscoveryTimerDpc@A2DP_Device@@CAXPEAU_KDPC@@PEAX11@Z; DeferredRoutine
0x14002ed42  call    cs:__imp_KeInitializeDpc
0x14002ed49  nop     dword ptr [rax+rax+00h]
0x14002ed4e  lea     rcx, [rdi+0C50h]; Timer
0x14002ed55  call    cs:__imp_KeInitializeTimer
0x14002ed5c  nop     dword ptr [rax+rax+00h]
0x14002ed61  lea     rcx, [rdi+0C90h]; Dpc
0x14002ed68  mov     r8, rdi; DeferredContext
0x14002ed6b  lea     rdx, ?ServiceReadyTimerDpc@A2DP_Device@@CAXPEAU_KDPC@@PEAX11@Z; DeferredRoutine
0x14002ed72  call    cs:__imp_KeInitializeDpc
0x14002ed79  nop     dword ptr [rax+rax+00h]
0x14002ed7e  lea     rcx, [rdi+338h]; Lock
0x14002ed85  mov     [rsp+88h+RemlockSize], 20h ; ' '; RemlockSize
0x14002ed8d  xor     r9d, r9d; HighWatermark
0x14002ed90  xor     r8d, r8d; MaxLockedMinutes
0x14002ed93  mov     edx, 50444141h; AllocateTag
0x14002ed98  call    cs:__imp_IoInitializeRemoveLockEx
0x14002ed9f  nop     dword ptr [rax+rax+00h]
0x14002eda4  mov     [rdi+170h], rsi
0x14002edab  lea     rcx, [rdi+2E8h]; Event
0x14002edb2  mov     rax, [rsi+28h]
0x14002edb6  xor     r8d, r8d; State
0x14002edb9  mov     [rdi+178h], rax
0x14002edc0  xor     edx, edx; Type
0x14002edc2  mov     rax, [rsi+18h]
0x14002edc6  mov     [rdi+180h], rax
0x14002edcd  mov     [rdi+0CD0h], rbp
0x14002edd4  call    cs:__imp_KeInitializeEvent
0x14002eddb  nop     dword ptr [rax+rax+00h]
0x14002ede0  lea     rcx, [rdi+300h]; Event
0x14002ede7  xor     r8d, r8d; State
0x14002edea  xor     edx, edx; Type
0x14002edec  call    cs:__imp_KeInitializeEvent
0x14002edf3  nop     dword ptr [rax+rax+00h]
0x14002edf8  lea     rcx, [rdi+318h]; Event
0x14002edff  xor     r8d, r8d; State
0x14002ee02  xor     edx, edx; Type
0x14002ee04  call    cs:__imp_KeInitializeEvent
0x14002ee0b  nop     dword ptr [rax+rax+00h]
0x14002ee10  mov     rcx, rdi; DeferredContext
0x14002ee13  mov     [rdi+330h], bp
0x14002ee1a  mov     [rdi+332h], bpl
0x14002ee21  call    ?InitializeStreamingState@A2DP_Device@@AEAAXXZ; A2DP_Device::InitializeStreamingState(void)
0x14002ee26  lea     rcx, [rdi+20h]; this
0x14002ee2a  mov     [rdi+188h], r15d
0x14002ee31  call    ?Initialize@IrpQueue@@QEAAXXZ; IrpQueue::Initialize(void)
0x14002ee36  lea     rcx, [rdi+78h]; this
0x14002ee3a  call    ?Initialize@IrpQueue@@QEAAXXZ; IrpQueue::Initialize(void)
0x14002ee3f  mov     [r14], ebp
0x14002ee42  lea     rsi, DriverParametersRegistryPathName
0x14002ee49  mov     r14d, 64h ; 'd'
0x14002ee4f  lea     rdx, aLevelincrement; "LevelIncrement"
0x14002ee56  mov     rcx, rsi
0x14002ee59  mov     [rdi+0CDCh], r14d
0x14002ee60  mov     r8d, r15d
0x14002ee63  call    QueryRegistryDWord
0x14002ee68  cmp     eax, r14d
0x14002ee6b  jnb     short loc_14002EE77
0x14002ee6d  cmp     eax, r15d
0x14002ee70  ja      short loc_14002EE7A
0x14002ee72  mov     eax, r15d
0x14002ee75  jmp     short loc_14002EE7A
0x14002ee77  mov     eax, r14d
0x14002ee7a  mov     ebx, [rdi+0CDCh]
0x14002ee80  lea     rdx, aLeveldecrement; "LevelDecrement"
0x14002ee87  mov     r8d, r15d
0x14002ee8a  mov     [rdi+0CE0h], eax
0x14002ee90  mov     rcx, rsi
0x14002ee93  call    QueryRegistryDWord
0x14002ee98  cmp     eax, ebx
0x14002ee9a  mov     ecx, ebx
0x14002ee9c  cmovb   ecx, eax
0x14002ee9f  cmp     ecx, r15d
0x14002eea2  jbe     short loc_14002EEAB
0x14002eea4  cmp     eax, ebx
0x14002eea6  cmovb   ebx, eax
0x14002eea9  jmp     short loc_14002EEAE
0x14002eeab  mov     ebx, r15d
0x14002eeae  mov     r8d, r15d
0x14002eeb1  mov     [rdi+0CE4h], ebx
0x14002eeb7  lea     rdx, aBackoffdecreme; "BackoffDecrement"
0x14002eebe  mov     [rdi+0CE8h], ebp
0x14002eec4  mov     rcx, rsi
0x14002eec7  mov     [rdi+0CECh], r14d
0x14002eece  call    QueryRegistryDWord
0x14002eed3  cmp     eax, r14d
0x14002eed6  jnb     short loc_14002EEE2
0x14002eed8  cmp     eax, r15d
0x14002eedb  ja      short loc_14002EEE5
0x14002eedd  mov     eax, r15d
0x14002eee0  jmp     short loc_14002EEE5
0x14002eee2  mov     eax, r14d
0x14002eee5  mov     ebx, [rdi+0CECh]
0x14002eeeb  lea     rdx, aBackofffloorin; "BackoffFloorIncrement"
0x14002eef2  mov     r8d, r15d
0x14002eef5  mov     [rdi+0CF8h], ebx
0x14002eefb  mov     rcx, rsi
0x14002eefe  mov     [rdi+0CF0h], eax
0x14002ef04  mov     [rdi+0CF4h], ebp
0x14002ef0a  call    QueryRegistryDWord
0x14002ef0f  cmp     eax, ebx
0x14002ef11  mov     ecx, ebx
0x14002ef13  cmovb   ecx, eax
0x14002ef16  cmp     ecx, r15d
0x14002ef19  jbe     short loc_14002EF22
0x14002ef1b  cmp     eax, ebx
0x14002ef1d  cmovb   ebx, eax
0x14002ef20  jmp     short loc_14002EF25
0x14002ef22  mov     ebx, r15d
0x14002ef25  mov     [rdi+0CFCh], ebx
0x14002ef2b  lea     rdx, aBackofffloorde; "BackoffFloorDecrement"
0x14002ef32  mov     ebx, [rdi+0CF8h]
0x14002ef38  mov     r8d, r15d
0x14002ef3b  mov     rcx, rsi
0x14002ef3e  call    QueryRegistryDWord
0x14002ef43  cmp     eax, ebx
0x14002ef45  mov     ecx, ebx
0x14002ef47  cmovb   ecx, eax
0x14002ef4a  cmp     ecx, r15d
0x14002ef4d  jbe     short loc_14002EF56
0x14002ef4f  cmp     eax, ebx
0x14002ef51  cmovb   ebx, eax
0x14002ef54  jmp     short loc_14002EF59
0x14002ef56  mov     ebx, r15d
0x14002ef59  mov     [rdi+0D00h], ebx
0x14002ef5f  lea     rdx, aStabilityincre; "StabilityIncrement"
0x14002ef66  mov     ebx, 3E8h
0x14002ef6b  mov     [rdi+0D04h], ebp
0x14002ef71  mov     r8d, 0Ah
0x14002ef77  mov     [rdi+0D08h], ebx
0x14002ef7d  mov     rcx, rsi
0x14002ef80  call    QueryRegistryDWord
0x14002ef85  cmp     eax, ebx
0x14002ef87  jnb     short loc_14002EF93
0x14002ef89  cmp     eax, r15d
0x14002ef8c  ja      short loc_14002EF95
0x14002ef8e  mov     eax, r15d
0x14002ef91  jmp     short loc_14002EF95
0x14002ef93  mov     eax, ebx
0x14002ef95  mov     r8d, r15d
0x14002ef98  mov     [rdi+0D0Ch], eax
0x14002ef9e  lea     rdx, aCongestionback; "CongestionBackoffEnabled"
0x14002efa5  mov     rcx, rsi
0x14002efa8  call    QueryRegistryDWord
0x14002efad  test    eax, eax
0x14002efaf  lea     rdx, aCongestiontest; "CongestionTestMode"
0x14002efb6  mov     rcx, rsi
0x14002efb9  setnz   al
0x14002efbc  xor     r8d, r8d
0x14002efbf  mov     [rdi+0D18h], al
0x14002efc5  call    QueryRegistryDWord
0x14002efca  test    eax, eax
0x14002efcc  setnz   al
0x14002efcf  mov     [rdi+0D19h], al
0x14002efd5  mov     rax, rdi
0x14002efd8  add     rsp, 58h
0x14002efdc  pop     r15
0x14002efde  pop     r14
0x14002efe0  pop     rdi
0x14002efe1  pop     rsi
0x14002efe2  pop     rbp
0x14002efe3  pop     rbx
0x14002efe4  retn
```
