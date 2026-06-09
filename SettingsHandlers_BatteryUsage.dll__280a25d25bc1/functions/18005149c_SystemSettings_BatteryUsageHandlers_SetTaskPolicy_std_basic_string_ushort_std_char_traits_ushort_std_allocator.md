# SystemSettings::BatteryUsageHandlers::SetTaskPolicy(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,SystemSettings::BatteryUsageHandlers::TaskPolicy)

- ea: `0x18005149c`
- end: `0x18005157c`
- name: `?SetTaskPolicy@BatteryUsageHandlers@SystemSettings@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4TaskPolicy@12@@Z`
- size: `224`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004bcb0`
- `0x18004e2b0`

## callees

- `0x1800028d0`
- `0x180013be0`
- `0x18001e360`
- `0x18001e5c8`
- `0x180048dac`
- `0x180048e68`
- `0x18005149c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005154f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005154f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::BatteryUsageHandlers::SetTaskPolicy(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // esi
  char v5; // r8
  SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *v6; // rcx
  int v7; // ebx
  SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *v8; // rcx
  int v9; // r8d
  int v10; // eax
  SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *v11; // rcx
  HSTRING string; // [rsp+20h] [rbp-28h] BYREF
  __int64 v14[2]; // [rsp+28h] [rbp-20h] BYREF

  v3 = a2;
  v14[1] = a1;
  string = 0;
  v14[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1, a2, a3);
  v7 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(
         (Microsoft::WRL::Wrappers::HString *)&string,
         v14,
         v5);
  if ( v7 >= 0 )
  {
    switch ( v3 )
    {
      case 1:
        v7 = SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::SetAppBGState(v6, string, 1);
        if ( v7 >= 0 )
        {
          v9 = 0;
LABEL_5:
          v10 = SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::SetAppExemptState(v8, string, v9);
LABEL_12:
          v7 = v10;
        }
        break;
      case 2:
        v7 = SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::SetAppBGState(v6, string, 1);
        if ( v7 >= 0 )
        {
          v9 = 1;
          goto LABEL_5;
        }
        break;
      case 3:
        v7 = SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::SetAppExemptState(v6, string, 0);
        if ( v7 >= 0 )
        {
          v10 = SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::SetAppBGState(v11, string, 0);
          goto LABEL_12;
        }
        break;
    }
  }
  WindowsDeleteString(string);
  string = 0;
  std::wstring::_Tidy_deallocate(a1);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18005149c  push    rbp
0x18005149e  push    rbx
0x18005149f  push    rsi
0x1800514a0  push    rdi
0x1800514a1  mov     rbp, rsp
0x1800514a4  sub     rsp, 48h
0x1800514a8  mov     rax, cs:__security_cookie
0x1800514af  xor     rax, rsp
0x1800514b2  mov     [rbp+var_10], rax
0x1800514b6  mov     esi, edx
0x1800514b8  mov     rdi, rcx
0x1800514bb  mov     [rbp+var_18], rcx
0x1800514bf  mov     [rbp+string], 0
0x1800514c7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800514cc  mov     [rbp+var_20], rax
0x1800514d0  lea     rdx, [rbp+var_20]
0x1800514d4  lea     rcx, [rbp+string]
0x1800514d8  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800514dd  mov     ebx, eax
0x1800514df  test    eax, eax
0x1800514e1  js      short loc_18005154B
0x1800514e3  cmp     esi, 1
0x1800514e6  jnz     short loc_180051508
0x1800514e8  mov     r8d, esi; int
0x1800514eb  mov     rdx, [rbp+string]; HSTRING
0x1800514ef  call    ?SetAppBGState@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEAUHSTRING__@@H@Z; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::SetAppBGState(HSTRING__ *,int)
0x1800514f4  mov     ebx, eax
0x1800514f6  test    eax, eax
0x1800514f8  js      short loc_18005154B
0x1800514fa  xor     r8d, r8d; int
0x1800514fd  mov     rdx, [rbp+string]; HSTRING
0x180051501  call    ?SetAppExemptState@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEAUHSTRING__@@H@Z; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::SetAppExemptState(HSTRING__ *,int)
0x180051506  jmp     short loc_180051549
0x180051508  cmp     esi, 2
0x18005150b  jnz     short loc_180051526
0x18005150d  lea     r8d, [rsi-1]; int
0x180051511  mov     rdx, [rbp+string]; HSTRING
0x180051515  call    ?SetAppBGState@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEAUHSTRING__@@H@Z; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::SetAppBGState(HSTRING__ *,int)
0x18005151a  mov     ebx, eax
0x18005151c  test    eax, eax
0x18005151e  js      short loc_18005154B
0x180051520  lea     r8d, [rsi-1]
0x180051524  jmp     short loc_1800514FD
0x180051526  cmp     esi, 3
0x180051529  jnz     short loc_18005154B
0x18005152b  xor     r8d, r8d; int
0x18005152e  mov     rdx, [rbp+string]; HSTRING
0x180051532  call    ?SetAppExemptState@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEAUHSTRING__@@H@Z; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::SetAppExemptState(HSTRING__ *,int)
0x180051537  mov     ebx, eax
0x180051539  test    eax, eax
0x18005153b  js      short loc_18005154B
0x18005153d  xor     r8d, r8d; int
0x180051540  mov     rdx, [rbp+string]; HSTRING
0x180051544  call    ?SetAppBGState@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEAUHSTRING__@@H@Z; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::SetAppBGState(HSTRING__ *,int)
0x180051549  mov     ebx, eax
0x18005154b  mov     rcx, [rbp+string]; string
0x18005154f  call    cs:__imp_WindowsDeleteString
0x180051555  mov     [rbp+string], 0
0x18005155d  mov     rcx, rdi
0x180051560  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180051565  mov     eax, ebx
0x180051567  mov     rcx, [rbp+var_10]
0x18005156b  xor     rcx, rsp; StackCookie
0x18005156e  call    __security_check_cookie
0x180051573  add     rsp, 48h
0x180051577  pop     rdi
0x180051578  pop     rsi
0x180051579  pop     rbx
0x18005157a  pop     rbp
0x18005157b  retn
```
