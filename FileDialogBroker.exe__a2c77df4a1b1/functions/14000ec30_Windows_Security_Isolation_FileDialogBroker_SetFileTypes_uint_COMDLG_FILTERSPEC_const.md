# Windows::Security::Isolation::FileDialogBroker::SetFileTypes(uint,_COMDLG_FILTERSPEC const *)

- ea: `0x14000ec30`
- end: `0x14000ecaa`
- name: `?SetFileTypes@FileDialogBroker@Isolation@Security@Windows@@UEAAJIPEBU_COMDLG_FILTERSPEC@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, const struct _COMDLG_FILTERSPEC *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000ecb0`
- `0x14000ecc0`
- `0x14000ecd0`

## callees

- `0x140009194`
- `0x14000ec30`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000ec47`: `FileDialogBroker::SetFileTypes`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetFileTypes(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2,
        const struct _COMDLG_FILTERSPEC *a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  _BYTE v10[80]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v10, (__int64)"FileDialogBroker::SetFileTypes");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, const struct _COMDLG_FILTERSPEC *))(*(_QWORD *)v6 + 32LL))(
           v6,
           a2,
           a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x273,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000ec30  mov     [rsp+arg_8], rbx
0x14000ec35  mov     [rsp+arg_10], rsi
0x14000ec3a  push    rdi
0x14000ec3b  sub     rsp, 70h
0x14000ec3f  mov     rdi, r8
0x14000ec42  mov     esi, edx
0x14000ec44  mov     rbx, rcx
0x14000ec47  lea     rdx, aFiledialogbrok_73; "FileDialogBroker::SetFileTypes"
0x14000ec4e  lea     rcx, [rsp+78h+var_58]
0x14000ec53  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000ec58  nop
0x14000ec59  lea     rcx, [rbx-8]
0x14000ec5d  mov     rax, [rcx]
0x14000ec60  mov     rax, [rax+38h]
0x14000ec64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec69  mov     r9, rax
0x14000ec6c  mov     rcx, [rax]
0x14000ec6f  mov     rax, [rcx+20h]
0x14000ec73  mov     r8, rdi
0x14000ec76  mov     edx, esi
0x14000ec78  mov     rcx, r9
0x14000ec7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec80  mov     ebx, eax
0x14000ec82  lea     rcx, [rsp+78h+var_58]; this
0x14000ec87  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000ec8c  mov     eax, ebx
0x14000ec8e  jmp     short loc_14000EC97
0x14000ec90  mov     eax, [rsp+78h+arg_0]
0x14000ec97  lea     r11, [rsp+78h+var_8]
0x14000ec9c  mov     rbx, [r11+18h]
0x14000eca0  mov     rsi, [r11+20h]
0x14000eca4  mov     rsp, r11
0x14000eca7  pop     rdi
0x14000eca8  retn
```
