# TaskScheduleFreeTrigger

- ea: `0x180020724`
- end: `0x180020857`
- name: `TaskScheduleFreeTrigger`
- size: `307`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18002067c`
- `0x180020724`
- `0x180020900`

## callees

- `0x18002067c`
- `0x1800206e0`
- `0x180020724`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall TaskScheduleFreeTrigger(__int64 a1, int a2, __int64 (__fastcall *a3)(__int64))
{
  __int64 v6; // rsi
  __int64 v7; // rbp
  unsigned int i; // r14d
  __int64 v9; // rcx
  __int64 result; // rax

  if ( a1 )
  {
    if ( *(_DWORD *)a1 )
    {
      switch ( *(_DWORD *)a1 )
      {
        case 1:
          result = FreeWnfTrigger(*(_QWORD *)(a1 + 8), a3);
          goto LABEL_25;
        case 2:
          result = FreeAggregateTrigger(*(_QWORD *)(a1 + 8), a3);
          goto LABEL_25;
        case 3:
          v9 = *(_QWORD *)(a1 + 8);
          if ( !v9 )
            goto LABEL_25;
          goto LABEL_24;
        case 4:
          v6 = *(_QWORD *)(a1 + 8);
          if ( !v6 )
            goto LABEL_25;
          v7 = *(_QWORD *)(v6 + 16);
          if ( v7 )
          {
            for ( i = 0; i < *(_DWORD *)(v6 + 12); v7 += 16 )
            {
              TaskScheduleFreeTrigger(v7, 0, a3);
              ++i;
            }
            a3(*(_QWORD *)(v6 + 16));
          }
          if ( *(_QWORD *)v6 )
            TaskScheduleFreeTrigger(*(_QWORD *)v6, 0, a3);
          break;
        case 6:
          v6 = *(_QWORD *)(a1 + 8);
          if ( !v6 )
            goto LABEL_25;
          FreeAggregateTrigger(*(_QWORD *)(v6 + 16), a3);
          break;
        default:
          goto LABEL_25;
      }
    }
    else
    {
      v6 = *(_QWORD *)(a1 + 8);
      if ( !v6 )
        goto LABEL_25;
      FreeWnfTrigger(*(_QWORD *)(v6 + 16), a3);
    }
    v9 = v6;
LABEL_24:
    result = a3(v9);
LABEL_25:
    if ( a2 )
      return a3(a1);
  }
  return result;
}

```

## disassembly

```asm
0x180020724  test    rcx, rcx
0x180020727  jz      locret_180020856
0x18002072d  push    rbx
0x18002072e  push    rbp
0x18002072f  push    rsi
0x180020730  push    rdi
0x180020731  push    r14
0x180020733  push    r15
0x180020735  sub     rsp, 28h
0x180020739  mov     r9d, [rcx]
0x18002073c  mov     rdi, r8
0x18002073f  mov     r15d, edx
0x180020742  mov     rbx, rcx
0x180020745  test    r9d, r9d
0x180020748  jz      loc_18002081A
0x18002074e  sub     r9d, 1
0x180020752  jz      loc_18002080C
0x180020758  sub     r9d, 1
0x18002075c  jz      loc_1800207FE
0x180020762  sub     r9d, 1
0x180020766  jz      loc_1800207F3
0x18002076c  sub     r9d, 1
0x180020770  jz      short loc_18002079A
0x180020772  cmp     r9d, 2
0x180020776  jnz     loc_18002083A
0x18002077c  mov     rsi, [rcx+8]
0x180020780  test    rsi, rsi
0x180020783  jz      loc_18002083A
0x180020789  mov     rcx, [rsi+10h]
0x18002078d  mov     rdx, r8
0x180020790  call    FreeAggregateTrigger
0x180020795  jmp     loc_18002082F
0x18002079a  mov     rsi, [rcx+8]
0x18002079e  test    rsi, rsi
0x1800207a1  jz      loc_18002083A
0x1800207a7  mov     rbp, [rsi+10h]
0x1800207ab  test    rbp, rbp
0x1800207ae  jz      short loc_1800207DF
0x1800207b0  xor     r14d, r14d
0x1800207b3  cmp     [rsi+0Ch], r14d
0x1800207b7  jbe     short loc_1800207D3
0x1800207b9  mov     r8, rdi
0x1800207bc  xor     edx, edx
0x1800207be  mov     rcx, rbp
0x1800207c1  call    TaskScheduleFreeTrigger
0x1800207c6  inc     r14d
0x1800207c9  add     rbp, 10h
0x1800207cd  cmp     r14d, [rsi+0Ch]
0x1800207d1  jb      short loc_1800207B9
0x1800207d3  mov     rcx, [rsi+10h]
0x1800207d7  mov     rax, rdi
0x1800207da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207df  mov     rcx, [rsi]
0x1800207e2  test    rcx, rcx
0x1800207e5  jz      short loc_18002082F
0x1800207e7  mov     r8, rdi
0x1800207ea  xor     edx, edx
0x1800207ec  call    TaskScheduleFreeTrigger
0x1800207f1  jmp     short loc_18002082F
0x1800207f3  mov     rcx, [rcx+8]
0x1800207f7  test    rcx, rcx
0x1800207fa  jz      short loc_18002083A
0x1800207fc  jmp     short loc_180020832
0x1800207fe  mov     rcx, [rcx+8]
0x180020802  mov     rdx, rdi
0x180020805  call    FreeAggregateTrigger
0x18002080a  jmp     short loc_18002083A
0x18002080c  mov     rcx, [rcx+8]
0x180020810  mov     rdx, rdi
0x180020813  call    FreeWnfTrigger
0x180020818  jmp     short loc_18002083A
0x18002081a  mov     rsi, [rcx+8]
0x18002081e  test    rsi, rsi
0x180020821  jz      short loc_18002083A
0x180020823  mov     rcx, [rsi+10h]
0x180020827  mov     rdx, rdi
0x18002082a  call    FreeWnfTrigger
0x18002082f  mov     rcx, rsi
0x180020832  mov     rax, rdi
0x180020835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002083a  test    r15d, r15d
0x18002083d  jz      short loc_18002084A
0x18002083f  mov     rcx, rbx
0x180020842  mov     rax, rdi
0x180020845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002084a  add     rsp, 28h
0x18002084e  pop     r15
0x180020850  pop     r14
0x180020852  pop     rdi
0x180020853  pop     rsi
0x180020854  pop     rbp
0x180020855  pop     rbx
0x180020856  retn
```
