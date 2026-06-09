# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::SetUSORebootBlock(bool)

- ea: `0x180024aa0`
- end: `0x180024b78`
- name: `?SetUSORebootBlock@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAAX_N@Z`
- size: `216`
- prototype: `void __fastcall(winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *__hidden this, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180020230`
- `0x180024f90`

## callees

- `0x180002dc0`
- `0x180024aa0`
- `0x1800257a8`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180024ae0`
- `ntdll!RtlPublishWnfStateData` at `0x180024ae0`
- `ntdll!NtDeleteWnfStateData` at `0x180024b26`
- `ntdll!NtDeleteWnfStateData` at `0x180024b26`
- `ntdll!RtlNtStatusToDosError` at `0x180024aec`
- `ntdll!RtlNtStatusToDosError` at `0x180024b32`
- `ntdll!RtlNtStatusToDosError` at `0x180024aec`
- `ntdll!RtlNtStatusToDosError` at `0x180024b32`

## string_xrefs

- `0x180024b0d`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`
- `0x180024b53`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::SetUSORebootBlock(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *this,
        char a2)
{
  signed int v2; // ebx
  NTSTATUS v3; // eax
  signed int v4; // eax
  NTSTATUS v5; // eax
  signed int v6; // eax
  int v7; // [rsp+20h] [rbp-38h]
  __int64 v8; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8 = WNF_USO_REBOOT_BLOCK_REQUESTED;
  v2 = 0;
  if ( a2 )
  {
    v3 = RtlPublishWnfStateData(WNF_USO_REBOOT_BLOCK_REQUESTED, 0, 0, 0);
    if ( v3 < 0 )
    {
      v4 = RtlNtStatusToDosError(v3);
      v2 = v4;
      if ( v4 > 0 )
        v2 = (unsigned __int16)v4 | 0x80070000;
    }
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CF,
        (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
        (const char *)(unsigned int)v2,
        0);
  }
  else
  {
    v5 = NtDeleteWnfStateData(&v8, 0);
    if ( v5 < 0 )
    {
      v6 = RtlNtStatusToDosError(v5);
      v2 = v6;
      if ( v6 > 0 )
        v2 = (unsigned __int16)v6 | 0x80070000;
    }
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1D4,
        (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
        (const char *)(unsigned int)v2,
        v7);
  }
}

```

## disassembly

```asm
0x180024aa0  push    rbx
0x180024aa2  sub     rsp, 50h
0x180024aa6  mov     rax, cs:__security_cookie
0x180024aad  xor     rax, rsp
0x180024ab0  mov     [rsp+58h+var_18], rax
0x180024ab5  lea     rax, ??_7?$WnfPublisherT@D@@6B@; const WnfPublisherT<char>::`vftable'
0x180024abc  mov     [rsp+58h+var_28], rax
0x180024ac1  mov     rcx, cs:WNF_USO_REBOOT_BLOCK_REQUESTED
0x180024ac8  mov     [rsp+58h+var_20], rcx
0x180024acd  xor     ebx, ebx
0x180024acf  test    dl, dl
0x180024ad1  jz      short loc_180024B1F
0x180024ad3  mov     qword ptr [rsp+58h+var_38], rbx; int
0x180024ad8  xor     r9d, r9d
0x180024adb  xor     r8d, r8d
0x180024ade  xor     edx, edx
0x180024ae0  call    cs:__imp_RtlPublishWnfStateData
0x180024ae6  test    eax, eax
0x180024ae8  jns     short loc_180024B01
0x180024aea  mov     ecx, eax; Status
0x180024aec  call    cs:__imp_RtlNtStatusToDosError
0x180024af2  mov     ebx, eax
0x180024af4  test    eax, eax
0x180024af6  jle     short loc_180024B01
0x180024af8  movzx   ebx, ax
0x180024afb  or      ebx, 80070000h
0x180024b01  mov     rcx, [rsp+58h]; this
0x180024b06  test    ebx, ebx
0x180024b08  jns     short loc_180024B65
0x180024b0a  mov     r9d, ebx; char *
0x180024b0d  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x180024b14  mov     edx, 1CFh; void *
0x180024b19  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180024b1f  xor     edx, edx
0x180024b21  lea     rcx, [rsp+58h+var_20]
0x180024b26  call    cs:__imp_NtDeleteWnfStateData
0x180024b2c  test    eax, eax
0x180024b2e  jns     short loc_180024B47
0x180024b30  mov     ecx, eax; Status
0x180024b32  call    cs:__imp_RtlNtStatusToDosError
0x180024b38  mov     ebx, eax
0x180024b3a  test    eax, eax
0x180024b3c  jle     short loc_180024B47
0x180024b3e  movzx   ebx, ax
0x180024b41  or      ebx, 80070000h
0x180024b47  mov     rcx, [rsp+58h]; this
0x180024b4c  test    ebx, ebx
0x180024b4e  jns     short loc_180024B65
0x180024b50  mov     r9d, ebx; char *
0x180024b53  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x180024b5a  mov     edx, 1D4h; void *
0x180024b5f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180024b65  mov     rcx, [rsp+58h+var_18]
0x180024b6a  xor     rcx, rsp; StackCookie
0x180024b6d  call    __security_check_cookie
0x180024b72  add     rsp, 50h
0x180024b76  pop     rbx
0x180024b77  retn
```
