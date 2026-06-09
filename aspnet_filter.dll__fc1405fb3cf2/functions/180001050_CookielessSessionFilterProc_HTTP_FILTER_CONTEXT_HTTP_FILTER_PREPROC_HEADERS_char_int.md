# CookielessSessionFilterProc(_HTTP_FILTER_CONTEXT *,_HTTP_FILTER_PREPROC_HEADERS *,char *,int *)

- ea: `0x180001050`
- end: `0x1800011e0`
- name: `?CookielessSessionFilterProc@@YAKPEAU_HTTP_FILTER_CONTEXT@@PEAU_HTTP_FILTER_PREPROC_HEADERS@@PEADPEAH@Z`
- size: `400`
- prototype: `__int64 __fastcall(struct _HTTP_FILTER_CONTEXT *, struct _HTTP_FILTER_PREPROC_HEADERS *, char *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180001ba0`

## callees

- `0x180001050`
- `0x18000138c`
- `0x1800030d4`
- `0x1800042f0`
- `0x1800043b0`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x18000107a`
- `KERNEL32!lstrlenA` at `0x18000107a`

## pseudocode

```c
__int64 __fastcall CookielessSessionFilterProc(
        struct _HTTP_FILTER_CONTEXT *a1,
        struct _HTTP_FILTER_PREPROC_HEADERS *a2,
        char *a3,
        int *a4)
{
  char *v7; // r14
  char *v8; // rbx
  char *v9; // rdx
  char v10; // r8
  int v11; // r10d
  unsigned __int8 v12; // si
  int v13; // edx
  __int64 v14; // rdi
  char v15; // bp
  char *v16; // rdx
  bool v17; // zf
  __int64 result; // rax
  int v19; // [rsp+70h] [rbp+18h]

  v7 = 0;
  v8 = 0;
  v19 = lstrlenA(a3);
  v9 = a3;
  v10 = 0;
  v11 = v19 - 1;
  while ( v11 >= 3 )
  {
    ++v9;
    --v11;
    if ( *(v9 - 1) == 47 )
    {
      if ( *v9 == 40 )
      {
        v8 = v9;
        while ( 1 )
        {
          ++v9;
          --v11;
          if ( *v9 == 41 && v9[1] == 47 )
            break;
          if ( v11 < 2 )
            goto LABEL_21;
        }
        v7 = v8 + 1;
        v10 = 1;
      }
      else if ( *v9 == 37 && v11 >= 6 && v9[1] == 50 && v9[2] == 56 )
      {
        v8 = v9;
        v9 += 2;
        v11 -= 2;
        while ( v11 >= 4 )
        {
          ++v9;
          --v11;
          if ( *v9 == 37 && v9[1] == 50 && v9[2] == 57 && v9[3] == 47 )
          {
            v7 = v8 + 3;
            v12 = 1;
            goto LABEL_23;
          }
        }
      }
    }
LABEL_21:
    if ( v10 )
    {
      v12 = 0;
LABEL_23:
      v13 = (_DWORD)v9 - (_DWORD)v7;
      v14 = v13;
      v15 = v7[v13];
      v7[v13] = 0;
      if ( (unsigned int)IsValidCookielessHeader(v7, v13) )
      {
        if ( ((unsigned int (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, const char *, char *))a2->SetHeader)(
               a1,
               "AspFilterSessionId:",
               v7) )
        {
          v16 = &v8[4 * v12 + 3 + v14];
          memmove_0(v8, v16, (int)a3 - (int)v16 + v19 + 1);
          *a4 = 1;
          return 134217730;
        }
        goto LABEL_29;
      }
      v7[v14] = v15;
      break;
    }
  }
  if ( ((unsigned int (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, const char *, char *))a2->SetHeader)(
         a1,
         "AspFilterSessionId:",
         byte_180005509) )
  {
    return 134217730;
  }
LABEL_29:
  v17 = (unsigned int)GetLastWin32Error() == 0;
  result = 134217732;
  if ( !v17 )
    return result;
  return 134217730;
}

```

## disassembly

```asm
0x180001050  mov     [rsp+arg_0], rbx
0x180001055  mov     [rsp+arg_18], r9
0x18000105a  push    rbp
0x18000105b  push    rsi
0x18000105c  push    rdi
0x18000105d  push    r12
0x18000105f  push    r13
0x180001061  push    r14
0x180001063  push    r15
0x180001065  sub     rsp, 20h
0x180001069  mov     r12, rcx
0x18000106c  mov     r15, r8
0x18000106f  mov     rcx, r8; lpString
0x180001072  mov     r13, rdx
0x180001075  xor     r14d, r14d
0x180001078  xor     ebx, ebx
0x18000107a  call    cs:__imp_lstrlenA
0x180001080  mov     [rsp+58h+arg_10], eax
0x180001084  mov     rdx, r15
0x180001087  xor     r8b, r8b
0x18000108a  mov     cl, 2Fh ; '/'
0x18000108c  lea     r10d, [rax-1]
0x180001090  cmp     r10d, 3
0x180001094  jl      loc_180001199
0x18000109a  inc     rdx
0x18000109d  dec     r10d
0x1800010a0  cmp     [rdx-1], cl
0x1800010a3  jnz     short loc_180001114
0x1800010a5  cmp     byte ptr [rdx], 28h ; '('
0x1800010a8  jnz     short loc_1800010CE
0x1800010aa  mov     rbx, rdx
0x1800010ad  inc     rdx
0x1800010b0  dec     r10d
0x1800010b3  cmp     byte ptr [rdx], 29h ; ')'
0x1800010b6  jnz     short loc_1800010BD
0x1800010b8  cmp     [rdx+1], cl
0x1800010bb  jz      short loc_1800010C5
0x1800010bd  cmp     r10d, 2
0x1800010c1  jl      short loc_180001114
0x1800010c3  jmp     short loc_1800010AD
0x1800010c5  lea     r14, [rbx+1]
0x1800010c9  mov     r8b, 1
0x1800010cc  jmp     short loc_180001114
0x1800010ce  cmp     byte ptr [rdx], 25h ; '%'
0x1800010d1  jnz     short loc_180001114
0x1800010d3  cmp     r10d, 6
0x1800010d7  jl      short loc_180001114
0x1800010d9  cmp     byte ptr [rdx+1], 32h ; '2'
0x1800010dd  jnz     short loc_180001114
0x1800010df  cmp     byte ptr [rdx+2], 38h ; '8'
0x1800010e3  jnz     short loc_180001114
0x1800010e5  mov     rbx, rdx
0x1800010e8  add     rdx, 2
0x1800010ec  sub     r10d, 2
0x1800010f0  jmp     short loc_18000110E
0x1800010f2  inc     rdx
0x1800010f5  dec     r10d
0x1800010f8  cmp     byte ptr [rdx], 25h ; '%'
0x1800010fb  jnz     short loc_18000110E
0x1800010fd  cmp     byte ptr [rdx+1], 32h ; '2'
0x180001101  jnz     short loc_18000110E
0x180001103  cmp     byte ptr [rdx+2], 39h ; '9'
0x180001107  jnz     short loc_18000110E
0x180001109  cmp     [rdx+3], cl
0x18000110c  jz      short loc_18000118C
0x18000110e  cmp     r10d, 4
0x180001112  jge     short loc_1800010F2
0x180001114  test    r8b, r8b
0x180001117  jz      loc_180001090
0x18000111d  xor     sil, sil
0x180001120  sub     edx, r14d; int
0x180001123  mov     rcx, r14; char *
0x180001126  movsxd  rdi, edx
0x180001129  mov     bpl, [rdi+r14]
0x18000112d  mov     byte ptr [rdi+r14], 0
0x180001132  call    ?IsValidCookielessHeader@@YAHPEADH@Z; IsValidCookielessHeader(char *,int)
0x180001137  test    eax, eax
0x180001139  jz      short loc_180001195
0x18000113b  mov     rax, [r13+8]
0x18000113f  lea     rdx, aAspfiltersessi; "AspFilterSessionId:"
0x180001146  mov     r8, r14
0x180001149  mov     rcx, r12
0x18000114c  call    cs:__guard_dispatch_icall_fptr
0x180001152  test    eax, eax
0x180001154  jz      short loc_1800011B8
0x180001156  movzx   eax, sil
0x18000115a  mov     rcx, rbx; void *
0x18000115d  lea     rdx, ds:3[rax*4]
0x180001165  mov     eax, [rsp+58h+arg_10]
0x180001169  add     rdx, rbx
0x18000116c  inc     eax
0x18000116e  add     rdx, rdi; Src
0x180001171  sub     r15d, edx
0x180001174  add     eax, r15d
0x180001177  movsxd  r8, eax; Size
0x18000117a  call    memmove_0
0x18000117f  mov     rax, [rsp+58h+arg_18]
0x180001184  mov     dword ptr [rax], 1
0x18000118a  jmp     short loc_1800011C6
0x18000118c  lea     r14, [rbx+3]
0x180001190  mov     sil, 1
0x180001193  jmp     short loc_180001120
0x180001195  mov     [rdi+r14], bpl
0x180001199  mov     rax, [r13+8]
0x18000119d  lea     r8, byte_180005509
0x1800011a4  lea     rdx, aAspfiltersessi; "AspFilterSessionId:"
0x1800011ab  mov     rcx, r12
0x1800011ae  call    cs:__guard_dispatch_icall_fptr
0x1800011b4  test    eax, eax
0x1800011b6  jnz     short loc_1800011C6
0x1800011b8  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800011bd  test    eax, eax
0x1800011bf  mov     eax, 8000004h
0x1800011c4  jnz     short loc_1800011CB
0x1800011c6  mov     eax, 8000002h
0x1800011cb  mov     rbx, [rsp+58h+arg_0]
0x1800011d0  add     rsp, 20h
0x1800011d4  pop     r15
0x1800011d6  pop     r14
0x1800011d8  pop     r13
0x1800011da  pop     r12
0x1800011dc  pop     rdi
0x1800011dd  pop     rsi
0x1800011de  pop     rbp
0x1800011df  retn
```
