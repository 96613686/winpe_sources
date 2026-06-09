# CDetourDis::CopyBytes(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x40e310`
- end: `0x40e4a3`
- name: `?CopyBytes@CDetourDis@@IAEPAEPBUCOPYENTRY@1@PAE1@Z`
- size: `403`
- prototype: `unsigned __int8 *__thiscall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x40e800`
- `0x40e830`
- `0x40e860`
- `0x40e8e0`
- `0x40e930`

## callees

- `0x40e310`
- `0x40eb1b`

## pseudocode

```c
unsigned __int8 *__thiscall CDetourDis::CopyBytes(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *Src)
{
  unsigned int v4; // ebp
  int v5; // eax
  int v6; // esi
  bool v7; // zf
  size_t v8; // esi
  int v9; // ebp
  size_t v10; // edi
  unsigned __int8 v11; // dl
  char v12; // dl
  unsigned __int8 *v13; // ecx
  unsigned __int8 *v14; // eax
  size_t v15; // edi
  size_t v16; // edi
  CDetourDis *v17; // edx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  char v21; // al
  int v24; // [esp+10h] [ebp-8h]

  v4 = *(_DWORD *)a2;
  v5 = HIWORD(*(_DWORD *)a2) & 0xF;
  v24 = *(_DWORD *)a2 >> 28;
  v6 = *(_DWORD *)a2 >> 8;
  if ( (v24 & 2) != 0 )
    v7 = *((_DWORD *)this + 1) == 0;
  else
    v7 = *(_DWORD *)this == 0;
  if ( !v7 )
    v6 = v4 >> 12;
  v8 = v6 & 0xF;
  v9 = (v4 >> 20) & 0xF;
  v10 = v8 - v9;
  if ( v5 )
  {
    v11 = Src[v5];
    v8 += *((_BYTE *)&CDetourDis::s_rbModRm + v11) & 0xF;
    if ( (*((_BYTE *)&CDetourDis::s_rbModRm + v11) & 0x10) != 0 )
    {
      if ( (Src[v5 + 1] & 7) == 5 )
      {
        v12 = v11 & 0xC0;
        if ( v12 )
        {
          if ( v12 == 64 )
          {
            ++v8;
            goto LABEL_14;
          }
          if ( v12 != (char)0x80 )
            goto LABEL_14;
        }
        v8 += 4;
      }
LABEL_14:
      v10 = v8 - v9;
    }
  }
  memcpy(a3, Src, v8);
  if ( !v9 )
  {
    v17 = this;
    goto LABEL_34;
  }
  if ( v10 == 1 )
  {
    v20 = (char)a3[v9];
    v13 = &Src[v8 + v20];
    v14 = &Src[v20 - (_DWORD)a3];
    goto LABEL_30;
  }
  if ( v10 != 2 )
  {
    if ( v10 == 4 )
    {
      v18 = *(_DWORD *)&a3[v9];
      v13 = &Src[v8 + v18];
      v14 = &Src[v18 - (_DWORD)a3];
LABEL_24:
      *(_DWORD *)&a3[v9] = v14;
      v17 = this;
      **((_DWORD **)this + 7) = v13;
      goto LABEL_34;
    }
    v13 = &Src[v8];
    v14 = (unsigned __int8 *)(Src - a3);
    v15 = v10 - 1;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( v16 )
      {
        if ( v16 != 2 )
        {
LABEL_22:
          v17 = this;
          **((_DWORD **)this + 7) = v13;
          goto LABEL_34;
        }
        goto LABEL_24;
      }
      goto LABEL_26;
    }
LABEL_30:
    a3[v9] = (unsigned __int8)v14;
    if ( (int)v14 >= -128 && (int)v14 <= 127 )
      goto LABEL_22;
    v17 = this;
    **((_DWORD **)this + 8) = 3;
    **((_DWORD **)this + 7) = v13;
    goto LABEL_34;
  }
  v19 = *(__int16 *)&a3[v9];
  v13 = &Src[v19 + v8];
  v14 = &Src[v19 - (_DWORD)a3];
LABEL_26:
  *(_WORD *)&a3[v9] = (_WORD)v14;
  if ( (int)v14 >= -32768 && (int)v14 <= 0x7FFF )
    goto LABEL_22;
  v17 = this;
  **((_DWORD **)this + 8) = 2;
  **((_DWORD **)this + 7) = v13;
LABEL_34:
  v21 = v24;
  if ( (v24 & 4) != 0 )
  {
    **((_DWORD **)v17 + 8) = -**((_DWORD **)v17 + 8);
    v21 = v24;
  }
  if ( (v21 & 1) != 0 )
    **((_DWORD **)v17 + 7) = -1;
  return &Src[v8];
}

```

## disassembly

```asm
0x40e310  sub     esp, 0Ch
0x40e313  mov     eax, [esp+0Ch+arg_0]
0x40e317  push    ebx
0x40e318  mov     ebx, [esp+10h+Src]
0x40e31c  push    ebp
0x40e31d  mov     ebp, [eax]
0x40e31f  mov     eax, ebp
0x40e321  mov     edx, ebp
0x40e323  shr     eax, 10h
0x40e326  shr     edx, 1Ch
0x40e329  and     eax, 0Fh
0x40e32c  mov     [esp+14h+var_8], edx
0x40e330  mov     edx, ebp
0x40e332  push    esi
0x40e333  mov     esi, ebp
0x40e335  shr     edx, 0Ch
0x40e338  shr     esi, 8
0x40e33b  test    byte ptr [esp+18h+var_8], 2
0x40e340  mov     [esp+18h+var_C], ecx
0x40e344  jz      short loc_40E34C
0x40e346  cmp     dword ptr [ecx+4], 0
0x40e34a  jmp     short loc_40E34F
0x40e34c  cmp     dword ptr [ecx], 0
0x40e34f  cmovnz  esi, edx
0x40e352  shr     ebp, 14h
0x40e355  and     esi, 0Fh
0x40e358  and     ebp, 0Fh
0x40e35b  push    edi
0x40e35c  mov     edi, esi
0x40e35e  sub     edi, ebp
0x40e360  test    eax, eax
0x40e362  jz      short loc_40E3A9
0x40e364  mov     dl, [eax+ebx]
0x40e367  add     eax, ebx
0x40e369  mov     [esp+1Ch+var_4], eax
0x40e36d  movzx   eax, dl
0x40e370  mov     cl, ds:?s_rbModRm@CDetourDis@@1QBEB[eax]; uchar const * const CDetourDis::s_rbModRm
0x40e376  movzx   eax, cl
0x40e379  and     eax, 0Fh
0x40e37c  add     esi, eax
0x40e37e  test    cl, 10h
0x40e381  jz      short loc_40E3A9
0x40e383  mov     eax, [esp+1Ch+var_4]
0x40e387  mov     al, [eax+1]
0x40e38a  and     al, 7
0x40e38c  cmp     al, 5
0x40e38e  jnz     short loc_40E3A5
0x40e390  and     dl, 0C0h
0x40e393  jz      short loc_40E3A2
0x40e395  cmp     dl, 40h ; '@'
0x40e398  jnz     short loc_40E39D
0x40e39a  inc     esi
0x40e39b  jmp     short loc_40E3A5
0x40e39d  cmp     dl, 80h
0x40e3a0  jnz     short loc_40E3A5
0x40e3a2  add     esi, 4
0x40e3a5  mov     edi, esi
0x40e3a7  sub     edi, ebp
0x40e3a9  push    esi; Size
0x40e3aa  push    ebx; Src
0x40e3ab  push    [esp+24h+arg_4]; void *
0x40e3af  call    _memcpy
0x40e3b4  add     esp, 0Ch
0x40e3b7  test    ebp, ebp
0x40e3b9  jz      loc_40E470
0x40e3bf  mov     edx, [esp+1Ch+arg_4]
0x40e3c3  mov     eax, edi
0x40e3c5  sub     eax, 1
0x40e3c8  jz      short loc_40E442
0x40e3ca  sub     eax, 1
0x40e3cd  jz      short loc_40E40F
0x40e3cf  sub     eax, 2
0x40e3d2  jz      short loc_40E3F5
0x40e3d4  mov     eax, ebx
0x40e3d6  lea     ecx, [esi+ebx]
0x40e3d9  sub     eax, edx
0x40e3db  sub     edi, 1
0x40e3de  jz      short loc_40E44F
0x40e3e0  sub     edi, 1
0x40e3e3  jz      short loc_40E41C
0x40e3e5  sub     edi, 2
0x40e3e8  jz      short loc_40E401
0x40e3ea  mov     edx, [esp+1Ch+var_C]
0x40e3ee  mov     eax, [edx+1Ch]
0x40e3f1  mov     [eax], ecx
0x40e3f3  jmp     short loc_40E474
0x40e3f5  mov     eax, [edx+ebp]
0x40e3f8  lea     ecx, [esi+eax]
0x40e3fb  sub     eax, edx
0x40e3fd  add     ecx, ebx
0x40e3ff  add     eax, ebx
0x40e401  mov     [edx+ebp], eax
0x40e404  mov     edx, [esp+1Ch+var_C]
0x40e408  mov     eax, [edx+1Ch]
0x40e40b  mov     [eax], ecx
0x40e40d  jmp     short loc_40E474
0x40e40f  movsx   eax, word ptr [edx+ebp]
0x40e413  lea     ecx, [eax+ebx]
0x40e416  sub     eax, edx
0x40e418  add     ecx, esi
0x40e41a  add     eax, ebx
0x40e41c  mov     [edx+ebp], ax
0x40e420  cmp     eax, 0FFFF8000h
0x40e425  jl      short loc_40E42E
0x40e427  cmp     eax, 7FFFh
0x40e42c  jle     short loc_40E3EA
0x40e42e  mov     edx, [esp+1Ch+var_C]
0x40e432  mov     eax, [edx+20h]
0x40e435  mov     dword ptr [eax], 2
0x40e43b  mov     eax, [edx+1Ch]
0x40e43e  mov     [eax], ecx
0x40e440  jmp     short loc_40E474
0x40e442  movsx   eax, byte ptr [edx+ebp]
0x40e446  lea     ecx, [esi+eax]
0x40e449  sub     eax, edx
0x40e44b  add     ecx, ebx
0x40e44d  add     eax, ebx
0x40e44f  mov     [edx+ebp], al
0x40e452  cmp     eax, 0FFFFFF80h
0x40e455  jl      short loc_40E45C
0x40e457  cmp     eax, 7Fh
0x40e45a  jle     short loc_40E3EA
0x40e45c  mov     edx, [esp+1Ch+var_C]
0x40e460  mov     eax, [edx+20h]
0x40e463  mov     dword ptr [eax], 3
0x40e469  mov     eax, [edx+1Ch]
0x40e46c  mov     [eax], ecx
0x40e46e  jmp     short loc_40E474
0x40e470  mov     edx, [esp+1Ch+var_C]
0x40e474  mov     eax, [esp+1Ch+var_8]
0x40e478  pop     edi
0x40e479  test    al, 4
0x40e47b  jz      short loc_40E48A
0x40e47d  mov     ecx, [edx+20h]
0x40e480  mov     eax, [ecx]
0x40e482  neg     eax
0x40e484  mov     [ecx], eax
0x40e486  mov     eax, [esp+18h+var_8]
0x40e48a  test    al, 1
0x40e48c  jz      short loc_40E497
0x40e48e  mov     eax, [edx+1Ch]
0x40e491  mov     dword ptr [eax], 0FFFFFFFFh
0x40e497  lea     eax, [esi+ebx]
0x40e49a  pop     esi
0x40e49b  pop     ebp
0x40e49c  pop     ebx
0x40e49d  add     esp, 0Ch
0x40e4a0  retn    0Ch
```
