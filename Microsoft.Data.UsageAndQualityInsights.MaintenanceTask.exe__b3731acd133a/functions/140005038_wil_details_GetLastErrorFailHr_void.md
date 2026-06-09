# wil::details::GetLastErrorFailHr(void)

- ea: `0x140005038`
- end: `0x140005089`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003a78`
- `0x140003e1c`
- `0x1400041ec`

## callees

- `0x14000274c`
- `0x140005038`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005043`

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
0x140005038  push    rbx
0x14000503a  sub     rsp, 40h
0x14000503e  mov     rbx, [rsp+48h]
0x140005043  call    cs:__imp_GetLastError
0x140005049  test    eax, eax
0x14000504b  jnz     short loc_140005077
0x14000504d  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x140005055  mov     [rsp+48h+var_20], rbx; __int64
0x14000505a  mov     [rsp+48h+var_28], 0; __int64
0x140005063  xor     r9d, r9d; int
0x140005066  xor     r8d, r8d; int
0x140005069  xor     edx, edx; int
0x14000506b  xor     ecx, ecx; int
0x14000506d  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140005072  mov     eax, 29Ch
0x140005077  test    eax, eax
0x140005079  jle     short loc_140005083
0x14000507b  movzx   eax, ax
0x14000507e  or      eax, 80070000h
0x140005083  add     rsp, 40h
0x140005087  pop     rbx
0x140005088  retn
```
