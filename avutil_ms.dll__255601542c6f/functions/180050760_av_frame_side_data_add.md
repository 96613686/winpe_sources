# av_frame_side_data_add

- ea: `0x180050760`
- end: `0x18005087a`
- name: `av_frame_side_data_add`
- size: `282`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x18002f150`
- `0x18002f210`
- `0x1800506c0`
- `0x180050760`
- `0x180050a80`
- `0x180050c40`
- `0x180050d8c`

## pseudocode

```c
__int64 __fastcall av_frame_side_data_add(_QWORD *a1, int *a2, unsigned int a3, __int64 *a4, unsigned int a5)
{
  __int64 v9; // rbx
  __int64 v10; // r9
  int v11; // edi
  __int64 result; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  _DWORD *v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // [rsp+68h] [rbp+20h] BYREF

  v9 = av_frame_side_data_desc(a3);
  v10 = *a4;
  v18 = *a4;
  v11 = a5 & 4;
  if ( (a5 & 4) != 0 )
  {
    result = av_buffer_ref(v10);
    v18 = result;
    v10 = result;
    if ( !result )
      return result;
  }
  if ( (a5 & 1) != 0 )
  {
    av_frame_side_data_remove(a1, a2, a3);
    v10 = v18;
  }
  if ( !v9 || (*(_BYTE *)(v9 + 8) & 2) == 0 )
  {
    v13 = *a2;
    if ( v13 > 0 )
    {
      v14 = 0;
      while ( 1 )
      {
        v15 = *(_DWORD **)(*a1 + 8 * v14);
        if ( *v15 == a3 )
          break;
        if ( ++v14 >= v13 )
          goto LABEL_11;
      }
      if ( v15 )
      {
        v17 = sub_180050D8C(v15, v10, a5);
LABEL_16:
        v16 = v17;
        goto LABEL_17;
      }
    }
  }
LABEL_11:
  if ( v10 )
  {
    v17 = sub_1800506C0((_DWORD)a1, (_DWORD)a2, a3, v10, *(_QWORD *)(v10 + 8), *(_QWORD *)(v10 + 16));
    goto LABEL_16;
  }
  v16 = 0;
LABEL_17:
  if ( v16 )
  {
    if ( !v11 )
      *a4 = 0;
  }
  else if ( v11 )
  {
    av_buffer_unref(&v18);
  }
  return v16;
}

```

## disassembly

```asm
0x180050760  mov     [rsp+arg_0], rbx
0x180050765  mov     [rsp+arg_8], rbp
0x18005076a  mov     [rsp+arg_10], rsi
0x18005076f  push    rdi
0x180050770  push    r12
0x180050772  push    r14
0x180050774  sub     rsp, 30h
0x180050778  mov     r14, rcx
0x18005077b  mov     r12, r9
0x18005077e  mov     ecx, r8d
0x180050781  mov     esi, r8d
0x180050784  mov     rbp, rdx
0x180050787  call    av_frame_side_data_desc
0x18005078c  mov     edi, [rsp+48h+arg_20]
0x180050790  mov     rbx, rax
0x180050793  mov     r9, [r12]
0x180050797  mov     [rsp+48h+arg_18], r9
0x18005079c  and     edi, 4
0x18005079f  jz      short loc_1800507BA
0x1800507a1  mov     rcx, r9
0x1800507a4  call    av_buffer_ref
0x1800507a9  mov     [rsp+48h+arg_18], rax
0x1800507ae  mov     r9, rax
0x1800507b1  test    rax, rax
0x1800507b4  jz      loc_180050861
0x1800507ba  test    byte ptr [rsp+48h+arg_20], 1
0x1800507bf  jz      short loc_1800507D4
0x1800507c1  mov     r8d, esi
0x1800507c4  mov     rdx, rbp
0x1800507c7  mov     rcx, r14
0x1800507ca  call    av_frame_side_data_remove
0x1800507cf  mov     r9, [rsp+48h+arg_18]
0x1800507d4  test    rbx, rbx
0x1800507d7  jz      short loc_1800507DF
0x1800507d9  test    byte ptr [rbx+8], 2
0x1800507dd  jnz     short loc_1800507FD
0x1800507df  movsxd  rdx, dword ptr [rbp+0]
0x1800507e3  mov     r8, [r14]
0x1800507e6  test    rdx, rdx
0x1800507e9  jle     short loc_1800507FD
0x1800507eb  xor     eax, eax
0x1800507ed  mov     rcx, [r8+rax*8]
0x1800507f1  cmp     [rcx], esi
0x1800507f3  jz      short loc_180050806
0x1800507f5  inc     rax
0x1800507f8  cmp     rax, rdx
0x1800507fb  jl      short loc_1800507ED
0x1800507fd  test    r9, r9
0x180050800  jnz     short loc_18005081A
0x180050802  xor     ebx, ebx
0x180050804  jmp     short loc_18005083D
0x180050806  test    rcx, rcx
0x180050809  jz      short loc_1800507FD
0x18005080b  mov     r8d, [rsp+48h+arg_20]
0x180050810  mov     rdx, r9
0x180050813  call    sub_180050D8C
0x180050818  jmp     short loc_18005083A
0x18005081a  mov     rax, [r9+10h]
0x18005081e  mov     r8d, esi
0x180050821  mov     [rsp+48h+var_20], rax
0x180050826  mov     rdx, rbp
0x180050829  mov     rax, [r9+8]
0x18005082d  mov     rcx, r14
0x180050830  mov     [rsp+48h+var_28], rax
0x180050835  call    sub_1800506C0
0x18005083a  mov     rbx, rax
0x18005083d  test    rbx, rbx
0x180050840  jz      short loc_180050850
0x180050842  test    edi, edi
0x180050844  jnz     short loc_18005085E
0x180050846  mov     qword ptr [r12], 0
0x18005084e  jmp     short loc_18005085E
0x180050850  test    edi, edi
0x180050852  jz      short loc_18005085E
0x180050854  lea     rcx, [rsp+48h+arg_18]
0x180050859  call    av_buffer_unref
0x18005085e  mov     rax, rbx
0x180050861  mov     rbx, [rsp+48h+arg_0]
0x180050866  mov     rbp, [rsp+48h+arg_8]
0x18005086b  mov     rsi, [rsp+48h+arg_10]
0x180050870  add     rsp, 30h
0x180050874  pop     r14
0x180050876  pop     r12
0x180050878  pop     rdi
0x180050879  retn
```
