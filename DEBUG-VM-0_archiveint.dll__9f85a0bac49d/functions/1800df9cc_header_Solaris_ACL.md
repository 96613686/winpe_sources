# header_Solaris_ACL

- ea: `0x1800df9cc`
- end: `0x1800dfbdc`
- name: `header_Solaris_ACL`
- size: `528`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1800075f4`

## callees

- `0x180006c00`
- `0x18000a2d0`
- `0x18000c0ec`
- `0x18000ce38`
- `0x1800ac628`
- `0x1800df9cc`
- `0x1800e25a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800dfb83`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800dfb83`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800dfbc5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800dfbc5`

## string_xrefs

- `0x1800dfa70`: `Malformed Solaris ACL attribute (invalid digit)`
- `0x1800dfa67`: `Malformed Solaris ACL attribute (count too large)`
- `0x1800dfaa5`: `Malformed Solaris ACL attribute (unsupported type %llu)`
- `0x1800dfad8`: `Malformed Solaris ACL attribute (body overflow)`
- `0x1800dfb91`: `Can't allocate memory for ACL`
- `0x1800dfb9f`: `Malformed Solaris ACL attribute (unparsable)`

## pseudocode

```c
__int64 __fastcall header_Solaris_ACL(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4, __int64 a5)
{
  int v7; // ebx
  __int64 v9; // rbp
  int v10; // edx
  unsigned int body_to_string; // ebx
  unsigned __int64 v12; // r9
  _BYTE *i; // rdi
  unsigned int v14; // r15d
  _BYTE *v15; // rdi
  __int64 v16; // rcx
  _BYTE *v17; // rbp
  _BYTE *v18; // rax
  __int64 v19; // rax
  unsigned int v20; // eax
  void *Block[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v23; // [rsp+40h] [rbp-48h]

  v23 = 0;
  v7 = a4;
  *(_OWORD *)Block = 0;
  v9 = tar_atol(a4 + 124, 12);
  body_to_string = read_body_to_string(a1, v10, (unsigned int)Block, v7, a5);
  if ( !body_to_string )
  {
    v12 = 0;
    for ( i = Block[0]; *i && i < (char *)Block[0] + v9; ++i )
    {
      if ( (unsigned __int8)(*i - 48) > 7u )
      {
        archive_set_error(a1, 0xFFFFFFFFLL, "Malformed Solaris ACL attribute (invalid digit)");
        goto LABEL_10;
      }
      v12 = (char)*i - 48 + 8 * v12;
      if ( v12 > 0xFFFFFF )
      {
        archive_set_error(a1, 0xFFFFFFFFLL, "Malformed Solaris ACL attribute (count too large)");
LABEL_10:
        body_to_string = -20;
        goto LABEL_29;
      }
    }
    if ( (v12 & 0xFFFFFFFFFFFC0000uLL) == 0x40000 )
    {
      v14 = 256;
    }
    else
    {
      if ( (v12 & 0xFC0000) != 0xC0000 )
      {
        archive_set_error(a1, 0xFFFFFFFFLL, "Malformed Solaris ACL attribute (unsupported type %llu)", v12);
        goto LABEL_10;
      }
      v14 = 15360;
    }
    v15 = i + 1;
    if ( v15 >= (char *)Block[0] + v9 )
    {
      archive_set_error(a1, 0xFFFFFFFFLL, "Malformed Solaris ACL attribute (body overflow)");
      goto LABEL_10;
    }
    v16 = v9 + (char *)Block[0] - (char *)v15;
    v17 = v15;
    if ( *v15 )
    {
      v18 = &v15[v16];
      do
      {
        if ( v15 >= v18 )
          break;
        ++v15;
      }
      while ( *v15 );
    }
    if ( a2[39] || (v19 = archive_string_conversion_from_charset(a1, "UTF-8", 1), (a2[39] = v19) != 0) )
    {
      a2[35] = 0;
      archive_strncat(a2 + 34, v17, v15 - v17);
      v20 = archive_acl_from_text_l(a3 + 1032, a2[34], v14, a2[39]);
      *(_DWORD *)(a3 + 160) |= 0x200u;
      body_to_string = v20;
      *(_DWORD *)(a3 + 16) = 0;
      if ( v20 )
      {
        if ( *(_DWORD *)_o__errno() == 12 )
          archive_set_error(a1, 12, "Can't allocate memory for ACL");
        else
          archive_set_error(a1, 0xFFFFFFFFLL, "Malformed Solaris ACL attribute (unparsable)");
      }
    }
    else
    {
      body_to_string = -30;
    }
  }
LABEL_29:
  Block[1] = 0;
  v23 = 0;
  free(Block[0]);
  return body_to_string;
}

```

## disassembly

```asm
0x1800df9cc  push    rbx
0x1800df9ce  push    rbp
0x1800df9cf  push    rsi
0x1800df9d0  push    rdi
0x1800df9d1  push    r13
0x1800df9d3  push    r14
0x1800df9d5  push    r15
0x1800df9d7  sub     rsp, 50h
0x1800df9db  xor     eax, eax
0x1800df9dd  mov     r14, rdx
0x1800df9e0  mov     rsi, rcx
0x1800df9e3  mov     [rsp+88h+var_48], rax
0x1800df9e8  xorps   xmm0, xmm0
0x1800df9eb  lea     rcx, [r9+7Ch]
0x1800df9ef  mov     rbx, r9
0x1800df9f2  mov     r13, r8
0x1800df9f5  lea     edx, [rax+0Ch]
0x1800df9f8  movups  xmmword ptr [rsp+88h+Block], xmm0
0x1800df9fd  call    tar_atol
0x1800dfa02  mov     rbp, rax
0x1800dfa05  lea     r8, [rsp+88h+Block]
0x1800dfa0a  mov     rax, [rsp+88h+arg_20]
0x1800dfa12  mov     r9, rbx
0x1800dfa15  mov     rcx, rsi
0x1800dfa18  mov     [rsp+88h+var_68], rax
0x1800dfa1d  call    read_body_to_string
0x1800dfa22  mov     ebx, eax
0x1800dfa24  test    eax, eax
0x1800dfa26  jnz     loc_1800DFBAE
0x1800dfa2c  mov     rcx, [rsp+88h+Block]
0x1800dfa31  xor     r9d, r9d
0x1800dfa34  mov     rdi, rcx
0x1800dfa37  cmp     byte ptr [rdi], 0
0x1800dfa3a  jz      short loc_1800DFA8C
0x1800dfa3c  lea     rax, [rcx+rbp]
0x1800dfa40  cmp     rdi, rax
0x1800dfa43  jnb     short loc_1800DFA8C
0x1800dfa45  mov     al, [rdi]
0x1800dfa47  sub     al, 30h ; '0'
0x1800dfa49  cmp     al, 7
0x1800dfa4b  ja      short loc_1800DFA70
0x1800dfa4d  movsx   eax, byte ptr [rdi]
0x1800dfa50  sub     eax, 30h ; '0'
0x1800dfa53  cdqe
0x1800dfa55  lea     r9, [rax+r9*8]
0x1800dfa59  cmp     r9, 0FFFFFFh
0x1800dfa60  ja      short loc_1800DFA67
0x1800dfa62  inc     rdi
0x1800dfa65  jmp     short loc_1800DFA37
0x1800dfa67  lea     r8, aMalformedSolar_2; "Malformed Solaris ACL attribute (count "...
0x1800dfa6e  jmp     short loc_1800DFA77
0x1800dfa70  lea     r8, aMalformedSolar_1; "Malformed Solaris ACL attribute (invali"...
0x1800dfa77  or      edx, 0FFFFFFFFh
0x1800dfa7a  mov     rcx, rsi
0x1800dfa7d  call    archive_set_error
0x1800dfa82  mov     ebx, 0FFFFFFECh
0x1800dfa87  jmp     loc_1800DFBAE
0x1800dfa8c  mov     rax, r9
0x1800dfa8f  and     rax, 0FFFFFFFFFFFC0000h
0x1800dfa95  cmp     rax, 40000h
0x1800dfa9b  jz      short loc_1800DFAC1
0x1800dfa9d  cmp     rax, 0C0000h
0x1800dfaa3  jz      short loc_1800DFAB9
0x1800dfaa5  lea     r8, aMalformedSolar; "Malformed Solaris ACL attribute (unsupp"...
0x1800dfaac  or      edx, 0FFFFFFFFh
0x1800dfaaf  mov     rcx, rsi
0x1800dfab2  call    archive_set_error
0x1800dfab7  jmp     short loc_1800DFA82
0x1800dfab9  mov     r15d, 3C00h
0x1800dfabf  jmp     short loc_1800DFAC7
0x1800dfac1  mov     r15d, 100h
0x1800dfac7  mov     rdx, rbp
0x1800dfaca  mov     rax, rcx
0x1800dfacd  add     rax, rdx
0x1800dfad0  inc     rdi
0x1800dfad3  cmp     rdi, rax
0x1800dfad6  jb      short loc_1800DFAE1
0x1800dfad8  lea     r8, aMalformedSolar_3; "Malformed Solaris ACL attribute (body o"...
0x1800dfadf  jmp     short loc_1800DFA77
0x1800dfae1  sub     rcx, rdi
0x1800dfae4  add     rcx, rbp
0x1800dfae7  mov     rbp, rdi
0x1800dfaea  cmp     byte ptr [rdi], 0
0x1800dfaed  jz      short loc_1800DFB00
0x1800dfaef  lea     rax, [rcx+rdi]
0x1800dfaf3  cmp     rdi, rax
0x1800dfaf6  jnb     short loc_1800DFB00
0x1800dfaf8  inc     rdi
0x1800dfafb  cmp     byte ptr [rdi], 0
0x1800dfafe  jnz     short loc_1800DFAF3
0x1800dfb00  cmp     qword ptr [r14+138h], 0
0x1800dfb08  jnz     short loc_1800DFB30
0x1800dfb0a  mov     r8d, 1
0x1800dfb10  lea     rdx, Str2; "UTF-8"
0x1800dfb17  mov     rcx, rsi
0x1800dfb1a  call    archive_string_conversion_from_charset
0x1800dfb1f  mov     [r14+138h], rax
0x1800dfb26  test    rax, rax
0x1800dfb29  jnz     short loc_1800DFB30
0x1800dfb2b  lea     ebx, [rax-1Eh]
0x1800dfb2e  jmp     short loc_1800DFBAE
0x1800dfb30  lea     rbx, [r14+110h]
0x1800dfb37  mov     qword ptr [r14+118h], 0
0x1800dfb42  sub     rdi, rbp
0x1800dfb45  mov     rcx, rbx
0x1800dfb48  mov     r8, rdi
0x1800dfb4b  mov     rdx, rbp
0x1800dfb4e  call    archive_strncat
0x1800dfb53  mov     r9, [r14+138h]
0x1800dfb5a  lea     rcx, [r13+408h]
0x1800dfb61  mov     rdx, [rbx]
0x1800dfb64  mov     r8d, r15d
0x1800dfb67  call    archive_acl_from_text_l
0x1800dfb6c  bts     dword ptr [r13+0A0h], 9
0x1800dfb75  mov     ebx, eax
0x1800dfb77  mov     dword ptr [r13+10h], 0
0x1800dfb7f  test    eax, eax
0x1800dfb81  jz      short loc_1800DFBAE
0x1800dfb83  call    cs:__imp__o__errno
0x1800dfb89  mov     rcx, rsi
0x1800dfb8c  cmp     dword ptr [rax], 0Ch
0x1800dfb8f  jnz     short loc_1800DFB9F
0x1800dfb91  lea     r8, aCanTAllocateMe_16; "Can't allocate memory for ACL"
0x1800dfb98  mov     edx, 0Ch
0x1800dfb9d  jmp     short loc_1800DFBA9
0x1800dfb9f  lea     r8, aMalformedSolar_0; "Malformed Solaris ACL attribute (unpars"...
0x1800dfba6  or      edx, 0FFFFFFFFh
0x1800dfba9  call    archive_set_error
0x1800dfbae  mov     rcx, [rsp+88h+Block]; Block
0x1800dfbb3  mov     [rsp+88h+Block+8], 0
0x1800dfbbc  mov     [rsp+88h+var_48], 0
0x1800dfbc5  call    cs:__imp_free
0x1800dfbcb  mov     eax, ebx
0x1800dfbcd  add     rsp, 50h
0x1800dfbd1  pop     r15
0x1800dfbd3  pop     r14
0x1800dfbd5  pop     r13
0x1800dfbd7  pop     rdi
0x1800dfbd8  pop     rsi
0x1800dfbd9  pop     rbp
0x1800dfbda  pop     rbx
0x1800dfbdb  retn
```
