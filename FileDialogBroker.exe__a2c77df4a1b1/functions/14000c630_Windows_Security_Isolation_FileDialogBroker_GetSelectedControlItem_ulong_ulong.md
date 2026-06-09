# Windows::Security::Isolation::FileDialogBroker::GetSelectedControlItem(ulong,ulong *)

- ea: `0x14000c630`
- end: `0x14000c6ad`
- name: `?GetSelectedControlItem@FileDialogBroker@Isolation@Security@Windows@@UEAAJKPEAK@Z`
- size: `125`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000c630`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000c647`: `FileDialogBroker::GetSelectedControlItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetSelectedControlItem(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2,
        unsigned int *a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  _BYTE v10[80]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v10, (__int64)"FileDialogBroker::GetSelectedControlItem");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v6 + 192LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6CF,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000c630  mov     [rsp+arg_8], rbx
0x14000c635  mov     [rsp+arg_10], rsi
0x14000c63a  push    rdi
0x14000c63b  sub     rsp, 70h
0x14000c63f  mov     rdi, r8
0x14000c642  mov     esi, edx
0x14000c644  mov     rbx, rcx
0x14000c647  lea     rdx, aFiledialogbrok_59; "FileDialogBroker::GetSelectedControlIte"...
0x14000c64e  lea     rcx, [rsp+78h+var_58]
0x14000c653  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000c658  nop
0x14000c659  lea     rcx, [rbx-30h]
0x14000c65d  mov     rax, [rcx]
0x14000c660  mov     rax, [rax+50h]
0x14000c664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c669  mov     r9, rax
0x14000c66c  mov     rcx, [rax]
0x14000c66f  mov     rax, [rcx+0C0h]
0x14000c676  mov     r8, rdi
0x14000c679  mov     edx, esi
0x14000c67b  mov     rcx, r9
0x14000c67e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c683  mov     ebx, eax
0x14000c685  lea     rcx, [rsp+78h+var_58]; this
0x14000c68a  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000c68f  mov     eax, ebx
0x14000c691  jmp     short loc_14000C69A
0x14000c693  mov     eax, [rsp+78h+arg_0]
0x14000c69a  lea     r11, [rsp+78h+var_8]
0x14000c69f  mov     rbx, [r11+18h]
0x14000c6a3  mov     rsi, [r11+20h]
0x14000c6a7  mov     rsp, r11
0x14000c6aa  pop     rdi
0x14000c6ab  retn
```
