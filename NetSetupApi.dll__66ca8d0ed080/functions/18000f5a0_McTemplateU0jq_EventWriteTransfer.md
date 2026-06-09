# McTemplateU0jq_EventWriteTransfer

- ea: `0x18000f5a0`
- end: `0x18000f602`
- name: `McTemplateU0jq_EventWriteTransfer`
- size: `98`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, int)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180001210`
- `0x180001390`
- `0x1800015b0`
- `0x180001600`
- `0x1800017a0`
- `0x180001900`
- `0x180003970`
- `0x180004ac0`
- `0x180004ec0`

## callees

- `0x18000f548`
- `0x1800119f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0jq_EventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-48h] BYREF
  __int64 v6; // [rsp+40h] [rbp-38h]
  __int64 v7; // [rsp+48h] [rbp-30h]
  int *v8; // [rsp+50h] [rbp-28h]
  __int64 v9; // [rsp+58h] [rbp-20h]
  int v10; // [rsp+98h] [rbp+20h] BYREF

  v10 = a4;
  v6 = a3;
  v8 = &v10;
  v7 = 16;
  v9 = 4;
  return McGenEventWrite_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)BeginApi, a3, 3u, &v5);
}

```

## disassembly

```asm
0x18000f5a0  mov     r11, rsp
0x18000f5a3  mov     [r11+20h], r9d
0x18000f5a7  sub     rsp, 78h
0x18000f5ab  mov     rax, cs:__security_cookie
0x18000f5b2  xor     rax, rsp
0x18000f5b5  mov     [rsp+78h+var_18], rax
0x18000f5ba  lea     rax, [r11+20h]
0x18000f5be  mov     [r11-38h], r8
0x18000f5c2  mov     [r11-28h], rax
0x18000f5c6  lea     rdx, BeginApi
0x18000f5cd  lea     rax, [r11-48h]
0x18000f5d1  mov     qword ptr [r11-30h], 10h
0x18000f5d9  mov     r9d, 3
0x18000f5df  mov     [r11-58h], rax
0x18000f5e3  mov     qword ptr [r11-20h], 4
0x18000f5eb  call    McGenEventWrite_EventWriteTransfer
0x18000f5f0  mov     rcx, [rsp+78h+var_18]
0x18000f5f5  xor     rcx, rsp; StackCookie
0x18000f5f8  call    __security_check_cookie
0x18000f5fd  add     rsp, 78h
0x18000f601  retn
```
