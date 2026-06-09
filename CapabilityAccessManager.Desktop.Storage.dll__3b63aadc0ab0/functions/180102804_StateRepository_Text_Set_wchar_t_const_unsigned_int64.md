# StateRepository::Text::Set(wchar_t const *,unsigned __int64)

- ea: `0x180102804`
- end: `0x18010294b`
- name: `?Set@Text@StateRepository@@QEAAJPEB_W_K@Z`
- size: `327`
- prototype: `__int64 __fastcall(StateRepository::Text *__hidden this, const wchar_t *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1801011ac`

## callees

- `0x1800eabf4`
- `0x1800edb2c`
- `0x18010272c`
- `0x1801027d0`
- `0x180102804`

## string_xrefs

- `0x18010286f`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x1801028af`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180102936`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Text::Set(const void **this, const wchar_t *a2)
{
  const wchar_t *v2; // rsi
  const wchar_t *v4; // rax
  __int64 v5; // rdx
  unsigned int v6; // ebx
  unsigned int v7; // edi
  __int64 v8; // rax
  unsigned __int64 v10; // rdi
  int v11; // eax
  unsigned int v12; // ebp
  _WORD *v13; // rdx
  __int64 v14; // rax
  unsigned __int64 v15; // r8
  _WORD *v16; // rcx
  int v17; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = a2;
  if ( a2 )
  {
    v4 = a2;
    v5 = 500000000;
    do
    {
      if ( !*v4 )
        break;
      ++v4;
      --v5;
    }
    while ( v5 );
    v6 = -2147024809;
    v7 = v5 == 0 ? 0x80070057 : 0;
    v8 = (500000000 - v5) & -(__int64)(v5 != 0);
    if ( !v5 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
        (const char *)v7,
        v17);
      return v7;
    }
    v10 = v8 + 1;
    v11 = StateRepository::Text::EnsureCapacity(this, v8 + 1, 0);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
        (const char *)(unsigned int)v11,
        v17);
      return v12;
    }
    v13 = *this;
    if ( v10 )
    {
      if ( v10 > 0x7FFFFFFF )
      {
        *v13 = 0;
      }
      else
      {
        v14 = 2147483646;
        v15 = v10;
        do
        {
          if ( !v14 )
            break;
          if ( !*v2 )
            break;
          *v13++ = *v2++;
          --v14;
          --v15;
        }
        while ( v15 );
        v16 = v13 - 1;
        v6 = v15 == 0 ? 0x8007007A : 0;
        if ( v15 )
          v16 = v13;
        *v16 = 0;
        if ( v15 )
        {
          this[1] = (const void *)v10;
          return 0;
        }
      }
    }
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
      (const char *)v6,
      v17);
  }
  StateRepository::TextA::Reset((StateRepository::TextA *)this);
  return 0;
}

```

## disassembly

```asm
0x180102804  push    rbx
0x180102806  push    rbp
0x180102807  push    rsi
0x180102808  push    rdi
0x180102809  push    r14
0x18010280b  push    r15
0x18010280d  sub     rsp, 28h
0x180102811  xor     r15d, r15d
0x180102814  mov     rsi, rdx
0x180102817  mov     r14, rcx
0x18010281a  test    rdx, rdx
0x18010281d  jnz     short loc_180102829
0x18010281f  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180102824  jmp     loc_180102926
0x180102829  mov     r8d, 1DCD6500h
0x18010282f  mov     rax, rsi
0x180102832  mov     edx, r8d
0x180102835  cmp     [rax], r15w
0x180102839  jz      short loc_180102845
0x18010283b  add     rax, 2
0x18010283f  sub     rdx, 1
0x180102843  jnz     short loc_180102835
0x180102845  mov     rax, rdx
0x180102848  mov     ebx, 80070057h
0x18010284d  neg     rax
0x180102850  mov     rcx, rdx
0x180102853  sbb     edi, edi
0x180102855  sub     r8, rdx
0x180102858  not     edi
0x18010285a  and     edi, ebx
0x18010285c  neg     rcx
0x18010285f  sbb     rax, rax
0x180102862  and     rax, r8
0x180102865  test    rdx, rdx
0x180102868  jnz     short loc_180102892
0x18010286a  mov     rcx, [rsp+58h]; this
0x18010286f  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\staterepositor"...
0x180102876  mov     r9d, edi; char *
0x180102879  mov     edx, 1Bh; void *
0x18010287e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180102883  mov     eax, edi
0x180102885  add     rsp, 28h
0x180102889  pop     r15
0x18010288b  pop     r14
0x18010288d  pop     rdi
0x18010288e  pop     rsi
0x18010288f  pop     rbp
0x180102890  pop     rbx
0x180102891  retn
0x180102892  lea     rdi, [rax+1]
0x180102896  xor     r8d, r8d; bool
0x180102899  mov     rdx, rdi; unsigned __int64
0x18010289c  mov     rcx, r14; this
0x18010289f  call    ?EnsureCapacity@Text@StateRepository@@QEAAJ_K_N@Z; StateRepository::Text::EnsureCapacity(unsigned __int64,bool)
0x1801028a4  mov     ebp, eax
0x1801028a6  test    eax, eax
0x1801028a8  jns     short loc_1801028C7
0x1801028aa  mov     rcx, [rsp+58h]; this
0x1801028af  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\staterepositor"...
0x1801028b6  mov     r9d, eax; char *
0x1801028b9  mov     edx, 1Dh; void *
0x1801028be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801028c3  mov     eax, ebp
0x1801028c5  jmp     short loc_180102885
0x1801028c7  mov     rdx, [r14]
0x1801028ca  test    rdi, rdi
0x1801028cd  jz      short loc_180102931
0x1801028cf  cmp     rdi, 7FFFFFFFh
0x1801028d6  ja      short loc_18010292D
0x1801028d8  mov     eax, 7FFFFFFEh
0x1801028dd  mov     r8, rdi
0x1801028e0  test    rax, rax
0x1801028e3  jz      short loc_180102901
0x1801028e5  movzx   ecx, word ptr [rsi]
0x1801028e8  test    cx, cx
0x1801028eb  jz      short loc_180102901
0x1801028ed  mov     [rdx], cx
0x1801028f0  add     rsi, 2
0x1801028f4  add     rdx, 2
0x1801028f8  dec     rax
0x1801028fb  sub     r8, 1
0x1801028ff  jnz     short loc_1801028E0
0x180102901  mov     rax, r8
0x180102904  lea     rcx, [rdx-2]
0x180102908  neg     rax
0x18010290b  sbb     ebx, ebx
0x18010290d  not     ebx
0x18010290f  and     ebx, 8007007Ah
0x180102915  test    r8, r8
0x180102918  cmovnz  rcx, rdx
0x18010291c  mov     [rcx], r15w
0x180102920  jz      short loc_180102931
0x180102922  mov     [r14+8], rdi
0x180102926  xor     eax, eax
0x180102928  jmp     loc_180102885
0x18010292d  mov     [rdx], r15w
0x180102931  mov     rcx, [rsp+58h]; this
0x180102936  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\staterepositor"...
0x18010293d  mov     r9d, ebx; char *
0x180102940  mov     edx, 1Eh; void *
0x180102945  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
