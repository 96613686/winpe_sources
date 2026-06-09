# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140002b2c`
- end: `0x140002b9c`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `112`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002be8`

## callees

- `0x1400016e8`
- `0x140001cf8`
- `0x140002aac`

## string_xrefs

- `0x140002b43`: `C:\__w\1\s\UCPDMgr\wil\Microsoft.Windows.Wil.Internal.0.2.159\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<3>(
        wil::details *a1,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // edi
  int v7; // esi
  int LastErrorFail; // eax
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // xmm0_8
  int v12; // r8d
  int v13; // r9d
  const char *v14; // [rsp+20h] [rbp-58h]
  int v15; // [rsp+20h] [rbp-58h]
  void *v16; // [rsp+30h] [rbp-48h]
  __int64 v17; // [rsp+50h] [rbp-28h] BYREF
  int v18; // [rsp+58h] [rbp-20h]
  _BYTE v19[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"C:\\__w\\1\\s\\UCPDMgr\\wil\\Microsoft.Windows.Wil.Internal.0.2.159\\inc\\wil\\opensou"
                                  "rce\\wil\\resource.h",
                    a4,
                    v14,
                    a6,
                    v16);
  v9 = (unsigned __int16)LastErrorFail | 0x80070000;
  if ( LastErrorFail <= 0 )
    v9 = (unsigned int)LastErrorFail;
  v10 = wil::details::ResultStatus::FromResult(v19, v9);
  v11 = *(_QWORD *)v10;
  v18 = *(_DWORD *)(v10 + 8);
  v17 = v11;
  wil::details::ReportFailure_Base<3,0>(v7, v6, v12, v13, v15, (__int64)a6, (__int64)&v17);
}

```

## disassembly

```asm
0x140002b2c  mov     [rsp+arg_0], rbx
0x140002b31  mov     [rsp+arg_8], rsi
0x140002b36  push    rdi
0x140002b37  sub     rsp, 70h
0x140002b3b  mov     rbx, [rsp+78h+arg_28]
0x140002b43  lea     r8, aCW1SUcpdmgrWil; "C:\\__w\\1\\s\\UCPDMgr\\wil\\Microsoft."...
0x140002b4a  mov     [rsp+78h+var_50], rbx; char *
0x140002b4f  mov     edi, edx
0x140002b51  mov     rsi, rcx
0x140002b54  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x140002b59  movzx   edx, ax
0x140002b5c  lea     rcx, [rsp+78h+var_18]
0x140002b61  or      edx, 80070000h
0x140002b67  test    eax, eax
0x140002b69  cmovle  edx, eax
0x140002b6c  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x140002b71  mov     edx, edi
0x140002b73  mov     rcx, rsi
0x140002b76  movsd   xmm0, qword ptr [rax]
0x140002b7a  mov     eax, [rax+8]
0x140002b7d  mov     [rsp+78h+var_20], eax
0x140002b81  lea     rax, [rsp+78h+var_28]
0x140002b86  mov     [rsp+78h+var_48], rax
0x140002b8b  mov     [rsp+78h+var_50], rbx
0x140002b90  movsd   [rsp+78h+var_28], xmm0
0x140002b96  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
