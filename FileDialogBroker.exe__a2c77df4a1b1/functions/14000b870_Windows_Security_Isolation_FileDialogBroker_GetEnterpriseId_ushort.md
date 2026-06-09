# Windows::Security::Isolation::FileDialogBroker::GetEnterpriseId(ushort * *)

- ea: `0x14000b870`
- end: `0x14000b8e0`
- name: `?GetEnterpriseId@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAPEAG@Z`
- size: `112`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000b870`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000b880`: `FileDialogBroker::GetEnterpriseId`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetEnterpriseId(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned __int16 **a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::GetEnterpriseId");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v4 + 400LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x469,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000b870  mov     [rsp+arg_8], rbx
0x14000b875  push    rdi
0x14000b876  sub     rsp, 70h
0x14000b87a  mov     rbx, rdx
0x14000b87d  mov     rdi, rcx
0x14000b880  lea     rdx, aFiledialogbrok_53; "FileDialogBroker::GetEnterpriseId"
0x14000b887  lea     rcx, [rsp+78h+var_58]
0x14000b88c  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000b891  nop
0x14000b892  lea     rcx, [rdi-10h]
0x14000b896  mov     rax, [rcx]
0x14000b899  mov     rax, [rax+40h]
0x14000b89d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b8a2  mov     r8, rax
0x14000b8a5  mov     rcx, [rax]
0x14000b8a8  mov     rax, [rcx+190h]
0x14000b8af  mov     rdx, rbx
0x14000b8b2  mov     rcx, r8
0x14000b8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b8ba  mov     ebx, eax
0x14000b8bc  lea     rcx, [rsp+78h+var_58]; this
0x14000b8c1  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000b8c6  mov     eax, ebx
0x14000b8c8  jmp     short loc_14000B8D1
0x14000b8ca  mov     eax, [rsp+78h+arg_0]
0x14000b8d1  mov     rbx, [rsp+78h+arg_8]
0x14000b8d9  add     rsp, 70h
0x14000b8dd  pop     rdi
0x14000b8de  retn
```
