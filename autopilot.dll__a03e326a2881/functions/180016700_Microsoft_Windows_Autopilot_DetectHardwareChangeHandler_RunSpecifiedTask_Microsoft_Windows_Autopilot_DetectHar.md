# Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::RunSpecifiedTask(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::TaskHandler,bool)

- ea: `0x180016700`
- end: `0x180016832`
- name: `?RunSpecifiedTask@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@SAJW4TaskHandler@1234@_N@Z`
- size: `306`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180017100`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x180013a40`
- `0x180015978`
- `0x180016700`
- `0x1800174f0`
- `0x18001d70c`
- `0x18001dc64`
- `0x18002e010`

## string_xrefs

- `0x180016781`: `onecoreuap\admin\moderndeployment\autopilot\dll\detecthardwarechange.cpp`
- `0x1800167c9`: `onecoreuap\admin\moderndeployment\autopilot\dll\detecthardwarechange.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::RunSpecifiedTask()
{
  const wchar_t *TaskNameForType; // rax
  __int64 v1; // r8
  int NamedAutopilotTask; // eax
  unsigned int v3; // ebx
  int v4; // eax
  __int64 *v6; // [rsp+20h] [rbp-40h] BYREF
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
  while ( TaskNameForType[v1] );
  std::wstring::_Construct<1,unsigned short const *>(v10, TaskNameForType, v1);
  v8 = 60000;
  v9 = 1000;
  v7[0] = 1;
  v6 = 0;
  NamedAutopilotTask = Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask(v10, (__int64 *)&v6);
  v3 = NamedAutopilotTask;
  if ( NamedAutopilotTask >= 0 )
  {
    v4 = Microsoft::Windows::Autopilot::AutoPilotTasks::RunTask(&v6, (const OLECHAR *)v10, (__int64)v7);
    v3 = v4;
    if ( v4 >= 0 )
    {
      if ( v6 )
        (*(void (__fastcall **)(__int64 *))(*v6 + 16))(v6);
      v3 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10F,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\detecthardwarechange.cpp",
        (const char *)(unsigned int)v4,
        (int)v6);
      if ( v6 )
        (*(void (__fastcall **)(__int64 *))(*v6 + 16))(v6);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\detecthardwarechange.cpp",
      (const char *)(unsigned int)NamedAutopilotTask,
      (int)v6);
    if ( v6 )
      (*(void (__fastcall **)(__int64 *))(*v6 + 16))(v6);
  }
  std::wstring::_Tidy_deallocate(v10);
  return v3;
}

```

## disassembly

```asm
0x180016700  mov     [rsp-8+arg_0], rbx
0x180016705  mov     [rsp-8+arg_8], rdi
0x18001670a  push    rbp
0x18001670b  mov     rbp, rsp
0x18001670e  sub     rsp, 60h
0x180016712  mov     rax, cs:__security_cookie
0x180016719  xor     rax, rsp
0x18001671c  mov     [rbp+var_8], rax
0x180016720  call    ?GetTaskNameForType@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@CAQEBGW4TaskHandler@1234@@Z; Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::GetTaskNameForType(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::TaskHandler)
0x180016725  xorps   xmm0, xmm0
0x180016728  movups  [rbp+var_28], xmm0
0x18001672c  xorps   xmm1, xmm1
0x18001672f  movdqu  [rbp+var_18], xmm1
0x180016734  or      r8, 0FFFFFFFFFFFFFFFFh
0x180016738  xor     edi, edi
0x18001673a  inc     r8
0x18001673d  cmp     [rax+r8*2], di
0x180016742  jnz     short loc_18001673A
0x180016744  mov     rdx, rax
0x180016747  lea     rcx, [rbp+var_28]
0x18001674b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180016750  nop
0x180016751  mov     [rbp+var_34], 0EA60h
0x180016758  mov     [rbp+var_30], 3E8h
0x18001675f  mov     [rbp+var_38], 1
0x180016763  mov     [rbp+var_40], rdi
0x180016767  lea     rdx, [rbp+var_40]
0x18001676b  lea     rcx, [rbp+var_28]
0x18001676f  call    ?GetNamedAutopilotTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIRegisteredTask@@@WRL@4@@Z; Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask(std::wstring const &,Microsoft::WRL::ComPtr<IRegisteredTask> &)
0x180016774  mov     ebx, eax
0x180016776  test    eax, eax
0x180016778  jns     short loc_1800167AB
0x18001677a  mov     rcx, [rbp+8]; this
0x18001677e  mov     r9d, eax; char *
0x180016781  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\moderndeployment\\au"...
0x180016788  mov     edx, 10Ch; void *
0x18001678d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016792  nop
0x180016793  mov     rcx, [rbp+var_40]
0x180016797  test    rcx, rcx
0x18001679a  jz      short loc_1800167A9
0x18001679c  mov     rax, [rcx]
0x18001679f  mov     rax, [rax+10h]
0x1800167a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167a8  nop
0x1800167a9  jmp     short loc_18001680B
0x1800167ab  lea     r8, [rbp+var_38]
0x1800167af  lea     rdx, [rbp+var_28]
0x1800167b3  lea     rcx, [rbp+var_40]
0x1800167b7  call    ?RunTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEAV?$ComPtr@UIRegisteredTask@@@WRL@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUBlockOnTaskCompletion@1234@@Z; Microsoft::Windows::Autopilot::AutoPilotTasks::RunTask(Microsoft::WRL::ComPtr<IRegisteredTask> &,std::wstring const &,Microsoft::Windows::Autopilot::AutoPilotTasks::BlockOnTaskCompletion const &)
0x1800167bc  mov     ebx, eax
0x1800167be  test    eax, eax
0x1800167c0  jns     short loc_1800167F3
0x1800167c2  mov     rcx, [rbp+8]; this
0x1800167c6  mov     r9d, eax; char *
0x1800167c9  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800167d0  mov     edx, 10Fh; void *
0x1800167d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800167da  nop
0x1800167db  mov     rcx, [rbp+var_40]
0x1800167df  test    rcx, rcx
0x1800167e2  jz      short loc_1800167F1
0x1800167e4  mov     rax, [rcx]
0x1800167e7  mov     rax, [rax+10h]
0x1800167eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167f0  nop
0x1800167f1  jmp     short loc_18001680B
0x1800167f3  mov     rcx, [rbp+var_40]
0x1800167f7  test    rcx, rcx
0x1800167fa  jz      short loc_180016809
0x1800167fc  mov     rax, [rcx]
0x1800167ff  mov     rax, [rax+10h]
0x180016803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016808  nop
0x180016809  mov     ebx, edi
0x18001680b  lea     rcx, [rbp+var_28]
0x18001680f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016814  mov     eax, ebx
0x180016816  mov     rcx, [rbp+var_8]
0x18001681a  xor     rcx, rsp; StackCookie
0x18001681d  call    __security_check_cookie
0x180016822  mov     rbx, [rsp+60h+arg_0]
0x180016827  mov     rdi, [rsp+60h+arg_8]
0x18001682c  add     rsp, 60h
0x180016830  pop     rbp
0x180016831  retn
```
