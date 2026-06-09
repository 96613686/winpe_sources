# PrecacheStoreLicenseForPackageResume2$catch$6

- ea: `0x180012577`
- end: `0x1800125a7`
- name: `PrecacheStoreLicenseForPackageResume2$catch$6`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000e610`
- `0x18000ea84`

## pseudocode

```c
__int64 __fastcall PrecacheStoreLicenseForPackageResume2_catch_6(__int64 a1, __int64 a2, const char *a3)
{
  wil *v4; // rcx

  wil::details::in1diag3::Log_CaughtException((wil::details::in1diag3 *)0x34C, a2, a3);
  *(_DWORD *)(a2 + 80) = wil::ResultFromCaughtException(v4);
  return 0;
}

```

## disassembly

```asm
0x180012577  mov     [rsp+arg_8], rdx
0x18001257c  push    rbp
0x18001257d  sub     rsp, 40h
0x180012581  mov     rbp, rdx
0x180012584  mov     ecx, 34Ch; this
0x180012589  call    ?Log_CaughtException@in1diag3@details@wil@@YAJIPEBD@Z; wil::details::in1diag3::Log_CaughtException(uint,char const *)
0x18001258e  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180012593  mov     [rbp+50h], eax
0x180012596  mov     rax, 0
0x1800125a0  add     rsp, 40h
0x1800125a4  pop     rbp
0x1800125a5  retn
```
