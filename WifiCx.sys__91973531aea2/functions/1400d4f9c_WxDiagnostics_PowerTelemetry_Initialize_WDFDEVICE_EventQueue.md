# WxDiagnostics::PowerTelemetry::Initialize(WDFDEVICE__ *,EventQueue *)

- ea: `0x1400d4f9c`
- end: `0x1400d50a2`
- name: `?Initialize@PowerTelemetry@WxDiagnostics@@QEAAXPEAUWDFDEVICE__@@PEAVEventQueue@@@Z`
- size: `262`
- prototype: `void __fastcall(WxDiagnostics::PowerTelemetry *__hidden this, struct WDFDEVICE__ *, struct EventQueue *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1400cee44`

## callees

- `0x14000c778`
- `0x14002ed50`
- `0x14004be04`
- `0x14004c1d8`
- `0x1400d4e70`
- `0x1400d4f9c`
- `0x1400d8614`

## import_xrefs

- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperCreateLibrary` at `0x1400d501a`
- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperCreateLibrary` at `0x1400d501a`

## pseudocode

```c
void __fastcall WxDiagnostics::PowerTelemetry::Initialize(
        WxDiagnostics::PowerTelemetry *this,
        struct WDFDEVICE__ *a2,
        struct EventQueue *a3)
{
  bool *v6; // rdx
  struct ILowPowerConnectedStandbyScenarioChangeCallback *v7; // r8
  int Library; // eax
  int v9; // edx
  int v10; // r9d
  char v11; // [rsp+40h] [rbp+8h] BYREF

  McGenEventRegister_EtwRegister();
  *((_QWORD *)this + 75) = a2;
  *((_QWORD *)this + 79) = a3;
  WxDiagnostics::PowerTelemetry::InitDeviceInstanceInfo(this, a2);
  v11 = 0;
  wificx::utils::power::IsAoAcPlatform((wificx::utils::power *)&v11, v6);
  if ( v11 )
  {
    Library = wificx::utils::power::SubscribeWnfPoScenarioChange(
                (WxDiagnostics::PowerTelemetry *)((char *)this + 16),
                (void **)(((unsigned __int64)this + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
                v7);
    if ( Library < 0 )
    {
      *((_QWORD *)this + 2) = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v10 = 15;
        goto LABEL_8;
      }
    }
    else
    {
      Library = SleepstudyHelperCreateLibrary(2017880407, (char *)this + 608);
      if ( Library < 0 )
      {
        *((_QWORD *)this + 76) = 0;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v10 = 14;
LABEL_8:
          LOBYTE(v9) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v9,
            1,
            v10,
            (__int64)WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids,
            Library);
        }
      }
    }
  }
  *((_QWORD *)this + 82) = CSystem::get_CurrentTime();
}

```

## disassembly

```asm
0x1400d4f9c  mov     [rsp+arg_8], rbx
0x1400d4fa1  mov     [rsp+arg_10], rsi
0x1400d4fa6  push    rdi
0x1400d4fa7  sub     rsp, 30h
0x1400d4fab  mov     rbx, r8
0x1400d4fae  mov     rdi, rdx
0x1400d4fb1  mov     rsi, rcx
0x1400d4fb4  call    McGenEventRegister_EtwRegister
0x1400d4fb9  mov     rdx, rdi; struct WDFDEVICE__ *
0x1400d4fbc  mov     [rsi+258h], rdi
0x1400d4fc3  mov     rcx, rsi; this
0x1400d4fc6  mov     [rsi+278h], rbx
0x1400d4fcd  call    ?InitDeviceInstanceInfo@PowerTelemetry@WxDiagnostics@@AEAAXPEAUWDFDEVICE__@@@Z; WxDiagnostics::PowerTelemetry::InitDeviceInstanceInfo(WDFDEVICE__ *)
0x1400d4fd2  xor     edi, edi
0x1400d4fd4  lea     rcx, [rsp+38h+arg_0]; this
0x1400d4fd9  mov     [rsp+38h+arg_0], dil
0x1400d4fde  call    ?IsAoAcPlatform@power@utils@wificx@@YAJPEA_N@Z; wificx::utils::power::IsAoAcPlatform(bool *)
0x1400d4fe3  cmp     [rsp+38h+arg_0], dil
0x1400d4fe8  jz      loc_1400D5085
0x1400d4fee  lea     rcx, [rsi+8]
0x1400d4ff2  mov     rax, rsi
0x1400d4ff5  neg     rax
0x1400d4ff8  sbb     rdx, rdx
0x1400d4ffb  and     rdx, rcx; void **
0x1400d4ffe  lea     rcx, [rsi+10h]; this
0x1400d5002  call    ?SubscribeWnfPoScenarioChange@power@utils@wificx@@YAJPEAPEAXPEAVILowPowerConnectedStandbyScenarioChangeCallback@@@Z; wificx::utils::power::SubscribeWnfPoScenarioChange(void * *,ILowPowerConnectedStandbyScenarioChangeCallback *)
0x1400d5007  test    eax, eax
0x1400d5009  js      short loc_1400D5043
0x1400d500b  lea     rbx, [rsi+260h]
0x1400d5012  mov     ecx, 78466957h
0x1400d5017  mov     rdx, rbx
0x1400d501a  call    cs:__imp_SleepstudyHelperCreateLibrary
0x1400d5021  nop     dword ptr [rax+rax+00h]
0x1400d5026  test    eax, eax
0x1400d5028  jns     short loc_1400D5085
0x1400d502a  mov     [rbx], rdi
0x1400d502d  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400d5034  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400d503b  jz      short loc_1400D5085
0x1400d503d  lea     r9d, [rdi+0Eh]
0x1400d5041  jmp     short loc_1400D505D
0x1400d5043  mov     [rsi+10h], rdi
0x1400d5047  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400d504e  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400d5055  jz      short loc_1400D5085
0x1400d5057  mov     r9d, 0Fh
0x1400d505d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d5064  mov     r8d, 1
0x1400d506a  mov     [rsp+38h+var_10], eax
0x1400d506e  mov     dl, 2
0x1400d5070  lea     rax, WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids
0x1400d5077  mov     [rsp+38h+var_18], rax
0x1400d507c  mov     rcx, [rcx+40h]
0x1400d5080  call    WPP_RECORDER_SF_d
0x1400d5085  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x1400d508a  mov     rbx, [rsp+38h+arg_8]
0x1400d508f  mov     [rsi+290h], rax
0x1400d5096  mov     rsi, [rsp+38h+arg_10]
0x1400d509b  add     rsp, 30h
0x1400d509f  pop     rdi
0x1400d50a0  retn
```
