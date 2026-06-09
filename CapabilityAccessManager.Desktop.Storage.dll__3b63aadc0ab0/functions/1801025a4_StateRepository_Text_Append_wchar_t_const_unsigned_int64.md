# StateRepository::Text::Append(wchar_t const *,unsigned __int64)

- ea: `0x1801025a4`
- end: `0x180102723`
- name: `?Append@Text@StateRepository@@QEAAJPEB_W_K@Z`
- size: `383`
- prototype: `__int64 __fastcall(StateRepository::Text *this, const wchar_t *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180104754`

## callees

- `0x1800eabf4`
- `0x1800edb2c`
- `0x1800f7630`
- `0x1801025a4`
- `0x18010272c`
- `0x180102954`

## string_xrefs

- `0x1801025ce`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180102630`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180102711`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Text::Append(StateRepository::Text *this, const wchar_t *a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rbx
  const wchar_t *v4; // rsi
  __int64 v7; // rdi
  unsigned __int64 v8; // r15
  int v9; // eax
  unsigned int v10; // ebp
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // r8
  _WORD *v13; // rax
  unsigned __int64 v14; // rax
  _WORD *v15; // r8
  unsigned __int64 i; // rdx
  _WORD *v17; // rcx
  __int64 v18; // r9
  int v19; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 0;
  if ( !a2 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD1,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
      (const char *)0x80070057LL);
    return 0;
  }
  if ( !*(_QWORD *)this )
    return StateRepository::Text::SetFromChars(this, a2, a3);
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(*(_QWORD *)this + 2 * v7) );
  v8 = v7 + a3 + 1;
  v9 = StateRepository::Text::EnsureCapacity(this, v8, 1);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v11 = v3 + 1;
    if ( v3 > 0x7FFFFFFE )
    {
      v18 = 2147942487LL;
    }
    else
    {
      v12 = v3 + 1;
      v13 = (_WORD *)(*(_QWORD *)this + 2 * v7);
      do
      {
        if ( !*v13 )
          break;
        ++v13;
        --v12;
      }
      while ( v12 );
      if ( v12 )
        v14 = v11 - v12;
      else
        v14 = 0;
      if ( v12 )
      {
        v15 = (_WORD *)(*(_QWORD *)this + 2 * v7 + 2 * v14);
        for ( i = v11 - v14; i; --i )
        {
          if ( !v3 )
            break;
          if ( !*v4 )
            break;
          *v15++ = *v4++;
          --v3;
        }
        v17 = v15 - 1;
        v18 = i == 0 ? 0x8007007A : 0;
        if ( i )
          v17 = v15;
        *v17 = 0;
        if ( i )
        {
          *((_QWORD *)this + 1) = v8;
          return 0;
        }
      }
      else
      {
        v18 = 2147942487LL;
      }
    }
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
      (const char *)v18,
      v19);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xDB,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
    (const char *)(unsigned int)v9,
    v19);
  return v10;
}

```

## disassembly

```asm
0x1801025a4  push    rbx
0x1801025a6  push    rbp
0x1801025a7  push    rsi
0x1801025a8  push    rdi
0x1801025a9  push    r12
0x1801025ab  push    r14
0x1801025ad  push    r15; int
0x1801025af  sub     rsp, 20h
0x1801025b3  xor     r12d, r12d
0x1801025b6  mov     rbx, r8
0x1801025b9  mov     rsi, rdx
0x1801025bc  mov     r14, rcx
0x1801025bf  test    r8, r8
0x1801025c2  jz      short loc_1801025E5
0x1801025c4  test    rdx, rdx
0x1801025c7  jnz     short loc_1801025F6
0x1801025c9  mov     rcx, [rsp+58h]; this
0x1801025ce  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\staterepositor"...
0x1801025d5  mov     r9d, 80070057h; char *
0x1801025db  mov     edx, 0D1h; void *
0x1801025e0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801025e5  xor     eax, eax
0x1801025e7  add     rsp, 20h
0x1801025eb  pop     r15
0x1801025ed  pop     r14
0x1801025ef  pop     r12
0x1801025f1  pop     rdi
0x1801025f2  pop     rsi
0x1801025f3  pop     rbp
0x1801025f4  pop     rbx
0x1801025f5  retn
0x1801025f6  mov     rax, [rcx]
0x1801025f9  test    rax, rax
0x1801025fc  jnz     short loc_180102605
0x1801025fe  call    ?SetFromChars@Text@StateRepository@@QEAAJPEB_W_K@Z; StateRepository::Text::SetFromChars(wchar_t const *,unsigned __int64)
0x180102603  jmp     short loc_1801025E7
0x180102605  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180102609  inc     rdi
0x18010260c  cmp     [rax+rdi*2], r12w
0x180102611  jnz     short loc_180102609
0x180102613  lea     r15, [r8+1]
0x180102617  mov     r8b, 1; bool
0x18010261a  add     r15, rdi
0x18010261d  mov     rdx, r15; unsigned __int64
0x180102620  call    ?EnsureCapacity@Text@StateRepository@@QEAAJ_K_N@Z; StateRepository::Text::EnsureCapacity(unsigned __int64,bool)
0x180102625  mov     ebp, eax
0x180102627  test    eax, eax
0x180102629  jns     short loc_180102648
0x18010262b  mov     rcx, [rsp+58h]; this
0x180102630  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\staterepositor"...
0x180102637  mov     r9d, eax; char *
0x18010263a  mov     edx, 0DBh; void *
0x18010263f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180102644  mov     eax, ebp
0x180102646  jmp     short loc_1801025E7
0x180102648  lea     rdx, [rbx+1]
0x18010264c  mov     r11d, 7FFFFFFEh
0x180102652  lea     rax, [rdx-1]
0x180102656  cmp     rax, r11
0x180102659  ja      loc_180102706
0x18010265f  mov     rax, [r14]
0x180102662  mov     r8, rdx
0x180102665  lea     r10, [rax+rdi*2]
0x180102669  mov     rax, r10
0x18010266c  cmp     [rax], r12w
0x180102670  jz      short loc_18010267C
0x180102672  add     rax, 2
0x180102676  sub     r8, 1
0x18010267a  jnz     short loc_18010266C
0x18010267c  mov     rax, r8
0x18010267f  mov     r9d, 80070057h
0x180102685  neg     rax
0x180102688  sbb     ecx, ecx
0x18010268a  not     ecx
0x18010268c  and     ecx, r9d
0x18010268f  test    r8, r8
0x180102692  jz      short loc_18010269C
0x180102694  mov     rax, rdx
0x180102697  sub     rax, r8
0x18010269a  jmp     short loc_18010269F
0x18010269c  mov     rax, r12
0x18010269f  test    r8, r8
0x1801026a2  jz      short loc_180102701
0x1801026a4  cmp     rbx, r11
0x1801026a7  ja      short loc_18010270C
0x1801026a9  lea     r8, [r10+rax*2]
0x1801026ad  sub     rdx, rax
0x1801026b0  jz      short loc_1801026D4
0x1801026b2  test    rbx, rbx
0x1801026b5  jz      short loc_1801026D4
0x1801026b7  movzx   eax, word ptr [rsi]
0x1801026ba  test    ax, ax
0x1801026bd  jz      short loc_1801026D4
0x1801026bf  mov     [r8], ax
0x1801026c3  add     rsi, 2
0x1801026c7  add     r8, 2
0x1801026cb  dec     rbx
0x1801026ce  sub     rdx, 1
0x1801026d2  jnz     short loc_1801026B2
0x1801026d4  mov     rax, rdx
0x1801026d7  lea     rcx, [r8-2]
0x1801026db  neg     rax
0x1801026de  sbb     r9d, r9d
0x1801026e1  not     r9d
0x1801026e4  and     r9d, 8007007Ah
0x1801026eb  test    rdx, rdx
0x1801026ee  cmovnz  rcx, r8
0x1801026f2  mov     [rcx], r12w
0x1801026f6  jz      short loc_18010270C
0x1801026f8  mov     [r14+8], r15
0x1801026fc  jmp     loc_1801025E5
0x180102701  mov     r9d, ecx
0x180102704  jmp     short loc_18010270C
0x180102706  mov     r9d, 80070057h; char *
0x18010270c  mov     rcx, [rsp+58h]; this
0x180102711  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\staterepositor"...
0x180102718  mov     edx, 0DCh; void *
0x18010271d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
