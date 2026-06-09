# Windows::Security::Isolation::FileDialogBroker::SetTemplateCustomization(IUnknown *)

- ea: `0x14000f320`
- end: `0x14000f390`
- name: `?SetTemplateCustomization@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAUIUnknown@@@Z`
- size: `112`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000f320`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000f330`: `FileDialogBroker::SetTemplateCustomization`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetTemplateCustomization(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IUnknown *a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::SetTemplateCustomization");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *))(*(_QWORD *)v4 + 304LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3F1,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000f320  mov     [rsp+arg_8], rbx
0x14000f325  push    rdi
0x14000f326  sub     rsp, 70h
0x14000f32a  mov     rbx, rdx
0x14000f32d  mov     rdi, rcx
0x14000f330  lea     rdx, aFiledialogbrok_47; "FileDialogBroker::SetTemplateCustomizat"...
0x14000f337  lea     rcx, [rsp+78h+var_58]
0x14000f33c  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000f341  nop
0x14000f342  lea     rcx, [rdi-10h]
0x14000f346  mov     rax, [rcx]
0x14000f349  mov     rax, [rax+40h]
0x14000f34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f352  mov     r8, rax
0x14000f355  mov     rcx, [rax]
0x14000f358  mov     rax, [rcx+130h]
0x14000f35f  mov     rdx, rbx
0x14000f362  mov     rcx, r8
0x14000f365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f36a  mov     ebx, eax
0x14000f36c  lea     rcx, [rsp+78h+var_58]; this
0x14000f371  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000f376  mov     eax, ebx
0x14000f378  jmp     short loc_14000F381
0x14000f37a  mov     eax, [rsp+78h+arg_0]
0x14000f381  mov     rbx, [rsp+78h+arg_8]
0x14000f389  add     rsp, 70h
0x14000f38d  pop     rdi
0x14000f38e  retn
```
