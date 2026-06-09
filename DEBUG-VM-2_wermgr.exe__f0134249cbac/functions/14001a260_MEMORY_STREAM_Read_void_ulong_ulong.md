# MEMORY_STREAM::Read(void *,ulong,ulong *)

- ea: `0x14001a260`
- end: `0x14001a2c8`
- name: `?Read@MEMORY_STREAM@@UEAAJPEAXKPEAK@Z`
- size: `104`
- prototype: `int(MEMORY_STREAM *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14001a260`
- `0x14001c9a8`

## pseudocode

```c
bool __fastcall MEMORY_STREAM::Read(MEMORY_STREAM *this, void *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v7; // ecx
  unsigned int v8; // ebx
  bool result; // al

  if ( a4 )
    *a4 = 0;
  v7 = *((_DWORD *)this + 5);
  v8 = v7 < *((_DWORD *)this + 4) ? *((_DWORD *)this + 4) - v7 : 0;
  if ( !v8 )
    return 1;
  if ( a3 < v8 )
    v8 = a3;
  memcpy_0(a2, (const void *)(*((_QWORD *)this + 1) + v7), v8);
  *((_DWORD *)this + 5) += v8;
  result = 0;
  if ( a4 )
  {
    *a4 = v8;
    return v8 < a3;
  }
  return result;
}

```

## disassembly

```asm
0x14001a260  push    rbx
0x14001a262  push    rbp
0x14001a263  push    rsi
0x14001a264  push    rdi
0x14001a265  sub     rsp, 28h
0x14001a269  mov     rdi, r9
0x14001a26c  mov     ebp, r8d
0x14001a26f  mov     r9, rdx
0x14001a272  mov     rsi, rcx
0x14001a275  test    rdi, rdi
0x14001a278  jz      short loc_14001A280
0x14001a27a  mov     dword ptr [rdi], 0
0x14001a280  mov     ecx, [rcx+14h]
0x14001a283  mov     eax, [rsi+10h]
0x14001a286  sub     eax, ecx
0x14001a288  cmp     ecx, [rsi+10h]
0x14001a28b  sbb     ebx, ebx
0x14001a28d  and     ebx, eax
0x14001a28f  jz      short loc_14001A2BA
0x14001a291  mov     edx, ecx
0x14001a293  cmp     ebp, ebx
0x14001a295  mov     rcx, r9; void *
0x14001a298  cmovb   ebx, ebp
0x14001a29b  add     rdx, [rsi+8]; Src
0x14001a29f  mov     r8d, ebx; Size
0x14001a2a2  call    memcpy_0
0x14001a2a7  add     [rsi+14h], ebx
0x14001a2aa  xor     eax, eax
0x14001a2ac  test    rdi, rdi
0x14001a2af  jz      short loc_14001A2BF
0x14001a2b1  cmp     ebx, ebp
0x14001a2b3  mov     [rdi], ebx
0x14001a2b5  setb    al
0x14001a2b8  jmp     short loc_14001A2BF
0x14001a2ba  mov     eax, 1
0x14001a2bf  add     rsp, 28h
0x14001a2c3  pop     rdi
0x14001a2c4  pop     rsi
0x14001a2c5  pop     rbp
0x14001a2c6  pop     rbx
0x14001a2c7  retn
```
