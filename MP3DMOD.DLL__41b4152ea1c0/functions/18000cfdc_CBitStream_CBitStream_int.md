# CBitStream::CBitStream(int)

- ea: `0x18000cfdc`
- end: `0x18000d04c`
- name: `??0CBitStream@@QEAA@H@Z`
- size: `112`
- prototype: `CBitStream *__fastcall(CBitStream *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cd94`
- `0x18000dff0`

## callees

- `0x18000cfdc`
- `0x18000e2bc`

## pseudocode

```c
CBitStream *__fastcall CBitStream::CBitStream(CBitStream *this, int a2)
{
  int i; // ecx
  CBitStream *result; // rax

  *(_QWORD *)this = &CBitStream::`vftable';
  for ( i = 0; i < 16; ++i )
  {
    if ( 1 << i >= a2 )
      break;
  }
  *((_DWORD *)this + 4) = 1 << i;
  *((_DWORD *)this + 5) = 8 * (1 << i);
  *((_QWORD *)this + 6) = operator new(1 << i);
  result = this;
  *((_QWORD *)this + 1) = 0;
  *((_BYTE *)this + 56) = 1;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_BYTE *)this + 40) = 0;
  return result;
}

```

## disassembly

```asm
0x18000cfdc  push    rbx
0x18000cfde  sub     rsp, 20h
0x18000cfe2  lea     rax, ??_7CBitStream@@6B@; const CBitStream::`vftable'
0x18000cfe9  mov     rbx, rcx
0x18000cfec  mov     [rcx], rax
0x18000cfef  xor     ecx, ecx
0x18000cff1  mov     eax, 1
0x18000cff6  shl     eax, cl
0x18000cff8  cmp     eax, edx
0x18000cffa  jge     short loc_18000D003
0x18000cffc  inc     ecx
0x18000cffe  cmp     ecx, 10h
0x18000d001  jl      short loc_18000CFF1
0x18000d003  mov     edx, 1
0x18000d008  shl     edx, cl
0x18000d00a  movsxd  rcx, edx; Size
0x18000d00d  mov     [rbx+10h], edx
0x18000d010  lea     eax, ds:0[rdx*8]
0x18000d017  mov     [rbx+14h], eax
0x18000d01a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d01f  mov     [rbx+30h], rax
0x18000d023  mov     rax, rbx
0x18000d026  mov     qword ptr [rbx+8], 0
0x18000d02e  mov     byte ptr [rbx+38h], 1
0x18000d032  mov     qword ptr [rbx+18h], 0
0x18000d03a  mov     qword ptr [rbx+20h], 0
0x18000d042  mov     byte ptr [rbx+28h], 0
0x18000d046  add     rsp, 20h
0x18000d04a  pop     rbx
0x18000d04b  retn
```
