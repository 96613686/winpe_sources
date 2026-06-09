# Parser::Tokenizer::getToken(void)

- ea: `0x180003280`
- end: `0x1800039ce`
- name: `?getToken@Tokenizer@Parser@@QEAA?AW4TokenKind@12@XZ`
- size: `1870`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ffd0`
- `0x18002a4c0`
- `0x18002a630`
- `0x18002a7b0`
- `0x18002aae0`
- `0x18002ad70`
- `0x18002ae70`

## callees

- `0x180003280`
- `0x1800039e0`
- `0x180003d54`
- `0x1800100a0`
- `0x18002bd28`
- `0x1800434ba`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180003488`
- `msvcrt!_wcsnicmp` at `0x180003488`
- `msvcrt!iswalnum` at `0x1800034bd`
- `msvcrt!iswalnum` at `0x1800034d8`
- `msvcrt!iswalnum` at `0x1800036f9`
- `msvcrt!iswalnum` at `0x18000370f`
- `msvcrt!iswalnum` at `0x1800034bd`
- `msvcrt!iswalnum` at `0x1800034d8`
- `msvcrt!iswalnum` at `0x1800036f9`
- `msvcrt!iswalnum` at `0x18000370f`
- `msvcrt!iswalpha` at `0x1800032c2`
- `msvcrt!iswalpha` at `0x1800034a9`
- `msvcrt!iswalpha` at `0x1800036e3`
- `msvcrt!iswalpha` at `0x1800032c2`
- `msvcrt!iswalpha` at `0x1800034a9`
- `msvcrt!iswalpha` at `0x1800036e3`
- `msvcrt!iswdigit` at `0x18000386b`
- `msvcrt!iswdigit` at `0x18000386b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800033ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800035ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800033ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800035ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000333b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003385`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003517`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003588`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800035a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003673`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800036a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003734`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003792`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000333b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003385`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003517`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003588`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800035a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003673`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800036a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003734`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003792`

## string_xrefs

- `0x1800037ee`: `com\complus\src\events\queryengine\parser.cpp`
- `0x1800038e4`: `com\complus\src\events\queryengine\parser.cpp`

## pseudocode

```c
__int64 __fastcall Parser::Tokenizer::getToken(wint_t **a1)
{
  wint_t *v2; // rcx
  wint_t v3; // ax
  wint_t *v4; // r8
  int v5; // edx
  int v6; // ecx
  __int64 result; // rax
  int v8; // ecx
  int v9; // eax
  void **v10; // r15
  LPVOID v11; // rax
  size_t v12; // rbx
  unsigned int v13; // r14d
  int v14; // esi
  int v15; // ebx
  __int64 v16; // rbp
  size_t v17; // r13
  int v18; // eax
  __int64 v19; // r13
  wint_t *v20; // rsi
  wint_t v21; // cx
  int v22; // ecx
  __int64 v23; // rbx
  wint_t v24; // ax
  wint_t *v25; // rbx
  unsigned int v26; // r14d
  unsigned __int16 *v27; // rsi
  __int64 v28; // rax
  int v29; // ecx
  _QWORD *v30; // r15
  int v31; // ecx
  LPVOID v32; // rax
  _WORD *v33; // rdx
  unsigned __int64 v34; // rcx
  __int64 v35; // rax
  int v36; // ecx
  int v37; // ecx
  wint_t v38; // cx
  wint_t v39; // cx
  int v40; // ecx
  int v41; // ecx
  wint_t v42; // ax
  unsigned __int16 v43; // r9
  wint_t v44; // ax
  Parser::Tokenizer *v45; // rcx

  while ( 1 )
  {
    v2 = *a1;
    v3 = **a1;
    if ( v3 != 32 && (unsigned __int16)(v3 - 9) > 1u )
      break;
    *a1 = v2 + 1;
  }
  a1[1] = v2;
  if ( !iswalpha(*v2) )
  {
    v4 = *a1;
    v5 = **a1;
    if ( v5 == 61 )
    {
      v8 = *((_DWORD *)a1 + 7);
      v9 = v8 - 8;
      if ( v4[1] == 61 )
      {
        if ( (v9 & 0xFFFFFFFC) == 0 && v8 != 10 )
          CoTaskMemFree(a1[5]);
        *a1 += 2;
        result = 12;
        a1[3] = (wint_t *)12;
      }
      else
      {
        if ( (v9 & 0xFFFFFFFC) == 0 && v8 != 10 )
          CoTaskMemFree(a1[5]);
        ++*a1;
        result = 12;
        a1[3] = (wint_t *)12;
      }
    }
    else if ( v5 == 34 )
    {
LABEL_38:
      v24 = v4[1];
      v25 = v4 + 1;
      v26 = 0;
      v27 = 0;
      if ( v24 )
      {
        do
        {
          if ( v24 == 92 && ((v42 = v25[1], v42 == 34) || v42 == 39) )
          {
            v28 = 4;
          }
          else
          {
            if ( *v25 == (_WORD)v5 )
              goto LABEL_44;
            v28 = 2;
          }
          v25 = (wint_t *)((char *)v25 + v28);
          v27 = (unsigned __int16 *)((char *)v27 + 1);
          v24 = *v25;
        }
        while ( *v25 );
      }
      else
      {
        v24 = 0;
      }
      if ( v24 == (_WORD)v5 )
      {
LABEL_44:
        v29 = *((_DWORD *)a1 + 7);
        if ( ((v29 - 8) & 0xFFFFFFFC) != 0 || v29 == 10 )
        {
          v30 = a1 + 5;
        }
        else
        {
          v30 = a1 + 5;
          CoTaskMemFree(a1[5]);
        }
        *((_DWORD *)a1 + 6) = 8;
        *((_DWORD *)a1 + 7) = 8;
        a1[4] = v27;
        v32 = CoTaskMemAlloc(saturated_mul((unsigned __int64)v27 + 1, 2u));
        *v30 = v32;
        if ( !v32 )
          InternalError(L"com\\complus\\src\\events\\queryengine\\parser.cpp", 0x89u, 0xC0001204, 0x10u);
        v33 = *a1 + 1;
        *a1 = v25 + 1;
        v34 = 0;
        if ( v27 )
        {
          do
          {
            if ( *v33 == 92 && ((v43 = v33[1], v43 == 34) || v43 == 39) )
            {
              a1[5][v34] = v43;
              v35 = 4;
            }
            else
            {
              *(_WORD *)(*v30 + 2 * v34) = *v33;
              v35 = 2;
            }
            ++v34;
            v33 = (_WORD *)((char *)v33 + v35);
          }
          while ( v34 < (unsigned __int64)v27 );
        }
        *(_WORD *)(*v30 + 2LL * (_QWORD)v27) = 0;
        return 8;
      }
      return v26;
    }
    else if ( **a1 )
    {
      if ( v5 == 41 )
      {
        v36 = *((_DWORD *)a1 + 7);
        if ( ((v36 - 8) & 0xFFFFFFFC) == 0 && v36 != 10 )
          CoTaskMemFree(a1[5]);
        ++*a1;
        result = 19;
        a1[3] = (wint_t *)19;
      }
      else
      {
        switch ( **a1 )
        {
          case '!':
          case '~':
            v45 = (Parser::Tokenizer *)a1;
            if ( v4[1] == 61 )
              goto LABEL_103;
            Parser::Tokenizer::FreeCurrentToken((Parser::Tokenizer *)a1);
            ++*a1;
            result = 4;
            *((_DWORD *)a1 + 6) = 4;
            break;
          case '&':
            v40 = *((_DWORD *)a1 + 7);
            if ( ((v40 - 8) & 0xFFFFFFFC) == 0 && v40 != 10 )
              CoTaskMemFree(a1[5]);
            ++*a1;
            result = 2;
            a1[3] = (wint_t *)2;
            return result;
          case '\'':
            goto LABEL_38;
          case '(':
            v6 = *((_DWORD *)a1 + 7);
            if ( ((v6 - 8) & 0xFFFFFFFC) == 0 && v6 != 10 )
              CoTaskMemFree(a1[5]);
            ++*a1;
            result = 18;
            a1[3] = (wint_t *)18;
            return result;
          case '+':
          case '-':
            if ( iswdigit(v4[1]) )
              goto LABEL_97;
            goto LABEL_102;
          case '0':
          case '1':
          case '2':
          case '3':
          case '4':
          case '5':
          case '6':
          case '7':
          case '8':
          case '9':
LABEL_97:
            result = Parser::Tokenizer::matchInteger(a1);
            break;
          case '<':
            v44 = v4[1];
            v45 = (Parser::Tokenizer *)a1;
            if ( v44 == 62 )
            {
LABEL_103:
              Parser::Tokenizer::FreeCurrentToken(v45);
              *a1 += 2;
              result = 13;
              *((_DWORD *)a1 + 6) = 13;
            }
            else if ( v44 == 61 )
            {
              Parser::Tokenizer::FreeCurrentToken((Parser::Tokenizer *)a1);
              *a1 += 2;
              result = 15;
              *((_DWORD *)a1 + 6) = 15;
            }
            else
            {
              Parser::Tokenizer::FreeCurrentToken((Parser::Tokenizer *)a1);
              ++*a1;
              result = 14;
              *((_DWORD *)a1 + 6) = 14;
            }
            break;
          case '>':
            if ( v4[1] == 61 )
            {
              Parser::Tokenizer::FreeCurrentToken((Parser::Tokenizer *)a1);
              *a1 += 2;
              result = 17;
              *((_DWORD *)a1 + 6) = 17;
            }
            else
            {
              Parser::Tokenizer::FreeCurrentToken((Parser::Tokenizer *)a1);
              ++*a1;
              result = 16;
              *((_DWORD *)a1 + 6) = 16;
            }
            break;
          case '{':
            Parser::Tokenizer::matchGUID(a1);
          case '|':
            v41 = *((_DWORD *)a1 + 7);
            if ( ((v41 - 8) & 0xFFFFFFFC) == 0 && v41 != 10 )
              CoTaskMemFree(a1[5]);
            ++*a1;
            result = 3;
            a1[3] = (wint_t *)3;
            break;
          default:
LABEL_102:
            result = 0;
            break;
        }
      }
    }
    else
    {
      v31 = *((_DWORD *)a1 + 7);
      if ( ((v31 - 8) & 0xFFFFFFFC) == 0 && v31 != 10 )
        CoTaskMemFree(a1[5]);
      a1[3] = (wint_t *)20;
      return 20;
    }
    return result;
  }
  v13 = 0;
  v14 = 0;
  v15 = 6;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v14 > v15 )
        goto LABEL_32;
      v16 = (v15 + v14) / 2;
      v17 = qword_180063878[3 * v16];
      v18 = _wcsnicmp(*a1, (&off_180063870)[3 * v16], v17);
      if ( v18 >= 0 )
        break;
      v15 = v16 - 1;
    }
    if ( v18 <= 0 )
      break;
    v14 = v16 + 1;
  }
  v19 = v17;
  if ( iswalpha((*a1)[v19]) )
    goto LABEL_32;
  v37 = *((_DWORD *)a1 + 7);
  if ( ((v37 - 8) & 0xFFFFFFFC) == 0 && v37 != 10 )
    CoTaskMemFree(a1[5]);
  *((_DWORD *)a1 + 7) = 0;
  result = LODWORD(qword_180063878[3 * v16 + 1]);
  *a1 = (wint_t *)((char *)*a1 + v19 * 2);
  *((_DWORD *)a1 + 6) = result;
  if ( !(_DWORD)result )
  {
LABEL_32:
    v20 = *a1;
    if ( iswalnum(**a1) )
    {
      do
      {
        v21 = v20[1];
        ++v20;
      }
      while ( iswalnum(v21) );
    }
    if ( *v20 == 46 )
    {
      if ( !iswalpha(v20[1]) )
        return v13;
      v38 = v20[2];
      v20 += 2;
      if ( iswalnum(v38) )
      {
        do
        {
          v39 = v20[1];
          ++v20;
        }
        while ( iswalnum(v39) );
      }
    }
    v22 = *((_DWORD *)a1 + 7);
    v23 = v20 - *a1;
    if ( ((v22 - 8) & 0xFFFFFFFC) != 0 || v22 == 10 )
    {
      v10 = (void **)(a1 + 5);
    }
    else
    {
      v10 = (void **)(a1 + 5);
      CoTaskMemFree(a1[5]);
    }
    *((_DWORD *)a1 + 6) = 11;
    *((_DWORD *)a1 + 7) = 11;
    a1[4] = (wint_t *)v23;
    v11 = CoTaskMemAlloc(saturated_mul(v23 + 1, 2u));
    *v10 = v11;
    if ( !v11 )
      InternalError(L"com\\complus\\src\\events\\queryengine\\parser.cpp", 0xEDu, 0xC0001204, 0x10u);
    v12 = 2 * v23;
    memcpy_0(*v10, *a1, v12);
    *(_WORD *)((char *)*v10 + v12) = 0;
    v13 = 11;
    *a1 = v20;
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x180003280  push    rdi
0x180003282  sub     rsp, 40h
0x180003286  mov     rdi, rcx
0x180003289  mov     rcx, [rdi]
0x18000328c  movzx   eax, word ptr [rcx]
0x18000328f  cmp     ax, 20h ; ' '
0x180003293  jz      loc_180003357
0x180003299  sub     ax, 9
0x18000329d  cmp     ax, 1
0x1800032a1  jbe     loc_180003357
0x1800032a7  mov     [rsp+48h+arg_0], rbx
0x1800032ac  mov     [rsp+48h+arg_10], rsi
0x1800032b1  mov     [rdi+8], rcx
0x1800032b5  movzx   ecx, word ptr [rcx]; C
0x1800032b8  mov     [rsp+48h+var_20], r14
0x1800032bd  mov     [rsp+48h+var_28], r15
0x1800032c2  call    cs:__imp_iswalpha
0x1800032c8  test    eax, eax
0x1800032ca  jnz     loc_18000342E
0x1800032d0  mov     r8, [rdi]
0x1800032d3  movzx   edx, word ptr [r8]
0x1800032d7  cmp     edx, 3Dh ; '='
0x1800032da  jz      loc_180003363
0x1800032e0  cmp     edx, 22h ; '"'
0x1800032e3  jz      loc_180003522; jumptable 0000000180003323 case 39
0x1800032e9  test    edx, edx
0x1800032eb  jz      loc_180003590
0x1800032f1  cmp     edx, 29h ; ')'
0x1800032f4  jz      loc_18000365D
0x1800032fa  lea     eax, [rdx-21h]; switch 94 cases
0x1800032fd  cmp     eax, 5Dh
0x180003300  ja      def_180003323; jumptable 0000000180003323 default case, cases 34-37,41,42,44,46,47,58,59,61,63-122,125
0x180003306  lea     r15, __ImageBase
0x18000330d  cdqe
0x18000330f  movzx   eax, ds:(byte_180003970 - 180000000h)[r15+rax]
0x180003318  mov     ecx, ds:(jpt_180003323 - 180000000h)[r15+rax*4]
0x180003320  add     rcx, r15
0x180003323  jmp     rcx; switch jump
0x180003325  mov     ecx, [rdi+1Ch]; jumptable 0000000180003323 case 40
0x180003328  lea     eax, [rcx-8]
0x18000332b  test    eax, 0FFFFFFFCh
0x180003330  jnz     short loc_180003341
0x180003332  cmp     ecx, 0Ah
0x180003335  jz      short loc_180003341
0x180003337  mov     rcx, [rdi+28h]; pv
0x18000333b  call    cs:__imp_CoTaskMemFree
0x180003341  add     qword ptr [rdi], 2
0x180003345  mov     eax, 12h
0x18000334a  mov     qword ptr [rdi+18h], 12h
0x180003352  jmp     loc_180003414
0x180003357  lea     rax, [rcx+2]
0x18000335b  mov     [rdi], rax
0x18000335e  jmp     loc_180003289
0x180003363  cmp     word ptr [r8+2], 3Dh ; '='
0x180003369  mov     ecx, [rdi+1Ch]
0x18000336c  lea     eax, [rcx-8]
0x18000336f  jz      loc_180003782
0x180003375  test    eax, 0FFFFFFFCh
0x18000337a  jnz     short loc_18000338B
0x18000337c  cmp     ecx, 0Ah
0x18000337f  jz      short loc_18000338B
0x180003381  mov     rcx, [rdi+28h]; pv
0x180003385  call    cs:__imp_CoTaskMemFree
0x18000338b  add     qword ptr [rdi], 2
0x18000338f  mov     eax, 0Ch
0x180003394  mov     qword ptr [rdi+18h], 0Ch
0x18000339c  jmp     short loc_180003414
0x18000339e  lea     r15, [rdi+28h]
0x1800033a2  lea     rcx, [rbx+1]
0x1800033a6  mov     dword ptr [rdi+18h], 0Bh
0x1800033ad  mov     eax, 2
0x1800033b2  mov     dword ptr [rdi+1Ch], 0Bh
0x1800033b9  mul     rcx
0x1800033bc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800033c3  mov     [rdi+20h], rbx
0x1800033c7  cmovb   rax, rcx
0x1800033cb  mov     rcx, rax; cb
0x1800033ce  call    cs:__imp_CoTaskMemAlloc
0x1800033d4  mov     [r15], rax
0x1800033d7  test    rax, rax
0x1800033da  jz      loc_1800038DF
0x1800033e0  mov     rdx, [rdi]; Src
0x1800033e3  add     rbx, rbx
0x1800033e6  mov     rcx, [r15]; void *
0x1800033e9  mov     r8, rbx; Size
0x1800033ec  call    memcpy_0
0x1800033f1  mov     rax, [r15]
0x1800033f4  mov     [rbx+rax], r14w
0x1800033f9  mov     r14d, 0Bh
0x1800033ff  mov     [rdi], rsi
0x180003402  mov     eax, r14d
0x180003405  mov     r12, [rsp+48h+var_10]
0x18000340a  mov     rbp, [rsp+48h+arg_8]
0x18000340f  mov     r13, [rsp+48h+var_18]
0x180003414  mov     r15, [rsp+48h+var_28]
0x180003419  mov     r14, [rsp+48h+var_20]
0x18000341e  mov     rsi, [rsp+48h+arg_10]
0x180003423  mov     rbx, [rsp+48h+arg_0]
0x180003428  add     rsp, 40h
0x18000342c  pop     rdi
0x18000342d  retn
0x18000342e  mov     [rsp+48h+arg_8], rbp
0x180003433  lea     r15, __ImageBase
0x18000343a  xor     r14d, r14d
0x18000343d  mov     [rsp+48h+var_10], r12
0x180003442  mov     esi, r14d
0x180003445  mov     [rsp+48h+var_18], r13
0x18000344a  mov     ebx, 6
0x18000344f  nop
0x180003450  cmp     esi, ebx
0x180003452  jg      short loc_1800034B7
0x180003454  mov     rcx, [rdi]; String1
0x180003457  lea     eax, [rbx+rsi]
0x18000345a  cdq
0x18000345b  sub     eax, edx
0x18000345d  sar     eax, 1
0x18000345f  movsxd  rbp, eax
0x180003462  lea     rdx, ds:0[rbp*2]
0x18000346a  add     rdx, rbp
0x18000346d  lea     r12, ds:0[rdx*8]
0x180003475  mov     r13, [r12+r15+63878h]
0x18000347d  mov     rdx, [r12+r15+63870h]; String2
0x180003485  mov     r8, r13; MaxCount
0x180003488  call    cs:__imp__wcsnicmp
0x18000348e  test    eax, eax
0x180003490  js      short loc_180003499
0x180003492  jle     short loc_18000349E
0x180003494  lea     esi, [rbp+1]
0x180003497  jmp     short loc_180003450
0x180003499  lea     ebx, [rbp-1]
0x18000349c  jmp     short loc_180003450
0x18000349e  mov     rcx, [rdi]
0x1800034a1  add     r13, r13
0x1800034a4  movzx   ecx, word ptr [rcx+r13]; C
0x1800034a9  call    cs:__imp_iswalpha
0x1800034af  test    eax, eax
0x1800034b1  jz      loc_18000368F
0x1800034b7  mov     rsi, [rdi]
0x1800034ba  movzx   ecx, word ptr [rsi]; C
0x1800034bd  call    cs:__imp_iswalnum
0x1800034c3  test    eax, eax
0x1800034c5  jz      short loc_1800034E2
0x1800034c7  nop     word ptr [rax+rax+00000000h]
0x1800034d0  movzx   ecx, word ptr [rsi+2]; C
0x1800034d4  add     rsi, 2
0x1800034d8  call    cs:__imp_iswalnum
0x1800034de  test    eax, eax
0x1800034e0  jnz     short loc_1800034D0
0x1800034e2  cmp     word ptr [rsi], 2Eh ; '.'
0x1800034e6  jz      loc_1800036DF
0x1800034ec  mov     ecx, [rdi+1Ch]
0x1800034ef  mov     rbx, rsi
0x1800034f2  sub     rbx, [rdi]
0x1800034f5  sar     rbx, 1
0x1800034f8  lea     eax, [rcx-8]
0x1800034fb  test    eax, 0FFFFFFFCh
0x180003500  jnz     loc_18000339E
0x180003506  cmp     ecx, 0Ah
0x180003509  jz      loc_18000339E
0x18000350f  mov     rcx, [rdi+28h]; pv
0x180003513  lea     r15, [rdi+28h]
0x180003517  call    cs:__imp_CoTaskMemFree
0x18000351d  jmp     loc_1800033A2
0x180003522  movzx   eax, word ptr [r8+2]; jumptable 0000000180003323 case 39
0x180003527  lea     rbx, [r8+2]
0x18000352b  xor     r14d, r14d
0x18000352e  mov     esi, r14d
0x180003531  test    ax, ax
0x180003534  jz      loc_1800036CA
0x18000353a  nop     word ptr [rax+rax+00h]
0x180003540  cmp     ax, 5Ch ; '\'
0x180003544  jz      loc_1800037AE
0x18000354a  movzx   eax, word ptr [rbx]
0x18000354d  cmp     ax, dx
0x180003550  jz      short loc_18000356E
0x180003552  mov     eax, 2
0x180003557  add     rbx, rax
0x18000355a  inc     rsi
0x18000355d  movzx   eax, word ptr [rbx]
0x180003560  test    ax, ax
0x180003563  jnz     short loc_180003540
0x180003565  cmp     ax, dx
0x180003568  jnz     loc_180003655
0x18000356e  mov     ecx, [rdi+1Ch]
0x180003571  lea     eax, [rcx-8]
0x180003574  test    eax, 0FFFFFFFCh
0x180003579  jnz     short loc_1800035BE
0x18000357b  cmp     ecx, 0Ah
0x18000357e  jz      short loc_1800035BE
0x180003580  mov     rcx, [rdi+28h]; pv
0x180003584  lea     r15, [rdi+28h]
0x180003588  call    cs:__imp_CoTaskMemFree
0x18000358e  jmp     short loc_1800035C2
0x180003590  mov     ecx, [rdi+1Ch]
0x180003593  lea     eax, [rcx-8]
0x180003596  test    eax, 0FFFFFFFCh
0x18000359b  jnz     short loc_1800035AC
0x18000359d  cmp     ecx, 0Ah
0x1800035a0  jz      short loc_1800035AC
0x1800035a2  mov     rcx, [rdi+28h]; pv
0x1800035a6  call    cs:__imp_CoTaskMemFree
0x1800035ac  mov     qword ptr [rdi+18h], 14h
0x1800035b4  mov     eax, 14h
0x1800035b9  jmp     loc_180003414
0x1800035be  lea     r15, [rdi+28h]
0x1800035c2  lea     rcx, [rsi+1]
0x1800035c6  mov     dword ptr [rdi+18h], 8
0x1800035cd  mov     eax, 2
0x1800035d2  mov     dword ptr [rdi+1Ch], 8
0x1800035d9  mul     rcx
0x1800035dc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800035e3  mov     [rdi+20h], rsi
0x1800035e7  cmovb   rax, rcx
0x1800035eb  mov     rcx, rax; cb
0x1800035ee  call    cs:__imp_CoTaskMemAlloc
0x1800035f4  mov     [r15], rax
0x1800035f7  test    rax, rax
0x1800035fa  jz      loc_1800037E9
0x180003600  mov     rdx, [rdi]
0x180003603  lea     rax, [rbx+2]
0x180003607  add     rdx, 2
0x18000360b  mov     [rdi], rax
0x18000360e  mov     rcx, r14
0x180003611  test    rsi, rsi
0x180003614  jz      short loc_180003647
0x180003616  nop     word ptr [rax+rax+00000000h]
0x180003620  movzx   r8d, word ptr [rdx]
0x180003624  cmp     r8w, 5Ch ; '\'
0x180003629  jz      loc_1800037C6
0x18000362f  mov     rax, [r15]
0x180003632  mov     [rax+rcx*2], r8w
0x180003637  mov     eax, 2
0x18000363c  inc     rcx
0x18000363f  add     rdx, rax
0x180003642  cmp     rcx, rsi
0x180003645  jb      short loc_180003620
0x180003647  mov     rax, [r15]
0x18000364a  mov     [rax+rsi*2], r14w
0x18000364f  mov     r14d, 8
0x180003655  mov     eax, r14d
0x180003658  jmp     loc_180003414
0x18000365d  mov     ecx, [rdi+1Ch]
0x180003660  lea     eax, [rcx-8]
0x180003663  test    eax, 0FFFFFFFCh
0x180003668  jnz     short loc_180003679
0x18000366a  cmp     ecx, 0Ah
0x18000366d  jz      short loc_180003679
0x18000366f  mov     rcx, [rdi+28h]; pv
0x180003673  call    cs:__imp_CoTaskMemFree
0x180003679  add     qword ptr [rdi], 2
0x18000367d  mov     eax, 13h
0x180003682  mov     qword ptr [rdi+18h], 13h
0x18000368a  jmp     loc_180003414
0x18000368f  mov     ecx, [rdi+1Ch]
0x180003692  lea     eax, [rcx-8]
0x180003695  test    eax, 0FFFFFFFCh
0x18000369a  jnz     short loc_1800036AB
0x18000369c  cmp     ecx, 0Ah
0x18000369f  jz      short loc_1800036AB
0x1800036a1  mov     rcx, [rdi+28h]; pv
0x1800036a5  call    cs:__imp_CoTaskMemFree
0x1800036ab  mov     [rdi+1Ch], r14d
0x1800036af  mov     eax, [r12+r15+63880h]
0x1800036b7  add     [rdi], r13
0x1800036ba  mov     [rdi+18h], eax
0x1800036bd  test    eax, eax
0x1800036bf  jnz     loc_180003405
0x1800036c5  jmp     loc_1800034B7
0x1800036ca  mov     eax, r14d
0x1800036cd  jmp     loc_180003565
0x1800036d2  mov     rcx, rdi; jumptable 0000000180003323 case 123
0x1800036d5  call    ?matchGUID@Tokenizer@Parser@@AEAA?AW4TokenKind@12@XZ; Parser::Tokenizer::matchGUID(void)
0x1800036da  jmp     loc_180003414
0x1800036df  movzx   ecx, word ptr [rsi+2]; C
0x1800036e3  call    cs:__imp_iswalpha
0x1800036e9  test    eax, eax
0x1800036eb  jz      loc_180003402
0x1800036f1  movzx   ecx, word ptr [rsi+4]; C
0x1800036f5  add     rsi, 4
0x1800036f9  call    cs:__imp_iswalnum
0x1800036ff  test    eax, eax
0x180003701  jz      loc_1800034EC
0x180003707  movzx   ecx, word ptr [rsi+2]; C
0x18000370b  add     rsi, 2
0x18000370f  call    cs:__imp_iswalnum
0x180003715  test    eax, eax
0x180003717  jnz     short loc_180003707
0x180003719  jmp     loc_1800034EC
0x18000371e  mov     ecx, [rdi+1Ch]; jumptable 0000000180003323 case 38
0x180003721  lea     eax, [rcx-8]
0x180003724  test    eax, 0FFFFFFFCh
0x180003729  jnz     short loc_18000373A
0x18000372b  cmp     ecx, 0Ah
0x18000372e  jz      short loc_18000373A
0x180003730  mov     rcx, [rdi+28h]; pv
0x180003734  call    cs:__imp_CoTaskMemFree
0x18000373a  add     qword ptr [rdi], 2
0x18000373e  mov     eax, 2
0x180003743  mov     qword ptr [rdi+18h], 2
0x18000374b  jmp     loc_180003414
  ... truncated ...
```
