# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::UserActiveHoursMax(void)

- ea: `0x1800254d0`
- end: `0x180025525`
- name: `?UserActiveHoursMax@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAAHXZ`
- size: `85`
- prototype: `__int64 __fastcall(winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1800265e0`

## callees

- `0x180023414`
- `0x1800254d0`
- `0x1800257a8`
- `0x180027d4c`

## string_xrefs

- `0x180025504`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`

## pseudocode

```c
__int64 __fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::UserActiveHoursMax(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *this)
{
  __int64 result; // rax
  int EffectiveActiveHoursMaxRange; // eax
  const wil::ResultException *v4; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v7; // [rsp+48h] [rbp+10h] BYREF

  if ( !winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsSupported(this) )
    return 0;
  v7 = 0;
  try
  {
    EffectiveActiveHoursMaxRange = CUsoPolicyHelper::GetEffectiveActiveHoursMaxRange(&v7);
    if ( EffectiveActiveHoursMaxRange < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x134,
        (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
        (const char *)(unsigned int)EffectiveActiveHoursMaxRange,
        (int)v4);
    result = v7;
  }
  catch ( const wil::ResultException *v4 )
  {
    *((_DWORD *)this + 14) = *((_DWORD *)v4 + 8);
    return 0;
  }
  catch ( ... )
  {
    *((_DWORD *)this + 14) = -2147467259;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800254d0  mov     [rsp+arg_0], rcx
0x1800254d5  sub     rsp, 38h
0x1800254d9  call    ?IsSupported@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA_NXZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsSupported(void)
0x1800254de  test    al, al
0x1800254e0  jnz     short loc_1800254E6
0x1800254e2  xor     eax, eax
0x1800254e4  jmp     short loc_18002551F
0x1800254e6  mov     [rsp+38h+arg_8], 0
0x1800254ee  lea     rcx, [rsp+38h+arg_8]; unsigned int *
0x1800254f3  call    ?GetEffectiveActiveHoursMaxRange@CUsoPolicyHelper@@SAJPEAK@Z; CUsoPolicyHelper::GetEffectiveActiveHoursMaxRange(ulong *)
0x1800254f8  mov     rcx, [rsp+38h]; this
0x1800254fd  test    eax, eax
0x1800254ff  jns     short loc_180025515
0x180025501  mov     r9d, eax; char *
0x180025504  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x18002550b  mov     edx, 134h; void *
0x180025510  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180025515  mov     eax, [rsp+38h+arg_8]
0x180025519  jmp     short loc_18002551F
0x18002551b  jmp     short $+2
0x18002551d  xor     eax, eax
0x18002551f  add     rsp, 38h
0x180025523  retn
```
