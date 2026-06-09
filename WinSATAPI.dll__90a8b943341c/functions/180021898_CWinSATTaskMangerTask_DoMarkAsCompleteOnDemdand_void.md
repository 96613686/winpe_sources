# CWinSATTaskMangerTask::DoMarkAsCompleteOnDemdand(void)

- ea: `0x180021898`
- end: `0x1800219cc`
- name: `?DoMarkAsCompleteOnDemdand@CWinSATTaskMangerTask@@AEAAXXZ`
- size: `308`
- prototype: `void __fastcall(CWinSATTaskMangerTask *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800213a4`

## callees

- `0x18001b790`
- `0x180021898`
- `0x180021afc`
- `0x180021ebc`
- `0x18002d430`
- `0x18002d650`
- `0x18002d7ec`

## import_xrefs

- `msvcrt!_time64` at `0x1800218fa`
- `msvcrt!_time64` at `0x1800218fa`

## string_xrefs

- `0x18002192e`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x1800219af`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x18002191f`: `Cannot save %s to the registry`
- `0x18002199b`: `Cannot save %s to the registry`
- `0x180021962`: `Cannot read %s from the registry`
- `0x1800218e2`: `Cannot determine if %s exists in the registry`
- `0x1800218d6`: `FirstIdleCompletionTimeDate`
- `0x180021906`: `FirstIdleCompletionTimeDate`
- `0x180021988`: `FirstIdleAssessmentCompletionDuration`

## pseudocode

```c
void __fastcall CWinSATTaskMangerTask::DoMarkAsCompleteOnDemdand(CWinSATTaskMangerTask *this)
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  unsigned int DoesValueExist; // eax
  const wchar_t *v4; // rbx
  unsigned int v5; // edx
  __time64_t v6; // rdi
  __int64 v7; // rcx
  unsigned int v8; // eax
  CWinSATTaskMangerTask *v9; // rcx
  __int64 v10; // rcx
  unsigned int v11; // [rsp+48h] [rbp+18h] BYREF
  unsigned __int64 v12; // [rsp+50h] [rbp+20h] BYREF

  LOBYTE(v11) = 0;
  if ( !CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(this, (bool *)&v11) || !(_BYTE)v11 )
  {
    LOBYTE(v11) = 0;
    DoesValueExist = RegHelper::DoesValueExist(v2, v1, &v11);
    if ( DoesValueExist )
    {
      v4 = L"FirstIdleCompletionTimeDate";
      v5 = 416;
    }
    else
    {
      if ( (_BYTE)v11 )
        return;
      v6 = _time64(0);
      v8 = RegHelper::WriteQWORDValue(v7, L"FirstIdleCompletionTimeDate", v6);
      if ( v8 )
        Record_Win32Error_w(
          "base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp",
          0x1B4u,
          v8,
          (char)L"FirstIdleCompletionTimeDate");
      v12 = 0;
      v4 = (const wchar_t *)L"FirstIdleRunTimeDate";
      DoesValueExist = RegHelper::ReadQWORDValue(1, L"FirstIdleRunTimeDate", &v12);
      if ( DoesValueExist )
      {
        v5 = 449;
      }
      else
      {
        v11 = 0;
        CWinSATTaskMangerTask::SQMFirstCompletionDuration(v9, v12, v6, &v11);
        v4 = L"FirstIdleAssessmentCompletionDuration";
        DoesValueExist = RegHelper::WriteQWORDValue(v10, L"FirstIdleAssessmentCompletionDuration", v11);
        if ( !DoesValueExist )
          return;
        v5 = 463;
      }
    }
    Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp", v5, DoesValueExist, (char)v4);
  }
}

```

## disassembly

```asm
0x180021898  mov     [rsp-8+arg_0], rbx
0x18002189d  mov     [rsp-8+arg_18], rdi
0x1800218a2  push    rbp
0x1800218a3  mov     rbp, rsp
0x1800218a6  sub     rsp, 30h
0x1800218aa  lea     rdx, [rbp+arg_8]; bool *
0x1800218ae  mov     byte ptr [rbp+arg_8], 0
0x1800218b2  call    ?HasIdleWinSATCompletedOnce@CWinSATTaskMangerTask@@AEAA_NAEA_N@Z; CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(bool &)
0x1800218b7  test    al, al
0x1800218b9  jz      short loc_1800218C5
0x1800218bb  cmp     byte ptr [rbp+arg_8], 0
0x1800218bf  jnz     loc_1800219BB
0x1800218c5  lea     r8, [rbp+arg_8]
0x1800218c9  mov     byte ptr [rbp+arg_8], 0
0x1800218cd  call    ?DoesValueExist@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEA_N@Z; RegHelper::DoesValueExist(WinSATRegistryKeys::Enum,ushort const *,bool &)
0x1800218d2  test    eax, eax
0x1800218d4  jz      short loc_1800218EE
0x1800218d6  lea     rbx, ValueName; "FirstIdleCompletionTimeDate"
0x1800218dd  mov     edx, 1A0h
0x1800218e2  lea     r9, aCannotDetermin; "Cannot determine if %s exists in the re"...
0x1800218e9  jmp     loc_1800219A7
0x1800218ee  cmp     byte ptr [rbp+arg_8], 0
0x1800218f2  jnz     loc_1800219BB
0x1800218f8  xor     ecx, ecx; Time
0x1800218fa  call    cs:__imp__time64
0x180021901  nop     dword ptr [rax+rax+00h]
0x180021906  lea     rbx, ValueName; "FirstIdleCompletionTimeDate"
0x18002190d  mov     r8, rax
0x180021910  mov     rdx, rbx
0x180021913  mov     rdi, rax
0x180021916  call    ?WriteQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBG_K@Z; RegHelper::WriteQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64)
0x18002191b  test    eax, eax
0x18002191d  jz      short loc_18002193F
0x18002191f  lea     r9, aCannotSaveSToT; "Cannot save %s to the registry"
0x180021926  mov     qword ptr [rsp+30h+var_10], rbx; char
0x18002192b  mov     r8d, eax; unsigned int
0x18002192e  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021935  mov     edx, 1B4h; unsigned int
0x18002193a  call    Record_Win32Error_w
0x18002193f  and     [rbp+arg_10], 0
0x180021944  lea     rbx, aFirstidlerunti; "FirstIdleRunTimeDate"
0x18002194b  xor     r9d, r9d
0x18002194e  lea     r8, [rbp+arg_10]
0x180021952  mov     rdx, rbx
0x180021955  lea     ecx, [r9+1]
0x180021959  call    ?ReadQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEA_KPEA_N@Z; RegHelper::ReadQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64 &,bool *)
0x18002195e  test    eax, eax
0x180021960  jz      short loc_180021970
0x180021962  lea     r9, aCannotReadSFro; "Cannot read %s from the registry"
0x180021969  mov     edx, 1C1h
0x18002196e  jmp     short loc_1800219A7
0x180021970  mov     rdx, [rbp+arg_10]; unsigned __int64
0x180021974  lea     r9, [rbp+arg_8]; unsigned int *
0x180021978  and     [rbp+arg_8], 0
0x18002197c  mov     r8, rdi; unsigned __int64
0x18002197f  call    ?SQMFirstCompletionDuration@CWinSATTaskMangerTask@@AEAAX_K0AEAK@Z; CWinSATTaskMangerTask::SQMFirstCompletionDuration(unsigned __int64,unsigned __int64,ulong &)
0x180021984  mov     r8d, [rbp+arg_8]
0x180021988  lea     rbx, aFirstidleasses; "FirstIdleAssessmentCompletionDuration"
0x18002198f  mov     rdx, rbx
0x180021992  call    ?WriteQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBG_K@Z; RegHelper::WriteQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64)
0x180021997  test    eax, eax
0x180021999  jz      short loc_1800219BB
0x18002199b  lea     r9, aCannotSaveSToT; "Cannot save %s to the registry"
0x1800219a2  mov     edx, 1CFh; unsigned int
0x1800219a7  mov     r8d, eax; unsigned int
0x1800219aa  mov     qword ptr [rsp+30h+var_10], rbx; char
0x1800219af  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x1800219b6  call    Record_Win32Error_w
0x1800219bb  mov     rbx, [rsp+30h+arg_0]
0x1800219c0  mov     rdi, [rsp+30h+arg_18]
0x1800219c5  add     rsp, 30h
0x1800219c9  pop     rbp
0x1800219ca  retn
```
