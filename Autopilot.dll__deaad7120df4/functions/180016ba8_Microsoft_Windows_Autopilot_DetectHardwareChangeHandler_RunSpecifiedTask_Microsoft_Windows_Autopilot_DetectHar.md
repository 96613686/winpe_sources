# Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::RunSpecifiedTask(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::TaskHandler,bool)

- ea: `0x180016ba8`
- end: `0x180016cdb`
- name: `?RunSpecifiedTask@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@SAJW4TaskHandler@1234@_N@Z`
- size: `307`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180017620`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180013de4`
- `0x180015db4`
- `0x180016ba8`
- `0x180017a20`
- `0x18001dea4`
- `0x18001e450`
- `0x18002f010`

## string_xrefs

- `0x180016c29`: `onecoreuap\admin\moderndeployment\autopilot\dll\detecthardwarechange.cpp`
- `0x180016c71`: `onecoreuap\admin\moderndeployment\autopilot\dll\detecthardwarechange.cpp`

## pseudocode

```c
__int64 Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::RunSpecifiedTask()
{
  __int64 TaskNameForType; // rax
  __int64 v1; // r8
  int NamedAutopilotTask; // eax
  unsigned int v3; // ebx
  int v4; // eax
  __int64 v6; // [rsp+20h] [rbp-40h] BYREF
  char v7[4]; // [rsp+28h] [rbp-38h] BYREF
  int v8; // [rsp+2Ch] [rbp-34h]
  int v9; // [rsp+30h] [rbp-30h]
  _OWORD v10[2]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  TaskNameForType = Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::GetTaskNameForType();
  memset(v10, 0, sizeof(v10));
  v1 = -1;
  do
    ++v1;
  while ( *(_WORD *)(TaskNameForType + 2 * v1) );
  std::wstring::_Construct<1,unsigned short const *>(v10, TaskNameForType);
  v8 = 60000;
  v9 = 1000;
  v7[0] = 1;
  v6 = 0;
  NamedAutopilotTask = Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask(v10, &v6);
  v3 = NamedAutopilotTask;
  if ( NamedAutopilotTask >= 0 )
  {
    v4 = Microsoft::Windows::Autopilot::AutoPilotTasks::RunTask(&v6, v10, v7);
    v3 = v4;
    if ( v4 >= 0 )
    {
      if ( v6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      v3 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10F,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\detecthardwarechange.cpp",
        (const char *)(unsigned int)v4,
        v6);
      if ( v6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\detecthardwarechange.cpp",
      (const char *)(unsigned int)NamedAutopilotTask,
      v6);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  std::wstring::_Tidy_deallocate(v10);
  return v3;
}

```

## disassembly

```asm
0x180016ba8  mov     [rsp-8+arg_0], rbx
0x180016bad  mov     [rsp-8+arg_8], rdi
0x180016bb2  push    rbp
0x180016bb3  mov     rbp, rsp
0x180016bb6  sub     rsp, 60h
0x180016bba  mov     rax, cs:__security_cookie
0x180016bc1  xor     rax, rsp
0x180016bc4  mov     [rbp+var_8], rax
0x180016bc8  call    ?GetTaskNameForType@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@CAQEBGW4TaskHandler@1234@@Z; Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::GetTaskNameForType(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::TaskHandler)
0x180016bcd  xorps   xmm0, xmm0
0x180016bd0  movups  [rbp+var_28], xmm0
0x180016bd4  xorps   xmm1, xmm1
0x180016bd7  movdqu  [rbp+var_18], xmm1
0x180016bdc  or      r8, 0FFFFFFFFFFFFFFFFh
0x180016be0  xor     edi, edi
0x180016be2  inc     r8
0x180016be5  cmp     [rax+r8*2], di
0x180016bea  jnz     short loc_180016BE2
0x180016bec  mov     rdx, rax
0x180016bef  lea     rcx, [rbp+var_28]
0x180016bf3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180016bf8  nop
0x180016bf9  mov     [rbp+var_34], 0EA60h
0x180016c00  mov     [rbp+var_30], 3E8h
0x180016c07  mov     [rbp+var_38], 1
0x180016c0b  mov     [rbp+var_40], rdi
0x180016c0f  lea     rdx, [rbp+var_40]
0x180016c13  lea     rcx, [rbp+var_28]
0x180016c17  call    ?GetNamedAutopilotTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIRegisteredTask@@@WRL@4@@Z; Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask(std::wstring const &,Microsoft::WRL::ComPtr<IRegisteredTask> &)
0x180016c1c  mov     ebx, eax
0x180016c1e  test    eax, eax
0x180016c20  jns     short loc_180016C53
0x180016c22  mov     rcx, [rbp+8]; this
0x180016c26  mov     r9d, eax; char *
0x180016c29  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\moderndeployment\\au"...
0x180016c30  mov     edx, 10Ch; void *
0x180016c35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016c3a  nop
0x180016c3b  mov     rcx, [rbp+var_40]
0x180016c3f  test    rcx, rcx
0x180016c42  jz      short loc_180016C51
0x180016c44  mov     rax, [rcx]
0x180016c47  mov     rax, [rax+10h]
0x180016c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c50  nop
0x180016c51  jmp     short loc_180016CB3
0x180016c53  lea     r8, [rbp+var_38]
0x180016c57  lea     rdx, [rbp+var_28]
0x180016c5b  lea     rcx, [rbp+var_40]
0x180016c5f  call    ?RunTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEAV?$ComPtr@UIRegisteredTask@@@WRL@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUBlockOnTaskCompletion@1234@@Z; Microsoft::Windows::Autopilot::AutoPilotTasks::RunTask(Microsoft::WRL::ComPtr<IRegisteredTask> &,std::wstring const &,Microsoft::Windows::Autopilot::AutoPilotTasks::BlockOnTaskCompletion const &)
0x180016c64  mov     ebx, eax
0x180016c66  test    eax, eax
0x180016c68  jns     short loc_180016C9B
0x180016c6a  mov     rcx, [rbp+8]; this
0x180016c6e  mov     r9d, eax; char *
0x180016c71  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\moderndeployment\\au"...
0x180016c78  mov     edx, 10Fh; void *
0x180016c7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016c82  nop
0x180016c83  mov     rcx, [rbp+var_40]
0x180016c87  test    rcx, rcx
0x180016c8a  jz      short loc_180016C99
0x180016c8c  mov     rax, [rcx]
0x180016c8f  mov     rax, [rax+10h]
0x180016c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c98  nop
0x180016c99  jmp     short loc_180016CB3
0x180016c9b  mov     rcx, [rbp+var_40]
0x180016c9f  test    rcx, rcx
0x180016ca2  jz      short loc_180016CB1
0x180016ca4  mov     rax, [rcx]
0x180016ca7  mov     rax, [rax+10h]
0x180016cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cb0  nop
0x180016cb1  mov     ebx, edi
0x180016cb3  lea     rcx, [rbp+var_28]
0x180016cb7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016cbc  mov     eax, ebx
0x180016cbe  mov     rcx, [rbp+var_8]
0x180016cc2  xor     rcx, rsp; StackCookie
0x180016cc5  call    __security_check_cookie
0x180016cca  mov     rbx, [rsp+60h+arg_0]
0x180016ccf  mov     rdi, [rsp+60h+arg_8]
0x180016cd4  add     rsp, 60h
0x180016cd8  pop     rbp
0x180016cd9  retn
```
