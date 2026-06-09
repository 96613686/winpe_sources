# McTemplateU0zq_EtwEventWriteTransfer

- ea: `0x180017004`
- end: `0x180017099`
- name: `McTemplateU0zq_EtwEventWriteTransfer`
- size: `149`
- prototype: `__int64 __fastcall(__int64, int, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800043d0`

## callees

- `0x180007da0`
- `0x180017004`
- `0x18001a380`

## pseudocode

```c
__int64 __fastcall McTemplateU0zq_EtwEventWriteTransfer(__int64 a1, int a2, const wchar_t *a3, int a4)
{
  __int64 v4; // rax
  int v5; // eax
  _BYTE v7[16]; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-38h]
  int v9; // [rsp+48h] [rbp-30h]
  int v10; // [rsp+4Ch] [rbp-2Ch]
  int *v11; // [rsp+50h] [rbp-28h]
  __int64 v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+98h] [rbp+20h] BYREF

  v13 = a4;
  if ( a3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a3[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  v9 = v5;
  v10 = 0;
  v11 = &v13;
  v12 = 4;
  if ( !a3 )
    a3 = L"NULL";
  v8 = a3;
  return McGenEventWrite_EtwEventWriteTransfer((unsigned int)L"NULL", a2, (_DWORD)a3, 3, (__int64)v7);
}

```

## disassembly

```asm
0x180017004  mov     [rsp+arg_18], r9d
0x180017009  sub     rsp, 78h
0x18001700d  mov     rax, cs:__security_cookie
0x180017014  xor     rax, rsp
0x180017017  mov     [rsp+78h+var_18], rax
0x18001701c  xor     r9d, r9d
0x18001701f  test    r8, r8
0x180017022  jz      short loc_18001703B
0x180017024  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017028  inc     rax
0x18001702b  cmp     [r8+rax*2], r9w
0x180017030  jnz     short loc_180017028
0x180017032  lea     eax, ds:2[rax*2]
0x180017039  jmp     short loc_180017040
0x18001703b  mov     eax, 0Ah
0x180017040  mov     [rsp+78h+var_30], eax
0x180017044  lea     rcx, aNull_1; "NULL"
0x18001704b  lea     rax, [rsp+78h+arg_18]
0x180017053  mov     [rsp+78h+var_2C], r9d
0x180017058  test    r8, r8
0x18001705b  mov     [rsp+78h+var_28], rax
0x180017060  lea     rax, [rsp+78h+var_48]
0x180017065  mov     [rsp+78h+var_20], 4
0x18001706e  cmovz   r8, rcx
0x180017072  mov     [rsp+78h+var_58], rax
0x180017077  mov     r9d, 3
0x18001707d  mov     [rsp+78h+var_38], r8
0x180017082  call    McGenEventWrite_EtwEventWriteTransfer
0x180017087  mov     rcx, [rsp+78h+var_18]
0x18001708c  xor     rcx, rsp; StackCookie
0x18001708f  call    __security_check_cookie
0x180017094  add     rsp, 78h
0x180017098  retn
```
