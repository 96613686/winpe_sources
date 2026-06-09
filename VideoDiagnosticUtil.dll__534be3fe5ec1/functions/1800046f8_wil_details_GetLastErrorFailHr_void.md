# wil::details::GetLastErrorFailHr(void)

- ea: `0x1800046f8`
- end: `0x18000474d`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `85`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003354`
- `0x180003700`
- `0x180008188`

## callees

- `0x1800025f4`
- `0x1800046f8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800046fc`
- `KERNEL32!GetLastError` at `0x1800046fc`

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
0x1800046f8  sub     rsp, 48h
0x1800046fc  call    cs:__imp_GetLastError
0x180004703  nop     dword ptr [rax+rax+00h]
0x180004708  test    eax, eax
0x18000470a  jnz     short loc_18000473D
0x18000470c  mov     rax, [rsp+48h]
0x180004711  xor     r9d, r9d; int
0x180004714  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x18000471c  xor     r8d, r8d; int
0x18000471f  mov     [rsp+48h+var_20], rax; __int64
0x180004724  xor     edx, edx; int
0x180004726  xor     ecx, ecx; int
0x180004728  mov     [rsp+48h+var_28], 0; __int64
0x180004731  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004736  mov     eax, 29Ch
0x18000473b  jmp     short loc_18000473F
0x18000473d  jle     short loc_180004747
0x18000473f  movzx   eax, ax
0x180004742  or      eax, 80070000h
0x180004747  add     rsp, 48h
0x18000474b  retn
```
