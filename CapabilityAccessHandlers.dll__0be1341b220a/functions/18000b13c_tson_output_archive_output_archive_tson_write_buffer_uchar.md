# tson::output_archive::output_archive(tson::write_buffer &,uchar)

- ea: `0x18000b13c`
- end: `0x18000b1e7`
- name: `??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z`
- size: `171`
- prototype: `tson::output_archive *__fastcall(tson::output_archive *this, struct tson::write_buffer *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000eb08`

## callees

- `0x1800056e0`
- `0x18000ab88`
- `0x18000b13c`

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
0x18000b13c  mov     [rsp+arg_8], rbx
0x18000b141  mov     [rsp+arg_10], r8b
0x18000b146  push    rdi
0x18000b147  sub     rsp, 20h
0x18000b14b  xor     eax, eax
0x18000b14d  mov     qword ptr [rcx], 0
0x18000b154  mov     byte ptr [rcx+8], 0
0x18000b158  mov     rbx, rdx
0x18000b15b  mov     [rcx+0Ah], ax
0x18000b15f  mov     rdi, rcx
0x18000b162  mov     [rcx+10h], rax
0x18000b166  xor     edx, edx; Val
0x18000b168  mov     [rcx+18h], al
0x18000b16b  lea     r8d, [rax+64h]; Size
0x18000b16f  add     rcx, 1Ch; void *
0x18000b173  call    memset_0
0x18000b178  mov     qword ptr [rdi+80h], 0
0x18000b183  lea     rdx, [rsp+28h+arg_0]
0x18000b188  mov     rcx, rbx
0x18000b18b  mov     dword ptr [rdi+88h], 0
0x18000b195  mov     [rdi+90h], rbx
0x18000b19c  mov     [rsp+28h+arg_0], 80h
0x18000b1a1  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000b1a6  mov     rcx, [rdi+90h]
0x18000b1ad  lea     rdx, [rsp+28h+arg_10]
0x18000b1b2  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000b1b7  mov     rax, [rdi+80h]
0x18000b1be  cmp     rax, 19h
0x18000b1c2  jnb     short loc_18000B1D5
0x18000b1c4  mov     dword ptr [rdi+rax*4+1Ch], 1
0x18000b1cc  inc     qword ptr [rdi+80h]
0x18000b1d3  jmp     short loc_18000B1D9
0x18000b1d5  mov     byte ptr [rdi+18h], 1
0x18000b1d9  mov     rbx, [rsp+28h+arg_8]
0x18000b1de  mov     rax, rdi
0x18000b1e1  add     rsp, 20h
0x18000b1e5  pop     rdi
0x18000b1e6  retn
```
