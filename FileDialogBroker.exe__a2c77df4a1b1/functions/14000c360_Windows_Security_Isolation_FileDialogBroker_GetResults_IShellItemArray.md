# Windows::Security::Isolation::FileDialogBroker::GetResults(IShellItemArray * *)

- ea: `0x14000c360`
- end: `0x14000c44c`
- name: `?GetResults@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAPEAUIShellItemArray@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, struct IShellItemArray **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140007df4`
- `0x140009150`
- `0x140009194`
- `0x14000c360`
- `0x14000f8d0`
- `0x14000f9c0`
- `0x140010654`
- `0x140014010`

## string_xrefs

- `0x14000c3c0`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000c37a`: `FileDialogBroker::GetResults`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetResults(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IShellItemArray **a2)
{
  struct IShellItemArray **v2; // rbx
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
  FileDialogBrokerTraceLogging::WatchCurrentThread(v13, "FileDialogBroker::GetResults");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 4) + 40LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, struct IShellItemArray **))(*(_QWORD *)v4 + 216LL))(v4, v2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x57F,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v5,
        v13[0]);
    v18 = 0;
    try
    {
      v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 4) + 88LL))((char *)this - 32);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v18,
        v6);
    }
    catch ( ... )
    {
      IUnknown = Windows::Security::Isolation::FileDialogBroker::GetIUnknown((Windows::Security::Isolation::FileDialogBroker *)((char *)this - 32));
      ImpersonationTokenForClientOfObject_nothrow = wil::GetImpersonationTokenForClientOfObject_nothrow(
                                                      (__int64)IUnknown,
                                                      v10,
                                                      &v18);
      if ( ImpersonationTokenForClientOfObject_nothrow < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x58F,
          (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
          (const char *)(unsigned int)ImpersonationTokenForClientOfObject_nothrow,
          v12);
      v2 = a2;
    }
    Windows::Security::Isolation::BrokerUtils::AddItemArrayToBfs(v18, *v2);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v13);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x597,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x14000c360  mov     rax, rsp
0x14000c363  mov     [rax+20h], rbx
0x14000c367  mov     [rax+10h], rdx
0x14000c36b  mov     [rax+8], rcx
0x14000c36f  push    rdi
0x14000c370  sub     rsp, 70h
0x14000c374  mov     rbx, rdx
0x14000c377  mov     rdi, rcx
0x14000c37a  lea     rdx, aFiledialogbrok_74; "FileDialogBroker::GetResults"
0x14000c381  lea     rcx, [rax-58h]
0x14000c385  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000c38a  nop
0x14000c38b  mov     rax, [rdi-20h]
0x14000c38f  lea     rcx, [rdi-20h]
0x14000c393  mov     rax, [rax+28h]
0x14000c397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c39c  mov     r8, rax
0x14000c39f  mov     rcx, [rax]
0x14000c3a2  mov     rax, [rcx+0D8h]
0x14000c3a9  mov     rdx, rbx
0x14000c3ac  mov     rcx, r8
0x14000c3af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c3b4  mov     rcx, [rsp+78h]; this
0x14000c3b9  test    eax, eax
0x14000c3bb  jns     short loc_14000C3D1
0x14000c3bd  mov     r9d, eax; char *
0x14000c3c0  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000c3c7  mov     edx, 57Fh; void *
0x14000c3cc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000c3d1  mov     [rsp+78h+arg_10], 0
0x14000c3dd  mov     rax, [rdi-20h]
0x14000c3e1  lea     rcx, [rdi-20h]
0x14000c3e5  mov     rax, [rax+58h]
0x14000c3e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c3ee  mov     rdx, rax
0x14000c3f1  lea     rcx, [rsp+78h+arg_10]
0x14000c3f9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14000c3fe  nop
0x14000c3ff  jmp     short loc_14000C409
0x14000c401  mov     rbx, [rsp+78h+arg_8]
0x14000c409  mov     rdx, [rbx]; struct IShellItemArray *
0x14000c40c  mov     rcx, [rsp+78h+arg_10]; void *
0x14000c414  call    ?AddItemArrayToBfs@BrokerUtils@Isolation@Security@Windows@@SAXPEAXPEAUIShellItemArray@@@Z; Windows::Security::Isolation::BrokerUtils::AddItemArrayToBfs(void *,IShellItemArray *)
0x14000c419  nop
0x14000c41a  lea     rcx, [rsp+78h+arg_10]
0x14000c422  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14000c427  nop
0x14000c428  lea     rcx, [rsp+78h+var_58]; this
0x14000c42d  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000c432  xor     eax, eax
0x14000c434  jmp     short loc_14000C43D
0x14000c436  mov     eax, [rsp+78h+arg_0]
0x14000c43d  mov     rbx, [rsp+78h+arg_18]
0x14000c445  add     rsp, 70h
0x14000c449  pop     rdi
0x14000c44a  retn
```
