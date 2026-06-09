# av_frame_replace

- ea: `0x18003ba10`
- end: `0x18003bd12`
- name: `av_frame_replace`
- size: `770`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x18003f740`

## callees

- `0x18002f190`
- `0x18002f210`
- `0x180032150`
- `0x180035db0`
- `0x18003b7d0`
- `0x18003ba10`
- `0x18003bd20`
- `0x18003bfe0`
- `0x1800449d0`
- `0x180044cc0`
- `0x180044d50`
- `0x180050ab0`
- `0x18007a960`
- `0x18007b020`

## pseudocode

```c
__int64 __fastcall av_frame_replace(__int64 a1, __int64 a2)
{
  _QWORD *v5; // r14
  int v6; // esi
  unsigned int i; // ebp
  int v8; // eax
  int *v9; // r14
  int v10; // ebp
  int v11; // esi
  int *v12; // rsi
  char *v13; // rax
  int v14; // ebp
  __int64 v15; // r15
  int j; // esi
  _QWORD *v17; // rsi
  __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  void *v20; // rax

  if ( a1 == a2 )
    return 4294967274LL;
  v5 = (_QWORD *)(a2 + 184);
  if ( !*(_QWORD *)(a2 + 184) )
  {
    av_frame_unref(a1);
    if ( *(_QWORD *)a2 || *(_QWORD *)(a2 + 8) || *(_QWORD *)(a2 + 16) || *(_QWORD *)(a2 + 24) )
      return av_frame_ref(a1, a2);
    v6 = sub_18003BFE0(a1, a2, 0);
    if ( v6 < 0 )
    {
LABEL_9:
      av_frame_unref(a1);
      return (unsigned int)v6;
    }
  }
  *(_DWORD *)(a1 + 116) = *(_DWORD *)(a2 + 116);
  *(_DWORD *)(a1 + 104) = *(_DWORD *)(a2 + 104);
  *(_DWORD *)(a1 + 108) = *(_DWORD *)(a2 + 108);
  *(_DWORD *)(a1 + 112) = *(_DWORD *)(a2 + 112);
  v6 = av_channel_layout_copy(a1 + 384, a2 + 384);
  if ( v6 < 0 )
    goto LABEL_9;
  _mm_lfence();
  av_frame_side_data_free(a1 + 264, a1 + 272);
  av_dict_free(a1 + 312);
  v6 = sub_18003BFE0(a1, a2, 0);
  if ( v6 < 0 )
    goto LABEL_9;
  _mm_lfence();
  for ( i = 0; i < 8; ++i )
  {
    v6 = av_buffer_replace(a1 + 8 * ((int)i + 23LL), *v5);
    if ( v6 < 0 )
      goto LABEL_9;
    ++v5;
  }
  if ( *(_QWORD *)(a2 + 248) )
  {
    v8 = *(_DWORD *)(a1 + 256);
    v9 = (int *)(a2 + 256);
    v10 = *(_DWORD *)(a2 + 256);
    if ( v8 != v10 )
    {
      if ( v8 <= v10 )
        v10 = *(_DWORD *)(a1 + 256);
      v11 = v10;
      if ( v10 >= v8 )
      {
        v12 = (int *)(a2 + 256);
      }
      else
      {
        do
          av_buffer_unref(*(_QWORD *)(a1 + 248) + 8LL * v11++);
        while ( v11 < *(_DWORD *)(a1 + 256) );
        v12 = (int *)(a2 + 256);
      }
      v13 = (char *)av_realloc_array(*(_QWORD *)(a1 + 248), *v9, 8);
      if ( !v13 )
        goto LABEL_25;
      *(_QWORD *)(a1 + 248) = v13;
      *(_DWORD *)(a1 + 256) = *v12;
      sub_18007B020(&v13[8 * v10], 0, 8LL * (*v12 - v10));
      v9 = v12;
    }
    v14 = 0;
    if ( *v9 > 0 )
    {
      v15 = 0;
      do
      {
        v6 = av_buffer_replace(*(_QWORD *)(a1 + 248) + 8LL * v14, *(_QWORD *)(v15 + *(_QWORD *)(a2 + 248)));
        if ( v6 < 0 )
          goto LABEL_9;
        ++v14;
        v15 += 8;
      }
      while ( v14 < *v9 );
    }
  }
  else if ( *(_QWORD *)(a1 + 248) )
  {
    for ( j = 0; j < *(_DWORD *)(a1 + 256); ++j )
      av_buffer_unref(*(_QWORD *)(a1 + 248) + 8LL * j);
    av_freep(a1 + 248);
  }
  _mm_lfence();
  v6 = av_buffer_replace(a1 + 328, *(_QWORD *)(a2 + 328));
  if ( v6 < 0 )
    goto LABEL_9;
  v17 = (_QWORD *)(a1 + 96);
  if ( *(_QWORD *)(a1 + 96) != a1 )
  {
    _mm_lfence();
    av_freep(a1 + 96);
  }
  v18 = *(_QWORD *)(a2 + 96);
  if ( v18 == a2 )
  {
    *v17 = a1;
  }
  else
  {
    if ( *(int *)(a1 + 388) <= 0 || (v19 = *(int *)(a1 + 388), v19 > 0x1FFFFFFFFFFFFFFFLL) )
    {
      v6 = -22;
      goto LABEL_9;
    }
    _mm_lfence();
    v20 = av_memdup(v18, 8 * v19);
    *v17 = v20;
    if ( !v20 )
    {
LABEL_25:
      v6 = -12;
      goto LABEL_9;
    }
  }
  _mm_lfence();
  sub_18007A960(a1, a2, 64);
  sub_18007A960(a1 + 64, a2 + 64, 32);
  return 0;
}

```

## disassembly

```asm
0x18003ba10  mov     [rsp+arg_0], rbx
0x18003ba15  mov     [rsp+arg_8], rbp
0x18003ba1a  mov     [rsp+arg_10], rsi
0x18003ba1f  push    rdi
0x18003ba20  push    r14
0x18003ba22  push    r15
0x18003ba24  sub     rsp, 20h
0x18003ba28  mov     rdi, rdx
0x18003ba2b  mov     rbx, rcx
0x18003ba2e  cmp     rcx, rdx
0x18003ba31  jnz     short loc_18003BA3A
0x18003ba33  mov     eax, 0FFFFFFEAh
0x18003ba38  jmp     short loc_18003BA85
0x18003ba3a  lea     r14, [rdx+0B8h]
0x18003ba41  cmp     qword ptr [r14], 0
0x18003ba45  jnz     short loc_18003BAAB
0x18003ba47  call    av_frame_unref
0x18003ba4c  cmp     qword ptr [rdi], 0
0x18003ba50  jnz     short loc_18003BA9E
0x18003ba52  cmp     qword ptr [rdi+8], 0
0x18003ba57  jnz     short loc_18003BA9E
0x18003ba59  cmp     qword ptr [rdi+10h], 0
0x18003ba5e  jnz     short loc_18003BA9E
0x18003ba60  cmp     qword ptr [rdi+18h], 0
0x18003ba65  jnz     short loc_18003BA9E
0x18003ba67  xor     r8d, r8d
0x18003ba6a  mov     rdx, rdi
0x18003ba6d  mov     rcx, rbx
0x18003ba70  call    sub_18003BFE0
0x18003ba75  mov     esi, eax
0x18003ba77  test    eax, eax
0x18003ba79  jns     short loc_18003BAAB
0x18003ba7b  mov     rcx, rbx
0x18003ba7e  call    av_frame_unref
0x18003ba83  mov     eax, esi
0x18003ba85  mov     rbx, [rsp+38h+arg_0]
0x18003ba8a  mov     rbp, [rsp+38h+arg_8]
0x18003ba8f  mov     rsi, [rsp+38h+arg_10]
0x18003ba94  add     rsp, 20h
0x18003ba98  pop     r15
0x18003ba9a  pop     r14
0x18003ba9c  pop     rdi
0x18003ba9d  retn
0x18003ba9e  mov     rdx, rdi
0x18003baa1  mov     rcx, rbx
0x18003baa4  call    av_frame_ref
0x18003baa9  jmp     short loc_18003BA85
0x18003baab  mov     eax, [rdi+74h]
0x18003baae  lea     rdx, [rdi+180h]
0x18003bab5  mov     [rbx+74h], eax
0x18003bab8  lea     rcx, [rbx+180h]
0x18003babf  mov     eax, [rdi+68h]
0x18003bac2  mov     [rbx+68h], eax
0x18003bac5  mov     eax, [rdi+6Ch]
0x18003bac8  mov     [rbx+6Ch], eax
0x18003bacb  mov     eax, [rdi+70h]
0x18003bace  mov     [rbx+70h], eax
0x18003bad1  call    av_channel_layout_copy
0x18003bad6  mov     esi, eax
0x18003bad8  test    eax, eax
0x18003bada  js      short loc_18003BA7B
0x18003badc  lfence
0x18003badf  lea     rdx, [rbx+110h]
0x18003bae6  lea     rcx, [rbx+108h]
0x18003baed  call    av_frame_side_data_free
0x18003baf2  lea     rcx, [rbx+138h]
0x18003baf9  call    av_dict_free
0x18003bafe  xor     r8d, r8d
0x18003bb01  mov     rdx, rdi
0x18003bb04  mov     rcx, rbx
0x18003bb07  call    sub_18003BFE0
0x18003bb0c  mov     esi, eax
0x18003bb0e  test    eax, eax
0x18003bb10  js      loc_18003BA7B
0x18003bb16  lfence
0x18003bb19  xor     ebp, ebp
0x18003bb1b  mov     rdx, [r14]
0x18003bb1e  movsxd  rax, ebp
0x18003bb21  add     rax, 17h
0x18003bb25  lea     rcx, [rbx+rax*8]
0x18003bb29  call    av_buffer_replace
0x18003bb2e  mov     esi, eax
0x18003bb30  test    eax, eax
0x18003bb32  js      loc_18003BA7B
0x18003bb38  inc     ebp
0x18003bb3a  add     r14, 8
0x18003bb3e  cmp     ebp, 8
0x18003bb41  jb      short loc_18003BB1B
0x18003bb43  cmp     qword ptr [rdi+0F8h], 0
0x18003bb4b  jz      loc_18003BC2C
0x18003bb51  mov     eax, [rbx+100h]
0x18003bb57  lea     r14, [rdi+100h]
0x18003bb5e  mov     ebp, [r14]
0x18003bb61  cmp     eax, ebp
0x18003bb63  jz      loc_18003BBED
0x18003bb69  cmovle  ebp, eax
0x18003bb6c  mov     esi, ebp
0x18003bb6e  cmp     ebp, eax
0x18003bb70  jge     short loc_18003BB98
0x18003bb72  mov     rax, [rbx+0F8h]
0x18003bb79  movsxd  rcx, esi
0x18003bb7c  lea     rcx, [rax+rcx*8]
0x18003bb80  call    av_buffer_unref
0x18003bb85  inc     esi
0x18003bb87  cmp     esi, [rbx+100h]
0x18003bb8d  jl      short loc_18003BB72
0x18003bb8f  lea     rsi, [rdi+100h]
0x18003bb96  jmp     short loc_18003BB9B
0x18003bb98  mov     rsi, r14
0x18003bb9b  movsxd  rdx, dword ptr [r14]
0x18003bb9e  mov     r8d, 8
0x18003bba4  mov     rcx, [rbx+0F8h]
0x18003bbab  call    av_realloc_array
0x18003bbb0  mov     rcx, rax
0x18003bbb3  test    rax, rax
0x18003bbb6  jnz     short loc_18003BBC2
0x18003bbb8  mov     esi, 0FFFFFFF4h
0x18003bbbd  jmp     loc_18003BA7B
0x18003bbc2  mov     [rbx+0F8h], rcx
0x18003bbc9  xor     edx, edx
0x18003bbcb  mov     eax, [rsi]
0x18003bbcd  mov     [rbx+100h], eax
0x18003bbd3  mov     eax, [rsi]
0x18003bbd5  sub     eax, ebp
0x18003bbd7  movsxd  r8, eax
0x18003bbda  movsxd  rax, ebp
0x18003bbdd  shl     r8, 3
0x18003bbe1  lea     rcx, [rcx+rax*8]
0x18003bbe5  call    sub_18007B020
0x18003bbea  mov     r14, rsi
0x18003bbed  xor     ebp, ebp
0x18003bbef  cmp     [r14], ebp
0x18003bbf2  jle     short loc_18003BC64
0x18003bbf4  xor     r15d, r15d
0x18003bbf7  mov     rdx, [rdi+0F8h]
0x18003bbfe  mov     rax, [rbx+0F8h]
0x18003bc05  movsxd  rcx, ebp
0x18003bc08  mov     rdx, [r15+rdx]
0x18003bc0c  lea     rcx, [rax+rcx*8]
0x18003bc10  call    av_buffer_replace
0x18003bc15  mov     esi, eax
0x18003bc17  test    eax, eax
0x18003bc19  js      loc_18003BA7B
0x18003bc1f  inc     ebp
0x18003bc21  add     r15, 8
0x18003bc25  cmp     ebp, [r14]
0x18003bc28  jl      short loc_18003BBF7
0x18003bc2a  jmp     short loc_18003BC64
0x18003bc2c  lea     r14, [rbx+0F8h]
0x18003bc33  cmp     qword ptr [r14], 0
0x18003bc37  jz      short loc_18003BC64
0x18003bc39  xor     esi, esi
0x18003bc3b  cmp     [rbx+100h], esi
0x18003bc41  jle     short loc_18003BC5C
0x18003bc43  mov     rax, [r14]
0x18003bc46  movsxd  rdx, esi
0x18003bc49  lea     rcx, [rax+rdx*8]
0x18003bc4d  call    av_buffer_unref
0x18003bc52  inc     esi
0x18003bc54  cmp     esi, [rbx+100h]
0x18003bc5a  jl      short loc_18003BC43
0x18003bc5c  mov     rcx, r14
0x18003bc5f  call    av_freep
0x18003bc64  lfence
0x18003bc67  mov     rdx, [rdi+148h]
0x18003bc6e  lea     rcx, [rbx+148h]
0x18003bc75  call    av_buffer_replace
0x18003bc7a  mov     esi, eax
0x18003bc7c  test    eax, eax
0x18003bc7e  js      loc_18003BA7B
0x18003bc84  lea     rsi, [rbx+60h]
0x18003bc88  cmp     [rsi], rbx
0x18003bc8b  jz      short loc_18003BC98
0x18003bc8d  lfence
0x18003bc90  mov     rcx, rsi
0x18003bc93  call    av_freep
0x18003bc98  mov     rcx, [rdi+60h]
0x18003bc9c  cmp     rcx, rdi
0x18003bc9f  jz      short loc_18003BCE1
0x18003bca1  movsxd  rax, dword ptr [rbx+184h]
0x18003bca8  test    eax, eax
0x18003bcaa  jle     short loc_18003BCD7
0x18003bcac  mov     rdx, rax
0x18003bcaf  mov     rax, 1FFFFFFFFFFFFFFFh
0x18003bcb9  cmp     rdx, rax
0x18003bcbc  ja      short loc_18003BCD7
0x18003bcbe  lfence
0x18003bcc1  shl     rdx, 3
0x18003bcc5  call    av_memdup
0x18003bcca  mov     [rsi], rax
0x18003bccd  test    rax, rax
0x18003bcd0  jnz     short loc_18003BCE4
0x18003bcd2  jmp     loc_18003BBB8
0x18003bcd7  mov     esi, 0FFFFFFEAh
0x18003bcdc  jmp     loc_18003BA7B
0x18003bce1  mov     [rsi], rbx
0x18003bce4  lfence
0x18003bce7  mov     r8d, 40h ; '@'
0x18003bced  mov     rdx, rdi
0x18003bcf0  mov     rcx, rbx
0x18003bcf3  call    sub_18007A960
0x18003bcf8  lea     rdx, [rdi+40h]
0x18003bcfc  mov     r8d, 20h ; ' '
0x18003bd02  lea     rcx, [rbx+40h]
0x18003bd06  call    sub_18007A960
0x18003bd0b  xor     eax, eax
0x18003bd0d  jmp     loc_18003BA85
```
