# SystemSettings::BatteryUsageHandlers::GetTaskPolicy(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,SystemSettings::BatteryUsageHandlers::TaskPolicy *)

- ea: `0x1800513a4`
- end: `0x180051494`
- name: `?GetTaskPolicy@BatteryUsageHandlers@SystemSettings@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAW4TaskPolicy@12@@Z`
- size: `240`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004aab0`
- `0x18004b580`
- `0x18004b9f0`
- `0x18004ce90`
- `0x18004ddc0`
- `0x18004e210`

## callees

- `0x1800028d0`
- `0x180013be0`
- `0x18001e360`
- `0x18001e5c8`
- `0x18004834c`
- `0x1800483dc`
- `0x1800513a4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051460`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051460`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::BatteryUsageHandlers::GetTaskPolicy(__int64 a1, _DWORD *a2, __int64 a3)
{
  char v5; // r8
  SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *v6; // rcx
  int AppBackgroundCapable; // ebx
  SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *v8; // rcx
  HSTRING string; // [rsp+20h] [rbp-30h] BYREF
  int v11; // [rsp+28h] [rbp-28h] BYREF
  int v12; // [rsp+2Ch] [rbp-24h] BYREF
  __int64 v13[2]; // [rsp+30h] [rbp-20h] BYREF

  v13[1] = a1;
  v11 = 0;
  v12 = 0;
  string = 0;
  v13[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1, a2, a3);
  AppBackgroundCapable = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(
                           (Microsoft::WRL::Wrappers::HString *)&string,
                           v13,
                           v5);
  if ( AppBackgroundCapable >= 0 )
  {
    *a2 = 0;
    AppBackgroundCapable = SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetAppBackgroundCapable(
                             v6,
                             string,
                             &v11);
    if ( AppBackgroundCapable >= 0 )
    {
      if ( !v11 )
        goto LABEL_10;
      AppBackgroundCapable = SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetAppBGCapability(
                               v8,
                               string,
                               (enum SystemSettings::BatteryUsageHandlers::BackgroundCapability *)&v12);
      if ( AppBackgroundCapable < 0 )
        goto LABEL_11;
      if ( ((v12 - 2) & 0xFFFFFFFD) == 0 )
      {
LABEL_10:
        *a2 = 1;
        goto LABEL_11;
      }
      if ( v12 == 3 )
      {
        *a2 = 2;
      }
      else if ( v12 == 1 )
      {
        *a2 = 3;
      }
    }
  }
LABEL_11:
  WindowsDeleteString(string);
  string = 0;
  std::wstring::_Tidy_deallocate(a1);
  return (unsigned int)AppBackgroundCapable;
}

```

## disassembly

```asm
0x1800513a4  mov     [rsp-18h+arg_10], rbx
0x1800513a9  push    rbp
0x1800513aa  push    rsi
0x1800513ab  push    rdi
0x1800513ac  mov     rbp, rsp
0x1800513af  sub     rsp, 50h
0x1800513b3  mov     rax, cs:__security_cookie
0x1800513ba  xor     rax, rsp
0x1800513bd  mov     [rbp+var_10], rax
0x1800513c1  mov     rdi, rdx
0x1800513c4  mov     rsi, rcx
0x1800513c7  mov     [rbp+var_18], rcx
0x1800513cb  mov     [rbp+var_28], 0
0x1800513d2  mov     [rbp+var_24], 0
0x1800513d9  mov     [rbp+string], 0
0x1800513e1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800513e6  mov     [rbp+var_20], rax
0x1800513ea  lea     rdx, [rbp+var_20]
0x1800513ee  lea     rcx, [rbp+string]
0x1800513f2  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800513f7  mov     ebx, eax
0x1800513f9  test    eax, eax
0x1800513fb  js      short loc_18005145C
0x1800513fd  mov     dword ptr [rdi], 0
0x180051403  lea     r8, [rbp+var_28]; int *
0x180051407  mov     rdx, [rbp+string]; HSTRING
0x18005140b  call    ?GetAppBackgroundCapable@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEAUHSTRING__@@PEAH@Z; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetAppBackgroundCapable(HSTRING__ *,int *)
0x180051410  mov     ebx, eax
0x180051412  test    eax, eax
0x180051414  js      short loc_18005145C
0x180051416  cmp     [rbp+var_28], 0
0x18005141a  jz      short loc_180051456
0x18005141c  lea     r8, [rbp+var_24]; enum SystemSettings::BatteryUsageHandlers::BackgroundCapability *
0x180051420  mov     rdx, [rbp+string]; HSTRING
0x180051424  call    ?GetAppBGCapability@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEAUHSTRING__@@PEAW4BackgroundCapability@23@@Z; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetAppBGCapability(HSTRING__ *,SystemSettings::BatteryUsageHandlers::BackgroundCapability *)
0x180051429  mov     ebx, eax
0x18005142b  test    eax, eax
0x18005142d  js      short loc_18005145C
0x18005142f  mov     ecx, [rbp+var_24]
0x180051432  lea     eax, [rcx-2]
0x180051435  test    eax, 0FFFFFFFDh
0x18005143a  jz      short loc_180051456
0x18005143c  cmp     ecx, 3
0x18005143f  jnz     short loc_180051449
0x180051441  mov     dword ptr [rdi], 2
0x180051447  jmp     short loc_18005145C
0x180051449  cmp     ecx, 1
0x18005144c  jnz     short loc_18005145C
0x18005144e  mov     dword ptr [rdi], 3
0x180051454  jmp     short loc_18005145C
0x180051456  mov     dword ptr [rdi], 1
0x18005145c  mov     rcx, [rbp+string]; string
0x180051460  call    cs:__imp_WindowsDeleteString
0x180051466  mov     [rbp+string], 0
0x18005146e  mov     rcx, rsi
0x180051471  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180051476  mov     eax, ebx
0x180051478  mov     rcx, [rbp+var_10]
0x18005147c  xor     rcx, rsp; StackCookie
0x18005147f  call    __security_check_cookie
0x180051484  mov     rbx, [rsp+50h+arg_10]
0x18005148c  add     rsp, 50h
0x180051490  pop     rdi
0x180051491  pop     rsi
0x180051492  pop     rbp
0x180051493  retn
```
