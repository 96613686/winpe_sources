# Windows::Security::Isolation::FileDialogBroker::AddText(ulong,ushort const *)

- ea: `0x140009b50`
- end: `0x140009bca`
- name: `?AddText@FileDialogBroker@Isolation@Security@Windows@@UEAAJKPEBG@Z`
- size: `122`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x140009b50`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x140009b67`: `FileDialogBroker::AddText`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::AddText(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  _BYTE v10[80]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v10, "FileDialogBroker::AddText");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)v6 + 88LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x64D,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x140009b50  mov     [rsp+arg_8], rbx
0x140009b55  mov     [rsp+arg_10], rsi
0x140009b5a  push    rdi
0x140009b5b  sub     rsp, 70h
0x140009b5f  mov     rdi, r8
0x140009b62  mov     esi, edx
0x140009b64  mov     rbx, rcx
0x140009b67  lea     rdx, aFiledialogbrok_62; "FileDialogBroker::AddText"
0x140009b6e  lea     rcx, [rsp+78h+var_58]
0x140009b73  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x140009b78  nop
0x140009b79  lea     rcx, [rbx-30h]
0x140009b7d  mov     rax, [rcx]
0x140009b80  mov     rax, [rax+50h]
0x140009b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b89  mov     r9, rax
0x140009b8c  mov     rcx, [rax]
0x140009b8f  mov     rax, [rcx+58h]
0x140009b93  mov     r8, rdi
0x140009b96  mov     edx, esi
0x140009b98  mov     rcx, r9
0x140009b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ba0  mov     ebx, eax
0x140009ba2  lea     rcx, [rsp+78h+var_58]; this
0x140009ba7  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x140009bac  mov     eax, ebx
0x140009bae  jmp     short loc_140009BB7
0x140009bb0  mov     eax, [rsp+78h+arg_0]
0x140009bb7  lea     r11, [rsp+78h+var_8]
0x140009bbc  mov     rbx, [r11+18h]
0x140009bc0  mov     rsi, [r11+20h]
0x140009bc4  mov     rsp, r11
0x140009bc7  pop     rdi
0x140009bc8  retn
```
