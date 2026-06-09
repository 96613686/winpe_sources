# wil::details::GetLastErrorFailHr(void)

- ea: `0x140003998`
- end: `0x1400039e9`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002d28`
- `0x1400030f8`

## callees

- `0x1400021b8`
- `0x140003998`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400039a3`
- `KERNEL32!GetLastError` at `0x1400039a3`

## pseudocode

```c
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
0x140003998  push    rbx
0x14000399a  sub     rsp, 40h
0x14000399e  mov     rbx, [rsp+48h]
0x1400039a3  call    cs:__imp_GetLastError
0x1400039a9  test    eax, eax
0x1400039ab  jnz     short loc_1400039D7
0x1400039ad  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x1400039b5  mov     [rsp+48h+var_20], rbx; __int64
0x1400039ba  mov     [rsp+48h+var_28], 0; __int64
0x1400039c3  xor     r9d, r9d; int
0x1400039c6  xor     r8d, r8d; int
0x1400039c9  xor     edx, edx; int
0x1400039cb  xor     ecx, ecx; int
0x1400039cd  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400039d2  mov     eax, 29Ch
0x1400039d7  test    eax, eax
0x1400039d9  jle     short loc_1400039E3
0x1400039db  movzx   eax, ax
0x1400039de  or      eax, 80070000h
0x1400039e3  add     rsp, 40h
0x1400039e7  pop     rbx
0x1400039e8  retn
```
