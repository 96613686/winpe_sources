# Windows::Security::Isolation::FileDialogBroker::GetCurrentFilterSpec(ushort * *)

- ea: `0x14000aaf0`
- end: `0x14000ab60`
- name: `?GetCurrentFilterSpec@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAPEAG@Z`
- size: `112`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000aaf0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000ab00`: `FileDialogBroker::GetCurrentFilterSpec`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetCurrentFilterSpec(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned __int16 **a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::GetCurrentFilterSpec");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v4 + 248LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3AB,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000aaf0  mov     [rsp+arg_8], rbx
0x14000aaf5  push    rdi
0x14000aaf6  sub     rsp, 70h
0x14000aafa  mov     rbx, rdx
0x14000aafd  mov     rdi, rcx
0x14000ab00  lea     rdx, aFiledialogbrok_84; "FileDialogBroker::GetCurrentFilterSpec"
0x14000ab07  lea     rcx, [rsp+78h+var_58]
0x14000ab0c  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000ab11  nop
0x14000ab12  lea     rcx, [rdi-10h]
0x14000ab16  mov     rax, [rcx]
0x14000ab19  mov     rax, [rax+40h]
0x14000ab1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab22  mov     r8, rax
0x14000ab25  mov     rcx, [rax]
0x14000ab28  mov     rax, [rcx+0F8h]
0x14000ab2f  mov     rdx, rbx
0x14000ab32  mov     rcx, r8
0x14000ab35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab3a  mov     ebx, eax
0x14000ab3c  lea     rcx, [rsp+78h+var_58]; this
0x14000ab41  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000ab46  mov     eax, ebx
0x14000ab48  jmp     short loc_14000AB51
0x14000ab4a  mov     eax, [rsp+78h+arg_0]
0x14000ab51  mov     rbx, [rsp+78h+arg_8]
0x14000ab59  add     rsp, 70h
0x14000ab5d  pop     rdi
0x14000ab5e  retn
```
