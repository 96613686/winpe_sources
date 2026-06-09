# CMetadataIFDReaderWriter::GetTagVariantValueInline(IFD::FieldEntry *,tagPROPVARIANT *)

- ea: `0x180055030`
- end: `0x1800552a3`
- name: `?GetTagVariantValueInline@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEAUtagPROPVARIANT@@@Z`
- size: `627`
- prototype: `__int64 __fastcall(CMetadataIFDReaderWriter *__hidden this, struct IFD::FieldEntry *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180054d54`

## callees

- `0x180053d08`
- `0x180055030`
- `0x1800553a4`
- `0x1800bb784`
- `0x18017b528`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055140`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800551e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055228`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055140`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800551e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055228`

## pseudocode

```c
__int64 __fastcall CMetadataIFDReaderWriter::GetTagVariantValueInline(
        CMetadataIFDReaderWriter *this,
        struct IFD::FieldEntry *a2,
        PROPVARIANT *a3)
{
  unsigned int *v3; // r14
  unsigned int v7; // ebx
  unsigned int v8; // edx
  unsigned int v9; // r14d
  VARTYPE v10; // ax
  int ValueAsciiTag; // eax
  int v13; // ecx
  void *v14; // r15
  bool v15; // zf
  unsigned int v16; // r15d
  void *v17; // r14
  unsigned int v18; // r15d
  void *v19; // rax
  int Src; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int8 *p_Src; // [rsp+78h] [rbp+20h] BYREF

  v3 = (unsigned int *)((char *)a2 + 20);
  if ( (*((_BYTE *)a2 + 16) & 0x10) != 0 )
  {
    v7 = 0;
  }
  else
  {
    v7 = IFD::TagEntry::ComputeTagDataSize(a2, (unsigned int *)a2 + 5);
    if ( (v7 & 0x80000000) != 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        return v7;
      DoStackCapture(v7);
      v15 = (_DWORD)g_doStackCaptures == 0;
      goto LABEL_29;
    }
    *((_DWORD *)a2 + 4) |= 0x10u;
  }
  v8 = *((unsigned __int16 *)a2 + 1);
  v9 = *v3;
  if ( v8 > 7 )
  {
    switch ( v8 )
    {
      case 8u:
        goto LABEL_5;
      case 9u:
        *(_WORD *)a3 = 3;
        goto LABEL_18;
      case 0xBu:
        *(_WORD *)a3 = 4;
        goto LABEL_18;
    }
    goto LABEL_45;
  }
  if ( v8 == 7 )
  {
    if ( v9 )
    {
      v14 = CoTaskMemAlloc(v9);
      if ( !v14 )
      {
LABEL_40:
        v7 = -2147024882;
LABEL_41:
        v15 = (_DWORD)g_doStackCaptures == 0;
LABEL_29:
        if ( v15 )
          return v7;
        v13 = v7;
LABEL_31:
        DoStackCapture(v13);
        return v7;
      }
      Src = *((_DWORD *)a2 + 2);
      memcpy_0(v14, &Src, v9);
    }
    else
    {
      v14 = 0;
    }
    *(_WORD *)a3 = 65;
    *((_DWORD *)a3 + 2) = v9;
    a3[2] = v14;
    return v7;
  }
  if ( v8 == 1 )
  {
LABEL_33:
    *(_WORD *)a3 = 17 - (v8 != 1);
    if ( *((_DWORD *)a2 + 1) <= 1u )
    {
      *((_BYTE *)a3 + 8) = *((_BYTE *)a2 + 8);
      return v7;
    }
    v16 = v9;
    v17 = CoTaskMemAlloc(v9);
    if ( v17 )
    {
      Src = *((_DWORD *)a2 + 2);
      memcpy_0(v17, &Src, v16);
      *(_WORD *)a3 |= 0x1000u;
      *((_DWORD *)a3 + 2) = *((_DWORD *)a2 + 1);
LABEL_37:
      a3[2] = v17;
      return v7;
    }
    goto LABEL_40;
  }
  if ( v8 != 2 )
  {
    if ( v8 == 3 )
    {
LABEL_5:
      v10 = 18;
      if ( v8 != 3 )
        v10 = 2;
      *(_WORD *)a3 = v10;
      if ( *((_DWORD *)a2 + 1) <= 1u )
      {
        *((_WORD *)a3 + 4) = *((_WORD *)a2 + 4);
        return v7;
      }
      v18 = v9;
      v19 = CoTaskMemAlloc(v9);
      v17 = v19;
      if ( v19 )
      {
        Src = *((_DWORD *)a2 + 2);
        memcpy_0(v19, &Src, v18);
        *(_WORD *)a3 |= 0x1000u;
        *((_DWORD *)a3 + 2) = *((_DWORD *)a2 + 1);
        goto LABEL_37;
      }
      goto LABEL_40;
    }
    if ( v8 == 4 )
    {
      *(_WORD *)a3 = 19;
LABEL_18:
      *((_DWORD *)a3 + 2) = *((_DWORD *)a2 + 2);
      return v7;
    }
    if ( v8 != 6 )
    {
LABEL_45:
      if ( !v9 )
        return v7;
      v7 = -2147418113;
      goto LABEL_41;
    }
    goto LABEL_33;
  }
  Src = *((_DWORD *)a2 + 2);
  p_Src = (unsigned __int8 *)&Src;
  ValueAsciiTag = CMetadataIFDReaderWriter::GetValueAsciiTag(this, v9, &p_Src, 0, a3);
  v7 = ValueAsciiTag;
  if ( ValueAsciiTag < 0 && (_DWORD)g_doStackCaptures )
  {
    v13 = ValueAsciiTag;
    goto LABEL_31;
  }
  return v7;
}

```

## disassembly

```asm
0x180055030  mov     [rsp+arg_0], rbx
0x180055035  push    rbp
0x180055036  push    rsi
0x180055037  push    r12
0x180055039  push    r14
0x18005503b  push    r15
0x18005503d  sub     rsp, 30h
0x180055041  test    byte ptr [rdx+10h], 10h
0x180055045  lea     r14, [rdx+14h]
0x180055049  mov     rsi, r8
0x18005504c  mov     rbp, rdx
0x18005504f  mov     r15, rcx
0x180055052  jz      short loc_1800550A9
0x180055054  xor     ebx, ebx
0x180055056  movzx   edx, word ptr [rbp+2]
0x18005505a  mov     r14d, [r14]
0x18005505d  cmp     edx, 7
0x180055060  jbe     short loc_1800550C4
0x180055062  mov     ecx, edx
0x180055064  sub     ecx, 8
0x180055067  jnz     loc_180055275
0x18005506d  mov     eax, 12h
0x180055072  lea     ecx, [rax-0Fh]
0x180055075  cmp     edx, ecx
0x180055077  lea     r8d, [rax-10h]
0x18005507b  cmovnz  ax, r8w
0x180055080  mov     [rsi], ax
0x180055083  cmp     dword ptr [rbp+4], 1
0x180055087  ja      loc_180055222
0x18005508d  movzx   eax, word ptr [rbp+8]
0x180055091  mov     [rsi+8], ax
0x180055095  mov     eax, ebx
0x180055097  mov     rbx, [rsp+58h+arg_0]
0x18005509c  add     rsp, 30h
0x1800550a0  pop     r15
0x1800550a2  pop     r14
0x1800550a4  pop     r12
0x1800550a6  pop     rsi
0x1800550a7  pop     rbp
0x1800550a8  retn
0x1800550a9  mov     rdx, r14; unsigned int *
0x1800550ac  mov     rcx, rbp; this
0x1800550af  call    ?ComputeTagDataSize@TagEntry@IFD@@IEAAJPEAK@Z; IFD::TagEntry::ComputeTagDataSize(ulong *)
0x1800550b4  mov     ebx, eax
0x1800550b6  test    eax, eax
0x1800550b8  js      loc_180055180
0x1800550be  or      dword ptr [rbp+10h], 10h
0x1800550c2  jmp     short loc_180055056
0x1800550c4  jz      short loc_180055135
0x1800550c6  mov     ecx, edx
0x1800550c8  sub     ecx, 1
0x1800550cb  jz      loc_1800551C1
0x1800550d1  sub     ecx, 1
0x1800550d4  jz      short loc_1800550F1
0x1800550d6  sub     ecx, 1
0x1800550d9  jz      short loc_18005506D
0x1800550db  sub     ecx, 1
0x1800550de  jnz     loc_1800551AF
0x1800550e4  mov     word ptr [rsi], 13h
0x1800550e9  mov     eax, [rbp+8]
0x1800550ec  mov     [rsi+8], eax
0x1800550ef  jmp     short loc_180055095
0x1800550f1  mov     eax, [rbp+8]
0x1800550f4  lea     r8, [rsp+58h+arg_18]; unsigned __int8 **
0x1800550f9  mov     [rsp+58h+Src], eax
0x1800550fd  xor     r9d, r9d; int
0x180055100  lea     rax, [rsp+58h+Src]
0x180055105  mov     [rsp+58h+var_38], rsi; struct tagPROPVARIANT *
0x18005510a  mov     edx, r14d; unsigned int
0x18005510d  mov     [rsp+58h+arg_18], rax
0x180055112  mov     rcx, r15; this
0x180055115  call    ?GetValueAsciiTag@CMetadataIFDReaderWriter@@IEAAJKPEAPEAEHPEAUtagPROPVARIANT@@@Z; CMetadataIFDReaderWriter::GetValueAsciiTag(ulong,uchar * *,int,tagPROPVARIANT *)
0x18005511a  mov     ebx, eax
0x18005511c  test    eax, eax
0x18005511e  jns     loc_180055095
0x180055124  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18005512b  jz      loc_180055095
0x180055131  mov     ecx, eax
0x180055133  jmp     short loc_1800551A5
0x180055135  test    r14d, r14d
0x180055138  jz      short loc_18005517B
0x18005513a  mov     ecx, r14d; cb
0x18005513d  mov     r12d, r14d
0x180055140  call    cs:__imp_CoTaskMemAlloc
0x180055146  mov     r15, rax
0x180055149  test    rax, rax
0x18005514c  jz      loc_18005525D
0x180055152  mov     eax, [rbp+8]
0x180055155  lea     rdx, [rsp+58h+Src]; Src
0x18005515a  mov     r8d, r12d; Size
0x18005515d  mov     [rsp+58h+Src], eax
0x180055161  mov     rcx, r15; void *
0x180055164  call    memcpy_0
0x180055169  mov     word ptr [rsi], 41h ; 'A'
0x18005516e  mov     [rsi+8], r14d
0x180055172  mov     [rsi+10h], r15
0x180055176  jmp     loc_180055095
0x18005517b  xor     r15d, r15d
0x18005517e  jmp     short loc_180055169
0x180055180  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180055186  test    eax, eax
0x180055188  jz      loc_180055095
0x18005518e  mov     ecx, ebx; int
0x180055190  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180055195  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18005519b  test    eax, eax
0x18005519d  jz      loc_180055095
0x1800551a3  mov     ecx, ebx; int
0x1800551a5  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800551aa  jmp     loc_180055095
0x1800551af  sub     ecx, 1
0x1800551b2  jz      loc_18005528E
0x1800551b8  cmp     ecx, 1
0x1800551bb  jnz     loc_18005528E
0x1800551c1  dec     edx
0x1800551c3  neg     edx
0x1800551c5  sbb     ax, ax
0x1800551c8  add     ax, 11h
0x1800551cc  mov     [rsi], ax
0x1800551cf  cmp     dword ptr [rbp+4], 1
0x1800551d3  ja      short loc_1800551E0
0x1800551d5  mov     al, [rbp+8]
0x1800551d8  mov     [rsi+8], al
0x1800551db  jmp     loc_180055095
0x1800551e0  mov     ecx, r14d; cb
0x1800551e3  mov     r15d, r14d
0x1800551e6  call    cs:__imp_CoTaskMemAlloc
0x1800551ec  mov     r14, rax
0x1800551ef  test    rax, rax
0x1800551f2  jz      short loc_18005525D
0x1800551f4  mov     eax, [rbp+8]
0x1800551f7  lea     rdx, [rsp+58h+Src]; Src
0x1800551fc  mov     r8d, r15d; Size
0x1800551ff  mov     [rsp+58h+Src], eax
0x180055203  mov     rcx, r14; void *
0x180055206  call    memcpy_0
0x18005520b  mov     eax, 1000h
0x180055210  or      [rsi], ax
0x180055213  mov     eax, [rbp+4]
0x180055216  mov     [rsi+8], eax
0x180055219  mov     [rsi+10h], r14
0x18005521d  jmp     loc_180055095
0x180055222  mov     ecx, r14d; cb
0x180055225  mov     r15d, r14d
0x180055228  call    cs:__imp_CoTaskMemAlloc
0x18005522e  mov     r14, rax
0x180055231  test    rax, rax
0x180055234  jz      short loc_18005525D
0x180055236  mov     ecx, [rbp+8]
0x180055239  lea     rdx, [rsp+58h+Src]; Src
0x18005523e  mov     [rsp+58h+Src], ecx
0x180055242  mov     r8d, r15d; Size
0x180055245  mov     rcx, rax; void *
0x180055248  call    memcpy_0
0x18005524d  mov     eax, 1000h
0x180055252  or      [rsi], ax
0x180055255  mov     ecx, [rbp+4]
0x180055258  mov     [rsi+8], ecx
0x18005525b  jmp     short loc_180055219
0x18005525d  mov     ebx, 8007000Eh
0x180055262  jmp     short loc_180055269
0x180055264  mov     ebx, 8000FFFFh
0x180055269  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180055270  jmp     loc_18005519D
0x180055275  sub     ecx, 1
0x180055278  jz      short loc_180055299
0x18005527a  sub     ecx, 1
0x18005527d  jz      short loc_18005528E
0x18005527f  sub     ecx, 1
0x180055282  jnz     short loc_18005528E
0x180055284  mov     word ptr [rsi], 4
0x180055289  jmp     loc_1800550E9
0x18005528e  test    r14d, r14d
0x180055291  jz      loc_180055095
0x180055297  jmp     short loc_180055264
0x180055299  mov     word ptr [rsi], 3
0x18005529e  jmp     loc_1800550E9
```
