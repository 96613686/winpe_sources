# Windows::Security::Isolation::FileDialogBroker::GetProperties(IPropertyStore * *)

- ea: `0x14000c190`
- end: `0x14000c21c`
- name: `?GetProperties@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAPEAUIPropertyStore@@@Z`
- size: `140`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x140009194`
- `0x14000c190`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000c1e6`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000c1a0`: `FileDialogBroker::GetProperties`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetProperties(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IPropertyStore **a2)
{
  __int64 v4; // rax
  int v5; // eax
  const char *v6; // r9
  __int64 result; // rax
  int v8[22]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::GetProperties");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 5) + 48LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, struct IPropertyStore **))(*(_QWORD *)v4 + 240LL))(v4, a2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5D6,
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
                           (void *)0x5DA,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000c190  mov     [rsp+arg_8], rbx
0x14000c195  push    rdi
0x14000c196  sub     rsp, 70h
0x14000c19a  mov     rbx, rdx
0x14000c19d  mov     rdi, rcx
0x14000c1a0  lea     rdx, aFiledialogbrok_18; "FileDialogBroker::GetProperties"
0x14000c1a7  lea     rcx, [rsp+78h+var_58]
0x14000c1ac  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000c1b1  nop
0x14000c1b2  lea     rcx, [rdi-28h]
0x14000c1b6  mov     rax, [rcx]
0x14000c1b9  mov     rax, [rax+30h]
0x14000c1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c1c2  mov     r8, rax
0x14000c1c5  mov     rcx, [rax]
0x14000c1c8  mov     rax, [rcx+0F0h]
0x14000c1cf  mov     rdx, rbx
0x14000c1d2  mov     rcx, r8
0x14000c1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c1da  mov     rcx, [rsp+78h]; this
0x14000c1df  test    eax, eax
0x14000c1e1  jns     short loc_14000C1F8
0x14000c1e3  mov     r9d, eax; char *
0x14000c1e6  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000c1ed  mov     edx, 5D6h; void *
0x14000c1f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000c1f8  lea     rcx, [rsp+78h+var_58]; this
0x14000c1fd  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000c202  xor     eax, eax
0x14000c204  jmp     short loc_14000C20D
0x14000c206  mov     eax, [rsp+78h+arg_0]
0x14000c20d  mov     rbx, [rsp+78h+arg_8]
0x14000c215  add     rsp, 70h
0x14000c219  pop     rdi
0x14000c21a  retn
```
