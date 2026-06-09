# wil::details::GetLastErrorFailHr(void)

- ea: `0x1400049c4`
- end: `0x140004a15`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003c20`
- `0x1400040e4`

## callees

- `0x1400023c0`
- `0x1400049c4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400049cf`
- `KERNEL32!GetLastError` at `0x1400049cf`

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
0x1400049c4  push    rbx
0x1400049c6  sub     rsp, 40h
0x1400049ca  mov     rbx, [rsp+48h]
0x1400049cf  call    cs:__imp_GetLastError
0x1400049d5  test    eax, eax
0x1400049d7  jnz     short loc_140004A03
0x1400049d9  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x1400049e1  mov     [rsp+48h+var_20], rbx; __int64
0x1400049e6  mov     [rsp+48h+var_28], 0; __int64
0x1400049ef  xor     r9d, r9d; int
0x1400049f2  xor     r8d, r8d; int
0x1400049f5  xor     edx, edx; int
0x1400049f7  xor     ecx, ecx; int
0x1400049f9  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400049fe  mov     eax, 29Ch
0x140004a03  test    eax, eax
0x140004a05  jle     short loc_140004A0F
0x140004a07  movzx   eax, ax
0x140004a0a  or      eax, 80070000h
0x140004a0f  add     rsp, 40h
0x140004a13  pop     rbx
0x140004a14  retn
```
