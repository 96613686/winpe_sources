# CMetadataIFDReaderWriter::GetTagVariantValueAtOffset(IFD::FieldEntry *,tagPROPVARIANT *)

- ea: `0x180048f40`
- end: `0x180049434`
- name: `?GetTagVariantValueAtOffset@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEAUtagPROPVARIANT@@@Z`
- size: `1268`
- prototype: `__int64 __fastcall(CMetadataIFDReaderWriter *this, struct IFD::FieldEntry *, PROPVARIANT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180049c00`

## callees

- `0x180048f40`
- `0x18004943c`
- `0x180049eb8`
- `0x18004a284`
- `0x18004a3d0`
- `0x18004ad80`
- `0x1800bd9d4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180048fce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180048fce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800490f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800490f8`

## pseudocode

```c
__int64 __fastcall CMetadataIFDReaderWriter::GetTagVariantValueAtOffset(
        CMetadataIFDReaderWriter *this,
        struct IFD::FieldEntry *a2,
        PROPVARIANT *a3)
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
        *(_WORD *)a3 = 4113;
LABEL_72:
        *((_DWORD *)a3 + 2) = v8;
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
            *(_WORD *)a3 = 4112;
            goto LABEL_72;
          }
          goto LABEL_90;
        }
        *(_WORD *)a3 = 4115;
        goto LABEL_58;
      }
      goto LABEL_63;
    }
    *(_WORD *)a3 = 65;
    *((_DWORD *)a3 + 2) = v8;
    a3[2] = v3;
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
      *(_WORD *)a3 = 4099;
    }
    else
    {
      v17 = (unsigned int)v28 - 10;
      if ( v28 == 10 )
      {
        v18 = 20;
LABEL_16:
        *(_WORD *)a3 = v18;
        if ( (*((_BYTE *)this + 132) & 1) == 0 )
        {
LABEL_19:
          if ( *((_DWORD *)a2 + 1) == 1 )
          {
            *((_DWORD *)a3 + 2) = *(_DWORD *)v3;
            *((_DWORD *)a3 + 3) = *((_DWORD *)v3 + 1);
LABEL_24:
            CoTaskMemFree(v3);
            return v11;
          }
          *(_WORD *)a3 |= 0x1000u;
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
          *(_WORD *)a3 = 5;
          a3[1] = *(PROPVARIANT *)v3;
          goto LABEL_24;
        }
        *(_WORD *)a3 = 4101;
LABEL_47:
        *((_DWORD *)a3 + 2) = *((_DWORD *)a2 + 1);
LABEL_48:
        a3[2] = v3;
        return v11;
      }
      *(_WORD *)a3 = 4100;
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
  *(_WORD *)a3 = v25;
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
  a3[2] = v3;
  v3 = 0;
  *((_DWORD *)a3 + 2) = v26;
LABEL_23:
  if ( v3 )
    goto LABEL_24;
  return v11;
}

```

## disassembly

```asm
0x180048f40  mov     [rsp-38h+arg_0], rbx
0x180048f45  push    rbp
0x180048f46  push    rsi
0x180048f47  push    rdi
0x180048f48  push    r12
0x180048f4a  push    r13
0x180048f4c  push    r14
0x180048f4e  push    r15
0x180048f50  mov     rbp, rsp
0x180048f53  sub     rsp, 40h
0x180048f57  movzx   eax, word ptr [rdx+2]
0x180048f5b  xor     esi, esi
0x180048f5d  test    byte ptr [rdx+10h], 10h
0x180048f61  mov     r14, r8
0x180048f64  mov     r15, rdx
0x180048f67  mov     [rbp+arg_8], ax
0x180048f6b  mov     r13, rcx
0x180048f6e  jz      loc_18004911F
0x180048f74  mov     rdi, [r13+78h]
0x180048f78  mov     r12d, [r15+14h]
0x180048f7c  mov     ebx, [r15+8]
0x180048f80  lea     rcx, [rdi+10h]
0x180048f84  mov     rax, [rcx]
0x180048f87  mov     rax, [rax+70h]
0x180048f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f90  mov     rax, [rdi]
0x180048f93  mov     edx, ebx
0x180048f95  xor     r9d, r9d
0x180048f98  xor     r8d, r8d
0x180048f9b  mov     rcx, rdi
0x180048f9e  mov     rax, [rax+68h]
0x180048fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048fa7  mov     ebx, eax
0x180048fa9  test    eax, eax
0x180048fab  js      loc_1800491C1
0x180048fb1  lea     rcx, [rdi+10h]
0x180048fb5  mov     rax, [rcx]
0x180048fb8  mov     rax, [rax+78h]
0x180048fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048fc1  xor     edi, edi
0x180048fc3  test    ebx, ebx
0x180048fc5  js      loc_1800491A9
0x180048fcb  mov     rcx, r12; cb
0x180048fce  call    cs:__imp_CoTaskMemAlloc
0x180048fd5  nop     dword ptr [rax+rax+00h]
0x180048fda  mov     [rbp+var_10], rax
0x180048fde  mov     rsi, rax
0x180048fe1  test    rax, rax
0x180048fe4  jz      loc_1800493D0
0x180048fea  mov     rax, [r13+78h]
0x180048fee  lea     r9, [rbp+arg_18]
0x180048ff2  mov     r8d, r12d
0x180048ff5  mov     [rbp+arg_18], edi
0x180048ff8  lea     rdx, [rax+10h]
0x180048ffc  neg     rax
0x180048fff  sbb     rcx, rcx
0x180049002  and     rcx, rdx
0x180049005  mov     rdx, rsi
0x180049008  mov     rax, [rcx]
0x18004900b  mov     rax, [rax+18h]
0x18004900f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049014  mov     r8d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18004901b  mov     ebx, eax
0x18004901d  test    eax, eax
0x18004901f  js      loc_1800491D9
0x180049025  cmp     r12d, [rbp+arg_18]
0x180049029  jnz     loc_180049315
0x18004902f  test    ebx, ebx
0x180049031  js      loc_1800490F0
0x180049037  movzx   edx, [rbp+arg_8]
0x18004903b  cmp     edx, 7
0x18004903e  ja      loc_18004913F
0x180049044  jz      loc_180049164
0x18004904a  mov     ecx, edx
0x18004904c  sub     ecx, 1
0x18004904f  jz      loc_18004932A
0x180049055  sub     ecx, 1
0x180049058  jz      short loc_1800490C8
0x18004905a  sub     ecx, 1
0x18004905d  jz      loc_1800492C3
0x180049063  sub     ecx, 1
0x180049066  jz      loc_18004927A
0x18004906c  sub     ecx, 1
0x18004906f  jnz     loc_1800493DA
0x180049075  lea     eax, [rcx+15h]
0x180049078  mov     [r14], ax
0x18004907c  test    byte ptr [r13+84h], 1
0x180049084  jz      short loc_1800490AE
0x180049086  mov     r9d, [r15+4]
0x18004908a  lea     r8, [rbp+var_10]
0x18004908e  mov     [rsp+40h+var_18], rdi
0x180049093  mov     dword ptr [rsp+40h+var_20], 1
0x18004909b  call    ?SwapByteOrder@CMetadataIFDReaderWriter@@IEAAJW4TagType@IFD@@PEAPEAEIHPEAH@Z; CMetadataIFDReaderWriter::SwapByteOrder(IFD::TagType,uchar * *,uint,int,int *)
0x1800490a0  mov     ebx, eax
0x1800490a2  test    eax, eax
0x1800490a4  js      loc_180049226
0x1800490aa  mov     rsi, [rbp+var_10]
0x1800490ae  cmp     dword ptr [r15+4], 1
0x1800490b3  jnz     loc_18004920C
0x1800490b9  mov     eax, [rsi]
0x1800490bb  mov     [r14+8], eax
0x1800490bf  mov     eax, [rsi+4]
0x1800490c2  mov     [r14+0Ch], eax
0x1800490c6  jmp     short loc_1800490F5
0x1800490c8  mov     r9d, 1; int
0x1800490ce  mov     [rsp+40h+var_20], r14; struct tagPROPVARIANT *
0x1800490d3  lea     r8, [rbp+var_10]; unsigned __int8 **
0x1800490d7  mov     edx, r12d; unsigned int
0x1800490da  mov     rcx, r13; this
0x1800490dd  call    ?GetValueAsciiTag@CMetadataIFDReaderWriter@@IEAAJKPEAPEAEHPEAUtagPROPVARIANT@@@Z; CMetadataIFDReaderWriter::GetValueAsciiTag(ulong,uchar * *,int,tagPROPVARIANT *)
0x1800490e2  mov     ebx, eax
0x1800490e4  test    eax, eax
0x1800490e6  js      loc_18004926D
0x1800490ec  mov     rsi, [rbp+var_10]
0x1800490f0  test    rsi, rsi
0x1800490f3  jz      short loc_180049104
0x1800490f5  mov     rcx, rsi; pv
0x1800490f8  call    cs:__imp_CoTaskMemFree
0x1800490ff  nop     dword ptr [rax+rax+00h]
0x180049104  mov     eax, ebx
0x180049106  mov     rbx, [rsp+40h+arg_0]
0x18004910e  add     rsp, 40h
0x180049112  pop     r15
0x180049114  pop     r14
0x180049116  pop     r13
0x180049118  pop     r12
0x18004911a  pop     rdi
0x18004911b  pop     rsi
0x18004911c  pop     rbp
0x18004911d  retn
0x18004911f  add     rdx, 14h; unsigned int *
0x180049123  mov     rcx, r15; this
0x180049126  call    ?ComputeTagDataSize@TagEntry@IFD@@IEAAJPEAK@Z; IFD::TagEntry::ComputeTagDataSize(ulong *)
0x18004912b  mov     ebx, eax
0x18004912d  test    eax, eax
0x18004912f  js      loc_18004923E
0x180049135  or      dword ptr [r15+10h], 10h
0x18004913a  jmp     loc_180048F74
0x18004913f  mov     ecx, edx
0x180049141  sub     ecx, 8
0x180049144  jz      loc_1800492C3
0x18004914a  sub     ecx, 1
0x18004914d  jz      loc_180049429
0x180049153  sub     ecx, 1
0x180049156  jnz     loc_1800493EA
0x18004915c  lea     eax, [rcx+14h]
0x18004915f  jmp     loc_180049078
0x180049164  mov     rcx, r15; this
0x180049167  mov     word ptr [r14], 41h ; 'A'
0x18004916d  mov     [r14+8], r12d
0x180049171  mov     [r14+10h], rsi
0x180049175  call    ?IsCommentTag@FieldEntry@IFD@@QEAAHXZ; IFD::FieldEntry::IsCommentTag(void)
0x18004917a  test    eax, eax
0x18004917c  jz      short loc_180049104
0x18004917e  mov     r8d, r12d; unsigned int
0x180049181  mov     rdx, rsi; unsigned __int8 *
0x180049184  mov     rcx, r13; this
0x180049187  call    ?ProcessCommentByteOrder@CMetadataIFDReaderWriter@@IEAAJPEAEK@Z; CMetadataIFDReaderWriter::ProcessCommentByteOrder(uchar *,ulong)
0x18004918c  mov     ebx, eax
0x18004918e  test    eax, eax
0x180049190  jns     loc_180049104
0x180049196  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18004919c  jz      loc_180049104
0x1800491a2  mov     ecx, eax
0x1800491a4  jmp     loc_180049263
0x1800491a9  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800491af  jz      loc_1800490F0
0x1800491b5  mov     ecx, ebx; int
0x1800491b7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800491bc  jmp     loc_1800490F0
0x1800491c1  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x1800491c7  jz      loc_180048FB1
0x1800491cd  mov     ecx, ebx; int
0x1800491cf  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800491d4  jmp     loc_180048FB1
0x1800491d9  test    r8d, r8d
0x1800491dc  jz      loc_1800492FB
0x1800491e2  mov     ecx, eax; int
0x1800491e4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800491e9  mov     r8d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800491f0  test    r8d, r8d
0x1800491f3  jz      loc_18004902F
0x1800491f9  mov     ecx, ebx; int
0x1800491fb  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180049200  mov     r8d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180049207  jmp     loc_18004902F
0x18004920c  mov     eax, 1000h
0x180049211  or      [r14], ax
0x180049215  mov     eax, [r15+4]
0x180049219  mov     [r14+8], eax
0x18004921d  mov     [r14+10h], rsi
0x180049221  jmp     loc_180049104
0x180049226  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18004922c  jz      loc_180049308
0x180049232  mov     ecx, eax; int
0x180049234  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180049239  jmp     loc_1800490EC
0x18004923e  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180049244  test    eax, eax
0x180049246  jz      loc_180049104
0x18004924c  mov     ecx, ebx; int
0x18004924e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180049253  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180049259  test    eax, eax
0x18004925b  jz      loc_180049104
0x180049261  mov     ecx, ebx; int
0x180049263  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180049268  jmp     loc_180049104
0x18004926d  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180049273  jnz     short loc_180049232
0x180049275  jmp     loc_1800490EC
0x18004927a  mov     word ptr [r14], 1013h
0x180049280  test    byte ptr [r13+84h], 1
0x180049288  jz      short loc_180049215
0x18004928a  mov     r9d, [r15+4]
0x18004928e  lea     r8, [rbp+var_10]
0x180049292  mov     [rsp+40h+var_18], rdi
0x180049297  mov     dword ptr [rsp+40h+var_20], 1
0x18004929f  call    ?SwapByteOrder@CMetadataIFDReaderWriter@@IEAAJW4TagType@IFD@@PEAPEAEIHPEAH@Z; CMetadataIFDReaderWriter::SwapByteOrder(IFD::TagType,uchar * *,uint,int,int *)
0x1800492a4  mov     ebx, eax
0x1800492a6  test    eax, eax
0x1800492a8  jns     short loc_1800492BA
0x1800492aa  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800492b0  jnz     short loc_180049232
0x1800492b2  test    eax, eax
0x1800492b4  js      loc_1800490EC
0x1800492ba  mov     rsi, [rbp+var_10]
0x1800492be  jmp     loc_180049215
0x1800492c3  cmp     word ptr [r15+2], 3
0x1800492c9  mov     eax, 1012h
0x1800492ce  lea     ecx, [rax-10h]
0x1800492d1  cmovnz  ax, cx
0x1800492d5  mov     [r14], ax
0x1800492d9  test    byte ptr [r13+84h], 1
0x1800492e1  jnz     loc_180049393
0x1800492e7  mov     ecx, [r15+4]
0x1800492eb  mov     [r14+10h], rsi
0x1800492ef  mov     rsi, rdi
0x1800492f2  mov     [r14+8], ecx
0x1800492f6  jmp     loc_1800490F0
0x1800492fb  test    eax, eax
0x1800492fd  jns     loc_180049025
0x180049303  jmp     loc_1800491F0
0x180049308  test    eax, eax
0x18004930a  js      loc_1800490EC
0x180049310  jmp     loc_1800490AA
0x180049315  mov     ebx, 88982F72h
0x18004931a  test    r8d, r8d
0x18004931d  jz      loc_18004902F
0x180049323  mov     ecx, ebx
0x180049325  jmp     loc_1800491E4
0x18004932a  mov     word ptr [r14], 1011h
0x180049330  mov     [r14+8], r12d
0x180049334  jmp     loc_18004921D
0x180049339  mov     r9d, [r15+4]
0x18004933d  lea     r8, [rbp+var_10]
0x180049341  mov     [rsp+40h+var_18], rdi
0x180049346  mov     edx, 0Ch
0x18004934b  mov     dword ptr [rsp+40h+var_20], 1
0x180049353  call    ?SwapByteOrder@CMetadataIFDReaderWriter@@IEAAJW4TagType@IFD@@PEAPEAEIHPEAH@Z; CMetadataIFDReaderWriter::SwapByteOrder(IFD::TagType,uchar * *,uint,int,int *)
0x180049358  mov     ebx, eax
0x18004935a  test    eax, eax
0x18004935c  jns     short loc_180049372
0x18004935e  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180049364  jnz     loc_180049232
0x18004936a  test    eax, eax
0x18004936c  js      loc_1800490EC
0x180049372  mov     rsi, [rbp+var_10]
0x180049376  cmp     dword ptr [r15+4], 1
0x18004937b  jnz     loc_180049413
0x180049381  mov     word ptr [r14], 5
0x180049387  mov     rax, [rsi]
0x18004938a  mov     [r14+8], rax
0x18004938e  jmp     loc_1800490F5
0x180049393  mov     r9d, [r15+4]
0x180049397  lea     r8, [rbp+var_10]
0x18004939b  mov     [rsp+40h+var_18], rdi
0x1800493a0  mov     dword ptr [rsp+40h+var_20], 1
0x1800493a8  call    ?SwapByteOrder@CMetadataIFDReaderWriter@@IEAAJW4TagType@IFD@@PEAPEAEIHPEAH@Z; CMetadataIFDReaderWriter::SwapByteOrder(IFD::TagType,uchar * *,uint,int,int *)
0x1800493ad  mov     ebx, eax
0x1800493af  test    eax, eax
0x1800493b1  jns     short loc_1800493C7
0x1800493b3  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800493b9  jnz     loc_180049232
0x1800493bf  test    eax, eax
0x1800493c1  js      loc_1800490EC
0x1800493c7  mov     rsi, [rbp+var_10]
0x1800493cb  jmp     loc_1800492E7
0x1800493d0  mov     ebx, 8007000Eh
0x1800493d5  jmp     loc_1800491A9
0x1800493da  cmp     ecx, 1
0x1800493dd  jnz     short loc_180049406
0x1800493df  mov     word ptr [r14], 1010h
0x1800493e5  jmp     loc_180049330
0x1800493ea  sub     ecx, 1
0x1800493ed  jz      short loc_18004941E
0x1800493ef  cmp     ecx, 1
0x1800493f2  jnz     short loc_180049406
0x1800493f4  test    [r13+84h], cl
0x1800493fb  jz      loc_180049376
  ... truncated ...
```
