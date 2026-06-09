# wil::details::GetLastErrorFailHr(void)

- ea: `0x180004658`
- end: `0x1800046a6`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003648`
- `0x180003a54`

## callees

- `0x1800027fc`
- `0x180004658`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000465c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000465c`

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
0x180004658  sub     rsp, 48h
0x18000465c  call    cs:__imp_GetLastError
0x180004662  test    eax, eax
0x180004664  jnz     short loc_180004697
0x180004666  mov     rax, [rsp+48h]
0x18000466b  xor     r9d, r9d; int
0x18000466e  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180004676  xor     r8d, r8d; int
0x180004679  mov     [rsp+48h+var_20], rax; __int64
0x18000467e  xor     edx, edx; int
0x180004680  xor     ecx, ecx; int
0x180004682  mov     [rsp+48h+var_28], 0; __int64
0x18000468b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004690  mov     eax, 29Ch
0x180004695  jmp     short loc_180004699
0x180004697  jle     short loc_1800046A1
0x180004699  movzx   eax, ax
0x18000469c  or      eax, 80070000h
0x1800046a1  add     rsp, 48h
0x1800046a5  retn
```
