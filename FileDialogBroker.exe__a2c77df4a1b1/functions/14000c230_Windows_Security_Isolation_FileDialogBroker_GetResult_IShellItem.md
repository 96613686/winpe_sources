# Windows::Security::Isolation::FileDialogBroker::GetResult(IShellItem * *)

- ea: `0x14000c230`
- end: `0x14000c31c`
- name: `?GetResult@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAPEAUIShellItem@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, struct IShellItem **)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c330`
- `0x14000c340`
- `0x14000c350`

## callees

- `0x140007df4`
- `0x140009150`
- `0x140009194`
- `0x14000c230`
- `0x14000f8d0`
- `0x14000f9c0`
- `0x140010764`
- `0x140014010`

## string_xrefs

- `0x14000c290`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000c24a`: `FileDialogBroker::GetResult`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetResult(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IShellItem **a2)
{
  struct IShellItem **v2; // rbx
  __int64 v4; // rax
  int v5; // eax
  __int64 v6; // rax
  const char *v7; // r9
  __int64 result; // rax
  struct IUnknown *IUnknown; // rax
  __int64 v10; // rdx
  int ImpersonationTokenForClientOfObject_nothrow; // eax
  int v12; // [rsp+20h] [rbp-58h]
  int v13[22]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  void *v18; // [rsp+90h] [rbp+18h] BYREF

  v2 = a2;
  FileDialogBrokerTraceLogging::WatchCurrentThread(v13, "FileDialogBroker::GetResult");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, struct IShellItem **))(*(_QWORD *)v4 + 160LL))(v4, v2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x323,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v5,
        v13[0]);
    v18 = 0;
    try
    {
      v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 1) + 88LL))((char *)this - 8);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v18,
        v6);
    }
    catch ( ... )
    {
      IUnknown = Windows::Security::Isolation::FileDialogBroker::GetIUnknown((Windows::Security::Isolation::FileDialogBroker *)((char *)this - 8));
      ImpersonationTokenForClientOfObject_nothrow = wil::GetImpersonationTokenForClientOfObject_nothrow(
                                                      (__int64)IUnknown,
                                                      v10,
                                                      &v18);
      if ( ImpersonationTokenForClientOfObject_nothrow < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x333,
          (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
          (const char *)(unsigned int)ImpersonationTokenForClientOfObject_nothrow,
          v12);
      v2 = a2;
    }
    Windows::Security::Isolation::BrokerUtils::AddItemToBfs((char *)v18, *v2);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v13);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x33B,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x14000c230  mov     rax, rsp
0x14000c233  mov     [rax+20h], rbx
0x14000c237  mov     [rax+10h], rdx
0x14000c23b  mov     [rax+8], rcx
0x14000c23f  push    rdi
0x14000c240  sub     rsp, 70h
0x14000c244  mov     rbx, rdx
0x14000c247  mov     rdi, rcx
0x14000c24a  lea     rdx, aFiledialogbrok_44; "FileDialogBroker::GetResult"
0x14000c251  lea     rcx, [rax-58h]
0x14000c255  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000c25a  nop
0x14000c25b  mov     rax, [rdi-8]
0x14000c25f  lea     rcx, [rdi-8]
0x14000c263  mov     rax, [rax+38h]
0x14000c267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c26c  mov     r8, rax
0x14000c26f  mov     rcx, [rax]
0x14000c272  mov     rax, [rcx+0A0h]
0x14000c279  mov     rdx, rbx
0x14000c27c  mov     rcx, r8
0x14000c27f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c284  mov     rcx, [rsp+78h]; this
0x14000c289  test    eax, eax
0x14000c28b  jns     short loc_14000C2A1
0x14000c28d  mov     r9d, eax; char *
0x14000c290  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000c297  mov     edx, 323h; void *
0x14000c29c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000c2a1  mov     [rsp+78h+arg_10], 0
0x14000c2ad  mov     rax, [rdi-8]
0x14000c2b1  lea     rcx, [rdi-8]
0x14000c2b5  mov     rax, [rax+58h]
0x14000c2b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c2be  mov     rdx, rax
0x14000c2c1  lea     rcx, [rsp+78h+arg_10]
0x14000c2c9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14000c2ce  nop
0x14000c2cf  jmp     short loc_14000C2D9
0x14000c2d1  mov     rbx, [rsp+78h+arg_8]
0x14000c2d9  mov     rdx, [rbx]; struct IShellItem *
0x14000c2dc  mov     rcx, [rsp+78h+arg_10]; void *
0x14000c2e4  call    ?AddItemToBfs@BrokerUtils@Isolation@Security@Windows@@SAXPEAXPEAUIShellItem@@@Z; Windows::Security::Isolation::BrokerUtils::AddItemToBfs(void *,IShellItem *)
0x14000c2e9  nop
0x14000c2ea  lea     rcx, [rsp+78h+arg_10]
0x14000c2f2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14000c2f7  nop
0x14000c2f8  lea     rcx, [rsp+78h+var_58]; this
0x14000c2fd  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000c302  xor     eax, eax
0x14000c304  jmp     short loc_14000C30D
0x14000c306  mov     eax, [rsp+78h+arg_0]
0x14000c30d  mov     rbx, [rsp+78h+arg_18]
0x14000c315  add     rsp, 70h
0x14000c319  pop     rdi
0x14000c31a  retn
```
