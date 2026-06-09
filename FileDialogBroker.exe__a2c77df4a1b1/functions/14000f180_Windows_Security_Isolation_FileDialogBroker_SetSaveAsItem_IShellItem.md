# Windows::Security::Isolation::FileDialogBroker::SetSaveAsItem(IShellItem *)

- ea: `0x14000f180`
- end: `0x14000f20c`
- name: `?SetSaveAsItem@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAUIShellItem@@@Z`
- size: `140`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, struct IShellItem *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x140009194`
- `0x14000f180`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000f1d6`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000f190`: `FileDialogBroker::SetSaveAsItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetSaveAsItem(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IShellItem *a2)
{
  __int64 v4; // rax
  int v5; // eax
  const char *v6; // r9
  __int64 result; // rax
  int v8[22]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::SetSaveAsItem");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 5) + 48LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, struct IShellItem *))(*(_QWORD *)v4 + 216LL))(v4, a2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5AF,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v5,
        v8[0]);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5B3,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000f180  mov     [rsp+arg_8], rbx
0x14000f185  push    rdi
0x14000f186  sub     rsp, 70h
0x14000f18a  mov     rbx, rdx
0x14000f18d  mov     rdi, rcx
0x14000f190  lea     rdx, aFiledialogbrok_56; "FileDialogBroker::SetSaveAsItem"
0x14000f197  lea     rcx, [rsp+78h+var_58]
0x14000f19c  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000f1a1  nop
0x14000f1a2  lea     rcx, [rdi-28h]
0x14000f1a6  mov     rax, [rcx]
0x14000f1a9  mov     rax, [rax+30h]
0x14000f1ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f1b2  mov     r8, rax
0x14000f1b5  mov     rcx, [rax]
0x14000f1b8  mov     rax, [rcx+0D8h]
0x14000f1bf  mov     rdx, rbx
0x14000f1c2  mov     rcx, r8
0x14000f1c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f1ca  mov     rcx, [rsp+78h]; this
0x14000f1cf  test    eax, eax
0x14000f1d1  jns     short loc_14000F1E8
0x14000f1d3  mov     r9d, eax; char *
0x14000f1d6  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000f1dd  mov     edx, 5AFh; void *
0x14000f1e2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000f1e8  lea     rcx, [rsp+78h+var_58]; this
0x14000f1ed  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000f1f2  xor     eax, eax
0x14000f1f4  jmp     short loc_14000F1FD
0x14000f1f6  mov     eax, [rsp+78h+arg_0]
0x14000f1fd  mov     rbx, [rsp+78h+arg_8]
0x14000f205  add     rsp, 70h
0x14000f209  pop     rdi
0x14000f20a  retn
```
