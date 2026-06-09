# OobeEasyConnectTask::AttemptDeleteBootstrapProfile(wil::write_lock_required)

- ea: `0x1800482b4`
- end: `0x18004843a`
- name: `?AttemptDeleteBootstrapProfile@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z`
- size: `390`
- prototype: `void __fastcall(__int64, char)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800215a0`
- `0x180022800`
- `0x180049e90`

## callees

- `0x180008c84`
- `0x18000ad20`
- `0x180022c1c`
- `0x1800482b4`
- `0x180048440`
- `0x1800485a4`
- `0x180059010`

## string_xrefs

- `0x1800482da`: `OobeEasyConnectTask::AttemptDeleteBootstrapProfile`
- `0x180048325`: `OobeEasyConnectTask::AttemptDeleteBootstrapProfile`
- `0x18004838c`: `OobeEasyConnectTask::AttemptDeleteBootstrapProfile`
- `0x1800483e1`: `OobeEasyConnectTask::AttemptDeleteBootstrapProfile`
- `0x180048405`: `OobeEasyConnectTask::AttemptDeleteBootstrapProfile`
- `0x1800483f9`: `There is no bootstrap profile, move m_state to WaitingForCorrectStateForProfileEnable`
- `0x180048319`: `There were no profiles downloaded and OOBE is not complete, do NOT delete bootstrap profile, m_state is now Complete`
- `0x18004834e`: `Esim Service is not idle, wait`
- `0x180048399`: `Delete profile called, changing m_state to WaitingForCorrectStateForProfileEnable`
- `0x1800483aa`: `DeleteProfile failed with hr=0x%08x, changing m_state to Error`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall OobeEasyConnectTask::AttemptDeleteBootstrapProfile(__int64 a1, char a2)
{
  __int64 v4; // rcx
  _QWORD *v5; // rdx
  int v6; // eax
  int v7; // esi
  __int64 v8; // rdx
  __int64 v9; // r8

  if ( *(_DWORD *)(a1 + 96) == 3 )
  {
    if ( *(_QWORD *)(a1 + 192) && *(_BYTE *)(a1 + 168) )
    {
      if ( !*(_QWORD *)(a1 + 1176) && !*(_BYTE *)(a1 + 128) )
      {
        MBSettingUXLogging::Info(
          "OobeEasyConnectTask::AttemptDeleteBootstrapProfile",
          0x301u,
          "There were no profiles downloaded and OOBE is not complete, do NOT delete bootstrap profile, m_state is now Complete");
        *(_DWORD *)(a1 + 96) = 5;
LABEL_9:
        OobeEasyConnectTask::PublishCurrentTaskStateWnf(a1);
        return;
      }
      if ( *(_DWORD *)(a1 + 164) != 1 )
      {
        MBSettingUXLogging::Info(
          "OobeEasyConnectTask::AttemptDeleteBootstrapProfile",
          0x308u,
          "Esim Service is not idle, wait");
        return;
      }
      if ( *(_DWORD *)(a1 + 160) <= 1u )
      {
        MBSettingUXLogging::Info(
          "OobeEasyConnectTask::AttemptDeleteBootstrapProfile",
          0x30Eu,
          "If at this point, there is no eSim present or esimState is unknown, set m_state to error");
        *(_DWORD *)(a1 + 96) = 7;
        goto LABEL_9;
      }
      v4 = *(_QWORD *)(a1 + 72);
      v5 = (_QWORD *)(a1 + 176);
      if ( *(_QWORD *)(a1 + 200) > 7u )
        v5 = (_QWORD *)*v5;
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)v4 + 56LL))(v4, v5, 0);
      v7 = v6;
      if ( v6 < 0 )
      {
        MBSettingUXLogging::Error(
          "OobeEasyConnectTask::AttemptDeleteBootstrapProfile",
          0x320u,
          "DeleteProfile failed with hr=0x%08x, changing m_state to Error",
          v6);
        *(_DWORD *)(a1 + 96) = 7;
        OobeEasyConnectTask::PublishCurrentTaskStateWnf(a1);
        MBSettingUXLogging::BootstrapProfileDeletion(v7, 0);
        return;
      }
      MBSettingUXLogging::Info(
        "OobeEasyConnectTask::AttemptDeleteBootstrapProfile",
        0x317u,
        "Delete profile called, changing m_state to WaitingForCorrectStateForProfileEnable");
    }
    else
    {
      MBSettingUXLogging::Info(
        "OobeEasyConnectTask::AttemptDeleteBootstrapProfile",
        0x2F9u,
        "There is no bootstrap profile, move m_state to WaitingForCorrectStateForProfileEnable");
    }
    *(_DWORD *)(a1 + 96) = 4;
    OobeEasyConnectTask::PublishCurrentTaskStateWnf(a1);
    LOBYTE(v8) = a2;
    OobeEasyConnectTask::AttemptEnableDownloadedProfile(a1, v8, v9);
    return;
  }
  MBSettingUXLogging::Info("OobeEasyConnectTask::AttemptDeleteBootstrapProfile", 0x2F3u, "Not in the correct state");
}

```

## disassembly

```asm
0x1800482b4  mov     [rsp+arg_0], rbx
0x1800482b9  mov     [rsp+arg_8], rsi
0x1800482be  push    rdi
0x1800482bf  sub     rsp, 20h
0x1800482c3  cmp     dword ptr [rcx+60h], 3
0x1800482c7  mov     bl, dl
0x1800482c9  mov     rdi, rcx
0x1800482cc  jz      short loc_1800482EB
0x1800482ce  lea     r8, aNotInTheCorrec; "Not in the correct state"
0x1800482d5  mov     edx, 2F3h; unsigned int
0x1800482da  lea     rcx, aOobeeasyconnec_18; "OobeEasyConnectTask::AttemptDeleteBoots"...
0x1800482e1  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800482e6  jmp     loc_18004842A
0x1800482eb  cmp     qword ptr [rcx+0C0h], 0
0x1800482f3  jz      loc_1800483F9
0x1800482f9  cmp     byte ptr [rcx+0A8h], 0
0x180048300  jz      loc_1800483F9
0x180048306  cmp     qword ptr [rcx+498h], 0
0x18004830e  jnz     short loc_180048345
0x180048310  cmp     byte ptr [rcx+80h], 0
0x180048317  jnz     short loc_180048345
0x180048319  lea     r8, aThereWereNoPro; "There were no profiles downloaded and O"...
0x180048320  mov     edx, 301h; unsigned int
0x180048325  lea     rcx, aOobeeasyconnec_18; "OobeEasyConnectTask::AttemptDeleteBoots"...
0x18004832c  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180048331  mov     dword ptr [rdi+60h], 5
0x180048338  mov     rcx, rdi
0x18004833b  call    ?PublishCurrentTaskStateWnf@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::PublishCurrentTaskStateWnf(wil::write_lock_required)
0x180048340  jmp     loc_18004842A
0x180048345  cmp     dword ptr [rcx+0A4h], 1
0x18004834c  jz      short loc_18004835F
0x18004834e  lea     r8, aEsimServiceIsN_0; "Esim Service is not idle, wait"
0x180048355  mov     edx, 308h
0x18004835a  jmp     loc_1800482DA
0x18004835f  cmp     dword ptr [rcx+0A0h], 1
0x180048366  jbe     short loc_1800483D5
0x180048368  mov     rcx, [rcx+48h]
0x18004836c  lea     rdx, [rdi+0B0h]
0x180048373  cmp     qword ptr [rdx+18h], 7
0x180048378  mov     rax, [rcx]
0x18004837b  jbe     short loc_180048380
0x18004837d  mov     rdx, [rdx]
0x180048380  mov     rax, [rax+38h]
0x180048384  xor     r8d, r8d
0x180048387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004838c  lea     rcx, aOobeeasyconnec_18; "OobeEasyConnectTask::AttemptDeleteBoots"...
0x180048393  mov     esi, eax
0x180048395  test    eax, eax
0x180048397  js      short loc_1800483A7
0x180048399  lea     r8, aDeleteProfileC; "Delete profile called, changing m_state"...
0x1800483a0  mov     edx, 317h
0x1800483a5  jmp     short loc_18004840C
0x1800483a7  mov     r9d, esi
0x1800483aa  lea     r8, aDeleteprofileF; "DeleteProfile failed with hr=0x%08x, ch"...
0x1800483b1  mov     edx, 320h; unsigned int
0x1800483b6  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x1800483bb  mov     rcx, rdi
0x1800483be  mov     dword ptr [rdi+60h], 7
0x1800483c5  call    ?PublishCurrentTaskStateWnf@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::PublishCurrentTaskStateWnf(wil::write_lock_required)
0x1800483ca  xor     edx, edx; unsigned int
0x1800483cc  mov     ecx, esi; int
0x1800483ce  call    ?BootstrapProfileDeletion@MBSettingUXLogging@@SAXJK@Z; MBSettingUXLogging::BootstrapProfileDeletion(long,ulong)
0x1800483d3  jmp     short loc_18004842A
0x1800483d5  lea     r8, aIfAtThisPointT; "If at this point, there is no eSim pres"...
0x1800483dc  mov     edx, 30Eh; unsigned int
0x1800483e1  lea     rcx, aOobeeasyconnec_18; "OobeEasyConnectTask::AttemptDeleteBoots"...
0x1800483e8  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800483ed  mov     dword ptr [rdi+60h], 7
0x1800483f4  jmp     loc_180048338
0x1800483f9  lea     r8, aThereIsNoBoots; "There is no bootstrap profile, move m_s"...
0x180048400  mov     edx, 2F9h; unsigned int
0x180048405  lea     rcx, aOobeeasyconnec_18; "OobeEasyConnectTask::AttemptDeleteBoots"...
0x18004840c  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180048411  mov     rcx, rdi
0x180048414  mov     dword ptr [rdi+60h], 4
0x18004841b  call    ?PublishCurrentTaskStateWnf@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::PublishCurrentTaskStateWnf(wil::write_lock_required)
0x180048420  mov     dl, bl
0x180048422  mov     rcx, rdi
0x180048425  call    ?AttemptEnableDownloadedProfile@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::AttemptEnableDownloadedProfile(wil::write_lock_required)
0x18004842a  mov     rbx, [rsp+28h+arg_0]
0x18004842f  mov     rsi, [rsp+28h+arg_8]
0x180048434  add     rsp, 20h
0x180048438  pop     rdi
0x180048439  retn
```
