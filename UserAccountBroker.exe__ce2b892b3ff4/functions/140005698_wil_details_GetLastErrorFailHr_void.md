# wil::details::GetLastErrorFailHr(void)

- ea: `0x140005698`
- end: `0x1400056e6`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400049d0`
- `0x140004da0`

## callees

- `0x14000419c`
- `0x140005698`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000569c`
- `KERNEL32!GetLastError` at `0x14000569c`

## pseudocode

```c
signed int __fastcall wil::details::GetLastErrorFailHr(wil::details *this)
{
  signed int result; // eax
  wil::details *v2; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  result = GetLastError();
  if ( result )
  {
    if ( result <= 0 )
      return result;
  }
  else
  {
    LODWORD(v2) = -2147024228;
    wil::details::ReportFailure_Hr<2>(0, 0, 0, 0, 0, retaddr, v2);
    LOWORD(result) = 668;
  }
  return (unsigned __int16)result | 0x80070000;
}

```

## disassembly

```asm
0x140005698  sub     rsp, 48h
0x14000569c  call    cs:__imp_GetLastError
0x1400056a2  test    eax, eax
0x1400056a4  jnz     short loc_1400056D7
0x1400056a6  mov     rax, [rsp+48h]
0x1400056ab  xor     r9d, r9d; int
0x1400056ae  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x1400056b6  xor     r8d, r8d; int
0x1400056b9  mov     [rsp+48h+var_20], rax; __int64
0x1400056be  xor     edx, edx; int
0x1400056c0  xor     ecx, ecx; int
0x1400056c2  mov     [rsp+48h+var_28], 0; __int64
0x1400056cb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400056d0  mov     eax, 29Ch
0x1400056d5  jmp     short loc_1400056D9
0x1400056d7  jle     short loc_1400056E1
0x1400056d9  movzx   eax, ax
0x1400056dc  or      eax, 80070000h
0x1400056e1  add     rsp, 48h
0x1400056e5  retn
```
