# ReadBuffer::Init(Tracker *,ReadBuffer *,int *)

- ea: `0x1400013c4`
- end: `0x140001466`
- name: `?Init@ReadBuffer@@QEAAJPEAVTracker@@PEAV1@PEAH@Z`
- size: `162`
- prototype: `__int64 __fastcall(ReadBuffer *__hidden this, struct Tracker *, struct ReadBuffer *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140003a9c`
- `0x140004ba4`

## callees

- `0x1400013c4`
- `0x140004f58`
- `0x140006494`

## pseudocode

```c
__int64 __fastcall ReadBuffer::Init(ReadBuffer *this, struct Tracker *a2, struct ReadBuffer *a3, int *a4)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v8; // edi
  int v9; // eax
  void *v10; // rax

  v4 = -1;
  *(_QWORD *)this = a2;
  v5 = 0;
  *((_DWORD *)this + 12) = -1;
  *((_DWORD *)this + 7) = -1;
  *((_DWORD *)this + 13) = -1;
  *((_DWORD *)this + 14) = -1;
  *((_DWORD *)this + 17) = -1;
  if ( a3 )
  {
    v8 = *((_DWORD *)a3 + 5) - *((_DWORD *)a3 + 6);
    if ( v8 > 0 )
      v4 = *((_DWORD *)a3 + 5) - *((_DWORD *)a3 + 6);
    *a4 = v4;
  }
  else
  {
    v8 = 0;
  }
  v9 = 1024;
  if ( v8 >= 1024 )
    v9 = v8;
  *((_DWORD *)this + 4) = v9;
  v10 = MemAlloc(v9 + 1);
  *((_QWORD *)this + 1) = v10;
  if ( v10 )
  {
    if ( v8 > 0 )
      memcpy_0(v10, (const void *)(*((_QWORD *)a3 + 1) + *((int *)this + 6)), v8 + 1);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v5;
}

```

## disassembly

```asm
0x1400013c4  mov     [rsp+arg_0], rbx
0x1400013c9  mov     [rsp+arg_8], rbp
0x1400013ce  mov     [rsp+arg_10], rsi
0x1400013d3  push    rdi
0x1400013d4  sub     rsp, 20h
0x1400013d8  or      eax, 0FFFFFFFFh
0x1400013db  mov     [rcx], rdx
0x1400013de  xor     ebx, ebx
0x1400013e0  mov     [rcx+30h], eax
0x1400013e3  mov     [rcx+1Ch], eax
0x1400013e6  mov     rbp, r8
0x1400013e9  mov     [rcx+34h], eax
0x1400013ec  mov     rsi, rcx
0x1400013ef  mov     [rcx+38h], eax
0x1400013f2  mov     [rcx+44h], eax
0x1400013f5  test    r8, r8
0x1400013f8  jz      short loc_14000140C
0x1400013fa  mov     edi, [r8+14h]
0x1400013fe  sub     edi, [r8+18h]
0x140001402  test    edi, edi
0x140001404  cmovg   eax, edi
0x140001407  mov     [r9], eax
0x14000140a  jmp     short loc_14000140E
0x14000140c  mov     edi, ebx
0x14000140e  mov     eax, 400h
0x140001413  cmp     edi, eax
0x140001415  cmovge  eax, edi
0x140001418  mov     [rcx+10h], eax
0x14000141b  inc     eax
0x14000141d  movsxd  rcx, eax; unsigned __int64
0x140001420  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x140001425  mov     [rsi+8], rax
0x140001429  test    rax, rax
0x14000142c  jnz     short loc_140001435
0x14000142e  mov     ebx, 8007000Eh
0x140001433  jmp     short loc_14000144F
0x140001435  test    edi, edi
0x140001437  jle     short loc_14000144F
0x140001439  movsxd  rdx, dword ptr [rsi+18h]
0x14000143d  lea     ecx, [rdi+1]
0x140001440  add     rdx, [rbp+8]; Src
0x140001444  movsxd  r8, ecx; Size
0x140001447  mov     rcx, rax; void *
0x14000144a  call    memcpy_0
0x14000144f  mov     rbp, [rsp+28h+arg_8]
0x140001454  mov     eax, ebx
0x140001456  mov     rbx, [rsp+28h+arg_0]
0x14000145b  mov     rsi, [rsp+28h+arg_10]
0x140001460  add     rsp, 20h
0x140001464  pop     rdi
0x140001465  retn
```
