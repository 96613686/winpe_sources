# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180007940`
- end: `0x1800079b1`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `113`
- prototype: `void __fastcall __noreturn(wil::details *, __int64, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18000ce88`

## callees

- `0x180004d28`
- `0x180005270`
- `0x1800077c0`
- `0x180007940`

## string_xrefs

- `0x180007952`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`

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
  int v10; // r8d
  int v11; // r9d
  const char *v12; // [rsp+20h] [rbp-58h]
  int v13; // [rsp+20h] [rbp-58h]
  void *v14; // [rsp+30h] [rbp-48h]
  __int64 v15; // [rsp+50h] [rbp-28h] BYREF
  int v16; // [rsp+58h] [rbp-20h]
  _BYTE v17[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    (void *)0xF6,
                    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\w"
                                  "pnuserservice.cpp",
                    a4,
                    v12,
                    a6,
                    v14);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v8 = wil::details::ResultStatus::FromResult(v17, (unsigned int)LastErrorFail);
  v9 = *(_QWORD *)v8;
  v16 = *(_DWORD *)(v8 + 8);
  v15 = v9;
  wil::details::ReportFailure_Base<0,0>(v6, 246, v10, v11, v13, (__int64)a6, (__int64)&v15);
}

```

## disassembly

```asm
0x180007940  mov     [rsp+arg_0], rbx
0x180007945  push    rdi
0x180007946  sub     rsp, 70h
0x18000794a  mov     rdi, [rsp+78h+arg_28]
0x180007952  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180007959  mov     edx, 0F6h; void *
0x18000795e  mov     [rsp+78h+var_50], rdi; char *
0x180007963  mov     rbx, rcx
0x180007966  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000796b  test    eax, eax
0x18000796d  jle     short loc_180007977
0x18000796f  movzx   eax, ax
0x180007972  or      eax, 80070000h
0x180007977  mov     edx, eax
0x180007979  lea     rcx, [rsp+78h+var_18]
0x18000797e  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180007983  mov     edx, 0F6h
0x180007988  mov     rcx, rbx
0x18000798b  movsd   xmm0, qword ptr [rax]
0x18000798f  mov     eax, [rax+8]
0x180007992  mov     [rsp+78h+var_20], eax
0x180007996  lea     rax, [rsp+78h+var_28]
0x18000799b  mov     [rsp+78h+var_48], rax
0x1800079a0  mov     [rsp+78h+var_50], rdi
0x1800079a5  movsd   [rsp+78h+var_28], xmm0
0x1800079ab  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
