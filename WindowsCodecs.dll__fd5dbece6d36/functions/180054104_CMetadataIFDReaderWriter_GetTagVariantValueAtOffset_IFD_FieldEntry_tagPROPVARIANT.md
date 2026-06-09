# CMetadataIFDReaderWriter::GetTagVariantValueAtOffset(IFD::FieldEntry *,tagPROPVARIANT *)

- ea: `0x180054104`
- end: `0x1800545eb`
- name: `?GetTagVariantValueAtOffset@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEAUtagPROPVARIANT@@@Z`
- size: `1255`
- prototype: `__int64 __fastcall(CMetadataIFDReaderWriter *__hidden this, struct IFD::FieldEntry *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180054d54`

## callees

- `0x180053d08`
- `0x180054104`
- `0x1800545f4`
- `0x180054fec`
- `0x1800553a4`
- `0x180055c8c`
- `0x1800bb784`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054192`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054192`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800542b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800542b6`

## pseudocode

```c
__int64 __fastcall CMetadataIFDReaderWriter::GetTagVariantValueAtOffset(
        CMetadataIFDReaderWriter *this,
        struct IFD::FieldEntry *a2,
        struct tagPROPVARIANT *a3)
{
  unsigned __int8 *v3; // rsi
  _QWORD *v7; // rdi
  SIZE_T v8; // r12
  unsigned int v9; // ebx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // eax
  int v15; // r8d
  __int64 v16; // rcx
  __int64 v17; // rcx
  VARTYPE v18; // ax
  int ValueAsciiTag; // eax
  int v21; // eax
  int v22; // ecx
  bool v23; // zf
  int v24; // ecx
  VARTYPE v25; // ax
  LONG v26; // ecx
  unsigned __int8 *v27[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 v28; // [rsp+88h] [rbp+48h]
  int v29; // [rsp+98h] [rbp+58h] BYREF

  v3 = 0;
  v28 = *((_WORD *)a2 + 1);
  if ( (*((_BYTE *)a2 + 16) & 0x10) == 0 )
  {
    v11 = IFD::TagEntry::ComputeTagDataSize(a2, (unsigned int *)a2 + 5);
    if ( (v11 & 0x80000000) != 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        return v11;
      DoStackCapture(v11);
      if ( !(_DWORD)g_doStackCaptures )
        return v11;
      v22 = v11;
      goto LABEL_54;
    }
    *((_DWORD *)a2 + 4) |= 0x10u;
  }
  v7 = (_QWORD *)*((_QWORD *)this + 15);
  v8 = *((unsigned int *)a2 + 5);
  v9 = *((_DWORD *)a2 + 2);
  (*(void (__fastcall **)(_QWORD *))(v7[2] + 112LL))(v7 + 2);
  v10 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD, _QWORD))(*v7 + 104LL))(v7, v9, 0, 0);
  v11 = v10;
  if ( v10 < 0 && (_DWORD)g_doStackCaptures )
    DoStackCapture(v10);
  (*(void (__fastcall **)(_QWORD *))(v7[2] + 120LL))(v7 + 2);
  if ( (v11 & 0x80000000) != 0 )
  {
LABEL_36:
    v23 = (_DWORD)g_doStackCaptures == 0;
    goto LABEL_37;
  }
  v27[0] = (unsigned __int8 *)CoTaskMemAlloc(v8);
  v3 = v27[0];
  if ( !v27[0] )
  {
    v11 = -2147024882;
    goto LABEL_36;
  }
  v12 = *((_QWORD *)this + 15);
  v29 = 0;
  v13 = (v12 + 16) & -(__int64)(v12 != 0);
  v14 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, _QWORD, int *))(*(_QWORD *)v13 + 24LL))(
          v13,
          v27[0],
          (unsigned int)v8,
          &v29);
  v15 = (int)g_doStackCaptures;
  v11 = v14;
  if ( v14 >= 0 )
  {
    if ( (_DWORD)v8 == v29 )
      goto LABEL_7;
    v11 = -2003292302;
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_7;
    v24 = -2003292302;
    goto LABEL_43;
  }
  if ( (_DWORD)g_doStackCaptures )
  {
    v24 = v14;
LABEL_43:
    DoStackCapture(v24);
    v15 = (int)g_doStackCaptures;
  }
  if ( v15 )
  {
    DoStackCapture(v11);
    v15 = (int)g_doStackCaptures;
  }
LABEL_7:
  if ( (v11 & 0x80000000) != 0 )
    goto LABEL_23;
  if ( v28 <= 7u )
  {
    if ( v28 != 7 )
    {
      if ( v28 == 1 )
      {
        a3->vt = 4113;
LABEL_72:
        a3->lVal = v8;
        goto LABEL_48;
      }
      if ( v28 == 2 )
      {
        ValueAsciiTag = CMetadataIFDReaderWriter::GetValueAsciiTag(this, v8, v27, 1, a3);
        v11 = ValueAsciiTag;
        if ( ValueAsciiTag >= 0 || !(_DWORD)g_doStackCaptures )
          goto LABEL_22;
        goto LABEL_50;
      }
      if ( v28 != 3 )
      {
        v16 = (unsigned int)v28 - 4;
        if ( v28 != 4 )
        {
          v17 = (unsigned int)v28 - 5;
          if ( v28 == 5 )
          {
            v18 = 21;
            goto LABEL_16;
          }
          if ( v28 == 6 )
          {
            a3->vt = 4112;
            goto LABEL_72;
          }
          goto LABEL_90;
        }
        a3->vt = 4115;
        goto LABEL_58;
      }
      goto LABEL_63;
    }
    a3->vt = 65;
    a3->lVal = v8;
    a3->bstrblobVal.pData = v3;
    if ( !(unsigned int)IFD::FieldEntry::IsCommentTag(a2) )
      return v11;
    v21 = CMetadataIFDReaderWriter::ProcessCommentByteOrder(this, v3, v8);
    v11 = v21;
    if ( v21 >= 0 || !(_DWORD)g_doStackCaptures )
      return v11;
    v22 = v21;
LABEL_54:
    DoStackCapture(v22);
    return v11;
  }
  if ( v28 != 8 )
  {
    v16 = (unsigned int)v28 - 9;
    if ( v28 == 9 )
    {
      a3->vt = 4099;
    }
    else
    {
      v17 = (unsigned int)v28 - 10;
      if ( v28 == 10 )
      {
        v18 = 20;
LABEL_16:
        a3->vt = v18;
        if ( (*((_BYTE *)this + 132) & 1) == 0 )
        {
LABEL_19:
          if ( *((_DWORD *)a2 + 1) == 1 )
          {
            a3->lVal = *(_DWORD *)v3;
            a3->hVal.HighPart = *((_DWORD *)v3 + 1);
LABEL_24:
            CoTaskMemFree(v3);
            return v11;
          }
          a3->vt |= 0x1000u;
          goto LABEL_47;
        }
        ValueAsciiTag = CMetadataIFDReaderWriter::SwapByteOrder(v17, v28, v27, *((unsigned int *)a2 + 1), 1, 0);
        v11 = ValueAsciiTag;
        if ( ValueAsciiTag >= 0 )
        {
          v3 = v27[0];
          goto LABEL_19;
        }
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_22;
LABEL_50:
        DoStackCapture(ValueAsciiTag);
LABEL_22:
        v3 = v27[0];
        goto LABEL_23;
      }
      v16 = (unsigned int)v28 - 11;
      if ( v28 != 11 )
      {
        if ( v28 != 12 )
        {
LABEL_90:
          v11 = -2147418113;
          v23 = v15 == 0;
LABEL_37:
          if ( !v23 )
            DoStackCapture(v11);
          goto LABEL_23;
        }
        if ( (*((_BYTE *)this + 132) & 1) != 0 )
        {
          ValueAsciiTag = CMetadataIFDReaderWriter::SwapByteOrder(v16, 12, v27, *((unsigned int *)a2 + 1), 1, 0);
          v11 = ValueAsciiTag;
          if ( ValueAsciiTag < 0 )
          {
            if ( !(_DWORD)g_doStackCaptures )
              goto LABEL_22;
            goto LABEL_50;
          }
          v3 = v27[0];
        }
        if ( *((_DWORD *)a2 + 1) == 1 )
        {
          a3->vt = 5;
          a3->hVal.QuadPart = *(_QWORD *)v3;
          goto LABEL_24;
        }
        a3->vt = 4101;
LABEL_47:
        a3->lVal = *((_DWORD *)a2 + 1);
LABEL_48:
        a3->bstrblobVal.pData = v3;
        return v11;
      }
      a3->vt = 4100;
    }
LABEL_58:
    if ( (*((_BYTE *)this + 132) & 1) != 0 )
    {
      ValueAsciiTag = CMetadataIFDReaderWriter::SwapByteOrder(v16, v28, v27, *((unsigned int *)a2 + 1), 1, 0);
      v11 = ValueAsciiTag;
      if ( ValueAsciiTag < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_22;
        goto LABEL_50;
      }
      v3 = v27[0];
    }
    goto LABEL_47;
  }
LABEL_63:
  v25 = 4114;
  if ( *((_WORD *)a2 + 1) != 3 )
    v25 = 4098;
  a3->vt = v25;
  if ( (*((_BYTE *)this + 132) & 1) != 0 )
  {
    ValueAsciiTag = CMetadataIFDReaderWriter::SwapByteOrder(4098, v28, v27, *((unsigned int *)a2 + 1), 1, 0);
    v11 = ValueAsciiTag;
    if ( ValueAsciiTag < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_22;
      goto LABEL_50;
    }
    v3 = v27[0];
  }
  v26 = *((_DWORD *)a2 + 1);
  a3->bstrblobVal.pData = v3;
  v3 = 0;
  a3->lVal = v26;
LABEL_23:
  if ( v3 )
    goto LABEL_24;
  return v11;
}

```

## disassembly

```asm
0x180054104  mov     [rsp-38h+arg_0], rbx
0x180054109  push    rbp
0x18005410a  push    rsi
0x18005410b  push    rdi
0x18005410c  push    r12
0x18005410e  push    r13
0x180054110  push    r14
0x180054112  push    r15
0x180054114  mov     rbp, rsp
0x180054117  sub     rsp, 40h
0x18005411b  movzx   eax, word ptr [rdx+2]
0x18005411f  xor     esi, esi
0x180054121  test    byte ptr [rdx+10h], 10h
0x180054125  mov     r14, r8
0x180054128  mov     r15, rdx
0x18005412b  mov     [rbp+arg_8], ax
0x18005412f  mov     r13, rcx
0x180054132  jz      loc_1800542D6
0x180054138  mov     rdi, [r13+78h]
0x18005413c  mov     r12d, [r15+14h]
0x180054140  mov     ebx, [r15+8]
0x180054144  lea     rcx, [rdi+10h]
0x180054148  mov     rax, [rcx]
0x18005414b  mov     rax, [rax+70h]
0x18005414f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054154  mov     rax, [rdi]
0x180054157  mov     edx, ebx
0x180054159  xor     r9d, r9d
0x18005415c  xor     r8d, r8d
0x18005415f  mov     rcx, rdi
0x180054162  mov     rax, [rax+68h]
0x180054166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005416b  mov     ebx, eax
0x18005416d  test    eax, eax
0x18005416f  js      loc_180054378
0x180054175  lea     rcx, [rdi+10h]
0x180054179  mov     rax, [rcx]
0x18005417c  mov     rax, [rax+78h]
0x180054180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054185  xor     edi, edi
0x180054187  test    ebx, ebx
0x180054189  js      loc_180054360
0x18005418f  mov     rcx, r12; cb
0x180054192  call    cs:__imp_CoTaskMemAlloc
0x180054198  mov     [rbp+var_10], rax
0x18005419c  mov     rsi, rax
0x18005419f  test    rax, rax
0x1800541a2  jz      loc_180054587
0x1800541a8  mov     rax, [r13+78h]
0x1800541ac  lea     r9, [rbp+arg_18]
0x1800541b0  mov     r8d, r12d
0x1800541b3  mov     [rbp+arg_18], edi
0x1800541b6  lea     rdx, [rax+10h]
0x1800541ba  neg     rax
0x1800541bd  sbb     rcx, rcx
0x1800541c0  and     rcx, rdx
0x1800541c3  mov     rdx, rsi
0x1800541c6  mov     rax, [rcx]
0x1800541c9  mov     rax, [rax+18h]
0x1800541cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800541d2  mov     r8d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800541d9  mov     ebx, eax
0x1800541db  test    eax, eax
0x1800541dd  js      loc_180054390
0x1800541e3  cmp     r12d, [rbp+arg_18]
0x1800541e7  jnz     loc_1800544CC
0x1800541ed  test    ebx, ebx
0x1800541ef  js      loc_1800542AE
0x1800541f5  movzx   edx, [rbp+arg_8]
0x1800541f9  cmp     edx, 7
0x1800541fc  ja      loc_1800542F6
0x180054202  jz      loc_18005431B
0x180054208  mov     ecx, edx
0x18005420a  sub     ecx, 1
0x18005420d  jz      loc_1800544E1
0x180054213  sub     ecx, 1
0x180054216  jz      short loc_180054286
0x180054218  sub     ecx, 1
0x18005421b  jz      loc_18005447A
0x180054221  sub     ecx, 1
0x180054224  jz      loc_180054431
0x18005422a  sub     ecx, 1
0x18005422d  jnz     loc_180054591
0x180054233  lea     eax, [rcx+15h]
0x180054236  mov     [r14], ax
0x18005423a  test    byte ptr [r13+84h], 1
0x180054242  jz      short loc_18005426C
0x180054244  mov     r9d, [r15+4]
0x180054248  lea     r8, [rbp+var_10]
0x18005424c  mov     [rsp+40h+var_18], rdi
0x180054251  mov     dword ptr [rsp+40h+var_20], 1
0x180054259  call    ?SwapByteOrder@CMetadataIFDReaderWriter@@IEAAJW4TagType@IFD@@PEAPEAEIHPEAH@Z; CMetadataIFDReaderWriter::SwapByteOrder(IFD::TagType,uchar * *,uint,int,int *)
0x18005425e  mov     ebx, eax
0x180054260  test    eax, eax
0x180054262  js      loc_1800543DD
0x180054268  mov     rsi, [rbp+var_10]
0x18005426c  cmp     dword ptr [r15+4], 1
0x180054271  jnz     loc_1800543C3
0x180054277  mov     eax, [rsi]
0x180054279  mov     [r14+8], eax
0x18005427d  mov     eax, [rsi+4]
0x180054280  mov     [r14+0Ch], eax
0x180054284  jmp     short loc_1800542B3
0x180054286  mov     r9d, 1; int
0x18005428c  mov     [rsp+40h+var_20], r14; struct tagPROPVARIANT *
0x180054291  lea     r8, [rbp+var_10]; unsigned __int8 **
0x180054295  mov     edx, r12d; unsigned int
0x180054298  mov     rcx, r13; this
0x18005429b  call    ?GetValueAsciiTag@CMetadataIFDReaderWriter@@IEAAJKPEAPEAEHPEAUtagPROPVARIANT@@@Z; CMetadataIFDReaderWriter::GetValueAsciiTag(ulong,uchar * *,int,tagPROPVARIANT *)
0x1800542a0  mov     ebx, eax
0x1800542a2  test    eax, eax
0x1800542a4  js      loc_180054424
0x1800542aa  mov     rsi, [rbp+var_10]
0x1800542ae  test    rsi, rsi
0x1800542b1  jz      short loc_1800542BC
0x1800542b3  mov     rcx, rsi; pv
0x1800542b6  call    cs:__imp_CoTaskMemFree
0x1800542bc  mov     eax, ebx
0x1800542be  mov     rbx, [rsp+40h+arg_0]
0x1800542c6  add     rsp, 40h
0x1800542ca  pop     r15
0x1800542cc  pop     r14
0x1800542ce  pop     r13
0x1800542d0  pop     r12
0x1800542d2  pop     rdi
0x1800542d3  pop     rsi
0x1800542d4  pop     rbp
0x1800542d5  retn
0x1800542d6  add     rdx, 14h; unsigned int *
0x1800542da  mov     rcx, r15; this
0x1800542dd  call    ?ComputeTagDataSize@TagEntry@IFD@@IEAAJPEAK@Z; IFD::TagEntry::ComputeTagDataSize(ulong *)
0x1800542e2  mov     ebx, eax
0x1800542e4  test    eax, eax
0x1800542e6  js      loc_1800543F5
0x1800542ec  or      dword ptr [r15+10h], 10h
0x1800542f1  jmp     loc_180054138
0x1800542f6  mov     ecx, edx
0x1800542f8  sub     ecx, 8
0x1800542fb  jz      loc_18005447A
0x180054301  sub     ecx, 1
0x180054304  jz      loc_1800545E0
0x18005430a  sub     ecx, 1
0x18005430d  jnz     loc_1800545A1
0x180054313  lea     eax, [rcx+14h]
0x180054316  jmp     loc_180054236
0x18005431b  mov     rcx, r15; this
0x18005431e  mov     word ptr [r14], 41h ; 'A'
0x180054324  mov     [r14+8], r12d
0x180054328  mov     [r14+10h], rsi
0x18005432c  call    ?IsCommentTag@FieldEntry@IFD@@QEAAHXZ; IFD::FieldEntry::IsCommentTag(void)
0x180054331  test    eax, eax
0x180054333  jz      short loc_1800542BC
0x180054335  mov     r8d, r12d; unsigned int
0x180054338  mov     rdx, rsi; unsigned __int8 *
0x18005433b  mov     rcx, r13; this
0x18005433e  call    ?ProcessCommentByteOrder@CMetadataIFDReaderWriter@@IEAAJPEAEK@Z; CMetadataIFDReaderWriter::ProcessCommentByteOrder(uchar *,ulong)
0x180054343  mov     ebx, eax
0x180054345  test    eax, eax
0x180054347  jns     loc_1800542BC
0x18005434d  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180054353  jz      loc_1800542BC
0x180054359  mov     ecx, eax
0x18005435b  jmp     loc_18005441A
0x180054360  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180054366  jz      loc_1800542AE
0x18005436c  mov     ecx, ebx; int
0x18005436e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180054373  jmp     loc_1800542AE
0x180054378  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x18005437e  jz      loc_180054175
0x180054384  mov     ecx, ebx; int
0x180054386  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18005438b  jmp     loc_180054175
0x180054390  test    r8d, r8d
0x180054393  jz      loc_1800544B2
0x180054399  mov     ecx, eax; int
0x18005439b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800543a0  mov     r8d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800543a7  test    r8d, r8d
0x1800543aa  jz      loc_1800541ED
0x1800543b0  mov     ecx, ebx; int
0x1800543b2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800543b7  mov     r8d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800543be  jmp     loc_1800541ED
0x1800543c3  mov     eax, 1000h
0x1800543c8  or      [r14], ax
0x1800543cc  mov     eax, [r15+4]
0x1800543d0  mov     [r14+8], eax
0x1800543d4  mov     [r14+10h], rsi
0x1800543d8  jmp     loc_1800542BC
0x1800543dd  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800543e3  jz      loc_1800544BF
0x1800543e9  mov     ecx, eax; int
0x1800543eb  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800543f0  jmp     loc_1800542AA
0x1800543f5  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800543fb  test    eax, eax
0x1800543fd  jz      loc_1800542BC
0x180054403  mov     ecx, ebx; int
0x180054405  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18005440a  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180054410  test    eax, eax
0x180054412  jz      loc_1800542BC
0x180054418  mov     ecx, ebx; int
0x18005441a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18005441f  jmp     loc_1800542BC
0x180054424  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18005442a  jnz     short loc_1800543E9
0x18005442c  jmp     loc_1800542AA
0x180054431  mov     word ptr [r14], 1013h
0x180054437  test    byte ptr [r13+84h], 1
0x18005443f  jz      short loc_1800543CC
0x180054441  mov     r9d, [r15+4]
0x180054445  lea     r8, [rbp+var_10]
0x180054449  mov     [rsp+40h+var_18], rdi
0x18005444e  mov     dword ptr [rsp+40h+var_20], 1
0x180054456  call    ?SwapByteOrder@CMetadataIFDReaderWriter@@IEAAJW4TagType@IFD@@PEAPEAEIHPEAH@Z; CMetadataIFDReaderWriter::SwapByteOrder(IFD::TagType,uchar * *,uint,int,int *)
0x18005445b  mov     ebx, eax
0x18005445d  test    eax, eax
0x18005445f  jns     short loc_180054471
0x180054461  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180054467  jnz     short loc_1800543E9
0x180054469  test    eax, eax
0x18005446b  js      loc_1800542AA
0x180054471  mov     rsi, [rbp+var_10]
0x180054475  jmp     loc_1800543CC
0x18005447a  cmp     word ptr [r15+2], 3
0x180054480  mov     eax, 1012h
0x180054485  lea     ecx, [rax-10h]
0x180054488  cmovnz  ax, cx
0x18005448c  mov     [r14], ax
0x180054490  test    byte ptr [r13+84h], 1
0x180054498  jnz     loc_18005454A
0x18005449e  mov     ecx, [r15+4]
0x1800544a2  mov     [r14+10h], rsi
0x1800544a6  mov     rsi, rdi
0x1800544a9  mov     [r14+8], ecx
0x1800544ad  jmp     loc_1800542AE
0x1800544b2  test    eax, eax
0x1800544b4  jns     loc_1800541E3
0x1800544ba  jmp     loc_1800543A7
0x1800544bf  test    eax, eax
0x1800544c1  js      loc_1800542AA
0x1800544c7  jmp     loc_180054268
0x1800544cc  mov     ebx, 88982F72h
0x1800544d1  test    r8d, r8d
0x1800544d4  jz      loc_1800541ED
0x1800544da  mov     ecx, ebx
0x1800544dc  jmp     loc_18005439B
0x1800544e1  mov     word ptr [r14], 1011h
0x1800544e7  mov     [r14+8], r12d
0x1800544eb  jmp     loc_1800543D4
0x1800544f0  mov     r9d, [r15+4]
0x1800544f4  lea     r8, [rbp+var_10]
0x1800544f8  mov     [rsp+40h+var_18], rdi
0x1800544fd  mov     edx, 0Ch
0x180054502  mov     dword ptr [rsp+40h+var_20], 1
0x18005450a  call    ?SwapByteOrder@CMetadataIFDReaderWriter@@IEAAJW4TagType@IFD@@PEAPEAEIHPEAH@Z; CMetadataIFDReaderWriter::SwapByteOrder(IFD::TagType,uchar * *,uint,int,int *)
0x18005450f  mov     ebx, eax
0x180054511  test    eax, eax
0x180054513  jns     short loc_180054529
0x180054515  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18005451b  jnz     loc_1800543E9
0x180054521  test    eax, eax
0x180054523  js      loc_1800542AA
0x180054529  mov     rsi, [rbp+var_10]
0x18005452d  cmp     dword ptr [r15+4], 1
0x180054532  jnz     loc_1800545CA
0x180054538  mov     word ptr [r14], 5
0x18005453e  mov     rax, [rsi]
0x180054541  mov     [r14+8], rax
0x180054545  jmp     loc_1800542B3
0x18005454a  mov     r9d, [r15+4]
0x18005454e  lea     r8, [rbp+var_10]
0x180054552  mov     [rsp+40h+var_18], rdi
0x180054557  mov     dword ptr [rsp+40h+var_20], 1
0x18005455f  call    ?SwapByteOrder@CMetadataIFDReaderWriter@@IEAAJW4TagType@IFD@@PEAPEAEIHPEAH@Z; CMetadataIFDReaderWriter::SwapByteOrder(IFD::TagType,uchar * *,uint,int,int *)
0x180054564  mov     ebx, eax
0x180054566  test    eax, eax
0x180054568  jns     short loc_18005457E
0x18005456a  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180054570  jnz     loc_1800543E9
0x180054576  test    eax, eax
0x180054578  js      loc_1800542AA
0x18005457e  mov     rsi, [rbp+var_10]
0x180054582  jmp     loc_18005449E
0x180054587  mov     ebx, 8007000Eh
0x18005458c  jmp     loc_180054360
0x180054591  cmp     ecx, 1
0x180054594  jnz     short loc_1800545BD
0x180054596  mov     word ptr [r14], 1010h
0x18005459c  jmp     loc_1800544E7
0x1800545a1  sub     ecx, 1
0x1800545a4  jz      short loc_1800545D5
0x1800545a6  cmp     ecx, 1
0x1800545a9  jnz     short loc_1800545BD
0x1800545ab  test    [r13+84h], cl
0x1800545b2  jz      loc_18005452D
0x1800545b8  jmp     loc_1800544F0
0x1800545bd  mov     ebx, 8000FFFFh
  ... truncated ...
```
