# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::TrySetUserActiveHours(std::chrono::duration<__int64,std::ratio<1,10000000>> const &,std::chrono::duration<__int64,std::ratio<1,10000000>> const &)

- ea: `0x180024f14`
- end: `0x180024f8a`
- name: `?TrySetUserActiveHours@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA_NAEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@0@Z`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180024ed0`

## callees

- `0x18001d9f4`
- `0x180023414`
- `0x180024f14`
- `0x1800257a8`
- `0x1800281b0`

## string_xrefs

- `0x180024f65`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`

## pseudocode

```c
char __fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::TrySetUserActiveHours(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *a1,
        __int64 a2,
        __int64 a3)
{
  char result; // al
  unsigned int *v6; // rax
  unsigned int *v7; // r9
  int active; // eax
  int v9; // [rsp+20h] [rbp-18h] BYREF
  const wil::ResultException *v10; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v13; // [rsp+58h] [rbp+20h] BYREF

  result = winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsSupported(a1);
  if ( result )
  {
    std::chrono::duration_cast<std::chrono::duration<int,std::ratio<3600,1>>,__int64,std::ratio<1,10000000>,0>(&v13, a2);
    v6 = (unsigned int *)std::chrono::duration_cast<std::chrono::duration<int,std::ratio<3600,1>>,__int64,std::ratio<1,10000000>,0>(
                           &v9,
                           a3);
    try
    {
      active = CUsoPolicyHelper::SetActiveHours(*v7, *v6);
      if ( active < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x14D,
          (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
          (const char *)(unsigned int)active,
          v9);
      result = 1;
    }
    catch ( const wil::ResultException *v10 )
    {
      *((_DWORD *)a1 + 14) = *((_DWORD *)v10 + 8);
      return 0;
    }
    catch ( ... )
    {
      *((_DWORD *)a1 + 14) = -2147467259;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180024f14  mov     [rsp+arg_8], rbx
0x180024f19  mov     [rsp+arg_0], rcx
0x180024f1e  push    rdi
0x180024f1f  sub     rsp, 30h
0x180024f23  mov     rbx, r8
0x180024f26  mov     rdi, rdx
0x180024f29  call    ?IsSupported@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA_NXZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsSupported(void)
0x180024f2e  test    al, al
0x180024f30  jz      short loc_180024F7E
0x180024f32  mov     rdx, rdi
0x180024f35  lea     rcx, [rsp+38h+arg_18]
0x180024f3a  call    ??$duration_cast@V?$duration@HU?$ratio@$0OBA@$00@std@@@chrono@std@@_JU?$ratio@$00$0JIJGIA@@3@$0A@@chrono@std@@YA?AV?$duration@HU?$ratio@$0OBA@$00@std@@@01@AEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@01@@Z; std::chrono::duration_cast<std::chrono::duration<int,std::ratio<3600,1>>,__int64,std::ratio<1,10000000>,0>(std::chrono::duration<__int64,std::ratio<1,10000000>> const &)
0x180024f3f  mov     r9, rax
0x180024f42  mov     rdx, rbx
0x180024f45  lea     rcx, [rsp+38h+var_18]
0x180024f4a  call    ??$duration_cast@V?$duration@HU?$ratio@$0OBA@$00@std@@@chrono@std@@_JU?$ratio@$00$0JIJGIA@@3@$0A@@chrono@std@@YA?AV?$duration@HU?$ratio@$0OBA@$00@std@@@01@AEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@01@@Z; std::chrono::duration_cast<std::chrono::duration<int,std::ratio<3600,1>>,__int64,std::ratio<1,10000000>,0>(std::chrono::duration<__int64,std::ratio<1,10000000>> const &)
0x180024f4f  mov     edx, [rax]; char
0x180024f51  mov     ecx, [r9]; Data
0x180024f54  call    ?SetActiveHours@CUsoPolicyHelper@@SAJKK@Z; CUsoPolicyHelper::SetActiveHours(ulong,ulong)
0x180024f59  mov     rcx, [rsp+38h]; this
0x180024f5e  test    eax, eax
0x180024f60  jns     short loc_180024F76
0x180024f62  mov     r9d, eax; char *
0x180024f65  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x180024f6c  mov     edx, 14Dh; void *
0x180024f71  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180024f76  mov     al, 1
0x180024f78  jmp     short loc_180024F7E
0x180024f7a  jmp     short $+2
0x180024f7c  xor     al, al
0x180024f7e  mov     rbx, [rsp+38h+arg_8]
0x180024f83  add     rsp, 30h
0x180024f87  pop     rdi
0x180024f88  retn
```
