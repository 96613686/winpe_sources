# McTemplateU0s_EtwEventWriteTransfer

- ea: `0x180007d20`
- end: `0x180007d99`
- name: `McTemplateU0s_EtwEventWriteTransfer`
- size: `121`
- prototype: `__int64 __fastcall(__int64, int, const char *)`
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x180001d90`
- `0x180002560`
- `0x180003000`
- `0x1800030f0`
- `0x180003dc0`
- `0x180003fb0`
- `0x1800043d0`
- `0x1800058e0`
- `0x180005a90`
- `0x180005b30`
- `0x180005c20`
- `0x180006600`
- `0x1800066f0`
- `0x180007ea0`
- `0x18000bee0`

## callees

- `0x180007d20`
- `0x180007da0`
- `0x18001a380`

## pseudocode

```c
__int64 __fastcall McTemplateU0s_EtwEventWriteTransfer(__int64 a1, int a2, const char *a3)
{
  __int64 v3; // rax
  int v4; // eax
  _BYTE v6[16]; // [rsp+30h] [rbp-38h] BYREF
  const char *v7; // [rsp+40h] [rbp-28h]
  int v8; // [rsp+48h] [rbp-20h]
  int v9; // [rsp+4Ch] [rbp-1Ch]

  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = v3 + 1;
  }
  else
  {
    v4 = 5;
  }
  v8 = v4;
  v9 = 0;
  if ( !a3 )
    a3 = "NULL";
  v7 = a3;
  return McGenEventWrite_EtwEventWriteTransfer((unsigned int)"NULL", a2, (_DWORD)a3, 2, (__int64)v6);
}

```

## disassembly

```asm
0x180007d20  sub     rsp, 68h
0x180007d24  mov     rax, cs:__security_cookie
0x180007d2b  xor     rax, rsp
0x180007d2e  mov     [rsp+68h+var_18], rax
0x180007d33  test    r8, r8
0x180007d36  jz      short loc_180007D92
0x180007d38  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180007d3f  nop
0x180007d40  inc     rax
0x180007d43  cmp     byte ptr [r8+rax], 0
0x180007d48  jnz     short loc_180007D40
0x180007d4a  inc     eax
0x180007d4c  test    r8, r8
0x180007d4f  mov     [rsp+68h+var_20], eax
0x180007d53  lea     rcx, aNull; "NULL"
0x180007d5a  mov     [rsp+68h+var_1C], 0
0x180007d62  cmovz   r8, rcx
0x180007d66  lea     rax, [rsp+68h+var_38]
0x180007d6b  mov     r9d, 2
0x180007d71  mov     [rsp+68h+var_28], r8
0x180007d76  mov     [rsp+68h+var_48], rax
0x180007d7b  call    McGenEventWrite_EtwEventWriteTransfer
0x180007d80  mov     rcx, [rsp+68h+var_18]
0x180007d85  xor     rcx, rsp; StackCookie
0x180007d88  call    __security_check_cookie
0x180007d8d  add     rsp, 68h
0x180007d91  retn
0x180007d92  mov     eax, 5
0x180007d97  jmp     short loc_180007D4C
```
