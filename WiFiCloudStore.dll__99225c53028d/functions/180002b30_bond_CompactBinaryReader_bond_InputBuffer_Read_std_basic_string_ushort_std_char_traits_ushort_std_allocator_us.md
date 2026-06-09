# bond::CompactBinaryReader<bond::InputBuffer>::Read<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180002b30`
- end: `0x180002dd7`
- name: `??$Read@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `679`
- prototype: `void *__fastcall(bond::InputBuffer *this, bond::InputBuffer *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180002e70`
- `0x180026c5c`

## callees

- `0x180002b30`
- `0x180020390`
- `0x180025308`
- `0x1800269f4`
- `0x180027e28`
- `0x18002a8dc`
- `0x18002bb01`
- `0x18003071c`
- `0x180036240`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180002d9a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180002d9a`

## pseudocode

```c
void *__fastcall bond::CompactBinaryReader<bond::InputBuffer>::Read<std::wstring>(
        bond::InputBuffer *this,
        bond::InputBuffer *a2)
{
  __int64 v2; // rdi
  __int64 v5; // rax
  char *v6; // rdx
  unsigned int v7; // r14d
  unsigned int v8; // ecx
  _BYTE *v9; // rdi
  char v10; // al
  unsigned __int64 v11; // r12
  unsigned __int64 v12; // r13
  unsigned __int64 v13; // r15
  __int64 v14; // rdi
  unsigned __int64 v15; // rcx
  size_t v16; // rcx
  void *v17; // rax
  unsigned __int64 v18; // r9
  unsigned int v19; // r14d
  void *result; // rax
  bond::InputBuffer *v21; // rdx
  _WORD *v22; // rdi
  unsigned __int64 i; // rcx
  bond::InputBuffer *v24; // rcx
  void *v25; // rdi
  unsigned int v26; // ecx
  char *v27; // rdi
  char v28; // al
  void *v29; // [rsp+80h] [rbp+8h] BYREF

  v2 = *((unsigned int *)this + 8);
  LODWORD(v29) = 0;
  if ( *((unsigned int *)this + 6) <= (unsigned __int64)(v2 + 4) )
  {
    bond::GenericReadVariableUnsigned<bond::InputBuffer,unsigned int>(this, &v29);
    v7 = (unsigned int)v29;
  }
  else
  {
    v5 = *((_QWORD *)this + 2);
    v6 = (char *)(v2 + v5 + 1);
    v7 = *(_BYTE *)(v2 + v5) & 0x7F;
    if ( (unsigned int)*(char *)(v2 + v5) >= 0x80 )
    {
      v8 = *v6;
      v9 = v6 + 1;
      v10 = *v6;
      LODWORD(v6) = (_DWORD)v6 + 1;
      v7 |= (v10 & 0x7F) << 7;
      if ( v8 >= 0x80 )
      {
        v6 = v9 + 1;
        v7 |= (*v9 & 0x7F) << 14;
        if ( (unsigned int)(char)*v9 >= 0x80 )
        {
          v26 = *v6;
          v27 = v9 + 2;
          v28 = *v6;
          LODWORD(v6) = (_DWORD)v6 + 1;
          v7 |= (v28 & 0x7F) << 21;
          if ( v26 >= 0x80 )
          {
            LODWORD(v6) = (_DWORD)v27 + 1;
            v7 |= *v27 << 28;
          }
        }
      }
    }
    *((_DWORD *)this + 8) = (_DWORD)v6 - *((_DWORD *)this + 4);
  }
  v11 = *((_QWORD *)a2 + 2);
  if ( v7 <= v11 )
  {
    *((_QWORD *)a2 + 2) = v7;
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v24 = a2;
    else
      v24 = *(bond::InputBuffer **)a2;
    *((_WORD *)v24 + v7) = 0;
  }
  else
  {
    v12 = *((_QWORD *)a2 + 3);
    v13 = v7 - v11;
    if ( v13 > v12 - v11 )
    {
      v14 = 0x7FFFFFFFFFFFFFFELL;
      if ( 0x7FFFFFFFFFFFFFFELL - v11 < v13 )
        std::_Xlength_error("string too long");
      v15 = v12 >> 1;
      if ( v12 > 0x7FFFFFFFFFFFFFFELL - (v12 >> 1) )
      {
        v16 = -2;
      }
      else
      {
        v14 = v15 + v12;
        if ( (v7 | 7uLL) >= v15 + v12 )
          v14 = v7 | 7LL;
        if ( (unsigned __int64)(v14 + 1) > 0x7FFFFFFFFFFFFFFFLL )
          std::_Throw_bad_array_new_length();
        v16 = 2 * (v14 + 1);
        if ( !v16 )
        {
          v17 = 0;
          goto LABEL_14;
        }
      }
      if ( v16 < 0x1000 )
        v17 = operator new(v16);
      else
        v17 = (void *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>();
LABEL_14:
      v29 = v17;
      v18 = v7 - v11;
      *((_QWORD *)a2 + 2) = v7;
      *((_QWORD *)a2 + 3) = v14;
      if ( v12 > 7 )
      {
        v25 = *(void **)a2;
        _lambda_b70241e9b5ebaad244db3e52d52cab17_::operator()(v17, *(_QWORD *)a2, v11, v18);
        std::_Deallocate<16>(v25, 2 * v12 + 2);
      }
      else
      {
        _lambda_b70241e9b5ebaad244db3e52d52cab17_::operator()(v17, a2, v11, v18);
      }
      *(_QWORD *)a2 = v29;
      goto LABEL_17;
    }
    *((_QWORD *)a2 + 2) = v7;
    if ( v12 <= 7 )
      v21 = a2;
    else
      v21 = *(bond::InputBuffer **)a2;
    v22 = (_WORD *)((char *)v21 + 2 * v11);
    if ( v13 )
    {
      for ( i = v7 - v11; i; --i )
        *v22++ = 0;
    }
    *((_WORD *)v21 + v7) = 0;
  }
LABEL_17:
  v19 = 2 * v7;
  if ( *((_QWORD *)a2 + 2) )
  {
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(bond::InputBuffer **)a2;
  }
  else
  {
    a2 = (bond::InputBuffer *)&`bond::string_data<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>'::`2'::c;
  }
  if ( v19 > *((_DWORD *)this + 6) - *((_DWORD *)this + 8) )
    bond::InputBuffer::EofException(this, v19);
  result = memcpy_0(a2, (const void *)(*((_QWORD *)this + 2) + *((unsigned int *)this + 8)), v19);
  *((_DWORD *)this + 8) += v19;
  return result;
}

```

## disassembly

```asm
0x180002b30  mov     rax, rsp
0x180002b33  push    rbx
0x180002b34  push    rbp
0x180002b35  push    rsi
0x180002b36  push    rdi
0x180002b37  push    r12
0x180002b39  push    r13
0x180002b3b  push    r14
0x180002b3d  push    r15
0x180002b3f  sub     rsp, 38h
0x180002b43  mov     edi, [rcx+20h]
0x180002b46  mov     rbx, rdx
0x180002b49  mov     dword ptr [rax+8], 0
0x180002b50  mov     rsi, rcx
0x180002b53  mov     eax, [rcx+18h]
0x180002b56  lea     rdx, [rdi+4]
0x180002b5a  cmp     rax, rdx
0x180002b5d  jbe     loc_180002D02
0x180002b63  mov     rax, [rcx+10h]
0x180002b67  mov     r8d, 80h
0x180002b6d  movsx   ecx, byte ptr [rdi+rax]
0x180002b71  lea     rdx, [rax+1]
0x180002b75  mov     r14d, ecx
0x180002b78  add     rdx, rdi
0x180002b7b  and     r14d, 7Fh
0x180002b7f  cmp     ecx, r8d
0x180002b82  jb      short loc_180002BA2
0x180002b84  movsx   ecx, byte ptr [rdx]
0x180002b87  lea     rdi, [rdx+1]
0x180002b8b  mov     eax, ecx
0x180002b8d  mov     rdx, rdi
0x180002b90  and     eax, 7Fh
0x180002b93  shl     eax, 7
0x180002b96  or      r14d, eax
0x180002b99  cmp     ecx, r8d
0x180002b9c  jnb     loc_180002D48
0x180002ba2  sub     edx, [rsi+10h]
0x180002ba5  mov     [rsi+20h], edx
0x180002ba8  mov     r12, [rbx+10h]
0x180002bac  mov     ebp, r14d
0x180002baf  cmp     rbp, r12
0x180002bb2  jbe     loc_180002CE4
0x180002bb8  mov     r13, [rbx+18h]
0x180002bbc  mov     r15d, ebp
0x180002bbf  mov     rax, r13
0x180002bc2  sub     r15, r12
0x180002bc5  sub     rax, r12
0x180002bc8  cmp     r15, rax
0x180002bcb  jbe     loc_180002CB6
0x180002bd1  mov     rdi, 7FFFFFFFFFFFFFFEh
0x180002bdb  mov     rax, rdi
0x180002bde  sub     rax, r12
0x180002be1  cmp     rax, r15
0x180002be4  jb      loc_180002D93
0x180002bea  mov     rcx, r13
0x180002bed  mov     rax, rdi
0x180002bf0  shr     rcx, 1
0x180002bf3  sub     rax, rcx
0x180002bf6  cmp     r13, rax
0x180002bf9  ja      loc_180002DA1
0x180002bff  lea     rdi, [rcx+r13]
0x180002c03  mov     eax, ebp
0x180002c05  or      rax, 7
0x180002c09  cmp     rax, rdi
0x180002c0c  cmovnb  rdi, rax
0x180002c10  mov     rax, 7FFFFFFFFFFFFFFFh
0x180002c1a  lea     rcx, [rdi+1]
0x180002c1e  cmp     rcx, rax
0x180002c21  ja      loc_180002DBB
0x180002c27  add     rcx, rcx
0x180002c2a  jnz     loc_180002DA8
0x180002c30  xor     eax, eax
0x180002c32  mov     [rsp+78h+arg_0], rax
0x180002c3a  mov     r9, r15
0x180002c3d  mov     [rbx+10h], rbp
0x180002c41  mov     r8, r12
0x180002c44  mov     [rbx+18h], rdi
0x180002c48  mov     rcx, rax
0x180002c4b  cmp     r13, 7
0x180002c4f  ja      loc_180002D1C
0x180002c55  mov     rdx, rbx
0x180002c58  call    ??R_lambda_b70241e9b5ebaad244db3e52d52cab17_@@SA@QEAGQEBG_K2G@Z; _lambda_b70241e9b5ebaad244db3e52d52cab17_::operator()(ushort * const,ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x180002c5d  mov     rax, [rsp+78h+arg_0]
0x180002c65  mov     [rbx], rax
0x180002c68  add     r14d, r14d
0x180002c6b  cmp     qword ptr [rbx+10h], 0
0x180002c70  jz      loc_180002D3C
0x180002c76  cmp     qword ptr [rbx+18h], 7
0x180002c7b  jbe     short loc_180002C80
0x180002c7d  mov     rbx, [rbx]
0x180002c80  mov     eax, [rsi+18h]
0x180002c83  sub     eax, [rsi+20h]
0x180002c86  cmp     r14d, eax
0x180002c89  ja      loc_180002DCB
0x180002c8f  mov     edx, [rsi+20h]
0x180002c92  mov     rcx, rbx; void *
0x180002c95  add     rdx, [rsi+10h]; Src
0x180002c99  mov     r8d, r14d; Size
0x180002c9c  call    memcpy_0
0x180002ca1  add     [rsi+20h], r14d
0x180002ca5  add     rsp, 38h
0x180002ca9  pop     r15
0x180002cab  pop     r14
0x180002cad  pop     r13
0x180002caf  pop     r12
0x180002cb1  pop     rdi
0x180002cb2  pop     rsi
0x180002cb3  pop     rbp
0x180002cb4  pop     rbx
0x180002cb5  retn
0x180002cb6  mov     [rbx+10h], rbp
0x180002cba  cmp     r13, 7
0x180002cbe  jbe     short loc_180002CDF
0x180002cc0  mov     rdx, [rbx]
0x180002cc3  lea     rdi, [rdx+r12*2]
0x180002cc7  test    r15, r15
0x180002cca  jz      short loc_180002CD7
0x180002ccc  xor     eax, eax
0x180002cce  mov     rcx, r15
0x180002cd1  movzx   eax, ax
0x180002cd4  rep stosw
0x180002cd7  xor     eax, eax
0x180002cd9  mov     [rdx+rbp*2], ax
0x180002cdd  jmp     short loc_180002C68
0x180002cdf  mov     rdx, rbx
0x180002ce2  jmp     short loc_180002CC3
0x180002ce4  mov     [rbx+10h], rbp
0x180002ce8  cmp     qword ptr [rbx+18h], 7
0x180002ced  jbe     short loc_180002CFD
0x180002cef  mov     rcx, [rbx]
0x180002cf2  xor     eax, eax
0x180002cf4  mov     [rcx+rbp*2], ax
0x180002cf8  jmp     loc_180002C68
0x180002cfd  mov     rcx, rbx; this
0x180002d00  jmp     short loc_180002CF2
0x180002d02  lea     rdx, [rsp+78h+arg_0]
0x180002d0a  call    ??$GenericReadVariableUnsigned@VInputBuffer@bond@@I@bond@@YAXAEAVInputBuffer@0@AEAI@Z; bond::GenericReadVariableUnsigned<bond::InputBuffer,uint>(bond::InputBuffer &,uint &)
0x180002d0f  mov     r14d, dword ptr [rsp+78h+arg_0]
0x180002d17  jmp     loc_180002BA8
0x180002d1c  mov     rdi, [rbx]
0x180002d1f  mov     rdx, rdi
0x180002d22  call    ??R_lambda_b70241e9b5ebaad244db3e52d52cab17_@@SA@QEAGQEBG_K2G@Z; _lambda_b70241e9b5ebaad244db3e52d52cab17_::operator()(ushort * const,ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x180002d27  lea     rdx, ds:2[r13*2]
0x180002d2f  mov     rcx, rdi
0x180002d32  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180002d37  jmp     loc_180002C5D
0x180002d3c  lea     rbx, ?c@?1???$string_data@GU?$char_traits@G@std@@V?$allocator@G@2@@bond@@YAPEAGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z@4GA; ushort `bond::string_data<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::wstring &)'::`2'::c
0x180002d43  jmp     loc_180002C80
0x180002d48  movsx   ecx, byte ptr [rdi]
0x180002d4b  lea     rdx, [rdi+1]
0x180002d4f  mov     eax, ecx
0x180002d51  and     eax, 7Fh
0x180002d54  shl     eax, 0Eh
0x180002d57  or      r14d, eax
0x180002d5a  cmp     ecx, r8d
0x180002d5d  jb      loc_180002BA2
0x180002d63  movsx   ecx, byte ptr [rdx]
0x180002d66  lea     rdi, [rdx+1]
0x180002d6a  mov     eax, ecx
0x180002d6c  mov     rdx, rdi
0x180002d6f  and     eax, 7Fh
0x180002d72  shl     eax, 15h
0x180002d75  or      r14d, eax
0x180002d78  cmp     ecx, r8d
0x180002d7b  jb      loc_180002BA2
0x180002d81  movsx   eax, byte ptr [rdi]
0x180002d84  lea     rdx, [rdi+1]
0x180002d88  shl     eax, 1Ch
0x180002d8b  or      r14d, eax
0x180002d8e  jmp     loc_180002BA2
0x180002d93  lea     rcx, aStringTooLong; "string too long"
0x180002d9a  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180002da1  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x180002da8  cmp     rcx, 1000h
0x180002daf  jb      short loc_180002DC1
0x180002db1  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x180002db6  jmp     loc_180002C32
0x180002dbb  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x180002dc1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002dc6  jmp     loc_180002C32
0x180002dcb  mov     edx, r14d; unsigned int
0x180002dce  mov     rcx, rsi; this
0x180002dd1  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
```
