# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180015b50`
- end: `0x180015bc7`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `119`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015bd0`

## callees

- `0x180015b50`
- `0x180015bf0`
- `0x180015f10`
- `0x180016f00`

## string_xrefs

- `0x180015b67`: `C:\__w\1\s\product\APIs\shared\ImpersonationUtils.h`
- `0x180015b95`: `C:\__w\1\s\product\APIs\shared\ImpersonationUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<0>(
        wil::details *a1,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // ebx
  int v7; // edi
  signed int LastErrorFail; // eax
  __int64 v9; // rax
  __int64 v10; // xmm0_8
  int v11; // r9d
  const char *v12; // [rsp+20h] [rbp-58h]
  int v13; // [rsp+20h] [rbp-58h]
  void *v14; // [rsp+30h] [rbp-48h]
  __int64 v15; // [rsp+50h] [rbp-28h] BYREF
  int v16; // [rsp+58h] [rbp-20h]
  _BYTE v17[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"C:\\__w\\1\\s\\product\\APIs\\shared\\ImpersonationUtils.h",
                    a4,
                    v12,
                    a6,
                    v14);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v9 = wil::details::ResultStatus::FromResult(v17, (unsigned int)LastErrorFail);
  v10 = *(_QWORD *)v9;
  v16 = *(_DWORD *)(v9 + 8);
  v15 = v10;
  wil::details::ReportFailure_Base<0,0>(
    v7,
    v6,
    (unsigned int)"C:\\__w\\1\\s\\product\\APIs\\shared\\ImpersonationUtils.h",
    v11,
    v13,
    (__int64)a6,
    (__int64)&v15);
}

```

## disassembly

```asm
0x180015b50  mov     [rsp+arg_0], rbx
0x180015b55  mov     [rsp+arg_8], rsi
0x180015b5a  push    rdi
0x180015b5b  sub     rsp, 70h
0x180015b5f  mov     rsi, [rsp+78h+arg_28]
0x180015b67  lea     r8, aCW1SProductApi_26; "C:\\__w\\1\\s\\product\\APIs\\shared\\I"...
0x180015b6e  mov     [rsp+78h+var_50], rsi; char *
0x180015b73  mov     ebx, edx
0x180015b75  mov     rdi, rcx
0x180015b78  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180015b7d  test    eax, eax
0x180015b7f  jle     short loc_180015B89
0x180015b81  movzx   eax, ax
0x180015b84  or      eax, 80070000h
0x180015b89  mov     edx, eax
0x180015b8b  lea     rcx, [rsp+78h+var_18]
0x180015b90  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180015b95  lea     r8, aCW1SProductApi_26; "C:\\__w\\1\\s\\product\\APIs\\shared\\I"...
0x180015b9c  mov     edx, ebx
0x180015b9e  mov     rcx, rdi
0x180015ba1  movsd   xmm0, qword ptr [rax]
0x180015ba5  mov     eax, [rax+8]
0x180015ba8  mov     [rsp+78h+var_20], eax
0x180015bac  lea     rax, [rsp+78h+var_28]
0x180015bb1  mov     [rsp+78h+var_48], rax
0x180015bb6  mov     [rsp+78h+var_50], rsi
0x180015bbb  movsd   [rsp+78h+var_28], xmm0
0x180015bc1  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
