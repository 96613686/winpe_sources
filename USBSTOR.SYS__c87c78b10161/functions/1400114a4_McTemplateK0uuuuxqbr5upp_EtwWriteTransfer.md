# McTemplateK0uuuuxqbr5upp_EtwWriteTransfer

- ea: `0x1400114a4`
- end: `0x1400115a3`
- name: `McTemplateK0uuuuxqbr5upp_EtwWriteTransfer`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004910`

## callees

- `0x140011440`
- `0x140013950`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0uuuuxqbr5upp_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        const GUID *a3,
        __int64 a4,
        int a5,
        int a6,
        char a7,
        char a8,
        int a9,
        __int64 a10,
        char a11,
        char a12,
        char a13)
{
  char v14; // [rsp+30h] [rbp-D0h] BYREF
  char v15; // [rsp+38h] [rbp-C8h] BYREF
  char v16; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+50h] [rbp-B0h] BYREF
  char *v18; // [rsp+60h] [rbp-A0h]
  __int64 v19; // [rsp+68h] [rbp-98h]
  char *v20; // [rsp+70h] [rbp-90h]
  __int64 v21; // [rsp+78h] [rbp-88h]
  char *v22; // [rsp+80h] [rbp-80h]
  __int64 v23; // [rsp+88h] [rbp-78h]
  char *v24; // [rsp+90h] [rbp-70h]
  __int64 v25; // [rsp+98h] [rbp-68h]
  char *v26; // [rsp+A0h] [rbp-60h]
  __int64 v27; // [rsp+A8h] [rbp-58h]
  int *v28; // [rsp+B0h] [rbp-50h]
  __int64 v29; // [rsp+B8h] [rbp-48h]
  __int64 v30; // [rsp+C0h] [rbp-40h]
  int v31; // [rsp+C8h] [rbp-38h]
  int v32; // [rsp+CCh] [rbp-34h]
  char *v33; // [rsp+D0h] [rbp-30h]
  __int64 v34; // [rsp+D8h] [rbp-28h]
  char *v35; // [rsp+E0h] [rbp-20h]
  __int64 v36; // [rsp+E8h] [rbp-18h]
  char *v37; // [rsp+F0h] [rbp-10h]
  __int64 v38; // [rsp+F8h] [rbp-8h]

  v19 = 1;
  v16 = 0;
  v18 = &v14;
  v20 = &v15;
  v22 = &v16;
  v24 = &a7;
  v26 = &a8;
  v28 = &a9;
  v30 = a10;
  v31 = a9;
  v33 = &a11;
  v35 = &a12;
  v37 = &a13;
  v15 = 0;
  v14 = 0;
  v21 = 1;
  v23 = 1;
  v25 = 1;
  v27 = 8;
  v29 = 4;
  v32 = 0;
  v34 = 1;
  v36 = 8;
  v38 = 8;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 0, &v17);
}

```

## disassembly

```asm
0x1400114a4  push    rbp
0x1400114a6  lea     rbp, [rsp-10h]
0x1400114ab  sub     rsp, 110h
0x1400114b2  mov     rax, cs:__security_cookie
0x1400114b9  xor     rax, rsp
0x1400114bc  mov     [rbp+10h+var_10], rax
0x1400114c0  xor     r9d, r9d; int
0x1400114c3  mov     [rsp+110h+var_A8], 1
0x1400114cc  lea     rax, [rsp+110h+var_E0]
0x1400114d1  mov     [rsp+110h+var_D0], r9b
0x1400114d6  mov     [rsp+110h+var_B0], rax
0x1400114db  lea     rax, [rsp+110h+var_D8]
0x1400114e0  mov     [rsp+110h+var_A0], rax
0x1400114e5  lea     rax, [rsp+110h+var_D0]
0x1400114ea  mov     [rbp+10h+var_90], rax
0x1400114ee  lea     rax, [rbp+10h+arg_30]
0x1400114f2  mov     [rbp+10h+var_80], rax
0x1400114f6  lea     rax, [rbp+10h+arg_38]
0x1400114fa  mov     [rbp+10h+var_70], rax
0x1400114fe  lea     rax, [rbp+10h+arg_40]
0x140011502  mov     [rbp+10h+var_60], rax
0x140011506  mov     rax, [rbp+10h+arg_48]
0x14001150a  mov     [rbp+10h+var_50], rax
0x14001150e  mov     eax, [rbp+10h+arg_40]
0x140011511  mov     [rbp+10h+var_48], eax
0x140011514  lea     rax, [rbp+10h+arg_50]
0x140011518  mov     [rbp+10h+var_40], rax
0x14001151c  lea     rax, [rbp+10h+arg_58]
0x140011520  mov     [rbp+10h+var_30], rax
0x140011524  lea     rax, [rbp+10h+arg_60]
0x14001152b  mov     [rbp+10h+var_20], rax
0x14001152f  lea     rax, [rsp+110h+var_C0]
0x140011534  mov     [rsp+110h+var_F0], rax; PEVENT_DATA_DESCRIPTOR
0x140011539  mov     [rsp+110h+var_D8], r9b
0x14001153e  mov     [rsp+110h+var_E0], r9b
0x140011543  mov     [rsp+110h+var_98], 1
0x14001154c  mov     [rbp+10h+var_88], 1
0x140011554  mov     [rbp+10h+var_78], 1
0x14001155c  mov     [rbp+10h+var_68], 8
0x140011564  mov     [rbp+10h+var_58], 4
0x14001156c  mov     [rbp+10h+var_44], r9d
0x140011570  mov     [rbp+10h+var_38], 1
0x140011578  mov     [rbp+10h+var_28], 8
0x140011580  mov     [rbp+10h+var_18], 8
0x140011588  call    McGenEventWrite_EtwWriteTransfer
0x14001158d  mov     rcx, [rbp+10h+var_10]
0x140011591  xor     rcx, rsp; StackCookie
0x140011594  call    __security_check_cookie
0x140011599  add     rsp, 110h
0x1400115a0  pop     rbp
0x1400115a1  retn
```
