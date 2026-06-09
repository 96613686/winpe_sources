# wil::details::GetLastErrorFailHr(void)

- ea: `0x1400045a8`
- end: `0x1400045f9`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003960`
- `0x140003d30`
- `0x140008710`

## callees

- `0x140002dac`
- `0x1400045a8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400045b3`
- `KERNEL32!GetLastError` at `0x1400045b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall wil::details::GetLastErrorFailHr(wil::details *this)
{
  signed int result; // eax
  wil::details *v2; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  result = GetLastError();
  if ( !result )
  {
    LODWORD(v2) = -2147024228;
    wil::details::ReportFailure_Hr<2>(0, 0, 0, 0, 0, retaddr, v2);
    result = 668;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1400045a8  push    rbx
0x1400045aa  sub     rsp, 40h
0x1400045ae  mov     rbx, [rsp+48h]
0x1400045b3  call    cs:__imp_GetLastError
0x1400045b9  test    eax, eax
0x1400045bb  jnz     short loc_1400045E7
0x1400045bd  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x1400045c5  mov     [rsp+48h+var_20], rbx; __int64
0x1400045ca  mov     [rsp+48h+var_28], 0; __int64
0x1400045d3  xor     r9d, r9d; int
0x1400045d6  xor     r8d, r8d; int
0x1400045d9  xor     edx, edx; int
0x1400045db  xor     ecx, ecx; int
0x1400045dd  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400045e2  mov     eax, 29Ch
0x1400045e7  test    eax, eax
0x1400045e9  jle     short loc_1400045F3
0x1400045eb  movzx   eax, ax
0x1400045ee  or      eax, 80070000h
0x1400045f3  add     rsp, 40h
0x1400045f7  pop     rbx
0x1400045f8  retn
```
