# Windows::Security::Isolation::FileDialogBroker::SetProperties(IPropertyStore *)

- ea: `0x14000f0e0`
- end: `0x14000f16c`
- name: `?SetProperties@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAUIPropertyStore@@@Z`
- size: `140`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, struct IPropertyStore *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x140009194`
- `0x14000f0e0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000f136`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000f0f0`: `FileDialogBroker::SetProperties`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetProperties(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IPropertyStore *a2)
{
  __int64 v4; // rax
  int v5; // eax
  const char *v6; // r9
  __int64 result; // rax
  int v8[22]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::SetProperties");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 5) + 48LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, struct IPropertyStore *))(*(_QWORD *)v4 + 224LL))(v4, a2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5BC,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v5,
        v8[0]);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5C0,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000f0e0  mov     [rsp+arg_8], rbx
0x14000f0e5  push    rdi
0x14000f0e6  sub     rsp, 70h
0x14000f0ea  mov     rbx, rdx
0x14000f0ed  mov     rdi, rcx
0x14000f0f0  lea     rdx, aFiledialogbrok_40; "FileDialogBroker::SetProperties"
0x14000f0f7  lea     rcx, [rsp+78h+var_58]
0x14000f0fc  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000f101  nop
0x14000f102  lea     rcx, [rdi-28h]
0x14000f106  mov     rax, [rcx]
0x14000f109  mov     rax, [rax+30h]
0x14000f10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f112  mov     r8, rax
0x14000f115  mov     rcx, [rax]
0x14000f118  mov     rax, [rcx+0E0h]
0x14000f11f  mov     rdx, rbx
0x14000f122  mov     rcx, r8
0x14000f125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f12a  mov     rcx, [rsp+78h]; this
0x14000f12f  test    eax, eax
0x14000f131  jns     short loc_14000F148
0x14000f133  mov     r9d, eax; char *
0x14000f136  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000f13d  mov     edx, 5BCh; void *
0x14000f142  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000f148  lea     rcx, [rsp+78h+var_58]; this
0x14000f14d  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000f152  xor     eax, eax
0x14000f154  jmp     short loc_14000F15D
0x14000f156  mov     eax, [rsp+78h+arg_0]
0x14000f15d  mov     rbx, [rsp+78h+arg_8]
0x14000f165  add     rsp, 70h
0x14000f169  pop     rdi
0x14000f16a  retn
```
