# CVideoObjectDecoder::decodeMV(CVector *,long,long,long)

- ea: `0x180012898`
- end: `0x1800129f0`
- name: `?decodeMV@CVideoObjectDecoder@@AEAAJPEAVCVector@@JJJ@Z`
- size: `344`
- prototype: `__int64 __fastcall(CInputBitStream **this, struct CVector *, int, int, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800106c0`
- `0x180011040`
- `0x180011aa8`

## callees

- `0x18000dd4c`
- `0x180012898`
- `0x180012b0c`
- `0x180012c04`

## pseudocode

```c
__int64 __fastcall CVideoObjectDecoder::decodeMV(CInputBitStream **this, struct CVector *a2, int a3, int a4, int a5)
{
  unsigned __int8 MaxBits; // al
  unsigned __int8 *v8; // r8
  int *v9; // rdi
  int v10; // edx
  unsigned __int8 v11; // al
  int v12; // edx
  __int64 result; // rax
  char v14; // r9
  int v15; // ecx
  int v16; // eax
  char v17; // r8
  __int16 v18; // [rsp+30h] [rbp-18h] BYREF
  __int16 v19; // [rsp+70h] [rbp+28h] BYREF

  v19 = 0;
  CVideoObjectDecoder::find16x16MVpred((CVideoObjectDecoder *)this, (struct CVector *)&v19, a2, a3, a4, a5);
  if ( !*((_DWORD *)this + 2) )
  {
    v18 = 0;
    CVideoObjectDecoder::getDiffMV((CVideoObjectDecoder *)this, (struct CVector *)&v18);
    if ( !*((_DWORD *)this[274] + 5) )
    {
      v14 = v19 + v18;
      v15 = *((_DWORD *)this + 24);
      v12 = (char)(HIBYTE(v19) + HIBYTE(v18));
      v16 = (char)(v19 + v18);
      if ( v16 >= -v15 )
      {
        v17 = v19 + v18;
        if ( v16 >= v15 )
          v17 = v14 - 2 * v15;
      }
      else
      {
        v17 = v14 + 2 * v15;
      }
      if ( v12 >= -v15 )
      {
        if ( v12 >= v15 )
          LOBYTE(v12) = v12 - 2 * v15;
      }
      else
      {
        LOBYTE(v12) = 2 * v15 + v12;
      }
      *(_BYTE *)a2 = v17;
      goto LABEL_23;
    }
    return 4294967196LL;
  }
  MaxBits = CInputBitStream::getMaxBits(this[274], 0xDu, &gDecodeCodeTableMV);
  if ( *((_DWORD *)this[274] + 5) )
    return 4294967196LL;
  v9 = (int *)(this + 460);
  v10 = MaxBits + (char)v19 - 32;
  if ( v10 <= *((_DWORD *)this + 921) )
  {
    if ( v10 < *v9 )
      LOBYTE(v10) = v10 + 64;
  }
  else
  {
    LOBYTE(v10) = v10 - 64;
  }
  *(_BYTE *)a2 = v10;
  v11 = CInputBitStream::getMaxBits(this[274], 0xDu, v8);
  if ( *((_DWORD *)this[274] + 5) )
    return 4294967196LL;
  v12 = v11 + SHIBYTE(v19) - 32;
  if ( v12 <= *((_DWORD *)this + 921) )
  {
    if ( v12 < *v9 )
      LOBYTE(v12) = v12 + 64;
  }
  else
  {
    LOBYTE(v12) = v12 - 64;
  }
LABEL_23:
  result = 0;
  *((_BYTE *)a2 + 1) = v12;
  return result;
}

```

## disassembly

```asm
0x180012898  push    rbp
0x18001289a  push    rbx
0x18001289b  push    rsi
0x18001289c  push    rdi
0x18001289d  mov     rbp, rsp
0x1800128a0  sub     rsp, 48h
0x1800128a4  mov     eax, [rbp+arg_20]
0x1800128a7  mov     rsi, rdx
0x1800128aa  mov     [rsp+48h+var_20], eax; int
0x1800128ae  mov     rbx, rcx
0x1800128b1  mov     [rsp+48h+var_28], r9d; int
0x1800128b6  mov     r9d, r8d; int
0x1800128b9  mov     r8, rdx; struct CVector *
0x1800128bc  mov     [rbp+arg_0], 0
0x1800128c2  lea     rdx, [rbp+arg_0]; struct CVector *
0x1800128c6  call    ?find16x16MVpred@CVideoObjectDecoder@@AEBAXAEAVCVector@@PEBV2@JJJ@Z; CVideoObjectDecoder::find16x16MVpred(CVector &,CVector const *,long,long,long)
0x1800128cb  cmp     dword ptr [rbx+8], 0
0x1800128cf  jz      loc_18001296A
0x1800128d5  mov     rcx, [rbx+890h]; this
0x1800128dc  lea     r8, ?gDecodeCodeTableMV@@3PAEA; unsigned __int8 *
0x1800128e3  mov     edx, 0Dh; unsigned int
0x1800128e8  call    ?getMaxBits@CInputBitStream@@QEAAEKPEAE@Z; CInputBitStream::getMaxBits(ulong,uchar *)
0x1800128ed  mov     rcx, [rbx+890h]
0x1800128f4  cmp     dword ptr [rcx+14h], 0
0x1800128f8  jnz     loc_180012989
0x1800128fe  movsx   edx, byte ptr [rbp+arg_0]
0x180012902  lea     rdi, [rbx+0E60h]
0x180012909  add     edx, 0FFFFFFE0h
0x18001290c  movzx   ecx, al
0x18001290f  add     edx, ecx
0x180012911  cmp     edx, [rbx+0E64h]
0x180012917  jle     short loc_18001291E
0x180012919  sub     dl, 40h ; '@'
0x18001291c  jmp     short loc_180012925
0x18001291e  cmp     edx, [rdi]
0x180012920  jge     short loc_180012925
0x180012922  add     dl, 40h ; '@'
0x180012925  mov     [rsi], dl
0x180012927  mov     edx, 0Dh; unsigned int
0x18001292c  mov     rcx, [rbx+890h]; this
0x180012933  call    ?getMaxBits@CInputBitStream@@QEAAEKPEAE@Z; CInputBitStream::getMaxBits(ulong,uchar *)
0x180012938  mov     rcx, [rbx+890h]
0x18001293f  cmp     dword ptr [rcx+14h], 0
0x180012943  jnz     short loc_180012989
0x180012945  movsx   edx, byte ptr [rbp+arg_0+1]
0x180012949  add     edx, 0FFFFFFE0h
0x18001294c  movzx   ecx, al
0x18001294f  add     edx, ecx
0x180012951  cmp     edx, [rbx+0E64h]
0x180012957  jle     short loc_180012961
0x180012959  sub     dl, 40h ; '@'
0x18001295c  jmp     loc_1800129E2
0x180012961  cmp     edx, [rdi]
0x180012963  jge     short loc_1800129E2
0x180012965  add     dl, 40h ; '@'
0x180012968  jmp     short loc_1800129E2
0x18001296a  lea     rdx, [rbp+var_18]; struct CVector *
0x18001296e  mov     [rbp+var_18], 0
0x180012974  mov     rcx, rbx; this
0x180012977  call    ?getDiffMV@CVideoObjectDecoder@@AEAAXAEAVCVector@@@Z; CVideoObjectDecoder::getDiffMV(CVector &)
0x18001297c  mov     rax, [rbx+890h]
0x180012983  cmp     dword ptr [rax+14h], 0
0x180012987  jz      short loc_180012990
0x180012989  mov     eax, 0FFFFFF9Ch
0x18001298e  jmp     short loc_1800129E7
0x180012990  mov     al, byte ptr [rbp+var_18+1]
0x180012993  add     al, byte ptr [rbp+arg_0+1]
0x180012996  mov     r9b, byte ptr [rbp+var_18]
0x18001299a  add     r9b, byte ptr [rbp+arg_0]
0x18001299e  mov     ecx, [rbx+60h]
0x1800129a1  mov     r10d, ecx
0x1800129a4  movsx   edx, al
0x1800129a7  neg     r10d
0x1800129aa  movsx   eax, r9b
0x1800129ae  cmp     eax, r10d
0x1800129b1  jge     short loc_1800129BE
0x1800129b3  mov     r8b, cl
0x1800129b6  add     r8b, r8b
0x1800129b9  add     r8b, r9b
0x1800129bc  jmp     short loc_1800129CC
0x1800129be  mov     r8b, r9b
0x1800129c1  cmp     eax, ecx
0x1800129c3  jl      short loc_1800129CC
0x1800129c5  mov     al, cl
0x1800129c7  add     al, al
0x1800129c9  sub     r8b, al
0x1800129cc  cmp     edx, r10d
0x1800129cf  jge     short loc_1800129D7
0x1800129d1  add     cl, cl
0x1800129d3  add     dl, cl
0x1800129d5  jmp     short loc_1800129DF
0x1800129d7  cmp     edx, ecx
0x1800129d9  jl      short loc_1800129DF
0x1800129db  add     cl, cl
0x1800129dd  sub     dl, cl
0x1800129df  mov     [rsi], r8b
0x1800129e2  xor     eax, eax
0x1800129e4  mov     [rsi+1], dl
0x1800129e7  add     rsp, 48h
0x1800129eb  pop     rdi
0x1800129ec  pop     rsi
0x1800129ed  pop     rbx
0x1800129ee  pop     rbp
0x1800129ef  retn
```
