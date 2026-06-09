# CWMVideoDecMediaObject::CreateDecoder(ulong,long,long,double,ulong,uchar *,ulong)

- ea: `0x180003bd0`
- end: `0x180003c69`
- name: `?CreateDecoder@CWMVideoDecMediaObject@@IEAAPEAVSessionFrameDecoder@@KJJNKPEAEK@Z`
- size: `153`
- prototype: `struct SessionFrameDecoder *__fastcall(CWMVideoDecMediaObject *this, unsigned int, int, int, double)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800050bc`
- `0x1800078c0`

## callees

- `0x18000145c`
- `0x180003bd0`
- `0x180009248`
- `0x180022010`

## pseudocode

```c
struct SessionFrameDecoder *__fastcall CWMVideoDecMediaObject::CreateDecoder(
        CWMVideoDecMediaObject *this,
        unsigned int a2,
        int a3,
        int a4,
        double a5)
{
  void (__fastcall ***v8)(_QWORD, __int64); // rax
  void (__fastcall ***v9)(_QWORD, __int64); // rbx
  unsigned int v10; // edx

  v8 = (void (__fastcall ***)(_QWORD, __int64))operator new(0x28u);
  v9 = v8;
  if ( !v8 )
    return 0;
  v8[4] = 0;
  *v8 = (void (__fastcall **)(_QWORD, __int64))&SessionFrameDecoder::`vftable';
  v8[3] = 0;
  if ( a2 == 1347833175 )
  {
    v10 = 861293911;
  }
  else
  {
    v10 = 1096174935;
    if ( a2 != 844125783 )
      v10 = a2;
  }
  if ( (int)SessionFrameDecoder::Init((struct CInputBitStream **)v8, v10, a5, a3, a4) < 0 )
  {
    (**v9)(v9, 1);
    return 0;
  }
  return (struct SessionFrameDecoder *)v9;
}

```

## disassembly

```asm
0x180003bd0  push    rbx
0x180003bd2  push    rbp
0x180003bd3  push    rsi
0x180003bd4  push    rdi
0x180003bd5  sub     rsp, 38h
0x180003bd9  mov     ecx, 28h ; '('; Size
0x180003bde  mov     esi, r9d
0x180003be1  mov     ebp, r8d
0x180003be4  mov     edi, edx
0x180003be6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003beb  mov     rbx, rax
0x180003bee  test    rax, rax
0x180003bf1  jz      short loc_180003C59
0x180003bf3  mov     qword ptr [rbx+20h], 0
0x180003bfb  lea     rax, ??_7SessionFrameDecoder@@6B@; const SessionFrameDecoder::`vftable'
0x180003c02  mov     [rbx], rax
0x180003c05  mov     qword ptr [rbx+18h], 0
0x180003c0d  cmp     edi, 50564D57h
0x180003c13  jz      short loc_180003C25
0x180003c15  cmp     edi, 32505657h
0x180003c1b  mov     edx, 41564D57h
0x180003c20  cmovnz  edx, edi
0x180003c23  jmp     short loc_180003C2A
0x180003c25  mov     edx, 33564D57h; unsigned int
0x180003c2a  movsd   xmm2, [rsp+58h+arg_20]; double
0x180003c33  mov     r9d, ebp; int
0x180003c36  mov     rcx, rbx; this
0x180003c39  mov     [rsp+58h+var_38], esi; int
0x180003c3d  call    ?Init@SessionFrameDecoder@@QEAAJKNJJ@Z; SessionFrameDecoder::Init(ulong,double,long,long)
0x180003c42  test    eax, eax
0x180003c44  jns     short loc_180003C64
0x180003c46  mov     rax, [rbx]
0x180003c49  mov     edx, 1
0x180003c4e  mov     rcx, rbx
0x180003c51  mov     rax, [rax]
0x180003c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c59  xor     eax, eax
0x180003c5b  add     rsp, 38h
0x180003c5f  pop     rdi
0x180003c60  pop     rsi
0x180003c61  pop     rbp
0x180003c62  pop     rbx
0x180003c63  retn
0x180003c64  mov     rax, rbx
0x180003c67  jmp     short loc_180003C5B
```
