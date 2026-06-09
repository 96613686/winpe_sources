# Windows::Security::Isolation::FileDialogBroker::SetTitle(ushort const *)

- ea: `0x14000f3a0`
- end: `0x14000f410`
- name: `?SetTitle@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEBG@Z`
- size: `112`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000f420`
- `0x14000f430`
- `0x14000f440`

## callees

- `0x140009194`
- `0x14000f3a0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000f3b0`: `FileDialogBroker::SetTitle`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetTitle(
        Windows::Security::Isolation::FileDialogBroker *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::SetTitle");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v4 + 136LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x306,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000f3a0  mov     [rsp+arg_8], rbx
0x14000f3a5  push    rdi
0x14000f3a6  sub     rsp, 70h
0x14000f3aa  mov     rbx, rdx
0x14000f3ad  mov     rdi, rcx
0x14000f3b0  lea     rdx, aFiledialogbrok_77; "FileDialogBroker::SetTitle"
0x14000f3b7  lea     rcx, [rsp+78h+var_58]
0x14000f3bc  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000f3c1  nop
0x14000f3c2  lea     rcx, [rdi-8]
0x14000f3c6  mov     rax, [rcx]
0x14000f3c9  mov     rax, [rax+38h]
0x14000f3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f3d2  mov     r8, rax
0x14000f3d5  mov     rcx, [rax]
0x14000f3d8  mov     rax, [rcx+88h]
0x14000f3df  mov     rdx, rbx
0x14000f3e2  mov     rcx, r8
0x14000f3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f3ea  mov     ebx, eax
0x14000f3ec  lea     rcx, [rsp+78h+var_58]; this
0x14000f3f1  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000f3f6  mov     eax, ebx
0x14000f3f8  jmp     short loc_14000F401
0x14000f3fa  mov     eax, [rsp+78h+arg_0]
0x14000f401  mov     rbx, [rsp+78h+arg_8]
0x14000f409  add     rsp, 70h
0x14000f40d  pop     rdi
0x14000f40e  retn
```
