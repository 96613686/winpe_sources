# McTemplateU0dz_EventWriteTransfer

- ea: `0x1400113a0`
- end: `0x140011431`
- name: `McTemplateU0dz_EventWriteTransfer`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140010900`

## callees

- `0x140006748`
- `0x1400113a0`
- `0x140012f60`

## pseudocode

```c
ULONG __fastcall McTemplateU0dz_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, int a3, const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-48h] BYREF
  int *v8; // [rsp+40h] [rbp-38h]
  __int64 v9; // [rsp+48h] [rbp-30h]
  const wchar_t *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]
  int v13; // [rsp+90h] [rbp+18h] BYREF

  v13 = a3;
  v9 = 4;
  v8 = &v13;
  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  v11 = v5;
  v12 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v10 = a4;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, 0, 3u, &v7);
}

```

## disassembly

```asm
0x1400113a0  mov     r11, rsp
0x1400113a3  mov     [r11+18h], r8d
0x1400113a7  sub     rsp, 78h
0x1400113ab  mov     rax, cs:__security_cookie
0x1400113b2  xor     rax, rsp
0x1400113b5  mov     [rsp+78h+var_18], rax
0x1400113ba  xor     r8d, r8d
0x1400113bd  mov     qword ptr [r11-30h], 4
0x1400113c5  lea     rax, [r11+18h]
0x1400113c9  mov     [r11-38h], rax
0x1400113cd  test    r9, r9
0x1400113d0  jz      short loc_1400113E9
0x1400113d2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400113d6  inc     rax
0x1400113d9  cmp     [r9+rax*2], r8w
0x1400113de  jnz     short loc_1400113D6
0x1400113e0  lea     eax, ds:2[rax*2]
0x1400113e7  jmp     short loc_1400113EE
0x1400113e9  mov     eax, 0Ah
0x1400113ee  test    r9, r9
0x1400113f1  mov     [rsp+78h+var_20], eax
0x1400113f5  lea     rcx, aNull_0; "NULL"
0x1400113fc  mov     [rsp+78h+var_1C], r8d
0x140011401  cmovz   r9, rcx
0x140011405  lea     rax, [rsp+78h+var_48]
0x14001140a  mov     [rsp+78h+var_28], r9
0x14001140f  mov     r9d, 3
0x140011415  mov     [rsp+78h+var_58], rax
0x14001141a  call    McGenEventWrite_EventWriteTransfer
0x14001141f  mov     rcx, [rsp+78h+var_18]
0x140011424  xor     rcx, rsp; StackCookie
0x140011427  call    __security_check_cookie
0x14001142c  add     rsp, 78h
0x140011430  retn
```
