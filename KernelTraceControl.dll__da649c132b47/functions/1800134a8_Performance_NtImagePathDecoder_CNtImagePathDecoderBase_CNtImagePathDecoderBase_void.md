# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::~CNtImagePathDecoderBase(void)

- ea: `0x1800134a8`
- end: `0x180013598`
- name: `??1CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAA@XZ`
- size: `240`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CNtImagePathDecoderBase *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180009e6c`
- `0x18000f658`
- `0x180016ad0`
- `0x1800171b4`
- `0x180017260`
- `0x180027edc`

## callees

- `0x1800132ec`
- `0x1800134a8`
- `0x1800268f4`

## pseudocode

```c
void __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::~CNtImagePathDecoderBase(void **this)
{
  void **v2; // rdi
  void **v3; // rsi
  void *v4; // rdx

  if ( (unsigned __int64)this[17] >= 8 )
    operator delete(this[14]);
  this[17] = (void *)7;
  this[16] = 0;
  *((_WORD *)this + 56) = 0;
  if ( (unsigned __int64)this[12] >= 8 )
    operator delete(this[9]);
  this[12] = (void *)7;
  this[11] = 0;
  *((_WORD *)this + 36) = 0;
  v2 = (void **)this[5];
  if ( v2 )
  {
    v3 = (void **)this[6];
    while ( v2 != v3 )
    {
      if ( (unsigned __int64)v2[4] >= 8 )
        operator delete(v2[1]);
      v2[4] = (void *)7;
      v2[3] = 0;
      *((_WORD *)v2 + 4) = 0;
      v2 += 5;
    }
    operator delete(this[5]);
  }
  this[5] = 0;
  this[6] = 0;
  this[7] = 0;
  v4 = this[1];
  if ( v4 )
  {
    std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Destroy(this, v4, this[2]);
    operator delete(this[1]);
  }
  this[1] = 0;
  this[2] = 0;
  this[3] = 0;
}

```

## disassembly

```asm
0x1800134a8  mov     rax, rsp
0x1800134ab  mov     [rax+8], rbx
0x1800134af  mov     [rax+10h], rbp
0x1800134b3  mov     [rax+18h], rsi
0x1800134b7  mov     [rax+20h], rdi
0x1800134bb  push    r14
0x1800134bd  sub     rsp, 20h
0x1800134c1  cmp     qword ptr [rcx+88h], 8
0x1800134c9  mov     rbx, rcx
0x1800134cc  jb      short loc_1800134D7
0x1800134ce  mov     rcx, [rcx+70h]; Block
0x1800134d2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800134d7  xor     ebp, ebp
0x1800134d9  mov     r14d, 7
0x1800134df  mov     [rbx+88h], r14
0x1800134e6  mov     [rbx+80h], rbp
0x1800134ed  mov     [rbx+70h], bp
0x1800134f1  cmp     qword ptr [rbx+60h], 8
0x1800134f6  jb      short loc_180013501
0x1800134f8  mov     rcx, [rbx+48h]; Block
0x1800134fc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013501  mov     [rbx+60h], r14
0x180013505  mov     [rbx+58h], rbp
0x180013509  mov     [rbx+48h], bp
0x18001350d  mov     rdi, [rbx+28h]
0x180013511  test    rdi, rdi
0x180013514  jz      short loc_18001354A
0x180013516  mov     rsi, [rbx+30h]
0x18001351a  jmp     short loc_18001353C
0x18001351c  cmp     qword ptr [rdi+20h], 8
0x180013521  jb      short loc_18001352C
0x180013523  mov     rcx, [rdi+8]; Block
0x180013527  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001352c  mov     [rdi+20h], r14
0x180013530  mov     [rdi+18h], rbp
0x180013534  mov     [rdi+8], bp
0x180013538  add     rdi, 28h ; '('
0x18001353c  cmp     rdi, rsi
0x18001353f  jnz     short loc_18001351C
0x180013541  mov     rcx, [rbx+28h]; Block
0x180013545  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001354a  mov     [rbx+28h], rbp
0x18001354e  mov     [rbx+30h], rbp
0x180013552  mov     [rbx+38h], rbp
0x180013556  mov     rdx, [rbx+8]
0x18001355a  test    rdx, rdx
0x18001355d  jz      short loc_180013571
0x18001355f  mov     r8, [rbx+10h]
0x180013563  call    ?_Destroy@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@IEAAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@0@Z; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Destroy(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)
0x180013568  mov     rcx, [rbx+8]; Block
0x18001356c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013571  mov     rsi, [rsp+28h+arg_10]
0x180013576  mov     rdi, [rsp+28h+arg_18]
0x18001357b  mov     [rbx+8], rbp
0x18001357f  mov     [rbx+10h], rbp
0x180013583  mov     [rbx+18h], rbp
0x180013587  mov     rbx, [rsp+28h+arg_0]
0x18001358c  mov     rbp, [rsp+28h+arg_8]
0x180013591  add     rsp, 20h
0x180013595  pop     r14
0x180013597  retn
```
