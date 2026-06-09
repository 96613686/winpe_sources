# av_bsf_alloc

- ea: `0x180005ac0`
- end: `0x180005bb2`
- name: `av_bsf_alloc`
- size: `242`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180005cb0`
- `0x180005e50`
- `0x180005f30`
- `0x1800060b4`

## callees

- `0x180005ac0`
- `0x180005c00`
- `0x180006350`
- `0x18000ed70`
- `0x180022716`
- `0x180022740`

## pseudocode

```c
__int64 __fastcall av_bsf_alloc(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  _QWORD *v6; // rbx
  _QWORD *v7; // rbx
  _QWORD *v8; // rbx
  _QWORD *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  _QWORD *v13; // [rsp+40h] [rbp+18h] BYREF

  v4 = (_QWORD *)av_mallocz(72);
  v5 = v4;
  if ( !v4 )
    return 4294967284LL;
  v13 = v4;
  *v4 = &off_180026B60;
  v13[1] = a1;
  v6 = v13;
  v6[3] = avcodec_parameters_alloc();
  v7 = v13;
  v7[4] = avcodec_parameters_alloc();
  v8 = v13;
  if ( v13[3] && v13[4] )
  {
    if ( !*(_DWORD *)(a1 + 24) )
      goto LABEL_8;
    v8[2] = av_mallocz(*(int *)(a1 + 24));
    v9 = (_QWORD *)v13[2];
    if ( v9 )
    {
      v10 = *(_QWORD *)(a1 + 16);
      if ( v10 )
      {
        *v9 = v10;
        av_opt_set_defaults(v13[2]);
      }
LABEL_8:
      v11 = av_packet_alloc();
      v5[7] = v11;
      if ( v11 )
      {
        *a2 = v13;
        return 0;
      }
    }
  }
  av_bsf_free(&v13);
  return 4294967284LL;
}

```

## disassembly

```asm
0x180005ac0  mov     [rsp+arg_0], rbx
0x180005ac5  mov     [rsp+arg_8], rsi
0x180005aca  mov     [rsp+arg_18], rdi
0x180005acf  push    r14
0x180005ad1  sub     rsp, 20h
0x180005ad5  mov     rsi, rcx
0x180005ad8  mov     r14, rdx
0x180005adb  mov     ecx, 48h ; 'H'
0x180005ae0  call    av_mallocz
0x180005ae5  mov     rdi, rax
0x180005ae8  test    rax, rax
0x180005aeb  jz      loc_180005B97
0x180005af1  mov     [rsp+28h+arg_10], rax
0x180005af6  lea     rax, off_180026B60; "AVBSFContext"
0x180005afd  mov     [rdi], rax
0x180005b00  mov     rax, [rsp+28h+arg_10]
0x180005b05  mov     [rax+8], rsi
0x180005b09  mov     rbx, [rsp+28h+arg_10]
0x180005b0e  call    avcodec_parameters_alloc
0x180005b13  mov     [rbx+18h], rax
0x180005b17  mov     rbx, [rsp+28h+arg_10]
0x180005b1c  call    avcodec_parameters_alloc
0x180005b21  mov     [rbx+20h], rax
0x180005b25  mov     rbx, [rsp+28h+arg_10]
0x180005b2a  cmp     qword ptr [rbx+18h], 0
0x180005b2f  jz      short loc_180005B8D
0x180005b31  cmp     qword ptr [rbx+20h], 0
0x180005b36  jz      short loc_180005B8D
0x180005b38  cmp     dword ptr [rsi+18h], 0
0x180005b3c  jz      short loc_180005B73
0x180005b3e  movsxd  rcx, dword ptr [rsi+18h]
0x180005b42  call    av_mallocz
0x180005b47  mov     [rbx+10h], rax
0x180005b4b  mov     rax, [rsp+28h+arg_10]
0x180005b50  mov     rcx, [rax+10h]
0x180005b54  test    rcx, rcx
0x180005b57  jz      short loc_180005B8D
0x180005b59  mov     rax, [rsi+10h]
0x180005b5d  test    rax, rax
0x180005b60  jz      short loc_180005B73
0x180005b62  mov     [rcx], rax
0x180005b65  mov     rcx, [rsp+28h+arg_10]
0x180005b6a  mov     rcx, [rcx+10h]
0x180005b6e  call    av_opt_set_defaults
0x180005b73  call    av_packet_alloc
0x180005b78  mov     [rdi+38h], rax
0x180005b7c  test    rax, rax
0x180005b7f  jz      short loc_180005B8D
0x180005b81  mov     rax, [rsp+28h+arg_10]
0x180005b86  mov     [r14], rax
0x180005b89  xor     eax, eax
0x180005b8b  jmp     short loc_180005B9C
0x180005b8d  lea     rcx, [rsp+28h+arg_10]
0x180005b92  call    av_bsf_free
0x180005b97  mov     eax, 0FFFFFFF4h
0x180005b9c  mov     rbx, [rsp+28h+arg_0]
0x180005ba1  mov     rsi, [rsp+28h+arg_8]
0x180005ba6  mov     rdi, [rsp+28h+arg_18]
0x180005bab  add     rsp, 20h
0x180005baf  pop     r14
0x180005bb1  retn
```
