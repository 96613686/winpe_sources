# CAVIMemStream::Create(__int64,__int64)

- ea: `0x1800109a0`
- end: `0x180010ad9`
- name: `?Create@CAVIMemStream@@UEAAJ_J0@Z`
- size: `313`
- prototype: `__int64 __fastcall(CAVIMemStream *__hidden this, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010d60`

## callees

- `0x180001d0c`
- `0x1800109a0`

## import_xrefs

- `USER32!SetRect` at `0x180010a16`
- `USER32!SetRect` at `0x180010a16`

## pseudocode

```c
__int64 __fastcall CAVIMemStream::Create(CAVIMemStream *this, int a2, _DWORD *a3)
{
  int v5; // edx
  _DWORD *i; // rcx
  __int64 v7; // rdi
  unsigned int v8; // eax
  unsigned int v9; // eax

  *((_QWORD *)this + 2) = a3;
  if ( a2 == 8 )
  {
    *((_QWORD *)this + 3) = a3;
    if ( !a3[5] )
      a3[4] = 0;
    memset_0((char *)this + 52, 0, 0xCCu);
    *((_DWORD *)this + 13) = 1935960438;
    *((_DWORD *)this + 21) = 1;
    *((_DWORD *)this + 18) = 1;
    *((_DWORD *)this + 19) = 15;
    *((_DWORD *)this + 25) = 0;
    SetRect((LPRECT)((char *)this + 104), 0, 0, a3[1], a3[2]);
    v5 = *a3 + 4 * a3[8];
    *((_QWORD *)this + 5) = *((_QWORD *)this + 2) + v5;
    *((_DWORD *)this + 8) = v5;
    *((_DWORD *)this + 12) = a3[5];
  }
  else if ( a2 == 12 )
  {
    for ( i = a3 + 3; *i != 544501094; i = (_DWORD *)((char *)i + (unsigned int)i[1] + 8) )
      ;
    *((_QWORD *)this + 3) = i + 2;
    *((_DWORD *)this + 8) = i[1];
    do
      i = (_DWORD *)((char *)i + (unsigned int)i[1] + 8);
    while ( *i != 1635017060 );
    v7 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 5) = i + 2;
    *((_DWORD *)this + 12) = i[1];
    memset_0((char *)this + 52, 0, 0xCCu);
    v8 = *((_DWORD *)this + 12);
    *((_DWORD *)this + 13) = 1935963489;
    v9 = v8 / *(unsigned __int16 *)(v7 + 12);
    *((_DWORD *)this + 25) = *(unsigned __int16 *)(v7 + 12);
    *((_DWORD *)this + 21) = v9;
    *((_DWORD *)this + 18) = *(unsigned __int16 *)(v7 + 12);
    *((_DWORD *)this + 19) = *(_DWORD *)(v7 + 8);
  }
  return 0;
}

```

## disassembly

```asm
0x1800109a0  mov     [rsp+arg_0], rbx
0x1800109a5  mov     [rsp+arg_8], rsi
0x1800109aa  push    rdi
0x1800109ab  sub     rsp, 30h
0x1800109af  mov     [rcx+10h], r8
0x1800109b3  mov     rdi, r8
0x1800109b6  mov     rsi, rcx
0x1800109b9  cmp     edx, 8
0x1800109bc  jnz     short loc_180010A3D
0x1800109be  mov     [rcx+18h], r8
0x1800109c2  cmp     dword ptr [r8+14h], 0
0x1800109c7  jnz     short loc_1800109D1
0x1800109c9  mov     dword ptr [r8+10h], 0
0x1800109d1  xor     edx, edx; Val
0x1800109d3  mov     r8d, 0CCh; Size
0x1800109d9  add     rcx, 34h ; '4'; void *
0x1800109dd  call    memset_0
0x1800109e2  mov     eax, 1
0x1800109e7  mov     dword ptr [rsi+34h], 73646976h
0x1800109ee  mov     [rsi+54h], eax
0x1800109f1  lea     rcx, [rsi+68h]; lprc
0x1800109f5  mov     [rsi+48h], eax
0x1800109f8  xor     r8d, r8d; yTop
0x1800109fb  mov     dword ptr [rsi+4Ch], 0Fh
0x180010a02  xor     edx, edx; xLeft
0x180010a04  mov     dword ptr [rsi+64h], 0
0x180010a0b  mov     eax, [rdi+8]
0x180010a0e  mov     r9d, [rdi+4]; xRight
0x180010a12  mov     [rsp+38h+yBottom], eax; yBottom
0x180010a16  call    cs:__imp_SetRect
0x180010a1c  mov     eax, [rdi]
0x180010a1e  mov     ecx, [rdi+20h]
0x180010a21  lea     edx, [rax+rcx*4]
0x180010a24  movsxd  rax, edx
0x180010a27  add     rax, [rsi+10h]
0x180010a2b  mov     [rsi+28h], rax
0x180010a2f  mov     [rsi+20h], edx
0x180010a32  mov     eax, [rdi+14h]
0x180010a35  mov     [rsi+30h], eax
0x180010a38  jmp     loc_180010AC7
0x180010a3d  cmp     edx, 0Ch
0x180010a40  jnz     loc_180010AC7
0x180010a46  lea     rcx, [r8+0Ch]
0x180010a4a  mov     edx, 20746D66h
0x180010a4f  jmp     short loc_180010A5B
0x180010a51  mov     eax, [rcx+4]
0x180010a54  add     rcx, 8
0x180010a58  add     rcx, rax
0x180010a5b  cmp     [rcx], edx
0x180010a5d  jnz     short loc_180010A51
0x180010a5f  lea     rax, [rcx+8]
0x180010a63  mov     [rsi+18h], rax
0x180010a67  mov     eax, [rcx+4]
0x180010a6a  mov     [rsi+20h], eax
0x180010a6d  mov     eax, [rcx+4]
0x180010a70  add     rcx, 8
0x180010a74  add     rcx, rax
0x180010a77  cmp     dword ptr [rcx], 61746164h
0x180010a7d  jnz     short loc_180010A6D
0x180010a7f  mov     rdi, [rsi+18h]
0x180010a83  lea     rax, [rcx+8]
0x180010a87  mov     [rsi+28h], rax
0x180010a8b  xor     edx, edx; Val
0x180010a8d  mov     eax, [rcx+4]
0x180010a90  mov     r8d, 0CCh; Size
0x180010a96  lea     rcx, [rsi+34h]; void *
0x180010a9a  mov     [rsi+30h], eax
0x180010a9d  call    memset_0
0x180010aa2  mov     eax, [rsi+30h]
0x180010aa5  xor     edx, edx
0x180010aa7  mov     dword ptr [rsi+34h], 73647561h
0x180010aae  movzx   ecx, word ptr [rdi+0Ch]
0x180010ab2  div     ecx
0x180010ab4  mov     [rsi+64h], ecx
0x180010ab7  mov     [rsi+54h], eax
0x180010aba  movzx   eax, word ptr [rdi+0Ch]
0x180010abe  mov     [rsi+48h], eax
0x180010ac1  mov     eax, [rdi+8]
0x180010ac4  mov     [rsi+4Ch], eax
0x180010ac7  mov     rbx, [rsp+38h+arg_0]
0x180010acc  xor     eax, eax
0x180010ace  mov     rsi, [rsp+38h+arg_8]
0x180010ad3  add     rsp, 30h
0x180010ad7  pop     rdi
0x180010ad8  retn
```
