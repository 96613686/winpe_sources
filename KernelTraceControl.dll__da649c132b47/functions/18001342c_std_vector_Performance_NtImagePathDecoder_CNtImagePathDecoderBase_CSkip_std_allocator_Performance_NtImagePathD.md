# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(void)

- ea: `0x18001342c`
- end: `0x1800134a7`
- name: `??1?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180027eac`

## callees

- `0x18001342c`
- `0x1800268f4`

## pseudocode

```c
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>(
        __int64 a1)
{
  __int64 v1; // rbx
  __int64 v3; // rsi

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    v3 = *(_QWORD *)(a1 + 16);
    while ( v1 != v3 )
    {
      if ( *(_QWORD *)(v1 + 32) >= 8u )
        operator delete(*(void **)(v1 + 8));
      *(_QWORD *)(v1 + 32) = 7;
      *(_QWORD *)(v1 + 24) = 0;
      *(_WORD *)(v1 + 8) = 0;
      v1 += 40;
    }
    operator delete(*(void **)(a1 + 8));
  }
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
}

```

## disassembly

```asm
0x18001342c  mov     [rsp+arg_0], rbx
0x180013431  mov     [rsp+arg_8], rbp
0x180013436  mov     [rsp+arg_10], rsi
0x18001343b  push    rdi
0x18001343c  sub     rsp, 20h
0x180013440  mov     rbx, [rcx+8]
0x180013444  xor     ebp, ebp
0x180013446  mov     rdi, rcx
0x180013449  test    rbx, rbx
0x18001344c  jz      short loc_180013486
0x18001344e  mov     rsi, [rcx+10h]
0x180013452  jmp     short loc_180013478
0x180013454  cmp     qword ptr [rbx+20h], 8
0x180013459  jb      short loc_180013464
0x18001345b  mov     rcx, [rbx+8]; Block
0x18001345f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013464  mov     qword ptr [rbx+20h], 7
0x18001346c  mov     [rbx+18h], rbp
0x180013470  mov     [rbx+8], bp
0x180013474  add     rbx, 28h ; '('
0x180013478  cmp     rbx, rsi
0x18001347b  jnz     short loc_180013454
0x18001347d  mov     rcx, [rdi+8]; Block
0x180013481  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013486  mov     rbx, [rsp+28h+arg_0]
0x18001348b  mov     rsi, [rsp+28h+arg_10]
0x180013490  mov     [rdi+8], rbp
0x180013494  mov     [rdi+10h], rbp
0x180013498  mov     [rdi+18h], rbp
0x18001349c  mov     rbp, [rsp+28h+arg_8]
0x1800134a1  add     rsp, 20h
0x1800134a5  pop     rdi
0x1800134a6  retn
```
