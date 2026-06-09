# OobeEasyConnectTask::AttemptEnableDownloadedProfile(wil::write_lock_required)

- ea: `0x180048440`
- end: `0x18004859e`
- name: `?AttemptEnableDownloadedProfile@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z`
- size: `350`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800215a0`
- `0x180022800`
- `0x1800482b4`

## callees

- `0x180008c84`
- `0x18000ad20`
- `0x18000bde0`
- `0x18001a1b8`
- `0x180022c1c`
- `0x180048440`
- `0x180059010`

## string_xrefs

- `0x1800484d1`: `Esim Service is not idle, wait`
- `0x18004845f`: `OobeEasyConnectTask::AttemptEnableDownloadedProfile`
- `0x18004850b`: `OobeEasyConnectTask::AttemptEnableDownloadedProfile`
- `0x18004854d`: `OobeEasyConnectTask::AttemptEnableDownloadedProfile`
- `0x180048578`: `OobeEasyConnectTask::AttemptEnableDownloadedProfile`
- `0x18004856c`: `There were no profiles downloaded, nothing to enable. Change state to Complete`
- `0x18004855b`: `Downloading profile does not match last downloaded profile. Wait for ESimSettingOperationInstallProfile`
- `0x180048516`: `Called SetProfileEnablement. Changing state to Complete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
void __fastcall OobeEasyConnectTask::AttemptEnableDownloadedProfile(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  _QWORD *v6; // rcx
  _QWORD *v7; // r8
  int v8; // eax

  if ( *(_DWORD *)(a1 + 96) == 4 )
  {
    v4 = (_QWORD *)(a1 + 232);
    if ( *(_QWORD *)(a1 + 1176) || *v4 )
    {
      v5 = (_QWORD *)(a1 + 1160);
      if ( *v4 )
      {
        v6 = (_QWORD *)(a1 + 216);
        if ( v5[3] <= 7u )
          v7 = v5;
        else
          v7 = (_QWORD *)*v5;
        if ( v6[3] > 7u )
          v6 = (_QWORD *)*v6;
        if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v6, *v4, v7) )
        {
          MBSettingUXLogging::Info(
            "OobeEasyConnectTask::AttemptEnableDownloadedProfile",
            0x339u,
            "Downloading profile does not match last downloaded profile. Wait for ESimSettingOperationInstallProfile");
          return;
        }
      }
      if ( *(_DWORD *)(a1 + 164) != 1 )
      {
        MBSettingUXLogging::Info(
          "OobeEasyConnectTask::AttemptEnableDownloadedProfile",
          0x33Fu,
          "Esim Service is not idle, wait");
        return;
      }
      if ( *(_DWORD *)(a1 + 160) <= 1u )
      {
        MBSettingUXLogging::Warn(
          "OobeEasyConnectTask::AttemptEnableDownloadedProfile",
          0x346u,
          "If at this point, there is no eSim present or esimState is unknown, set m_state to error");
      }
      else
      {
        if ( v5[3] > 7u )
          v5 = (_QWORD *)*v5;
        LOBYTE(a3) = 1;
        v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64, _QWORD))(**(_QWORD **)(a1 + 72) + 88LL))(
               *(_QWORD *)(a1 + 72),
               v5,
               a3,
               0);
        if ( v8 >= 0 )
        {
          MBSettingUXLogging::Info(
            "OobeEasyConnectTask::AttemptEnableDownloadedProfile",
            0x350u,
            "Called SetProfileEnablement. Changing state to Complete");
LABEL_25:
          *(_DWORD *)(a1 + 96) = 5;
          goto LABEL_26;
        }
        MBSettingUXLogging::Error(
          "OobeEasyConnectTask::AttemptEnableDownloadedProfile",
          0x356u,
          "SetProfileEnablement failed with hr=0x%08x. Changing state to Error",
          v8);
      }
      *(_DWORD *)(a1 + 96) = 7;
LABEL_26:
      OobeEasyConnectTask::PublishCurrentTaskStateWnf(a1);
      return;
    }
    MBSettingUXLogging::Info(
      "OobeEasyConnectTask::AttemptEnableDownloadedProfile",
      0x332u,
      "There were no profiles downloaded, nothing to enable. Change state to Complete");
    goto LABEL_25;
  }
  MBSettingUXLogging::Info("OobeEasyConnectTask::AttemptEnableDownloadedProfile", 0x32Cu, "Not in the correct state");
}

```

## disassembly

```asm
0x180048440  mov     [rsp+arg_0], rbx
0x180048445  push    rdi
0x180048446  sub     rsp, 30h
0x18004844a  cmp     dword ptr [rcx+60h], 4
0x18004844e  mov     rbx, rcx
0x180048451  jz      short loc_180048470
0x180048453  lea     r8, aNotInTheCorrec; "Not in the correct state"
0x18004845a  mov     edx, 32Ch; unsigned int
0x18004845f  lea     rcx, aOobeeasyconnec_3; "OobeEasyConnectTask::AttemptEnableDownl"...
0x180048466  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18004846b  jmp     loc_180048593
0x180048470  mov     r9, [rcx+498h]
0x180048477  lea     rax, [rcx+0E8h]
0x18004847e  test    r9, r9
0x180048481  jnz     short loc_18004848C
0x180048483  cmp     [rax], r9
0x180048486  jz      loc_18004856C
0x18004848c  mov     rdx, [rax]
0x18004848f  lea     rdi, [rcx+488h]
0x180048496  test    rdx, rdx
0x180048499  jz      short loc_1800484C8
0x18004849b  add     rcx, 0D8h
0x1800484a2  cmp     qword ptr [rdi+18h], 7
0x1800484a7  jbe     short loc_1800484AE
0x1800484a9  mov     r8, [rdi]
0x1800484ac  jmp     short loc_1800484B1
0x1800484ae  mov     r8, rdi
0x1800484b1  cmp     qword ptr [rcx+18h], 7
0x1800484b6  jbe     short loc_1800484BB
0x1800484b8  mov     rcx, [rcx]
0x1800484bb  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800484c0  test    al, al
0x1800484c2  jz      loc_18004855B
0x1800484c8  cmp     dword ptr [rbx+0A4h], 1
0x1800484cf  jz      short loc_1800484DF
0x1800484d1  lea     r8, aEsimServiceIsN_0; "Esim Service is not idle, wait"
0x1800484d8  mov     edx, 33Fh
0x1800484dd  jmp     short loc_18004845F
0x1800484df  cmp     dword ptr [rbx+0A0h], 1
0x1800484e6  jbe     short loc_180048541
0x1800484e8  cmp     qword ptr [rdi+18h], 7
0x1800484ed  mov     rcx, [rbx+48h]
0x1800484f1  mov     rax, [rcx]
0x1800484f4  jbe     short loc_1800484F9
0x1800484f6  mov     rdi, [rdi]
0x1800484f9  mov     rax, [rax+58h]
0x1800484fd  xor     r9d, r9d
0x180048500  mov     r8b, 1
0x180048503  mov     rdx, rdi
0x180048506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004850b  lea     rcx, aOobeeasyconnec_3; "OobeEasyConnectTask::AttemptEnableDownl"...
0x180048512  test    eax, eax
0x180048514  js      short loc_180048524
0x180048516  lea     r8, aCalledSetprofi; "Called SetProfileEnablement. Changing s"...
0x18004851d  mov     edx, 350h
0x180048522  jmp     short loc_18004857F
0x180048524  mov     r9d, eax
0x180048527  lea     r8, aSetprofileenab; "SetProfileEnablement failed with hr=0x%"...
0x18004852e  mov     edx, 356h; unsigned int
0x180048533  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x180048538  mov     dword ptr [rbx+60h], 7
0x18004853f  jmp     short loc_18004858B
0x180048541  lea     r8, aIfAtThisPointT; "If at this point, there is no eSim pres"...
0x180048548  mov     edx, 346h; unsigned int
0x18004854d  lea     rcx, aOobeeasyconnec_3; "OobeEasyConnectTask::AttemptEnableDownl"...
0x180048554  call    ?Warn@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Warn(char const *,ulong,char const *,...)
0x180048559  jmp     short loc_180048538
0x18004855b  lea     r8, aDownloadingPro; "Downloading profile does not match last"...
0x180048562  mov     edx, 339h
0x180048567  jmp     loc_18004845F
0x18004856c  lea     r8, aThereWereNoPro_0; "There were no profiles downloaded, noth"...
0x180048573  mov     edx, 332h; unsigned int
0x180048578  lea     rcx, aOobeeasyconnec_3; "OobeEasyConnectTask::AttemptEnableDownl"...
0x18004857f  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180048584  mov     dword ptr [rbx+60h], 5
0x18004858b  mov     rcx, rbx
0x18004858e  call    ?PublishCurrentTaskStateWnf@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::PublishCurrentTaskStateWnf(wil::write_lock_required)
0x180048593  mov     rbx, [rsp+38h+arg_0]
0x180048598  add     rsp, 30h
0x18004859c  pop     rdi
0x18004859d  retn
```
