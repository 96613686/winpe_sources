# Windows::Security::Isolation::FileDialogBroker::NotifyItemSelected(ulong,ulong)

- ea: `0x14000cf60`
- end: `0x14000cfdd`
- name: `?NotifyItemSelected@FileDialogBroker@Isolation@Security@Windows@@UEAAJKK@Z`
- size: `125`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000cf60`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000cf77`: `FileDialogBroker::NotifyItemSelected`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::NotifyItemSelected(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2,
        unsigned int a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  _BYTE v10[80]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v10, (__int64)"FileDialogBroker::NotifyItemSelected");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 256LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3B5,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000cf60  mov     [rsp+arg_8], rbx
0x14000cf65  mov     [rsp+arg_10], rsi
0x14000cf6a  push    rdi
0x14000cf6b  sub     rsp, 70h
0x14000cf6f  mov     edi, r8d
0x14000cf72  mov     esi, edx
0x14000cf74  mov     rbx, rcx
0x14000cf77  lea     rdx, aFiledialogbrok_60; "FileDialogBroker::NotifyItemSelected"
0x14000cf7e  lea     rcx, [rsp+78h+var_58]
0x14000cf83  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000cf88  nop
0x14000cf89  lea     rcx, [rbx-10h]
0x14000cf8d  mov     rax, [rcx]
0x14000cf90  mov     rax, [rax+40h]
0x14000cf94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cf99  mov     r9, rax
0x14000cf9c  mov     rcx, [rax]
0x14000cf9f  mov     rax, [rcx+100h]
0x14000cfa6  mov     r8d, edi
0x14000cfa9  mov     edx, esi
0x14000cfab  mov     rcx, r9
0x14000cfae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cfb3  mov     ebx, eax
0x14000cfb5  lea     rcx, [rsp+78h+var_58]; this
0x14000cfba  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000cfbf  mov     eax, ebx
0x14000cfc1  jmp     short loc_14000CFCA
0x14000cfc3  mov     eax, [rsp+78h+arg_0]
0x14000cfca  lea     r11, [rsp+78h+var_8]
0x14000cfcf  mov     rbx, [r11+18h]
0x14000cfd3  mov     rsi, [r11+20h]
0x14000cfd7  mov     rsp, r11
0x14000cfda  pop     rdi
0x14000cfdb  retn
```
