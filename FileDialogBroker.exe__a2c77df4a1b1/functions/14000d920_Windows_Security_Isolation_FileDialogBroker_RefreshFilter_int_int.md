# Windows::Security::Isolation::FileDialogBroker::RefreshFilter(int,int)

- ea: `0x14000d920`
- end: `0x14000d99d`
- name: `?RefreshFilter@FileDialogBroker@Isolation@Security@Windows@@UEAAJHH@Z`
- size: `125`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000d920`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000d937`: `FileDialogBroker::RefreshFilter`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::RefreshFilter(
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

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v10, (__int64)"FileDialogBroker::RefreshFilter");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 312LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3FB,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000d920  mov     [rsp+arg_8], rbx
0x14000d925  mov     [rsp+arg_10], rsi
0x14000d92a  push    rdi
0x14000d92b  sub     rsp, 70h
0x14000d92f  mov     edi, r8d
0x14000d932  mov     esi, edx
0x14000d934  mov     rbx, rcx
0x14000d937  lea     rdx, aFiledialogbrok_13; "FileDialogBroker::RefreshFilter"
0x14000d93e  lea     rcx, [rsp+78h+var_58]
0x14000d943  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000d948  nop
0x14000d949  lea     rcx, [rbx-10h]
0x14000d94d  mov     rax, [rcx]
0x14000d950  mov     rax, [rax+40h]
0x14000d954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d959  mov     r9, rax
0x14000d95c  mov     rcx, [rax]
0x14000d95f  mov     rax, [rcx+138h]
0x14000d966  mov     r8d, edi
0x14000d969  mov     edx, esi
0x14000d96b  mov     rcx, r9
0x14000d96e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d973  mov     ebx, eax
0x14000d975  lea     rcx, [rsp+78h+var_58]; this
0x14000d97a  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000d97f  mov     eax, ebx
0x14000d981  jmp     short loc_14000D98A
0x14000d983  mov     eax, [rsp+78h+arg_0]
0x14000d98a  lea     r11, [rsp+78h+var_8]
0x14000d98f  mov     rbx, [r11+18h]
0x14000d993  mov     rsi, [r11+20h]
0x14000d997  mov     rsp, r11
0x14000d99a  pop     rdi
0x14000d99b  retn
```
