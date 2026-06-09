# Microsoft::Windows::Autopilot::AutoPilotTasks::EnableNamedTask(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001ddcc`
- end: `0x18001de9d`
- name: `?EnableNamedTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800155d4`

## callees

- `0x180010764`
- `0x18001ddcc`
- `0x18001dea4`
- `0x18002f010`

## string_xrefs

- `0x18001ddf7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001de49`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotTasks::EnableNamedTask(_QWORD *a1)
{
  int NamedAutopilotTask; // eax
  unsigned int v2; // ebx
  const char *v3; // r9
  __int64 result; // rax
  __int64 v5; // rbx
  int v6; // eax
  unsigned int v7; // edi
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  v10 = 0;
  try
  {
    NamedAutopilotTask = Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask(a1, &v10);
    v2 = NamedAutopilotTask;
    if ( NamedAutopilotTask >= 0 )
    {
      v5 = v10;
      v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 88LL))(v10, 0xFFFFFFFFLL);
      v7 = v6;
      if ( v6 >= 0 )
      {
        if ( v5 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
          (const char *)(unsigned int)v6,
          v8);
        if ( v5 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        result = v7;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
        (const char *)(unsigned int)NamedAutopilotTask,
        v8);
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      result = v2;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x78,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x18001ddcc  mov     [rsp+arg_0], rbx
0x18001ddd1  push    rdi; int
0x18001ddd2  sub     rsp, 20h
0x18001ddd6  mov     [rsp+28h+arg_8], 0
0x18001dddf  lea     rdx, [rsp+28h+arg_8]
0x18001dde4  call    ?GetNamedAutopilotTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIRegisteredTask@@@WRL@4@@Z; Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask(std::wstring const &,Microsoft::WRL::ComPtr<IRegisteredTask> &)
0x18001dde9  mov     ebx, eax
0x18001ddeb  test    eax, eax
0x18001dded  jns     short loc_18001DE24
0x18001ddef  mov     rcx, [rsp+28h]; this
0x18001ddf4  mov     r9d, eax; char *
0x18001ddf7  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001ddfe  mov     edx, 71h ; 'q'; void *
0x18001de03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001de08  nop
0x18001de09  mov     rcx, [rsp+28h+arg_8]
0x18001de0e  test    rcx, rcx
0x18001de11  jz      short loc_18001DE20
0x18001de13  mov     rax, [rcx]
0x18001de16  mov     rax, [rax+10h]
0x18001de1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de1f  nop
0x18001de20  mov     eax, ebx
0x18001de22  jmp     short loc_18001DE91
0x18001de24  mov     rbx, [rsp+28h+arg_8]
0x18001de29  mov     rax, [rbx]
0x18001de2c  or      edx, 0FFFFFFFFh
0x18001de2f  mov     rcx, rbx
0x18001de32  mov     rax, [rax+58h]
0x18001de36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de3b  mov     edi, eax
0x18001de3d  test    eax, eax
0x18001de3f  jns     short loc_18001DE74
0x18001de41  mov     rcx, [rsp+28h]; this
0x18001de46  mov     r9d, eax; char *
0x18001de49  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001de50  mov     edx, 74h ; 't'; void *
0x18001de55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001de5a  nop
0x18001de5b  test    rbx, rbx
0x18001de5e  jz      short loc_18001DE70
0x18001de60  mov     rax, [rbx]
0x18001de63  mov     rcx, rbx
0x18001de66  mov     rax, [rax+10h]
0x18001de6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de6f  nop
0x18001de70  mov     eax, edi
0x18001de72  jmp     short loc_18001DE91
0x18001de74  test    rbx, rbx
0x18001de77  jz      short loc_18001DE89
0x18001de79  mov     rax, [rbx]
0x18001de7c  mov     rcx, rbx
0x18001de7f  mov     rax, [rax+10h]
0x18001de83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de88  nop
0x18001de89  xor     eax, eax
0x18001de8b  jmp     short loc_18001DE91
0x18001de8d  mov     eax, dword ptr [rsp+28h+arg_8]
0x18001de91  mov     rbx, [rsp+28h+arg_0]
0x18001de96  add     rsp, 20h
0x18001de9a  pop     rdi
0x18001de9b  retn
```
