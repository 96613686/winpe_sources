# av_frame_side_data_clone

- ea: `0x180050880`
- end: `0x180050a73`
- name: `av_frame_side_data_clone`
- size: `499`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation`

## callees

- `0x18002f150`
- `0x18002f190`
- `0x18002f210`
- `0x180035d20`
- `0x180035db0`
- `0x1800506c0`
- `0x180050880`
- `0x180050a80`
- `0x180050c40`
- `0x180050d58`

## pseudocode

```c
__int64 __fastcall av_frame_side_data_clone(_QWORD *a1, int *a2, unsigned int *a3, char a4)
{
  __int64 v8; // rsi
  _QWORD *v9; // rcx
  int v10; // eax
  _QWORD *v11; // rsi
  __int64 result; // rax
  int v13; // ebx
  __int64 v14; // rax
  __int64 v15; // rbp
  int v16; // esi
  int v17; // edi
  __int64 v18; // rdx
  __int64 *i; // r8
  __int64 v20[5]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v21; // [rsp+60h] [rbp+8h] BYREF

  if ( !a1 || !a3 || !a2 || *a2 && !*a1 )
    return 4294967274LL;
  v8 = av_frame_side_data_desc(*a3);
  if ( (a4 & 1) != 0 )
    av_frame_side_data_remove(a1, a2, *a3);
  if ( !v8 || (*(_BYTE *)(v8 + 8) & 2) == 0 )
  {
    v9 = (_QWORD *)*a1;
    v10 = 0;
    if ( *a2 > 0 )
    {
      while ( 1 )
      {
        v11 = (_QWORD *)*v9;
        if ( *(_DWORD *)*v9 == *a3 )
          break;
        ++v10;
        ++v9;
        if ( v10 >= *a2 )
          goto LABEL_13;
      }
      if ( v11 )
      {
        v21 = 0;
        if ( (a4 & 2) == 0 )
          return 4294967279LL;
        result = av_dict_copy(&v21, *((_QWORD *)a3 + 3), 0);
        if ( (int)result < 0 )
        {
          _mm_lfence();
          return result;
        }
        v13 = av_buffer_replace(v11 + 4, *((_QWORD *)a3 + 4));
        _mm_lfence();
        if ( v13 < 0 )
        {
          av_dict_free(&v21);
          return (unsigned int)v13;
        }
        av_dict_free(v11 + 3);
        v11[3] = v21;
        v11[1] = *((_QWORD *)a3 + 1);
        v11[2] = *((_QWORD *)a3 + 2);
        return 0;
      }
    }
  }
LABEL_13:
  v20[0] = av_buffer_ref(*((_QWORD *)a3 + 4));
  if ( !v20[0] )
    return 4294967284LL;
  v14 = sub_1800506C0((_DWORD)a1, (_DWORD)a2, *a3, v20[0], *((_QWORD *)a3 + 1), *((_QWORD *)a3 + 2));
  v15 = v14;
  if ( !v14 )
  {
    av_buffer_unref(v20);
    return 4294967284LL;
  }
  v16 = av_dict_copy(v14 + 24, *((_QWORD *)a3 + 3), 0);
  if ( v16 >= 0 )
    return 0;
  _mm_lfence();
  v17 = *a2 - 1;
  if ( v17 >= 0 )
  {
    v18 = v17;
    for ( i = (__int64 *)(*a1 + 8LL * v17); ; --i )
    {
      v21 = *i;
      if ( v21 == v15 )
        break;
      --v17;
      if ( --v18 < 0 )
        return (unsigned int)v16;
    }
    sub_180050D58(&v21);
    *(_QWORD *)(*a1 + 8LL * v17) = *(_QWORD *)(*a1 + 8LL * (*a2)-- - 8);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180050880  mov     [rsp+arg_8], rbx
0x180050885  mov     [rsp+arg_10], rbp
0x18005088a  push    rsi
0x18005088b  push    rdi
0x18005088c  push    r14
0x18005088e  sub     rsp, 40h
0x180050892  mov     ebp, r9d
0x180050895  mov     rdi, r8
0x180050898  mov     rbx, rdx
0x18005089b  mov     r14, rcx
0x18005089e  test    rcx, rcx
0x1800508a1  jz      loc_180050A5B
0x1800508a7  test    r8, r8
0x1800508aa  jz      loc_180050A5B
0x1800508b0  test    rdx, rdx
0x1800508b3  jz      loc_180050A5B
0x1800508b9  cmp     dword ptr [rdx], 0
0x1800508bc  jz      short loc_1800508C8
0x1800508be  cmp     qword ptr [rcx], 0
0x1800508c2  jz      loc_180050A5B
0x1800508c8  mov     ecx, [r8]
0x1800508cb  call    av_frame_side_data_desc
0x1800508d0  mov     rsi, rax
0x1800508d3  test    bpl, 1
0x1800508d7  jz      short loc_1800508E7
0x1800508d9  mov     r8d, [rdi]
0x1800508dc  mov     rdx, rbx
0x1800508df  mov     rcx, r14
0x1800508e2  call    av_frame_side_data_remove
0x1800508e7  test    rsi, rsi
0x1800508ea  jz      short loc_1800508F2
0x1800508ec  test    byte ptr [rsi+8], 2
0x1800508f0  jnz     short loc_18005090E
0x1800508f2  mov     rcx, [r14]
0x1800508f5  xor     eax, eax
0x1800508f7  cmp     [rbx], eax
0x1800508f9  jle     short loc_18005090E
0x1800508fb  mov     edx, [rdi]
0x1800508fd  mov     rsi, [rcx]
0x180050900  cmp     [rsi], edx
0x180050902  jz      short loc_180050932
0x180050904  inc     eax
0x180050906  add     rcx, 8
0x18005090a  cmp     eax, [rbx]
0x18005090c  jl      short loc_1800508FD
0x18005090e  mov     rcx, [rdi+20h]
0x180050912  call    av_buffer_ref
0x180050917  mov     [rsp+58h+var_28], rax
0x18005091c  mov     r9, rax
0x18005091f  test    rax, rax
0x180050922  jnz     loc_1800509BD
0x180050928  mov     eax, 0FFFFFFF4h
0x18005092d  jmp     loc_180050A60
0x180050932  test    rsi, rsi
0x180050935  jz      short loc_18005090E
0x180050937  mov     [rsp+58h+arg_0], 0
0x180050940  test    bpl, 2
0x180050944  jnz     short loc_180050950
0x180050946  mov     eax, 0FFFFFFEFh
0x18005094b  jmp     loc_180050A60
0x180050950  mov     rdx, [rdi+18h]
0x180050954  lea     rcx, [rsp+58h+arg_0]
0x180050959  xor     r8d, r8d
0x18005095c  call    av_dict_copy
0x180050961  test    eax, eax
0x180050963  jns     short loc_18005096D
0x180050965  lfence
0x180050968  jmp     loc_180050A60
0x18005096d  mov     rdx, [rdi+20h]
0x180050971  lea     rcx, [rsi+20h]
0x180050975  call    av_buffer_replace
0x18005097a  mov     ebx, eax
0x18005097c  lfence
0x18005097f  test    eax, eax
0x180050981  jns     short loc_180050994
0x180050983  lea     rcx, [rsp+58h+arg_0]
0x180050988  call    av_dict_free
0x18005098d  mov     eax, ebx
0x18005098f  jmp     loc_180050A60
0x180050994  lea     rcx, [rsi+18h]
0x180050998  call    av_dict_free
0x18005099d  mov     rax, [rsp+58h+arg_0]
0x1800509a2  mov     [rsi+18h], rax
0x1800509a6  mov     rax, [rdi+8]
0x1800509aa  mov     [rsi+8], rax
0x1800509ae  mov     rax, [rdi+10h]
0x1800509b2  mov     [rsi+10h], rax
0x1800509b6  xor     eax, eax
0x1800509b8  jmp     loc_180050A60
0x1800509bd  mov     rax, [rdi+10h]
0x1800509c1  mov     rdx, rbx
0x1800509c4  mov     r8d, [rdi]
0x1800509c7  mov     rcx, r14
0x1800509ca  mov     [rsp+58h+var_30], rax
0x1800509cf  mov     rax, [rdi+8]
0x1800509d3  mov     [rsp+58h+var_38], rax
0x1800509d8  call    sub_1800506C0
0x1800509dd  mov     rbp, rax
0x1800509e0  test    rax, rax
0x1800509e3  jnz     short loc_1800509F4
0x1800509e5  lea     rcx, [rsp+58h+var_28]
0x1800509ea  call    av_buffer_unref
0x1800509ef  jmp     loc_180050928
0x1800509f4  mov     rdx, [rdi+18h]
0x1800509f8  lea     rcx, [rax+18h]
0x1800509fc  xor     r8d, r8d
0x1800509ff  call    av_dict_copy
0x180050a04  mov     esi, eax
0x180050a06  test    eax, eax
0x180050a08  jns     short loc_1800509B6
0x180050a0a  lfence
0x180050a0d  mov     edi, [rbx]
0x180050a0f  sub     edi, 1
0x180050a12  js      short loc_180050A57
0x180050a14  mov     rcx, [r14]
0x180050a17  movsxd  rdx, edi
0x180050a1a  lea     r8, [rcx+rdx*8]
0x180050a1e  mov     rax, [r8]
0x180050a21  mov     [rsp+58h+arg_0], rax
0x180050a26  cmp     rax, rbp
0x180050a29  jz      short loc_180050A39
0x180050a2b  dec     edi
0x180050a2d  sub     r8, 8
0x180050a31  sub     rdx, 1
0x180050a35  jns     short loc_180050A1E
0x180050a37  jmp     short loc_180050A57
0x180050a39  lea     rcx, [rsp+58h+arg_0]
0x180050a3e  call    sub_180050D58
0x180050a43  mov     r8, [r14]
0x180050a46  movsxd  rax, dword ptr [rbx]
0x180050a49  movsxd  rdx, edi
0x180050a4c  mov     rcx, [r8+rax*8-8]
0x180050a51  mov     [r8+rdx*8], rcx
0x180050a55  dec     dword ptr [rbx]
0x180050a57  mov     eax, esi
0x180050a59  jmp     short loc_180050A60
0x180050a5b  mov     eax, 0FFFFFFEAh
0x180050a60  mov     rbx, [rsp+58h+arg_8]
0x180050a65  mov     rbp, [rsp+58h+arg_10]
0x180050a6a  add     rsp, 40h
0x180050a6e  pop     r14
0x180050a70  pop     rdi
0x180050a71  pop     rsi
0x180050a72  retn
```
