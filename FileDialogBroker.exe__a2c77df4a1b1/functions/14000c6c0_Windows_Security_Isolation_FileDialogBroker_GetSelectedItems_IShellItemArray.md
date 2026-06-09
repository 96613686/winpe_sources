# Windows::Security::Isolation::FileDialogBroker::GetSelectedItems(IShellItemArray * *)

- ea: `0x14000c6c0`
- end: `0x14000c74c`
- name: `?GetSelectedItems@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAPEAUIShellItemArray@@@Z`
- size: `140`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, struct IShellItemArray **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x140009194`
- `0x14000c6c0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000c716`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000c6d0`: `FileDialogBroker::GetSelectedItems`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetSelectedItems(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IShellItemArray **a2)
{
  __int64 v4; // rax
  int v5; // eax
  const char *v6; // r9
  __int64 result; // rax
  int v8[22]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::GetSelectedItems");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 4) + 40LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, struct IShellItemArray **))(*(_QWORD *)v4 + 224LL))(v4, a2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5A0,
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
                           (void *)0x5A4,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000c6c0  mov     [rsp+arg_8], rbx
0x14000c6c5  push    rdi
0x14000c6c6  sub     rsp, 70h
0x14000c6ca  mov     rbx, rdx
0x14000c6cd  mov     rdi, rcx
0x14000c6d0  lea     rdx, aFiledialogbrok_14; "FileDialogBroker::GetSelectedItems"
0x14000c6d7  lea     rcx, [rsp+78h+var_58]
0x14000c6dc  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000c6e1  nop
0x14000c6e2  lea     rcx, [rdi-20h]
0x14000c6e6  mov     rax, [rcx]
0x14000c6e9  mov     rax, [rax+28h]
0x14000c6ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c6f2  mov     r8, rax
0x14000c6f5  mov     rcx, [rax]
0x14000c6f8  mov     rax, [rcx+0E0h]
0x14000c6ff  mov     rdx, rbx
0x14000c702  mov     rcx, r8
0x14000c705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c70a  mov     rcx, [rsp+78h]; this
0x14000c70f  test    eax, eax
0x14000c711  jns     short loc_14000C728
0x14000c713  mov     r9d, eax; char *
0x14000c716  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000c71d  mov     edx, 5A0h; void *
0x14000c722  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000c728  lea     rcx, [rsp+78h+var_58]; this
0x14000c72d  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000c732  xor     eax, eax
0x14000c734  jmp     short loc_14000C73D
0x14000c736  mov     eax, [rsp+78h+arg_0]
0x14000c73d  mov     rbx, [rsp+78h+arg_8]
0x14000c745  add     rsp, 70h
0x14000c749  pop     rdi
0x14000c74a  retn
```
