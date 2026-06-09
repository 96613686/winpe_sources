# Windows::Security::Isolation::FileDialogBroker::AddEditBox(ulong,ushort const *)

- ea: `0x1400096c0`
- end: `0x14000973a`
- name: `?AddEditBox@FileDialogBroker@Isolation@Security@Windows@@UEAAJKPEBG@Z`
- size: `122`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x1400096c0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x1400096d7`: `FileDialogBroker::AddEditBox`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::AddEditBox(
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

  FileDialogBrokerTraceLogging::WatchCurrentThread(v10, "FileDialogBroker::AddEditBox");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)v6 + 72LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x639,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x1400096c0  mov     [rsp+arg_8], rbx
0x1400096c5  mov     [rsp+arg_10], rsi
0x1400096ca  push    rdi
0x1400096cb  sub     rsp, 70h
0x1400096cf  mov     rdi, r8
0x1400096d2  mov     esi, edx
0x1400096d4  mov     rbx, rcx
0x1400096d7  lea     rdx, aFiledialogbrok_64; "FileDialogBroker::AddEditBox"
0x1400096de  lea     rcx, [rsp+78h+var_58]
0x1400096e3  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x1400096e8  nop
0x1400096e9  lea     rcx, [rbx-30h]
0x1400096ed  mov     rax, [rcx]
0x1400096f0  mov     rax, [rax+50h]
0x1400096f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400096f9  mov     r9, rax
0x1400096fc  mov     rcx, [rax]
0x1400096ff  mov     rax, [rcx+48h]
0x140009703  mov     r8, rdi
0x140009706  mov     edx, esi
0x140009708  mov     rcx, r9
0x14000970b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009710  mov     ebx, eax
0x140009712  lea     rcx, [rsp+78h+var_58]; this
0x140009717  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000971c  mov     eax, ebx
0x14000971e  jmp     short loc_140009727
0x140009720  mov     eax, [rsp+78h+arg_0]
0x140009727  lea     r11, [rsp+78h+var_8]
0x14000972c  mov     rbx, [r11+18h]
0x140009730  mov     rsi, [r11+20h]
0x140009734  mov     rsp, r11
0x140009737  pop     rdi
0x140009738  retn
```
