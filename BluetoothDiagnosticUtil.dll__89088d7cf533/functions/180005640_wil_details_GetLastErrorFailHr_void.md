# wil::details::GetLastErrorFailHr(void)

- ea: `0x180005640`
- end: `0x180005698`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `88`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004cb4`
- `0x1800081f8`

## callees

- `0x1800020e8`
- `0x180005640`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000564b`
- `KERNEL32!GetLastError` at `0x18000564b`

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
0x180005640  push    rbx
0x180005642  sub     rsp, 40h
0x180005646  mov     rbx, [rsp+48h]
0x18000564b  call    cs:__imp_GetLastError
0x180005652  nop     dword ptr [rax+rax+00h]
0x180005657  test    eax, eax
0x180005659  jnz     short loc_180005685
0x18000565b  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180005663  mov     [rsp+48h+var_20], rbx; __int64
0x180005668  mov     [rsp+48h+var_28], 0; __int64
0x180005671  xor     r9d, r9d; int
0x180005674  xor     r8d, r8d; int
0x180005677  xor     edx, edx; int
0x180005679  xor     ecx, ecx; int
0x18000567b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005680  mov     eax, 29Ch
0x180005685  test    eax, eax
0x180005687  jle     short loc_180005691
0x180005689  movzx   eax, ax
0x18000568c  or      eax, 80070000h
0x180005691  add     rsp, 40h
0x180005695  pop     rbx
0x180005696  retn
```
