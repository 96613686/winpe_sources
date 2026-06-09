# av_write_frame

- ea: `0x1800121d0`
- end: `0x18001229e`
- name: `av_write_frame`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800144ac`

## callees

- `0x1800121d0`
- `0x18001315c`
- `0x180014244`
- `0x18001b9f6`
- `0x18001baf8`
- `0x18001bcb4`
- `0x18001d6e0`

## pseudocode

```c
__int64 __fastcall av_write_frame(_QWORD *a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v5; // rax
  int v6; // ebx
  __int64 v7; // rax
  __int64 result; // rax
  unsigned int v9; // edi
  __int64 v10; // rax

  v2 = a1[63];
  if ( a2 )
  {
    if ( (*(_DWORD *)(a2 + 40) & 0x2000) != 0 )
    {
      v2 = a2;
    }
    else
    {
      *(_QWORD *)(v2 + 24) = *(_QWORD *)(a2 + 24);
      *(_DWORD *)(v2 + 32) = *(_DWORD *)(a2 + 32);
      result = av_packet_copy_props();
      _mm_lfence();
      if ( (int)result < 0 )
        return result;
      if ( *(_QWORD *)a2 )
      {
        v10 = av_buffer_ref();
        *(_QWORD *)v2 = v10;
        if ( !v10 )
        {
          v9 = -12;
          goto LABEL_12;
        }
      }
    }
    v9 = sub_180014244(a1, v2, 0);
LABEL_12:
    av_packet_unref(v2);
    return v9;
  }
  v5 = a1[2];
  if ( (*(_BYTE *)(v5 + 68) & 2) == 0 )
    return 1;
  v6 = (*(__int64 (**)(void))(v5 + 80))();
  sub_18001315C(a1);
  if ( v6 >= 0 )
  {
    _mm_lfence();
    v7 = a1[4];
    if ( v7 )
    {
      if ( *(int *)(v7 + 84) < 0 )
        return *(unsigned int *)(v7 + 84);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800121d0  mov     [rsp+arg_0], rbx
0x1800121d5  mov     [rsp+arg_8], rsi
0x1800121da  push    rdi
0x1800121db  sub     rsp, 20h
0x1800121df  mov     rbx, [rcx+1F8h]
0x1800121e6  mov     rdi, rdx
0x1800121e9  mov     rsi, rcx
0x1800121ec  test    rdx, rdx
0x1800121ef  jnz     short loc_180012231
0x1800121f1  mov     rax, [rcx+10h]
0x1800121f5  test    byte ptr [rax+44h], 2
0x1800121f9  jz      short loc_18001222A
0x1800121fb  mov     rax, [rax+50h]
0x1800121ff  call    cs:__guard_dispatch_icall_fptr
0x180012205  mov     rcx, rsi
0x180012208  mov     ebx, eax
0x18001220a  call    sub_18001315C
0x18001220f  test    ebx, ebx
0x180012211  js      short loc_180012226
0x180012213  lfence
0x180012216  mov     rax, [rsi+20h]
0x18001221a  test    rax, rax
0x18001221d  jz      short loc_180012226
0x18001221f  cmp     [rax+54h], edi
0x180012222  cmovl   ebx, [rax+54h]
0x180012226  mov     eax, ebx
0x180012228  jmp     short loc_180012257
0x18001222a  mov     eax, 1
0x18001222f  jmp     short loc_180012257
0x180012231  test    dword ptr [rdx+28h], 2000h
0x180012238  jz      short loc_180012267
0x18001223a  mov     rbx, rdi
0x18001223d  xor     r8d, r8d
0x180012240  mov     rdx, rbx
0x180012243  mov     rcx, rsi
0x180012246  call    sub_180014244
0x18001224b  mov     edi, eax
0x18001224d  mov     rcx, rbx
0x180012250  call    av_packet_unref
0x180012255  mov     eax, edi
0x180012257  mov     rbx, [rsp+28h+arg_0]
0x18001225c  mov     rsi, [rsp+28h+arg_8]
0x180012261  add     rsp, 20h
0x180012265  pop     rdi
0x180012266  retn
0x180012267  mov     rax, [rdx+18h]
0x18001226b  mov     rcx, rbx
0x18001226e  mov     [rbx+18h], rax
0x180012272  mov     eax, [rdx+20h]
0x180012275  mov     [rbx+20h], eax
0x180012278  call    av_packet_copy_props
0x18001227d  lfence
0x180012280  test    eax, eax
0x180012282  js      short loc_180012257
0x180012284  mov     rcx, [rdi]
0x180012287  test    rcx, rcx
0x18001228a  jz      short loc_18001223D
0x18001228c  call    av_buffer_ref
0x180012291  mov     [rbx], rax
0x180012294  test    rax, rax
0x180012297  jnz     short loc_18001223D
0x180012299  lea     edi, [rax-0Ch]
0x18001229c  jmp     short loc_18001224D
```
