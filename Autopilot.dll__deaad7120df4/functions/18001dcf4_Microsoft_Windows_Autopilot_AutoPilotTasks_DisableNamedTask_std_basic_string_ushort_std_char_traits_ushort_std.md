# Microsoft::Windows::Autopilot::AutoPilotTasks::DisableNamedTask(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001dcf4`
- end: `0x18001ddc4`
- name: `?DisableNamedTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800168c0`

## callees

- `0x180010764`
- `0x18001dcf4`
- `0x18001dea4`
- `0x18002f010`

## string_xrefs

- `0x18001dd1f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001dd70`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotTasks::DisableNamedTask(_QWORD *a1)
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
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 88LL))(v10, 0);
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
          (void *)0x80,
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
        (void *)0x7D,
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
                           (void *)0x84,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x18001dcf4  mov     [rsp+arg_0], rbx
0x18001dcf9  push    rdi; int
0x18001dcfa  sub     rsp, 20h
0x18001dcfe  mov     [rsp+28h+arg_8], 0
0x18001dd07  lea     rdx, [rsp+28h+arg_8]
0x18001dd0c  call    ?GetNamedAutopilotTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIRegisteredTask@@@WRL@4@@Z; Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask(std::wstring const &,Microsoft::WRL::ComPtr<IRegisteredTask> &)
0x18001dd11  mov     ebx, eax
0x18001dd13  test    eax, eax
0x18001dd15  jns     short loc_18001DD4C
0x18001dd17  mov     rcx, [rsp+28h]; this
0x18001dd1c  mov     r9d, eax; char *
0x18001dd1f  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001dd26  mov     edx, 7Dh ; '}'; void *
0x18001dd2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dd30  nop
0x18001dd31  mov     rcx, [rsp+28h+arg_8]
0x18001dd36  test    rcx, rcx
0x18001dd39  jz      short loc_18001DD48
0x18001dd3b  mov     rax, [rcx]
0x18001dd3e  mov     rax, [rax+10h]
0x18001dd42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd47  nop
0x18001dd48  mov     eax, ebx
0x18001dd4a  jmp     short loc_18001DDB8
0x18001dd4c  mov     rbx, [rsp+28h+arg_8]
0x18001dd51  mov     rax, [rbx]
0x18001dd54  xor     edx, edx
0x18001dd56  mov     rcx, rbx
0x18001dd59  mov     rax, [rax+58h]
0x18001dd5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd62  mov     edi, eax
0x18001dd64  test    eax, eax
0x18001dd66  jns     short loc_18001DD9B
0x18001dd68  mov     rcx, [rsp+28h]; this
0x18001dd6d  mov     r9d, eax; char *
0x18001dd70  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001dd77  mov     edx, 80h; void *
0x18001dd7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dd81  nop
0x18001dd82  test    rbx, rbx
0x18001dd85  jz      short loc_18001DD97
0x18001dd87  mov     rax, [rbx]
0x18001dd8a  mov     rcx, rbx
0x18001dd8d  mov     rax, [rax+10h]
0x18001dd91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd96  nop
0x18001dd97  mov     eax, edi
0x18001dd99  jmp     short loc_18001DDB8
0x18001dd9b  test    rbx, rbx
0x18001dd9e  jz      short loc_18001DDB0
0x18001dda0  mov     rax, [rbx]
0x18001dda3  mov     rcx, rbx
0x18001dda6  mov     rax, [rax+10h]
0x18001ddaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddaf  nop
0x18001ddb0  xor     eax, eax
0x18001ddb2  jmp     short loc_18001DDB8
0x18001ddb4  mov     eax, dword ptr [rsp+28h+arg_8]
0x18001ddb8  mov     rbx, [rsp+28h+arg_0]
0x18001ddbd  add     rsp, 20h
0x18001ddc1  pop     rdi
0x18001ddc2  retn
```
