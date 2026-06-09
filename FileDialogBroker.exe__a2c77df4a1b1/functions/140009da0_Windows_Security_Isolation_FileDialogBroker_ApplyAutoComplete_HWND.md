# Windows::Security::Isolation::FileDialogBroker::ApplyAutoComplete(HWND__ *)

- ea: `0x140009da0`
- end: `0x140009e10`
- name: `?ApplyAutoComplete@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAUHWND__@@@Z`
- size: `112`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x140009da0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x140009db0`: `FileDialogBroker::ApplyAutoComplete`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::ApplyAutoComplete(
        Windows::Security::Isolation::FileDialogBroker *this,
        HWND a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::ApplyAutoComplete");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, HWND))(*(_QWORD *)v4 + 336LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x419,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x140009da0  mov     [rsp+arg_8], rbx
0x140009da5  push    rdi
0x140009da6  sub     rsp, 70h
0x140009daa  mov     rbx, rdx
0x140009dad  mov     rdi, rcx
0x140009db0  lea     rdx, aFiledialogbrok_48; "FileDialogBroker::ApplyAutoComplete"
0x140009db7  lea     rcx, [rsp+78h+var_58]
0x140009dbc  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x140009dc1  nop
0x140009dc2  lea     rcx, [rdi-10h]
0x140009dc6  mov     rax, [rcx]
0x140009dc9  mov     rax, [rax+40h]
0x140009dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009dd2  mov     r8, rax
0x140009dd5  mov     rcx, [rax]
0x140009dd8  mov     rax, [rcx+150h]
0x140009ddf  mov     rdx, rbx
0x140009de2  mov     rcx, r8
0x140009de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009dea  mov     ebx, eax
0x140009dec  lea     rcx, [rsp+78h+var_58]; this
0x140009df1  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x140009df6  mov     eax, ebx
0x140009df8  jmp     short loc_140009E01
0x140009dfa  mov     eax, [rsp+78h+arg_0]
0x140009e01  mov     rbx, [rsp+78h+arg_8]
0x140009e09  add     rsp, 70h
0x140009e0d  pop     rdi
0x140009e0e  retn
```
