# wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)

- ea: `0x140003e30`
- end: `0x140003f08`
- name: `?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z`
- size: `216`
- prototype: `bool(wil::details_abi::heap_buffer *__hidden this, const void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400056d0`
- `0x140007474`
- `0x14000c180`

## callees

- `0x140003e30`
- `0x140003f40`
- `0x14000959e`
- `0x140009640`
- `0x14000f2cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140003ecc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140003efa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140003ecc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140003efa`

## pseudocode

```c
char __fastcall wil::details_abi::heap_buffer::push_back(
        wil::details_abi::heap_buffer *this,
        const void *a2,
        size_t a3)
{
  size_t v5; // rdx
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rdx
  void *v9; // r9
  size_t v10; // rsi

  v5 = *((_QWORD *)this + 2) - *(_QWORD *)this;
  if ( a3 + *((_QWORD *)this + 1) - *(_QWORD *)this < v5 )
    goto LABEL_5;
  v7 = 2 * v5;
  v8 = a3;
  if ( a3 < v7 )
    v8 = v7;
  if ( wil::details_abi::heap_buffer::reserve(this, v8) )
  {
LABEL_5:
    v9 = (void *)*((_QWORD *)this + 1);
    v10 = 0;
    if ( (unsigned __int64)v9 < *((_QWORD *)this + 2) )
      v10 = *((_QWORD *)this + 2) - (_QWORD)v9;
    if ( !a3 )
      goto LABEL_12;
    if ( !v9 )
      goto LABEL_13;
    if ( a2 && v10 >= a3 )
    {
      memcpy_0(v9, a2, a3);
LABEL_12:
      *((_QWORD *)this + 1) += a3;
      return 1;
    }
    memset_0(v9, 0, v10);
    if ( a2 )
    {
      if ( v10 >= a3 )
        goto LABEL_12;
      *(_DWORD *)_o__errno() = 34;
    }
    else
    {
LABEL_13:
      *(_DWORD *)_o__errno() = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_12;
  }
  return 0;
}

```

## disassembly

```asm
0x140003e30  mov     [rsp+arg_8], rbx
0x140003e35  mov     [rsp+arg_10], rbp
0x140003e3a  push    rdi
0x140003e3b  sub     rsp, 20h
0x140003e3f  mov     rax, [rcx+8]
0x140003e43  mov     rbp, rdx
0x140003e46  sub     rax, [rcx]
0x140003e49  mov     rdi, r8
0x140003e4c  mov     rdx, [rcx+10h]
0x140003e50  add     rax, r8
0x140003e53  sub     rdx, [rcx]
0x140003e56  mov     rbx, rcx
0x140003e59  cmp     rax, rdx
0x140003e5c  jb      short loc_140003E75
0x140003e5e  lea     rax, [rdx+rdx]
0x140003e62  mov     rdx, r8
0x140003e65  cmp     r8, rax
0x140003e68  cmovb   rdx, rax; unsigned __int64
0x140003e6c  call    ?reserve@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::reserve(unsigned __int64)
0x140003e71  test    al, al
0x140003e73  jz      short loc_140003EDF
0x140003e75  mov     r9, [rbx+8]
0x140003e79  mov     rax, [rbx+10h]
0x140003e7d  sub     rax, r9
0x140003e80  mov     [rsp+28h+arg_0], rsi
0x140003e85  xor     esi, esi
0x140003e87  cmp     r9, [rbx+10h]
0x140003e8b  cmovb   rsi, rax
0x140003e8f  test    rdi, rdi
0x140003e92  jz      short loc_140003EB1
0x140003e94  test    r9, r9
0x140003e97  jz      short loc_140003ECC
0x140003e99  test    rbp, rbp
0x140003e9c  jz      short loc_140003EE3
0x140003e9e  cmp     rsi, rdi
0x140003ea1  jb      short loc_140003EE3
0x140003ea3  mov     r8, rdi; Size
0x140003ea6  mov     rdx, rbp; Src
0x140003ea9  mov     rcx, r9; void *
0x140003eac  call    memcpy_0
0x140003eb1  add     [rbx+8], rdi
0x140003eb5  mov     al, 1
0x140003eb7  mov     rsi, [rsp+28h+arg_0]
0x140003ebc  mov     rbx, [rsp+28h+arg_8]
0x140003ec1  mov     rbp, [rsp+28h+arg_10]
0x140003ec6  add     rsp, 20h
0x140003eca  pop     rdi
0x140003ecb  retn
0x140003ecc  call    cs:__imp__o__errno
0x140003ed2  mov     dword ptr [rax], 16h
0x140003ed8  call    _invalid_parameter_noinfo
0x140003edd  jmp     short loc_140003EB1
0x140003edf  xor     al, al
0x140003ee1  jmp     short loc_140003EBC
0x140003ee3  mov     r8, rsi; Size
0x140003ee6  xor     edx, edx; Val
0x140003ee8  mov     rcx, r9; void *
0x140003eeb  call    memset_0
0x140003ef0  test    rbp, rbp
0x140003ef3  jz      short loc_140003ECC
0x140003ef5  cmp     rsi, rdi
0x140003ef8  jnb     short loc_140003EB1
0x140003efa  call    cs:__imp__o__errno
0x140003f00  mov     dword ptr [rax], 22h ; '"'
0x140003f06  jmp     short loc_140003ED8
```
