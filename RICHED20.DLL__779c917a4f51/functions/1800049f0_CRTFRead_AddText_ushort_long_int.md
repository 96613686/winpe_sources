# CRTFRead::AddText(ushort *,long,int)

- ea: `0x1800049f0`
- end: `0x180004fd5`
- name: `?AddText@CRTFRead@@AEAAHPEAGJH@Z`
- size: `1509`
- prototype: `__int64 __fastcall(CRTFRead *__hidden this, unsigned __int16 *, int, int)`
- caller_count: `4`
- callee_count: `13`
- tags: ``

## callers

- `0x1800026c0`
- `0x1800049f0`
- `0x18002a7d0`
- `0x1800474a8`

## callees

- `0x1800049f0`
- `0x180004fe0`
- `0x180005480`
- `0x180008f04`
- `0x1800165c0`
- `0x18001bc20`
- `0x1800202a0`
- `0x180022780`
- `0x180048f8c`
- `0x18008a9d8`
- `0x18008b44c`
- `0x1800910fe`
- `0x180092010`

## pseudocode

```c
__int64 __fastcall CRTFRead::AddText(CRTFRead *this, unsigned __int16 *a2, int a3, int a4)
{
  int v4; // r14d
  unsigned __int16 *v5; // rbp
  __int64 v7; // rsi
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // ecx
  char *v11; // r13
  __int64 v12; // rdi
  unsigned int v13; // r15d
  int v14; // eax
  int v15; // ecx
  __int64 v16; // rdx
  _QWORD *v17; // rdi
  int v18; // esi
  struct IUndoBuilder *v19; // rdx
  int v20; // r8d
  int v21; // r12d
  int i; // edi
  unsigned int v23; // ecx
  __int64 v24; // rbp
  int v25; // eax
  int v26; // edi
  __int64 v27; // rsi
  struct IFormatCache *v29; // rdi
  int v30; // ecx
  unsigned int v31; // edi
  unsigned __int8 v32; // al
  char v33; // cl
  __int64 v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rcx
  int v37; // eax
  bool v38; // zf
  unsigned int v39; // edi
  struct CUniscribe *Uniscribe; // rax
  CTxtBreaker *v41; // rcx
  CTxtBreaker *v42; // rax
  CTxtBreaker **v43; // rdx
  __int16 v44; // dx
  __int16 v45; // ax
  char *v46; // rsi
  __int64 v47; // rcx
  int v48; // [rsp+80h] [rbp+8h] BYREF

  v4 = a3;
  v48 = 0;
  v5 = a2;
  if ( a3 <= 0 )
    return *((unsigned int *)this + 12);
  v7 = *((_QWORD *)this + 27);
  if ( (unsigned int)a3 > *((_DWORD *)this + 171) )
  {
    v4 = *((_DWORD *)this + 171);
    *((_DWORD *)this + 12) = 18;
  }
  v8 = *((int *)this + 148);
  if ( *(_WORD *)(v7 + 10) == 13 )
  {
    if ( v4 >= 15 - (int)v8 )
      v4 = 15 - v8;
    if ( v4 > 0 )
    {
      v46 = (char *)this + 2 * v8;
      memmove_0(v46 + 556, a2, 2LL * v4);
      *(_WORD *)&v46[2 * v4 + 556] = 0;
      *((_DWORD *)this + 148) += v4;
    }
    return 0;
  }
  else
  {
    if ( (_DWORD)v8 && a4 )
    {
      *((_DWORD *)this + 148) = 0;
      if ( (*(_BYTE *)(v7 + 4) & 2) != 0 )
      {
        if ( (unsigned int)*((unsigned __int16 *)this + 122) - 2 <= 5 && *((_WORD *)this + v8 + 277) == 9 )
        {
          if ( (int)v8 <= 1 )
          {
            *((_WORD *)this + 356) = 1024;
          }
          else
          {
            v44 = *((_WORD *)this + v8 + 276);
            if ( v44 == 46 )
            {
              v45 = 512;
            }
            else if ( v44 == 41 )
            {
              v45 = 0;
              if ( *((_WORD *)this + 278) == 40 )
                v45 = 256;
            }
            else
            {
              v45 = 768;
            }
            *((_WORD *)this + 356) = v45 | *((_WORD *)this + 356) & 0xFCFF;
          }
        }
      }
      else
      {
        CRTFRead::AddText(this, (unsigned __int16 *)this + 278, v8, 0);
      }
    }
    v9 = *((_DWORD *)this + 172);
    if ( v9
      && (v47 = *((_QWORD *)this + 8), *(_DWORD *)(v47 + 40) == v9)
      && (*((_WORD *)CRchTxtPtr::GetPF((CRchTxtPtr *)(v47 + 8)) + 1) & 0x4000) != 0
      && *((_DWORD *)this + 78)
      && !(unsigned int)CTxtPtr::IsAfterEOP((CTxtPtr *)(*((_QWORD *)this + 8) + 24LL)) )
    {
      *((_DWORD *)this + 79) = 0;
      *((_DWORD *)this + 12) = 6;
    }
    else
    {
      v10 = *((_DWORD *)this + 59);
      if ( v10 || *((_DWORD *)this + 60) )
      {
        v11 = (char *)this + 64;
        CTxtRange::SetCharFormat(
          *((CTxtRange **)this + 8),
          (CRTFRead *)((char *)this + 84),
          0,
          0,
          v10,
          *((_DWORD *)this + 60));
        *(_QWORD *)((char *)this + 236) = 0;
      }
      else
      {
        v11 = (char *)this + 64;
      }
      v12 = *(_QWORD *)v11;
      (**(void (__fastcall ***)(struct IFormatCache *, _QWORD))qword_1800A41F0)(
        qword_1800A41F0,
        (unsigned int)*(__int16 *)(*(_QWORD *)v11 + 96LL));
      v13 = *(__int16 *)(v12 + 96);
      if ( v7 && (v14 = *(_DWORD *)(v7 + 20), v14 >= 0) )
      {
        v15 = *((_DWORD *)this + 2);
        if ( v15 > 0 && v14 < v15 && *(_QWORD *)this )
          v16 = *(_QWORD *)this + *((_DWORD *)this + 4) * v14;
        else
          v16 = 0;
        v17 = (_QWORD *)((char *)this + 64);
      }
      else
      {
        v16 = 0;
        v17 = v11;
      }
      if ( *((_WORD *)this + 357)
        && v16
        && *(_WORD *)(v16 + 72) == 0xFFFF
        && (*((char *)this + 472) >= 0 || (GetCharFlags(*v5, 0) & 0x800000) == 0) )
      {
        v21 = CTxtRange::CleanseAndReplaceRange(*((CTxtRange **)this + 8), v4, v5, 0, 0, v5, 0, 0);
      }
      else
      {
        v18 = 0;
        v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, _QWORD, _DWORD, int *, _DWORD))(*(_QWORD *)*v17 + 560LL))(
                *v17,
                (unsigned int)v4,
                v5,
                0,
                0,
                &v48,
                0);
        for ( i = v4; i > 0; v18 |= GetCharFlags(v23, 0) )
        {
          v23 = *v5++;
          --i;
        }
        v24 = *((_QWORD *)this + 7);
        v25 = *(_DWORD *)(v24 + 192);
        v26 = v18 & (v18 ^ v25);
        if ( v26 )
        {
          v30 = v25 | v26;
          *(_DWORD *)(v24 + 192) = v25 | v26;
          v31 = v26 & 0x61086013;
          if ( v31 && (v30 & 0x61086013) == v31 )
          {
            if ( *(_WORD *)(v24 + 196) == 0xFFFF )
            {
              v32 = *(_BYTE *)(v24 + 198);
              v33 = v32 | 1;
              if ( v32 != (v32 | 1) )
              {
                v34 = *(_QWORD *)(v24 + 64);
                *(_BYTE *)(v24 + 198) = v33;
                *(_DWORD *)(v34 + 56) |= 0x80u;
                (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(v24 + 48) + 72LL))(
                  *(_QWORD *)(v24 + 48),
                  0,
                  0);
              }
            }
            CTxtEdit::ItemizeDoc((CTxtEdit *)v24, v19, v20);
            v35 = *(_QWORD *)(v24 + 80);
            if ( v35 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 64LL))(v35);
            v36 = *(_QWORD *)(v24 + 88);
            if ( v36 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 64LL))(v36);
            *(_DWORD *)(v24 + 180) ^= (*(_DWORD *)(v24 + 180) ^ (*(_DWORD *)(v24 + 192) << 22)) & 0x400000;
          }
          v37 = HIBYTE(v31) & 1;
          v38 = (v31 & 0x61000000) == 0;
          v39 = v37 + 2;
          if ( v38 )
            v39 = v37;
          if ( v39 )
          {
            Uniscribe = GetUniscribe();
            v41 = *(CTxtBreaker **)(v24 + 168);
            if ( v41 )
              goto LABEL_90;
            if ( Uniscribe )
            {
              v42 = (CTxtBreaker *)CW32System::PvAlloc(0x28u, 0x40u);
              v41 = v42;
              if ( v42 )
              {
                v43 = (CTxtBreaker **)(v24 + 128);
                *((_QWORD *)v42 + 3) = 0;
                *((_QWORD *)v42 + 4) = 0;
                *(_QWORD *)v42 = &CTxtBreaker::`vftable';
                if ( v24 != -128 )
                {
                  *((_QWORD *)v42 + 1) = *v43;
                  *v43 = v42;
                }
                *((_QWORD *)v42 + 2) = v24;
              }
              else
              {
                v41 = 0;
              }
              *(_QWORD *)(v24 + 168) = v41;
              if ( v41 )
              {
LABEL_90:
                if ( (unsigned int)CTxtBreaker::AddBreaker(v41, v39) )
                  CTxtBreaker::Refresh(*(CTxtBreaker **)(v24 + 168));
              }
            }
          }
        }
      }
      v27 = *(_QWORD *)v11;
      if ( v13 != *(__int16 *)(*(_QWORD *)v11 + 96LL) )
      {
        v29 = qword_1800A41F0;
        (**(void (__fastcall ***)(struct IFormatCache *, _QWORD))qword_1800A41F0)(qword_1800A41F0, v13);
        (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(*(_QWORD *)v29 + 8LL))(
          v29,
          (unsigned int)*(__int16 *)(v27 + 96));
        *(_WORD *)(v27 + 96) = v13;
      }
      if ( v13 != -1 )
        (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(*(_QWORD *)qword_1800A41F0 + 8LL))(qword_1800A41F0, v13);
      if ( v21 == v4 || (*((_DWORD *)this + 12) = 6, v21 > 0) )
      {
        *((_DWORD *)this + 171) -= v21;
        return *((unsigned int *)this + 12);
      }
    }
    return 6;
  }
}

```

## disassembly

```asm
0x1800049f0  mov     rax, rsp
0x1800049f3  push    rbx
0x1800049f4  push    rbp
0x1800049f5  push    r12
0x1800049f7  push    r14
0x1800049f9  sub     rsp, 58h
0x1800049fd  xor     r12d, r12d
0x180004a00  mov     r14d, r8d
0x180004a03  mov     [rax+8], r12d
0x180004a07  mov     rbp, rdx
0x180004a0a  mov     rbx, rcx
0x180004a0d  test    r8d, r8d
0x180004a10  jle     loc_180004BEB
0x180004a16  mov     [rax+10h], rsi
0x180004a1a  mov     eax, [rcx+2ACh]
0x180004a20  mov     rsi, [rcx+0D8h]
0x180004a27  cmp     r8d, eax
0x180004a2a  ja      loc_180004E7F
0x180004a30  cmp     word ptr [rsi+0Ah], 0Dh
0x180004a35  movsxd  rcx, dword ptr [rcx+250h]
0x180004a3c  mov     [rsp+78h+var_28], rdi
0x180004a41  jz      loc_180004C2E
0x180004a47  test    ecx, ecx
0x180004a49  jnz     loc_180004EBD
0x180004a4f  mov     eax, [rbx+2B0h]
0x180004a55  test    eax, eax
0x180004a57  jnz     loc_180004F37
0x180004a5d  mov     ecx, [rbx+0ECh]
0x180004a63  mov     [rsp+78h+var_30], r13
0x180004a68  mov     [rsp+78h+var_38], r15
0x180004a6d  test    ecx, ecx
0x180004a6f  jnz     short loc_180004A7E
0x180004a71  cmp     [rbx+0F0h], r12d
0x180004a78  jz      loc_180004F49
0x180004a7e  mov     eax, [rbx+0F0h]
0x180004a84  lea     r13, [rbx+40h]
0x180004a88  mov     dword ptr [rsp+78h+var_50], eax; unsigned int
0x180004a8c  lea     rdx, [rbx+54h]; struct CCharFormat *
0x180004a90  mov     dword ptr [rsp+78h+var_58], ecx; unsigned int
0x180004a94  xor     r9d, r9d; struct IUndoBuilder *
0x180004a97  mov     rcx, [r13+0]; this
0x180004a9b  xor     r8d, r8d; unsigned int
0x180004a9e  call    ?SetCharFormat@CTxtRange@@QEAAJPEBVCCharFormat@@KPEAVIUndoBuilder@@KK@Z; CTxtRange::SetCharFormat(CCharFormat const *,ulong,IUndoBuilder *,ulong,ulong)
0x180004aa3  mov     [rbx+0ECh], r12
0x180004aaa  mov     rcx, cs:qword_1800A41F0
0x180004ab1  mov     rdi, [r13+0]
0x180004ab5  mov     rax, [rcx]
0x180004ab8  movsx   edx, word ptr [rdi+60h]
0x180004abc  mov     rax, [rax]
0x180004abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ac4  movsx   r15d, word ptr [rdi+60h]
0x180004ac9  test    rsi, rsi
0x180004acc  jz      loc_180004DCC
0x180004ad2  mov     eax, [rsi+14h]
0x180004ad5  test    eax, eax
0x180004ad7  js      loc_180004DCC
0x180004add  mov     ecx, [rbx+8]
0x180004ae0  test    ecx, ecx
0x180004ae2  jle     loc_180004DD7
0x180004ae8  cmp     eax, ecx
0x180004aea  jge     loc_180004DD7
0x180004af0  mov     rcx, [rbx]
0x180004af3  test    rcx, rcx
0x180004af6  jz      loc_180004DD7
0x180004afc  imul    eax, [rbx+10h]
0x180004b00  movsxd  rdx, eax
0x180004b03  add     rdx, rcx
0x180004b06  lea     rdi, [rbx+40h]
0x180004b0a  cmp     [rbx+2CAh], r12w
0x180004b12  jnz     loc_180004D7D
0x180004b18  mov     rcx, [rdi]
0x180004b1b  lea     rdx, [rsp+78h+arg_0]
0x180004b23  mov     dword ptr [rsp+78h+var_48], r12d
0x180004b28  xor     r9d, r9d
0x180004b2b  mov     [rsp+78h+var_50], rdx
0x180004b30  mov     r8, rbp
0x180004b33  mov     edx, r14d
0x180004b36  mov     dword ptr [rsp+78h+var_58], r12d
0x180004b3b  mov     rax, [rcx]
0x180004b3e  mov     rax, [rax+230h]
0x180004b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b4a  xor     esi, esi
0x180004b4c  mov     r12d, eax
0x180004b4f  mov     edi, r14d
0x180004b52  test    r14d, r14d
0x180004b55  jle     short loc_180004B77
0x180004b57  nop     word ptr [rax+rax+00000000h]
0x180004b60  movzx   ecx, word ptr [rbp+0]; unsigned int
0x180004b64  lea     rbp, [rbp+2]
0x180004b68  xor     edx, edx; unsigned __int8
0x180004b6a  dec     edi
0x180004b6c  call    ?GetCharFlags@@YAKKE@Z; GetCharFlags(ulong,uchar)
0x180004b71  or      esi, eax
0x180004b73  test    edi, edi
0x180004b75  jg      short loc_180004B60
0x180004b77  mov     rbp, [rbx+38h]
0x180004b7b  mov     eax, [rbp+0C0h]
0x180004b81  mov     edi, eax
0x180004b83  xor     edi, esi
0x180004b85  and     edi, esi
0x180004b87  jnz     loc_180004C49
0x180004b8d  mov     rsi, [r13+0]
0x180004b91  mov     r13, [rsp+78h+var_30]
0x180004b96  movsx   eax, word ptr [rsi+60h]
0x180004b9a  cmp     r15d, eax
0x180004b9d  jnz     short loc_180004BF9
0x180004b9f  cmp     r15d, 0FFFFFFFFh
0x180004ba3  jz      short loc_180004BBB
0x180004ba5  mov     rcx, cs:qword_1800A41F0
0x180004bac  mov     edx, r15d
0x180004baf  mov     rax, [rcx]
0x180004bb2  mov     rax, [rax+8]
0x180004bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bbb  mov     r15, [rsp+78h+var_38]
0x180004bc0  cmp     r12d, r14d
0x180004bc3  jnz     loc_180004FC0
0x180004bc9  sub     [rbx+2ACh], r12d
0x180004bd0  mov     eax, [rbx+30h]
0x180004bd3  mov     rdi, [rsp+78h+var_28]
0x180004bd8  mov     rsi, [rsp+78h+arg_8]
0x180004be0  add     rsp, 58h
0x180004be4  pop     r14
0x180004be6  pop     r12
0x180004be8  pop     rbp
0x180004be9  pop     rbx
0x180004bea  retn
0x180004beb  mov     eax, [rcx+30h]
0x180004bee  add     rsp, 58h
0x180004bf2  pop     r14
0x180004bf4  pop     r12
0x180004bf6  pop     rbp
0x180004bf7  pop     rbx
0x180004bf8  retn
0x180004bf9  mov     rdi, cs:qword_1800A41F0
0x180004c00  mov     edx, r15d
0x180004c03  mov     rcx, rdi
0x180004c06  mov     rax, [rdi]
0x180004c09  mov     rax, [rax]
0x180004c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c11  mov     rax, [rdi]
0x180004c14  mov     rcx, rdi
0x180004c17  movsx   edx, word ptr [rsi+60h]
0x180004c1b  mov     rax, [rax+8]
0x180004c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c24  mov     [rsi+60h], r15w
0x180004c29  jmp     loc_180004B9F
0x180004c2e  mov     eax, 0Fh
0x180004c33  sub     eax, ecx
0x180004c35  cmp     r14d, eax
0x180004c38  cmovge  r14d, eax
0x180004c3c  test    r14d, r14d
0x180004c3f  jg      loc_180004E8E
0x180004c45  xor     eax, eax
0x180004c47  jmp     short loc_180004BD3
0x180004c49  mov     ecx, edi
0x180004c4b  or      ecx, eax
0x180004c4d  mov     [rbp+0C0h], ecx
0x180004c53  and     edi, 61086013h
0x180004c59  jz      loc_180004CEF
0x180004c5f  and     ecx, 61086013h
0x180004c65  cmp     ecx, edi
0x180004c67  jnz     loc_180004CEF
0x180004c6d  cmp     word ptr [rbp+0C4h], 0FFFFh
0x180004c75  jnz     short loc_180004CAE
0x180004c77  movzx   eax, byte ptr [rbp+0C6h]
0x180004c7e  movzx   ecx, al
0x180004c81  or      cl, 1
0x180004c84  cmp     al, cl
0x180004c86  jz      short loc_180004CAE
0x180004c88  mov     rax, [rbp+40h]
0x180004c8c  xor     r8d, r8d
0x180004c8f  mov     [rbp+0C6h], cl
0x180004c95  xor     edx, edx
0x180004c97  or      dword ptr [rax+38h], 80h
0x180004c9e  mov     rcx, [rbp+30h]
0x180004ca2  mov     rax, [rcx]
0x180004ca5  mov     rax, [rax+48h]
0x180004ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cae  mov     rcx, rbp; this
0x180004cb1  call    ?ItemizeDoc@CTxtEdit@@QEAAXPEAVIUndoBuilder@@J@Z; CTxtEdit::ItemizeDoc(IUndoBuilder *,long)
0x180004cb6  mov     rcx, [rbp+50h]
0x180004cba  test    rcx, rcx
0x180004cbd  jnz     loc_180004F6C
0x180004cc3  mov     rcx, [rbp+58h]
0x180004cc7  test    rcx, rcx
0x180004cca  jnz     loc_180004F7D
0x180004cd0  mov     eax, [rbp+0B4h]
0x180004cd6  mov     ecx, [rbp+0C0h]
0x180004cdc  shl     ecx, 16h
0x180004cdf  xor     ecx, eax
0x180004ce1  and     ecx, 400000h
0x180004ce7  xor     ecx, eax
0x180004ce9  mov     [rbp+0B4h], ecx
0x180004cef  mov     eax, edi
0x180004cf1  shr     eax, 18h
0x180004cf4  and     eax, 1
0x180004cf7  test    edi, 61000000h
0x180004cfd  lea     edi, [rax+2]
0x180004d00  cmovz   edi, eax
0x180004d03  test    edi, edi
0x180004d05  jz      loc_180004B8D
0x180004d0b  call    ?GetUniscribe@@YAPEAVCUniscribe@@XZ; GetUniscribe(void)
0x180004d10  mov     rcx, [rbp+0A8h]
0x180004d17  test    rcx, rcx
0x180004d1a  jnz     loc_180004FA0
0x180004d20  test    rax, rax
0x180004d23  jz      loc_180004B8D
0x180004d29  mov     edx, 40h ; '@'; unsigned int
0x180004d2e  mov     ecx, 28h ; '('; unsigned int
0x180004d33  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x180004d38  mov     rcx, rax
0x180004d3b  test    rax, rax
0x180004d3e  jz      loc_180004F8E
0x180004d44  lea     rdx, [rbp+80h]
0x180004d4b  mov     qword ptr [rcx+18h], 0
0x180004d53  mov     qword ptr [rcx+20h], 0
0x180004d5b  lea     rax, ??_7CTxtBreaker@@6B@; const CTxtBreaker::`vftable'
0x180004d62  mov     [rcx], rax
0x180004d65  test    rdx, rdx
0x180004d68  jz      short loc_180004D74
0x180004d6a  mov     rax, [rdx]
0x180004d6d  mov     [rcx+8], rax
0x180004d71  mov     [rdx], rcx
0x180004d74  mov     [rcx+10h], rbp
0x180004d78  jmp     loc_180004F90
0x180004d7d  test    rdx, rdx
0x180004d80  jz      loc_180004B18
0x180004d86  cmp     word ptr [rdx+48h], 0FFFFh
0x180004d8b  jnz     loc_180004B18
0x180004d91  test    byte ptr [rbx+1D8h], 80h
0x180004d98  jnz     loc_180004F52
0x180004d9e  mov     rcx, [rbx+40h]; this
0x180004da2  xor     r9d, r9d; int
0x180004da5  mov     [rsp+78h+var_40], r12d; unsigned int
0x180004daa  mov     r8, rbp; unsigned __int16 *
0x180004dad  mov     [rsp+78h+var_48], r12; int *
0x180004db2  mov     edx, r14d; int
0x180004db5  mov     [rsp+78h+var_50], rbp; unsigned __int16 *
0x180004dba  mov     [rsp+78h+var_58], r12; struct IUndoBuilder *
0x180004dbf  call    ?CleanseAndReplaceRange@CTxtRange@@QEAAJJPEBGHPEAVIUndoBuilder@@PEAGPEAJK@Z; CTxtRange::CleanseAndReplaceRange(long,ushort const *,int,IUndoBuilder *,ushort *,long *,ulong)
0x180004dc4  mov     r12d, eax
0x180004dc7  jmp     loc_180004B8D
0x180004dcc  mov     rdx, r12
0x180004dcf  mov     rdi, r13
0x180004dd2  jmp     loc_180004B0A
0x180004dd7  mov     rdx, r12
0x180004dda  jmp     loc_180004B06
0x180004ddf  movzx   eax, word ptr [rbx+0F4h]
0x180004de6  sub     eax, 2
0x180004de9  cmp     eax, 5
0x180004dec  ja      loc_180004A4F
0x180004df2  cmp     word ptr [rbx+rcx*2+22Ah], 9
0x180004dfb  jnz     loc_180004A4F
0x180004e01  cmp     ecx, 1
0x180004e04  jle     loc_180004F29
0x180004e0a  movzx   edx, word ptr [rbx+rcx*2+228h]
0x180004e12  movzx   ecx, word ptr [rbx+2C8h]
0x180004e19  cmp     dx, 2Eh ; '.'
0x180004e1d  jnz     loc_180004EF1
0x180004e23  mov     eax, 200h
0x180004e28  jmp     loc_180004F12
0x180004e2d  add     rcx, 8; this
0x180004e31  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x180004e36  mov     ecx, 4000h
0x180004e3b  test    [rax+2], cx
0x180004e3f  jz      loc_180004A5D
0x180004e45  cmp     [rbx+138h], r12d
0x180004e4c  jz      loc_180004A5D
0x180004e52  mov     rcx, [rbx+40h]
0x180004e56  add     rcx, 18h; this
0x180004e5a  call    ?IsAfterEOP@CTxtPtr@@QEAAHXZ; CTxtPtr::IsAfterEOP(void)
0x180004e5f  test    eax, eax
0x180004e61  jnz     loc_180004A5D
0x180004e67  mov     [rbx+13Ch], r12d
0x180004e6e  mov     dword ptr [rbx+30h], 6
0x180004e75  mov     eax, 6
0x180004e7a  jmp     loc_180004BD3
0x180004e7f  mov     r14d, eax
0x180004e82  mov     dword ptr [rcx+30h], 12h
0x180004e89  jmp     loc_180004A30
0x180004e8e  movsxd  rax, r14d
0x180004e91  lea     rsi, [rbx+rcx*2]
0x180004e95  lea     rcx, [rsi+22Ch]; void *
0x180004e9c  lea     rdi, [rax+rax]
0x180004ea0  mov     r8, rdi; Size
0x180004ea3  call    memmove_0
0x180004ea8  mov     [rdi+rsi+22Ch], r12w
0x180004eb1  add     [rbx+250h], r14d
0x180004eb8  jmp     loc_180004C45
0x180004ebd  test    r9d, r9d
0x180004ec0  jz      loc_180004A4F
0x180004ec6  mov     [rbx+250h], r12d
0x180004ecd  test    byte ptr [rsi+4], 2
0x180004ed1  jnz     loc_180004DDF
0x180004ed7  mov     r8d, ecx; int
0x180004eda  lea     rdx, [rbx+22Ch]; unsigned __int16 *
0x180004ee1  mov     rcx, rbx; this
0x180004ee4  xor     r9d, r9d; int
0x180004ee7  call    ?AddText@CRTFRead@@AEAAHPEAGJH@Z; CRTFRead::AddText(ushort *,long,int)
0x180004eec  jmp     loc_180004A4F
  ... truncated ...
```
