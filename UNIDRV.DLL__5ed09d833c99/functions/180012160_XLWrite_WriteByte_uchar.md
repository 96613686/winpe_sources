# XLWrite::WriteByte(uchar)

- ea: `0x180012160`
- end: `0x180012231`
- name: `?WriteByte@XLWrite@@QEAAJE@Z`
- size: `209`
- prototype: `__int64 __fastcall(XLWrite *this, char)`
- caller_count: `56`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ee10`
- `0x18000f394`
- `0x18000f498`
- `0x18000f798`
- `0x18000f844`
- `0x18000fb50`
- `0x18000fe80`
- `0x1800120ac`
- `0x180012238`
- `0x1800122c4`
- `0x180012450`
- `0x180012498`
- `0x180012850`
- `0x180012ac0`
- `0x180012c98`
- `0x180012f00`
- `0x1800136a8`
- `0x180013b70`
- `0x180014040`
- `0x1800144c0`
- `0x180014b40`
- `0x1800155e0`
- `0x180015814`
- `0x180015b9c`
- `0x180015c10`
- `0x180015f98`
- `0x18001d8e0`
- `0x18001dc4c`
- `0x18001dff8`
- `0x1800316a0`
- `0x180032180`
- `0x18003cba8`
- `0x18003d4e8`
- `0x18003e350`
- `0x18003ea0c`
- `0x18003f4d0`
- `0x180041fc4`
- `0x180043844`
- `0x180043980`
- `0x1800459b4`
- `0x180046654`
- `0x180046f3c`
- `0x18006d7ec`
- `0x18006e418`
- `0x18006e8fc`
- `0x18006e934`
- `0x18006e96c`
- `0x18006e9c0`
- `0x18006ea14`
- `0x18006ea58`

## callees

- `0x180012160`
- `0x180076660`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001220f`
- `KERNEL32!LocalFree` at `0x18001220f`
- `KERNEL32!LocalAlloc` at `0x1800121d7`
- `KERNEL32!LocalAlloc` at `0x1800121d7`

## pseudocode

```c
__int64 __fastcall XLWrite::WriteByte(XLWrite *this, char a2)
{
  __int64 v4; // rcx
  unsigned __int64 v5; // rdx
  unsigned int v7; // eax
  unsigned int v8; // esi
  char *v9; // rbp
  const void *v10; // rdx
  unsigned int v11; // eax
  void *v12; // rcx
  __int64 v13; // rax

  v4 = *((unsigned int *)this + 7);
  if ( (int)v4 + 1 >= (unsigned int)v4 )
  {
    v5 = *((unsigned int *)this + 6);
    if ( v5 < v4 + 8 )
    {
      v7 = v5 + 8;
      if ( (int)v5 + 8 < (unsigned int)v5 )
        return 2147549183LL;
      v8 = v5 + 2048;
      if ( (int)v5 + 2048 < (unsigned int)v5 || v7 > 0xFFFFF7FF )
        return 2147549183LL;
      for ( ; v8 < v7; v8 += 2048 )
        ;
      v9 = (char *)LocalAlloc(0, v8);
      if ( !v9 )
        return 2147549183LL;
      v10 = (const void *)*((_QWORD *)this + 1);
      if ( v10 )
      {
        v11 = *((_DWORD *)this + 7);
        if ( v11 )
          memcpy_0(v9, v10, v11);
        v12 = (void *)*((_QWORD *)this + 1);
        if ( v12 )
          LocalFree(v12);
      }
      v13 = *((unsigned int *)this + 7);
      *((_DWORD *)this + 6) = v8;
      *((_QWORD *)this + 2) = &v9[v13];
      *((_QWORD *)this + 1) = v9;
    }
    if ( *((_QWORD *)this + 1) )
    {
      *(_BYTE *)(*((_QWORD *)this + 2))++ = a2;
      ++*((_DWORD *)this + 7);
      return 0;
    }
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x180012160  push    rbx
0x180012162  push    rbp
0x180012163  push    rsi
0x180012164  push    rdi
0x180012165  sub     rsp, 28h
0x180012169  mov     rbx, rcx
0x18001216c  movzx   edi, dl
0x18001216f  mov     ecx, [rcx+1Ch]
0x180012172  lea     eax, [rcx+1]
0x180012175  cmp     eax, ecx
0x180012177  jb      short loc_1800121AD
0x180012179  mov     edx, [rbx+18h]
0x18001217c  lea     rax, [rcx+8]
0x180012180  cmp     rdx, rax
0x180012183  jb      short loc_1800121A6
0x180012185  cmp     qword ptr [rbx+8], 0
0x18001218a  jz      short loc_1800121AD
0x18001218c  mov     rax, [rbx+10h]
0x180012190  mov     [rax], dil
0x180012193  inc     qword ptr [rbx+10h]
0x180012197  inc     dword ptr [rbx+1Ch]
0x18001219a  xor     eax, eax
0x18001219c  add     rsp, 28h
0x1800121a0  pop     rdi
0x1800121a1  pop     rsi
0x1800121a2  pop     rbp
0x1800121a3  pop     rbx
0x1800121a4  retn
0x1800121a6  lea     eax, [rdx+8]
0x1800121a9  cmp     eax, edx
0x1800121ab  jnb     short loc_1800121B4
0x1800121ad  mov     eax, 8000FFFFh
0x1800121b2  jmp     short loc_18001219C
0x1800121b4  lea     esi, [rdx+800h]
0x1800121ba  cmp     esi, edx
0x1800121bc  jb      short loc_1800121AD
0x1800121be  cmp     eax, 0FFFFF7FFh
0x1800121c3  ja      short loc_1800121AD
0x1800121c5  cmp     esi, eax
0x1800121c7  jnb     short loc_1800121D3
0x1800121c9  add     esi, 800h
0x1800121cf  cmp     esi, eax
0x1800121d1  jb      short loc_1800121C9
0x1800121d3  mov     edx, esi; uBytes
0x1800121d5  xor     ecx, ecx; uFlags
0x1800121d7  call    cs:__imp_LocalAlloc
0x1800121de  nop     dword ptr [rax+rax+00h]
0x1800121e3  mov     rbp, rax
0x1800121e6  test    rax, rax
0x1800121e9  jz      short loc_1800121AD
0x1800121eb  mov     rdx, [rbx+8]; Src
0x1800121ef  test    rdx, rdx
0x1800121f2  jz      short loc_18001221B
0x1800121f4  mov     eax, [rbx+1Ch]
0x1800121f7  test    eax, eax
0x1800121f9  jz      short loc_180012206
0x1800121fb  mov     r8d, eax; Size
0x1800121fe  mov     rcx, rbp; void *
0x180012201  call    memcpy_0
0x180012206  mov     rcx, [rbx+8]; hMem
0x18001220a  test    rcx, rcx
0x18001220d  jz      short loc_18001221B
0x18001220f  call    cs:__imp_LocalFree
0x180012216  nop     dword ptr [rax+rax+00h]
0x18001221b  mov     eax, [rbx+1Ch]
0x18001221e  add     rax, rbp
0x180012221  mov     [rbx+18h], esi
0x180012224  mov     [rbx+10h], rax
0x180012228  mov     [rbx+8], rbp
0x18001222c  jmp     loc_180012185
```
