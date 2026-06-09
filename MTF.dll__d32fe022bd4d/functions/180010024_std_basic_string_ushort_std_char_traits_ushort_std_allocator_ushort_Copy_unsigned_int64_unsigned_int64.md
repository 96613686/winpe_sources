# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180010024`
- end: `0x180010137`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `275`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800101a4`
- `0x18001031c`
- `0x18002b48c`
- `0x18002b58c`

## callees

- `0x180001fc4`
- `0x1800021c8`
- `0x180002966`
- `0x180010024`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180010103`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010103`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Copy(const void **Src, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // r14
  const void *v11; // rdx
  _QWORD *result; // rax
  void *v13; // rax
  unsigned __int64 v14; // rcx
  __int64 *v15; // rdx
  __int64 v16; // [rsp+0h] [rbp-48h] BYREF
  void *v20; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    if ( v7 >> 1 > v6 / 3 )
    {
      v4 = v8 + v7;
      if ( v7 > 0x7FFFFFFFFFFFFFFELL - v8 )
        v4 = 0x7FFFFFFFFFFFFFFELL;
    }
  }
  try
  {
    v9 = v4 + 1;
    if ( v4 == -1 )
    {
      v10 = 0;
    }
    else if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0 )
    {
      std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
    try
    {
      v13 = 0;
      v14 = a2 + 1;
      if ( a2 != -1 && (v14 > 0x7FFFFFFFFFFFFFFFLL || (v13 = operator new(2 * v14)) == 0) )
        std::_Xbad_alloc();
      v20 = v13;
    }
    catch ( ... )
    {
      v15 = &v16;
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(Src, v15, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v10 = v20;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 8 )
      v11 = v5;
    else
      v11 = *v5;
    memcpy_0(v10, v11, 2 * v3);
  }
  if ( (unsigned __int64)v5[3] >= 8 )
    operator delete((void *)*v5);
  result = v5 + 2;
  *v5 = v10;
  v5[3] = (const void *)v4;
  if ( v4 >= 8 )
    v5 = (const void **)v10;
  *result = v3;
  *((_WORD *)v5 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x180010024  mov     [rsp+arg_10], r8
0x180010029  mov     [rsp+arg_8], rdx
0x18001002e  mov     [rsp+arg_0], rcx
0x180010033  push    rbx
0x180010034  push    rsi
0x180010035  push    rdi
0x180010036  push    r14
0x180010038  push    r15
0x18001003a  sub     rsp, 20h
0x18001003e  mov     r15, r8
0x180010041  mov     rdi, rdx
0x180010044  mov     rbx, rcx
0x180010047  or      rdx, 7
0x18001004b  mov     r9, 7FFFFFFFFFFFFFFEh
0x180010055  cmp     rdx, r9
0x180010058  ja      short loc_18001008E
0x18001005a  mov     rdi, rdx
0x18001005d  mov     r8, [rcx+18h]
0x180010061  mov     rcx, r8
0x180010064  shr     rcx, 1
0x180010067  mov     rax, 0AAAAAAAAAAAAAAABh
0x180010071  mul     rdx
0x180010074  shr     rdx, 1
0x180010077  cmp     rcx, rdx
0x18001007a  jbe     short loc_18001008E
0x18001007c  mov     rax, r9
0x18001007f  sub     rax, rcx
0x180010082  cmp     r8, rax
0x180010085  lea     rdi, [rcx+r8]
0x180010089  jbe     short loc_18001008E
0x18001008b  mov     rdi, r9
0x18001008e  lea     rcx, [rdi+1]
0x180010092  xor     esi, esi
0x180010094  test    rcx, rcx
0x180010097  jz      short loc_1800100BE
0x180010099  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800100a3  cmp     rcx, rax
0x1800100a6  ja      loc_180010130
0x1800100ac  add     rcx, rcx; Size
0x1800100af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800100b4  mov     r14, rax
0x1800100b7  test    rax, rax
0x1800100ba  jz      short loc_180010130
0x1800100bc  jmp     short loc_1800100C1
0x1800100be  mov     r14, rsi
0x1800100c1  jmp     short loc_1800100D9
0x1800100c3  xor     esi, esi
0x1800100c5  mov     rbx, [rsp+48h+arg_0]
0x1800100ca  mov     r15, [rsp+48h+arg_10]
0x1800100cf  mov     rdi, [rsp+48h+arg_8]
0x1800100d4  mov     r14, [rsp+48h+arg_18]
0x1800100d9  test    r15, r15
0x1800100dc  jz      short loc_1800100F9
0x1800100de  cmp     qword ptr [rbx+18h], 8
0x1800100e3  jb      short loc_1800100EA
0x1800100e5  mov     rdx, [rbx]
0x1800100e8  jmp     short loc_1800100ED
0x1800100ea  mov     rdx, rbx; Src
0x1800100ed  lea     r8, [r15+r15]; Size
0x1800100f1  mov     rcx, r14; void *
0x1800100f4  call    memcpy_0
0x1800100f9  cmp     qword ptr [rbx+18h], 8
0x1800100fe  jb      short loc_180010109
0x180010100  mov     rcx, [rbx]
0x180010103  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010109  lea     rax, [rbx+10h]
0x18001010d  mov     [rbx], r14
0x180010110  mov     [rbx+18h], rdi
0x180010114  cmp     rdi, 8
0x180010118  cmovnb  rbx, r14
0x18001011c  mov     [rax], r15
0x18001011f  mov     [rbx+r15*2], si
0x180010124  add     rsp, 20h
0x180010128  pop     r15
0x18001012a  pop     r14
0x18001012c  pop     rdi
0x18001012d  pop     rsi
0x18001012e  pop     rbx
0x18001012f  retn
0x180010130  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
