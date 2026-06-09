# BCryptIumContextManagerCreateContext

- ea: `0x140007fac`
- end: `0x140008256`
- name: `BCryptIumContextManagerCreateContext`
- size: `682`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140010490`

## callees

- `0x140007fac`
- `0x14000825c`
- `0x140008f8c`
- `0x14001193c`
- `0x140011964`
- `0x140011cf4`
- `0x14003a010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x14000800a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x14000800a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008037`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008127`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008127`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008211`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008211`

## pseudocode

```c
__int64 __fastcall BCryptIumContextManagerCreateContext(_QWORD *a1)
{
  _QWORD *v2; // rax
  __int64 v3; // rdi
  unsigned int v4; // ebx
  PVOID *v5; // rcx
  DWORD LastError; // eax
  int v7; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  struct BCRYPTIUM_CONTEXT *i; // rax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 *v14; // rax
  __int64 v15; // [rsp+40h] [rbp+8h] BYREF

  *a1 = 0;
  v15 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids);
  v2 = LocalAlloc(0x40u, 0x58u);
  v3 = (__int64)v2;
  if ( v2 )
  {
    v2[1] = v2;
    *v2 = v2;
    *((_DWORD *)v2 + 20) = 10;
    *((_DWORD *)v2 + 16) = 1023;
    *((_DWORD *)v2 + 17) = 1;
    v7 = BCryptIumRpcHandleInit((struct BCRYPTIUM_CONTEXT *)v2);
    v4 = v7;
    if ( v7 >= 0 )
    {
      v7 = ((__int64 (__fastcall *)(__int64 *))xmmword_140052DF8)(&v15);
      v4 = v7;
      if ( v7 >= 0 )
      {
        AcquireSRWLockExclusive(&SRWLock);
        for ( i = qword_140052C28; ; i = *(struct BCRYPTIUM_CONTEXT **)i )
        {
          if ( i == (struct BCRYPTIUM_CONTEXT *)&qword_140052C28 )
          {
            if ( (unsigned int)dword_140052C38 < 2 )
            {
              *(_QWORD *)(v3 + 16) = v15;
              v14 = (__int64 *)qword_140052C30;
              if ( *(struct BCRYPTIUM_CONTEXT ***)qword_140052C30 != &qword_140052C28 )
                __fastfail(3u);
              *(_QWORD *)v3 = &qword_140052C28;
              *(_QWORD *)(v3 + 8) = v14;
              *v14 = v3;
              qword_140052C30 = v3;
              ++dword_140052C38;
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                goto LABEL_40;
              v13 = 73;
            }
            else
            {
              v4 = -1073741823;
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_40;
              v13 = 72;
            }
            WPP_SF_L(v12[2], v13);
            goto LABEL_40;
          }
          if ( *((_QWORD *)i + 2) == v15 )
            break;
        }
        v4 = -1073741823;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            71,
            &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids,
            3221225473LL);
LABEL_40:
        ReleaseSRWLockExclusive(&SRWLock);
        if ( (v4 & 0x80000000) == 0 )
        {
          *a1 = *(_QWORD *)(v3 + 16);
          v5 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            return v4;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_15;
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids);
          goto LABEL_14;
        }
        goto LABEL_13;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_13:
        BCryptIumContextManagerFreeContext((struct BCRYPTIUM_CONTEXT *)v3);
        goto LABEL_14;
      }
      v9 = 69;
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      v9 = 68;
    }
    WPP_SF_d(v8[2], v9, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids, (unsigned int)v7);
    goto LABEL_13;
  }
  v4 = -1073741801;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids, LastError);
LABEL_14:
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_15:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 )
    WPP_SF_d(v5[2], 76, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x140007fac  mov     [rsp+arg_8], rbx
0x140007fb1  mov     [rsp+arg_10], rbp
0x140007fb6  push    rsi
0x140007fb7  push    rdi
0x140007fb8  push    r14
0x140007fba  sub     rsp, 20h
0x140007fbe  mov     rsi, rcx
0x140007fc1  mov     qword ptr [rcx], 0
0x140007fc8  mov     [rsp+38h+arg_0], 0
0x140007fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x140007fd8  lea     rbp, WPP_GLOBAL_Control
0x140007fdf  lea     r14, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x140007fe6  cmp     rcx, rbp
0x140007fe9  jz      short loc_140008002
0x140007feb  test    byte ptr [rcx+1Ch], 4
0x140007fef  jz      short loc_140008002
0x140007ff1  mov     rcx, [rcx+10h]
0x140007ff5  mov     edx, 42h ; 'B'
0x140007ffa  mov     r8, r14
0x140007ffd  call    WPP_SF_
0x140008002  mov     edx, 58h ; 'X'; uBytes
0x140008007  lea     ecx, [rdx-18h]; uFlags
0x14000800a  call    cs:__imp_LocalAlloc
0x140008010  mov     rdi, rax
0x140008013  test    rax, rax
0x140008016  jnz     short loc_140008058
0x140008018  mov     ebx, 0C0000017h
0x14000801d  mov     rcx, cs:WPP_GLOBAL_Control
0x140008024  cmp     rcx, rbp
0x140008027  jz      loc_1400080D8
0x14000802d  test    byte ptr [rcx+1Ch], 1
0x140008031  jz      loc_1400080B9
0x140008037  call    cs:__imp_GetLastError
0x14000803d  mov     rcx, cs:WPP_GLOBAL_Control
0x140008044  lea     edx, [rdi+43h]
0x140008047  mov     r9d, eax
0x14000804a  mov     r8, r14
0x14000804d  mov     rcx, [rcx+10h]
0x140008051  call    WPP_SF_d
0x140008056  jmp     short loc_1400080B2
0x140008058  mov     rcx, rdi; struct BCRYPTIUM_CONTEXT *
0x14000805b  mov     [rax+8], rdi
0x14000805f  mov     [rax], rdi
0x140008062  mov     dword ptr [rax+50h], 0Ah
0x140008069  mov     dword ptr [rax+40h], 3FFh
0x140008070  mov     dword ptr [rax+44h], 1
0x140008077  call    ?BCryptIumRpcHandleInit@@YAJPEAUBCRYPTIUM_CONTEXT@@@Z; BCryptIumRpcHandleInit(BCRYPTIUM_CONTEXT *)
0x14000807c  mov     ebx, eax
0x14000807e  test    eax, eax
0x140008080  jns     short loc_1400080ED
0x140008082  mov     rcx, cs:WPP_GLOBAL_Control
0x140008089  cmp     rcx, rbp
0x14000808c  jz      short loc_1400080A8
0x14000808e  test    byte ptr [rcx+1Ch], 1
0x140008092  jz      short loc_1400080A8
0x140008094  mov     edx, 44h ; 'D'
0x140008099  mov     rcx, [rcx+10h]
0x14000809d  mov     r9d, eax
0x1400080a0  mov     r8, r14
0x1400080a3  call    WPP_SF_d
0x1400080a8  xor     edx, edx
0x1400080aa  mov     rcx, rdi; struct BCRYPTIUM_CONTEXT *
0x1400080ad  call    BCryptIumContextManagerFreeContext
0x1400080b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400080b9  cmp     rcx, rbp
0x1400080bc  jz      short loc_1400080D8
0x1400080be  test    byte ptr [rcx+1Ch], 4
0x1400080c2  jz      short loc_1400080D8
0x1400080c4  mov     rcx, [rcx+10h]
0x1400080c8  mov     edx, 4Ch ; 'L'
0x1400080cd  mov     r9d, ebx
0x1400080d0  mov     r8, r14
0x1400080d3  call    WPP_SF_d
0x1400080d8  mov     rbp, [rsp+38h+arg_10]
0x1400080dd  mov     eax, ebx
0x1400080df  mov     rbx, [rsp+38h+arg_8]
0x1400080e4  add     rsp, 20h
0x1400080e8  pop     r14
0x1400080ea  pop     rdi
0x1400080eb  pop     rsi
0x1400080ec  retn
0x1400080ed  mov     rax, qword ptr cs:xmmword_140052DF8
0x1400080f4  lea     rcx, [rsp+38h+arg_0]
0x1400080f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080fe  mov     ebx, eax
0x140008100  test    eax, eax
0x140008102  jns     short loc_140008120
0x140008104  mov     rcx, cs:WPP_GLOBAL_Control
0x14000810b  cmp     rcx, rbp
0x14000810e  jz      short loc_1400080A8
0x140008110  test    byte ptr [rcx+1Ch], 1
0x140008114  jz      short loc_1400080A8
0x140008116  mov     edx, 45h ; 'E'
0x14000811b  jmp     loc_140008099
0x140008120  lea     rcx, SRWLock; SRWLock
0x140008127  call    cs:__imp_AcquireSRWLockExclusive
0x14000812d  mov     rax, cs:qword_140052C28
0x140008134  lea     rdx, qword_140052C28
0x14000813b  mov     rcx, [rsp+38h+arg_0]
0x140008140  jmp     short loc_14000814B
0x140008142  cmp     [rax+10h], rcx
0x140008146  jz      short loc_140008184
0x140008148  mov     rax, [rax]
0x14000814b  cmp     rax, rdx
0x14000814e  jnz     short loc_140008142
0x140008150  mov     r9d, 2
0x140008156  cmp     cs:dword_140052C38, r9d
0x14000815d  jb      short loc_1400081B1
0x14000815f  mov     ebx, 0C0000001h
0x140008164  mov     rcx, cs:WPP_GLOBAL_Control
0x14000816b  cmp     rcx, rbp
0x14000816e  jz      loc_14000820A
0x140008174  test    byte ptr [rcx+1Ch], 1
0x140008178  jz      loc_14000820A
0x14000817e  lea     edx, [r9+46h]
0x140008182  jmp     short loc_140008201
0x140008184  mov     ebx, 0C0000001h
0x140008189  mov     rcx, cs:WPP_GLOBAL_Control
0x140008190  cmp     rcx, rbp
0x140008193  jz      short loc_14000820A
0x140008195  test    byte ptr [rcx+1Ch], 1
0x140008199  jz      short loc_14000820A
0x14000819b  mov     rcx, [rcx+10h]
0x14000819f  mov     edx, 47h ; 'G'
0x1400081a4  mov     r9d, ebx
0x1400081a7  mov     r8, r14
0x1400081aa  call    WPP_SF_d
0x1400081af  jmp     short loc_14000820A
0x1400081b1  mov     [rdi+10h], rcx
0x1400081b5  mov     rax, cs:qword_140052C30
0x1400081bc  cmp     [rax], rdx
0x1400081bf  jz      short loc_1400081C8
0x1400081c1  mov     ecx, 3
0x1400081c6  int     29h; Win8: RtlFailFast(ecx)
0x1400081c8  mov     [rdi], rdx
0x1400081cb  mov     [rdi+8], rax
0x1400081cf  mov     [rax], rdi
0x1400081d2  mov     r9d, cs:dword_140052C38
0x1400081d9  inc     r9d
0x1400081dc  mov     cs:qword_140052C30, rdi
0x1400081e3  mov     cs:dword_140052C38, r9d
0x1400081ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400081f1  cmp     rcx, rbp
0x1400081f4  jz      short loc_14000820A
0x1400081f6  test    byte ptr [rcx+1Ch], 4
0x1400081fa  jz      short loc_14000820A
0x1400081fc  mov     edx, 49h ; 'I'
0x140008201  mov     rcx, [rcx+10h]
0x140008205  call    WPP_SF_L
0x14000820a  lea     rcx, SRWLock; SRWLock
0x140008211  call    cs:__imp_ReleaseSRWLockExclusive
0x140008217  test    ebx, ebx
0x140008219  js      loc_1400080A8
0x14000821f  mov     rax, [rdi+10h]
0x140008223  mov     [rsi], rax
0x140008226  mov     rcx, cs:WPP_GLOBAL_Control
0x14000822d  cmp     rcx, rbp
0x140008230  jz      loc_1400080D8
0x140008236  test    byte ptr [rcx+1Ch], 4
0x14000823a  jz      loc_1400080B9
0x140008240  mov     rcx, [rcx+10h]
0x140008244  mov     edx, 4Bh ; 'K'
0x140008249  mov     r8, r14
0x14000824c  call    WPP_SF_
0x140008251  jmp     loc_1400080B2
```
