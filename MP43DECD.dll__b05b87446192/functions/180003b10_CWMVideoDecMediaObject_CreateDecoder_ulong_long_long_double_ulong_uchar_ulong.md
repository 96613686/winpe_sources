# CWMVideoDecMediaObject::CreateDecoder(ulong,long,long,double,ulong,uchar *,ulong)

- ea: `0x180003b10`
- end: `0x180003ba9`
- name: `?CreateDecoder@CWMVideoDecMediaObject@@IEAAPEAVSessionFrameDecoder@@KJJNKPEAEK@Z`
- size: `153`
- prototype: `struct SessionFrameDecoder *__fastcall(CWMVideoDecMediaObject *this, unsigned int, int, int, double)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180004ffc`
- `0x180007800`

## callees

- `0x18000142c`
- `0x180003b10`
- `0x180009188`
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
  _QWORD *v8; // rax
  void (__fastcall ***v9)(_QWORD, __int64); // rbx
  unsigned int v10; // edx

  v8 = operator new(0x28u);
  v9 = (void (__fastcall ***)(_QWORD, __int64))v8;
  if ( !v8 )
    return 0;
  v8[4] = 0;
  *v8 = &SessionFrameDecoder::`vftable';
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
  if ( SessionFrameDecoder::Init((SessionFrameDecoder *)v8, v10, a5, a3, a4) < 0 )
  {
    (**v9)(v9, 1);
    return 0;
  }
  return (struct SessionFrameDecoder *)v9;
}

```

## disassembly

```asm
0x180003b10  push    rbx
0x180003b12  push    rbp
0x180003b13  push    rsi
0x180003b14  push    rdi
0x180003b15  sub     rsp, 38h
0x180003b19  mov     ecx, 28h ; '('; Size
0x180003b1e  mov     esi, r9d
0x180003b21  mov     ebp, r8d
0x180003b24  mov     edi, edx
0x180003b26  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003b2b  mov     rbx, rax
0x180003b2e  test    rax, rax
0x180003b31  jz      short loc_180003B99
0x180003b33  mov     qword ptr [rbx+20h], 0
0x180003b3b  lea     rax, ??_7SessionFrameDecoder@@6B@; const SessionFrameDecoder::`vftable'
0x180003b42  mov     [rbx], rax
0x180003b45  mov     qword ptr [rbx+18h], 0
0x180003b4d  cmp     edi, 50564D57h
0x180003b53  jz      short loc_180003B65
0x180003b55  cmp     edi, 32505657h
0x180003b5b  mov     edx, 41564D57h
0x180003b60  cmovnz  edx, edi
0x180003b63  jmp     short loc_180003B6A
0x180003b65  mov     edx, 33564D57h; unsigned int
0x180003b6a  movsd   xmm2, [rsp+58h+arg_20]; double
0x180003b73  mov     r9d, ebp; int
0x180003b76  mov     rcx, rbx; this
0x180003b79  mov     [rsp+58h+var_38], esi; int
0x180003b7d  call    ?Init@SessionFrameDecoder@@QEAAJKNJJ@Z; SessionFrameDecoder::Init(ulong,double,long,long)
0x180003b82  test    eax, eax
0x180003b84  jns     short loc_180003BA4
0x180003b86  mov     rax, [rbx]
0x180003b89  mov     edx, 1
0x180003b8e  mov     rcx, rbx
0x180003b91  mov     rax, [rax]
0x180003b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b99  xor     eax, eax
0x180003b9b  add     rsp, 38h
0x180003b9f  pop     rdi
0x180003ba0  pop     rsi
0x180003ba1  pop     rbp
0x180003ba2  pop     rbx
0x180003ba3  retn
0x180003ba4  mov     rax, rbx
0x180003ba7  jmp     short loc_180003B9B
```
