# std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)

- ea: `0x14000b16c`
- end: `0x14000b1e4`
- name: `?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ`
- size: `120`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140006064`
- `0x1400066fc`
- `0x1400083bc`
- `0x140008524`
- `0x140008784`
- `0x1400098b0`
- `0x140009fa4`
- `0x14000f54c`

## callees

- `0x140001934`
- `0x14000b16c`

## pseudocode

```c
void __fastcall std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(_QWORD *a1)
{
  _BYTE *v1; // rax
  __int64 v3; // rdx
  _BYTE *v4; // rcx
  unsigned __int64 v5; // rdx
  unsigned __int64 i; // r8
  _BYTE *v7; // rcx

  v1 = (_BYTE *)*a1;
  if ( *a1 )
  {
    v3 = a1[2];
    v4 = (_BYTE *)*a1;
    v5 = v3 - (_QWORD)v1;
    for ( i = v5; i; --i )
      *v4++ = 0;
    if ( v5 < 0x1000 )
    {
      v7 = v1;
    }
    else
    {
      v7 = (_BYTE *)*((_QWORD *)v1 - 1);
      if ( (unsigned __int64)(v1 - v7 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v7);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x14000b16c  push    rbx
0x14000b16e  sub     rsp, 20h
0x14000b172  mov     rax, [rcx]
0x14000b175  mov     rbx, rcx
0x14000b178  test    rax, rax
0x14000b17b  jz      short loc_14000B1DE
0x14000b17d  mov     rdx, [rcx+10h]
0x14000b181  mov     rcx, rax
0x14000b184  sub     rdx, rax; unsigned __int64
0x14000b187  mov     r8, rdx
0x14000b18a  jz      short loc_14000B198
0x14000b18c  mov     byte ptr [rcx], 0
0x14000b18f  inc     rcx
0x14000b192  sub     r8, 1
0x14000b196  jnz     short loc_14000B18C
0x14000b198  cmp     rdx, 1000h
0x14000b19f  jb      short loc_14000B1BF
0x14000b1a1  mov     rcx, [rax-8]
0x14000b1a5  sub     rax, rcx
0x14000b1a8  sub     rax, 8
0x14000b1ac  cmp     rax, 1Fh
0x14000b1b0  ja      short loc_14000B1B8
0x14000b1b2  add     rdx, 27h ; '''
0x14000b1b6  jmp     short loc_14000B1C2
0x14000b1b8  mov     ecx, 5
0x14000b1bd  int     29h; Win8: RtlFailFast(ecx)
0x14000b1bf  mov     rcx, rax; void *
0x14000b1c2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000b1c7  mov     qword ptr [rbx], 0
0x14000b1ce  mov     qword ptr [rbx+8], 0
0x14000b1d6  mov     qword ptr [rbx+10h], 0
0x14000b1de  add     rsp, 20h
0x14000b1e2  pop     rbx
0x14000b1e3  retn
```
