# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18002e160`
- end: `0x18002e1e0`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `128`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002e1e0`

## callees

- `0x180002b10`
- `0x180003c90`
- `0x1800137e0`
- `0x18002e160`

## string_xrefs

- `0x18002e177`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.2.162\inc\wil\opensource\wil\resource.h`
- `0x18002e1ae`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.2.162\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<3>(
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
                    (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.2.162\\inc\\wil\\opensource\\wil\\resource.h",
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
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.2.162\\inc\\wil\\opensource\\wil\\resource.h",
    v11,
    v13,
    (__int64)a6,
    (__int64)&v15,
    0);
}

```

## disassembly

```asm
0x18002e160  mov     [rsp+arg_0], rbx
0x18002e165  mov     [rsp+arg_8], rsi
0x18002e16a  push    rdi
0x18002e16b  sub     rsp, 70h
0x18002e16f  mov     rsi, [rsp+78h+arg_28]
0x18002e177  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18002e17e  mov     [rsp+78h+var_50], rsi; char *
0x18002e183  mov     ebx, edx
0x18002e185  mov     rdi, rcx
0x18002e188  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18002e18d  test    eax, eax
0x18002e18f  jle     short loc_18002E199
0x18002e191  movzx   eax, ax
0x18002e194  or      eax, 80070000h
0x18002e199  mov     edx, eax
0x18002e19b  lea     rcx, [rsp+78h+var_18]
0x18002e1a0  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x18002e1a5  mov     [rsp+78h+var_40], 0
0x18002e1ae  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18002e1b5  mov     edx, ebx
0x18002e1b7  mov     rcx, rdi
0x18002e1ba  movsd   xmm0, qword ptr [rax]
0x18002e1be  mov     eax, [rax+8]
0x18002e1c1  mov     [rsp+78h+var_20], eax
0x18002e1c5  lea     rax, [rsp+78h+var_28]
0x18002e1ca  mov     [rsp+78h+var_48], rax
0x18002e1cf  mov     [rsp+78h+var_50], rsi
0x18002e1d4  movsd   [rsp+78h+var_28], xmm0
0x18002e1da  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
