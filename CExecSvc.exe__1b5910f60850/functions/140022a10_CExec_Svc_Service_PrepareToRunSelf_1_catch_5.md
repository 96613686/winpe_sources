# _CExec::Svc::Service::PrepareToRunSelf_::_1_::catch$5

- ea: `0x140022a10`
- end: `0x140022a94`
- name: `_CExec::Svc::Service::PrepareToRunSelf_::_1_::catch$5`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x140002ed8`
- `0x140006684`
- `0x140007960`
- `0x1400109d0`

## string_xrefs

- `0x140022a25`: `onecore\vm\compute\service\cexec\service\cexecsvc.cpp`

## pseudocode

```c
void __fastcall __noreturn CExec::Svc::Service::PrepareToRunSelf_::_1_::catch_5(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // r8

  v5 = wil::details::in1diag3::Log_CaughtException(
         *(wil::details::in1diag3 **)(a2 + 152),
         (void *)0x75,
         (unsigned int)"onecore\\vm\\compute\\service\\cexec\\service\\cexecsvc.cpp",
         a4);
  v6 = v5;
  LODWORD(v6) = v5 & 0xEFFFFFFF;
  _snwprintf_s<16>(a2 + 104, 16, L"%%%%%u", v6);
  _snwprintf_s<16>(a2 + 72, 16, L"0x%08X", v5 & 0xEFFFFFFF);
  VmEventWrite<unsigned short (&)[16],unsigned short (&)[16]>(
    &MSCEXEC_SERVICE_START_FAILED,
    v7,
    v8,
    (const unsigned __int16 *)(a2 + 104),
    (unsigned __int16 *)(a2 + 72));
  throw;
}

```

## disassembly

```asm
0x140022a10  mov     [rsp+arg_8], rdx
0x140022a15  push    rbx
0x140022a16  push    rbp
0x140022a17  sub     rsp, 48h
0x140022a1b  mov     rbp, rdx
0x140022a1e  mov     rcx, [rbp+98h]; this
0x140022a25  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\service\\cexec\\s"...
0x140022a2c  mov     edx, 75h ; 'u'; void *
0x140022a31  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x140022a36  mov     ebx, eax
0x140022a38  mov     r9d, eax
0x140022a3b  btr     r9d, 1Ch
0x140022a40  lea     r8, aU; "%%%%%u"
0x140022a47  mov     edx, 10h
0x140022a4c  lea     rcx, [rbp+68h]
0x140022a50  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x140022a55  btr     ebx, 1Ch
0x140022a59  mov     r9d, ebx
0x140022a5c  lea     r8, a0x08x; "0x%08X"
0x140022a63  mov     edx, 10h
0x140022a68  lea     rcx, [rbp+48h]
0x140022a6c  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x140022a71  lea     rax, [rbp+48h]
0x140022a75  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x140022a7a  lea     r9, [rbp+68h]
0x140022a7e  lea     rcx, MSCEXEC_SERVICE_START_FAILED; EventDescriptor
0x140022a85  call    ??$VmEventWrite@AEAY0BA@GAEAY0BA@G@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@AEAY0BA@G2@Z; VmEventWrite<ushort (&)[16],ushort (&)[16]>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort (&)[16],ushort (&)[16])
0x140022a8a  xor     edx, edx; pThrowInfo
0x140022a8c  xor     ecx, ecx; pExceptionObject
0x140022a8e  call    _CxxThrowException_0
```
