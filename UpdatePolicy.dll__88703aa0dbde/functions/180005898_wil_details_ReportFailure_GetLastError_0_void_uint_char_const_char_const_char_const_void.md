# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180005898`
- end: `0x180005919`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180005920`

## callees

- `0x180006084`
- `0x1800064a4`
- `0x180007738`

## string_xrefs

- `0x1800058aa`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`
- `0x1800058e4`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`

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
  int v6; // edi
  int LastErrorFail; // eax
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // xmm0_8
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
                    (void *)0x173,
                    (unsigned int)"C:\\__w\\1\\s\\src\\inc\\UndockedUpdateStack.hpp",
                    a4,
                    v12,
                    a6,
                    v14);
  v8 = (unsigned __int16)LastErrorFail | 0x80070000;
  if ( LastErrorFail <= 0 )
    v8 = (unsigned int)LastErrorFail;
  v9 = wil::details::ResultStatus::FromResult(v17, v8);
  v10 = *(_QWORD *)v9;
  v16 = *(_DWORD *)(v9 + 8);
  v15 = v10;
  wil::details::ReportFailure_Base<0,0>(
    v6,
    371,
    (unsigned int)"C:\\__w\\1\\s\\src\\inc\\UndockedUpdateStack.hpp",
    v11,
    v13,
    (__int64)a6,
    (__int64)&v15,
    0);
}

```

## disassembly

```asm
0x180005898  mov     [rsp+arg_0], rbx
0x18000589d  push    rdi
0x18000589e  sub     rsp, 70h
0x1800058a2  mov     rbx, [rsp+78h+arg_28]
0x1800058aa  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x1800058b1  mov     edx, 173h; void *
0x1800058b6  mov     [rsp+78h+var_50], rbx; char *
0x1800058bb  mov     rdi, rcx
0x1800058be  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800058c3  movzx   edx, ax
0x1800058c6  lea     rcx, [rsp+78h+var_18]
0x1800058cb  or      edx, 80070000h
0x1800058d1  test    eax, eax
0x1800058d3  cmovle  edx, eax
0x1800058d6  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x1800058db  mov     [rsp+78h+var_40], 0
0x1800058e4  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x1800058eb  mov     edx, 173h
0x1800058f0  mov     rcx, rdi
0x1800058f3  movsd   xmm0, qword ptr [rax]
0x1800058f7  mov     eax, [rax+8]
0x1800058fa  mov     [rsp+78h+var_20], eax
0x1800058fe  lea     rax, [rsp+78h+var_28]
0x180005903  mov     [rsp+78h+var_48], rax
0x180005908  mov     [rsp+78h+var_50], rbx
0x18000590d  movsd   [rsp+78h+var_28], xmm0
0x180005913  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
