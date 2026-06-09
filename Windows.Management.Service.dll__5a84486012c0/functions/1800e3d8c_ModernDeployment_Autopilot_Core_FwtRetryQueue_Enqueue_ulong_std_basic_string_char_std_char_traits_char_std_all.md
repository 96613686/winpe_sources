# ModernDeployment::Autopilot::Core::FwtRetryQueue::Enqueue(ulong,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1800e3d8c`
- end: `0x1800e4004`
- name: `?Enqueue@FwtRetryQueue@Core@Autopilot@ModernDeployment@@SAJKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `632`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x1800dc524`
- `0x1800deab8`

## callees

- `0x18000b820`
- `0x180067a34`
- `0x180067a54`
- `0x18007748c`
- `0x18007755c`
- `0x1800775c4`
- `0x18008019c`
- `0x1800887b8`
- `0x18008cfa4`
- `0x1800e3d8c`
- `0x1800e400c`
- `0x1800e40a0`
- `0x1800e4314`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e3eef`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e3eef`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800e3f71`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800e3f71`

## string_xrefs

- `0x1800e3dd5`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtretryqueue.cpp`
- `0x1800e3e0e`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtretryqueue.cpp`
- `0x1800e3e39`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtretryqueue.cpp`
- `0x1800e3e89`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtretryqueue.cpp`
- `0x1800e3f10`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtretryqueue.cpp`
- `0x1800e3f83`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtretryqueue.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall ModernDeployment::Autopilot::Core::FwtRetryQueue::Enqueue(unsigned int a1, __int64 a2)
{
  int Count; // eax
  int v6; // eax
  unsigned int v7; // ebx
  const WCHAR *v8; // rax
  HANDLE FileW; // rbx
  const char *v10; // r9
  unsigned int v11; // ebx
  const void *v12; // rax
  const char *v13; // r9
  unsigned int LastError; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-88h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-68h] BYREF
  unsigned int v17[2]; // [rsp+48h] [rbp-60h] BYREF
  _OWORD v18[2]; // [rsp+50h] [rbp-58h] BYREF
  _BYTE v19[32]; // [rsp+70h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl'::`2'::impl) )
  {
    v17[0] = 0;
    Count = ModernDeployment::Autopilot::Core::FwtRetryQueue::GetCount(v17);
    if ( Count < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtretryqueue.cpp",
        (const char *)(unsigned int)Count,
        dwCreationDisposition);
    if ( v17[0] < 0x3E8 )
    {
      v18[0] = 0;
      v18[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v18[0]) = 0;
      v6 = ModernDeployment::Autopilot::Core::EnsureQueueFolder(v18);
      v7 = v6;
      if ( v6 >= 0 )
      {
        ModernDeployment::Autopilot::Core::MakeFilePath(v19, v18, a1);
        v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v19);
        FileW = CreateFileW(v8, 0x40000000u, 0, 0, 2u, 0x80u, 0);
        *(_QWORD *)v17 = FileW;
        if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        {
          NumberOfBytesWritten = 0;
          v12 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
          if ( WriteFile(FileW, v12, *(_DWORD *)(a2 + 16), &NumberOfBytesWritten, 0) )
          {
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v17);
            std::wstring::_Tidy_deallocate(v19);
            std::wstring::_Tidy_deallocate(v18);
            return 0;
          }
          else
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x5C,
                          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\f"
                                        "wtretryqueue.cpp",
                          v13);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v17);
            std::wstring::_Tidy_deallocate(v19);
            std::wstring::_Tidy_deallocate(v18);
            return LastError;
          }
        }
        else
        {
          v11 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x54,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtretryqueue.cpp",
                  v10);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v17);
          std::wstring::_Tidy_deallocate(v19);
          std::wstring::_Tidy_deallocate(v18);
          return v11;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x48,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtretryqueue.cpp",
          (const char *)(unsigned int)v6,
          dwCreationDisposition);
        std::wstring::_Tidy_deallocate(v18);
        return v7;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtretryqueue.cpp",
        (const char *)0x8007006FLL,
        dwCreationDisposition);
      return 2147942511LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtretryqueue.cpp",
      (const char *)0x80004001LL,
      dwCreationDisposition);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x1800e3d8c  mov     [rsp+arg_10], rbx
0x1800e3d91  mov     [rsp+arg_18], rsi
0x1800e3d96  push    rdi
0x1800e3d97  sub     rsp, 0A0h
0x1800e3d9e  mov     rax, cs:__security_cookie
0x1800e3da5  xor     rax, rsp
0x1800e3da8  mov     [rsp+0A8h+var_18], rax
0x1800e3db0  mov     rsi, rdx
0x1800e3db3  mov     edi, ecx
0x1800e3db5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800e3dbc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800e3dc1  test    al, al
0x1800e3dc3  jnz     short loc_1800E3DED
0x1800e3dc5  mov     rcx, [rsp+0A8h]; this
0x1800e3dcd  mov     ebx, 80004001h
0x1800e3dd2  mov     r9d, ebx; char *
0x1800e3dd5  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e3ddc  mov     edx, 3Dh ; '='; void *
0x1800e3de1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3de6  mov     eax, ebx
0x1800e3de8  jmp     loc_1800E3FDE
0x1800e3ded  mov     [rsp+0A8h+var_60], 0
0x1800e3df5  lea     rcx, [rsp+0A8h+var_60]; unsigned int *
0x1800e3dfa  call    ?GetCount@FwtRetryQueue@Core@Autopilot@ModernDeployment@@SAJAEAK@Z; ModernDeployment::Autopilot::Core::FwtRetryQueue::GetCount(ulong &)
0x1800e3dff  mov     rcx, [rsp+0A8h]; this
0x1800e3e07  test    eax, eax
0x1800e3e09  jns     short loc_1800E3E1F
0x1800e3e0b  mov     r9d, eax; char *
0x1800e3e0e  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e3e15  mov     edx, 41h ; 'A'; void *
0x1800e3e1a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e3e1f  cmp     [rsp+0A8h+var_60], 3E8h
0x1800e3e27  jb      short loc_1800E3E51
0x1800e3e29  mov     rcx, [rsp+0A8h]; this
0x1800e3e31  mov     ebx, 8007006Fh
0x1800e3e36  mov     r9d, ebx; char *
0x1800e3e39  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e3e40  mov     edx, 44h ; 'D'; void *
0x1800e3e45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3e4a  mov     eax, ebx
0x1800e3e4c  jmp     loc_1800E3FDE
0x1800e3e51  xorps   xmm0, xmm0
0x1800e3e54  movups  [rsp+0A8h+var_58], xmm0
0x1800e3e59  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800e3e61  movdqu  [rsp+0A8h+var_48], xmm1
0x1800e3e67  xor     eax, eax
0x1800e3e69  mov     word ptr [rsp+0A8h+var_58], ax
0x1800e3e6e  lea     rcx, [rsp+0A8h+var_58]
0x1800e3e73  call    ModernDeployment__Autopilot__Core__EnsureQueueFolder
0x1800e3e78  mov     ebx, eax
0x1800e3e7a  test    eax, eax
0x1800e3e7c  jns     short loc_1800E3EAC
0x1800e3e7e  mov     rcx, [rsp+0A8h]; this
0x1800e3e86  mov     r9d, eax; char *
0x1800e3e89  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e3e90  mov     edx, 48h ; 'H'; void *
0x1800e3e95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3e9a  nop
0x1800e3e9b  lea     rcx, [rsp+0A8h+var_58]
0x1800e3ea0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e3ea5  mov     eax, ebx
0x1800e3ea7  jmp     loc_1800E3FDE
0x1800e3eac  mov     r8d, edi
0x1800e3eaf  lea     rdx, [rsp+0A8h+var_58]
0x1800e3eb4  lea     rcx, [rsp+0A8h+var_38]
0x1800e3eb9  call    ModernDeployment__Autopilot__Core__MakeFilePath
0x1800e3ebe  lea     rcx, [rsp+0A8h+var_38]
0x1800e3ec3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e3ec8  mov     rcx, rax; lpFileName
0x1800e3ecb  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x1800e3ed4  mov     [rsp+0A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800e3edc  mov     [rsp+0A8h+dwCreationDisposition], 2; dwCreationDisposition
0x1800e3ee4  xor     r9d, r9d; lpSecurityAttributes
0x1800e3ee7  xor     r8d, r8d; dwShareMode
0x1800e3eea  mov     edx, 40000000h; dwDesiredAccess
0x1800e3eef  call    cs:__imp_CreateFileW
0x1800e3ef5  mov     rbx, rax
0x1800e3ef8  mov     qword ptr [rsp+0A8h+var_60], rax
0x1800e3efd  inc     rax
0x1800e3f00  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800e3f06  jnz     short loc_1800E3F49
0x1800e3f08  mov     rcx, [rsp+0A8h]; this
0x1800e3f10  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e3f17  mov     edx, 54h ; 'T'; void *
0x1800e3f1c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e3f21  mov     ebx, eax
0x1800e3f23  lea     rcx, [rsp+0A8h+var_60]
0x1800e3f28  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e3f2d  lea     rcx, [rsp+0A8h+var_38]
0x1800e3f32  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e3f37  nop
0x1800e3f38  lea     rcx, [rsp+0A8h+var_58]
0x1800e3f3d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e3f42  mov     eax, ebx
0x1800e3f44  jmp     loc_1800E3FDE
0x1800e3f49  mov     [rsp+0A8h+NumberOfBytesWritten], 0
0x1800e3f51  mov     rcx, rsi
0x1800e3f54  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800e3f59  mov     qword ptr [rsp+0A8h+dwCreationDisposition], 0; lpOverlapped
0x1800e3f62  lea     r9, [rsp+0A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800e3f67  mov     r8d, [rsi+10h]; nNumberOfBytesToWrite
0x1800e3f6b  mov     rdx, rax; lpBuffer
0x1800e3f6e  mov     rcx, rbx; hFile
0x1800e3f71  call    cs:__imp_WriteFile
0x1800e3f77  test    eax, eax
0x1800e3f79  jnz     short loc_1800E3FB7
0x1800e3f7b  mov     rcx, [rsp+0A8h]; this
0x1800e3f83  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e3f8a  lea     edx, [rax+5Ch]; void *
0x1800e3f8d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e3f92  mov     ebx, eax
0x1800e3f94  lea     rcx, [rsp+0A8h+var_60]
0x1800e3f99  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e3f9e  lea     rcx, [rsp+0A8h+var_38]
0x1800e3fa3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e3fa8  nop
0x1800e3fa9  lea     rcx, [rsp+0A8h+var_58]
0x1800e3fae  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e3fb3  mov     eax, ebx
0x1800e3fb5  jmp     short loc_1800E3FDE
0x1800e3fb7  lea     rcx, [rsp+0A8h+var_60]
0x1800e3fbc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e3fc1  lea     rcx, [rsp+0A8h+var_38]
0x1800e3fc6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e3fcb  nop
0x1800e3fcc  lea     rcx, [rsp+0A8h+var_58]
0x1800e3fd1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e3fd6  xor     eax, eax
0x1800e3fd8  jmp     short loc_1800E3FDE
0x1800e3fda  mov     eax, [rsp+0A8h+NumberOfBytesWritten]
0x1800e3fde  mov     rcx, [rsp+0A8h+var_18]
0x1800e3fe6  xor     rcx, rsp; StackCookie
0x1800e3fe9  call    __security_check_cookie
0x1800e3fee  lea     r11, [rsp+0A8h+var_8]
0x1800e3ff6  mov     rbx, [r11+20h]
0x1800e3ffa  mov     rsi, [r11+28h]
0x1800e3ffe  mov     rsp, r11
0x1800e4001  pop     rdi
0x1800e4002  retn
```
