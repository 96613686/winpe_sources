# tson::output_archive::output_archive(tson::write_buffer &,uchar)

- ea: `0x18000b3b0`
- end: `0x18000b45b`
- name: `??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z`
- size: `171`
- prototype: `tson::output_archive *__fastcall(tson::output_archive *this, struct tson::write_buffer *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e47c`

## callees

- `0x180003710`
- `0x18000ae94`
- `0x18000b3b0`

## pseudocode

```c
tson::output_archive *__fastcall tson::output_archive::output_archive(
        tson::output_archive *this,
        struct tson::write_buffer *a2,
        char a3)
{
  unsigned __int64 v5; // rax
  char v7; // [rsp+30h] [rbp+8h] BYREF
  char v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = a3;
  *(_QWORD *)this = 0;
  *((_BYTE *)this + 8) = 0;
  *((_WORD *)this + 5) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_BYTE *)this + 24) = 0;
  memset_0((char *)this + 28, 0, 0x64u);
  *((_QWORD *)this + 16) = 0;
  *((_DWORD *)this + 34) = 0;
  *((_QWORD *)this + 18) = a2;
  v7 = 0x80;
  tson::write_buffer::push_back<unsigned char>(a2, &v7);
  tson::write_buffer::push_back<unsigned char>(*((tson::write_buffer **)this + 18), &v8);
  v5 = *((_QWORD *)this + 16);
  if ( v5 >= 0x19 )
  {
    *((_BYTE *)this + 24) = 1;
  }
  else
  {
    *((_DWORD *)this + v5 + 7) = 1;
    ++*((_QWORD *)this + 16);
  }
  return this;
}

```

## disassembly

```asm
0x18000b3b0  mov     [rsp+arg_8], rbx
0x18000b3b5  mov     [rsp+arg_10], r8b
0x18000b3ba  push    rdi
0x18000b3bb  sub     rsp, 20h
0x18000b3bf  xor     eax, eax
0x18000b3c1  mov     qword ptr [rcx], 0
0x18000b3c8  mov     byte ptr [rcx+8], 0
0x18000b3cc  mov     rbx, rdx
0x18000b3cf  mov     [rcx+0Ah], ax
0x18000b3d3  mov     rdi, rcx
0x18000b3d6  mov     [rcx+10h], rax
0x18000b3da  xor     edx, edx; Val
0x18000b3dc  mov     [rcx+18h], al
0x18000b3df  lea     r8d, [rax+64h]; Size
0x18000b3e3  add     rcx, 1Ch; void *
0x18000b3e7  call    memset_0
0x18000b3ec  mov     qword ptr [rdi+80h], 0
0x18000b3f7  lea     rdx, [rsp+28h+arg_0]
0x18000b3fc  mov     rcx, rbx
0x18000b3ff  mov     dword ptr [rdi+88h], 0
0x18000b409  mov     [rdi+90h], rbx
0x18000b410  mov     [rsp+28h+arg_0], 80h
0x18000b415  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000b41a  mov     rcx, [rdi+90h]
0x18000b421  lea     rdx, [rsp+28h+arg_10]
0x18000b426  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000b42b  mov     rax, [rdi+80h]
0x18000b432  cmp     rax, 19h
0x18000b436  jnb     short loc_18000B449
0x18000b438  mov     dword ptr [rdi+rax*4+1Ch], 1
0x18000b440  inc     qword ptr [rdi+80h]
0x18000b447  jmp     short loc_18000B44D
0x18000b449  mov     byte ptr [rdi+18h], 1
0x18000b44d  mov     rbx, [rsp+28h+arg_8]
0x18000b452  mov     rax, rdi
0x18000b455  add     rsp, 20h
0x18000b459  pop     rdi
0x18000b45a  retn
```
