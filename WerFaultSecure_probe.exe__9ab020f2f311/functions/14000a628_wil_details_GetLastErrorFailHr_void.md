# wil::details::GetLastErrorFailHr(void)

- ea: `0x14000a628`
- end: `0x14000a679`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140008f9c`
- `0x14000936c`
- `0x140009764`

## callees

- `0x140004a5c`
- `0x14000a628`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a633`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a633`

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
0x14000a628  push    rbx
0x14000a62a  sub     rsp, 40h
0x14000a62e  mov     rbx, [rsp+48h]
0x14000a633  call    cs:__imp_GetLastError
0x14000a639  test    eax, eax
0x14000a63b  jnz     short loc_14000A667
0x14000a63d  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x14000a645  mov     [rsp+48h+var_20], rbx; __int64
0x14000a64a  mov     [rsp+48h+var_28], 0; __int64
0x14000a653  xor     r9d, r9d; int
0x14000a656  xor     r8d, r8d; int
0x14000a659  xor     edx, edx; int
0x14000a65b  xor     ecx, ecx; int
0x14000a65d  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000a662  mov     eax, 29Ch
0x14000a667  test    eax, eax
0x14000a669  jle     short loc_14000A673
0x14000a66b  movzx   eax, ax
0x14000a66e  or      eax, 80070000h
0x14000a673  add     rsp, 40h
0x14000a677  pop     rbx
0x14000a678  retn
```
