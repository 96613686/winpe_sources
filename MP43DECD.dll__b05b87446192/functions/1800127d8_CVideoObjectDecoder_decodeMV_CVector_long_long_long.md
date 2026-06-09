# CVideoObjectDecoder::decodeMV(CVector *,long,long,long)

- ea: `0x1800127d8`
- end: `0x180012930`
- name: `?decodeMV@CVideoObjectDecoder@@AEAAJPEAVCVector@@JJJ@Z`
- size: `344`
- prototype: `__int64 __fastcall(CVideoObjectDecoder *__hidden this, struct CVector *, int, int, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180010600`
- `0x180010f80`
- `0x1800119e8`

## callees

- `0x18000dc8c`
- `0x1800127d8`
- `0x180012a4c`
- `0x180012b44`

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
0x1800127d8  push    rbp
0x1800127da  push    rbx
0x1800127db  push    rsi
0x1800127dc  push    rdi
0x1800127dd  mov     rbp, rsp
0x1800127e0  sub     rsp, 48h
0x1800127e4  mov     eax, [rbp+arg_20]
0x1800127e7  mov     rsi, rdx
0x1800127ea  mov     [rsp+48h+var_20], eax; int
0x1800127ee  mov     rbx, rcx
0x1800127f1  mov     [rsp+48h+var_28], r9d; int
0x1800127f6  mov     r9d, r8d; int
0x1800127f9  mov     r8, rdx; struct CVector *
0x1800127fc  mov     [rbp+arg_0], 0
0x180012802  lea     rdx, [rbp+arg_0]; struct CVector *
0x180012806  call    ?find16x16MVpred@CVideoObjectDecoder@@AEBAXAEAVCVector@@PEBV2@JJJ@Z; CVideoObjectDecoder::find16x16MVpred(CVector &,CVector const *,long,long,long)
0x18001280b  cmp     dword ptr [rbx+8], 0
0x18001280f  jz      loc_1800128AA
0x180012815  mov     rcx, [rbx+890h]; this
0x18001281c  lea     r8, ?gDecodeCodeTableMV@@3PAEA; unsigned __int8 *
0x180012823  mov     edx, 0Dh; unsigned int
0x180012828  call    ?getMaxBits@CInputBitStream@@QEAAEKPEAE@Z; CInputBitStream::getMaxBits(ulong,uchar *)
0x18001282d  mov     rcx, [rbx+890h]
0x180012834  cmp     dword ptr [rcx+14h], 0
0x180012838  jnz     loc_1800128C9
0x18001283e  movsx   edx, byte ptr [rbp+arg_0]
0x180012842  lea     rdi, [rbx+0E60h]
0x180012849  add     edx, 0FFFFFFE0h
0x18001284c  movzx   ecx, al
0x18001284f  add     edx, ecx
0x180012851  cmp     edx, [rbx+0E64h]
0x180012857  jle     short loc_18001285E
0x180012859  sub     dl, 40h ; '@'
0x18001285c  jmp     short loc_180012865
0x18001285e  cmp     edx, [rdi]
0x180012860  jge     short loc_180012865
0x180012862  add     dl, 40h ; '@'
0x180012865  mov     [rsi], dl
0x180012867  mov     edx, 0Dh; unsigned int
0x18001286c  mov     rcx, [rbx+890h]; this
0x180012873  call    ?getMaxBits@CInputBitStream@@QEAAEKPEAE@Z; CInputBitStream::getMaxBits(ulong,uchar *)
0x180012878  mov     rcx, [rbx+890h]
0x18001287f  cmp     dword ptr [rcx+14h], 0
0x180012883  jnz     short loc_1800128C9
0x180012885  movsx   edx, byte ptr [rbp+arg_0+1]
0x180012889  add     edx, 0FFFFFFE0h
0x18001288c  movzx   ecx, al
0x18001288f  add     edx, ecx
0x180012891  cmp     edx, [rbx+0E64h]
0x180012897  jle     short loc_1800128A1
0x180012899  sub     dl, 40h ; '@'
0x18001289c  jmp     loc_180012922
0x1800128a1  cmp     edx, [rdi]
0x1800128a3  jge     short loc_180012922
0x1800128a5  add     dl, 40h ; '@'
0x1800128a8  jmp     short loc_180012922
0x1800128aa  lea     rdx, [rbp+var_18]; struct CVector *
0x1800128ae  mov     [rbp+var_18], 0
0x1800128b4  mov     rcx, rbx; this
0x1800128b7  call    ?getDiffMV@CVideoObjectDecoder@@AEAAXAEAVCVector@@@Z; CVideoObjectDecoder::getDiffMV(CVector &)
0x1800128bc  mov     rax, [rbx+890h]
0x1800128c3  cmp     dword ptr [rax+14h], 0
0x1800128c7  jz      short loc_1800128D0
0x1800128c9  mov     eax, 0FFFFFF9Ch
0x1800128ce  jmp     short loc_180012927
0x1800128d0  mov     al, byte ptr [rbp+var_18+1]
0x1800128d3  add     al, byte ptr [rbp+arg_0+1]
0x1800128d6  mov     r9b, byte ptr [rbp+var_18]
0x1800128da  add     r9b, byte ptr [rbp+arg_0]
0x1800128de  mov     ecx, [rbx+60h]
0x1800128e1  mov     r10d, ecx
0x1800128e4  movsx   edx, al
0x1800128e7  neg     r10d
0x1800128ea  movsx   eax, r9b
0x1800128ee  cmp     eax, r10d
0x1800128f1  jge     short loc_1800128FE
0x1800128f3  mov     r8b, cl
0x1800128f6  add     r8b, r8b
0x1800128f9  add     r8b, r9b
0x1800128fc  jmp     short loc_18001290C
0x1800128fe  mov     r8b, r9b
0x180012901  cmp     eax, ecx
0x180012903  jl      short loc_18001290C
0x180012905  mov     al, cl
0x180012907  add     al, al
0x180012909  sub     r8b, al
0x18001290c  cmp     edx, r10d
0x18001290f  jge     short loc_180012917
0x180012911  add     cl, cl
0x180012913  add     dl, cl
0x180012915  jmp     short loc_18001291F
0x180012917  cmp     edx, ecx
0x180012919  jl      short loc_18001291F
0x18001291b  add     cl, cl
0x18001291d  sub     dl, cl
0x18001291f  mov     [rsi], r8b
0x180012922  xor     eax, eax
0x180012924  mov     [rsi+1], dl
0x180012927  add     rsp, 48h
0x18001292b  pop     rdi
0x18001292c  pop     rsi
0x18001292d  pop     rbx
0x18001292e  pop     rbp
0x18001292f  retn
```
