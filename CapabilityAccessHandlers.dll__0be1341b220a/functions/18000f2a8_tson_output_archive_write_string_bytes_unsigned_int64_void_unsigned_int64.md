# tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)

- ea: `0x18000f2a8`
- end: `0x18000f352`
- name: `?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z`
- size: `170`
- prototype: `void __fastcall(tson::output_archive *this, __int64, void *, rsize_t)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a54c`
- `0x18000a5a4`
- `0x18000ac78`

## callees

- `0x18000ab88`
- `0x18000e17c`
- `0x18000f2a8`

## pseudocode

```c
void __fastcall tson::output_archive::write_string_bytes(tson::output_archive *this, __int64 a2, void *a3, rsize_t a4)
{
  unsigned __int64 v6; // rcx
  char *v8; // rdx
  char v9; // ah
  tson::write_buffer *v10; // rcx
  char v11; // [rsp+30h] [rbp+8h] BYREF
  char v12; // [rsp+38h] [rbp+10h] BYREF

  v6 = a2 + 1;
  if ( (unsigned __int64)(a2 + 1) > 0x7F )
  {
    if ( v6 > 0x7FFF && *((int *)this + 34) >= 0 )
      *((_DWORD *)this + 34) = -2147483637;
    v9 = BYTE1(v6) | 0x80;
    v12 = a2 + 1;
    v10 = (tson::write_buffer *)*((_QWORD *)this + 18);
    v11 = v9;
    tson::write_buffer::push_back<unsigned char>(v10, &v11);
    v8 = &v12;
  }
  else
  {
    v11 = a3 != 0 ? v6 : 0;
    v8 = &v11;
  }
  tson::write_buffer::push_back<unsigned char>(*((tson::write_buffer **)this + 18), v8);
  tson::write_buffer::push_back(*((void ***)this + 18), a3, a4);
}

```

## disassembly

```asm
0x18000f2a8  mov     [rsp+arg_10], rbx
0x18000f2ad  mov     [rsp+arg_18], rsi
0x18000f2b2  push    rdi
0x18000f2b3  sub     rsp, 20h
0x18000f2b7  mov     rbx, rcx
0x18000f2ba  mov     rsi, r9
0x18000f2bd  lea     rcx, [rdx+1]
0x18000f2c1  mov     rdi, r8
0x18000f2c4  cmp     rcx, 7Fh
0x18000f2c8  ja      short loc_18000F2DF
0x18000f2ca  mov     rax, r8
0x18000f2cd  neg     rax
0x18000f2d0  sbb     dl, dl
0x18000f2d2  and     dl, cl
0x18000f2d4  mov     [rsp+28h+arg_0], dl
0x18000f2d8  lea     rdx, [rsp+28h+arg_0]
0x18000f2dd  jmp     short loc_18000F325
0x18000f2df  cmp     rcx, 7FFFh
0x18000f2e6  jbe     short loc_18000F2FB
0x18000f2e8  cmp     dword ptr [rbx+88h], 0
0x18000f2ef  jl      short loc_18000F2FB
0x18000f2f1  mov     dword ptr [rbx+88h], 8000000Bh
0x18000f2fb  bts     rcx, 0Fh
0x18000f300  lea     rdx, [rsp+28h+arg_0]
0x18000f305  mov     rax, rcx
0x18000f308  mov     [rsp+28h+arg_8], cl
0x18000f30c  mov     rcx, [rbx+90h]
0x18000f313  shr     rax, 8
0x18000f317  mov     [rsp+28h+arg_0], al
0x18000f31b  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000f320  lea     rdx, [rsp+28h+arg_8]
0x18000f325  mov     rcx, [rbx+90h]
0x18000f32c  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000f331  mov     rcx, [rbx+90h]; this
0x18000f338  mov     r8, rsi; unsigned __int64
0x18000f33b  mov     rdx, rdi; void *
0x18000f33e  mov     rbx, [rsp+28h+arg_10]
0x18000f343  mov     rsi, [rsp+28h+arg_18]
0x18000f348  add     rsp, 20h
0x18000f34c  pop     rdi
0x18000f34d  jmp     ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
```
