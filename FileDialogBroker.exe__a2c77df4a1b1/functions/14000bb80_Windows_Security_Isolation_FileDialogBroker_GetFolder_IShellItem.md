# Windows::Security::Isolation::FileDialogBroker::GetFolder(IShellItem * *)

- ea: `0x14000bb80`
- end: `0x14000bbed`
- name: `?GetFolder@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAPEAUIShellItem@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, struct IShellItem **)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000bc00`
- `0x14000bc10`
- `0x14000bc20`

## callees

- `0x140009194`
- `0x14000bb80`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000bb90`: `FileDialogBroker::GetFolder`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetFolder(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IShellItem **a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::GetFolder");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, struct IShellItem **))(*(_QWORD *)v4 + 104LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2DE,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000bb80  mov     [rsp+arg_8], rbx
0x14000bb85  push    rdi
0x14000bb86  sub     rsp, 70h
0x14000bb8a  mov     rbx, rdx
0x14000bb8d  mov     rdi, rcx
0x14000bb90  lea     rdx, aFiledialogbrok_86; "FileDialogBroker::GetFolder"
0x14000bb97  lea     rcx, [rsp+78h+var_58]
0x14000bb9c  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000bba1  nop
0x14000bba2  lea     rcx, [rdi-8]
0x14000bba6  mov     rax, [rcx]
0x14000bba9  mov     rax, [rax+38h]
0x14000bbad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bbb2  mov     r8, rax
0x14000bbb5  mov     rcx, [rax]
0x14000bbb8  mov     rax, [rcx+68h]
0x14000bbbc  mov     rdx, rbx
0x14000bbbf  mov     rcx, r8
0x14000bbc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bbc7  mov     ebx, eax
0x14000bbc9  lea     rcx, [rsp+78h+var_58]; this
0x14000bbce  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000bbd3  mov     eax, ebx
0x14000bbd5  jmp     short loc_14000BBDE
0x14000bbd7  mov     eax, [rsp+78h+arg_0]
0x14000bbde  mov     rbx, [rsp+78h+arg_8]
0x14000bbe6  add     rsp, 70h
0x14000bbea  pop     rdi
0x14000bbeb  retn
```
