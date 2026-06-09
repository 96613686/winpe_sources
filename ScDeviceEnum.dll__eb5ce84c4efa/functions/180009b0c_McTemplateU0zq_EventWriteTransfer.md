# McTemplateU0zq_EventWriteTransfer

- ea: `0x180009b0c`
- end: `0x180009ba1`
- name: `McTemplateU0zq_EventWriteTransfer`
- size: `149`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const wchar_t *, int)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180008ab0`
- `0x180009274`
- `0x180009490`
- `0x180010638`
- `0x1800106bc`
- `0x180010b54`
- `0x180010dd0`

## callees

- `0x180007120`
- `0x180009b0c`
- `0x18001e020`

## pseudocode

```c
ULONG __fastcall McTemplateU0zq_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3, int a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-48h] BYREF
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
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, (__int64)a3, 3u, &v7);
}

```

## disassembly

```asm
0x180009b0c  mov     [rsp+arg_18], r9d
0x180009b11  sub     rsp, 78h
0x180009b15  mov     rax, cs:__security_cookie
0x180009b1c  xor     rax, rsp
0x180009b1f  mov     [rsp+78h+var_18], rax
0x180009b24  xor     r9d, r9d
0x180009b27  test    r8, r8
0x180009b2a  jz      short loc_180009B43
0x180009b2c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009b30  inc     rax
0x180009b33  cmp     [r8+rax*2], r9w
0x180009b38  jnz     short loc_180009B30
0x180009b3a  lea     eax, ds:2[rax*2]
0x180009b41  jmp     short loc_180009B48
0x180009b43  mov     eax, 0Ah
0x180009b48  mov     [rsp+78h+var_30], eax
0x180009b4c  lea     rcx, aNull_0; "NULL"
0x180009b53  lea     rax, [rsp+78h+arg_18]
0x180009b5b  mov     [rsp+78h+var_2C], r9d
0x180009b60  test    r8, r8
0x180009b63  mov     [rsp+78h+var_28], rax
0x180009b68  lea     rax, [rsp+78h+var_48]
0x180009b6d  mov     [rsp+78h+var_20], 4
0x180009b76  cmovz   r8, rcx
0x180009b7a  mov     [rsp+78h+var_58], rax
0x180009b7f  mov     r9d, 3
0x180009b85  mov     [rsp+78h+var_38], r8
0x180009b8a  call    McGenEventWrite_EventWriteTransfer
0x180009b8f  mov     rcx, [rsp+78h+var_18]
0x180009b94  xor     rcx, rsp; StackCookie
0x180009b97  call    __security_check_cookie
0x180009b9c  add     rsp, 78h
0x180009ba0  retn
```
