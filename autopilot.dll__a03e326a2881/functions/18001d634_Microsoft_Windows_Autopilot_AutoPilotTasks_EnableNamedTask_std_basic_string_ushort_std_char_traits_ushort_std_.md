# Microsoft::Windows::Autopilot::AutoPilotTasks::EnableNamedTask(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001d634`
- end: `0x18001d705`
- name: `?EnableNamedTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800151cc`

## callees

- `0x1800105f4`
- `0x18001d634`
- `0x18001d70c`
- `0x18002e010`

## string_xrefs

- `0x18001d65f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001d6b1`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`

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
0x18001d634  mov     [rsp+arg_0], rbx
0x18001d639  push    rdi; int
0x18001d63a  sub     rsp, 20h
0x18001d63e  mov     [rsp+28h+arg_8], 0
0x18001d647  lea     rdx, [rsp+28h+arg_8]
0x18001d64c  call    ?GetNamedAutopilotTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIRegisteredTask@@@WRL@4@@Z; Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask(std::wstring const &,Microsoft::WRL::ComPtr<IRegisteredTask> &)
0x18001d651  mov     ebx, eax
0x18001d653  test    eax, eax
0x18001d655  jns     short loc_18001D68C
0x18001d657  mov     rcx, [rsp+28h]; this
0x18001d65c  mov     r9d, eax; char *
0x18001d65f  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001d666  mov     edx, 71h ; 'q'; void *
0x18001d66b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d670  nop
0x18001d671  mov     rcx, [rsp+28h+arg_8]
0x18001d676  test    rcx, rcx
0x18001d679  jz      short loc_18001D688
0x18001d67b  mov     rax, [rcx]
0x18001d67e  mov     rax, [rax+10h]
0x18001d682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d687  nop
0x18001d688  mov     eax, ebx
0x18001d68a  jmp     short loc_18001D6F9
0x18001d68c  mov     rbx, [rsp+28h+arg_8]
0x18001d691  mov     rax, [rbx]
0x18001d694  or      edx, 0FFFFFFFFh
0x18001d697  mov     rcx, rbx
0x18001d69a  mov     rax, [rax+58h]
0x18001d69e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6a3  mov     edi, eax
0x18001d6a5  test    eax, eax
0x18001d6a7  jns     short loc_18001D6DC
0x18001d6a9  mov     rcx, [rsp+28h]; this
0x18001d6ae  mov     r9d, eax; char *
0x18001d6b1  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001d6b8  mov     edx, 74h ; 't'; void *
0x18001d6bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d6c2  nop
0x18001d6c3  test    rbx, rbx
0x18001d6c6  jz      short loc_18001D6D8
0x18001d6c8  mov     rax, [rbx]
0x18001d6cb  mov     rcx, rbx
0x18001d6ce  mov     rax, [rax+10h]
0x18001d6d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6d7  nop
0x18001d6d8  mov     eax, edi
0x18001d6da  jmp     short loc_18001D6F9
0x18001d6dc  test    rbx, rbx
0x18001d6df  jz      short loc_18001D6F1
0x18001d6e1  mov     rax, [rbx]
0x18001d6e4  mov     rcx, rbx
0x18001d6e7  mov     rax, [rax+10h]
0x18001d6eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6f0  nop
0x18001d6f1  xor     eax, eax
0x18001d6f3  jmp     short loc_18001D6F9
0x18001d6f5  mov     eax, dword ptr [rsp+28h+arg_8]
0x18001d6f9  mov     rbx, [rsp+28h+arg_0]
0x18001d6fe  add     rsp, 20h
0x18001d702  pop     rdi
0x18001d703  retn
```
