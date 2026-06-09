# CLogState::_MapPageRange(CReadMap &,_RANGEENTRY *,ulong *)

- ea: `0x180009cd8`
- end: `0x180009d7c`
- name: `?_MapPageRange@CLogState@@AEAAHAEAVCReadMap@@PEAU_RANGEENTRY@@PEAK@Z`
- size: `164`
- prototype: `int(CLogState *__hidden this, struct CReadMap *, struct _RANGEENTRY *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009178`

## callees

- `0x180009cd8`
- `0x18000ce08`

## pseudocode

```c
__int64 __fastcall CLogState::_MapPageRange(
        CLogState *this,
        struct CReadMap *a2,
        struct _RANGEENTRY *a3,
        unsigned int *a4)
{
  int v6; // eax
  unsigned int v7; // eax
  int v8; // edx
  int v9; // eax
  unsigned int v10; // ecx
  unsigned int v11; // edx
  _DWORD *v12; // r8
  int *v13; // r10
  _DWORD *v14; // r9
  unsigned int v16; // eax
  int v17; // eax

  if ( *((_DWORD *)a3 + 4) == *((_DWORD *)this + 7) )
    v6 = *((_DWORD *)this + 6);
  else
    v6 = *((_DWORD *)this + 14);
  v7 = (unsigned int)(v6 - *((_DWORD *)a3 + 2)) / *((_DWORD *)this + 20);
  v8 = 8160 * v7;
  v9 = *((_DWORD *)this + 20) * v7;
  v10 = *a4;
  v11 = v8 - *(_DWORD *)a3;
  *((_DWORD *)a3 + 3) = v9;
  if ( v11 >= v10 )
  {
    v11 = 8160 * (v10 / 0x1FE0);
    *((_DWORD *)a3 + 3) = *((_DWORD *)this + 20) * (v10 / 0x1FE0);
  }
  *((_DWORD *)a3 + 1) = v11;
  *a4 = v10 - v11;
  CReadMap::AddRange(a2, a3);
  if ( !*v14 )
    return 1;
  v12[2] += v12[3];
  v16 = v12[2];
  *v12 = 0;
  if ( v13[26] )
  {
    if ( v16 >= v13[14] )
    {
      v17 = *v13;
      ++v12[4];
      v12[2] = v17;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180009cd8  sub     rsp, 28h
0x180009cdc  mov     eax, [rcx+1Ch]
0x180009cdf  mov     r11, rdx
0x180009ce2  mov     r10, rcx
0x180009ce5  cmp     [r8+10h], eax
0x180009ce9  jnz     short loc_180009CF0
0x180009ceb  mov     eax, [rcx+18h]
0x180009cee  jmp     short loc_180009CF3
0x180009cf0  mov     eax, [rcx+38h]
0x180009cf3  sub     eax, [r8+8]
0x180009cf7  xor     edx, edx
0x180009cf9  div     dword ptr [rcx+50h]
0x180009cfc  imul    edx, eax, 1FE0h
0x180009d02  imul    eax, [rcx+50h]
0x180009d06  mov     ecx, [r9]
0x180009d09  sub     edx, [r8]
0x180009d0c  mov     [r8+0Ch], eax
0x180009d10  cmp     edx, ecx
0x180009d12  jb      short loc_180009D2F
0x180009d14  mov     eax, 80808081h
0x180009d19  mul     ecx
0x180009d1b  shr     edx, 0Ch
0x180009d1e  mov     eax, edx
0x180009d20  imul    eax, [r10+50h]
0x180009d25  imul    edx, 1FE0h
0x180009d2b  mov     [r8+0Ch], eax
0x180009d2f  sub     ecx, edx
0x180009d31  mov     [r8+4], edx
0x180009d35  mov     [r9], ecx
0x180009d38  mov     rdx, r8; struct _RANGEENTRY *
0x180009d3b  mov     rcx, r11; this
0x180009d3e  call    ?AddRange@CReadMap@@QEAAXAEAU_RANGEENTRY@@@Z; CReadMap::AddRange(_RANGEENTRY &)
0x180009d43  xor     ecx, ecx
0x180009d45  cmp     [r9], ecx
0x180009d48  jnz     short loc_180009D4F
0x180009d4a  lea     eax, [rcx+1]
0x180009d4d  jmp     short loc_180009D77
0x180009d4f  mov     eax, [r8+0Ch]
0x180009d53  add     [r8+8], eax
0x180009d57  mov     eax, [r8+8]
0x180009d5b  mov     [r8], ecx
0x180009d5e  cmp     [r10+68h], ecx
0x180009d62  jz      short loc_180009D75
0x180009d64  cmp     eax, [r10+38h]
0x180009d68  jb      short loc_180009D75
0x180009d6a  mov     eax, [r10]
0x180009d6d  inc     dword ptr [r8+10h]
0x180009d71  mov     [r8+8], eax
0x180009d75  xor     eax, eax
0x180009d77  add     rsp, 28h
0x180009d7b  retn
```
