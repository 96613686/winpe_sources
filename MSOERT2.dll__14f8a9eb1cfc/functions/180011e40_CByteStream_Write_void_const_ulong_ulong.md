# CByteStream::Write(void const *,ulong,ulong *)

- ea: `0x180011e40`
- end: `0x180011ec3`
- name: `?Write@CByteStream@@UEAAJPEBXKPEAK@Z`
- size: `131`
- prototype: `int(CByteStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180011e40`
- `0x180011ecc`
- `0x180012f82`

## pseudocode

```c
__int64 __fastcall CByteStream::Write(CByteStream *this, const void *a2, unsigned int a3, unsigned int *a4)
{
  size_t v4; // rsi
  unsigned int v7; // r8d
  int v9; // edi
  unsigned int v10; // eax

  v4 = a3;
  v7 = a3 + *((_DWORD *)this + 3);
  if ( v7 < (unsigned int)v4 || v7 >= 0xFFFFFFFE )
  {
    return (unsigned int)-2147024882;
  }
  else
  {
    v9 = 0;
    if ( v7 + 2 <= *((_DWORD *)this + 4) || (v9 = CByteStream::_HrGrowBuffer(this, v4, v7 + 256), v9 >= 0) )
    {
      memcpy_0((void *)(*((_QWORD *)this + 3) + *((unsigned int *)this + 5)), a2, v4);
      *((_DWORD *)this + 5) += v4;
      v10 = *((_DWORD *)this + 5);
      if ( v10 > *((_DWORD *)this + 3) )
        *((_DWORD *)this + 3) = v10;
      if ( a4 )
        *a4 = v4;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180011e40  push    rbx
0x180011e42  push    rbp
0x180011e43  push    rsi
0x180011e44  push    rdi
0x180011e45  push    r14
0x180011e47  sub     rsp, 20h
0x180011e4b  mov     esi, r8d
0x180011e4e  mov     r14, r9
0x180011e51  mov     r8d, [rcx+0Ch]
0x180011e55  mov     rbp, rdx
0x180011e58  add     r8d, esi
0x180011e5b  mov     rbx, rcx
0x180011e5e  cmp     r8d, esi
0x180011e61  jb      short loc_180011EB1
0x180011e63  lea     eax, [r8+2]
0x180011e67  cmp     eax, 2
0x180011e6a  jb      short loc_180011EB1
0x180011e6c  xor     edi, edi
0x180011e6e  cmp     eax, [rcx+10h]
0x180011e71  jbe     short loc_180011E87
0x180011e73  add     r8d, 100h; unsigned int
0x180011e7a  mov     edx, esi; unsigned int
0x180011e7c  call    ?_HrGrowBuffer@CByteStream@@AEAAJKK@Z; CByteStream::_HrGrowBuffer(ulong,ulong)
0x180011e81  mov     edi, eax
0x180011e83  test    eax, eax
0x180011e85  js      short loc_180011EB6
0x180011e87  mov     ecx, [rbx+14h]
0x180011e8a  mov     r8, rsi; Size
0x180011e8d  add     rcx, [rbx+18h]; void *
0x180011e91  mov     rdx, rbp; Src
0x180011e94  call    memcpy_0
0x180011e99  add     [rbx+14h], esi
0x180011e9c  mov     eax, [rbx+14h]
0x180011e9f  cmp     eax, [rbx+0Ch]
0x180011ea2  jbe     short loc_180011EA7
0x180011ea4  mov     [rbx+0Ch], eax
0x180011ea7  test    r14, r14
0x180011eaa  jz      short loc_180011EB6
0x180011eac  mov     [r14], esi
0x180011eaf  jmp     short loc_180011EB6
0x180011eb1  mov     edi, 8007000Eh
0x180011eb6  mov     eax, edi
0x180011eb8  add     rsp, 20h
0x180011ebc  pop     r14
0x180011ebe  pop     rdi
0x180011ebf  pop     rsi
0x180011ec0  pop     rbp
0x180011ec1  pop     rbx
0x180011ec2  retn
```
