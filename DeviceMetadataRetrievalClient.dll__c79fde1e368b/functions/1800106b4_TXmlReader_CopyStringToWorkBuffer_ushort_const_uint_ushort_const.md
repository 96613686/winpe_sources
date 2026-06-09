# TXmlReader::CopyStringToWorkBuffer(ushort const *,uint,ushort const * *)

- ea: `0x1800106b4`
- end: `0x1800107db`
- name: `?CopyStringToWorkBuffer@TXmlReader@@IEAAJPEBGIPEAPEBG@Z`
- size: `295`
- prototype: `__int64 __fastcall(TXmlReader *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180010a84`

## callees

- `0x1800106b4`

## import_xrefs

- `msvcrt!malloc` at `0x18001072f`
- `msvcrt!malloc` at `0x18001072f`
- `msvcrt!free` at `0x180010716`
- `msvcrt!free` at `0x180010716`

## pseudocode

```c
__int64 __fastcall TXmlReader::CopyStringToWorkBuffer(
        TXmlReader *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 **a4)
{
  unsigned __int64 v7; // rcx
  size_t v8; // rbx
  unsigned int v9; // ecx
  void *v10; // rcx
  void *v11; // rax
  unsigned __int64 v12; // rbx
  _WORD *v13; // rdx
  __int64 v14; // rax
  _WORD *v15; // rcx
  unsigned int v16; // eax

  *a4 = 0;
  v7 = a3 + 1LL;
  if ( v7 < a3 )
    return (unsigned int)-2147024362;
  v8 = 2 * v7;
  if ( is_mul_ok(v7, 2u) )
  {
    v9 = 0;
  }
  else
  {
    v8 = -1;
    v9 = -2147024362;
  }
  if ( !v9 )
  {
    if ( v8 <= *((_QWORD *)this + 2) )
    {
      v8 = *((_QWORD *)this + 2);
    }
    else
    {
      v10 = (void *)*((_QWORD *)this + 1);
      if ( v10 )
        free(v10);
      *((_QWORD *)this + 2) = 0;
      if ( v8 < 0x400 )
        v8 = 1024;
      v11 = malloc(v8);
      *((_QWORD *)this + 1) = v11;
      if ( !v11 )
        return (unsigned int)-2147024882;
      *((_QWORD *)this + 2) = v8;
    }
    v12 = v8 >> 1;
    v9 = -2147024809;
    v13 = (_WORD *)*((_QWORD *)this + 1);
    if ( v12 )
    {
      if ( v12 > 0x7FFFFFFF )
      {
        *v13 = 0;
        return v9;
      }
      v14 = 2147483646;
      do
      {
        if ( !v14 )
          break;
        if ( !*a2 )
          break;
        *v13++ = *a2++;
        --v14;
        --v12;
      }
      while ( v12 );
      v15 = v13 - 1;
      if ( v12 )
        v15 = v13;
      v16 = v12 == 0 ? 0x8007007A : 0;
      *v15 = 0;
    }
    else
    {
      v16 = -2147024809;
    }
    v9 = v16;
    if ( !v16 )
      *a4 = (const unsigned __int16 *)*((_QWORD *)this + 1);
  }
  return v9;
}

```

## disassembly

```asm
0x1800106b4  mov     [rsp+arg_0], rbx
0x1800106b9  mov     [rsp+arg_8], rbp
0x1800106be  push    rsi
0x1800106bf  push    rdi
0x1800106c0  push    r14
0x1800106c2  sub     rsp, 20h
0x1800106c6  mov     eax, r8d
0x1800106c9  xor     ebp, ebp
0x1800106cb  mov     rdi, rcx
0x1800106ce  mov     [r9], rbp
0x1800106d1  mov     r14, r9
0x1800106d4  mov     rsi, rdx
0x1800106d7  lea     rcx, [rax+1]
0x1800106db  cmp     rcx, rax
0x1800106de  jb      loc_1800107C1
0x1800106e4  lea     eax, [rbp+2]
0x1800106e7  mul     rcx
0x1800106ea  mov     rbx, rax
0x1800106ed  test    rdx, rdx
0x1800106f0  jnz     short loc_1800106F6
0x1800106f2  mov     ecx, ebp
0x1800106f4  jmp     short loc_1800106FF
0x1800106f6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800106fa  mov     ecx, 80070216h
0x1800106ff  test    ecx, ecx
0x180010701  jnz     loc_1800107C6
0x180010707  cmp     rbx, [rdi+10h]
0x18001070b  jbe     short loc_18001074B
0x18001070d  mov     rcx, [rdi+8]; Block
0x180010711  test    rcx, rcx
0x180010714  jz      short loc_18001071C
0x180010716  call    cs:__imp_free
0x18001071c  mov     eax, 400h
0x180010721  mov     [rdi+10h], rbp
0x180010725  cmp     rbx, rax
0x180010728  cmovb   rbx, rax
0x18001072c  mov     rcx, rbx; Size
0x18001072f  call    cs:__imp_malloc
0x180010735  mov     [rdi+8], rax
0x180010739  test    rax, rax
0x18001073c  jz      short loc_180010744
0x18001073e  mov     [rdi+10h], rbx
0x180010742  jmp     short loc_18001074F
0x180010744  mov     ecx, 8007000Eh
0x180010749  jmp     short loc_1800107C6
0x18001074b  mov     rbx, [rdi+10h]
0x18001074f  shr     rbx, 1
0x180010752  mov     ecx, 80070057h
0x180010757  mov     rdx, [rdi+8]
0x18001075b  jz      short loc_1800107B5
0x18001075d  cmp     rbx, 7FFFFFFFh
0x180010764  ja      short loc_1800107BC
0x180010766  mov     eax, 7FFFFFFEh
0x18001076b  test    rax, rax
0x18001076e  jz      short loc_18001078C
0x180010770  movzx   ecx, word ptr [rsi]
0x180010773  test    cx, cx
0x180010776  jz      short loc_18001078C
0x180010778  mov     [rdx], cx
0x18001077b  add     rsi, 2
0x18001077f  add     rdx, 2
0x180010783  dec     rax
0x180010786  sub     rbx, 1
0x18001078a  jnz     short loc_18001076B
0x18001078c  test    rbx, rbx
0x18001078f  lea     rcx, [rdx-2]
0x180010793  cmovnz  rcx, rdx
0x180010797  neg     rbx
0x18001079a  sbb     eax, eax
0x18001079c  not     eax
0x18001079e  and     eax, 8007007Ah
0x1800107a3  mov     [rcx], bp
0x1800107a6  mov     ecx, eax
0x1800107a8  test    eax, eax
0x1800107aa  jnz     short loc_1800107C6
0x1800107ac  mov     rax, [rdi+8]
0x1800107b0  mov     [r14], rax
0x1800107b3  jmp     short loc_1800107C6
0x1800107b5  mov     eax, ecx
0x1800107b7  test    rbx, rbx
0x1800107ba  jz      short loc_1800107A6
0x1800107bc  mov     [rdx], bp
0x1800107bf  jmp     short loc_1800107C6
0x1800107c1  mov     ecx, 80070216h
0x1800107c6  mov     rbx, [rsp+38h+arg_0]
0x1800107cb  mov     eax, ecx
0x1800107cd  mov     rbp, [rsp+38h+arg_8]
0x1800107d2  add     rsp, 20h
0x1800107d6  pop     r14
0x1800107d8  pop     rdi
0x1800107d9  pop     rsi
0x1800107da  retn
```
