# ModernDeployment::Autopilot::Core::FwtRetryQueue::Enqueue(ulong,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1800e66f4`
- end: `0x1800e6978`
- name: `?Enqueue@FwtRetryQueue@Core@Autopilot@ModernDeployment@@SAJKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `644`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x1800ded04`
- `0x1800e12c0`

## callees

- `0x18000b8f0`
- `0x180067e34`
- `0x180067e54`
- `0x180077d0c`
- `0x180077de0`
- `0x180077e54`
- `0x180080bac`
- `0x180089660`
- `0x18008e088`
- `0x1800e66f4`
- `0x1800e6980`
- `0x1800e6a20`
- `0x1800e6ca4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e6857`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e6857`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800e68df`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800e68df`

## string_xrefs

- `0x1800e673d`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtretryqueue.cpp`
- `0x1800e6776`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtretryqueue.cpp`
- `0x1800e67a1`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtretryqueue.cpp`
- `0x1800e67f1`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtretryqueue.cpp`
- `0x1800e687e`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtretryqueue.cpp`
- `0x1800e68f7`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtretryqueue.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
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
0x1800e66f4  mov     [rsp+arg_10], rbx
0x1800e66f9  mov     [rsp+arg_18], rsi
0x1800e66fe  push    rdi
0x1800e66ff  sub     rsp, 0A0h
0x1800e6706  mov     rax, cs:__security_cookie
0x1800e670d  xor     rax, rsp
0x1800e6710  mov     [rsp+0A8h+var_18], rax
0x1800e6718  mov     rsi, rdx
0x1800e671b  mov     edi, ecx
0x1800e671d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800e6724  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800e6729  test    al, al
0x1800e672b  jnz     short loc_1800E6755
0x1800e672d  mov     rcx, [rsp+0A8h]; this
0x1800e6735  mov     ebx, 80004001h
0x1800e673a  mov     r9d, ebx; char *
0x1800e673d  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e6744  mov     edx, 3Dh ; '='; void *
0x1800e6749  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e674e  mov     eax, ebx
0x1800e6750  jmp     loc_1800E6952
0x1800e6755  mov     [rsp+0A8h+var_60], 0
0x1800e675d  lea     rcx, [rsp+0A8h+var_60]; unsigned int *
0x1800e6762  call    ?GetCount@FwtRetryQueue@Core@Autopilot@ModernDeployment@@SAJAEAK@Z; ModernDeployment::Autopilot::Core::FwtRetryQueue::GetCount(ulong &)
0x1800e6767  mov     rcx, [rsp+0A8h]; this
0x1800e676f  test    eax, eax
0x1800e6771  jns     short loc_1800E6787
0x1800e6773  mov     r9d, eax; char *
0x1800e6776  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e677d  mov     edx, 41h ; 'A'; void *
0x1800e6782  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e6787  cmp     [rsp+0A8h+var_60], 3E8h
0x1800e678f  jb      short loc_1800E67B9
0x1800e6791  mov     rcx, [rsp+0A8h]; this
0x1800e6799  mov     ebx, 8007006Fh
0x1800e679e  mov     r9d, ebx; char *
0x1800e67a1  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e67a8  mov     edx, 44h ; 'D'; void *
0x1800e67ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e67b2  mov     eax, ebx
0x1800e67b4  jmp     loc_1800E6952
0x1800e67b9  xorps   xmm0, xmm0
0x1800e67bc  movups  [rsp+0A8h+var_58], xmm0
0x1800e67c1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800e67c9  movdqu  [rsp+0A8h+var_48], xmm1
0x1800e67cf  xor     eax, eax
0x1800e67d1  mov     word ptr [rsp+0A8h+var_58], ax
0x1800e67d6  lea     rcx, [rsp+0A8h+var_58]
0x1800e67db  call    ModernDeployment__Autopilot__Core__EnsureQueueFolder
0x1800e67e0  mov     ebx, eax
0x1800e67e2  test    eax, eax
0x1800e67e4  jns     short loc_1800E6814
0x1800e67e6  mov     rcx, [rsp+0A8h]; this
0x1800e67ee  mov     r9d, eax; char *
0x1800e67f1  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e67f8  mov     edx, 48h ; 'H'; void *
0x1800e67fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e6802  nop
0x1800e6803  lea     rcx, [rsp+0A8h+var_58]
0x1800e6808  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e680d  mov     eax, ebx
0x1800e680f  jmp     loc_1800E6952
0x1800e6814  mov     r8d, edi
0x1800e6817  lea     rdx, [rsp+0A8h+var_58]
0x1800e681c  lea     rcx, [rsp+0A8h+var_38]
0x1800e6821  call    ModernDeployment__Autopilot__Core__MakeFilePath
0x1800e6826  lea     rcx, [rsp+0A8h+var_38]
0x1800e682b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e6830  mov     rcx, rax; lpFileName
0x1800e6833  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x1800e683c  mov     [rsp+0A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800e6844  mov     [rsp+0A8h+dwCreationDisposition], 2; dwCreationDisposition
0x1800e684c  xor     r9d, r9d; lpSecurityAttributes
0x1800e684f  xor     r8d, r8d; dwShareMode
0x1800e6852  mov     edx, 40000000h; dwDesiredAccess
0x1800e6857  call    cs:__imp_CreateFileW
0x1800e685e  nop     dword ptr [rax+rax+00h]
0x1800e6863  mov     rbx, rax
0x1800e6866  mov     qword ptr [rsp+0A8h+var_60], rax
0x1800e686b  inc     rax
0x1800e686e  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800e6874  jnz     short loc_1800E68B7
0x1800e6876  mov     rcx, [rsp+0A8h]; this
0x1800e687e  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e6885  mov     edx, 54h ; 'T'; void *
0x1800e688a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e688f  mov     ebx, eax
0x1800e6891  lea     rcx, [rsp+0A8h+var_60]
0x1800e6896  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e689b  lea     rcx, [rsp+0A8h+var_38]
0x1800e68a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e68a5  nop
0x1800e68a6  lea     rcx, [rsp+0A8h+var_58]
0x1800e68ab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e68b0  mov     eax, ebx
0x1800e68b2  jmp     loc_1800E6952
0x1800e68b7  mov     [rsp+0A8h+NumberOfBytesWritten], 0
0x1800e68bf  mov     rcx, rsi
0x1800e68c2  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800e68c7  mov     qword ptr [rsp+0A8h+dwCreationDisposition], 0; lpOverlapped
0x1800e68d0  lea     r9, [rsp+0A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800e68d5  mov     r8d, [rsi+10h]; nNumberOfBytesToWrite
0x1800e68d9  mov     rdx, rax; lpBuffer
0x1800e68dc  mov     rcx, rbx; hFile
0x1800e68df  call    cs:__imp_WriteFile
0x1800e68e6  nop     dword ptr [rax+rax+00h]
0x1800e68eb  test    eax, eax
0x1800e68ed  jnz     short loc_1800E692B
0x1800e68ef  mov     rcx, [rsp+0A8h]; this
0x1800e68f7  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e68fe  lea     edx, [rax+5Ch]; void *
0x1800e6901  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e6906  mov     ebx, eax
0x1800e6908  lea     rcx, [rsp+0A8h+var_60]
0x1800e690d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e6912  lea     rcx, [rsp+0A8h+var_38]
0x1800e6917  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e691c  nop
0x1800e691d  lea     rcx, [rsp+0A8h+var_58]
0x1800e6922  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e6927  mov     eax, ebx
0x1800e6929  jmp     short loc_1800E6952
0x1800e692b  lea     rcx, [rsp+0A8h+var_60]
0x1800e6930  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e6935  lea     rcx, [rsp+0A8h+var_38]
0x1800e693a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e693f  nop
0x1800e6940  lea     rcx, [rsp+0A8h+var_58]
0x1800e6945  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e694a  xor     eax, eax
0x1800e694c  jmp     short loc_1800E6952
0x1800e694e  mov     eax, [rsp+0A8h+NumberOfBytesWritten]
0x1800e6952  mov     rcx, [rsp+0A8h+var_18]
0x1800e695a  xor     rcx, rsp; StackCookie
0x1800e695d  call    __security_check_cookie
0x1800e6962  lea     r11, [rsp+0A8h+var_8]
0x1800e696a  mov     rbx, [r11+20h]
0x1800e696e  mov     rsi, [r11+28h]
0x1800e6972  mov     rsp, r11
0x1800e6975  pop     rdi
0x1800e6976  retn
```
