# Windows::Security::Isolation::FileDialogBroker::Initialize(int,ushort)

- ea: `0x14000cb70`
- end: `0x14000cbe4`
- name: `?Initialize@FileDialogBroker@Isolation@Security@Windows@@UEAAXHG@Z`
- size: `116`
- prototype: `void __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, int, unsigned __int16)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000cb88`: `FileDialogBroker::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Security::Isolation::FileDialogBroker::Initialize(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2,
        unsigned __int16 a3)
{
  __int64 v6; // rax
  const char *v7; // r9
  _BYTE v8[80]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::Initialize");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 216LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Throw_CaughtException(
      retaddr,
      (void *)0x38D,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      v7);
  }
}

```

## disassembly

```asm
0x14000cb70  mov     [rsp+arg_0], rbx
0x14000cb75  mov     [rsp+arg_8], rsi
0x14000cb7a  push    rdi
0x14000cb7b  sub     rsp, 70h
0x14000cb7f  movzx   ebx, r8w
0x14000cb83  mov     edi, edx
0x14000cb85  mov     rsi, rcx
0x14000cb88  lea     rdx, aFiledialogbrok_7; "FileDialogBroker::Initialize"
0x14000cb8f  lea     rcx, [rsp+78h+var_58]
0x14000cb94  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000cb99  nop
0x14000cb9a  lea     rcx, [rsi-10h]
0x14000cb9e  mov     rax, [rcx]
0x14000cba1  mov     rax, [rax+40h]
0x14000cba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cbaa  mov     r9, rax
0x14000cbad  mov     rcx, [rax]
0x14000cbb0  mov     rax, [rcx+0D8h]
0x14000cbb7  movzx   r8d, bx
0x14000cbbb  mov     edx, edi
0x14000cbbd  mov     rcx, r9
0x14000cbc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cbc5  nop
0x14000cbc6  lea     rcx, [rsp+78h+var_58]; this
0x14000cbcb  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000cbd0  nop
0x14000cbd1  lea     r11, [rsp+78h+var_8]
0x14000cbd6  mov     rbx, [r11+10h]
0x14000cbda  mov     rsi, [r11+18h]
0x14000cbde  mov     rsp, r11
0x14000cbe1  pop     rdi
0x14000cbe2  retn
```
