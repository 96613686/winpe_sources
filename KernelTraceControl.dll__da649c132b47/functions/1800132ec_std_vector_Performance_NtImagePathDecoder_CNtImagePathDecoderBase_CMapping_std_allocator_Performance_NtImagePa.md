# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::_Destroy(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)

- ea: `0x1800132ec`
- end: `0x180013364`
- name: `?_Destroy@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@IEAAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@0@Z`
- size: `120`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180012264`
- `0x18001285c`
- `0x180013364`
- `0x1800134a8`
- `0x1800287f4`
- `0x180028821`

## callees

- `0x1800132ec`
- `0x1800268f4`

## pseudocode

```c
_QWORD *__fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Destroy(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v4; // rbx
  _QWORD *result; // rax

  if ( a2 != a3 )
  {
    v4 = a2 + 9;
    do
    {
      if ( *v4 >= 8u )
        operator delete((void *)*(v4 - 3));
      *v4 = 7;
      *(v4 - 1) = 0;
      *((_WORD *)v4 - 12) = 0;
      if ( *(v4 - 5) >= 8u )
        operator delete((void *)*(v4 - 8));
      *(v4 - 5) = 7;
      *(v4 - 6) = 0;
      *((_WORD *)v4 - 32) = 0;
      v4 += 10;
      result = v4 - 9;
    }
    while ( v4 - 9 != a3 );
  }
  return result;
}

```

## disassembly

```asm
0x1800132ec  cmp     rdx, r8
0x1800132ef  jz      short locret_180013363
0x1800132f1  mov     [rsp+arg_0], rbx
0x1800132f6  mov     [rsp+arg_8], rsi
0x1800132fb  push    rdi
0x1800132fc  sub     rsp, 20h
0x180013300  mov     rdi, r8
0x180013303  lea     rbx, [rdx+48h]
0x180013307  xor     esi, esi
0x180013309  cmp     qword ptr [rbx], 8
0x18001330d  jb      short loc_180013318
0x18001330f  mov     rcx, [rbx-18h]; Block
0x180013313  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013318  mov     qword ptr [rbx], 7
0x18001331f  mov     [rbx-8], rsi
0x180013323  mov     [rbx-18h], si
0x180013327  cmp     qword ptr [rbx-28h], 8
0x18001332c  jb      short loc_180013337
0x18001332e  mov     rcx, [rbx-40h]; Block
0x180013332  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013337  mov     qword ptr [rbx-28h], 7
0x18001333f  mov     [rbx-30h], rsi
0x180013343  mov     [rbx-40h], si
0x180013347  add     rbx, 50h ; 'P'
0x18001334b  lea     rax, [rbx-48h]
0x18001334f  cmp     rax, rdi
0x180013352  jnz     short loc_180013309
0x180013354  mov     rbx, [rsp+28h+arg_0]
0x180013359  mov     rsi, [rsp+28h+arg_8]
0x18001335e  add     rsp, 20h
0x180013362  pop     rdi
0x180013363  retn
```
