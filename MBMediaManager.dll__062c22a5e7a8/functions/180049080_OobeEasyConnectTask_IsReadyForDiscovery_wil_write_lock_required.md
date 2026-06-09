# OobeEasyConnectTask::IsReadyForDiscovery(wil::write_lock_required)

- ea: `0x180049080`
- end: `0x180049213`
- name: `?IsReadyForDiscovery@OobeEasyConnectTask@@AEAA_NUwrite_lock_required@wil@@@Z`
- size: `403`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180022a3c`

## callees

- `0x18000ad20`
- `0x180049080`
- `0x18004921c`
- `0x18004c9d4`

## string_xrefs

- `0x180049147`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`
- `0x180049093`: `Already running/ran discovery`
- `0x18004909f`: `OobeEasyConnectTask::IsReadyForDiscovery`
- `0x1800490c7`: `OobeEasyConnectTask::IsReadyForDiscovery`
- `0x1800490ef`: `OobeEasyConnectTask::IsReadyForDiscovery`
- `0x180049169`: `OobeEasyConnectTask::IsReadyForDiscovery`
- `0x180049191`: `OobeEasyConnectTask::IsReadyForDiscovery`
- `0x1800491bb`: `OobeEasyConnectTask::IsReadyForDiscovery`
- `0x1800491cb`: `OobeEasyConnectTask::IsReadyForDiscovery`
- `0x1800490bb`: `Esim State is not ready for Discovery`
- `0x1800490e3`: `Esim Service Operational state is not idle`
- `0x180049185`: `Connected to the Internet, ready to run Discovery`
- `0x1800491af`: `Connected to the Internet with a Bootstrap profile, ready to run Discovery`
- `0x1800491db`: `Provisioning profile available, ready to run Discovery`
- `0x1800491f0`: `State is ready, but no connectivity available`

## pseudocode

```c
char __fastcall OobeEasyConnectTask::IsReadyForDiscovery(__int64 a1)
{
  _QWORD *v3; // rcx
  _BYTE *v4; // rdi
  unsigned int IsBootstrapProfile; // eax
  __int64 v6; // r9
  const char *v7; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( *(_DWORD *)(a1 + 96) )
  {
    MBSettingUXLogging::Info("OobeEasyConnectTask::IsReadyForDiscovery", 634, "Already running/ran discovery");
    return 0;
  }
  else if ( *(_DWORD *)(a1 + 160) == 2 )
  {
    if ( *(_DWORD *)(a1 + 164) == 1 )
    {
      v3 = (_QWORD *)(a1 + 176);
      v4 = (_BYTE *)(a1 + 168);
      if ( !v3[2] )
        goto LABEL_23;
      IsBootstrapProfile = MBUtil::GetIsBootstrapProfile(v3, (bool *)(a1 + 168));
      v6 = IsBootstrapProfile;
      if ( (int)(IsBootstrapProfile + 0x80000000) >= 0 && IsBootstrapProfile != -2147024894 )
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x291,
          (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
          (const char *)IsBootstrapProfile,
          (int)"GetIsBootstrapProfile failed",
          v7);
      if ( *v4 )
      {
LABEL_23:
        if ( *(_BYTE *)(a1 + 152) )
        {
          MBSettingUXLogging::Info(
            "OobeEasyConnectTask::IsReadyForDiscovery",
            671,
            "Connected to the Internet, ready to run Discovery");
          return 1;
        }
        else if ( *v4 && *(_DWORD *)(a1 + 156) == 5 )
        {
          MBSettingUXLogging::Info(
            "OobeEasyConnectTask::IsReadyForDiscovery",
            676,
            "Connected to the Internet with a Bootstrap profile, ready to run Discovery");
          return 1;
        }
        else if ( *(_BYTE *)(a1 + 208) )
        {
          MBSettingUXLogging::Info(
            "OobeEasyConnectTask::IsReadyForDiscovery",
            681,
            "Provisioning profile available, ready to run Discovery");
          return 1;
        }
        else
        {
          MBSettingUXLogging::Info(
            "OobeEasyConnectTask::IsReadyForDiscovery",
            685,
            "State is ready, but no connectivity available");
          return 0;
        }
      }
      else
      {
        MBSettingUXLogging::Info(
          "OobeEasyConnectTask::IsReadyForDiscovery",
          663,
          "Esim has an enabled profile, but it is not Bootstrap",
          v6);
        return 0;
      }
    }
    else
    {
      MBSettingUXLogging::Info(
        "OobeEasyConnectTask::IsReadyForDiscovery",
        646,
        "Esim Service Operational state is not idle");
      return 0;
    }
  }
  else
  {
    MBSettingUXLogging::Info("OobeEasyConnectTask::IsReadyForDiscovery", 640, "Esim State is not ready for Discovery");
    return 0;
  }
}

```

## disassembly

```asm
0x180049080  mov     [rsp+arg_0], rbx
0x180049085  push    rdi
0x180049086  sub     rsp, 30h
0x18004908a  mov     rbx, rcx
0x18004908d  cmp     dword ptr [rcx+60h], 0
0x180049091  jz      short loc_1800490B2
0x180049093  lea     r8, aAlreadyRunning; "Already running/ran discovery"
0x18004909a  mov     edx, 27Ah; unsigned int
0x18004909f  lea     rcx, aOobeeasyconnec_12; "OobeEasyConnectTask::IsReadyForDiscover"...
0x1800490a6  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800490ab  xor     al, al
0x1800490ad  jmp     loc_180049207
0x1800490b2  cmp     dword ptr [rcx+0A0h], 2
0x1800490b9  jz      short loc_1800490DA
0x1800490bb  lea     r8, aEsimStateIsNot; "Esim State is not ready for Discovery"
0x1800490c2  mov     edx, 280h; unsigned int
0x1800490c7  lea     rcx, aOobeeasyconnec_12; "OobeEasyConnectTask::IsReadyForDiscover"...
0x1800490ce  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800490d3  xor     al, al
0x1800490d5  jmp     loc_180049207
0x1800490da  cmp     dword ptr [rcx+0A4h], 1
0x1800490e1  jz      short loc_180049102
0x1800490e3  lea     r8, aEsimServiceOpe; "Esim Service Operational state is not i"...
0x1800490ea  mov     edx, 286h; unsigned int
0x1800490ef  lea     rcx, aOobeeasyconnec_12; "OobeEasyConnectTask::IsReadyForDiscover"...
0x1800490f6  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800490fb  xor     al, al
0x1800490fd  jmp     loc_180049207
0x180049102  add     rcx, 0B0h
0x180049109  lea     rdi, [rbx+0A8h]
0x180049110  cmp     qword ptr [rcx+10h], 0
0x180049115  jz      short loc_18004917C
0x180049117  mov     rdx, rdi
0x18004911a  call    ?GetIsBootstrapProfile@MBUtil@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEA_N@Z; MBUtil::GetIsBootstrapProfile(std::wstring const &,bool *)
0x18004911f  mov     r9d, eax; char *
0x180049122  mov     ecx, 80000000h
0x180049127  add     eax, ecx
0x180049129  test    ecx, eax
0x18004912b  jnz     short loc_180049158
0x18004912d  cmp     r9d, 80070002h
0x180049134  jz      short loc_180049158
0x180049136  mov     rcx, [rsp+38h]; this
0x18004913b  lea     rax, aGetisbootstrap; "GetIsBootstrapProfile failed"
0x180049142  mov     qword ptr [rsp+38h+var_18], rax; int
0x180049147  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18004914e  mov     edx, 291h; void *
0x180049153  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180049158  cmp     byte ptr [rdi], 0
0x18004915b  jnz     short loc_18004917C
0x18004915d  lea     r8, aEsimHasAnEnabl; "Esim has an enabled profile, but it is "...
0x180049164  mov     edx, 297h; unsigned int
0x180049169  lea     rcx, aOobeeasyconnec_12; "OobeEasyConnectTask::IsReadyForDiscover"...
0x180049170  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180049175  xor     al, al
0x180049177  jmp     loc_180049207
0x18004917c  cmp     byte ptr [rbx+98h], 0
0x180049183  jz      short loc_1800491A1
0x180049185  lea     r8, aConnectedToThe; "Connected to the Internet, ready to run"...
0x18004918c  mov     edx, 29Fh; unsigned int
0x180049191  lea     rcx, aOobeeasyconnec_12; "OobeEasyConnectTask::IsReadyForDiscover"...
0x180049198  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18004919d  mov     al, 1
0x18004919f  jmp     short loc_180049207
0x1800491a1  cmp     byte ptr [rdi], 0
0x1800491a4  jz      short loc_1800491CB
0x1800491a6  cmp     dword ptr [rbx+9Ch], 5
0x1800491ad  jnz     short loc_1800491CB
0x1800491af  lea     r8, aConnectedToThe_0; "Connected to the Internet with a Bootst"...
0x1800491b6  mov     edx, 2A4h; unsigned int
0x1800491bb  lea     rcx, aOobeeasyconnec_12; "OobeEasyConnectTask::IsReadyForDiscover"...
0x1800491c2  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800491c7  mov     al, 1
0x1800491c9  jmp     short loc_180049207
0x1800491cb  lea     rcx, aOobeeasyconnec_12; "OobeEasyConnectTask::IsReadyForDiscover"...
0x1800491d2  cmp     byte ptr [rbx+0D0h], 0
0x1800491d9  jz      short loc_1800491F0
0x1800491db  lea     r8, aProvisioningPr; "Provisioning profile available, ready t"...
0x1800491e2  mov     edx, 2A9h; unsigned int
0x1800491e7  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800491ec  mov     al, 1
0x1800491ee  jmp     short loc_180049207
0x1800491f0  lea     r8, aStateIsReadyBu; "State is ready, but no connectivity ava"...
0x1800491f7  mov     edx, 2ADh; unsigned int
0x1800491fc  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180049201  xor     al, al
0x180049203  jmp     short loc_180049207
0x180049205  xor     al, al
0x180049207  mov     rbx, [rsp+38h+arg_0]
0x18004920c  add     rsp, 30h
0x180049210  pop     rdi
0x180049211  retn
```
