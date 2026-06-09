# Windows::Security::Isolation::FileDialogBroker::IncludePlace(IShellItem *)

- ea: `0x14000ca80`
- end: `0x14000caf0`
- name: `?IncludePlace@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAUIShellItem@@@Z`
- size: `112`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, struct IShellItem *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000ca80`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000ca90`: `FileDialogBroker::IncludePlace`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::IncludePlace(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IShellItem *a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::IncludePlace");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, struct IShellItem *))(*(_QWORD *)v4 + 240LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3A1,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000ca80  mov     [rsp+arg_8], rbx
0x14000ca85  push    rdi
0x14000ca86  sub     rsp, 70h
0x14000ca8a  mov     rbx, rdx
0x14000ca8d  mov     rdi, rcx
0x14000ca90  lea     rdx, aFiledialogbrok_71; "FileDialogBroker::IncludePlace"
0x14000ca97  lea     rcx, [rsp+78h+var_58]
0x14000ca9c  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000caa1  nop
0x14000caa2  lea     rcx, [rdi-10h]
0x14000caa6  mov     rax, [rcx]
0x14000caa9  mov     rax, [rax+40h]
0x14000caad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cab2  mov     r8, rax
0x14000cab5  mov     rcx, [rax]
0x14000cab8  mov     rax, [rcx+0F0h]
0x14000cabf  mov     rdx, rbx
0x14000cac2  mov     rcx, r8
0x14000cac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000caca  mov     ebx, eax
0x14000cacc  lea     rcx, [rsp+78h+var_58]; this
0x14000cad1  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000cad6  mov     eax, ebx
0x14000cad8  jmp     short loc_14000CAE1
0x14000cada  mov     eax, [rsp+78h+arg_0]
0x14000cae1  mov     rbx, [rsp+78h+arg_8]
0x14000cae9  add     rsp, 70h
0x14000caed  pop     rdi
0x14000caee  retn
```
