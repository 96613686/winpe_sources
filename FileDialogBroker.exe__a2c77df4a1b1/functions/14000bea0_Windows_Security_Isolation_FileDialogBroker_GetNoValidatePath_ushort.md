# Windows::Security::Isolation::FileDialogBroker::GetNoValidatePath(ushort * *)

- ea: `0x14000bea0`
- end: `0x14000bf10`
- name: `?GetNoValidatePath@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAPEAG@Z`
- size: `112`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000bea0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000beb0`: `FileDialogBroker::GetNoValidatePath`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetNoValidatePath(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned __int16 **a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::GetNoValidatePath");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v4 + 368LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x441,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000bea0  mov     [rsp+arg_8], rbx
0x14000bea5  push    rdi
0x14000bea6  sub     rsp, 70h
0x14000beaa  mov     rbx, rdx
0x14000bead  mov     rdi, rcx
0x14000beb0  lea     rdx, aFiledialogbrok_32; "FileDialogBroker::GetNoValidatePath"
0x14000beb7  lea     rcx, [rsp+78h+var_58]
0x14000bebc  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000bec1  nop
0x14000bec2  lea     rcx, [rdi-10h]
0x14000bec6  mov     rax, [rcx]
0x14000bec9  mov     rax, [rax+40h]
0x14000becd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bed2  mov     r8, rax
0x14000bed5  mov     rcx, [rax]
0x14000bed8  mov     rax, [rcx+170h]
0x14000bedf  mov     rdx, rbx
0x14000bee2  mov     rcx, r8
0x14000bee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000beea  mov     ebx, eax
0x14000beec  lea     rcx, [rsp+78h+var_58]; this
0x14000bef1  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000bef6  mov     eax, ebx
0x14000bef8  jmp     short loc_14000BF01
0x14000befa  mov     eax, [rsp+78h+arg_0]
0x14000bf01  mov     rbx, [rsp+78h+arg_8]
0x14000bf09  add     rsp, 70h
0x14000bf0d  pop     rdi
0x14000bf0e  retn
```
