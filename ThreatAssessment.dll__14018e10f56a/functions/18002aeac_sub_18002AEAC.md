# sub_18002AEAC

- ea: `0x18002aeac`
- end: `0x18002af24`
- name: `sub_18002AEAC`
- size: `120`
- prototype: `BOOL __fastcall(LPINIT_ONCE lpInitOnce, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800470f4`

## callees

- `0x18002aeac`
- `0x18004ab50`
- `0x18013e840`
- `0x180141350`
- `0x18014cd80`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x18002aef6`
- `KERNEL32!InitOnceComplete` at `0x18002aef6`
- `KERNEL32!InitOnceBeginInitialize` at `0x18002aed5`
- `KERNEL32!InitOnceBeginInitialize` at `0x18002aed5`

## pseudocode

```c
BOOL __fastcall sub_18002AEAC(LPINIT_ONCE lpInitOnce, _QWORD *a2)
{
  BOOL result; // eax
  WINBOOL fPending; // [rsp+20h] [rbp-18h] BYREF

  result = InitOnceBeginInitialize(lpInitOnce, 0, &fPending, 0);
  if ( !result )
    sub_18014CD80();
  if ( fPending )
  {
    sub_18004AB50(*a2);
    result = InitOnceComplete(lpInitOnce, 0, 0);
    if ( !result )
      sub_18013E840();
  }
  return result;
}

```

## disassembly

```asm
0x18002aeac  mov     [rsp+arg_10], rbx
0x18002aeb1  push    rdi
0x18002aeb2  sub     rsp, 30h
0x18002aeb6  mov     rax, cs:__security_cookie
0x18002aebd  xor     rax, rsp
0x18002aec0  mov     [rsp+38h+var_10], rax
0x18002aec5  mov     rdi, rdx
0x18002aec8  lea     r8, [rsp+38h+fPending]; fPending
0x18002aecd  xor     edx, edx; dwFlags
0x18002aecf  xor     r9d, r9d; lpContext
0x18002aed2  mov     rbx, rcx
0x18002aed5  call    cs:InitOnceBeginInitialize
0x18002aedb  test    eax, eax
0x18002aedd  jz      short loc_18002AF1E
0x18002aedf  cmp     [rsp+38h+fPending], 0
0x18002aee4  jz      short loc_18002AF00
0x18002aee6  mov     rcx, [rdi]
0x18002aee9  call    sub_18004AB50
0x18002aeee  xor     r8d, r8d; lpContext
0x18002aef1  xor     edx, edx; dwFlags
0x18002aef3  mov     rcx, rbx; lpInitOnce
0x18002aef6  call    cs:InitOnceComplete
0x18002aefc  test    eax, eax
0x18002aefe  jz      short loc_18002AF18
0x18002af00  mov     rcx, [rsp+38h+var_10]
0x18002af05  xor     rcx, rsp; StackCookie
0x18002af08  call    __security_check_cookie
0x18002af0d  mov     rbx, [rsp+38h+arg_10]
0x18002af12  add     rsp, 30h
0x18002af16  pop     rdi
0x18002af17  retn
0x18002af18  call    sub_18013E840
0x18002af1e  call    sub_18014CD80
```
