# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18000ee50`
- end: `0x18000eec8`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `120`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800154a4`

## callees

- `0x180003d28`
- `0x1800061e0`
- `0x180006744`
- `0x18000ee50`

## string_xrefs

- `0x18000ee67`: `onecore\base\ci\management\dll\manageci.cpp`
- `0x18000ee9a`: `onecore\base\ci\management\dll\manageci.cpp`

## pseudocode

```c
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
  int v9; // r9d
  const char *v10; // [rsp+20h] [rbp-48h]
  void *v11; // [rsp+30h] [rbp-38h]

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
                    a4,
                    v10,
                    a6,
                    v11);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail, 0);
  wil::details::ReportFailure_Base<0,0>(v7, v6, (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp", v9);
}

```

## disassembly

```asm
0x18000ee50  mov     [rsp+arg_0], rbx
0x18000ee55  mov     [rsp+arg_8], rsi
0x18000ee5a  push    rdi
0x18000ee5b  sub     rsp, 60h
0x18000ee5f  mov     rsi, [rsp+68h+arg_28]
0x18000ee67  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x18000ee6e  mov     [rsp+68h+var_40], rsi; char *
0x18000ee73  mov     ebx, edx
0x18000ee75  mov     rdi, rcx
0x18000ee78  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000ee7d  xor     edx, edx; int
0x18000ee7f  test    eax, eax
0x18000ee81  jle     short loc_18000EE8B
0x18000ee83  movzx   eax, ax
0x18000ee86  or      eax, 80070000h
0x18000ee8b  mov     ecx, eax; this
0x18000ee8d  mov     [rsp+68h+var_18], eax
0x18000ee91  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ee96  mov     [rsp+68h+var_28], edx
0x18000ee9a  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x18000eea1  mov     [rsp+68h+var_30], rdx
0x18000eea6  mov     rcx, rdi
0x18000eea9  mov     [rsp+68h+var_14], eax
0x18000eead  lea     rax, [rsp+68h+var_18]
0x18000eeb2  mov     [rsp+68h+var_10], edx
0x18000eeb6  mov     edx, ebx
0x18000eeb8  mov     [rsp+68h+var_38], rax
0x18000eebd  mov     [rsp+68h+var_40], rsi
0x18000eec2  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
