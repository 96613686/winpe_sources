# CommonUtil::MpSmartUtilsInitializeForExe(CommonUtil::MpUtilsType * *)

- ea: `0x140003680`
- end: `0x1400036a6`
- name: `?MpSmartUtilsInitializeForExe@CommonUtil@@YAJPEAPEAUMpUtilsType@1@@Z`
- size: `38`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, struct CommonUtil::MpUtilsType **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001dba4`

## callees

- `0x140003680`
- `0x1400036a8`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpSmartUtilsInitializeForExe(CommonUtil *this, struct CommonUtil::MpUtilsType **a2)
{
  __int64 result; // rax

  result = MpUtilsInitializeForExe(this, a2);
  if ( (int)result >= 0 )
  {
    *(_QWORD *)this = 286331153;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140003680  push    rbx
0x140003682  sub     rsp, 20h
0x140003686  mov     rbx, rcx
0x140003689  call    MpUtilsInitializeForExe
0x14000368e  mov     edx, eax
0x140003690  shr     edx, 1Fh
0x140003693  test    dl, dl
0x140003695  jnz     short loc_1400036A0
0x140003697  mov     qword ptr [rbx], 11111111h
0x14000369e  xor     eax, eax
0x1400036a0  add     rsp, 20h
0x1400036a4  pop     rbx
0x1400036a5  retn
```
