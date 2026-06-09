# StateRepository::Text::Append(ushort const *,unsigned __int64)

- ea: `0x180014728`
- end: `0x18001480c`
- name: `?Append@Text@StateRepository@@QEAAJPEBG_K@Z`
- size: `228`
- prototype: `int(StateRepository::Text *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800146fc`
- `0x1800232c8`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x180014728`
- `0x180014814`
- `0x1800149f4`
- `0x180014abc`
- `0x180014ca0`

## string_xrefs

- `0x180014756`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x1800147aa`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x1800147f7`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`

## pseudocode

```c
int __fastcall StateRepository::Text::Append(
        StateRepository::Text *this,
        const unsigned __int16 *a2,
        unsigned __int64 a3)
{
  __int64 v7; // rdi
  unsigned __int64 v8; // r15
  int v9; // eax
  int v10; // r14d
  int v11; // eax
  int v12; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a3 )
  {
    if ( a2 )
    {
      if ( !*(_QWORD *)this )
        return StateRepository::Text::SetFromChars(this, a2, a3);
      v7 = -1;
      do
        ++v7;
      while ( *(_WORD *)(*(_QWORD *)this + 2 * v7) );
      v8 = v7 + a3 + 1;
      v9 = StateRepository::Text::EnsureCapacity(this, v8, 1);
      v10 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDB,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
          (const char *)(unsigned int)v9,
          v12);
        return v10;
      }
      v11 = StringCchCatNW((unsigned __int16 *)(*(_QWORD *)this + 2 * v7), a3 + 1, a2, a3);
      if ( v11 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0xDC,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
          (const char *)(unsigned int)v11,
          v12);
      *((_QWORD *)this + 1) = v8;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD1,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
        (const char *)0x80070057LL,
        v12);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180014728  push    rbx
0x18001472a  push    rbp
0x18001472b  push    rsi
0x18001472c  push    rdi
0x18001472d  push    r12
0x18001472f  push    r14
0x180014731  push    r15; int
0x180014733  sub     rsp, 20h
0x180014737  xor     r12d, r12d
0x18001473a  mov     rsi, r8
0x18001473d  mov     rbp, rdx
0x180014740  mov     rbx, rcx
0x180014743  test    r8, r8
0x180014746  jz      loc_1800147E1
0x18001474c  test    rdx, rdx
0x18001474f  jnz     short loc_18001476F
0x180014751  mov     rcx, [rsp+58h]; this
0x180014756  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\staterepositor"...
0x18001475d  mov     r9d, 80070057h; char *
0x180014763  mov     edx, 0D1h; void *
0x180014768  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001476d  jmp     short loc_1800147E1
0x18001476f  mov     rax, [rcx]
0x180014772  test    rax, rax
0x180014775  jnz     short loc_18001477E
0x180014777  call    ?SetFromChars@Text@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Text::SetFromChars(ushort const *,unsigned __int64)
0x18001477c  jmp     short loc_1800147E3
0x18001477e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180014782  inc     rdi
0x180014785  cmp     [rax+rdi*2], r12w
0x18001478a  jnz     short loc_180014782
0x18001478c  lea     r15, [r8+1]
0x180014790  mov     r8b, 1; bool
0x180014793  add     r15, rdi
0x180014796  mov     rdx, r15; unsigned __int64
0x180014799  call    ?EnsureCapacity@Text@StateRepository@@QEAAJ_K_N@Z; StateRepository::Text::EnsureCapacity(unsigned __int64,bool)
0x18001479e  mov     r14d, eax
0x1800147a1  test    eax, eax
0x1800147a3  jns     short loc_1800147C3
0x1800147a5  mov     rcx, [rsp+58h]; this
0x1800147aa  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\staterepositor"...
0x1800147b1  mov     r9d, eax; char *
0x1800147b4  mov     edx, 0DBh; void *
0x1800147b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800147be  mov     eax, r14d
0x1800147c1  jmp     short loc_1800147E3
0x1800147c3  mov     rax, [rbx]
0x1800147c6  lea     rdx, [rsi+1]; unsigned __int64
0x1800147ca  mov     r9, rsi; unsigned __int64
0x1800147cd  mov     r8, rbp; unsigned __int16 *
0x1800147d0  lea     rcx, [rax+rdi*2]; unsigned __int16 *
0x1800147d4  call    ?StringCchCatNW@@YAJPEAG_KPEBG1@Z; StringCchCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800147d9  test    eax, eax
0x1800147db  js      short loc_1800147F2
0x1800147dd  mov     [rbx+8], r15
0x1800147e1  xor     eax, eax
0x1800147e3  add     rsp, 20h
0x1800147e7  pop     r15
0x1800147e9  pop     r14
0x1800147eb  pop     r12
0x1800147ed  pop     rdi
0x1800147ee  pop     rsi
0x1800147ef  pop     rbp
0x1800147f0  pop     rbx
0x1800147f1  retn
0x1800147f2  mov     rcx, [rsp+58h]; this
0x1800147f7  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\staterepositor"...
0x1800147fe  mov     r9d, eax; char *
0x180014801  mov     edx, 0DCh; void *
0x180014806  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
