# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::UserActiveHoursStart(void)

- ea: `0x18002552c`
- end: `0x1800255ad`
- name: `?UserActiveHoursStart@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA?AV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@XZ`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180026620`

## callees

- `0x18001c8c4`
- `0x180023414`
- `0x18002552c`
- `0x1800257a8`
- `0x180027f2c`

## string_xrefs

- `0x180025574`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::UserActiveHoursStart(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *a1,
        _QWORD *a2)
{
  int EffectiveActiveHoursValues; // eax
  int v5; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v7; // [rsp+50h] [rbp+18h] BYREF
  unsigned int v8; // [rsp+58h] [rbp+20h] BYREF

  if ( winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsSupported(a1) )
  {
    v7 = 0;
    EffectiveActiveHoursValues = CUsoPolicyHelper::GetEffectiveActiveHoursValues(&v7, &v8);
    if ( EffectiveActiveHoursValues < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x106,
        (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
        (const char *)(unsigned int)EffectiveActiveHoursValues,
        v5);
    std::chrono::duration<__int64,std::ratio<1,10000000>>::duration<__int64,std::ratio<1,10000000>>(a2, &v7);
    return a2;
  }
  else
  {
    *a2 = 0;
    return a2;
  }
}

```

## disassembly

```asm
0x18002552c  mov     [rsp+arg_8], rdx
0x180025531  mov     [rsp+arg_0], rcx
0x180025536  push    rbx
0x180025537  sub     rsp, 30h
0x18002553b  mov     rbx, rdx
0x18002553e  call    ?IsSupported@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA_NXZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsSupported(void)
0x180025543  test    al, al
0x180025545  jnz     short loc_180025551
0x180025547  xor     eax, eax
0x180025549  mov     [rbx], rax
0x18002554c  mov     rax, rbx
0x18002554f  jmp     short loc_1800255A6
0x180025551  mov     [rsp+38h+arg_10], 0
0x180025559  lea     rdx, [rsp+38h+arg_18]; unsigned int *
0x18002555e  lea     rcx, [rsp+38h+arg_10]; unsigned int *
0x180025563  call    ?GetEffectiveActiveHoursValues@CUsoPolicyHelper@@SAJPEAK0@Z; CUsoPolicyHelper::GetEffectiveActiveHoursValues(ulong *,ulong *)
0x180025568  mov     rcx, [rsp+38h]; this
0x18002556d  test    eax, eax
0x18002556f  jns     short loc_180025585
0x180025571  mov     r9d, eax; char *
0x180025574  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x18002557b  mov     edx, 106h; void *
0x180025580  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180025585  mov     eax, [rsp+38h+arg_10]
0x180025589  mov     [rsp+38h+arg_10], eax
0x18002558d  lea     rdx, [rsp+38h+arg_10]
0x180025592  mov     rcx, rbx
0x180025595  call    ??$?0HU?$ratio@$0OBA@$00@std@@$0A@@?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@QEAA@AEBV?$duration@HU?$ratio@$0OBA@$00@std@@@12@@Z; std::chrono::duration<__int64,std::ratio<1,10000000>>::duration<__int64,std::ratio<1,10000000>>(std::chrono::duration<int,std::ratio<3600,1>> const &)
0x18002559a  mov     rax, rbx
0x18002559d  jmp     short loc_1800255A6
0x18002559f  jmp     short $+2
0x1800255a1  mov     rax, [rsp+38h+arg_8]
0x1800255a6  add     rsp, 30h
0x1800255aa  pop     rbx
0x1800255ab  retn
```
