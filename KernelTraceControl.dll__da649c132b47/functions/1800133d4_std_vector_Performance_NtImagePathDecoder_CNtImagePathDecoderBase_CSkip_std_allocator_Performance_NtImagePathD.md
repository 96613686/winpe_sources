# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>::_Destroy(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *)

- ea: `0x1800133d4`
- end: `0x18001342c`
- name: `?_Destroy@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@IEAAXPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@0@Z`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180028658`
- `0x180028685`

## callees

- `0x1800133d4`
- `0x1800268f4`

## pseudocode

```c
_QWORD *__fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Destroy(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v4; // rbx
  _QWORD *result; // rax

  if ( a2 != a3 )
  {
    v4 = a2 + 4;
    do
    {
      if ( *v4 >= 8u )
        operator delete((void *)*(v4 - 3));
      *v4 = 7;
      *(v4 - 1) = 0;
      *((_WORD *)v4 - 12) = 0;
      v4 += 5;
      result = v4 - 4;
    }
    while ( v4 - 4 != a3 );
  }
  return result;
}

```

## disassembly

```asm
0x1800133d4  cmp     rdx, r8
0x1800133d7  jz      short locret_18001342B
0x1800133d9  mov     [rsp+arg_0], rbx
0x1800133de  mov     [rsp+arg_8], rsi
0x1800133e3  push    rdi
0x1800133e4  sub     rsp, 20h
0x1800133e8  mov     rdi, r8
0x1800133eb  lea     rbx, [rdx+20h]
0x1800133ef  xor     esi, esi
0x1800133f1  cmp     qword ptr [rbx], 8
0x1800133f5  jb      short loc_180013400
0x1800133f7  mov     rcx, [rbx-18h]; Block
0x1800133fb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013400  mov     qword ptr [rbx], 7
0x180013407  mov     [rbx-8], rsi
0x18001340b  mov     [rbx-18h], si
0x18001340f  add     rbx, 28h ; '('
0x180013413  lea     rax, [rbx-20h]
0x180013417  cmp     rax, rdi
0x18001341a  jnz     short loc_1800133F1
0x18001341c  mov     rbx, [rsp+28h+arg_0]
0x180013421  mov     rsi, [rsp+28h+arg_8]
0x180013426  add     rsp, 20h
0x18001342a  pop     rdi
0x18001342b  retn
```
