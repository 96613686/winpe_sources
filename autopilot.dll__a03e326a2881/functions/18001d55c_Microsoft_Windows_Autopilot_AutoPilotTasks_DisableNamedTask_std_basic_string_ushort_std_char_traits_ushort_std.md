# Microsoft::Windows::Autopilot::AutoPilotTasks::DisableNamedTask(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001d55c`
- end: `0x18001d62c`
- name: `?DisableNamedTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `208`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016420`

## callees

- `0x1800105f4`
- `0x18001d55c`
- `0x18001d70c`
- `0x18002e010`

## string_xrefs

- `0x18001d587`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001d5d8`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 Microsoft::Windows::Autopilot::AutoPilotTasks::DisableNamedTask()
{
  int NamedAutopilotTask; // eax
  unsigned int v1; // ebx
  const char *v2; // r9
  __int64 result; // rax
  int v4; // eax
  unsigned int v5; // edi
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  try
  {
    NamedAutopilotTask = Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask();
    v1 = NamedAutopilotTask;
    if ( NamedAutopilotTask >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(MEMORY[0] + 88LL))(0, 0);
      v5 = v4;
      if ( v4 >= 0 )
      {
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x80,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
          (const char *)(unsigned int)v4,
          v6);
        result = v5;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
        (const char *)(unsigned int)NamedAutopilotTask,
        v6);
      result = v1;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x84,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
                           v2);
  }
  return result;
}

```

## disassembly

```asm
0x18001d55c  mov     [rsp+arg_0], rbx
0x18001d561  push    rdi; int
0x18001d562  sub     rsp, 20h
0x18001d566  mov     [rsp+28h+arg_8], 0
0x18001d56f  lea     rdx, [rsp+28h+arg_8]
0x18001d574  call    ?GetNamedAutopilotTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIRegisteredTask@@@WRL@4@@Z; Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask(std::wstring const &,Microsoft::WRL::ComPtr<IRegisteredTask> &)
0x18001d579  mov     ebx, eax
0x18001d57b  test    eax, eax
0x18001d57d  jns     short loc_18001D5B4
0x18001d57f  mov     rcx, [rsp+28h]; this
0x18001d584  mov     r9d, eax; char *
0x18001d587  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001d58e  mov     edx, 7Dh ; '}'; void *
0x18001d593  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d598  nop
0x18001d599  mov     rcx, [rsp+28h+arg_8]
0x18001d59e  test    rcx, rcx
0x18001d5a1  jz      short loc_18001D5B0
0x18001d5a3  mov     rax, [rcx]
0x18001d5a6  mov     rax, [rax+10h]
0x18001d5aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5af  nop
0x18001d5b0  mov     eax, ebx
0x18001d5b2  jmp     short loc_18001D620
0x18001d5b4  mov     rbx, [rsp+28h+arg_8]
0x18001d5b9  mov     rax, [rbx]
0x18001d5bc  xor     edx, edx
0x18001d5be  mov     rcx, rbx
0x18001d5c1  mov     rax, [rax+58h]
0x18001d5c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5ca  mov     edi, eax
0x18001d5cc  test    eax, eax
0x18001d5ce  jns     short loc_18001D603
0x18001d5d0  mov     rcx, [rsp+28h]; this
0x18001d5d5  mov     r9d, eax; char *
0x18001d5d8  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001d5df  mov     edx, 80h; void *
0x18001d5e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d5e9  nop
0x18001d5ea  test    rbx, rbx
0x18001d5ed  jz      short loc_18001D5FF
0x18001d5ef  mov     rax, [rbx]
0x18001d5f2  mov     rcx, rbx
0x18001d5f5  mov     rax, [rax+10h]
0x18001d5f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5fe  nop
0x18001d5ff  mov     eax, edi
0x18001d601  jmp     short loc_18001D620
0x18001d603  test    rbx, rbx
0x18001d606  jz      short loc_18001D618
0x18001d608  mov     rax, [rbx]
0x18001d60b  mov     rcx, rbx
0x18001d60e  mov     rax, [rax+10h]
0x18001d612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d617  nop
0x18001d618  xor     eax, eax
0x18001d61a  jmp     short loc_18001D620
0x18001d61c  mov     eax, dword ptr [rsp+28h+arg_8]
0x18001d620  mov     rbx, [rsp+28h+arg_0]
0x18001d625  add     rsp, 20h
0x18001d629  pop     rdi
0x18001d62a  retn
```
