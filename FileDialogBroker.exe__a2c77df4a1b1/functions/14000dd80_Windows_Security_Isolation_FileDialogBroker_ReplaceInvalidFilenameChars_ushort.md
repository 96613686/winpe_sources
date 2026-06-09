# Windows::Security::Isolation::FileDialogBroker::ReplaceInvalidFilenameChars(ushort *)

- ea: `0x14000dd80`
- end: `0x14000ddf0`
- name: `?ReplaceInvalidFilenameChars@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAG@Z`
- size: `112`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000dd80`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000dd90`: `FileDialogBroker::ReplaceInvalidFilenameChars`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::ReplaceInvalidFilenameChars(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(
    (__int64)v8,
    (__int64)"FileDialogBroker::ReplaceInvalidFilenameChars");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v4 + 296LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3E7,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000dd80  mov     [rsp+arg_8], rbx
0x14000dd85  push    rdi
0x14000dd86  sub     rsp, 70h
0x14000dd8a  mov     rbx, rdx
0x14000dd8d  mov     rdi, rcx
0x14000dd90  lea     rdx, aFiledialogbrok_5; "FileDialogBroker::ReplaceInvalidFilenam"...
0x14000dd97  lea     rcx, [rsp+78h+var_58]
0x14000dd9c  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000dda1  nop
0x14000dda2  lea     rcx, [rdi-10h]
0x14000dda6  mov     rax, [rcx]
0x14000dda9  mov     rax, [rax+40h]
0x14000ddad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ddb2  mov     r8, rax
0x14000ddb5  mov     rcx, [rax]
0x14000ddb8  mov     rax, [rcx+128h]
0x14000ddbf  mov     rdx, rbx
0x14000ddc2  mov     rcx, r8
0x14000ddc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ddca  mov     ebx, eax
0x14000ddcc  lea     rcx, [rsp+78h+var_58]; this
0x14000ddd1  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000ddd6  mov     eax, ebx
0x14000ddd8  jmp     short loc_14000DDE1
0x14000ddda  mov     eax, [rsp+78h+arg_0]
0x14000dde1  mov     rbx, [rsp+78h+arg_8]
0x14000dde9  add     rsp, 70h
0x14000dded  pop     rdi
0x14000ddee  retn
```
