# LexicalAnalyzer::TryTokenizeAsLiteral(SymbolType *,ulong *,bool *)

- ea: `0x18000e1c0`
- end: `0x18000e263`
- name: `?TryTokenizeAsLiteral@LexicalAnalyzer@@QEAAJPEAW4SymbolType@@PEAKPEA_N@Z`
- size: `163`
- prototype: `__int64 __fastcall(LexicalAnalyzer *__hidden this, enum SymbolType *, unsigned int *, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dc40`

## callees

- `0x18000a3a8`
- `0x18000e1c0`

## pseudocode

```c
__int64 __fastcall LexicalAnalyzer::TryTokenizeAsLiteral(
        LexicalAnalyzer *this,
        enum SymbolType *a2,
        unsigned int *a3,
        bool *a4)
{
  _WORD *v5; // rdx
  __int16 *v8; // rax
  unsigned int v9; // r8d
  __int16 v10; // cx
  struct String *v12; // rcx
  const unsigned __int16 *v13; // rax
  int v14; // eax
  unsigned int v15; // ecx

  v5 = (_WORD *)*((_QWORD *)this + 4);
  *a4 = 0;
  if ( *v5 != 34 && *v5 != 39 )
    return 0;
  v8 = v5 + 1;
  v9 = 1;
  v10 = v5[1];
  if ( v10 )
  {
    do
    {
      if ( v10 == *v5 )
        break;
      ++v8;
      ++v9;
      v10 = *v8;
    }
    while ( *v8 );
    if ( *v8 )
    {
      *(_DWORD *)a2 = 36;
      *a3 = v9 + 1;
      *a4 = 1;
      return 0;
    }
  }
  v12 = (LexicalAnalyzer *)((char *)this + 24);
  v13 = &qword_180016F98;
  if ( *((_QWORD *)this + 3) )
    v13 = *(const unsigned __int16 **)v12;
  v14 = ExceptionHelpers::SetCompilationException(v12, v5 - v13, v9, 0x6Au);
  v15 = -2147024809;
  if ( v14 < 0 )
    return (unsigned int)v14;
  return v15;
}

```

## disassembly

```asm
0x18000e1c0  mov     [rsp+arg_0], rbx
0x18000e1c5  push    rdi
0x18000e1c6  sub     rsp, 20h
0x18000e1ca  xor     edi, edi
0x18000e1cc  mov     r11, rdx
0x18000e1cf  mov     rdx, [rcx+20h]
0x18000e1d3  mov     r10, r8
0x18000e1d6  mov     rbx, rcx
0x18000e1d9  mov     [r9], dil
0x18000e1dc  cmp     word ptr [rdx], 22h ; '"'
0x18000e1e0  jz      short loc_18000E1E8
0x18000e1e2  cmp     word ptr [rdx], 27h ; '''
0x18000e1e6  jnz     short loc_18000E225
0x18000e1e8  lea     rax, [rdx+2]
0x18000e1ec  mov     r8d, 1; unsigned int
0x18000e1f2  movzx   ecx, word ptr [rax]
0x18000e1f5  test    cx, cx
0x18000e1f8  jz      short loc_18000E229
0x18000e1fa  cmp     cx, [rdx]
0x18000e1fd  jz      short loc_18000E20E
0x18000e1ff  add     rax, 2
0x18000e203  inc     r8d
0x18000e206  movzx   ecx, word ptr [rax]
0x18000e209  test    cx, cx
0x18000e20c  jnz     short loc_18000E1FA
0x18000e20e  cmp     [rax], di
0x18000e211  jz      short loc_18000E229
0x18000e213  lea     eax, [r8+1]
0x18000e217  mov     dword ptr [r11], 24h ; '$'
0x18000e21e  mov     [r10], eax
0x18000e221  mov     byte ptr [r9], 1
0x18000e225  xor     eax, eax
0x18000e227  jmp     short loc_18000E258
0x18000e229  lea     rcx, [rbx+18h]; struct String *
0x18000e22d  mov     r9d, 6Ah ; 'j'; unsigned int
0x18000e233  cmp     [rcx], rdi
0x18000e236  lea     rax, qword_180016F98
0x18000e23d  cmovnz  rax, [rcx]
0x18000e241  sub     rdx, rax
0x18000e244  sar     rdx, 1; unsigned int
0x18000e247  call    ?SetCompilationException@ExceptionHelpers@@SAJAEAVString@@KKI@Z; ExceptionHelpers::SetCompilationException(String &,ulong,ulong,uint)
0x18000e24c  test    eax, eax
0x18000e24e  mov     ecx, 80070057h
0x18000e253  cmovs   ecx, eax
0x18000e256  mov     eax, ecx
0x18000e258  mov     rbx, [rsp+28h+arg_0]
0x18000e25d  add     rsp, 20h
0x18000e261  pop     rdi
0x18000e262  retn
```
