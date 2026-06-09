# tson::output_archive::write_name(bool)

- ea: `0x18000f168`
- end: `0x18000f2a0`
- name: `?write_name@output_archive@tson@@AEAA_N_N@Z`
- size: `312`
- prototype: `char __fastcall(tson::output_archive *this, char)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ef58`
- `0x18000f358`

## callees

- `0x18000ab88`
- `0x18000e17c`
- `0x18000f168`

## pseudocode

```c
char __fastcall tson::output_archive::write_name(tson::output_archive *this, char a2)
{
  char *v2; // rsi
  __int64 v4; // rax
  tson::write_buffer *v6; // rcx
  tson::write_buffer *v7; // rcx
  tson::write_buffer *v8; // rcx
  _BYTE *v10; // rbx
  tson::write_buffer *v11; // rcx
  char v12; // [rsp+50h] [rbp+8h] BYREF

  v2 = (char *)this + 24;
  v4 = *((_QWORD *)this + 16);
  if ( v4 )
    v2 = &v2[4 * v4 - 4];
  else
    *v2 = 1;
  if ( *((_DWORD *)v2 + 1) == 2 )
  {
    *((_DWORD *)v2 + 1) = 3;
    v6 = (tson::write_buffer *)*((_QWORD *)this + 18);
    v12 = 3;
    tson::write_buffer::push_back<unsigned char>(v6, &v12);
    tson::write_buffer::push_back(*((void ***)this + 18), (char *)this + 10, 2u);
    *((_WORD *)this + 5) = 0;
  }
  else if ( !*((_DWORD *)v2 + 1) )
  {
    *((_DWORD *)v2 + 1) = 1;
    v7 = (tson::write_buffer *)*((_QWORD *)this + 18);
    v12 = 1;
    tson::write_buffer::push_back<unsigned char>(v7, &v12);
  }
  *((_QWORD *)this + 2) = 0;
  if ( *((_DWORD *)v2 + 1) != 3 )
  {
    if ( a2 )
    {
      v8 = (tson::write_buffer *)*((_QWORD *)this + 18);
      *(_QWORD *)this = 0;
      v12 = 6;
      tson::write_buffer::push_back<unsigned char>(v8, &v12);
      return 0;
    }
    v10 = (char *)this + 8;
    if ( !*(_QWORD *)this )
    {
      *v10 = 1;
      *(_QWORD *)this = "-";
    }
    v11 = (tson::write_buffer *)*((_QWORD *)this + 18);
    v12 = 5;
    *((_QWORD *)this + 2) = *((_QWORD *)v11 + 259) - *((_QWORD *)v11 + 258);
    tson::write_buffer::push_back<unsigned char>(v11, &v12);
    tson::write_buffer::push_back<unsigned char>(*((tson::write_buffer **)this + 18), (_BYTE *)this + 8);
    tson::write_buffer::push_back(*((void ***)this + 18), *(const void **)this, (unsigned __int8)*v10);
    *(_QWORD *)this = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000f168  push    rbx
0x18000f16a  push    rbp
0x18000f16b  push    rsi
0x18000f16c  push    rdi
0x18000f16d  sub     rsp, 28h
0x18000f171  lea     rsi, [rcx+18h]
0x18000f175  mov     bpl, dl
0x18000f178  mov     rax, [rsi+68h]
0x18000f17c  mov     rdi, rcx
0x18000f17f  test    rax, rax
0x18000f182  jz      short loc_18000F18E
0x18000f184  lea     rsi, [rsi+rax*4]
0x18000f188  add     rsi, 0FFFFFFFFFFFFFFFCh
0x18000f18c  jmp     short loc_18000F191
0x18000f18e  mov     byte ptr [rsi], 1
0x18000f191  cmp     dword ptr [rsi+4], 2
0x18000f195  jnz     short loc_18000F1D2
0x18000f197  mov     dword ptr [rsi+4], 3
0x18000f19e  lea     rdx, [rsp+48h+arg_0]
0x18000f1a3  mov     rcx, [rcx+90h]
0x18000f1aa  mov     [rsp+48h+arg_0], 3
0x18000f1af  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000f1b4  mov     rcx, [rdi+90h]; this
0x18000f1bb  lea     rdx, [rdi+0Ah]; void *
0x18000f1bf  mov     r8d, 2; unsigned __int64
0x18000f1c5  call    ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
0x18000f1ca  xor     eax, eax
0x18000f1cc  mov     [rdi+0Ah], ax
0x18000f1d0  jmp     short loc_18000F1F5
0x18000f1d2  cmp     dword ptr [rsi+4], 0
0x18000f1d6  jnz     short loc_18000F1F5
0x18000f1d8  mov     dword ptr [rsi+4], 1
0x18000f1df  lea     rdx, [rsp+48h+arg_0]
0x18000f1e4  mov     rcx, [rcx+90h]
0x18000f1eb  mov     [rsp+48h+arg_0], 1
0x18000f1f0  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000f1f5  mov     qword ptr [rdi+10h], 0
0x18000f1fd  cmp     dword ptr [rsi+4], 3
0x18000f201  jz      loc_18000F295
0x18000f207  test    bpl, bpl
0x18000f20a  jz      short loc_18000F22D
0x18000f20c  mov     rcx, [rdi+90h]
0x18000f213  lea     rdx, [rsp+48h+arg_0]
0x18000f218  mov     qword ptr [rdi], 0
0x18000f21f  mov     [rsp+48h+arg_0], 6
0x18000f224  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000f229  xor     al, al
0x18000f22b  jmp     short loc_18000F297
0x18000f22d  cmp     qword ptr [rdi], 0
0x18000f231  lea     rbx, [rdi+8]
0x18000f235  jnz     short loc_18000F244
0x18000f237  lea     rax, asc_180016DDC; "-"
0x18000f23e  mov     byte ptr [rbx], 1
0x18000f241  mov     [rdi], rax
0x18000f244  mov     rcx, [rdi+90h]
0x18000f24b  lea     rdx, [rsp+48h+arg_0]
0x18000f250  mov     [rsp+48h+arg_0], 5
0x18000f255  mov     rax, [rcx+818h]
0x18000f25c  sub     rax, [rcx+810h]
0x18000f263  mov     [rdi+10h], rax
0x18000f267  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000f26c  mov     rcx, [rdi+90h]
0x18000f273  mov     rdx, rbx
0x18000f276  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000f27b  movzx   r8d, byte ptr [rbx]; unsigned __int64
0x18000f27f  mov     rdx, [rdi]; void *
0x18000f282  mov     rcx, [rdi+90h]; this
0x18000f289  call    ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
0x18000f28e  mov     qword ptr [rdi], 0
0x18000f295  mov     al, 1
0x18000f297  add     rsp, 28h
0x18000f29b  pop     rdi
0x18000f29c  pop     rsi
0x18000f29d  pop     rbp
0x18000f29e  pop     rbx
0x18000f29f  retn
```
