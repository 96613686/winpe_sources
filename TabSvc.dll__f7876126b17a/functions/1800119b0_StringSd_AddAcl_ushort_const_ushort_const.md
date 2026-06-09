# StringSd::_AddAcl(ushort const *,ushort const *)

- ea: `0x1800119b0`
- end: `0x180011ada`
- name: `?_AddAcl@StringSd@@AEAAJPEBG0@Z`
- size: `298`
- prototype: `__int64 __fastcall(StringSd *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800169d0`
- `0x18001a6c0`

## callees

- `0x180010d90`
- `0x1800119b0`
- `0x18001c04c`
- `0x18001c058`
- `0x18002fb4c`

## pseudocode

```c
__int64 __fastcall StringSd::_AddAcl(StringSd *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 v6; // rax
  int v8; // ecx
  unsigned int v9; // esi
  unsigned int v10; // eax
  unsigned int v11; // edx
  unsigned int v12; // eax
  void *v13; // rax
  void *v14; // rbp

  if ( !a3 )
    return 2147549183LL;
  if ( a2 && (StringBuffer::Append(this, a2) < 0 || StringBuffer::Append(this, L":") < 0) )
    return 2147500037LL;
  v6 = -1;
  while ( a3[++v6] != 0 )
    ;
  v8 = *((_DWORD *)this + 2);
  v9 = v6 + 1;
  if ( (int)v6 + 1 > (unsigned int)(0x7FFFFFFF - v8) )
    return 2147500037LL;
  v10 = *((_DWORD *)this + 3);
  if ( v10 > 0x3FFFFFFF )
    return 2147500037LL;
  v11 = v8 + v9;
  if ( v8 + v9 > v10 )
  {
    v12 = 2 * v10;
    if ( v11 <= v12 )
      v11 = v12;
    *((_DWORD *)this + 3) = v11;
    v13 = operator new(saturated_mul(v11, 2u));
    v14 = v13;
    if ( *(_QWORD *)this )
      memcpy_0(v13, *(const void **)this, 2LL * *((unsigned int *)this + 2));
    operator delete(*(void **)this);
    *(_QWORD *)this = v14;
  }
  memcpy_0((void *)(*(_QWORD *)this + 2LL * *((unsigned int *)this + 2)), a3, 2LL * v9);
  *((_DWORD *)this + 2) += v9 - 1;
  return 0;
}

```

## disassembly

```asm
0x1800119b0  mov     [rsp+arg_10], rbx
0x1800119b5  push    rdi
0x1800119b6  sub     rsp, 20h
0x1800119ba  mov     rbx, r8
0x1800119bd  mov     rdi, rcx
0x1800119c0  test    r8, r8
0x1800119c3  jnz     short loc_1800119D5
0x1800119c5  mov     eax, 8000FFFFh
0x1800119ca  mov     rbx, [rsp+28h+arg_10]
0x1800119cf  add     rsp, 20h
0x1800119d3  pop     rdi
0x1800119d4  retn
0x1800119d5  mov     [rsp+28h+arg_8], rsi
0x1800119da  test    rdx, rdx
0x1800119dd  jz      short loc_180011A03
0x1800119df  call    ?Append@StringBuffer@@QEAAJPEBG@Z; StringBuffer::Append(ushort const *)
0x1800119e4  test    eax, eax
0x1800119e6  js      loc_180011AC5
0x1800119ec  lea     rdx, asc_180038328; ":"
0x1800119f3  mov     rcx, rdi; this
0x1800119f6  call    ?Append@StringBuffer@@QEAAJPEBG@Z; StringBuffer::Append(ushort const *)
0x1800119fb  test    eax, eax
0x1800119fd  js      loc_180011AC5
0x180011a03  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180011a0a  mov     rax, r8
0x180011a0d  nop     dword ptr [rax]
0x180011a10  cmp     word ptr [rbx+rax*2+2], 0
0x180011a16  lea     rax, [rax+1]
0x180011a1a  jnz     short loc_180011A10
0x180011a1c  mov     ecx, [rdi+8]
0x180011a1f  lea     esi, [rax+1]
0x180011a22  mov     eax, 7FFFFFFFh
0x180011a27  sub     eax, ecx
0x180011a29  cmp     esi, eax
0x180011a2b  ja      loc_180011AC5
0x180011a31  mov     eax, [rdi+0Ch]
0x180011a34  cmp     eax, 3FFFFFFFh
0x180011a39  ja      loc_180011AC5
0x180011a3f  lea     edx, [rcx+rsi]
0x180011a42  cmp     edx, eax
0x180011a44  jbe     short loc_180011A95
0x180011a46  add     eax, eax
0x180011a48  mov     [rsp+28h+arg_0], rbp
0x180011a4d  cmp     edx, eax
0x180011a4f  cmovbe  edx, eax
0x180011a52  mov     eax, 2
0x180011a57  mov     ecx, edx
0x180011a59  mul     rcx
0x180011a5c  mov     [rdi+0Ch], ecx
0x180011a5f  cmovb   rax, r8
0x180011a63  mov     rcx, rax; Size
0x180011a66  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011a6b  mov     rdx, [rdi]; Src
0x180011a6e  mov     rbp, rax
0x180011a71  test    rdx, rdx
0x180011a74  jz      short loc_180011A85
0x180011a76  mov     r8d, [rdi+8]
0x180011a7a  mov     rcx, rax; void *
0x180011a7d  add     r8, r8; Size
0x180011a80  call    memcpy_0
0x180011a85  mov     rcx, [rdi]; Block
0x180011a88  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011a8d  mov     [rdi], rbp
0x180011a90  mov     rbp, [rsp+28h+arg_0]
0x180011a95  mov     ecx, [rdi+8]
0x180011a98  mov     rdx, rbx; Src
0x180011a9b  mov     rax, [rdi]
0x180011a9e  mov     r8d, esi
0x180011aa1  add     r8, r8; Size
0x180011aa4  lea     rcx, [rax+rcx*2]; void *
0x180011aa8  call    memcpy_0
0x180011aad  lea     eax, [rsi-1]
0x180011ab0  mov     rsi, [rsp+28h+arg_8]
0x180011ab5  add     [rdi+8], eax
0x180011ab8  xor     eax, eax
0x180011aba  mov     rbx, [rsp+28h+arg_10]
0x180011abf  add     rsp, 20h
0x180011ac3  pop     rdi
0x180011ac4  retn
0x180011ac5  mov     rsi, [rsp+28h+arg_8]
0x180011aca  mov     eax, 80004005h
0x180011acf  mov     rbx, [rsp+28h+arg_10]
0x180011ad4  add     rsp, 20h
0x180011ad8  pop     rdi
0x180011ad9  retn
```
