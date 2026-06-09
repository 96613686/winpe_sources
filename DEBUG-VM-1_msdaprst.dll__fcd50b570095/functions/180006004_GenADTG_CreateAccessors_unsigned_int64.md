# GenADTG::CreateAccessors(unsigned __int64 *)

- ea: `0x180006004`
- end: `0x1800063f3`
- name: `?CreateAccessors@GenADTG@@QEAAXPEA_K@Z`
- size: `1007`
- prototype: `void(GenADTG *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x180007010`

## callees

- `0x180001d94`
- `0x18000266c`
- `0x1800027c0`
- `0x180003abc`
- `0x1800041ac`
- `0x1800041f8`
- `0x180006004`
- `0x180009bac`
- `0x180009c44`
- `0x18001a6c8`
- `0x18002cd54`
- `0x18002e02a`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GenADTG::CreateAccessors(GenADTG *this, unsigned __int64 *a2)
{
  CMetaData *v4; // r15
  unsigned __int128 v5; // rax
  unsigned __int8 *v6; // rax
  unsigned __int128 v7; // rax
  unsigned __int8 *v8; // rax
  int v9; // eax
  int v10; // edi
  unsigned __int16 v11; // bp
  unsigned int v12; // esi
  unsigned __int16 v13; // r14
  unsigned __int16 i; // di
  unsigned __int16 v15; // dx
  unsigned __int16 v16; // dx
  __int16 v17; // r9
  __int16 v18; // r10
  unsigned int v19; // r11d
  unsigned int Size; // r12d
  unsigned __int64 v21; // rcx
  __int64 v22; // r9
  struct tagDBBINDING *v23; // r8
  unsigned int v24; // eax
  unsigned __int128 v25; // rax
  unsigned __int8 *v26; // rax
  void **v27; // r14
  unsigned int v28; // edx
  unsigned __int16 v29; // di
  unsigned int v30; // edx
  unsigned __int16 j; // di
  unsigned __int16 v32; // r8
  unsigned __int16 v33; // r9
  int v34; // esi
  unsigned int v35; // eax
  unsigned __int8 *v36; // rax
  unsigned int v37; // eax
  unsigned int v38; // edx
  unsigned __int8 *v39; // rax
  __int64 v40; // rax
  __int64 v41; // [rsp+90h] [rbp+8h] BYREF

  v41 = 0;
  v4 = (GenADTG *)((char *)this + 128);
  v5 = *((unsigned __int16 *)this + 64) * (unsigned __int128)0x58uLL;
  if ( !is_mul_ok(*((unsigned __int16 *)this + 64), 0x58u) )
    LODWORD(v5) = -1;
  v6 = MMMAlloc(v5, DWORD2(v5));
  *((_QWORD *)this + 7) = v6;
  OnNullThrowOOM(v6);
  v7 = *(unsigned __int16 *)v4 * (unsigned __int128)2u;
  if ( !is_mul_ok(*(unsigned __int16 *)v4, 2u) )
    LODWORD(v7) = -1;
  v8 = MMMAlloc(v7, DWORD2(v7));
  *((_QWORD *)this + 32) = v8;
  OnNullThrowOOM(v8);
  *((_WORD *)this + 32) = 0;
  *((_WORD *)this + 102) = 0;
  v9 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
         *((_QWORD *)this + 3),
         &IID_IAccessor,
         &v41);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_180048578[0] )
        bidTraceW(off_1800481C0[0], 1718272, off_180048578[0], (unsigned int)v9, 1678);
    }
    ThrowHR(v10);
  }
  v11 = 0;
  v12 = 1;
  v13 = 0;
  for ( i = 0; i < *(_WORD *)v4; i += v19 )
  {
    CMetaData::mdGetFlags(v4, i);
    CMetaData::mdGetType(v4, v15);
    Size = CMetaData::mdGetSize(v4, v16);
    if ( (v18 & 0x2000) != 0 || v17 == 136 )
      v21 = v19;
    else
      v21 = 0;
    if ( !*((_DWORD *)this + 50) || !(_DWORD)v21 )
    {
      if ( (v18 & 0x60) != 0 || (_DWORD)v21 )
      {
        v21 = *((unsigned __int16 *)this + 102);
        *(_WORD *)(*((_QWORD *)this + 32) + 2 * v21) = v13;
        *((_WORD *)this + 102) += v19;
      }
      v22 = *((_QWORD *)this + 20);
      v23 = (struct tagDBBINDING *)(*((_QWORD *)this + 7) + 88LL * v13);
      if ( v22 )
        GenADTG::SetupDBBinding((GenADTG *)v21, (struct tagCOLRSDATA *)(v22 + 9648LL * i), v23, a2);
      else
        GenADTG::SetupDBBinding((GenADTG *)v21, (struct tagDBCOLUMNINFO *)(*((_QWORD *)this + 17) + 168LL * i), v23, a2);
      if ( Size > 0xFF && !v11 )
        v11 = v13;
      LOWORD(v19) = 1;
      ++v13;
      v24 = v12 + 1;
      if ( !v11 )
        v24 = v12;
      v12 = v24;
    }
  }
  *((_WORD *)this + 32) = v13;
  v25 = v12 * (unsigned __int128)8uLL;
  if ( !is_mul_ok(v12, 8u) )
    LODWORD(v25) = -1;
  v26 = MMMAlloc(v25, DWORD2(v25));
  v27 = (void **)((char *)this + 72);
  *((_QWORD *)this + 9) = v26;
  OnNullThrowOOM(v26);
  v29 = 0;
  if ( v12 >= 2 && (*v27 > v27 || (char *)*v27 + 8 * (unsigned __int16)(v12 - 1) < (char *)v27) )
  {
    v30 = v12 & 0xFFFFFFFE;
    do
      v29 += 2;
    while ( v29 < v30 );
    memset_0(*v27, 0, 16 * ((unsigned __int64)(unsigned __int16)(v30 + 1) >> 1));
  }
  while ( v29 < v12 )
    *((_QWORD *)*v27 + v29++) = 0;
  *((_DWORD *)this + 20) = v12;
  for ( j = 0; (unsigned int)j < *((_DWORD *)this + 20); ++j )
  {
    if ( j )
    {
      v32 = 1;
      v33 = j + v11 - 1;
    }
    else
    {
      if ( v11 )
        v32 = v11;
      else
        v32 = *((_WORD *)this + 32);
      v33 = 0;
    }
    v34 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v41 + 32LL))(
            v41,
            2,
            v32,
            *((_QWORD *)this + 7) + 88LL * v33,
            0,
            (__int64)*v27 + 8 * j,
            0);
    if ( v34 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048570[0] )
        bidTraceW(off_1800481C0[0], 1788928, off_180048570[0], (unsigned int)v34, 1747);
      ThrowHR(v34);
    }
  }
  v35 = ((unsigned int)*((unsigned __int16 *)this + 102) + 7) >> 3;
  *((_WORD *)this + 108) = v35;
  v36 = MMMAlloc((unsigned __int16)v35, v28);
  *((_QWORD *)this + 26) = v36;
  OnNullThrowOOM(v36);
  v37 = ((unsigned int)*((unsigned __int16 *)this + 32) + 7) >> 3;
  *((_WORD *)this + 116) = v37;
  v39 = MMMAlloc(2 * (unsigned int)(unsigned __int16)v37, v38);
  *((_QWORD *)this + 28) = v39;
  OnNullThrowOOM(v39);
  v40 = *((unsigned __int16 *)this + 116);
  *((_WORD *)this + 124) = v40;
  *((_QWORD *)this + 30) = *((_QWORD *)this + 28) + v40;
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v41);
}

```

## disassembly

```asm
0x180006004  mov     rax, rsp
0x180006007  push    rbx
0x180006008  push    rbp
0x180006009  push    rsi
0x18000600a  push    rdi
0x18000600b  push    r12
0x18000600d  push    r13
0x18000600f  push    r14
0x180006011  push    r15
0x180006013  sub     rsp, 48h
0x180006017  mov     r13, rdx
0x18000601a  mov     rbx, rcx
0x18000601d  xor     r12d, r12d
0x180006020  mov     [rax+8], r12
0x180006024  lea     r15, [rcx+80h]
0x18000602b  movzx   r8d, word ptr [r15]
0x18000602f  lea     eax, [r12+58h]
0x180006034  mul     r8
0x180006037  lea     rdi, [r12-1]
0x18000603c  cmovb   rax, rdi
0x180006040  mov     ecx, eax; unsigned int
0x180006042  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180006047  mov     [rbx+38h], rax
0x18000604b  mov     rcx, rax; void *
0x18000604e  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180006053  movzx   ecx, word ptr [r15]
0x180006057  lea     esi, [rdi+3]
0x18000605a  mov     eax, esi
0x18000605c  mul     rcx
0x18000605f  cmovb   rax, rdi
0x180006063  mov     ecx, eax; unsigned int
0x180006065  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000606a  mov     [rbx+100h], rax
0x180006071  mov     rcx, rax; void *
0x180006074  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180006079  mov     [rbx+40h], r12w
0x18000607e  mov     [rbx+0CCh], r12w
0x180006086  mov     rcx, [rbx+18h]
0x18000608a  mov     rax, [rcx]
0x18000608d  lea     r8, [rsp+88h+arg_0]
0x180006095  lea     rdx, IID_IAccessor
0x18000609c  mov     rax, [rax]
0x18000609f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060a4  mov     edi, eax
0x1800060a6  test    eax, eax
0x1800060a8  jns     short loc_1800060EA
0x1800060aa  test    byte ptr cs:_bidGblFlags, sil
0x1800060b1  jz      short loc_1800060E2
0x1800060b3  mov     rcx, cs:off_180048578; "<GenADTG::CreateAccessors|ADO|ERR>  HRE"...
0x1800060ba  test    rcx, rcx
0x1800060bd  jz      short loc_1800060E2
0x1800060bf  mov     dword ptr [rsp+88h+var_68], 68Eh
0x1800060c7  mov     r9d, eax
0x1800060ca  mov     r8, cs:off_180048578; "<GenADTG::CreateAccessors|ADO|ERR>  HRE"...
0x1800060d1  mov     edx, 1A3800h
0x1800060d6  mov     rcx, cs:off_1800481C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800060dd  call    _bidTraceW
0x1800060e2  mov     ecx, edi; int
0x1800060e4  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800060ea  mov     ebp, r12d
0x1800060ed  mov     r11d, 1
0x1800060f3  mov     esi, r11d
0x1800060f6  mov     r14d, r12d
0x1800060f9  mov     edi, r12d
0x1800060fc  cmp     r12w, [r15]
0x180006100  jnb     loc_180006200
0x180006106  movzx   edx, di; unsigned __int16
0x180006109  mov     rcx, r15; this
0x18000610c  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x180006111  mov     r10d, eax
0x180006114  mov     rcx, r15; this
0x180006117  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x18000611c  movzx   r9d, ax
0x180006120  mov     rcx, r15; this
0x180006123  call    ?mdGetSize@CMetaData@@QEAAKG@Z; CMetaData::mdGetSize(ushort)
0x180006128  mov     r12d, eax
0x18000612b  bt      r10d, 0Dh
0x180006130  jb      short loc_180006141
0x180006132  mov     eax, 88h
0x180006137  cmp     r9w, ax
0x18000613b  jz      short loc_180006141
0x18000613d  xor     ecx, ecx
0x18000613f  jmp     short loc_180006144
0x180006141  mov     ecx, r11d
0x180006144  cmp     dword ptr [rbx+0C8h], 0
0x18000614b  jz      short loc_180006155
0x18000614d  test    ecx, ecx
0x18000614f  jnz     loc_1800061EF
0x180006155  test    r10b, 60h
0x180006159  jnz     short loc_18000615F
0x18000615b  test    ecx, ecx
0x18000615d  jz      short loc_18000617A
0x18000615f  movzx   ecx, word ptr [rbx+0CCh]; this
0x180006166  mov     rax, [rbx+100h]
0x18000616d  mov     [rax+rcx*2], r14w
0x180006172  add     [rbx+0CCh], r11w
0x18000617a  mov     r9, [rbx+0A0h]
0x180006181  movzx   edx, di
0x180006184  movzx   eax, r14w
0x180006188  imul    r8, rax, 58h ; 'X'
0x18000618c  add     r8, [rbx+38h]; struct tagDBBINDING *
0x180006190  test    r9, r9
0x180006193  jz      short loc_1800061A9
0x180006195  imul    rdx, 25B0h
0x18000619c  add     rdx, r9; struct tagCOLRSDATA *
0x18000619f  mov     r9, r13; unsigned __int64 *
0x1800061a2  call    ?SetupDBBinding@GenADTG@@AEAAXPEAUtagCOLRSDATA@@PEAUtagDBBINDING@@PEA_K@Z; GenADTG::SetupDBBinding(tagCOLRSDATA *,tagDBBINDING *,unsigned __int64 *)
0x1800061a7  jmp     short loc_1800061BF
0x1800061a9  imul    rdx, 0A8h
0x1800061b0  add     rdx, [rbx+88h]; struct tagDBCOLUMNINFO *
0x1800061b7  mov     r9, r13; unsigned __int64 *
0x1800061ba  call    ?SetupDBBinding@GenADTG@@AEAAXPEAUtagDBCOLUMNINFO@@PEAUtagDBBINDING@@PEA_K@Z; GenADTG::SetupDBBinding(tagDBCOLUMNINFO *,tagDBBINDING *,unsigned __int64 *)
0x1800061bf  cmp     r12d, 0FFh
0x1800061c6  jbe     short loc_1800061D5
0x1800061c8  xor     r12d, r12d
0x1800061cb  test    bp, bp
0x1800061ce  cmovz   bp, r14w
0x1800061d3  jmp     short loc_1800061D8
0x1800061d5  xor     r12d, r12d
0x1800061d8  mov     r11d, 1
0x1800061de  add     r14w, r11w
0x1800061e2  lea     eax, [rsi+1]
0x1800061e5  test    bp, bp
0x1800061e8  cmovz   eax, esi
0x1800061eb  mov     esi, eax
0x1800061ed  jmp     short loc_1800061F2
0x1800061ef  xor     r12d, r12d
0x1800061f2  add     di, r11w
0x1800061f6  cmp     di, [r15]
0x1800061fa  jb      loc_180006106
0x180006200  mov     [rbx+40h], r14w
0x180006205  mov     ecx, esi
0x180006207  mov     eax, 8
0x18000620c  mul     rcx
0x18000620f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006216  cmovb   rax, rcx
0x18000621a  mov     ecx, eax; unsigned int
0x18000621c  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180006221  lea     r14, [rbx+48h]
0x180006225  mov     [r14], rax
0x180006228  mov     rcx, rax; void *
0x18000622b  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180006230  mov     edi, r12d
0x180006233  mov     r13d, 2
0x180006239  lea     r15d, [r13-1]
0x18000623d  cmp     esi, r13d
0x180006240  jb      short loc_18000629A
0x180006242  mov     r9, [r14]
0x180006245  cmp     r9, r14
0x180006248  ja      short loc_18000625D
0x18000624a  movzx   eax, si
0x18000624d  sub     ax, r15w
0x180006251  movzx   eax, ax
0x180006254  lea     rcx, [r9+rax*8]
0x180006258  cmp     rcx, r14
0x18000625b  jnb     short loc_18000629A
0x18000625d  mov     edx, esi
0x18000625f  and     edx, 0FFFFFFFEh
0x180006262  add     di, r13w
0x180006266  movzx   eax, di
0x180006269  cmp     eax, edx
0x18000626b  jb      short loc_180006262
0x18000626d  add     dx, r15w
0x180006271  movzx   r8d, dx
0x180006275  shr     r8, 1
0x180006278  shl     r8, 4
0x18000627c  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x180006280  xor     edx, edx; Val
0x180006282  mov     rcx, r9; void *
0x180006285  call    memset_0
0x18000628a  jmp     short loc_18000629A
0x18000628c  movzx   ecx, di
0x18000628f  mov     rax, [r14]
0x180006292  mov     [rax+rcx*8], r12
0x180006296  add     di, r15w
0x18000629a  movzx   eax, di
0x18000629d  cmp     eax, esi
0x18000629f  jb      short loc_18000628C
0x1800062a1  mov     [rbx+50h], esi
0x1800062a4  mov     edi, r12d
0x1800062a7  movzx   eax, di
0x1800062aa  cmp     eax, [rbx+50h]
0x1800062ad  jnb     loc_180006364
0x1800062b3  test    di, di
0x1800062b6  jnz     short loc_1800062CD
0x1800062b8  test    bp, bp
0x1800062bb  jnz     short loc_1800062C4
0x1800062bd  movzx   r8d, word ptr [rbx+40h]
0x1800062c2  jmp     short loc_1800062C8
0x1800062c4  movzx   r8d, bp
0x1800062c8  mov     r9d, r12d
0x1800062cb  jmp     short loc_1800062D8
0x1800062cd  mov     r8d, r15d
0x1800062d0  lea     r9d, [rdi+rbp]
0x1800062d4  sub     r9w, r15w
0x1800062d8  mov     rcx, [rsp+88h+arg_0]
0x1800062e0  mov     r10, [rcx]
0x1800062e3  movzx   edx, di
0x1800062e6  mov     rax, [r14]
0x1800062e9  lea     r11, [rax+rdx*8]
0x1800062ed  movzx   eax, r9w
0x1800062f1  imul    r9, rax, 58h ; 'X'
0x1800062f5  add     r9, [rbx+38h]
0x1800062f9  movzx   r8d, r8w
0x1800062fd  mov     [rsp+88h+var_58], r12
0x180006302  mov     [rsp+88h+var_60], r11
0x180006307  mov     [rsp+88h+var_68], r12
0x18000630c  mov     edx, r13d
0x18000630f  mov     rax, [r10+20h]
0x180006313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006318  mov     esi, eax
0x18000631a  test    eax, eax
0x18000631c  js      short loc_180006324
0x18000631e  add     di, r15w
0x180006322  jmp     short loc_1800062A7
0x180006324  test    byte ptr cs:_bidGblFlags, r13b
0x18000632b  jz      short loc_18000635C
0x18000632d  mov     rax, cs:off_180048570; "<GenADTG::CreateAccessors|ADO|ERR>  HRE"...
0x180006334  test    rax, rax
0x180006337  jz      short loc_18000635C
0x180006339  mov     dword ptr [rsp+88h+var_68], 6D3h
0x180006341  mov     r9d, esi
0x180006344  mov     r8, cs:off_180048570; "<GenADTG::CreateAccessors|ADO|ERR>  HRE"...
0x18000634b  mov     edx, 1B4C00h
0x180006350  mov     rcx, cs:off_1800481C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180006357  call    _bidTraceW
0x18000635c  mov     ecx, esi; int
0x18000635e  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180006364  movzx   eax, word ptr [rbx+0CCh]
0x18000636b  add     eax, 7
0x18000636e  shr     eax, 3
0x180006371  movzx   ecx, ax; unsigned int
0x180006374  mov     [rbx+0D8h], cx
0x18000637b  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180006380  mov     [rbx+0D0h], rax
0x180006387  mov     rcx, rax; void *
0x18000638a  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18000638f  movzx   eax, word ptr [rbx+40h]
0x180006393  add     eax, 7
0x180006396  shr     eax, 3
0x180006399  movzx   ecx, ax
0x18000639c  mov     [rbx+0E8h], cx
0x1800063a3  add     ecx, ecx; unsigned int
0x1800063a5  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800063aa  mov     [rbx+0E0h], rax
0x1800063b1  mov     rcx, rax; void *
0x1800063b4  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800063b9  movzx   eax, word ptr [rbx+0E8h]
0x1800063c0  mov     [rbx+0F8h], ax
0x1800063c7  add     rax, [rbx+0E0h]
0x1800063ce  mov     [rbx+0F0h], rax
0x1800063d5  lea     rcx, [rsp+88h+arg_0]
0x1800063dd  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800063e2  add     rsp, 48h
0x1800063e6  pop     r15
0x1800063e8  pop     r14
0x1800063ea  pop     r13
0x1800063ec  pop     r12
0x1800063ee  pop     rdi
0x1800063ef  pop     rsi
0x1800063f0  pop     rbp
0x1800063f1  pop     rbx
0x1800063f2  retn
```
