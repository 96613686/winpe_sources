# sub_18002ADBC

- ea: `0x18002adbc`
- end: `0x18002ae34`
- name: `sub_18002ADBC`
- size: `120`
- prototype: `BOOL __fastcall(LPINIT_ONCE lpInitOnce, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180046fc4`

## callees

- `0x18002adbc`
- `0x180049cb8`
- `0x18013e840`
- `0x180141350`
- `0x18014cd80`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x18002ae06`
- `KERNEL32!InitOnceComplete` at `0x18002ae06`
- `KERNEL32!InitOnceBeginInitialize` at `0x18002ade5`
- `KERNEL32!InitOnceBeginInitialize` at `0x18002ade5`

## pseudocode

```c
BOOL __fastcall sub_18002ADBC(LPINIT_ONCE lpInitOnce, _QWORD *a2)
{
  BOOL result; // eax
  WINBOOL fPending; // [rsp+20h] [rbp-18h] BYREF

  result = InitOnceBeginInitialize(lpInitOnce, 0, &fPending, 0);
  if ( !result )
    sub_18014CD80();
  if ( fPending )
  {
    sub_180049CB8(*a2);
    result = InitOnceComplete(lpInitOnce, 0, 0);
    if ( !result )
      sub_18013E840();
  }
  return result;
}

```

## disassembly

```asm
0x18002adbc  mov     [rsp+arg_10], rbx
0x18002adc1  push    rdi
0x18002adc2  sub     rsp, 30h
0x18002adc6  mov     rax, cs:__security_cookie
0x18002adcd  xor     rax, rsp
0x18002add0  mov     [rsp+38h+var_10], rax
0x18002add5  mov     rdi, rdx
0x18002add8  lea     r8, [rsp+38h+fPending]; fPending
0x18002addd  xor     edx, edx; dwFlags
0x18002addf  xor     r9d, r9d; lpContext
0x18002ade2  mov     rbx, rcx
0x18002ade5  call    cs:InitOnceBeginInitialize
0x18002adeb  test    eax, eax
0x18002aded  jz      short loc_18002AE2E
0x18002adef  cmp     [rsp+38h+fPending], 0
0x18002adf4  jz      short loc_18002AE10
0x18002adf6  mov     rcx, [rdi]
0x18002adf9  call    sub_180049CB8
0x18002adfe  xor     r8d, r8d; lpContext
0x18002ae01  xor     edx, edx; dwFlags
0x18002ae03  mov     rcx, rbx; lpInitOnce
0x18002ae06  call    cs:InitOnceComplete
0x18002ae0c  test    eax, eax
0x18002ae0e  jz      short loc_18002AE28
0x18002ae10  mov     rcx, [rsp+38h+var_10]
0x18002ae15  xor     rcx, rsp; StackCookie
0x18002ae18  call    __security_check_cookie
0x18002ae1d  mov     rbx, [rsp+38h+arg_10]
0x18002ae22  add     rsp, 30h
0x18002ae26  pop     rdi
0x18002ae27  retn
0x18002ae28  call    sub_18013E840
0x18002ae2e  call    sub_18014CD80
```
