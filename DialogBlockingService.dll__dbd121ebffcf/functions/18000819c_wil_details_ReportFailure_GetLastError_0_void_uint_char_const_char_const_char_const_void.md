# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18000819c`
- end: `0x180008214`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `120`
- prototype: `void __fastcall __noreturn(wil::details *, __int64, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000954c`

## callees

- `0x180004ee8`
- `0x1800055d0`
- `0x180008170`
- `0x18000819c`

## string_xrefs

- `0x1800081ae`: `base\embedded\sys\dialogblocking\service\lib\hookmgr.cpp`
- `0x1800081df`: `base\embedded\sys\dialogblocking\service\lib\hookmgr.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<0>(
        wil::details *a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // ebx
  signed int LastErrorFail; // eax
  __int64 v8; // rax
  __int64 v9; // xmm0_8
  int v10; // r9d
  const char *v11; // [rsp+20h] [rbp-58h]
  int v12; // [rsp+20h] [rbp-58h]
  void *v13; // [rsp+30h] [rbp-48h]
  __int64 v14; // [rsp+50h] [rbp-28h] BYREF
  int v15; // [rsp+58h] [rbp-20h]
  _BYTE v16[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    (void *)0x98,
                    (unsigned int)"base\\embedded\\sys\\dialogblocking\\service\\lib\\hookmgr.cpp",
                    a4,
                    v11,
                    a6,
                    v13);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v8 = wil::details::ResultStatus::FromResult(v16, (unsigned int)LastErrorFail);
  v9 = *(_QWORD *)v8;
  v15 = *(_DWORD *)(v8 + 8);
  v14 = v9;
  wil::details::ReportFailure_Base<0,0>(
    v6,
    152,
    (unsigned int)"base\\embedded\\sys\\dialogblocking\\service\\lib\\hookmgr.cpp",
    v10,
    v12,
    (__int64)a6,
    (__int64)&v14);
}

```

## disassembly

```asm
0x18000819c  mov     [rsp+arg_0], rbx
0x1800081a1  push    rdi
0x1800081a2  sub     rsp, 70h
0x1800081a6  mov     rdi, [rsp+78h+arg_28]
0x1800081ae  lea     r8, aBaseEmbeddedSy_0; "base\\embedded\\sys\\dialogblocking\\se"...
0x1800081b5  mov     edx, 98h; void *
0x1800081ba  mov     [rsp+78h+var_50], rdi; char *
0x1800081bf  mov     rbx, rcx
0x1800081c2  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800081c7  test    eax, eax
0x1800081c9  jle     short loc_1800081D3
0x1800081cb  movzx   eax, ax
0x1800081ce  or      eax, 80070000h
0x1800081d3  mov     edx, eax
0x1800081d5  lea     rcx, [rsp+78h+var_18]
0x1800081da  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x1800081df  lea     r8, aBaseEmbeddedSy_0; "base\\embedded\\sys\\dialogblocking\\se"...
0x1800081e6  mov     edx, 98h
0x1800081eb  mov     rcx, rbx
0x1800081ee  movsd   xmm0, qword ptr [rax]
0x1800081f2  mov     eax, [rax+8]
0x1800081f5  mov     [rsp+78h+var_20], eax
0x1800081f9  lea     rax, [rsp+78h+var_28]
0x1800081fe  mov     [rsp+78h+var_48], rax
0x180008203  mov     [rsp+78h+var_50], rdi
0x180008208  movsd   [rsp+78h+var_28], xmm0
0x18000820e  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
