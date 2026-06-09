# McTemplateU0z_EventWriteTransfer

- ea: `0x18000a508`
- end: `0x18000a582`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `122`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const wchar_t *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800094c8`
- `0x180010120`

## callees

- `0x18000a4b0`
- `0x18000a508`
- `0x180013840`

## pseudocode

```c
ULONG __fastcall McTemplateU0z_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v7; // [rsp+40h] [rbp-28h]
  int v8; // [rsp+48h] [rbp-20h]
  int v9; // [rsp+4Ch] [rbp-1Ch]

  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = 2 * v3 + 2;
  }
  else
  {
    v4 = 10;
  }
  v8 = v4;
  v9 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v7 = a3;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, (__int64)a3, 2u, &v6);
}

```

## disassembly

```asm
0x18000a508  sub     rsp, 68h
0x18000a50c  mov     rax, cs:__security_cookie
0x18000a513  xor     rax, rsp
0x18000a516  mov     [rsp+68h+var_18], rax
0x18000a51b  xor     r9d, r9d
0x18000a51e  test    r8, r8
0x18000a521  jz      short loc_18000A53A
0x18000a523  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a527  inc     rax
0x18000a52a  cmp     [r8+rax*2], r9w
0x18000a52f  jnz     short loc_18000A527
0x18000a531  lea     eax, ds:2[rax*2]
0x18000a538  jmp     short loc_18000A53F
0x18000a53a  mov     eax, 0Ah
0x18000a53f  test    r8, r8
0x18000a542  mov     [rsp+68h+var_20], eax
0x18000a546  lea     rcx, aNull_1; "NULL"
0x18000a54d  mov     [rsp+68h+var_1C], r9d
0x18000a552  cmovz   r8, rcx
0x18000a556  lea     rax, [rsp+68h+var_38]
0x18000a55b  mov     r9d, 2
0x18000a561  mov     [rsp+68h+var_28], r8
0x18000a566  mov     [rsp+68h+var_48], rax
0x18000a56b  call    McGenEventWrite_EventWriteTransfer
0x18000a570  mov     rcx, [rsp+68h+var_18]
0x18000a575  xor     rcx, rsp; StackCookie
0x18000a578  call    __security_check_cookie
0x18000a57d  add     rsp, 68h
0x18000a581  retn
```
