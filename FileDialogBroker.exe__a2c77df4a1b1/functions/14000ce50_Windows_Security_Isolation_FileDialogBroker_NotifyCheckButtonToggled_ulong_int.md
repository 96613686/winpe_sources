# Windows::Security::Isolation::FileDialogBroker::NotifyCheckButtonToggled(ulong,int)

- ea: `0x14000ce50`
- end: `0x14000cecd`
- name: `?NotifyCheckButtonToggled@FileDialogBroker@Isolation@Security@Windows@@UEAAJKH@Z`
- size: `125`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000ce50`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000ce67`: `FileDialogBroker::NotifyCheckButtonToggled`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::NotifyCheckButtonToggled(
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

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v10, (__int64)"FileDialogBroker::NotifyCheckButtonToggled");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 272LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3C9,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000ce50  mov     [rsp+arg_8], rbx
0x14000ce55  mov     [rsp+arg_10], rsi
0x14000ce5a  push    rdi
0x14000ce5b  sub     rsp, 70h
0x14000ce5f  mov     edi, r8d
0x14000ce62  mov     esi, edx
0x14000ce64  mov     rbx, rcx
0x14000ce67  lea     rdx, aFiledialogbrok_70; "FileDialogBroker::NotifyCheckButtonTogg"...
0x14000ce6e  lea     rcx, [rsp+78h+var_58]
0x14000ce73  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000ce78  nop
0x14000ce79  lea     rcx, [rbx-10h]
0x14000ce7d  mov     rax, [rcx]
0x14000ce80  mov     rax, [rax+40h]
0x14000ce84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce89  mov     r9, rax
0x14000ce8c  mov     rcx, [rax]
0x14000ce8f  mov     rax, [rcx+110h]
0x14000ce96  mov     r8d, edi
0x14000ce99  mov     edx, esi
0x14000ce9b  mov     rcx, r9
0x14000ce9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cea3  mov     ebx, eax
0x14000cea5  lea     rcx, [rsp+78h+var_58]; this
0x14000ceaa  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000ceaf  mov     eax, ebx
0x14000ceb1  jmp     short loc_14000CEBA
0x14000ceb3  mov     eax, [rsp+78h+arg_0]
0x14000ceba  lea     r11, [rsp+78h+var_8]
0x14000cebf  mov     rbx, [r11+18h]
0x14000cec3  mov     rsi, [r11+20h]
0x14000cec7  mov     rsp, r11
0x14000ceca  pop     rdi
0x14000cecb  retn
```
