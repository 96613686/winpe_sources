# TaskSchedulerFreeScheduleWithFunc(_TASK_SCHEDULE *,void (*)(void *))

- ea: `0x180020900`
- end: `0x1800209f1`
- name: `?TaskSchedulerFreeScheduleWithFunc@@YAXPEAU_TASK_SCHEDULE@@P6AXPEAX@Z@Z`
- size: `241`
- prototype: `void __fastcall(void **, void (*)(void *))`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180020a2c`

## callees

- `0x18000eea0`
- `0x180020724`
- `0x180020900`

## pseudocode

```c
void __fastcall TaskSchedulerFreeScheduleWithFunc(void **a1, void (*a2)(void *))
{
  void *v3; // rcx
  __int64 v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rdi
  void *v8; // rcx
  void *v9; // rcx
  void **v10; // rax

  MIDL_user_free(a1[2]);
  MIDL_user_free(*a1);
  v3 = a1[9];
  if ( v3 )
  {
    if ( *(_DWORD *)v3 )
    {
      if ( *(_DWORD *)v3 == 1 )
      {
        v7 = *((_QWORD *)v3 + 1);
        if ( v7 )
        {
          if ( *(_QWORD *)v7 )
            MIDL_user_free(*(void **)v7);
          v8 = *(void **)(v7 + 16);
          if ( v8 )
            MIDL_user_free(v8);
          v9 = (void *)v7;
          goto LABEL_24;
        }
      }
      else
      {
        if ( *(_DWORD *)v3 != 2 )
        {
          if ( (unsigned int)(*(_DWORD *)v3 - 3) > 1 )
            goto LABEL_25;
          v4 = *((_QWORD *)v3 + 1);
          if ( !v4 )
            goto LABEL_25;
          v5 = *(void **)(v4 + 16);
          goto LABEL_21;
        }
        v6 = *((_QWORD *)v3 + 1);
        if ( v6 )
        {
LABEL_20:
          v5 = *(void **)(v6 + 8);
LABEL_21:
          if ( v5 )
            MIDL_user_free(v5);
          v9 = (void *)*((_QWORD *)a1[9] + 1);
LABEL_24:
          MIDL_user_free(v9);
        }
      }
    }
    else
    {
      v10 = (void **)*((_QWORD *)v3 + 1);
      if ( v10 )
      {
        if ( *v10 )
          MIDL_user_free(*v10);
        v6 = *((_QWORD *)a1[9] + 1);
        goto LABEL_20;
      }
    }
LABEL_25:
    MIDL_user_free(a1[9]);
  }
  TaskScheduleFreeTrigger(a1[8], 1, MIDL_user_free);
  MIDL_user_free(a1);
}

```

## disassembly

```asm
0x180020900  mov     [rsp+arg_0], rbx
0x180020905  push    rdi
0x180020906  sub     rsp, 20h
0x18002090a  mov     rbx, rcx
0x18002090d  mov     rcx, [rcx+10h]; void *
0x180020911  call    MIDL_user_free
0x180020916  mov     rcx, [rbx]; void *
0x180020919  call    MIDL_user_free
0x18002091e  mov     rcx, [rbx+48h]
0x180020922  test    rcx, rcx
0x180020925  jz      loc_1800209CA
0x18002092b  mov     edx, [rcx]
0x18002092d  test    edx, edx
0x18002092f  jz      short loc_180020988
0x180020931  sub     edx, 1
0x180020934  jz      short loc_18002095F
0x180020936  sub     edx, 1
0x180020939  jz      short loc_180020954
0x18002093b  sub     edx, 1
0x18002093e  jz      short loc_180020945
0x180020940  cmp     edx, 1
0x180020943  jnz     short loc_1800209C1
0x180020945  mov     rcx, [rcx+8]
0x180020949  test    rcx, rcx
0x18002094c  jz      short loc_1800209C1
0x18002094e  mov     rcx, [rcx+10h]
0x180020952  jmp     short loc_1800209AA
0x180020954  mov     rcx, [rcx+8]
0x180020958  test    rcx, rcx
0x18002095b  jz      short loc_1800209C1
0x18002095d  jmp     short loc_1800209A6
0x18002095f  mov     rdi, [rcx+8]
0x180020963  test    rdi, rdi
0x180020966  jz      short loc_1800209C1
0x180020968  mov     rcx, [rdi]; void *
0x18002096b  test    rcx, rcx
0x18002096e  jz      short loc_180020975
0x180020970  call    MIDL_user_free
0x180020975  mov     rcx, [rdi+10h]; void *
0x180020979  test    rcx, rcx
0x18002097c  jz      short loc_180020983
0x18002097e  call    MIDL_user_free
0x180020983  mov     rcx, rdi
0x180020986  jmp     short loc_1800209BC
0x180020988  mov     rax, [rcx+8]
0x18002098c  test    rax, rax
0x18002098f  jz      short loc_1800209C1
0x180020991  mov     rcx, [rax]; void *
0x180020994  test    rcx, rcx
0x180020997  jz      short loc_18002099E
0x180020999  call    MIDL_user_free
0x18002099e  mov     rax, [rbx+48h]
0x1800209a2  mov     rcx, [rax+8]
0x1800209a6  mov     rcx, [rcx+8]; void *
0x1800209aa  test    rcx, rcx
0x1800209ad  jz      short loc_1800209B4
0x1800209af  call    MIDL_user_free
0x1800209b4  mov     rcx, [rbx+48h]
0x1800209b8  mov     rcx, [rcx+8]; void *
0x1800209bc  call    MIDL_user_free
0x1800209c1  mov     rcx, [rbx+48h]; void *
0x1800209c5  call    MIDL_user_free
0x1800209ca  mov     rcx, [rbx+40h]
0x1800209ce  lea     r8, MIDL_user_free
0x1800209d5  mov     edx, 1
0x1800209da  call    TaskScheduleFreeTrigger
0x1800209df  mov     rcx, rbx; void *
0x1800209e2  mov     rbx, [rsp+28h+arg_0]
0x1800209e7  add     rsp, 20h
0x1800209eb  pop     rdi
0x1800209ec  jmp     MIDL_user_free
```
