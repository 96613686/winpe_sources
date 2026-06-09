# CWinSATTaskMangerTask::DoSuccesfulCompletionRegistryAndSQMWork(void)

- ea: `0x1800219d4`
- end: `0x180021af5`
- name: `?DoSuccesfulCompletionRegistryAndSQMWork@CWinSATTaskMangerTask@@AEAAXXZ`
- size: `289`
- prototype: `void __fastcall(CWinSATTaskMangerTask *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800213a4`

## callees

- `0x18001b790`
- `0x1800219d4`
- `0x180021ebc`
- `0x18002d4dc`
- `0x18002d650`
- `0x18002d7ec`

## import_xrefs

- `msvcrt!_time64` at `0x180021a1d`
- `msvcrt!_time64` at `0x180021a1d`

## string_xrefs

- `0x180021a51`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x180021add`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x1800219ff`: `Cannot incriment %s in the registry`
- `0x180021a42`: `Cannot save %s to the registry`
- `0x180021ac9`: `Cannot save %s to the registry`
- `0x180021a8c`: `Cannot read %s from the registry`
- `0x180021a29`: `FirstIdleCompletionTimeDate`
- `0x1800219e8`: `IdleAssessmentCompletionCount`
- `0x180021ab6`: `FirstIdleAssessmentCompletionDuration`

## pseudocode

```c
void __fastcall CWinSATTaskMangerTask::DoSuccesfulCompletionRegistryAndSQMWork(CWinSATTaskMangerTask *this)
{
  const wchar_t *v1; // rbx
  unsigned int v2; // eax
  unsigned int v3; // edx
  __time64_t v4; // rbx
  __int64 v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // eax
  CWinSATTaskMangerTask *v8; // rcx
  __int64 v9; // rcx
  unsigned int v10; // [rsp+40h] [rbp+8h] BYREF
  int v11; // [rsp+44h] [rbp+Ch]
  unsigned __int64 v12; // [rsp+48h] [rbp+10h] BYREF

  v11 = HIDWORD(this);
  v10 = 0;
  v1 = (const wchar_t *)L"IdleAssessmentCompletionCount";
  v2 = RegHelper::IncrimentDWORDValue(this, L"IdleAssessmentCompletionCount", &v10);
  if ( v2 )
  {
    v3 = 343;
LABEL_10:
    Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp", v3, v2, (char)v1);
    return;
  }
  if ( v10 != 1 )
    return;
  v4 = _time64(0);
  v6 = RegHelper::WriteQWORDValue(v5, L"FirstIdleCompletionTimeDate", v4);
  if ( v6 )
    Record_Win32Error_w(
      "base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp",
      0x168u,
      v6,
      (char)L"FirstIdleCompletionTimeDate");
  v12 = 0;
  v7 = RegHelper::ReadQWORDValue(1, L"FirstIdleRunTimeDate", &v12);
  if ( v7 )
  {
    Record_Win32Error_w(
      "base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp",
      0x174u,
      v7,
      (char)L"FirstIdleRunTimeDate");
    return;
  }
  v10 = 0;
  CWinSATTaskMangerTask::SQMFirstCompletionDuration(v8, v12, v4, &v10);
  v1 = L"FirstIdleAssessmentCompletionDuration";
  v2 = RegHelper::WriteQWORDValue(v9, L"FirstIdleAssessmentCompletionDuration", v10);
  if ( v2 )
  {
    v3 = 385;
    goto LABEL_10;
  }
}

```

## disassembly

```asm
0x1800219d4  mov     rax, rsp
0x1800219d7  mov     [rax+18h], rbx
0x1800219db  mov     [rax+8], rcx
0x1800219df  push    rsi
0x1800219e0  sub     rsp, 30h
0x1800219e4  and     dword ptr [rax+8], 0
0x1800219e8  lea     rbx, aIdleassessment; "IdleAssessmentCompletionCount"
0x1800219ef  mov     rdx, rbx
0x1800219f2  lea     r8, [rax+8]
0x1800219f6  call    ?IncrimentDWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEAK@Z; RegHelper::IncrimentDWORDValue(WinSATRegistryKeys::Enum,ushort const *,ulong &)
0x1800219fb  test    eax, eax
0x1800219fd  jz      short loc_180021A10
0x1800219ff  lea     r9, aCannotIncrimen; "Cannot incriment %s in the registry"
0x180021a06  mov     edx, 157h
0x180021a0b  jmp     loc_180021AD5
0x180021a10  cmp     [rsp+38h+arg_0], 1
0x180021a15  jnz     loc_180021AE9
0x180021a1b  xor     ecx, ecx; Time
0x180021a1d  call    cs:__imp__time64
0x180021a24  nop     dword ptr [rax+rax+00h]
0x180021a29  lea     rsi, ValueName; "FirstIdleCompletionTimeDate"
0x180021a30  mov     r8, rax
0x180021a33  mov     rdx, rsi
0x180021a36  mov     rbx, rax
0x180021a39  call    ?WriteQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBG_K@Z; RegHelper::WriteQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64)
0x180021a3e  test    eax, eax
0x180021a40  jz      short loc_180021A62
0x180021a42  lea     r9, aCannotSaveSToT; "Cannot save %s to the registry"
0x180021a49  mov     qword ptr [rsp+38h+var_18], rsi; char
0x180021a4e  mov     r8d, eax; unsigned int
0x180021a51  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021a58  mov     edx, 168h; unsigned int
0x180021a5d  call    Record_Win32Error_w
0x180021a62  and     [rsp+38h+arg_8], 0
0x180021a68  lea     rsi, aFirstidlerunti; "FirstIdleRunTimeDate"
0x180021a6f  xor     r9d, r9d
0x180021a72  lea     r8, [rsp+38h+arg_8]
0x180021a77  mov     rdx, rsi
0x180021a7a  lea     ecx, [r9+1]
0x180021a7e  call    ?ReadQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEA_KPEA_N@Z; RegHelper::ReadQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64 &,bool *)
0x180021a83  test    eax, eax
0x180021a85  jz      short loc_180021A9A
0x180021a87  mov     qword ptr [rsp+38h+var_18], rsi
0x180021a8c  lea     r9, aCannotReadSFro; "Cannot read %s from the registry"
0x180021a93  mov     edx, 174h
0x180021a98  jmp     short loc_180021ADA
0x180021a9a  mov     rdx, [rsp+38h+arg_8]; unsigned __int64
0x180021a9f  lea     r9, [rsp+38h+arg_0]; unsigned int *
0x180021aa4  and     [rsp+38h+arg_0], 0
0x180021aa9  mov     r8, rbx; unsigned __int64
0x180021aac  call    ?SQMFirstCompletionDuration@CWinSATTaskMangerTask@@AEAAX_K0AEAK@Z; CWinSATTaskMangerTask::SQMFirstCompletionDuration(unsigned __int64,unsigned __int64,ulong &)
0x180021ab1  mov     r8d, [rsp+38h+arg_0]
0x180021ab6  lea     rbx, aFirstidleasses; "FirstIdleAssessmentCompletionDuration"
0x180021abd  mov     rdx, rbx
0x180021ac0  call    ?WriteQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBG_K@Z; RegHelper::WriteQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64)
0x180021ac5  test    eax, eax
0x180021ac7  jz      short loc_180021AE9
0x180021ac9  lea     r9, aCannotSaveSToT; "Cannot save %s to the registry"
0x180021ad0  mov     edx, 181h; unsigned int
0x180021ad5  mov     qword ptr [rsp+38h+var_18], rbx; char
0x180021ada  mov     r8d, eax; unsigned int
0x180021add  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021ae4  call    Record_Win32Error_w
0x180021ae9  mov     rbx, [rsp+38h+arg_10]
0x180021aee  add     rsp, 30h
0x180021af2  pop     rsi
0x180021af3  retn
```
