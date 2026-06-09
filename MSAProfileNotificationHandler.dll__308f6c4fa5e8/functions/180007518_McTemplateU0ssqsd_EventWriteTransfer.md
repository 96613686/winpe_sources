# McTemplateU0ssqsd_EventWriteTransfer

- ea: `0x180007518`
- end: `0x1800075f9`
- name: `McTemplateU0ssqsd_EventWriteTransfer`
- size: `225`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const char *, __int64, char, const char *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007360`

## callees

- `0x180001cb0`
- `0x180006f28`
- `0x180007518`

## string_xrefs

- `0x180007564`: `CProfileNotifyHandler::OnDelete`

## pseudocode

```c
ULONG __fastcall McTemplateU0ssqsd_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const char *a3,
        __int64 a4,
        char a5,
        const char *a6,
        char a7)
{
  __int64 v7; // rax
  int v9; // edx
  __int64 v10; // rcx
  int v11; // ecx
  const char *v12; // rcx
  bool v13; // zf
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-31h] BYREF
  const char *v16; // [rsp+40h] [rbp-21h]
  int v17; // [rsp+48h] [rbp-19h]
  int v18; // [rsp+4Ch] [rbp-15h]
  const char *v19; // [rsp+50h] [rbp-11h]
  __int64 v20; // [rsp+58h] [rbp-9h]
  char *v21; // [rsp+60h] [rbp-1h]
  __int64 v22; // [rsp+68h] [rbp+7h]
  const char *v23; // [rsp+70h] [rbp+Fh]
  int v24; // [rsp+78h] [rbp+17h]
  int v25; // [rsp+7Ch] [rbp+1Bh]
  char *v26; // [rsp+80h] [rbp+1Fh]
  __int64 v27; // [rsp+88h] [rbp+27h]

  v7 = -1;
  v9 = 5;
  if ( a3 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
    v11 = v10 + 1;
  }
  else
  {
    v11 = 5;
  }
  v17 = v11;
  v18 = 0;
  v19 = "CProfileNotifyHandler::OnDelete";
  v20 = 32;
  if ( !a3 )
    a3 = "NULL";
  v21 = &a5;
  v12 = a6;
  v16 = a3;
  v22 = 4;
  v13 = a6 == 0;
  if ( a6 )
  {
    do
      ++v7;
    while ( a6[v7] );
    v9 = v7 + 1;
    v13 = a6 == 0;
  }
  v24 = v9;
  v26 = &a7;
  if ( v13 )
    v12 = "NULL";
  v25 = 0;
  v23 = v12;
  v27 = 4;
  return McGenEventWrite_EventWriteTransfer((__int64)v12, a2, (__int64)a3, 6u, &v15);
}

```

## disassembly

```asm
0x180007518  push    rbp
0x18000751a  lea     rbp, [rsp-3Fh]
0x18000751f  sub     rsp, 0A0h
0x180007526  mov     rax, cs:__security_cookie
0x18000752d  xor     rax, rsp
0x180007530  mov     [rbp+3Fh+var_10], rax
0x180007534  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007538  xor     r9d, r9d
0x18000753b  mov     r10, rdx
0x18000753e  mov     edx, 5
0x180007543  test    r8, r8
0x180007546  jz      short loc_180007558
0x180007548  mov     rcx, rax
0x18000754b  inc     rcx
0x18000754e  cmp     [r8+rcx], r9b
0x180007552  jnz     short loc_18000754B
0x180007554  inc     ecx
0x180007556  jmp     short loc_18000755A
0x180007558  mov     ecx, edx
0x18000755a  mov     [rbp+3Fh+var_58], ecx
0x18000755d  lea     r11, aNull; "NULL"
0x180007564  lea     rcx, aCprofilenotify; "CProfileNotifyHandler::OnDelete"
0x18000756b  mov     [rbp+3Fh+var_54], r9d
0x18000756f  mov     [rbp+3Fh+var_50], rcx
0x180007573  test    r8, r8
0x180007576  lea     rcx, [rbp+3Fh+arg_20]
0x18000757a  mov     [rbp+3Fh+var_48], 20h ; ' '
0x180007582  cmovz   r8, r11
0x180007586  mov     [rbp+3Fh+var_40], rcx
0x18000758a  mov     rcx, [rbp+3Fh+arg_28]
0x18000758e  mov     [rbp+3Fh+var_60], r8
0x180007592  mov     [rbp+3Fh+var_38], 4
0x18000759a  test    rcx, rcx
0x18000759d  jz      short loc_1800075AE
0x18000759f  inc     rax
0x1800075a2  cmp     [rcx+rax], r9b
0x1800075a6  jnz     short loc_18000759F
0x1800075a8  lea     edx, [rax+1]
0x1800075ab  test    rcx, rcx
0x1800075ae  lea     rax, [rbp+3Fh+arg_30]
0x1800075b2  mov     [rbp+3Fh+var_28], edx
0x1800075b5  mov     [rbp+3Fh+var_20], rax
0x1800075b9  cmovz   rcx, r11
0x1800075bd  lea     rax, [rbp+3Fh+var_70]
0x1800075c1  mov     [rbp+3Fh+var_24], r9d
0x1800075c5  mov     r9d, 6
0x1800075cb  mov     [rsp+0A0h+var_80], rax
0x1800075d0  mov     rdx, r10
0x1800075d3  mov     [rbp+3Fh+var_30], rcx
0x1800075d7  mov     [rbp+3Fh+var_18], 4
0x1800075df  call    McGenEventWrite_EventWriteTransfer
0x1800075e4  mov     rcx, [rbp+3Fh+var_10]
0x1800075e8  xor     rcx, rsp; StackCookie
0x1800075eb  call    __security_check_cookie
0x1800075f0  add     rsp, 0A0h
0x1800075f7  pop     rbp
0x1800075f8  retn
```
