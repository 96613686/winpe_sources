# avformat_stream_group_create

- ea: `0x1800195f0`
- end: `0x180019764`
- name: `avformat_stream_group_create`
- size: `372`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180002268`
- `0x1800195f0`
- `0x18001bb94`
- `0x18001bb9a`
- `0x18001bbfa`
- `0x18001bd5c`
- `0x18001bd86`
- `0x18001bd92`

## pseudocode

```c
_QWORD *__fastcall avformat_stream_group_create(__int64 a1, int a2, __int64 a3)
{
  __int64 v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rsi
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  _QWORD *v12; // rbx
  char ***v13; // rcx
  char **v14; // rax
  _QWORD *v15; // rbx
  _QWORD *v16; // rbx
  __int64 v17; // rax
  _QWORD *v19; // [rsp+40h] [rbp+20h] BYREF

  v6 = av_realloc_array(*(_QWORD *)(a1 + 64), (unsigned int)(*(_DWORD *)(a1 + 56) + 1), 8);
  if ( !v6 )
    return 0;
  *(_QWORD *)(a1 + 64) = v6;
  v7 = (_QWORD *)av_mallocz(88);
  v8 = v7;
  if ( !v7 )
    return 0;
  v19 = v7;
  *v7 = &off_180026010;
  av_opt_set_defaults(v19);
  *((_DWORD *)v19 + 8) = a2;
  v9 = a2 - 1;
  if ( !v9 )
  {
    v16 = v19;
    v17 = av_iamf_audio_element_alloc();
LABEL_14:
    v16[5] = v17;
    if ( v19[5] )
      goto LABEL_15;
    goto LABEL_18;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    v16 = v19;
    v17 = av_iamf_mix_presentation_alloc();
    goto LABEL_14;
  }
  v11 = v10 - 1;
  if ( v11 )
  {
    if ( v11 == 1 )
    {
      v12 = v19;
      v12[5] = av_mallocz(24);
      v13 = (char ***)v19[5];
      if ( v13 )
      {
        v14 = &off_180028EC0;
LABEL_11:
        *v13 = v14;
        av_opt_set_defaults(v19[5]);
LABEL_15:
        if ( !a3 || !(unsigned int)av_opt_set_dict2(v19, a3, 1) )
        {
          v8[10] = a1;
          *((_DWORD *)v19 + 4) = *(_DWORD *)(a1 + 56);
          *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL * (unsigned int)(*(_DWORD *)(a1 + 56))++) = v19;
          return v19;
        }
      }
    }
  }
  else
  {
    v15 = v19;
    v15[5] = av_mallocz(72);
    v13 = (char ***)v19[5];
    if ( v13 )
    {
      v14 = &off_180028D80;
      goto LABEL_11;
    }
  }
LABEL_18:
  sub_180002268(&v19);
  return 0;
}

```

## disassembly

```asm
0x1800195f0  mov     [rsp-18h+arg_8], rbx
0x1800195f5  mov     [rsp-18h+arg_10], rsi
0x1800195fa  push    rbp
0x1800195fb  push    rdi
0x1800195fc  push    r14
0x1800195fe  mov     rbp, rsp
0x180019601  sub     rsp, 20h
0x180019605  mov     ebx, edx
0x180019607  mov     r14, r8
0x18001960a  mov     edx, [rcx+38h]
0x18001960d  mov     rdi, rcx
0x180019610  mov     rcx, [rcx+40h]
0x180019614  inc     edx
0x180019616  mov     r8d, 8
0x18001961c  call    av_realloc_array
0x180019621  test    rax, rax
0x180019624  jz      loc_18001974F
0x18001962a  mov     ecx, 58h ; 'X'
0x18001962f  mov     [rdi+40h], rax
0x180019633  call    av_mallocz
0x180019638  mov     rsi, rax
0x18001963b  test    rax, rax
0x18001963e  jz      loc_18001974F
0x180019644  mov     [rbp+arg_0], rax
0x180019648  lea     rax, off_180026010; "AVStreamGroup"
0x18001964f  mov     [rsi], rax
0x180019652  mov     rcx, [rbp+arg_0]
0x180019656  call    av_opt_set_defaults
0x18001965b  mov     rcx, [rbp+arg_0]
0x18001965f  mov     [rcx+20h], ebx
0x180019662  sub     ebx, 1
0x180019665  jz      loc_1800196ED
0x18001966b  sub     ebx, 1
0x18001966e  jz      short loc_1800196E2
0x180019670  sub     ebx, 1
0x180019673  jz      short loc_1800196AA
0x180019675  cmp     ebx, 1
0x180019678  jnz     loc_180019746
0x18001967e  mov     rbx, [rbp+arg_0]
0x180019682  mov     ecx, 18h
0x180019687  call    av_mallocz
0x18001968c  mov     [rbx+28h], rax
0x180019690  mov     rax, [rbp+arg_0]
0x180019694  mov     rcx, [rax+28h]
0x180019698  test    rcx, rcx
0x18001969b  jz      loc_180019746
0x1800196a1  lea     rax, off_180028EC0; "AVStreamGroupLCEVC"
0x1800196a8  jmp     short loc_1800196D0
0x1800196aa  mov     rbx, [rbp+arg_0]
0x1800196ae  mov     ecx, 48h ; 'H'
0x1800196b3  call    av_mallocz
0x1800196b8  mov     [rbx+28h], rax
0x1800196bc  mov     rax, [rbp+arg_0]
0x1800196c0  mov     rcx, [rax+28h]
0x1800196c4  test    rcx, rcx
0x1800196c7  jz      short loc_180019746
0x1800196c9  lea     rax, off_180028D80; "AVStreamGroupTileGrid"
0x1800196d0  mov     [rcx], rax
0x1800196d3  mov     rcx, [rbp+arg_0]
0x1800196d7  mov     rcx, [rcx+28h]
0x1800196db  call    av_opt_set_defaults
0x1800196e0  jmp     short loc_180019705
0x1800196e2  mov     rbx, [rbp+arg_0]
0x1800196e6  call    av_iamf_mix_presentation_alloc
0x1800196eb  jmp     short loc_1800196F6
0x1800196ed  mov     rbx, [rbp+arg_0]
0x1800196f1  call    av_iamf_audio_element_alloc
0x1800196f6  mov     [rbx+28h], rax
0x1800196fa  mov     rax, [rbp+arg_0]
0x1800196fe  cmp     qword ptr [rax+28h], 0
0x180019703  jz      short loc_180019746
0x180019705  test    r14, r14
0x180019708  jz      short loc_180019720
0x18001970a  mov     rcx, [rbp+arg_0]
0x18001970e  mov     r8d, 1
0x180019714  mov     rdx, r14
0x180019717  call    av_opt_set_dict2
0x18001971c  test    eax, eax
0x18001971e  jnz     short loc_180019746
0x180019720  mov     [rsi+50h], rdi
0x180019724  mov     ecx, [rdi+38h]
0x180019727  mov     rax, [rbp+arg_0]
0x18001972b  mov     [rax+10h], ecx
0x18001972e  mov     edx, [rdi+38h]
0x180019731  mov     rax, [rbp+arg_0]
0x180019735  mov     rcx, [rdi+40h]
0x180019739  mov     [rcx+rdx*8], rax
0x18001973d  inc     dword ptr [rdi+38h]
0x180019740  mov     rax, [rbp+arg_0]
0x180019744  jmp     short loc_180019751
0x180019746  lea     rcx, [rbp+arg_0]
0x18001974a  call    sub_180002268
0x18001974f  xor     eax, eax
0x180019751  mov     rbx, [rsp+20h+arg_8]
0x180019756  mov     rsi, [rsp+20h+arg_10]
0x18001975b  add     rsp, 20h
0x18001975f  pop     r14
0x180019761  pop     rdi
0x180019762  pop     rbp
0x180019763  retn
```
