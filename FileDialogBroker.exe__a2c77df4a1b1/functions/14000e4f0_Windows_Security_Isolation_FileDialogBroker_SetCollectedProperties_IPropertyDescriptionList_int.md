# Windows::Security::Isolation::FileDialogBroker::SetCollectedProperties(IPropertyDescriptionList *,int)

- ea: `0x14000e4f0`
- end: `0x14000e58b`
- name: `?SetCollectedProperties@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAUIPropertyDescriptionList@@H@Z`
- size: `155`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, struct IPropertyDescriptionList *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x140009194`
- `0x14000e4f0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000e551`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000e508`: `FileDialogBroker::SetCollectedProperties`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetCollectedProperties(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IPropertyDescriptionList *a2,
        unsigned int a3)
{
  __int64 v6; // rax
  int v7; // eax
  const char *v8; // r9
  __int64 result; // rax
  int v10[20]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v10, (__int64)"FileDialogBroker::SetCollectedProperties");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 5) + 48LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, struct IPropertyDescriptionList *, _QWORD))(*(_QWORD *)v6 + 232LL))(
           v6,
           a2,
           a3);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5C9,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v7,
        v10[0]);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5CD,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000e4f0  mov     [rsp+arg_8], rbx
0x14000e4f5  mov     [rsp+arg_10], rsi
0x14000e4fa  push    rdi
0x14000e4fb  sub     rsp, 70h
0x14000e4ff  mov     edi, r8d
0x14000e502  mov     rsi, rdx
0x14000e505  mov     rbx, rcx
0x14000e508  lea     rdx, aFiledialogbrok_81; "FileDialogBroker::SetCollectedPropertie"...
0x14000e50f  lea     rcx, [rsp+78h+var_58]
0x14000e514  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000e519  nop
0x14000e51a  lea     rcx, [rbx-28h]
0x14000e51e  mov     rax, [rcx]
0x14000e521  mov     rax, [rax+30h]
0x14000e525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e52a  mov     r9, rax
0x14000e52d  mov     rcx, [rax]
0x14000e530  mov     rax, [rcx+0E8h]
0x14000e537  mov     r8d, edi
0x14000e53a  mov     rdx, rsi
0x14000e53d  mov     rcx, r9
0x14000e540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e545  mov     rcx, [rsp+78h]; this
0x14000e54a  test    eax, eax
0x14000e54c  jns     short loc_14000E563
0x14000e54e  mov     r9d, eax; char *
0x14000e551  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000e558  mov     edx, 5C9h; void *
0x14000e55d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000e563  lea     rcx, [rsp+78h+var_58]; this
0x14000e568  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000e56d  xor     eax, eax
0x14000e56f  jmp     short loc_14000E578
0x14000e571  mov     eax, [rsp+78h+arg_0]
0x14000e578  lea     r11, [rsp+78h+var_8]
0x14000e57d  mov     rbx, [r11+18h]
0x14000e581  mov     rsi, [r11+20h]
0x14000e585  mov     rsp, r11
0x14000e588  pop     rdi
0x14000e589  retn
```
