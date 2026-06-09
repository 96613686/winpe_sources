# av_frame_side_data_new

- ea: `0x180050b50`
- end: `0x180050c40`
- name: `av_frame_side_data_new`
- size: `240`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x18002ebe0`
- `0x18002f210`
- `0x1800506c0`
- `0x180050a80`
- `0x180050b50`
- `0x180050c40`
- `0x180050d8c`

## pseudocode

```c
__int64 __fastcall av_frame_side_data_new(_QWORD *a1, int *a2, unsigned int a3, __int64 a4, unsigned int a5)
{
  __int64 v9; // rdi
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rax
  _DWORD *v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v17[3]; // [rsp+30h] [rbp-18h] BYREF

  v9 = av_frame_side_data_desc(a3);
  v10 = av_buffer_alloc(a4);
  v17[0] = v10;
  if ( (a5 & 1) != 0 )
  {
    av_frame_side_data_remove(a1, a2, a3);
    v10 = v17[0];
  }
  if ( v9 && (*(_BYTE *)(v9 + 8) & 2) != 0 )
    goto LABEL_9;
  v11 = *a2;
  if ( v11 <= 0 )
    goto LABEL_9;
  v12 = 0;
  while ( 1 )
  {
    v13 = *(_DWORD **)(*a1 + 8 * v12);
    if ( *v13 == a3 )
      break;
    if ( ++v12 >= v11 )
      goto LABEL_9;
  }
  if ( !v13 )
  {
LABEL_9:
    if ( !v10 )
    {
      v14 = 0;
LABEL_15:
      av_buffer_unref(v17);
      return v14;
    }
    v15 = sub_1800506C0((_DWORD)a1, (_DWORD)a2, a3, v10, *(_QWORD *)(v10 + 8), *(_QWORD *)(v10 + 16));
  }
  else
  {
    v15 = sub_180050D8C(v13, v10, a5);
  }
  v14 = v15;
  if ( !v15 )
    goto LABEL_15;
  return v14;
}

```

## disassembly

```asm
0x180050b50  mov     rax, rsp
0x180050b53  mov     [rax+8], rbx
0x180050b57  mov     [rax+10h], rbp
0x180050b5b  mov     [rax+18h], rsi
0x180050b5f  mov     [rax+20h], rdi
0x180050b63  push    r14
0x180050b65  sub     rsp, 40h
0x180050b69  mov     r14, rcx
0x180050b6c  mov     rbx, r9
0x180050b6f  mov     ecx, r8d
0x180050b72  mov     esi, r8d
0x180050b75  mov     rbp, rdx
0x180050b78  call    av_frame_side_data_desc
0x180050b7d  mov     rcx, rbx
0x180050b80  mov     rdi, rax
0x180050b83  call    av_buffer_alloc
0x180050b88  test    byte ptr [rsp+48h+arg_20], 1
0x180050b8d  mov     r9, rax
0x180050b90  mov     [rsp+48h+var_18], rax
0x180050b95  jz      short loc_180050BAA
0x180050b97  mov     r8d, esi
0x180050b9a  mov     rdx, rbp
0x180050b9d  mov     rcx, r14
0x180050ba0  call    av_frame_side_data_remove
0x180050ba5  mov     r9, [rsp+48h+var_18]
0x180050baa  test    rdi, rdi
0x180050bad  jz      short loc_180050BB5
0x180050baf  test    byte ptr [rdi+8], 2
0x180050bb3  jnz     short loc_180050BD3
0x180050bb5  movsxd  rdx, dword ptr [rbp+0]
0x180050bb9  mov     r8, [r14]
0x180050bbc  test    rdx, rdx
0x180050bbf  jle     short loc_180050BD3
0x180050bc1  xor     eax, eax
0x180050bc3  mov     rcx, [r8+rax*8]
0x180050bc7  cmp     [rcx], esi
0x180050bc9  jz      short loc_180050BDC
0x180050bcb  inc     rax
0x180050bce  cmp     rax, rdx
0x180050bd1  jl      short loc_180050BC3
0x180050bd3  test    r9, r9
0x180050bd6  jnz     short loc_180050BF0
0x180050bd8  xor     ebx, ebx
0x180050bda  jmp     short loc_180050C18
0x180050bdc  test    rcx, rcx
0x180050bdf  jz      short loc_180050BD3
0x180050be1  mov     r8d, [rsp+48h+arg_20]
0x180050be6  mov     rdx, r9
0x180050be9  call    sub_180050D8C
0x180050bee  jmp     short loc_180050C10
0x180050bf0  mov     rax, [r9+10h]
0x180050bf4  mov     r8d, esi
0x180050bf7  mov     [rsp+48h+var_20], rax
0x180050bfc  mov     rdx, rbp
0x180050bff  mov     rax, [r9+8]
0x180050c03  mov     rcx, r14
0x180050c06  mov     [rsp+48h+var_28], rax
0x180050c0b  call    sub_1800506C0
0x180050c10  mov     rbx, rax
0x180050c13  test    rax, rax
0x180050c16  jnz     short loc_180050C22
0x180050c18  lea     rcx, [rsp+48h+var_18]
0x180050c1d  call    av_buffer_unref
0x180050c22  mov     rbp, [rsp+48h+arg_8]
0x180050c27  mov     rax, rbx
0x180050c2a  mov     rbx, [rsp+48h+arg_0]
0x180050c2f  mov     rsi, [rsp+48h+arg_10]
0x180050c34  mov     rdi, [rsp+48h+arg_18]
0x180050c39  add     rsp, 40h
0x180050c3d  pop     r14
0x180050c3f  retn
```
