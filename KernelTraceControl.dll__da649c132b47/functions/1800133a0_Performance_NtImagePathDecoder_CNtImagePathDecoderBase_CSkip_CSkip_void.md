# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip::~CSkip(void)

- ea: `0x1800133a0`
- end: `0x1800133d1`
- name: `??1CSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAA@XZ`
- size: `49`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *__hidden this)`
- caller_count: `17`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180027d2b`
- `0x180027d37`
- `0x180027d9f`
- `0x180027dab`
- `0x180027e16`
- `0x180027e22`
- `0x180027e55`
- `0x180027e61`
- `0x180027ebc`
- `0x180027ecc`
- `0x18002864c`
- `0x1800286b8`
- `0x180028758`
- `0x1800287dc`
- `0x180028854`
- `0x180028eb0`
- `0x180028efe`

## callees

- `0x1800133a0`
- `0x1800268f4`

## pseudocode

```c
void __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip::~CSkip(void **this)
{
  if ( (unsigned __int64)this[4] >= 8 )
    operator delete(this[1]);
  this[4] = (void *)7;
  this[3] = 0;
  *((_WORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x1800133a0  push    rbx
0x1800133a2  sub     rsp, 20h
0x1800133a6  cmp     qword ptr [rcx+20h], 8
0x1800133ab  mov     rbx, rcx
0x1800133ae  jb      short loc_1800133B9
0x1800133b0  mov     rcx, [rcx+8]; Block
0x1800133b4  call    ??3@YAXPEAX@Z
0x1800133b9  xor     eax, eax
0x1800133bb  mov     qword ptr [rbx+20h], 7
0x1800133c3  mov     [rbx+18h], rax
0x1800133c7  mov     [rbx+8], ax
0x1800133cb  add     rsp, 20h
0x1800133cf  pop     rbx
0x1800133d0  retn
```
