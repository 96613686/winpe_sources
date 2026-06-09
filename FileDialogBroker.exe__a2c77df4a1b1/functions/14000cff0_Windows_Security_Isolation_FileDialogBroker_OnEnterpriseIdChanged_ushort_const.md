# Windows::Security::Isolation::FileDialogBroker::OnEnterpriseIdChanged(ushort const *)

- ea: `0x14000cff0`
- end: `0x14000d060`
- name: `?OnEnterpriseIdChanged@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEBG@Z`
- size: `112`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000cff0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000d000`: `FileDialogBroker::OnEnterpriseIdChanged`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::OnEnterpriseIdChanged(
        Windows::Security::Isolation::FileDialogBroker *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::OnEnterpriseIdChanged");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v4 + 384LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x455,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000cff0  mov     [rsp+arg_8], rbx
0x14000cff5  push    rdi
0x14000cff6  sub     rsp, 70h
0x14000cffa  mov     rbx, rdx
0x14000cffd  mov     rdi, rcx
0x14000d000  lea     rdx, aFiledialogbrok_16; "FileDialogBroker::OnEnterpriseIdChanged"
0x14000d007  lea     rcx, [rsp+78h+var_58]
0x14000d00c  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000d011  nop
0x14000d012  lea     rcx, [rdi-10h]
0x14000d016  mov     rax, [rcx]
0x14000d019  mov     rax, [rax+40h]
0x14000d01d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d022  mov     r8, rax
0x14000d025  mov     rcx, [rax]
0x14000d028  mov     rax, [rcx+180h]
0x14000d02f  mov     rdx, rbx
0x14000d032  mov     rcx, r8
0x14000d035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d03a  mov     ebx, eax
0x14000d03c  lea     rcx, [rsp+78h+var_58]; this
0x14000d041  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000d046  mov     eax, ebx
0x14000d048  jmp     short loc_14000D051
0x14000d04a  mov     eax, [rsp+78h+arg_0]
0x14000d051  mov     rbx, [rsp+78h+arg_8]
0x14000d059  add     rsp, 70h
0x14000d05d  pop     rdi
0x14000d05e  retn
```
