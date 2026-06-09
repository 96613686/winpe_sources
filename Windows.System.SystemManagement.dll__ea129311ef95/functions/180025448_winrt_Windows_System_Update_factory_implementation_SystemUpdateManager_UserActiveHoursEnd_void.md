# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::UserActiveHoursEnd(void)

- ea: `0x180025448`
- end: `0x1800254c9`
- name: `?UserActiveHoursEnd@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA?AV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@XZ`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1800265a0`

## callees

- `0x18001c8c4`
- `0x180023414`
- `0x180025448`
- `0x1800257a8`
- `0x180027f2c`

## string_xrefs

- `0x180025490`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::UserActiveHoursEnd(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *a1,
        _QWORD *a2)
{
  _QWORD *result; // rax
  int EffectiveActiveHoursValues; // eax
  const wil::ResultException *v6; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v11; // [rsp+50h] [rbp+18h] BYREF
  unsigned int v12; // [rsp+58h] [rbp+20h] BYREF

  if ( !winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsSupported(a1) )
  {
    *a2 = 0;
    return a2;
  }
  v11 = 0;
  try
  {
    EffectiveActiveHoursValues = CUsoPolicyHelper::GetEffectiveActiveHoursValues(&v12, &v11);
    if ( EffectiveActiveHoursValues < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x11E,
        (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
        (const char *)(unsigned int)EffectiveActiveHoursValues,
        (int)v6);
    std::chrono::duration<__int64,std::ratio<1,10000000>>::duration<__int64,std::ratio<1,10000000>>(a2, &v11);
    result = a2;
  }
  catch ( const wil::ResultException *v6 )
  {
    *((_DWORD *)a1 + 14) = *((_DWORD *)v6 + 8);
    *a2 = 0;
    return a2;
  }
  catch ( ... )
  {
    *((_DWORD *)a1 + 14) = -2147467259;
    *a2 = 0;
    return a2;
  }
  return result;
}

```

## disassembly

```asm
0x180025448  mov     [rsp+arg_8], rdx
0x18002544d  mov     [rsp+arg_0], rcx
0x180025452  push    rbx
0x180025453  sub     rsp, 30h
0x180025457  mov     rbx, rdx
0x18002545a  call    ?IsSupported@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA_NXZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsSupported(void)
0x18002545f  test    al, al
0x180025461  jnz     short loc_18002546D
0x180025463  xor     eax, eax
0x180025465  mov     [rbx], rax
0x180025468  mov     rax, rbx
0x18002546b  jmp     short loc_1800254C2
0x18002546d  mov     [rsp+38h+arg_10], 0
0x180025475  lea     rdx, [rsp+38h+arg_10]; unsigned int *
0x18002547a  lea     rcx, [rsp+38h+arg_18]; unsigned int *
0x18002547f  call    ?GetEffectiveActiveHoursValues@CUsoPolicyHelper@@SAJPEAK0@Z; CUsoPolicyHelper::GetEffectiveActiveHoursValues(ulong *,ulong *)
0x180025484  mov     rcx, [rsp+38h]; this
0x180025489  test    eax, eax
0x18002548b  jns     short loc_1800254A1
0x18002548d  mov     r9d, eax; char *
0x180025490  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x180025497  mov     edx, 11Eh; void *
0x18002549c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800254a1  mov     eax, [rsp+38h+arg_10]
0x1800254a5  mov     [rsp+38h+arg_10], eax
0x1800254a9  lea     rdx, [rsp+38h+arg_10]
0x1800254ae  mov     rcx, rbx
0x1800254b1  call    ??$?0HU?$ratio@$0OBA@$00@std@@$0A@@?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@QEAA@AEBV?$duration@HU?$ratio@$0OBA@$00@std@@@12@@Z; std::chrono::duration<__int64,std::ratio<1,10000000>>::duration<__int64,std::ratio<1,10000000>>(std::chrono::duration<int,std::ratio<3600,1>> const &)
0x1800254b6  mov     rax, rbx
0x1800254b9  jmp     short loc_1800254C2
0x1800254bb  jmp     short $+2
0x1800254bd  mov     rax, [rsp+38h+arg_8]
0x1800254c2  add     rsp, 30h
0x1800254c6  pop     rbx
0x1800254c7  retn
```
