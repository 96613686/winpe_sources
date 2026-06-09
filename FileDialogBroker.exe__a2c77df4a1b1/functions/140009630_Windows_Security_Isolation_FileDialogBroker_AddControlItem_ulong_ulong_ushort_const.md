# Windows::Security::Isolation::FileDialogBroker::AddControlItem(ulong,ulong,ushort const *)

- ea: `0x140009630`
- end: `0x1400096ae`
- name: `?AddControlItem@FileDialogBroker@Isolation@Security@Windows@@UEAAJKKPEBG@Z`
- size: `126`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x140009630`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x140009649`: `FileDialogBroker::AddControlItem`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::AddControlItem(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  __int64 v8; // rax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  _BYTE v12[120]; // [rsp+30h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v12, "FileDialogBroker::AddControlItem");
  try
  {
    v8 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, const unsigned __int16 *))(*(_QWORD *)v8 + 152LL))(
           v8,
           a2,
           a3,
           a4);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v12);
    result = v9;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x69D,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x140009630  push    rbx
0x140009632  push    rsi
0x140009633  push    rdi
0x140009634  push    r14
0x140009636  sub     rsp, 88h
0x14000963d  mov     rdi, r9
0x140009640  mov     esi, r8d
0x140009643  mov     r14d, edx
0x140009646  mov     rbx, rcx
0x140009649  lea     rdx, aFiledialogbrok_88; "FileDialogBroker::AddControlItem"
0x140009650  lea     rcx, [rsp+0A8h+var_78]
0x140009655  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000965a  nop
0x14000965b  lea     rcx, [rbx-30h]
0x14000965f  mov     rax, [rcx]
0x140009662  mov     rax, [rax+50h]
0x140009666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000966b  mov     r10, rax
0x14000966e  mov     rcx, [rax]
0x140009671  mov     rax, [rcx+98h]
0x140009678  mov     r9, rdi
0x14000967b  mov     r8d, esi
0x14000967e  mov     edx, r14d
0x140009681  mov     rcx, r10
0x140009684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009689  mov     ebx, eax
0x14000968b  lea     rcx, [rsp+0A8h+var_78]; this
0x140009690  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x140009695  mov     eax, ebx
0x140009697  jmp     short loc_1400096A0
0x140009699  mov     eax, [rsp+0A8h+arg_0]
0x1400096a0  add     rsp, 88h
0x1400096a7  pop     r14
0x1400096a9  pop     rdi
0x1400096aa  pop     rsi
0x1400096ab  pop     rbx
0x1400096ac  retn
```
