# UXFrame::RequestLifecycleEvent(UXFrameHelpers::PropertyKeys::LifecycleEventName)

- ea: `0x180049bf8`
- end: `0x180049da4`
- name: `?RequestLifecycleEvent@UXFrame@@AEAAXW4LifecycleEventName@PropertyKeys@UXFrameHelpers@@@Z`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800444f4`

## callees

- `0x1800043f4`
- `0x1800088ac`
- `0x18000d0f0`
- `0x18000d810`
- `0x18001047c`
- `0x180017044`
- `0x180039574`
- `0x18003c228`
- `0x18003c86c`
- `0x18003e968`
- `0x180049bf8`
- `0x18004ae28`
- `0x180050128`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180049c6b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180049c6b`

## string_xrefs

- `0x180049d92`: `pcshell\shell\uxframe\dll\UXFrame.cpp`
- `0x180049c2a`: `LauncherProcessID`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall UXFrame::RequestLifecycleEvent(_QWORD *a1, int a2)
{
  DWORD v3; // ebx
  HANDLE v4; // rsi
  __int64 *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  std::_Ref_count_base *v8; // rcx
  RTL_SRWLOCK *v9; // rbx
  __int64 *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // eax
  HANDLE v14; // [rsp+20h] [rbp-59h] BYREF
  std::_Ref_count_base *v15; // [rsp+28h] [rbp-51h]
  DWORD v16; // [rsp+30h] [rbp-49h] BYREF
  HANDLE v17; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v18[8]; // [rsp+40h] [rbp-39h] BYREF
  std::_Ref_count_base *v19; // [rsp+48h] [rbp-31h]
  _QWORD v20[9]; // [rsp+50h] [rbp-29h] BYREF
  __int128 v21; // [rsp+98h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( a2 )
  {
    v13 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x5CB,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
      (const char *)v13,
      (int)v14);
  }
  if ( !a1[88] )
  {
    v17 = 0;
    winrt::hstring::hstring((winrt::hstring *)&v14, L"LauncherProcessID");
    v3 = ValueSetUtils::get_value_or<unsigned int,winrt::Windows::Foundation::Collections::ValueSet>(&v14, a1 + 22);
    v16 = v3;
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v14);
    if ( v3 && (v4 = OpenProcess(0x100000u, 0, v3), (v17 = v4) != 0) )
    {
      v5 = (__int64 *)std::make_shared<ThreadpoolProcessWatcher,>(&v14);
      v6 = *v5;
      v7 = v5[1];
      *v5 = 0;
      v5[1] = 0;
      a1[88] = v6;
      v8 = (std::_Ref_count_base *)a1[89];
      a1[89] = v7;
      if ( v8 )
        std::_Ref_count_base::_Decref(v8);
      if ( v15 )
        std::_Ref_count_base::_Decref(v15);
      v9 = (RTL_SRWLOCK *)a1[88];
      v10 = (__int64 *)std::enable_shared_from_this<UXFrame>::shared_from_this(a1 + 5, v18);
      v20[8] = a1;
      v11 = *v10;
      v12 = v10[1];
      *v10 = 0;
      v10[1] = 0;
      v20[0] = off_18005E6A0;
      v20[1] = a1;
      v20[2] = v11;
      v20[3] = v12;
      v21 = 0;
      v20[7] = v20;
      v14 = v4;
      v17 = 0;
      ThreadpoolProcessWatcher::Start(v9, &v14, (__int64)v20);
      std::_Func_class<void,>::_Tidy(v20);
      if ( v19 )
        std::_Ref_count_base::_Decref(v19);
    }
    else
    {
      v14 = a1;
      UXFrameTelemetry::UnableToMonitorLauncherProcess<UXFrame *,unsigned int &>(&v14, &v16);
    }
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
  }
}

```

## disassembly

```asm
0x180049bf8  push    rbp
0x180049bfa  push    rbx
0x180049bfb  push    rsi
0x180049bfc  push    rdi
0x180049bfd  lea     rbp, [rsp-3Fh]
0x180049c02  sub     rsp, 0B8h
0x180049c09  mov     rdi, rcx
0x180049c0c  test    edx, edx
0x180049c0e  jnz     loc_180049D81
0x180049c14  cmp     qword ptr [rcx+2C0h], 0
0x180049c1c  jnz     loc_180049D75
0x180049c22  mov     [rbp+57h+var_98], 0
0x180049c2a  lea     rdx, aLauncherproces; "LauncherProcessID"
0x180049c31  lea     rcx, [rbp+57h+var_B0]; this
0x180049c35  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180049c3a  nop
0x180049c3b  lea     rdx, [rdi+0B0h]
0x180049c42  lea     rcx, [rbp+57h+var_B0]
0x180049c46  call    ??$get_value_or@IUValueSet@Collections@Foundation@Windows@winrt@@@ValueSetUtils@@YAIAEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@2@I@Z; ValueSetUtils::get_value_or<uint,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &,uint)
0x180049c4b  mov     ebx, eax
0x180049c4d  mov     [rbp+57h+var_A0], eax
0x180049c50  lea     rcx, [rbp+57h+var_B0]
0x180049c54  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180049c59  test    ebx, ebx
0x180049c5b  jz      loc_180049D5A
0x180049c61  mov     r8d, ebx; dwProcessId
0x180049c64  xor     edx, edx; bInheritHandle
0x180049c66  mov     ecx, 100000h; dwDesiredAccess
0x180049c6b  call    cs:__imp_OpenProcess
0x180049c71  mov     rsi, rax
0x180049c74  mov     [rbp+57h+var_98], rax
0x180049c78  test    rax, rax
0x180049c7b  jz      loc_180049D5A
0x180049c81  lea     rcx, [rbp+57h+var_B0]
0x180049c85  call    ??$make_shared@VThreadpoolProcessWatcher@@$$V@std@@YA?AV?$shared_ptr@VThreadpoolProcessWatcher@@@0@XZ; std::make_shared<ThreadpoolProcessWatcher,>(void)
0x180049c8a  mov     rcx, [rax]
0x180049c8d  mov     rdx, [rax+8]
0x180049c91  mov     qword ptr [rax], 0
0x180049c98  mov     qword ptr [rax+8], 0
0x180049ca0  mov     [rdi+2C0h], rcx
0x180049ca7  mov     rcx, [rdi+2C8h]; this
0x180049cae  mov     [rdi+2C8h], rdx
0x180049cb5  test    rcx, rcx
0x180049cb8  jz      short loc_180049CBF
0x180049cba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049cbf  mov     rcx, [rbp+57h+var_A8]; this
0x180049cc3  test    rcx, rcx
0x180049cc6  jz      short loc_180049CCD
0x180049cc8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049ccd  mov     rbx, [rdi+2C0h]
0x180049cd4  lea     rcx, [rdi+28h]
0x180049cd8  lea     rdx, [rbp+57h+var_90]
0x180049cdc  call    ?shared_from_this@?$enable_shared_from_this@VUXFrame@@@std@@QEAA?AV?$shared_ptr@VUXFrame@@@2@XZ; std::enable_shared_from_this<UXFrame>::shared_from_this(void)
0x180049ce1  nop
0x180049ce2  mov     [rbp+57h+var_40], rdi
0x180049ce6  mov     rcx, [rax]
0x180049ce9  mov     rdx, [rax+8]
0x180049ced  mov     qword ptr [rax], 0
0x180049cf4  mov     qword ptr [rax+8], 0
0x180049cfc  lea     rax, off_18005E6A0
0x180049d03  mov     [rbp+57h+var_80], rax
0x180049d07  mov     [rbp+57h+var_78], rdi
0x180049d0b  mov     [rbp+57h+var_70], rcx
0x180049d0f  mov     [rbp+57h+var_68], rdx
0x180049d13  xorps   xmm0, xmm0
0x180049d16  movdqu  [rbp+57h+var_38], xmm0
0x180049d1b  lea     rax, [rbp+57h+var_80]
0x180049d1f  mov     [rbp+57h+var_48], rax
0x180049d23  mov     [rbp+57h+var_B0], rsi
0x180049d27  mov     [rbp+57h+var_98], 0
0x180049d2f  lea     r8, [rbp+57h+var_80]
0x180049d33  lea     rdx, [rbp+57h+var_B0]
0x180049d37  mov     rcx, rbx
0x180049d3a  call    ?Start@ThreadpoolProcessWatcher@@QEAAXV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$$QEAV?$function@$$A6AXXZ@std@@PEAU_FILETIME@@@Z; ThreadpoolProcessWatcher::Start(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::function<void (void)> &&,_FILETIME *)
0x180049d3f  nop
0x180049d40  lea     rcx, [rbp+57h+var_80]
0x180049d44  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180049d49  nop
0x180049d4a  mov     rcx, [rbp+57h+var_88]; this
0x180049d4e  test    rcx, rcx
0x180049d51  jz      short loc_180049D6C
0x180049d53  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049d58  jmp     short loc_180049D6C
0x180049d5a  mov     [rbp+57h+var_B0], rdi
0x180049d5e  lea     rdx, [rbp+57h+var_A0]
0x180049d62  lea     rcx, [rbp+57h+var_B0]
0x180049d66  call    ??$UnableToMonitorLauncherProcess@PEAVUXFrame@@AEAI@UXFrameTelemetry@@SAX$$QEAPEAVUXFrame@@AEAI@Z; UXFrameTelemetry::UnableToMonitorLauncherProcess<UXFrame *,uint &>(UXFrame * &&,uint &)
0x180049d6b  nop
0x180049d6c  lea     rcx, [rbp+57h+var_98]
0x180049d70  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180049d75  add     rsp, 0B8h
0x180049d7c  pop     rdi
0x180049d7d  pop     rsi
0x180049d7e  pop     rbx
0x180049d7f  pop     rbp
0x180049d80  retn
0x180049d81  mov     ecx, 80070057h
0x180049d86  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180049d8b  mov     r9d, eax; char *
0x180049d8e  mov     rcx, [rbp+5Fh]; this
0x180049d92  lea     r8, aPcshellShellUx_2; "pcshell\\shell\\uxframe\\dll\\UXFrame.c"...
0x180049d99  mov     edx, 5CBh; void *
0x180049d9e  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
```
