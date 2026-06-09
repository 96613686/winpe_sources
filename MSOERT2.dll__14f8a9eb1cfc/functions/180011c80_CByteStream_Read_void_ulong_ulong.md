# CByteStream::Read(void *,ulong,ulong *)

- ea: `0x180011c80`
- end: `0x180011cec`
- name: `?Read@CByteStream@@UEAAJPEAXKPEAK@Z`
- size: `108`
- prototype: `int(CByteStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800090b0`

## callees

- `0x180011c80`
- `0x180012f82`

## pseudocode

```c
__int64 __fastcall CByteStream::Read(CByteStream *this, void *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v4; // edi
  unsigned int v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // ecx

  v4 = 0;
  v7 = -2147024809;
  if ( a2 )
  {
    v8 = *((_DWORD *)this + 3);
    v7 = 0;
    if ( v8 )
    {
      v9 = *((_DWORD *)this + 5);
      if ( v9 >= v8 )
      {
        if ( v9 > v8 )
          v7 = -2147418113;
      }
      else
      {
        v4 = v8 - v9;
        if ( a3 < v8 - v9 )
          v4 = a3;
        memcpy_0(a2, (const void *)(*((_QWORD *)this + 3) + v9), v4);
        *((_DWORD *)this + 5) += v4;
      }
    }
  }
  if ( a4 )
    *a4 = v4;
  return v7;
}

```

## disassembly

```asm
0x180011c80  push    rbx
0x180011c82  push    rsi
0x180011c83  push    rdi
0x180011c84  push    r14
0x180011c86  sub     rsp, 28h
0x180011c8a  xor     edi, edi
0x180011c8c  mov     r14, r9
0x180011c8f  mov     r9, rdx
0x180011c92  mov     rsi, rcx
0x180011c95  mov     ebx, 80070057h
0x180011c9a  test    rdx, rdx
0x180011c9d  jz      short loc_180011CD8
0x180011c9f  mov     eax, [rcx+0Ch]
0x180011ca2  xor     ebx, ebx
0x180011ca4  test    eax, eax
0x180011ca6  jz      short loc_180011CD8
0x180011ca8  mov     ecx, [rcx+14h]
0x180011cab  cmp     ecx, eax
0x180011cad  jnb     short loc_180011CD0
0x180011caf  mov     edx, ecx
0x180011cb1  mov     edi, eax
0x180011cb3  sub     edi, ecx
0x180011cb5  mov     rcx, r9; void *
0x180011cb8  cmp     r8d, edi
0x180011cbb  cmovb   edi, r8d
0x180011cbf  add     rdx, [rsi+18h]; Src
0x180011cc3  mov     r8d, edi; Size
0x180011cc6  call    memcpy_0
0x180011ccb  add     [rsi+14h], edi
0x180011cce  jmp     short loc_180011CD8
0x180011cd0  mov     edx, 8000FFFFh
0x180011cd5  cmova   ebx, edx
0x180011cd8  test    r14, r14
0x180011cdb  jz      short loc_180011CE0
0x180011cdd  mov     [r14], edi
0x180011ce0  mov     eax, ebx
0x180011ce2  add     rsp, 28h
0x180011ce6  pop     r14
0x180011ce8  pop     rdi
0x180011ce9  pop     rsi
0x180011cea  pop     rbx
0x180011ceb  retn
```
