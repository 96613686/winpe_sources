# Windows::Security::Isolation::FileDialogBroker::AddPlace(IShellItem *,FDAP)

- ea: `0x1400097c0`
- end: `0x14000983f`
- name: `?AddPlace@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAUIShellItem@@W4FDAP@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *this, struct IShellItem *, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140009850`
- `0x140009860`
- `0x140009870`

## callees

- `0x140009194`
- `0x1400097c0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x1400097d8`: `FileDialogBroker::AddPlace`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::AddPlace(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IShellItem *a2,
        unsigned int a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  _BYTE v10[80]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v10, "FileDialogBroker::AddPlace");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, struct IShellItem *, _QWORD))(*(_QWORD *)v6 + 168LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x34F,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x1400097c0  mov     [rsp+arg_8], rbx
0x1400097c5  mov     [rsp+arg_10], rsi
0x1400097ca  push    rdi
0x1400097cb  sub     rsp, 70h
0x1400097cf  mov     edi, r8d
0x1400097d2  mov     rsi, rdx
0x1400097d5  mov     rbx, rcx
0x1400097d8  lea     rdx, aFiledialogbrok_23; "FileDialogBroker::AddPlace"
0x1400097df  lea     rcx, [rsp+78h+var_58]
0x1400097e4  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x1400097e9  nop
0x1400097ea  lea     rcx, [rbx-8]
0x1400097ee  mov     rax, [rcx]
0x1400097f1  mov     rax, [rax+38h]
0x1400097f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400097fa  mov     r9, rax
0x1400097fd  mov     rcx, [rax]
0x140009800  mov     rax, [rcx+0A8h]
0x140009807  mov     r8d, edi
0x14000980a  mov     rdx, rsi
0x14000980d  mov     rcx, r9
0x140009810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009815  mov     ebx, eax
0x140009817  lea     rcx, [rsp+78h+var_58]; this
0x14000981c  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x140009821  mov     eax, ebx
0x140009823  jmp     short loc_14000982C
0x140009825  mov     eax, [rsp+78h+arg_0]
0x14000982c  lea     r11, [rsp+78h+var_8]
0x140009831  mov     rbx, [r11+18h]
0x140009835  mov     rsi, [r11+20h]
0x140009839  mov     rsp, r11
0x14000983c  pop     rdi
0x14000983d  retn
```
