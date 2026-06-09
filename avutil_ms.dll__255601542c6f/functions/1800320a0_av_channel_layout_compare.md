# av_channel_layout_compare

- ea: `0x1800320a0`
- end: `0x180032144`
- name: `av_channel_layout_compare`
- size: `164`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003bf24`
- `0x1800465b0`

## callees

- `0x180031dd0`
- `0x1800320a0`

## pseudocode

```c
__int64 __fastcall av_channel_layout_compare(int *a1, __int64 a2)
{
  int v2; // r8d
  int v5; // ecx
  unsigned int v6; // edi
  int v8; // ebx

  v2 = a1[1];
  if ( v2 == *(_DWORD *)(a2 + 4) )
  {
    v5 = *a1;
    v6 = 0;
    if ( (v5 == 0) == (*(_DWORD *)a2 == 0) )
    {
      if ( !v5 )
        return 0;
      if ( ((v5 - 1) & 0xFFFFFFFD) == 0 && v5 == *(_DWORD *)a2 )
      {
        LOBYTE(v6) = *((_QWORD *)a1 + 1) != *(_QWORD *)(a2 + 8);
        return v6;
      }
      if ( v2 <= 0 )
        return 0;
      while ( 1 )
      {
        v8 = av_channel_layout_channel_from_index(a1, v6);
        if ( v8 != (unsigned int)av_channel_layout_channel_from_index(a2, v6) )
          break;
        if ( (int)++v6 >= a1[1] )
          return 0;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800320a0  mov     [rsp+arg_0], rbx
0x1800320a5  mov     [rsp+arg_8], rsi
0x1800320aa  mov     [rsp+arg_10], rdi
0x1800320af  push    r14
0x1800320b1  sub     rsp, 20h
0x1800320b5  mov     r8d, [rcx+4]
0x1800320b9  mov     r14, rdx
0x1800320bc  mov     rsi, rcx
0x1800320bf  cmp     r8d, [rdx+4]
0x1800320c3  jnz     short loc_180032129
0x1800320c5  mov     ecx, [rcx]
0x1800320c7  xor     edi, edi
0x1800320c9  test    ecx, ecx
0x1800320cb  mov     edx, edi
0x1800320cd  mov     eax, edi
0x1800320cf  setz    dl
0x1800320d2  cmp     [r14], edi
0x1800320d5  setz    al
0x1800320d8  cmp     edx, eax
0x1800320da  jnz     short loc_180032129
0x1800320dc  test    ecx, ecx
0x1800320de  jz      short loc_180032125
0x1800320e0  lea     eax, [rcx-1]
0x1800320e3  test    eax, 0FFFFFFFDh
0x1800320e8  jnz     short loc_1800320FF
0x1800320ea  cmp     ecx, [r14]
0x1800320ed  jnz     short loc_1800320FF
0x1800320ef  mov     rax, [r14+8]
0x1800320f3  cmp     [rsi+8], rax
0x1800320f7  setnz   dil
0x1800320fb  mov     eax, edi
0x1800320fd  jmp     short loc_18003212E
0x1800320ff  test    r8d, r8d
0x180032102  jle     short loc_180032125
0x180032104  mov     edx, edi
0x180032106  mov     rcx, rsi
0x180032109  call    av_channel_layout_channel_from_index
0x18003210e  mov     edx, edi
0x180032110  mov     rcx, r14
0x180032113  mov     ebx, eax
0x180032115  call    av_channel_layout_channel_from_index
0x18003211a  cmp     ebx, eax
0x18003211c  jnz     short loc_180032129
0x18003211e  inc     edi
0x180032120  cmp     edi, [rsi+4]
0x180032123  jl      short loc_180032104
0x180032125  xor     eax, eax
0x180032127  jmp     short loc_18003212E
0x180032129  mov     eax, 1
0x18003212e  mov     rbx, [rsp+28h+arg_0]
0x180032133  mov     rsi, [rsp+28h+arg_8]
0x180032138  mov     rdi, [rsp+28h+arg_10]
0x18003213d  add     rsp, 20h
0x180032141  pop     r14
0x180032143  retn
```
