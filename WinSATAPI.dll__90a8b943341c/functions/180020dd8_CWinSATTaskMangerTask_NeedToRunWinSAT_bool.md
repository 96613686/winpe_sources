# CWinSATTaskMangerTask::NeedToRunWinSAT(bool &)

- ea: `0x180020dd8`
- end: `0x180020f33`
- name: `?NeedToRunWinSAT@CWinSATTaskMangerTask@@AEAAJAEA_N@Z`
- size: `347`
- prototype: `__int64 __fastcall(CWinSATTaskMangerTask *this, bool *, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800213a4`

## callees

- `0x180002690`
- `0x18000f0e8`
- `0x1800100a0`
- `0x180020dd8`
- `0x18002fb50`
- `0x180033010`

## string_xrefs

- `0x180020e50`: `base\winsat\api-dll\winsattaskmangertask.cpp`
- `0x180020ed6`: `base\winsat\api-dll\winsattaskmangertask.cpp`
- `0x180020ef3`: `base\winsat\api-dll\winsattaskmangertask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWinSATTaskMangerTask::NeedToRunWinSAT(
        CWinSATTaskMangerTask *this,
        bool *a2,
        struct IXMLDOMDocument2 **a3)
{
  int State; // ebx
  void (__fastcall *v6)(void *, __int64, _QWORD); // rax
  enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 v7; // ebx
  __int32 v8; // ebx
  __int32 v9; // ebx
  __int32 v10; // ebx
  enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 v12; // [rsp+20h] [rbp-1C8h] BYREF
  __int64 v13; // [rsp+28h] [rbp-1C0h]
  char v14[8]; // [rsp+30h] [rbp-1B8h] BYREF
  __int64 v15; // [rsp+38h] [rbp-1B0h]
  __int128 v16; // [rsp+40h] [rbp-1A8h]
  __int64 v17; // [rsp+68h] [rbp-180h]
  __int128 v18; // [rsp+70h] [rbp-178h]

  v13 = -2;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v12 = WINSAT_ASSESSMENT_STATE_MIN;
  State = DataStoreReader::LoadMostRecentResultsAndGetState((struct WinSATData *)v14, &v12, a3);
  if ( State >= 0 )
  {
    *a2 = 1;
    v6 = (void (__fastcall *)(void *, __int64, _QWORD))*((_QWORD *)this + 17);
    v7 = v12;
    if ( v6 )
      v6(&unk_18004A8B0, 10266, (unsigned int)v12);
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            if ( v10 == 1 )
              Log_Text_F((__int64)"base\\winsat\\api-dll\\winsattaskmangertask.cpp", 134, "assessment state is invalid");
          }
          else
          {
            Log_Text_F(
              (__int64)"base\\winsat\\api-dll\\winsattaskmangertask.cpp",
              131,
              "assessment state is not avaialable");
          }
        }
        else
        {
          Log_Text_F(
            (__int64)"base\\winsat\\api-dll\\winsattaskmangertask.cpp",
            128,
            "assessment state is incoherent with the hardware");
        }
      }
      else
      {
        Log_Text_F(
          (__int64)"base\\winsat\\api-dll\\winsattaskmangertask.cpp",
          138,
          "assessment state is valid - no need to run winsat");
        *a2 = 0;
      }
    }
    else
    {
      Log_Text_F((__int64)"base\\winsat\\api-dll\\winsattaskmangertask.cpp", 125, "assessment state is unknown");
    }
    State = 0;
  }
  else
  {
    Log_Text_F((__int64)"base\\winsat\\api-dll\\winsattaskmangertask.cpp", 110, "failed to obtain winast result status");
  }
  WinSATCriticalHardwareInfo::~WinSATCriticalHardwareInfo((WinSATCriticalHardwareInfo *)v14);
  return (unsigned int)State;
}

```

## disassembly

```asm
0x180020dd8  mov     rax, rsp
0x180020ddb  push    rdi
0x180020ddc  sub     rsp, 1E0h
0x180020de3  mov     [rsp+1E8h+var_1C0], 0FFFFFFFFFFFFFFFEh
0x180020dec  mov     [rax+18h], rbx
0x180020df0  mov     [rax+20h], rsi
0x180020df4  mov     rax, cs:__security_cookie
0x180020dfb  xor     rax, rsp
0x180020dfe  mov     [rsp+1E8h+var_18], rax
0x180020e06  mov     rdi, rdx
0x180020e09  mov     rsi, rcx
0x180020e0c  and     [rsp+1E8h+var_1B0], 0
0x180020e12  xorps   xmm0, xmm0
0x180020e15  movdqa  [rsp+1E8h+var_1A8], xmm0
0x180020e1b  and     [rsp+1E8h+var_180], 0
0x180020e21  xorps   xmm1, xmm1
0x180020e24  movdqa  [rsp+1E8h+var_178], xmm1
0x180020e2a  and     [rsp+1E8h+var_1C8], 0
0x180020e2f  lea     rdx, [rsp+1E8h+var_1C8]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *
0x180020e34  lea     rcx, [rsp+1E8h+var_1B8]; struct WinSATData *
0x180020e39  call    ?LoadMostRecentResultsAndGetState@DataStoreReader@@SAJAEAUWinSATData@@AEAW4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@_N@Z; DataStoreReader::LoadMostRecentResultsAndGetState(WinSATData &,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 &,bool)
0x180020e3e  mov     ebx, eax
0x180020e40  test    eax, eax
0x180020e42  jns     short loc_180020E61
0x180020e44  lea     r8, aFailedToObtain; "failed to obtain winast result status"
0x180020e4b  mov     edx, 6Eh ; 'n'
0x180020e50  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180020e57  call    Log_Text_F
0x180020e5c  jmp     loc_180020F01
0x180020e61  mov     byte ptr [rdi], 1
0x180020e64  mov     rax, [rsi+88h]
0x180020e6b  mov     ebx, [rsp+1E8h+var_1C8]
0x180020e6f  test    rax, rax
0x180020e72  jz      short loc_180020E88
0x180020e74  mov     r8d, ebx
0x180020e77  mov     edx, 281Ah
0x180020e7c  lea     rcx, unk_18004A8B0
0x180020e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e88  test    ebx, ebx
0x180020e8a  jz      short loc_180020EE7
0x180020e8c  sub     ebx, 1
0x180020e8f  jz      short loc_180020ECA
0x180020e91  sub     ebx, 1
0x180020e94  jz      short loc_180020EBC
0x180020e96  sub     ebx, 1
0x180020e99  jz      short loc_180020EAE
0x180020e9b  cmp     ebx, 1
0x180020e9e  jnz     short loc_180020EFF
0x180020ea0  lea     r8, aAssessmentStat; "assessment state is invalid"
0x180020ea7  mov     edx, 86h
0x180020eac  jmp     short loc_180020EF3
0x180020eae  lea     r8, aAssessmentStat_1; "assessment state is not avaialable"
0x180020eb5  mov     edx, 83h
0x180020eba  jmp     short loc_180020EF3
0x180020ebc  lea     r8, aAssessmentStat_2; "assessment state is incoherent with the"...
0x180020ec3  mov     edx, 80h
0x180020ec8  jmp     short loc_180020EF3
0x180020eca  lea     r8, aAssessmentStat_0; "assessment state is valid - no need to "...
0x180020ed1  mov     edx, 8Ah
0x180020ed6  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180020edd  call    Log_Text_F
0x180020ee2  mov     byte ptr [rdi], 0
0x180020ee5  jmp     short loc_180020EFF
0x180020ee7  lea     r8, aAssessmentStat_3; "assessment state is unknown"
0x180020eee  mov     edx, 7Dh ; '}'
0x180020ef3  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180020efa  call    Log_Text_F
0x180020eff  xor     ebx, ebx
0x180020f01  lea     rcx, [rsp+1E8h+var_1B8]; this
0x180020f06  call    ??1WinSATCriticalHardwareInfo@@QEAA@XZ; WinSATCriticalHardwareInfo::~WinSATCriticalHardwareInfo(void)
0x180020f0b  mov     eax, ebx
0x180020f0d  mov     rcx, [rsp+1E8h+var_18]
0x180020f15  xor     rcx, rsp; StackCookie
0x180020f18  call    __security_check_cookie
0x180020f1d  lea     r11, [rsp+1E8h+var_8]
0x180020f25  mov     rbx, [r11+20h]
0x180020f29  mov     rsi, [r11+28h]
0x180020f2d  mov     rsp, r11
0x180020f30  pop     rdi
0x180020f31  retn
```
