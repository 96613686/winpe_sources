# SystemSettings::BatteryUsageHandlers::DisplayManagerSingleton::AnyDisplaySupportsBrightness(void)

- ea: `0x180050004`
- end: `0x1800500b0`
- name: `?AnyDisplaySupportsBrightness@DisplayManagerSingleton@BatteryUsageHandlers@SystemSettings@@QEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(SystemSettings::BatteryUsageHandlers::DisplayManagerSingleton *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800369c0`

## callees

- `0x18000d47c`
- `0x18004fb44`
- `0x18004fe54`
- `0x180050004`
- `0x1800505e8`
- `0x180050950`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180050051`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180050051`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall SystemSettings::BatteryUsageHandlers::DisplayManagerSingleton::AnyDisplaySupportsBrightness(
        SystemSettings::BatteryUsageHandlers::DisplayManagerSingleton *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rdi
  char v4; // bl
  _QWORD *v6; // [rsp+40h] [rbp+8h] BYREF
  _QWORD *v7; // [rsp+48h] [rbp+10h] BYREF

  v2 = std::_Allocate<16,std::_Default_allocate_traits>(0xD0u);
  v3 = v2 + 4;
  v6 = v2 + 4;
  v2[25] = this;
  v2[4] = SystemSettings::BatteryUsageHandlers::DisplayManagerSingleton::GetDEMSupportedTargets__ResumeCoro_1;
  *((_DWORD *)v2 + 10) = 65538;
  v4 = 0;
  *v2 = 0;
  v2[1] = 0;
  v2[2] = 0;
  __ExceptionPtrCreate(v2 + 1);
  v7 = v3;
  *((_BYTE *)v3 + 160) = 0;
  std::experimental::generator<winrt::Windows::Internal::Graphics::Display::DisplayEnhancementManagement::DisplayEnhancementManagement,std::allocator<char>>::begin(
    &v7,
    &v6);
  while ( v6 )
  {
    if ( (unsigned __int8)winrt::impl::consume_Windows_Internal_Graphics_Display_DisplayEnhancementManagement_IDisplayEnhancementManagement<winrt::Windows::Internal::Graphics::Display::DisplayEnhancementManagement::IDisplayEnhancementManagement>::IsBrightnessCapable(*(v6 - 4)) )
    {
      v4 = 1;
      break;
    }
    std::experimental::generator<winrt::Windows::Internal::Graphics::Display::DisplayEnhancementManagement::DisplayEnhancementManagement,std::allocator<char>>::iterator::operator++(&v6);
  }
  std::experimental::generator<winrt::Windows::Internal::Graphics::Display::DisplayEnhancementManagement::DisplayEnhancementManagement,std::allocator<char>>::~generator<winrt::Windows::Internal::Graphics::Display::DisplayEnhancementManagement::DisplayEnhancementManagement,std::allocator<char>>(&v7);
  return v4;
}

```

## disassembly

```asm
0x180050004  mov     [rsp+arg_10], rbx
0x180050009  push    rdi
0x18005000a  sub     rsp, 30h
0x18005000e  mov     rbx, rcx
0x180050011  mov     ecx, 0D0h
0x180050016  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18005001b  mov     [rsp+38h+arg_0], rax
0x180050020  lea     rdi, [rax+20h]
0x180050024  mov     [rsp+38h+arg_0], rdi
0x180050029  mov     [rdi+0A8h], rbx
0x180050030  lea     rcx, SystemSettings__BatteryUsageHandlers__DisplayManagerSingleton__GetDEMSupportedTargets$_ResumeCoro$1
0x180050037  mov     [rdi], rcx
0x18005003a  mov     dword ptr [rdi+8], 10002h
0x180050041  xor     ebx, ebx
0x180050043  mov     [rax], rbx
0x180050046  lea     rcx, [rdi-18h]
0x18005004a  mov     [rcx], rbx
0x18005004d  mov     [rcx+8], rbx
0x180050051  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180050057  nop
0x180050058  mov     [rsp+38h+arg_8], rdi
0x18005005d  xor     eax, eax
0x18005005f  mov     [rdi+0A0h], al
0x180050065  lea     rdx, [rsp+38h+arg_0]
0x18005006a  lea     rcx, [rsp+38h+arg_8]
0x18005006f  call    ?begin@?$generator@UDisplayEnhancementManagement@1Display@Graphics@Internal@Windows@winrt@@V?$allocator@D@std@@@experimental@std@@QEAA?AUiterator@123@XZ; std::experimental::generator<winrt::Windows::Internal::Graphics::Display::DisplayEnhancementManagement::DisplayEnhancementManagement,std::allocator<char>>::begin(void)
0x180050074  mov     rcx, [rsp+38h+arg_0]
0x180050079  test    rcx, rcx
0x18005007c  jz      short loc_180050099
0x18005007e  mov     rcx, [rcx-20h]
0x180050082  call    ?IsBrightnessCapable@?$consume_Windows_Internal_Graphics_Display_DisplayEnhancementManagement_IDisplayEnhancementManagement@UIDisplayEnhancementManagement@DisplayEnhancementManagement@Display@Graphics@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Graphics_Display_DisplayEnhancementManagement_IDisplayEnhancementManagement<winrt::Windows::Internal::Graphics::Display::DisplayEnhancementManagement::IDisplayEnhancementManagement>::IsBrightnessCapable(void)
0x180050087  test    al, al
0x180050089  jnz     short loc_180050097
0x18005008b  lea     rcx, [rsp+38h+arg_0]
0x180050090  call    ??Eiterator@?$generator@UDisplayEnhancementManagement@1Display@Graphics@Internal@Windows@winrt@@V?$allocator@D@std@@@experimental@std@@QEAAAEAU0123@XZ; std::experimental::generator<winrt::Windows::Internal::Graphics::Display::DisplayEnhancementManagement::DisplayEnhancementManagement,std::allocator<char>>::iterator::operator++(void)
0x180050095  jmp     short loc_180050074
0x180050097  mov     bl, 1
0x180050099  lea     rcx, [rsp+38h+arg_8]
0x18005009e  call    ??1?$generator@UDisplayEnhancementManagement@1Display@Graphics@Internal@Windows@winrt@@V?$allocator@D@std@@@experimental@std@@QEAA@XZ; std::experimental::generator<winrt::Windows::Internal::Graphics::Display::DisplayEnhancementManagement::DisplayEnhancementManagement,std::allocator<char>>::~generator<winrt::Windows::Internal::Graphics::Display::DisplayEnhancementManagement::DisplayEnhancementManagement,std::allocator<char>>(void)
0x1800500a3  mov     al, bl
0x1800500a5  mov     rbx, [rsp+38h+arg_10]
0x1800500aa  add     rsp, 30h
0x1800500ae  pop     rdi
0x1800500af  retn
```
