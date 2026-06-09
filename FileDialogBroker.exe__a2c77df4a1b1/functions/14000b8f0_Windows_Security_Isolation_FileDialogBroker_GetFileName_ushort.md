# Windows::Security::Isolation::FileDialogBroker::GetFileName(ushort * *)

- ea: `0x14000b8f0`
- end: `0x14000b960`
- name: `?GetFileName@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAPEAG@Z`
- size: `112`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000b970`
- `0x14000b980`
- `0x14000b990`

## callees

- `0x140009194`
- `0x14000b8f0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000b900`: `FileDialogBroker::GetFileName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetFileName(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned __int16 **a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::GetFileName");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v4 + 128LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2FC,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000b8f0  mov     [rsp+arg_8], rbx
0x14000b8f5  push    rdi
0x14000b8f6  sub     rsp, 70h
0x14000b8fa  mov     rbx, rdx
0x14000b8fd  mov     rdi, rcx
0x14000b900  lea     rdx, aFiledialogbrok_36; "FileDialogBroker::GetFileName"
0x14000b907  lea     rcx, [rsp+78h+var_58]
0x14000b90c  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000b911  nop
0x14000b912  lea     rcx, [rdi-8]
0x14000b916  mov     rax, [rcx]
0x14000b919  mov     rax, [rax+38h]
0x14000b91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b922  mov     r8, rax
0x14000b925  mov     rcx, [rax]
0x14000b928  mov     rax, [rcx+80h]
0x14000b92f  mov     rdx, rbx
0x14000b932  mov     rcx, r8
0x14000b935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b93a  mov     ebx, eax
0x14000b93c  lea     rcx, [rsp+78h+var_58]; this
0x14000b941  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000b946  mov     eax, ebx
0x14000b948  jmp     short loc_14000B951
0x14000b94a  mov     eax, [rsp+78h+arg_0]
0x14000b951  mov     rbx, [rsp+78h+arg_8]
0x14000b959  add     rsp, 70h
0x14000b95d  pop     rdi
0x14000b95e  retn
```
