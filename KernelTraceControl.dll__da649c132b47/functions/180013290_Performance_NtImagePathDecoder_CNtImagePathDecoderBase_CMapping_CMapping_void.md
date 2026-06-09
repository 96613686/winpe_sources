# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping::~CMapping(void)

- ea: `0x180013290`
- end: `0x1800132ea`
- name: `??1CMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAA@XZ`
- size: `90`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800287e8`
- `0x180028860`

## callees

- `0x180013290`
- `0x1800268f4`

## pseudocode

```c
void __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping::~CMapping(void **this)
{
  if ( (unsigned __int64)this[9] >= 8 )
    operator delete(this[6]);
  this[9] = (void *)7;
  this[8] = 0;
  *((_WORD *)this + 24) = 0;
  if ( (unsigned __int64)this[4] >= 8 )
    operator delete(this[1]);
  this[4] = (void *)7;
  this[3] = 0;
  *((_WORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x180013290  mov     [rsp+arg_0], rbx
0x180013295  push    rdi
0x180013296  sub     rsp, 20h
0x18001329a  cmp     qword ptr [rcx+48h], 8
0x18001329f  mov     rbx, rcx
0x1800132a2  jb      short loc_1800132AD
0x1800132a4  mov     rcx, [rcx+30h]; Block
0x1800132a8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800132ad  xor     edi, edi
0x1800132af  mov     qword ptr [rbx+48h], 7
0x1800132b7  mov     [rbx+40h], rdi
0x1800132bb  mov     [rbx+30h], di
0x1800132bf  cmp     qword ptr [rbx+20h], 8
0x1800132c4  jb      short loc_1800132CF
0x1800132c6  mov     rcx, [rbx+8]; Block
0x1800132ca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800132cf  mov     qword ptr [rbx+20h], 7
0x1800132d7  mov     [rbx+18h], rdi
0x1800132db  mov     [rbx+8], di
0x1800132df  mov     rbx, [rsp+28h+arg_0]
0x1800132e4  add     rsp, 20h
0x1800132e8  pop     rdi
0x1800132e9  retn
```
