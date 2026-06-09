# CPimcTablet::GetCursorInfo(int,ushort * *,int *,int *)

- ea: `0x180009660`
- end: `0x180009820`
- name: `?GetCursorInfo@CPimcTablet@@UEAAJHPEAPEAGPEAH1@Z`
- size: `448`
- prototype: `__int64 __fastcall(CPimcTablet *__hidden this, int, unsigned __int16 **, int *, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180009660`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180009779`
- `ole32!CoTaskMemAlloc` at `0x180009779`

## pseudocode

```c
__int64 __fastcall CPimcTablet::GetCursorInfo(CPimcTablet *this, int a2, unsigned __int16 **a3, int *a4, int *a5)
{
  unsigned int v7; // r10d
  __int64 v8; // rdi
  _WORD *v9; // rax
  __int64 v10; // rdx
  unsigned __int64 v11; // r8
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rbx
  unsigned __int16 *v14; // rcx
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // r8
  __int64 v17; // rdx
  unsigned __int16 v18; // ax
  unsigned __int16 *v19; // rax

  v7 = (a2 >> 31) & 0x80070057;
  if ( a2 >> 31 != -1 )
  {
    v7 = (unsigned int)a2 >= *((_DWORD *)this + 13) ? 0x80070057 : 0;
    if ( (unsigned int)a2 < *((_DWORD *)this + 13) )
    {
      v7 = a3 == 0 ? 0x80070057 : 0;
      if ( a3 )
      {
        v7 = a4 == 0 ? 0x80070057 : 0;
        if ( a4 )
        {
          v7 = a5 == 0 ? 0x80070057 : 0;
          if ( a5 )
          {
            v8 = *(_QWORD *)(*((_QWORD *)this + 7) + 8LL * a2);
            v9 = *(_WORD **)v8;
            if ( *(_QWORD *)v8 )
            {
              v10 = 0x7FFFFFFF;
              do
              {
                if ( !*v9 )
                  break;
                ++v9;
                --v10;
              }
              while ( v10 );
              v7 = v10 == 0 ? 0x80070057 : 0;
              v11 = (0x7FFFFFFF - v10) & -(__int64)(v10 != 0);
              if ( v10 )
              {
                v12 = v11 + 1;
                if ( v11 + 1 >= v11 && (v13 = 2 * v12, is_mul_ok(v12, 2u)) )
                {
                  v14 = (unsigned __int16 *)CoTaskMemAlloc(2 * v12);
                  *a3 = v14;
                  v7 = v14 == 0 ? 0x8007000E : 0;
                  if ( v14 )
                  {
                    v15 = v13 >> 1;
                    if ( v15 )
                    {
                      if ( v15 <= 0x7FFFFFFF )
                      {
                        v16 = 2147483646 - v15;
                        v17 = *(_QWORD *)v8 - (_QWORD)v14;
                        do
                        {
                          if ( !(v16 + v15) )
                            break;
                          v18 = *(unsigned __int16 *)((char *)v14 + v17);
                          if ( !v18 )
                            break;
                          *v14++ = v18;
                          --v15;
                        }
                        while ( v15 );
                        v19 = v14 - 1;
                        if ( v15 )
                          v19 = v14;
                        *v19 = 0;
                      }
                      else
                      {
                        *v14 = 0;
                      }
                    }
                    *a4 = *(_DWORD *)(v8 + 8);
                    *a5 = *(_DWORD *)(v8 + 12);
                  }
                }
                else
                {
                  return (unsigned int)-2147024362;
                }
              }
            }
            else
            {
              return (unsigned int)-2147024809;
            }
          }
        }
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180009660  mov     rax, rsp
0x180009663  mov     [rax+8], rbx
0x180009667  mov     [rax+10h], rbp
0x18000966b  mov     [rax+18h], rsi
0x18000966f  mov     [rax+20h], rdi
0x180009673  push    r12
0x180009675  push    r14
0x180009677  push    r15
0x180009679  sub     rsp, 20h
0x18000967d  mov     r10d, edx
0x180009680  mov     rsi, r8
0x180009683  sar     r10d, 1Fh
0x180009687  mov     r8d, 80070057h
0x18000968d  mov     r15, r9
0x180009690  mov     r11, rcx
0x180009693  and     r10d, r8d
0x180009696  jl      loc_1800097FE
0x18000969c  cmp     edx, [rcx+34h]
0x18000969f  sbb     r10d, r10d
0x1800096a2  not     r10d
0x1800096a5  and     r10d, r8d
0x1800096a8  cmp     edx, [rcx+34h]
0x1800096ab  jnb     loc_1800097FE
0x1800096b1  mov     rax, rsi
0x1800096b4  neg     rax
0x1800096b7  sbb     r10d, r10d
0x1800096ba  xor     ebp, ebp
0x1800096bc  not     r10d
0x1800096bf  and     r10d, r8d
0x1800096c2  test    rsi, rsi
0x1800096c5  jz      loc_1800097FE
0x1800096cb  mov     rax, r9
0x1800096ce  neg     rax
0x1800096d1  sbb     r10d, r10d
0x1800096d4  not     r10d
0x1800096d7  and     r10d, r8d
0x1800096da  test    r9, r9
0x1800096dd  jz      loc_1800097FE
0x1800096e3  mov     r14, [rsp+38h+arg_20]
0x1800096e8  mov     rax, r14
0x1800096eb  neg     rax
0x1800096ee  sbb     r10d, r10d
0x1800096f1  not     r10d
0x1800096f4  and     r10d, r8d
0x1800096f7  test    r14, r14
0x1800096fa  jz      loc_1800097FE
0x180009700  mov     rax, [r11+38h]
0x180009704  movsxd  rcx, edx
0x180009707  mov     rdi, [rax+rcx*8]
0x18000970b  mov     rax, [rdi]
0x18000970e  test    rax, rax
0x180009711  jz      loc_1800097FB
0x180009717  mov     r12d, 7FFFFFFFh
0x18000971d  mov     edx, r12d
0x180009720  cmp     [rax], bp
0x180009723  jz      short loc_18000972F
0x180009725  add     rax, 2
0x180009729  sub     rdx, 1
0x18000972d  jnz     short loc_180009720
0x18000972f  mov     rax, rdx
0x180009732  mov     rcx, r12
0x180009735  neg     rax
0x180009738  mov     rax, rdx
0x18000973b  sbb     r10d, r10d
0x18000973e  sub     rcx, rdx
0x180009741  not     r10d
0x180009744  and     r10d, r8d
0x180009747  neg     rax
0x18000974a  sbb     r8, r8
0x18000974d  and     r8, rcx
0x180009750  test    rdx, rdx
0x180009753  jz      loc_1800097FE
0x180009759  lea     rcx, [r8+1]
0x18000975d  cmp     rcx, r8
0x180009760  jb      loc_1800097F3
0x180009766  mov     eax, 2
0x18000976b  mul     rcx
0x18000976e  mov     rbx, rax
0x180009771  test    rdx, rdx
0x180009774  jnz     short loc_1800097F3
0x180009776  mov     rcx, rax; cb
0x180009779  call    cs:__imp_CoTaskMemAlloc
0x18000977f  mov     rcx, rax
0x180009782  mov     [rsi], rax
0x180009785  neg     rax
0x180009788  sbb     r10d, r10d
0x18000978b  not     r10d
0x18000978e  and     r10d, 8007000Eh
0x180009795  test    rcx, rcx
0x180009798  jz      short loc_1800097FE
0x18000979a  shr     rbx, 1
0x18000979d  mov     rdx, [rdi]
0x1800097a0  jz      short loc_1800097E5
0x1800097a2  cmp     rbx, r12
0x1800097a5  jbe     short loc_1800097AC
0x1800097a7  mov     [rcx], bp
0x1800097aa  jmp     short loc_1800097E5
0x1800097ac  mov     r8d, 7FFFFFFEh
0x1800097b2  sub     r8, rbx
0x1800097b5  sub     rdx, rcx
0x1800097b8  lea     rax, [r8+rbx]
0x1800097bc  test    rax, rax
0x1800097bf  jz      short loc_1800097D7
0x1800097c1  movzx   eax, word ptr [rdx+rcx]
0x1800097c5  test    ax, ax
0x1800097c8  jz      short loc_1800097D7
0x1800097ca  mov     [rcx], ax
0x1800097cd  add     rcx, 2
0x1800097d1  sub     rbx, 1
0x1800097d5  jnz     short loc_1800097B8
0x1800097d7  test    rbx, rbx
0x1800097da  lea     rax, [rcx-2]
0x1800097de  cmovnz  rax, rcx
0x1800097e2  mov     [rax], bp
0x1800097e5  mov     eax, [rdi+8]
0x1800097e8  mov     [r15], eax
0x1800097eb  mov     eax, [rdi+0Ch]
0x1800097ee  mov     [r14], eax
0x1800097f1  jmp     short loc_1800097FE
0x1800097f3  mov     r10d, 80070216h
0x1800097f9  jmp     short loc_1800097FE
0x1800097fb  mov     r10d, r8d
0x1800097fe  mov     rbx, [rsp+38h+arg_0]
0x180009803  mov     eax, r10d
0x180009806  mov     rbp, [rsp+38h+arg_8]
0x18000980b  mov     rsi, [rsp+38h+arg_10]
0x180009810  mov     rdi, [rsp+38h+arg_18]
0x180009815  add     rsp, 20h
0x180009819  pop     r15
0x18000981b  pop     r14
0x18000981d  pop     r12
0x18000981f  retn
```
