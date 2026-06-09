# tson::output_archive::write_name(bool)

- ea: `0x18000e734`
- end: `0x18000e86c`
- name: `?write_name@output_archive@tson@@AEAA_N_N@Z`
- size: `312`
- prototype: `char __fastcall(tson::output_archive *this, char)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e698`
- `0x18000e924`

## callees

- `0x18000ae94`
- `0x18000dc18`
- `0x18000e734`

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
0x18000e734  push    rbx
0x18000e736  push    rbp
0x18000e737  push    rsi
0x18000e738  push    rdi
0x18000e739  sub     rsp, 28h
0x18000e73d  lea     rsi, [rcx+18h]
0x18000e741  mov     bpl, dl
0x18000e744  mov     rax, [rsi+68h]
0x18000e748  mov     rdi, rcx
0x18000e74b  test    rax, rax
0x18000e74e  jz      short loc_18000E75A
0x18000e750  lea     rsi, [rsi+rax*4]
0x18000e754  add     rsi, 0FFFFFFFFFFFFFFFCh
0x18000e758  jmp     short loc_18000E75D
0x18000e75a  mov     byte ptr [rsi], 1
0x18000e75d  cmp     dword ptr [rsi+4], 2
0x18000e761  jnz     short loc_18000E79E
0x18000e763  mov     dword ptr [rsi+4], 3
0x18000e76a  lea     rdx, [rsp+48h+arg_0]
0x18000e76f  mov     rcx, [rcx+90h]
0x18000e776  mov     [rsp+48h+arg_0], 3
0x18000e77b  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000e780  mov     rcx, [rdi+90h]; this
0x18000e787  lea     rdx, [rdi+0Ah]; void *
0x18000e78b  mov     r8d, 2; unsigned __int64
0x18000e791  call    ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
0x18000e796  xor     eax, eax
0x18000e798  mov     [rdi+0Ah], ax
0x18000e79c  jmp     short loc_18000E7C1
0x18000e79e  cmp     dword ptr [rsi+4], 0
0x18000e7a2  jnz     short loc_18000E7C1
0x18000e7a4  mov     dword ptr [rsi+4], 1
0x18000e7ab  lea     rdx, [rsp+48h+arg_0]
0x18000e7b0  mov     rcx, [rcx+90h]
0x18000e7b7  mov     [rsp+48h+arg_0], 1
0x18000e7bc  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000e7c1  mov     qword ptr [rdi+10h], 0
0x18000e7c9  cmp     dword ptr [rsi+4], 3
0x18000e7cd  jz      loc_18000E861
0x18000e7d3  test    bpl, bpl
0x18000e7d6  jz      short loc_18000E7F9
0x18000e7d8  mov     rcx, [rdi+90h]
0x18000e7df  lea     rdx, [rsp+48h+arg_0]
0x18000e7e4  mov     qword ptr [rdi], 0
0x18000e7eb  mov     [rsp+48h+arg_0], 6
0x18000e7f0  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000e7f5  xor     al, al
0x18000e7f7  jmp     short loc_18000E863
0x18000e7f9  cmp     qword ptr [rdi], 0
0x18000e7fd  lea     rbx, [rdi+8]
0x18000e801  jnz     short loc_18000E810
0x18000e803  lea     rax, asc_18001E808; "-"
0x18000e80a  mov     byte ptr [rbx], 1
0x18000e80d  mov     [rdi], rax
0x18000e810  mov     rcx, [rdi+90h]
0x18000e817  lea     rdx, [rsp+48h+arg_0]
0x18000e81c  mov     [rsp+48h+arg_0], 5
0x18000e821  mov     rax, [rcx+818h]
0x18000e828  sub     rax, [rcx+810h]
0x18000e82f  mov     [rdi+10h], rax
0x18000e833  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000e838  mov     rcx, [rdi+90h]
0x18000e83f  mov     rdx, rbx
0x18000e842  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000e847  movzx   r8d, byte ptr [rbx]; unsigned __int64
0x18000e84b  mov     rdx, [rdi]; void *
0x18000e84e  mov     rcx, [rdi+90h]; this
0x18000e855  call    ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
0x18000e85a  mov     qword ptr [rdi], 0
0x18000e861  mov     al, 1
0x18000e863  add     rsp, 28h
0x18000e867  pop     rdi
0x18000e868  pop     rsi
0x18000e869  pop     rbp
0x18000e86a  pop     rbx
0x18000e86b  retn
```
