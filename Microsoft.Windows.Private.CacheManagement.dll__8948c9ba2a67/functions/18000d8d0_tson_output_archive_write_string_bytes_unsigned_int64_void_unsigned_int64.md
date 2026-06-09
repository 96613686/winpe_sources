# tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)

- ea: `0x18000d8d0`
- end: `0x18000daba`
- name: `?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z`
- size: `490`
- prototype: `void __fastcall(tson::output_archive *this, __int64, void *, size_t)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180009810`
- `0x18000aec0`
- `0x18000c820`
- `0x18000c990`
- `0x18000cd80`

## callees

- `0x18000d8d0`
- `0x18000de80`
- `0x18001cf40`
- `0x18001d600`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000daa3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000daa3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000da4f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000da97`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000da4f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000da97`

## pseudocode

```c
void __fastcall tson::output_archive::write_string_bytes(tson::output_archive *this, __int64 a2, void *a3, size_t a4)
{
  unsigned __int64 v4; // rsi
  char v8; // bp
  tson::write_buffer **v9; // r14
  __int64 v10; // rbx
  __int16 v11; // si
  __int64 v12; // rbp
  tson::write_buffer **v13; // r12
  tson::write_buffer *v14; // rbx
  tson::write_buffer *v15; // rbx
  void *v16; // rcx
  size_t v17; // rsi

  v4 = a2 + 1;
  if ( (unsigned __int64)(a2 + 1) > 0x7F )
  {
    if ( v4 > 0x7FFF && *((int *)this + 34) >= 0 )
      *((_DWORD *)this + 34) = -2147483637;
    v11 = v4 | 0x8000;
    v9 = (tson::write_buffer **)((char *)this + 144);
    v12 = *((_QWORD *)this + 18);
    if ( *(_QWORD *)(v12 + 2072) < *(_QWORD *)(v12 + 2080)
      || (v13 = (tson::write_buffer **)((char *)this + 144),
          tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u)) )
    {
      v13 = (tson::write_buffer **)((char *)this + 144);
      *(_BYTE *)(*(_QWORD *)(v12 + 2072))++ = HIBYTE(v11);
    }
    v14 = *v9;
    if ( *((_QWORD *)*v9 + 259) < *((_QWORD *)*v9 + 260) || tson::write_buffer::reserve(*v9, 1u) )
    {
      v9 = v13;
      *(_BYTE *)(*((_QWORD *)v14 + 259))++ = v11;
    }
  }
  else
  {
    v8 = 0;
    v9 = (tson::write_buffer **)((char *)this + 144);
    v10 = *((_QWORD *)this + 18);
    if ( a3 )
      v8 = a2 + 1;
    if ( *(_QWORD *)(v10 + 2072) < *(_QWORD *)(v10 + 2080)
      || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
    {
      *(_BYTE *)(*(_QWORD *)(v10 + 2072))++ = v8;
    }
  }
  v15 = *v9;
  if ( *((_QWORD *)v15 + 260) - *((_QWORD *)v15 + 259) >= a4 || (_mm_lfence(), tson::write_buffer::reserve(v15, a4)) )
  {
    v16 = (void *)*((_QWORD *)v15 + 259);
    v17 = *((_QWORD *)v15 + 260) - (_QWORD)v16;
    if ( a4 )
    {
      if ( !v16 )
        goto LABEL_20;
      if ( a3 && v17 >= a4 )
      {
        memmove(v16, a3, a4);
        *((_QWORD *)v15 + 259) += a4;
        return;
      }
      memset(v16, 0, *((_QWORD *)v15 + 260) - (_QWORD)v16);
      if ( !a3 )
      {
LABEL_20:
        *_errno() = 22;
LABEL_27:
        _invalid_parameter_noinfo();
        goto LABEL_28;
      }
      if ( v17 < a4 )
      {
        *_errno() = 34;
        goto LABEL_27;
      }
    }
LABEL_28:
    *((_QWORD *)v15 + 259) += a4;
  }
}

```

## disassembly

```asm
0x18000d8d0  push    rbx
0x18000d8d2  push    rsi
0x18000d8d3  push    rdi
0x18000d8d4  push    r15
0x18000d8d6  sub     rsp, 28h
0x18000d8da  lea     rsi, [rdx+1]
0x18000d8de  mov     [rsp+48h+arg_0], rbp
0x18000d8e3  mov     [rsp+48h+var_28], r14
0x18000d8e8  mov     rdi, r9
0x18000d8eb  mov     r15, r8
0x18000d8ee  mov     rbx, rcx
0x18000d8f1  cmp     rsi, 7Fh
0x18000d8f5  ja      short loc_18000D948
0x18000d8f7  xor     ebp, ebp
0x18000d8f9  movzx   eax, sil
0x18000d8fd  test    r8, r8
0x18000d900  lea     r14, [rcx+90h]
0x18000d907  mov     rbx, [r14]
0x18000d90a  cmovnz  ebp, eax
0x18000d90d  mov     rax, [rbx+820h]
0x18000d914  cmp     [rbx+818h], rax
0x18000d91b  jb      short loc_18000D932
0x18000d91d  mov     edx, 1; unsigned __int64
0x18000d922  mov     rcx, rbx; this
0x18000d925  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000d92a  test    al, al
0x18000d92c  jz      loc_18000DA02
0x18000d932  mov     rax, [rbx+818h]
0x18000d939  mov     [rax], bpl
0x18000d93c  inc     qword ptr [rbx+818h]
0x18000d943  jmp     loc_18000DA02
0x18000d948  mov     [rsp+48h+arg_10], r13
0x18000d94d  cmp     rsi, 7FFFh
0x18000d954  jbe     short loc_18000D969
0x18000d956  cmp     dword ptr [rcx+88h], 0
0x18000d95d  jl      short loc_18000D969
0x18000d95f  mov     dword ptr [rcx+88h], 8000000Bh
0x18000d969  bts     rsi, 0Fh
0x18000d96e  mov     [rsp+48h+arg_8], r12
0x18000d973  lea     r14, [rcx+90h]
0x18000d97a  mov     r13, rsi
0x18000d97d  mov     rbp, [r14]
0x18000d980  shr     r13, 8
0x18000d984  mov     rax, [rbp+820h]
0x18000d98b  cmp     [rbp+818h], rax
0x18000d992  jb      short loc_18000D9A8
0x18000d994  mov     edx, 1; unsigned __int64
0x18000d999  mov     rcx, rbp; this
0x18000d99c  mov     r12, r14
0x18000d99f  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000d9a4  test    al, al
0x18000d9a6  jz      short loc_18000D9C0
0x18000d9a8  mov     rax, [rbp+818h]
0x18000d9af  lea     r12, [rbx+90h]
0x18000d9b6  mov     [rax], r13b
0x18000d9b9  inc     qword ptr [rbp+818h]
0x18000d9c0  mov     rbx, [r14]
0x18000d9c3  mov     r13, [rsp+48h+arg_10]
0x18000d9c8  mov     rax, [rbx+820h]
0x18000d9cf  cmp     [rbx+818h], rax
0x18000d9d6  jb      short loc_18000D9E9
0x18000d9d8  mov     edx, 1; unsigned __int64
0x18000d9dd  mov     rcx, rbx; this
0x18000d9e0  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000d9e5  test    al, al
0x18000d9e7  jz      short loc_18000D9FD
0x18000d9e9  mov     rax, [rbx+818h]
0x18000d9f0  mov     r14, r12
0x18000d9f3  mov     [rax], sil
0x18000d9f6  inc     qword ptr [rbx+818h]
0x18000d9fd  mov     r12, [rsp+48h+arg_8]
0x18000da02  mov     rbx, [r14]
0x18000da05  mov     r14, [rsp+48h+var_28]
0x18000da0a  mov     rbp, [rsp+48h+arg_0]
0x18000da0f  mov     rax, [rbx+820h]
0x18000da16  sub     rax, [rbx+818h]
0x18000da1d  cmp     rax, rdi
0x18000da20  jnb     short loc_18000DA34
0x18000da22  lfence
0x18000da25  mov     rdx, rdi; unsigned __int64
0x18000da28  mov     rcx, rbx; this
0x18000da2b  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000da30  test    al, al
0x18000da32  jz      short loc_18000DAB0
0x18000da34  mov     rcx, [rbx+818h]; void *
0x18000da3b  mov     rsi, [rbx+820h]
0x18000da42  sub     rsi, rcx
0x18000da45  test    rdi, rdi
0x18000da48  jz      short loc_18000DAA9
0x18000da4a  test    rcx, rcx
0x18000da4d  jnz     short loc_18000DA5D
0x18000da4f  call    cs:__imp__errno
0x18000da55  mov     dword ptr [rax], 16h
0x18000da5b  jmp     short loc_18000DAA3
0x18000da5d  test    r15, r15
0x18000da60  jz      short loc_18000DA83
0x18000da62  cmp     rsi, rdi
0x18000da65  jb      short loc_18000DA83
0x18000da67  mov     r8, rdi; Size
0x18000da6a  mov     rdx, r15; Src
0x18000da6d  call    memmove
0x18000da72  add     [rbx+818h], rdi
0x18000da79  add     rsp, 28h
0x18000da7d  pop     r15
0x18000da7f  pop     rdi
0x18000da80  pop     rsi
0x18000da81  pop     rbx
0x18000da82  retn
0x18000da83  mov     r8, rsi; Size
0x18000da86  xor     edx, edx; Val
0x18000da88  call    memset
0x18000da8d  test    r15, r15
0x18000da90  jz      short loc_18000DA4F
0x18000da92  cmp     rsi, rdi
0x18000da95  jnb     short loc_18000DAA9
0x18000da97  call    cs:__imp__errno
0x18000da9d  mov     dword ptr [rax], 22h ; '"'
0x18000daa3  call    cs:__imp__invalid_parameter_noinfo
0x18000daa9  add     [rbx+818h], rdi
0x18000dab0  add     rsp, 28h
0x18000dab4  pop     r15
0x18000dab6  pop     rdi
0x18000dab7  pop     rsi
0x18000dab8  pop     rbx
0x18000dab9  retn
```
