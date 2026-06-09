# Windows::Security::Isolation::FileDialogBroker::GetFileTypeIndex(uint *)

- ea: `0x14000bad0`
- end: `0x14000bb3d`
- name: `?GetFileTypeIndex@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAI@Z`
- size: `109`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000bb50`
- `0x14000bb60`
- `0x14000bb70`

## callees

- `0x140009194`
- `0x14000bad0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000bae0`: `FileDialogBroker::GetFileTypeIndex`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetFileTypeIndex(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int *a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::GetFileTypeIndex");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 48LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x287,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000bad0  mov     [rsp+arg_8], rbx
0x14000bad5  push    rdi
0x14000bad6  sub     rsp, 70h
0x14000bada  mov     rbx, rdx
0x14000badd  mov     rdi, rcx
0x14000bae0  lea     rdx, aFiledialogbrok_17; "FileDialogBroker::GetFileTypeIndex"
0x14000bae7  lea     rcx, [rsp+78h+var_58]
0x14000baec  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000baf1  nop
0x14000baf2  lea     rcx, [rdi-8]
0x14000baf6  mov     rax, [rcx]
0x14000baf9  mov     rax, [rax+38h]
0x14000bafd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bb02  mov     r8, rax
0x14000bb05  mov     rcx, [rax]
0x14000bb08  mov     rax, [rcx+30h]
0x14000bb0c  mov     rdx, rbx
0x14000bb0f  mov     rcx, r8
0x14000bb12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bb17  mov     ebx, eax
0x14000bb19  lea     rcx, [rsp+78h+var_58]; this
0x14000bb1e  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000bb23  mov     eax, ebx
0x14000bb25  jmp     short loc_14000BB2E
0x14000bb27  mov     eax, [rsp+78h+arg_0]
0x14000bb2e  mov     rbx, [rsp+78h+arg_8]
0x14000bb36  add     rsp, 70h
0x14000bb3a  pop     rdi
0x14000bb3b  retn
```
