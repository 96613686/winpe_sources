# tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)

- ea: `0x18000e874`
- end: `0x18000e91e`
- name: `?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z`
- size: `170`
- prototype: `void __fastcall(tson::output_archive *this, __int64, void *, rsize_t)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a5b4`
- `0x18000a60c`
- `0x18000aee8`

## callees

- `0x18000ae94`
- `0x18000dc18`
- `0x18000e874`

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
0x18000e874  mov     [rsp+arg_10], rbx
0x18000e879  mov     [rsp+arg_18], rsi
0x18000e87e  push    rdi
0x18000e87f  sub     rsp, 20h
0x18000e883  mov     rbx, rcx
0x18000e886  mov     rsi, r9
0x18000e889  lea     rcx, [rdx+1]
0x18000e88d  mov     rdi, r8
0x18000e890  cmp     rcx, 7Fh
0x18000e894  ja      short loc_18000E8AB
0x18000e896  mov     rax, r8
0x18000e899  neg     rax
0x18000e89c  sbb     dl, dl
0x18000e89e  and     dl, cl
0x18000e8a0  mov     [rsp+28h+arg_0], dl
0x18000e8a4  lea     rdx, [rsp+28h+arg_0]
0x18000e8a9  jmp     short loc_18000E8F1
0x18000e8ab  cmp     rcx, 7FFFh
0x18000e8b2  jbe     short loc_18000E8C7
0x18000e8b4  cmp     dword ptr [rbx+88h], 0
0x18000e8bb  jl      short loc_18000E8C7
0x18000e8bd  mov     dword ptr [rbx+88h], 8000000Bh
0x18000e8c7  bts     rcx, 0Fh
0x18000e8cc  lea     rdx, [rsp+28h+arg_0]
0x18000e8d1  mov     rax, rcx
0x18000e8d4  mov     [rsp+28h+arg_8], cl
0x18000e8d8  mov     rcx, [rbx+90h]
0x18000e8df  shr     rax, 8
0x18000e8e3  mov     [rsp+28h+arg_0], al
0x18000e8e7  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000e8ec  lea     rdx, [rsp+28h+arg_8]
0x18000e8f1  mov     rcx, [rbx+90h]
0x18000e8f8  call    ??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z; tson::write_buffer::push_back<uchar>(uchar const &)
0x18000e8fd  mov     rcx, [rbx+90h]; this
0x18000e904  mov     r8, rsi; unsigned __int64
0x18000e907  mov     rdx, rdi; void *
0x18000e90a  mov     rbx, [rsp+28h+arg_10]
0x18000e90f  mov     rsi, [rsp+28h+arg_18]
0x18000e914  add     rsp, 20h
0x18000e918  pop     rdi
0x18000e919  jmp     ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
```
