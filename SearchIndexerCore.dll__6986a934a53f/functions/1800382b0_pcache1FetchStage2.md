# pcache1FetchStage2

- ea: `0x1800382b0`
- end: `0x1800386c6`
- name: `pcache1FetchStage2`
- size: `1046`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180038240`

## callees

- `0x180024640`
- `0x1800382b0`
- `0x1800386cc`
- `0x180038780`
- `0x180038a0c`
- `0x180038d00`
- `0x180046f80`
- `0x18004c3a8`
- `0x180056bf0`
- `0x1800b0010`

## pseudocode

```c
__int64 __fastcall pcache1FetchStage2(__int64 *a1, unsigned int a2, __int64 a3)
{
  __int64 v3; // rsi
  __int64 v5; // rdx
  __int64 v7; // rcx
  int v8; // r15d
  __int64 v9; // r9
  unsigned int v10; // r10d
  __int64 v11; // r14
  __int64 v12; // r13
  __int64 v13; // rsi
  int v14; // eax
  __int64 v15; // r14
  __int64 v16; // r9
  __int64 *v17; // rdx
  __int64 i; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned int v21; // edx
  __int64 v22; // rdx
  _QWORD *v23; // rax
  unsigned int v25; // r11d
  int v26; // eax
  bool v27; // sf
  bool v28; // of
  __int64 v29; // [rsp+50h] [rbp+8h] BYREF

  v3 = *a1;
  v5 = *((unsigned int *)a1 + 14);
  v7 = (unsigned int)dword_1800D121C;
  v8 = a3;
  v9 = (unsigned int)dword_1800D11F0;
  v10 = DWORD2(xmmword_1800D0D88);
  if ( (_DWORD)a3 != 1 )
    goto LABEL_2;
  v25 = *((_DWORD *)a1 + 13);
  a3 = (unsigned int)v5 - v25;
  if ( (unsigned int)a3 < *(_DWORD *)(v3 + 16) && (unsigned int)a3 < *((_DWORD *)a1 + 10) )
  {
    if ( !dword_1800D11F0 || (v26 = dword_1800D121C, *((_DWORD *)a1 + 4) + *((_DWORD *)a1 + 5) > dword_1800D11EC) )
      v26 = DWORD2(xmmword_1800D0D88);
    if ( !v26 || v25 >= (unsigned int)a3 )
    {
LABEL_2:
      if ( (unsigned int)v5 >= *((_DWORD *)a1 + 15) )
      {
        pcache1ResizeHash(a1, v5, a3, (unsigned int)dword_1800D11F0);
        v7 = (unsigned int)dword_1800D121C;
        v9 = (unsigned int)dword_1800D11F0;
        v10 = DWORD2(xmmword_1800D0D88);
      }
      if ( *((_DWORD *)a1 + 7) )
      {
        a3 = *(_QWORD *)(v3 + 72);
        if ( !*(_WORD *)(a3 + 22) )
        {
          if ( (unsigned int)(*((_DWORD *)a1 + 14) + 1) >= *((_DWORD *)a1 + 9) )
            goto LABEL_35;
          if ( !(_DWORD)v9 || *((_DWORD *)a1 + 4) + *((_DWORD *)a1 + 5) > dword_1800D11EC )
            v7 = v10;
          if ( (_DWORD)v7 )
          {
LABEL_35:
            v16 = *(_QWORD *)(a3 + 32);
            v17 = (__int64 *)(*(_QWORD *)(v16 + 64) + 8LL * (unsigned int)(*(_DWORD *)(a3 + 16) % *(_DWORD *)(v16 + 60)));
            for ( i = *v17; i != a3; i = *(_QWORD *)(i + 24) )
              v17 = (__int64 *)(i + 24);
            *v17 = *(_QWORD *)(i + 24);
            --*(_DWORD *)(v16 + 56);
            *(_QWORD *)(*(_QWORD *)(a3 + 48) + 40LL) = *(_QWORD *)(a3 + 40);
            *(_QWORD *)(*(_QWORD *)(a3 + 40) + 48LL) = *(_QWORD *)(a3 + 48);
            v19 = *(_QWORD *)(a3 + 32);
            *(_QWORD *)(a3 + 40) = 0;
            --*(_DWORD *)(v19 + 52);
            v20 = *(_QWORD *)(a3 + 32);
            if ( *(_DWORD *)(v20 + 24) == *((_DWORD *)a1 + 6) )
            {
              *(_DWORD *)(v3 + 20) += *((_DWORD *)a1 + 7) - *(_DWORD *)(v20 + 28);
              goto LABEL_38;
            }
            pcache1FreePage(a3);
          }
        }
      }
      if ( a1[9] || !*((_DWORD *)a1 + 14) && (unsigned int)pcache1InitBulk(a1, v5, a3, v9) )
      {
        a3 = a1[9];
        a1[9] = *(_QWORD *)(a3 + 24);
        *(_QWORD *)(a3 + 24) = 0;
LABEL_33:
        ++*(_DWORD *)a1[1];
        if ( !a3 )
          return a3;
LABEL_38:
        ++*((_DWORD *)a1 + 14);
        v21 = a2 % *((_DWORD *)a1 + 15);
        *(_DWORD *)(a3 + 16) = a2;
        v22 = 8LL * v21;
        v23 = *(_QWORD **)(a3 + 8);
        *(_QWORD *)(a3 + 24) = *(_QWORD *)(v22 + a1[8]);
        *(_QWORD *)(a3 + 32) = a1;
        *(_QWORD *)(a3 + 40) = 0;
        *v23 = 0;
        *(_QWORD *)(v22 + a1[8]) = a3;
        if ( a2 > *((_DWORD *)a1 + 11) )
          *((_DWORD *)a1 + 11) = a2;
        return a3;
      }
      if ( v8 == 1 && qword_1800D0DA0 )
        qword_1800D0DA0(v7, v5, a3, v9);
      v11 = *((int *)a1 + 6);
      if ( (int)v11 <= dword_1800D11EC )
      {
        sqlite3_mutex_enter(qword_1800D1208);
        v13 = qword_1800D1210;
        if ( qword_1800D1210 )
        {
          qword_1800D1210 = *(_QWORD *)qword_1800D1210;
          v28 = __OFSUB__(dword_1800D1218 - 1, dword_1800D11F4);
          v27 = --dword_1800D1218 - dword_1800D11F4 < 0;
          dword_1800D121C = v27 ^ v28;
          sqlite3StatusHighwater(7, (unsigned int)v11);
          sqlite3StatusUp(1);
          sqlite3_mutex_leave(qword_1800D1208);
LABEL_28:
          if ( v8 == 1 && qword_1800D0DA8 )
            qword_1800D0DA8(v7, v5, a3, v9);
          if ( !v13 )
            return 0;
          a3 = v13 + *((int *)a1 + 4);
          *(_QWORD *)a3 = v13;
          *(_QWORD *)(a3 + 8) = a3 + 56;
          *(_DWORD *)(a3 + 20) = 0;
          *(_QWORD *)(a3 + 48) = 0;
          goto LABEL_33;
        }
        sqlite3_mutex_leave(qword_1800D1208);
      }
      v29 = 0;
      v12 = v11;
      v13 = 0;
      if ( (unsigned __int64)(v11 - 1) <= 0x7FFFFEFE )
      {
        if ( dword_1800D0870 )
        {
          sqlite3_mutex_enter(xmmword_1800D0D78);
          mallocWithAlarm((unsigned int)v11, &v29);
          sqlite3_mutex_leave(xmmword_1800D0D78);
          v13 = v29;
        }
        else
        {
          v13 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, __int64))qword_1800D0890)(
                  (unsigned int)v11,
                  v5,
                  a3,
                  v9);
        }
      }
      if ( v13 )
      {
        v14 = ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))xmmword_1800D08A8)(v13, v5, a3, v9);
        v7 = qword_1800D1208;
        v15 = v14;
        if ( qword_1800D1208 )
        {
          ((void (*)(void))xmmword_1800D08F0)();
          v7 = qword_1800D1208;
        }
        if ( v12 > qword_1800D0E78 )
          qword_1800D0E78 = v12;
        v5 = v15 + qword_1800D0E00;
        qword_1800D0E00 += v15;
        if ( qword_1800D0E00 > qword_1800D0E50 )
          qword_1800D0E50 = v5;
        if ( v7 )
          ((void (*)(void))xmmword_1800D0900)();
      }
      goto LABEL_28;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800382b0  push    rbx
0x1800382b2  push    rbp
0x1800382b3  push    rsi
0x1800382b4  push    r15
0x1800382b6  sub     rsp, 28h
0x1800382ba  mov     rsi, [rcx]
0x1800382bd  mov     ebp, edx
0x1800382bf  mov     edx, [rcx+38h]
0x1800382c2  mov     rbx, rcx
0x1800382c5  mov     ecx, cs:dword_1800D121C
0x1800382cb  mov     r15d, r8d
0x1800382ce  mov     r9d, cs:dword_1800D11F0
0x1800382d5  mov     r10d, dword ptr cs:xmmword_1800D0D88+8
0x1800382dc  cmp     r8d, 1
0x1800382e0  jz      loc_180038532
0x1800382e6  cmp     edx, [rbx+3Ch]
0x1800382e9  jnb     loc_1800385B1
0x1800382ef  cmp     dword ptr [rbx+1Ch], 0
0x1800382f3  mov     [rsp+48h+arg_8], rdi
0x1800382f8  jz      short loc_180038328
0x1800382fa  mov     r8, [rsi+48h]
0x1800382fe  cmp     word ptr [r8+16h], 0
0x180038304  jnz     short loc_180038328
0x180038306  mov     eax, [rbx+38h]
0x180038309  inc     eax
0x18003830b  cmp     eax, [rbx+24h]
0x18003830e  jnb     loc_180038474
0x180038314  test    r9d, r9d
0x180038317  jnz     loc_18003860D
0x18003831d  mov     ecx, r10d
0x180038320  test    ecx, ecx
0x180038322  jnz     loc_180038474
0x180038328  xor     edi, edi
0x18003832a  cmp     qword ptr [rbx+48h], 0
0x18003832f  jnz     loc_180038594
0x180038335  cmp     dword ptr [rbx+38h], 0
0x180038339  jz      loc_180038584
0x18003833f  mov     [rsp+48h+var_28], r14
0x180038344  cmp     r15d, 1
0x180038348  jnz     short loc_18003835B
0x18003834a  mov     rax, cs:qword_1800D0DA0
0x180038351  test    rax, rax
0x180038354  jz      short loc_18003835B
0x180038356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003835b  movsxd  r14, dword ptr [rbx+18h]
0x18003835f  cmp     r14d, cs:dword_1800D11EC
0x180038366  jle     loc_18003863D
0x18003836c  lea     rax, [r14-1]
0x180038370  mov     [rsp+48h+arg_10], r13
0x180038375  mov     [rsp+48h+arg_0], rdi
0x18003837a  mov     r13, r14
0x18003837d  mov     rsi, rdi
0x180038380  cmp     rax, 7FFFFEFEh
0x180038386  ja      short loc_1800383A7
0x180038388  cmp     cs:dword_1800D0870, 0
0x18003838f  jnz     loc_1800385DE
0x180038395  mov     rax, cs:qword_1800D0890
0x18003839c  mov     ecx, r14d
0x18003839f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383a4  mov     rsi, rax
0x1800383a7  test    rsi, rsi
0x1800383aa  jz      short loc_18003841C
0x1800383ac  mov     rax, qword ptr cs:xmmword_1800D08A8
0x1800383b3  mov     rcx, rsi
0x1800383b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383bb  mov     rcx, cs:qword_1800D1208
0x1800383c2  movsxd  r14, eax
0x1800383c5  test    rcx, rcx
0x1800383c8  jz      short loc_1800383DD
0x1800383ca  mov     rax, qword ptr cs:xmmword_1800D08F0
0x1800383d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383d6  mov     rcx, cs:qword_1800D1208
0x1800383dd  cmp     r13, cs:qword_1800D0E78
0x1800383e4  jg      loc_1800385D2
0x1800383ea  mov     rdx, cs:qword_1800D0E00
0x1800383f1  add     rdx, r14
0x1800383f4  cmp     rdx, cs:qword_1800D0E50
0x1800383fb  mov     cs:qword_1800D0E00, rdx
0x180038402  jle     short loc_18003840B
0x180038404  mov     cs:qword_1800D0E50, rdx
0x18003840b  test    rcx, rcx
0x18003840e  jz      short loc_18003841C
0x180038410  mov     rax, qword ptr cs:xmmword_1800D0900
0x180038417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003841c  mov     r13, [rsp+48h+arg_10]
0x180038421  mov     r14, [rsp+48h+var_28]
0x180038426  cmp     r15d, 1
0x18003842a  jnz     short loc_18003843D
0x18003842c  mov     rax, cs:qword_1800D0DA8
0x180038433  test    rax, rax
0x180038436  jz      short loc_18003843D
0x180038438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003843d  test    rsi, rsi
0x180038440  jz      loc_1800385A9
0x180038446  movsxd  r8, dword ptr [rbx+10h]
0x18003844a  add     r8, rsi
0x18003844d  lea     rax, [r8+38h]
0x180038451  mov     [r8], rsi
0x180038454  mov     [r8+8], rax
0x180038458  mov     dword ptr [r8+14h], 0
0x180038460  mov     [r8+30h], rdi
0x180038464  mov     rax, [rbx+8]
0x180038468  inc     dword ptr [rax]
0x18003846a  test    r8, r8
0x18003846d  jnz     short loc_1800384DF
0x18003846f  jmp     loc_180038520
0x180038474  mov     r9, [r8+20h]
0x180038478  xor     edx, edx
0x18003847a  mov     eax, [r8+10h]
0x18003847e  div     dword ptr [r9+3Ch]
0x180038482  mov     rax, [r9+40h]
0x180038486  lea     rdx, [rax+rdx*8]
0x18003848a  mov     rax, [rdx]
0x18003848d  cmp     rax, r8
0x180038490  jnz     loc_180038571
0x180038496  mov     rax, [rax+18h]
0x18003849a  xor     edi, edi
0x18003849c  mov     [rdx], rax
0x18003849f  dec     dword ptr [r9+38h]
0x1800384a3  mov     rax, [r8+28h]
0x1800384a7  mov     rdx, [r8+30h]
0x1800384ab  mov     [rdx+28h], rax
0x1800384af  mov     rdx, [r8+28h]
0x1800384b3  mov     rax, [r8+30h]
0x1800384b7  mov     [rdx+30h], rax
0x1800384bb  mov     rax, [r8+20h]
0x1800384bf  mov     [r8+28h], rdi
0x1800384c3  dec     dword ptr [rax+34h]
0x1800384c6  mov     rcx, [r8+20h]
0x1800384ca  mov     eax, [rbx+18h]
0x1800384cd  cmp     [rcx+18h], eax
0x1800384d0  jnz     loc_1800386B9
0x1800384d6  mov     eax, [rbx+1Ch]
0x1800384d9  sub     eax, [rcx+1Ch]
0x1800384dc  add     [rsi+14h], eax
0x1800384df  inc     dword ptr [rbx+38h]
0x1800384e2  xor     edx, edx
0x1800384e4  mov     eax, ebp
0x1800384e6  div     dword ptr [rbx+3Ch]
0x1800384e9  mov     [r8+10h], ebp
0x1800384ed  mov     rax, [rbx+40h]
0x1800384f1  lea     rdx, ds:0[rdx*8]
0x1800384f9  mov     rcx, [rdx+rax]
0x1800384fd  mov     rax, [r8+8]
0x180038501  mov     [r8+18h], rcx
0x180038505  mov     [r8+20h], rbx
0x180038509  mov     [r8+28h], rdi
0x18003850d  mov     [rax], rdi
0x180038510  mov     rax, [rbx+40h]
0x180038514  mov     [rdx+rax], r8
0x180038518  cmp     ebp, [rbx+2Ch]
0x18003851b  jbe     short loc_180038520
0x18003851d  mov     [rbx+2Ch], ebp
0x180038520  mov     rdi, [rsp+48h+arg_8]
0x180038525  mov     rax, r8
0x180038528  add     rsp, 28h
0x18003852c  pop     r15
0x18003852e  pop     rsi
0x18003852f  pop     rbp
0x180038530  pop     rbx
0x180038531  retn
0x180038532  mov     r11d, [rbx+34h]
0x180038536  mov     r8d, edx
0x180038539  sub     r8d, r11d
0x18003853c  cmp     r8d, [rsi+10h]
0x180038540  jnb     short loc_180038565
0x180038542  cmp     r8d, [rbx+28h]
0x180038546  jnb     short loc_180038565
0x180038548  test    r9d, r9d
0x18003854b  jnz     loc_180038624
0x180038551  mov     eax, r10d
0x180038554  test    eax, eax
0x180038556  jz      loc_1800382E6
0x18003855c  cmp     r11d, r8d
0x18003855f  jnb     loc_1800382E6
0x180038565  xor     eax, eax
0x180038567  add     rsp, 28h
0x18003856b  pop     r15
0x18003856d  pop     rsi
0x18003856e  pop     rbp
0x18003856f  pop     rbx
0x180038570  retn
0x180038571  lea     rdx, [rax+18h]
0x180038575  mov     rax, [rax+18h]
0x180038579  cmp     rax, r8
0x18003857c  jz      loc_180038496
0x180038582  jmp     short loc_180038571
0x180038584  mov     rcx, rbx
0x180038587  call    pcache1InitBulk
0x18003858c  test    eax, eax
0x18003858e  jz      loc_18003833F
0x180038594  mov     r8, [rbx+48h]
0x180038598  mov     rax, [r8+18h]
0x18003859c  mov     [rbx+48h], rax
0x1800385a0  mov     [r8+18h], rdi
0x1800385a4  jmp     loc_180038464
0x1800385a9  mov     r8, rdi
0x1800385ac  jmp     loc_180038520
0x1800385b1  mov     rcx, rbx
0x1800385b4  call    pcache1ResizeHash
0x1800385b9  mov     ecx, cs:dword_1800D121C
0x1800385bf  mov     r9d, cs:dword_1800D11F0
0x1800385c6  mov     r10d, dword ptr cs:xmmword_1800D0D88+8
0x1800385cd  jmp     loc_1800382EF
0x1800385d2  mov     cs:qword_1800D0E78, r13
0x1800385d9  jmp     loc_1800383EA
0x1800385de  mov     rcx, qword ptr cs:xmmword_1800D0D78
0x1800385e5  call    sqlite3_mutex_enter
0x1800385ea  lea     rdx, [rsp+48h+arg_0]
0x1800385ef  mov     ecx, r14d
0x1800385f2  call    mallocWithAlarm
0x1800385f7  mov     rcx, qword ptr cs:xmmword_1800D0D78
0x1800385fe  call    sqlite3_mutex_leave
0x180038603  mov     rsi, [rsp+48h+arg_0]
0x180038608  jmp     loc_1800383A7
0x18003860d  mov     eax, [rbx+14h]
0x180038610  add     eax, [rbx+10h]
0x180038613  cmp     eax, cs:dword_1800D11EC
0x180038619  jle     loc_180038320
0x18003861f  jmp     loc_18003831D
0x180038624  mov     eax, [rbx+14h]
0x180038627  add     eax, [rbx+10h]
0x18003862a  cmp     eax, cs:dword_1800D11EC
0x180038630  mov     eax, ecx
0x180038632  jle     loc_180038554
0x180038638  jmp     loc_180038551
0x18003863d  mov     rcx, cs:qword_1800D1208
0x180038644  call    sqlite3_mutex_enter
0x180038649  mov     rsi, cs:qword_1800D1210
0x180038650  test    rsi, rsi
0x180038653  jnz     short loc_180038666
0x180038655  mov     rcx, cs:qword_1800D1208
0x18003865c  call    sqlite3_mutex_leave
0x180038661  jmp     loc_18003836C
0x180038666  mov     rax, [rsi]
0x180038669  mov     edx, r14d
0x18003866c  mov     ecx, cs:dword_1800D1218
0x180038672  dec     ecx
0x180038674  mov     cs:qword_1800D1210, rax
0x18003867b  cmp     ecx, cs:dword_1800D11F4
0x180038681  mov     eax, edi
0x180038683  mov     cs:dword_1800D1218, ecx
0x180038689  mov     ecx, 7
0x18003868e  setl    al
0x180038691  mov     cs:dword_1800D121C, eax
0x180038697  call    sqlite3StatusHighwater
0x18003869c  mov     edx, 1
0x1800386a1  mov     ecx, edx
0x1800386a3  call    sqlite3StatusUp
0x1800386a8  mov     rcx, cs:qword_1800D1208
0x1800386af  call    sqlite3_mutex_leave
0x1800386b4  jmp     loc_180038421
0x1800386b9  mov     rcx, r8
0x1800386bc  call    pcache1FreePage
0x1800386c1  jmp     loc_18003832A
```
