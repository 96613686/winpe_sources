# wil::details::GetLastErrorFailHr(void)

- ea: `0x180005024`
- end: `0x180005072`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800038a8`
- `0x180003c4c`
- `0x180004044`

## callees

- `0x180002834`
- `0x180005024`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005028`
- `KERNEL32!GetLastError` at `0x180005028`

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
0x180005024  sub     rsp, 48h
0x180005028  call    cs:__imp_GetLastError
0x18000502e  test    eax, eax
0x180005030  jnz     short loc_180005063
0x180005032  mov     rax, [rsp+48h]
0x180005037  xor     r9d, r9d; int
0x18000503a  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180005042  xor     r8d, r8d; int
0x180005045  mov     [rsp+48h+var_20], rax; __int64
0x18000504a  xor     edx, edx; int
0x18000504c  xor     ecx, ecx; int
0x18000504e  mov     [rsp+48h+var_28], 0; __int64
0x180005057  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000505c  mov     eax, 29Ch
0x180005061  jmp     short loc_180005065
0x180005063  jle     short loc_18000506D
0x180005065  movzx   eax, ax
0x180005068  or      eax, 80070000h
0x18000506d  add     rsp, 48h
0x180005071  retn
```
