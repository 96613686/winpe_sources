# Windows::Security::Isolation::FileDialogBroker::GetEditBoxText(ulong,ushort * *)

- ea: `0x14000b7f0`
- end: `0x14000b86a`
- name: `?GetEditBoxText@FileDialogBroker@Isolation@Security@Windows@@UEAAJKPEAPEAG@Z`
- size: `122`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000b7f0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000b807`: `FileDialogBroker::GetEditBoxText`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetEditBoxText(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2,
        unsigned __int16 **a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  _BYTE v10[80]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v10, "FileDialogBroker::GetEditBoxText");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 **))(*(_QWORD *)v6 + 120LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x675,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000b7f0  mov     [rsp+arg_8], rbx
0x14000b7f5  mov     [rsp+arg_10], rsi
0x14000b7fa  push    rdi
0x14000b7fb  sub     rsp, 70h
0x14000b7ff  mov     rdi, r8
0x14000b802  mov     esi, edx
0x14000b804  mov     rbx, rcx
0x14000b807  lea     rdx, aFiledialogbrok_51; "FileDialogBroker::GetEditBoxText"
0x14000b80e  lea     rcx, [rsp+78h+var_58]
0x14000b813  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000b818  nop
0x14000b819  lea     rcx, [rbx-30h]
0x14000b81d  mov     rax, [rcx]
0x14000b820  mov     rax, [rax+50h]
0x14000b824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b829  mov     r9, rax
0x14000b82c  mov     rcx, [rax]
0x14000b82f  mov     rax, [rcx+78h]
0x14000b833  mov     r8, rdi
0x14000b836  mov     edx, esi
0x14000b838  mov     rcx, r9
0x14000b83b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b840  mov     ebx, eax
0x14000b842  lea     rcx, [rsp+78h+var_58]; this
0x14000b847  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000b84c  mov     eax, ebx
0x14000b84e  jmp     short loc_14000B857
0x14000b850  mov     eax, [rsp+78h+arg_0]
0x14000b857  lea     r11, [rsp+78h+var_8]
0x14000b85c  mov     rbx, [r11+18h]
0x14000b860  mov     rsi, [r11+20h]
0x14000b864  mov     rsp, r11
0x14000b867  pop     rdi
0x14000b868  retn
```
