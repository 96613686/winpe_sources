# sub_18002AFAC

- ea: `0x18002afac`
- end: `0x18002b024`
- name: `sub_18002AFAC`
- size: `120`
- prototype: `BOOL __fastcall(LPINIT_ONCE lpInitOnce, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180047010`

## callees

- `0x18002afac`
- `0x18004a054`
- `0x18013e840`
- `0x180141350`
- `0x18014cd80`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x18002aff6`
- `KERNEL32!InitOnceComplete` at `0x18002aff6`
- `KERNEL32!InitOnceBeginInitialize` at `0x18002afd5`
- `KERNEL32!InitOnceBeginInitialize` at `0x18002afd5`

## pseudocode

```c
BOOL __fastcall sub_18002AFAC(LPINIT_ONCE lpInitOnce, _QWORD *a2)
{
  BOOL result; // eax
  WINBOOL fPending; // [rsp+20h] [rbp-18h] BYREF

  result = InitOnceBeginInitialize(lpInitOnce, 0, &fPending, 0);
  if ( !result )
    sub_18014CD80();
  if ( fPending )
  {
    sub_18004A054(*a2);
    result = InitOnceComplete(lpInitOnce, 0, 0);
    if ( !result )
      sub_18013E840();
  }
  return result;
}

```

## disassembly

```asm
0x18002afac  mov     [rsp+arg_10], rbx
0x18002afb1  push    rdi
0x18002afb2  sub     rsp, 30h
0x18002afb6  mov     rax, cs:__security_cookie
0x18002afbd  xor     rax, rsp
0x18002afc0  mov     [rsp+38h+var_10], rax
0x18002afc5  mov     rdi, rdx
0x18002afc8  lea     r8, [rsp+38h+fPending]; fPending
0x18002afcd  xor     edx, edx; dwFlags
0x18002afcf  xor     r9d, r9d; lpContext
0x18002afd2  mov     rbx, rcx
0x18002afd5  call    cs:InitOnceBeginInitialize
0x18002afdb  test    eax, eax
0x18002afdd  jz      short loc_18002B01E
0x18002afdf  cmp     [rsp+38h+fPending], 0
0x18002afe4  jz      short loc_18002B000
0x18002afe6  mov     rcx, [rdi]
0x18002afe9  call    sub_18004A054
0x18002afee  xor     r8d, r8d; lpContext
0x18002aff1  xor     edx, edx; dwFlags
0x18002aff3  mov     rcx, rbx; lpInitOnce
0x18002aff6  call    cs:InitOnceComplete
0x18002affc  test    eax, eax
0x18002affe  jz      short loc_18002B018
0x18002b000  mov     rcx, [rsp+38h+var_10]
0x18002b005  xor     rcx, rsp; StackCookie
0x18002b008  call    __security_check_cookie
0x18002b00d  mov     rbx, [rsp+38h+arg_10]
0x18002b012  add     rsp, 30h
0x18002b016  pop     rdi
0x18002b017  retn
0x18002b018  call    sub_18013E840
0x18002b01e  call    sub_18014CD80
```
