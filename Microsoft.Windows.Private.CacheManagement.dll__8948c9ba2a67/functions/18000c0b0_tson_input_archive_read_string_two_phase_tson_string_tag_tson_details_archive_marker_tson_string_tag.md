# tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)

- ea: `0x18000c0b0`
- end: `0x18000c207`
- name: `??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z`
- size: `343`
- prototype: `char __fastcall(tson::input_archive *, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c210`

## callees

- `0x180002b50`
- `0x18000c0b0`
- `0x18000c310`
- `0x18001cf40`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall tson::input_archive::read_string_two_phase<tson::string_tag>(
        tson::input_archive *a1,
        __int64 a2,
        __int64 a3)
{
  unsigned __int8 *v5; // rax
  __int64 v6; // rdx
  _BYTE *v7; // rcx
  __int64 v8; // rcx
  unsigned __int8 v9; // dl
  __int64 v10; // rcx
  __int64 v11; // r8
  unsigned __int8 v12; // dl
  unsigned __int64 v13; // rcx
  wil::details::in1diag3 *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdi
  size_t v17; // rsi
  const void *v18; // rdx

  if ( !*(_BYTE *)(a3 + 16) )
  {
    *(_BYTE *)(a3 + 16) = 1;
    LOBYTE(v5) = tson::input_archive::search(a1);
    if ( !(_BYTE)v5 )
      return (char)v5;
    v6 = *(_QWORD *)a1;
    v7 = *(_BYTE **)(*(_QWORD *)a1 + 8LL);
    if ( (unsigned __int64)v7 >= *(_QWORD *)(*(_QWORD *)a1 + 16LL) )
    {
      *(_BYTE *)(v6 + 24) = 1;
    }
    else
    {
      *(_QWORD *)(v6 + 8) = v7 + 1;
      if ( v7 && *v7 != 24 && *((int *)a1 + 2) >= 0 )
        *((_DWORD *)a1 + 2) = -2147023267;
    }
    v8 = *(_QWORD *)a1;
    v9 = 0;
    v5 = *(unsigned __int8 **)(*(_QWORD *)a1 + 8LL);
    if ( (unsigned __int64)v5 >= *(_QWORD *)(*(_QWORD *)a1 + 16LL) )
    {
      *(_BYTE *)(v8 + 24) = 1;
    }
    else
    {
      v9 = *v5++;
      *(_QWORD *)(v8 + 8) = v5;
      if ( (v9 & 0x80u) != 0 )
      {
        v10 = *(_QWORD *)a1;
        v11 = v9 & 0x7F;
        v5 = *(unsigned __int8 **)(*(_QWORD *)a1 + 8LL);
        if ( (unsigned __int64)v5 >= *(_QWORD *)(*(_QWORD *)a1 + 16LL) )
        {
          *(_BYTE *)(v10 + 24) = 1;
          LOBYTE(v5) = v9;
          v13 = v9 | (unsigned __int64)(v11 << 8);
        }
        else
        {
          v12 = *v5;
          *(_QWORD *)(v10 + 8) = v5 + 1;
          LOBYTE(v5) = v12;
          v13 = v12 | ((unsigned __int64)(unsigned int)v11 << 8);
        }
        *(_QWORD *)(a3 + 8) = v13;
        return (char)v5;
      }
    }
    *(_QWORD *)(a3 + 8) = v9;
    return (char)v5;
  }
  v14 = *(wil::details::in1diag3 **)a3;
  if ( !*(_QWORD *)a3 || (v15 = *(_QWORD *)(a3 + 8)) == 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  v16 = *(_QWORD *)a1;
  v17 = 2 * v15 - 2;
  v18 = *(const void **)(v16 + 8);
  if ( (unsigned __int64)v18 + v17 > *(_QWORD *)(v16 + 16) )
  {
    *(_BYTE *)(v16 + 24) = 1;
  }
  else
  {
    _mm_lfence();
    memmove(v14, v18, v17);
    *(_QWORD *)(v16 + 8) += v17;
  }
  v5 = *(unsigned __int8 **)a3;
  *(_WORD *)(*(_QWORD *)a3 + 2LL * *(_QWORD *)(a3 + 8) - 2) = 0;
  return (char)v5;
}

```

## disassembly

```asm
0x18000c0b0  mov     [rsp+arg_18], rbx
0x18000c0b5  push    rdi
0x18000c0b6  sub     rsp, 20h
0x18000c0ba  cmp     byte ptr [r8+10h], 0
0x18000c0bf  mov     rbx, r8
0x18000c0c2  mov     rdi, rcx
0x18000c0c5  jnz     loc_18000C19E
0x18000c0cb  mov     byte ptr [r8+10h], 1
0x18000c0d0  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x18000c0d5  test    al, al
0x18000c0d7  jz      loc_18000C193
0x18000c0dd  mov     rdx, [rdi]
0x18000c0e0  mov     rcx, [rdx+8]
0x18000c0e4  cmp     rcx, [rdx+10h]
0x18000c0e8  jnb     short loc_18000C10B
0x18000c0ea  lea     rax, [rcx+1]
0x18000c0ee  mov     [rdx+8], rax
0x18000c0f2  test    rcx, rcx
0x18000c0f5  jz      short loc_18000C10F
0x18000c0f7  cmp     byte ptr [rcx], 18h
0x18000c0fa  jz      short loc_18000C10F
0x18000c0fc  cmp     dword ptr [rdi+8], 0
0x18000c100  jl      short loc_18000C10F
0x18000c102  mov     dword ptr [rdi+8], 8007065Dh
0x18000c109  jmp     short loc_18000C10F
0x18000c10b  mov     byte ptr [rdx+18h], 1
0x18000c10f  mov     rcx, [rdi]
0x18000c112  xor     dl, dl
0x18000c114  mov     rax, [rcx+8]
0x18000c118  cmp     rax, [rcx+10h]
0x18000c11c  jnb     short loc_18000C188
0x18000c11e  movzx   edx, byte ptr [rax]
0x18000c121  inc     rax
0x18000c124  mov     [rcx+8], rax
0x18000c128  test    dl, dl
0x18000c12a  jns     short loc_18000C18C
0x18000c12c  mov     rcx, [rdi]
0x18000c12f  movzx   eax, dl
0x18000c132  and     al, 7Fh
0x18000c134  movzx   r8d, al
0x18000c138  mov     rax, [rcx+8]
0x18000c13c  cmp     rax, [rcx+10h]
0x18000c140  jnb     short loc_18000C168
0x18000c142  movzx   edx, byte ptr [rax]
0x18000c145  inc     rax
0x18000c148  mov     [rcx+8], rax
0x18000c14c  mov     ecx, r8d
0x18000c14f  shl     rcx, 8
0x18000c153  movzx   eax, dl
0x18000c156  or      rcx, rax
0x18000c159  mov     [rbx+8], rcx
0x18000c15d  mov     rbx, [rsp+28h+arg_18]
0x18000c162  add     rsp, 20h
0x18000c166  pop     rdi
0x18000c167  retn
0x18000c168  mov     byte ptr [rcx+18h], 1
0x18000c16c  mov     rcx, r8
0x18000c16f  shl     rcx, 8
0x18000c173  movzx   eax, dl
0x18000c176  or      rcx, rax
0x18000c179  mov     [rbx+8], rcx
0x18000c17d  mov     rbx, [rsp+28h+arg_18]
0x18000c182  add     rsp, 20h
0x18000c186  pop     rdi
0x18000c187  retn
0x18000c188  mov     byte ptr [rcx+18h], 1
0x18000c18c  movzx   ecx, dl
0x18000c18f  mov     [rbx+8], rcx
0x18000c193  mov     rbx, [rsp+28h+arg_18]
0x18000c198  add     rsp, 20h
0x18000c19c  pop     rdi
0x18000c19d  retn
0x18000c19e  mov     rcx, [r8]; this
0x18000c1a1  test    rcx, rcx
0x18000c1a4  jz      short loc_18000C201
0x18000c1a6  mov     rax, [r8+8]
0x18000c1aa  cmp     rax, 1
0x18000c1ae  jb      short loc_18000C201
0x18000c1b0  mov     rdi, [rdi]
0x18000c1b3  mov     [rsp+28h+arg_8], rsi
0x18000c1b8  lea     rsi, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18000c1c0  mov     rdx, [rdi+8]; Src
0x18000c1c4  lea     rax, [rdx+rsi]
0x18000c1c8  cmp     rax, [rdi+10h]
0x18000c1cc  ja      short loc_18000C1DF
0x18000c1ce  lfence
0x18000c1d1  mov     r8, rsi; Size
0x18000c1d4  call    memmove
0x18000c1d9  add     [rdi+8], rsi
0x18000c1dd  jmp     short loc_18000C1E3
0x18000c1df  mov     byte ptr [rdi+18h], 1
0x18000c1e3  mov     rcx, [rbx+8]
0x18000c1e7  xor     edx, edx
0x18000c1e9  mov     rax, [rbx]
0x18000c1ec  mov     rsi, [rsp+28h+arg_8]
0x18000c1f1  mov     rbx, [rsp+28h+arg_18]
0x18000c1f6  mov     [rax+rcx*2-2], dx
0x18000c1fb  add     rsp, 20h
0x18000c1ff  pop     rdi
0x18000c200  retn
0x18000c201  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
