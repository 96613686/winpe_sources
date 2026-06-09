# Windows::Security::Isolation::FileDialogBroker::ChangeEnterpriseId(ushort const *)

- ea: `0x14000a060`
- end: `0x14000a0d0`
- name: `?ChangeEnterpriseId@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEBG@Z`
- size: `112`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000a060`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000a070`: `FileDialogBroker::ChangeEnterpriseId`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::ChangeEnterpriseId(
        Windows::Security::Isolation::FileDialogBroker *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::ChangeEnterpriseId");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v4 + 416LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x47D,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000a060  mov     [rsp+arg_8], rbx
0x14000a065  push    rdi
0x14000a066  sub     rsp, 70h
0x14000a06a  mov     rbx, rdx
0x14000a06d  mov     rdi, rcx
0x14000a070  lea     rdx, aFiledialogbrok_10; "FileDialogBroker::ChangeEnterpriseId"
0x14000a077  lea     rcx, [rsp+78h+var_58]
0x14000a07c  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000a081  nop
0x14000a082  lea     rcx, [rdi-10h]
0x14000a086  mov     rax, [rcx]
0x14000a089  mov     rax, [rax+40h]
0x14000a08d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a092  mov     r8, rax
0x14000a095  mov     rcx, [rax]
0x14000a098  mov     rax, [rcx+1A0h]
0x14000a09f  mov     rdx, rbx
0x14000a0a2  mov     rcx, r8
0x14000a0a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a0aa  mov     ebx, eax
0x14000a0ac  lea     rcx, [rsp+78h+var_58]; this
0x14000a0b1  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000a0b6  mov     eax, ebx
0x14000a0b8  jmp     short loc_14000A0C1
0x14000a0ba  mov     eax, [rsp+78h+arg_0]
0x14000a0c1  mov     rbx, [rsp+78h+arg_8]
0x14000a0c9  add     rsp, 70h
0x14000a0cd  pop     rdi
0x14000a0ce  retn
```
