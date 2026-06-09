# tson::write_buffer::push_back(void const *,unsigned __int64)

- ea: `0x180026d00`
- end: `0x180026da9`
- name: `?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z`
- size: `169`
- prototype: `bool(tson::write_buffer *__hidden this, const void *, unsigned __int64)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180019360`
- `0x1800193f8`
- `0x180026964`
- `0x1800273e4`
- `0x180027a80`
- `0x180028374`
- `0x180028588`

## callees

- `0x180002db8`
- `0x180003345`
- `0x180026d00`
- `0x1800272e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180026d91`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180026d91`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026d42`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026d85`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026d42`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026d85`

## pseudocode

```c
bool __fastcall tson::write_buffer::push_back(tson::write_buffer *this, const void *a2, size_t a3)
{
  bool result; // al
  void *v7; // rcx
  size_t v8; // rsi

  if ( *((_QWORD *)this + 260) - *((_QWORD *)this + 259) >= a3 || (result = tson::write_buffer::reserve(this, a3)) )
  {
    if ( a3 )
    {
      v7 = (void *)*((_QWORD *)this + 259);
      if ( !v7 )
      {
LABEL_5:
        *(_DWORD *)_o__errno(v7, a2, a3) = 22;
LABEL_12:
        _invalid_parameter_noinfo();
        goto LABEL_13;
      }
      v8 = *((_QWORD *)this + 260) - (_QWORD)v7;
      if ( a2 && v8 >= a3 )
      {
        memcpy_0(v7, a2, a3);
      }
      else
      {
        memset_0(v7, 0, *((_QWORD *)this + 260) - (_QWORD)v7);
        if ( !a2 )
          goto LABEL_5;
        if ( v8 < a3 )
        {
          *(_DWORD *)_o__errno(v7, a2, a3) = 34;
          goto LABEL_12;
        }
      }
    }
LABEL_13:
    *((_QWORD *)this + 259) += a3;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180026d00  push    rbx
0x180026d02  push    rbp
0x180026d03  push    rsi
0x180026d04  push    rdi
0x180026d05  sub     rsp, 28h
0x180026d09  mov     rax, [rcx+820h]
0x180026d10  mov     rbx, r8
0x180026d13  sub     rax, [rcx+818h]
0x180026d1a  mov     rbp, rdx
0x180026d1d  mov     rdi, rcx
0x180026d20  cmp     rax, r8
0x180026d23  jnb     short loc_180026D31
0x180026d25  mov     rdx, rbx; unsigned __int64
0x180026d28  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180026d2d  test    al, al
0x180026d2f  jz      short loc_180026DA0
0x180026d31  test    rbx, rbx
0x180026d34  jz      short loc_180026D97
0x180026d36  mov     rcx, [rdi+818h]; void *
0x180026d3d  test    rcx, rcx
0x180026d40  jnz     short loc_180026D50
0x180026d42  call    cs:__imp__o__errno
0x180026d48  mov     dword ptr [rax], 16h
0x180026d4e  jmp     short loc_180026D91
0x180026d50  mov     rsi, [rdi+820h]
0x180026d57  sub     rsi, rcx
0x180026d5a  test    rbp, rbp
0x180026d5d  jz      short loc_180026D71
0x180026d5f  cmp     rsi, rbx
0x180026d62  jb      short loc_180026D71
0x180026d64  mov     r8, rbx; Size
0x180026d67  mov     rdx, rbp; Src
0x180026d6a  call    memcpy_0
0x180026d6f  jmp     short loc_180026D97
0x180026d71  mov     r8, rsi; Size
0x180026d74  xor     edx, edx; Val
0x180026d76  call    memset_0
0x180026d7b  test    rbp, rbp
0x180026d7e  jz      short loc_180026D42
0x180026d80  cmp     rsi, rbx
0x180026d83  jnb     short loc_180026D97
0x180026d85  call    cs:__imp__o__errno
0x180026d8b  mov     dword ptr [rax], 22h ; '"'
0x180026d91  call    cs:__imp__invalid_parameter_noinfo
0x180026d97  add     [rdi+818h], rbx
0x180026d9e  mov     al, 1
0x180026da0  add     rsp, 28h
0x180026da4  pop     rdi
0x180026da5  pop     rsi
0x180026da6  pop     rbp
0x180026da7  pop     rbx
0x180026da8  retn
```
