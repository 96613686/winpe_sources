# BUFFER::Reserve(unsigned __int64,unsigned __int64)

- ea: `0x180012168`
- end: `0x180012281`
- name: `?Reserve@BUFFER@@QEAAJ_K0@Z`
- size: `281`
- prototype: `int(BUFFER *__hidden this, unsigned __int64, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180011f30`
- `0x180011fec`
- `0x1800122b8`
- `0x18001232c`

## callees

- `0x180012168`
- `0x180012288`
- `0x180012f82`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800121d7`
- `KERNEL32!HeapAlloc` at `0x1800121d7`
- `KERNEL32!HeapFree` at `0x18001225a`
- `KERNEL32!HeapFree` at `0x18001225a`
- `KERNEL32!GetProcessHeap` at `0x1800121c9`
- `KERNEL32!GetProcessHeap` at `0x18001224c`
- `KERNEL32!GetProcessHeap` at `0x1800121c9`
- `KERNEL32!GetProcessHeap` at `0x18001224c`

## pseudocode

```c
__int64 __fastcall BUFFER::Reserve(BUFFER *this, unsigned __int64 a2, unsigned __int64 a3)
{
  int v5; // eax
  SIZE_T v6; // r9
  SIZE_T v7; // rsi
  HANDLE ProcessHeap; // rax
  _BYTE *v9; // rax
  _BYTE *v10; // rbp
  size_t v11; // r8
  _BYTE *v12; // rcx
  __int64 v13; // rcx
  _BYTE *v14; // rax
  SIZE_T v15; // rdx
  __int64 v16; // rax
  _BYTE *i; // rcx
  SIZE_T v18; // rax
  void *v19; // rbx
  HANDLE v20; // rax
  unsigned __int64 v21; // [rsp+60h] [rbp+18h] BYREF

  v21 = a3;
  if ( *((_QWORD *)this + 1) >= a2 )
    return 0;
  v21 = 0;
  v5 = ULongLongMult(a2, 2u, &v21);
  v7 = v21;
  if ( v5 < 0 )
    v7 = v6;
  if ( v7 < 0x100 )
    v7 = 256;
  if ( v7 > *((_QWORD *)this + 1) && v7 >= v6 )
  {
    ProcessHeap = GetProcessHeap();
    v9 = HeapAlloc(ProcessHeap, 0, v7);
    v10 = v9;
    if ( v9 )
    {
      v11 = *((_QWORD *)this + 1);
      v12 = v9;
      if ( v11 )
      {
        memcpy_0(v9, *(const void **)this, v11);
        v13 = *((_QWORD *)this + 1);
        v14 = &v10[v13];
        v15 = v7 - v13;
        if ( v7 != v13 )
        {
          do
          {
            *v14++ = 0;
            --v15;
          }
          while ( v15 );
        }
        v16 = *((_QWORD *)this + 1);
        for ( i = *(_BYTE **)this; v16; --v16 )
          *i++ = 0;
      }
      else
      {
        v18 = v7;
        do
        {
          *v12++ = 0;
          --v18;
        }
        while ( v18 );
      }
      if ( *((_DWORD *)this + 4) )
      {
        v19 = *(void **)this;
        v20 = GetProcessHeap();
        HeapFree(v20, 0, v19);
      }
      *((_DWORD *)this + 4) = 1;
      *(_QWORD *)this = v10;
      *((_QWORD *)this + 1) = v7;
      return 0;
    }
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180012168  mov     [rsp+arg_10], r8
0x18001216d  push    rbx
0x18001216e  push    rbp
0x18001216f  push    rsi
0x180012170  push    rdi
0x180012171  sub     rsp, 28h
0x180012175  mov     r9, rdx
0x180012178  mov     rdi, rcx
0x18001217b  cmp     [rcx+8], rdx
0x18001217f  jb      short loc_180012188
0x180012181  xor     eax, eax
0x180012183  jmp     loc_180012278
0x180012188  xor     ebx, ebx
0x18001218a  lea     r8, [rsp+48h+arg_10]; unsigned __int64 *
0x18001218f  mov     rcx, r9; unsigned __int64
0x180012192  mov     [rsp+48h+arg_10], rbx
0x180012197  lea     edx, [rbx+2]; unsigned __int64
0x18001219a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001219f  mov     rsi, [rsp+48h+arg_10]
0x1800121a4  test    eax, eax
0x1800121a6  mov     eax, 100h
0x1800121ab  cmovs   rsi, r9
0x1800121af  cmp     rsi, rax
0x1800121b2  cmovb   rsi, rax
0x1800121b6  cmp     rsi, [rdi+8]
0x1800121ba  jbe     loc_180012273
0x1800121c0  cmp     rsi, r9
0x1800121c3  jb      loc_180012273
0x1800121c9  call    cs:__imp_GetProcessHeap
0x1800121cf  mov     r8, rsi; dwBytes
0x1800121d2  xor     edx, edx; dwFlags
0x1800121d4  mov     rcx, rax; hHeap
0x1800121d7  call    cs:__imp_HeapAlloc
0x1800121dd  mov     rbp, rax
0x1800121e0  test    rax, rax
0x1800121e3  jz      loc_180012273
0x1800121e9  mov     r8, [rdi+8]; Size
0x1800121ed  mov     rcx, rax; void *
0x1800121f0  test    r8, r8
0x1800121f3  jz      short loc_180012231
0x1800121f5  mov     rdx, [rdi]; Src
0x1800121f8  call    memcpy_0
0x1800121fd  mov     rcx, [rdi+8]
0x180012201  mov     rdx, rsi
0x180012204  lea     rax, [rcx+rbp]
0x180012208  sub     rdx, rcx
0x18001220b  jz      short loc_180012218
0x18001220d  mov     [rax], bl
0x18001220f  inc     rax
0x180012212  sub     rdx, 1
0x180012216  jnz     short loc_18001220D
0x180012218  mov     rax, [rdi+8]
0x18001221c  mov     rcx, [rdi]
0x18001221f  test    rax, rax
0x180012222  jz      short loc_180012244
0x180012224  mov     [rcx], bl
0x180012226  inc     rcx
0x180012229  sub     rax, 1
0x18001222d  jnz     short loc_180012224
0x18001222f  jmp     short loc_180012244
0x180012231  mov     rax, rsi
0x180012234  test    rsi, rsi
0x180012237  jz      short loc_180012244
0x180012239  mov     [rcx], bl
0x18001223b  inc     rcx
0x18001223e  sub     rax, 1
0x180012242  jnz     short loc_180012239
0x180012244  cmp     [rdi+10h], ebx
0x180012247  jz      short loc_180012260
0x180012249  mov     rbx, [rdi]
0x18001224c  call    cs:__imp_GetProcessHeap
0x180012252  mov     r8, rbx; lpMem
0x180012255  xor     edx, edx; dwFlags
0x180012257  mov     rcx, rax; hHeap
0x18001225a  call    cs:__imp_HeapFree
0x180012260  mov     dword ptr [rdi+10h], 1
0x180012267  mov     [rdi], rbp
0x18001226a  mov     [rdi+8], rsi
0x18001226e  jmp     loc_180012181
0x180012273  mov     eax, 8007000Eh
0x180012278  add     rsp, 28h
0x18001227c  pop     rdi
0x18001227d  pop     rsi
0x18001227e  pop     rbp
0x18001227f  pop     rbx
0x180012280  retn
```
