# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1400085ec`
- end: `0x1400086d9`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `237`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1400032f4`

## callees

- `0x140001674`
- `0x1400085ec`
- `0x14000de86`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x140008667`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x140008667`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400086ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400086ae`

## pseudocode

```c
size_t *__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // r14
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  void *v9; // rsi
  const void *v10; // rdx
  size_t *result; // rax
  void *v12; // rax
  __int64 *v13; // rdx
  __int64 v14; // [rsp+0h] [rbp-48h] BYREF
  void *v18; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    if ( v7 >> 1 > v6 / 3 )
    {
      v4 = v8 + v7;
      if ( v7 > -2LL - v8 )
        v4 = -2;
    }
  }
  try
  {
    if ( v4 != -1 )
    {
      v9 = operator new(v4 + 1);
      if ( v9 )
        goto LABEL_31;
      std::_Xbad_alloc();
    }
    v9 = 0;
  }
  catch ( ... )
  {
    try
    {
      v12 = 0;
      if ( a2 != -1 )
      {
        v12 = operator new(a2 + 1);
        if ( !v12 )
          std::_Xbad_alloc();
      }
      v18 = v12;
    }
    catch ( ... )
    {
      v13 = &v14;
      LOBYTE(v13) = 1;
      std::string::_Tidy(Src, v13, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v9 = v18;
  }
LABEL_31:
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v10 = v5;
    else
      v10 = *v5;
    memcpy_0(v9, v10, v3);
  }
  if ( (unsigned __int64)v5[3] >= 0x10 )
    operator delete((void *)*v5);
  result = (size_t *)(v5 + 2);
  *v5 = v9;
  v5[3] = (const void *)v4;
  if ( v4 >= 0x10 )
    v5 = (const void **)v9;
  *result = v3;
  *((_BYTE *)v5 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x1400085ec  mov     [rsp+arg_10], r8
0x1400085f1  mov     [rsp+arg_8], rdx
0x1400085f6  mov     [rsp+arg_0], rcx
0x1400085fb  push    rbx
0x1400085fc  push    rsi
0x1400085fd  push    rdi
0x1400085fe  push    r14
0x140008600  sub     rsp, 28h
0x140008604  mov     r14, r8
0x140008607  mov     rdi, rdx
0x14000860a  mov     rbx, rcx
0x14000860d  or      rdx, 0Fh
0x140008611  mov     r9, 0FFFFFFFFFFFFFFFEh
0x140008618  cmp     rdx, r9
0x14000861b  ja      short loc_140008651
0x14000861d  mov     rdi, rdx
0x140008620  mov     r8, [rcx+18h]
0x140008624  mov     rcx, r8
0x140008627  shr     rcx, 1
0x14000862a  mov     rax, 0AAAAAAAAAAAAAAABh
0x140008634  mul     rdx
0x140008637  shr     rdx, 1
0x14000863a  cmp     rcx, rdx
0x14000863d  jbe     short loc_140008651
0x14000863f  mov     rax, r9
0x140008642  sub     rax, rcx
0x140008645  cmp     r8, rax
0x140008648  lea     rdi, [rcx+r8]
0x14000864c  jbe     short loc_140008651
0x14000864e  mov     rdi, r9
0x140008651  lea     rcx, [rdi+1]; Size
0x140008655  test    rcx, rcx
0x140008658  jz      short loc_14000866D
0x14000865a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000865f  mov     rsi, rax
0x140008662  test    rax, rax
0x140008665  jnz     short loc_14000866F
0x140008667  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x14000866d  xor     esi, esi
0x14000866f  jmp     short loc_140008685
0x140008671  mov     rbx, [rsp+48h+arg_0]
0x140008676  mov     r14, [rsp+48h+arg_10]
0x14000867b  mov     rdi, [rsp+48h+arg_8]
0x140008680  mov     rsi, [rsp+48h+arg_18]
0x140008685  test    r14, r14
0x140008688  jz      short loc_1400086A4
0x14000868a  cmp     qword ptr [rbx+18h], 10h
0x14000868f  jb      short loc_140008696
0x140008691  mov     rdx, [rbx]
0x140008694  jmp     short loc_140008699
0x140008696  mov     rdx, rbx; Src
0x140008699  mov     r8, r14; Size
0x14000869c  mov     rcx, rsi; void *
0x14000869f  call    memcpy_0
0x1400086a4  cmp     qword ptr [rbx+18h], 10h
0x1400086a9  jb      short loc_1400086B4
0x1400086ab  mov     rcx, [rbx]
0x1400086ae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400086b4  lea     rax, [rbx+10h]
0x1400086b8  mov     [rbx], rsi
0x1400086bb  mov     [rbx+18h], rdi
0x1400086bf  cmp     rdi, 10h
0x1400086c3  cmovnb  rbx, rsi
0x1400086c7  mov     [rax], r14
0x1400086ca  mov     byte ptr [rbx+r14], 0
0x1400086cf  add     rsp, 28h
0x1400086d3  pop     r14
0x1400086d5  pop     rdi
0x1400086d6  pop     rsi
0x1400086d7  pop     rbx
0x1400086d8  retn
```
