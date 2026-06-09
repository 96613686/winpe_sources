# CIme_Lev3::CompositionString(__int64,CTextMsgFilter &)

- ea: `0x1800641d0`
- end: `0x180064b58`
- name: `?CompositionString@CIme_Lev3@@UEAAJ_JAEAVCTextMsgFilter@@@Z`
- size: `2440`
- prototype: `int(CIme_Lev3 *__hidden this, __int64, struct CTextMsgFilter *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180064100`

## callees

- `0x180046558`
- `0x18004c348`
- `0x180063de8`
- `0x180063f30`
- `0x1800641d0`
- `0x180064e28`
- `0x180065a88`
- `0x180065e60`
- `0x180090c0c`
- `0x180090cac`
- `0x180091140`
- `0x180092010`

## pseudocode

```c
__int64 __fastcall CIme_Lev3::CompositionString(CIme_Lev3 *this, __int64 a2, struct CTextMsgFilter *a3)
{
  _QWORD *v3; // r15
  struct CTextMsgFilter *v4; // rsi
  int v7; // r8d
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // r13d
  int v12; // r14d
  int v13; // r9d
  unsigned int ImmContext; // r12d
  int CompositionStringInfo; // eax
  int v16; // ecx
  unsigned __int64 v17; // rcx
  int v18; // edx
  char v19; // r12
  __int64 v20; // rcx
  int v21; // ecx
  int v22; // ecx
  __int64 v24; // rcx
  _DWORD *v25; // r12
  __int64 v26; // rcx
  char *v27; // rbx
  __int64 v28; // rcx
  char *v29; // r12
  int v30; // eax
  int v31; // r12d
  __int64 v32; // rcx
  int v33; // r13d
  CIme_Lev3 *v34; // rcx
  int v35; // ecx
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  int v39; // [rsp+68h] [rbp-98h] BYREF
  int v40[2]; // [rsp+70h] [rbp-90h] BYREF
  struct ITextFont *v41; // [rsp+78h] [rbp-88h] BYREF
  int v42; // [rsp+80h] [rbp-80h] BYREF
  __int64 v43; // [rsp+88h] [rbp-78h] BYREF
  __int64 v44; // [rsp+90h] [rbp-70h] BYREF
  int v45; // [rsp+98h] [rbp-68h] BYREF
  int v46; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned __int16 *v47; // [rsp+A0h] [rbp-60h]
  struct CTextMsgFilter *v48; // [rsp+A8h] [rbp-58h]
  unsigned __int8 v49[256]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v50[256]; // [rsp+1B0h] [rbp+B0h] BYREF

  v48 = a3;
  v3 = (_QWORD *)((char *)a3 + 120);
  v4 = a3;
  v45 = 0;
  *((_WORD *)this + 6) = 0;
  if ( *((_WORD *)this + 40) )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 320LL))(*v3);
    *((_WORD *)this + 40) = 0;
  }
  if ( !a2 || (a2 & 0x800) != 0 )
  {
    v40[0] = 0;
    if ( a2 )
      (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v3 + 144LL))(*v3, v40);
    v7 = *((_DWORD *)this + 11);
    if ( v7 )
    {
      v8 = *v3;
      v9 = *((unsigned int *)this + 10);
      v38 = 0;
      (*(void (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v8 + 192LL))(
        v8,
        v9,
        (unsigned int)(v9 + v7),
        &v38);
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 64LL))(v38, 0);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      *((_DWORD *)this + 11) = 0;
    }
    v10 = *((_QWORD *)this + 4);
    v43 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 56LL))(v10, &v43);
    if ( v43 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 16) + 152LL))(*((_QWORD *)v4 + 16));
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)v4 + 15) + 176LL))(
      *((_QWORD *)v4 + 15),
      4284967302LL,
      0);
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v4 + 15) + 280LL))(*((_QWORD *)v4 + 15), 0xFFFFFFFFLL);
    CIme::CheckInsertResultString(a2, v4, 0);
    if ( a2 )
      (*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)v4 + 15) + 152LL))(*((_QWORD *)v4 + 15), v40);
    (*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)v4 + 16) + 112LL))(*((_QWORD *)v4 + 16), &v45);
    *((_DWORD *)this + 10) = v45;
    if ( *((_DWORD *)v4 + 6) == 949 )
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)v4 + 15) + 176LL))(
        *((_QWORD *)v4 + 15),
        4284967301LL,
        0);
  }
  if ( (a2 & 0x18) == 0 )
    return 0;
  v11 = *((_DWORD *)this + 11);
  LODWORD(v41) = 0;
  v39 = 0;
  v12 = 0;
  LODWORD(v43) = 0;
  v40[0] = 0;
  v38 = 0;
  v46 = 0;
  v42 = 0;
  *((_DWORD *)this + 11) = 0;
  ImmContext = LocalGetImmContext(v4);
  if ( ImmContext )
  {
    CompositionStringInfo = CIme::GetCompositionStringInfo(
                              ImmContext,
                              8u,
                              v50,
                              v13,
                              v49,
                              256,
                              v40,
                              &v39,
                              *((_DWORD *)v4 + 6),
                              (*((unsigned __int16 *)v4 + 16) >> 1) & 1,
                              (*((unsigned __int16 *)v4 + 16) >> 6) & 1);
    v16 = 255;
    if ( CompositionStringInfo < 255 )
      v16 = CompositionStringInfo;
    *((_DWORD *)this + 11) = v16;
    v17 = v16;
    if ( v17 >= 256 )
      _report_rangecheckfailure();
    v50[v17] = 0;
    LocalReleaseImmContext(v4, ImmContext);
    v12 = v40[0];
    LODWORD(v41) = v39;
    LODWORD(v43) = v40[0];
  }
  v18 = *((_DWORD *)this + 11);
  v19 = 0;
  v47 = 0;
  if ( v18 )
  {
    v20 = *((_QWORD *)v4 + 15);
    v39 = 0;
    if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v20 + 328LL))(
            v20,
            (unsigned int)(v18 - v11),
            &v39)
      && v39 > 0 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 15) + 344LL))(*((_QWORD *)v4 + 15));
      v21 = *((_DWORD *)this + 11);
      if ( v21 <= v39 )
        v22 = 0;
      else
        v22 = v21 - v39;
      *((_DWORD *)this + 11) = v22;
      if ( (unsigned __int64)(2LL * v22) >= 0x200 )
        _report_rangecheckfailure();
      v50[v22] = 0;
      if ( !v22 && *((_DWORD *)v4 + 6) == 949 )
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v4 + 15) + 240LL))(*((_QWORD *)v4 + 15), 0);
    }
    v47 = CW32System::SysAllocString(v50);
    if ( !v47 )
      return 2147942414LL;
    if ( (a2 & 0x800) != 0 )
    {
      *((_WORD *)this + 6) = 1;
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)v4 + 15) + 176LL))(
        *((_QWORD *)v4 + 15),
        4284967301LL,
        0);
      if ( (*((_BYTE *)v4 + 32) & 4) == 0 )
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v4 + 15) + 280LL))(*((_QWORD *)v4 + 15), 0);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 16LL))(*((_QWORD *)this + 4));
      v24 = *((_QWORD *)v4 + 16);
      *(_QWORD *)v40 = 0;
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 144LL))(v24, v40);
      (*(void (__fastcall **)(_QWORD, char *))(**(_QWORD **)v40 + 56LL))(*(_QWORD *)v40, (char *)this + 32);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v40 + 16LL))(*(_QWORD *)v40);
      CIme::CheckKeyboardFontMatching(*((_DWORD *)this + 10), v4, *((struct ITextFont **)this + 4));
    }
  }
  if ( v11 || *((_DWORD *)this + 11) )
  {
    if ( (*((_BYTE *)v4 + 32) & 4) == 0 )
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v4 + 15) + 280LL))(*((_QWORD *)v4 + 15), 0);
    if ( v11
      || *((_DWORD *)v4 + 6) != 949
      || (*((_BYTE *)v4 + 32) & 0x10) == 0
      || *((_WORD *)this + 8)
      || (*((_WORD *)v4 + 16) & 0x1000) != 0 )
    {
      v27 = (char *)this + 40;
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)*v3 + 192LL))(
        *v3,
        *((unsigned int *)this + 10),
        (unsigned int)(*((_DWORD *)this + 10) + v11),
        &v38);
      if ( v11 )
      {
        if ( v12 )
        {
          (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v3 + 144LL))(*v3, &v42);
          v19 = 1;
        }
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 64LL))(v38, 0);
      }
    }
    else
    {
      v26 = *v3;
      v40[0] = 0;
      v27 = (char *)this + 40;
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v26 + 192LL))(
        v26,
        *((unsigned int *)this + 10),
        (unsigned int)(*((_DWORD *)this + 10) + 1),
        &v38);
      if ( !(*(unsigned int (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 72LL))(v38, v40) )
      {
        if ( v40[0] == 13 || v40[0] == 10 )
        {
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 224LL))(v38, *(unsigned int *)v27);
        }
        else
        {
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v3 + 176LL))(*v3, 4284967302LL, 0);
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 64LL))(v38, 0);
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v3 + 176LL))(*v3, 4284967301LL, 0);
        }
      }
    }
    *((_WORD *)this + 8) = 0;
    if ( v12 && !v19 )
      (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v3 + 144LL))(*v3, &v42);
    v28 = *((_QWORD *)this + 4);
    v44 = 0;
    if ( !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 56LL))(v28, &v44) && v44 )
    {
      if ( (*((_BYTE *)v4 + 32) & 8) != 0 )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 16) + 152LL))(*((_QWORD *)v4 + 16));
        v29 = (char *)this + 40;
LABEL_68:
        (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v38 + 64LL))(v38, v47);
        if ( v44 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        else
          v27 = v29;
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 128LL))(v38, &v46);
        v25 = (_DWORD *)((char *)v4 + 24);
        v30 = v46 - *(_DWORD *)v27;
        *((_DWORD *)this + 11) = v30;
        if ( *((_DWORD *)v4 + 6) == 949 )
        {
          v43 = 0;
          if ( v12 )
            (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v3 + 152LL))(*v3, &v42);
          if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, char *))(*(_QWORD *)v38 + 432LL))(
                 v38,
                 10,
                 &v43,
                 (char *)&v43 + 4) )
          {
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 448LL))(v38, 0);
          }
          (*(void (__fastcall **)(_QWORD, bool))(*(_QWORD *)*v3 + 240LL))(*v3, *((_DWORD *)this + 11) != 0);
        }
        else if ( v30 && v30 <= (int)v41 && v30 > 0 )
        {
          v31 = 0;
          do
          {
            v32 = *((_QWORD *)this + 4);
            v41 = 0;
            if ( (*(unsigned int (__fastcall **)(__int64, struct ITextFont **))(*(_QWORD *)v32 + 56LL))(v32, &v41)
              || !v41 )
            {
              break;
            }
            ((void (__fastcall *)(struct ITextFont *, __int64))v41->lpVtbl->Reset)(v41, 4284967297LL);
            v33 = v31 + 1;
            v34 = (CIme_Lev3 *)v49[v31];
            if ( v31 + 1 < *((_DWORD *)this + 11) )
            {
              do
              {
                if ( (_BYTE)v34 != v49[v33] )
                  break;
                ++v33;
              }
              while ( v33 < *((_DWORD *)this + 11) );
              v4 = v48;
            }
            CIme_Lev3::SetCompositionStyle(v34, v4, v49[v31], v41);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v38 + 224LL))(
              v38,
              (unsigned int)(v31 + *(_DWORD *)v27),
              (unsigned int)(*(_DWORD *)v27 + v33));
            (*(void (__fastcall **)(__int64, struct ITextFont *))(*(_QWORD *)v38 + 152LL))(v38, v41);
            ((void (__fastcall *)(struct ITextFont *))v41->lpVtbl->Release)(v41);
            v31 = v33;
          }
          while ( v33 < *((_DWORD *)this + 11) );
          v12 = v43;
          v25 = (_DWORD *)((char *)v4 + 24);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        goto LABEL_90;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 152LL))(v38);
    }
    v29 = v27;
    goto LABEL_68;
  }
  v25 = (_DWORD *)((char *)v4 + 24);
  if ( *((_DWORD *)v4 + 6) != 949 )
    goto LABEL_91;
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v4 + 15) + 352LL))(*((_QWORD *)v4 + 15), 0xFFFFFFFFLL);
LABEL_90:
  if ( *v25 == 949 )
    goto LABEL_102;
LABEL_91:
  if ( v12 > 0 )
  {
    v35 = *((_DWORD *)this + 11);
    if ( v12 < v35 )
      v35 = v12;
    v12 = v35 + *((_DWORD *)this + 10);
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)v4 + 16) + 224LL))(
      *((_QWORD *)v4 + 16),
      (unsigned int)v12,
      (unsigned int)v12);
    goto LABEL_100;
  }
  if ( v12 )
  {
LABEL_101:
    (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v3 + 152LL))(*v3, &v42);
    goto LABEL_102;
  }
  v36 = *v3;
  v37 = *((unsigned int *)this + 10);
  v44 = 0;
  if ( !(*(unsigned int (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v36 + 192LL))(
          v36,
          v37,
          (unsigned int)(v37 + 1),
          &v38) )
  {
    if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, char *))(*(_QWORD *)v38 + 432LL))(
           v38,
           32,
           &v44,
           (char *)&v44 + 4) )
    {
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v38 + 448LL))(v38, 32);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
LABEL_100:
    if ( v12 )
      goto LABEL_101;
  }
LABEL_102:
  if ( v47 )
    CW32System::SysFreeString(v47);
  if ( *v25 == 950 || *v25 == 936 )
    (*(void (__fastcall **)(CIme_Lev3 *, __int64, __int64, struct CTextMsgFilter *, int))(*(_QWORD *)this + 32LL))(
      this,
      5,
      1,
      v4,
      1);
  return 0;
}

```

## disassembly

```asm
0x1800641d0  mov     [rsp-8+arg_8], rbx
0x1800641d5  push    rbp
0x1800641d6  push    rsi
0x1800641d7  push    rdi
0x1800641d8  push    r12
0x1800641da  push    r13
0x1800641dc  push    r14
0x1800641de  push    r15
0x1800641e0  lea     rbp, [rsp-2C0h]
0x1800641e8  sub     rsp, 3C0h
0x1800641ef  mov     rax, cs:__security_cookie
0x1800641f6  xor     rax, rsp
0x1800641f9  mov     [rbp+2F0h+var_40], rax
0x180064200  xor     r12d, r12d
0x180064203  mov     [rbp+2F0h+var_348], r8
0x180064207  lea     r15, [r8+78h]
0x18006420b  mov     rsi, r8
0x18006420e  mov     rbx, rdx
0x180064211  mov     rdi, rcx
0x180064214  mov     [rbp+2F0h+var_358], r12d
0x180064218  mov     [rcx+0Ch], r12w
0x18006421d  cmp     [rcx+50h], r12w
0x180064222  jz      short loc_18006423B
0x180064224  mov     rcx, [r15]
0x180064227  mov     rax, [rcx]
0x18006422a  mov     rax, [rax+140h]
0x180064231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064236  mov     [rdi+50h], r12w
0x18006423b  test    rbx, rbx
0x18006423e  jz      short loc_18006424B
0x180064240  bt      rbx, 0Bh
0x180064245  jnb     loc_1800643A3
0x18006424b  mov     [rsp+3F0h+var_380], r12d
0x180064250  test    rbx, rbx
0x180064253  jz      short loc_18006426C
0x180064255  mov     rcx, [r15]
0x180064258  lea     rdx, [rsp+3F0h+var_380]
0x18006425d  mov     rax, [rcx]
0x180064260  mov     rax, [rax+90h]
0x180064267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006426c  mov     r8d, [rdi+2Ch]
0x180064270  test    r8d, r8d
0x180064273  jz      short loc_1800642BF
0x180064275  mov     rcx, [r15]
0x180064278  lea     r9, [rsp+3F0h+var_390]
0x18006427d  mov     edx, [rdi+28h]
0x180064280  add     r8d, edx
0x180064283  mov     [rsp+3F0h+var_390], r12
0x180064288  mov     rax, [rcx]
0x18006428b  mov     rax, [rax+0C0h]
0x180064292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064297  mov     rcx, [rsp+3F0h+var_390]
0x18006429c  xor     edx, edx
0x18006429e  mov     rax, [rcx]
0x1800642a1  mov     rax, [rax+40h]
0x1800642a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800642aa  mov     rcx, [rsp+3F0h+var_390]
0x1800642af  mov     rax, [rcx]
0x1800642b2  mov     rax, [rax+10h]
0x1800642b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800642bb  mov     [rdi+2Ch], r12d
0x1800642bf  mov     rcx, [rdi+20h]
0x1800642c3  lea     rdx, [rbp+2F0h+var_368]
0x1800642c7  mov     [rbp+2F0h+var_368], r12
0x1800642cb  mov     rax, [rcx]
0x1800642ce  mov     rax, [rax+38h]
0x1800642d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800642d7  mov     rdx, [rbp+2F0h+var_368]
0x1800642db  test    rdx, rdx
0x1800642de  jz      short loc_180064306
0x1800642e0  mov     rcx, [rsi+80h]
0x1800642e7  mov     rax, [rcx]
0x1800642ea  mov     rax, [rax+98h]
0x1800642f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800642f6  mov     rcx, [rbp+2F0h+var_368]
0x1800642fa  mov     rax, [rcx]
0x1800642fd  mov     rax, [rax+10h]
0x180064301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064306  mov     rcx, [rsi+78h]
0x18006430a  xor     r8d, r8d
0x18006430d  mov     edx, 0FF676986h
0x180064312  mov     rax, [rcx]
0x180064315  mov     rax, [rax+0B0h]
0x18006431c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064321  mov     rcx, [rsi+78h]
0x180064325  or      edx, 0FFFFFFFFh
0x180064328  mov     rax, [rcx]
0x18006432b  mov     rax, [rax+118h]
0x180064332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064337  xor     r8d, r8d; __int16 *
0x18006433a  mov     rdx, rsi; struct CTextMsgFilter *
0x18006433d  mov     rcx, rbx; __int64
0x180064340  call    ?CheckInsertResultString@CIme@@KAJ_JAEAVCTextMsgFilter@@PEAF@Z; CIme::CheckInsertResultString(__int64,CTextMsgFilter &,short *)
0x180064345  test    rbx, rbx
0x180064348  jz      short loc_180064362
0x18006434a  mov     rcx, [rsi+78h]
0x18006434e  lea     rdx, [rsp+3F0h+var_380]
0x180064353  mov     rax, [rcx]
0x180064356  mov     rax, [rax+98h]
0x18006435d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064362  mov     rcx, [rsi+80h]
0x180064369  lea     rdx, [rbp+2F0h+var_358]
0x18006436d  mov     rax, [rcx]
0x180064370  mov     rax, [rax+70h]
0x180064374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064379  mov     eax, [rbp+2F0h+var_358]
0x18006437c  mov     [rdi+28h], eax
0x18006437f  cmp     dword ptr [rsi+18h], 3B5h
0x180064386  jnz     short loc_1800643A3
0x180064388  mov     rcx, [rsi+78h]
0x18006438c  xor     r8d, r8d
0x18006438f  mov     edx, 0FF676985h
0x180064394  mov     rax, [rcx]
0x180064397  mov     rax, [rax+0B0h]
0x18006439e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800643a3  test    bl, 18h
0x1800643a6  jz      loc_180064B2C
0x1800643ac  mov     r13d, [rdi+2Ch]
0x1800643b0  mov     eax, r12d
0x1800643b3  mov     rcx, rsi; struct CTextMsgFilter *
0x1800643b6  mov     dword ptr [rsp+3F0h+var_378], eax
0x1800643ba  mov     [rsp+3F0h+var_388], eax
0x1800643be  mov     r14d, r12d
0x1800643c1  mov     dword ptr [rbp+2F0h+var_368], r12d
0x1800643c5  mov     [rsp+3F0h+var_380], r12d
0x1800643ca  mov     [rsp+3F0h+var_390], r12
0x1800643cf  mov     [rbp+2F0h+var_354], r12d
0x1800643d3  mov     [rbp+2F0h+var_370], r12d
0x1800643d7  mov     [rdi+2Ch], r12d
0x1800643db  call    ?LocalGetImmContext@@YAKAEAVCTextMsgFilter@@@Z; LocalGetImmContext(CTextMsgFilter &)
0x1800643e0  mov     r12d, eax
0x1800643e3  mov     eax, 1
0x1800643e8  test    r12d, r12d
0x1800643eb  jz      loc_18006448F
0x1800643f1  movzx   edx, word ptr [rsi+20h]
0x1800643f5  lea     r8, [rbp+2F0h+var_240]; unsigned __int16 *
0x1800643fc  mov     ecx, edx
0x1800643fe  shr     edx, 1
0x180064400  and     edx, eax
0x180064402  shr     ecx, 6
0x180064405  and     ecx, eax
0x180064407  mov     eax, [rsi+18h]
0x18006440a  mov     [rsp+3F0h+var_3A0], ecx; int
0x18006440e  mov     ecx, r12d; unsigned int
0x180064411  mov     [rsp+3F0h+var_3A8], edx; int
0x180064415  mov     edx, 8; unsigned int
0x18006441a  mov     [rsp+3F0h+var_3B0], eax; unsigned int
0x18006441e  lea     rax, [rsp+3F0h+var_388]
0x180064423  mov     [rsp+3F0h+var_3B8], rax; int *
0x180064428  lea     rax, [rsp+3F0h+var_380]
0x18006442d  mov     [rsp+3F0h+var_3C0], rax; int *
0x180064432  lea     rax, [rbp+2F0h+var_340]
0x180064436  mov     [rsp+3F0h+var_3C8], 100h; int
0x18006443e  mov     [rsp+3F0h+var_3D0], rax; unsigned __int8 *
0x180064443  call    ?GetCompositionStringInfo@CIme@@KAHKKPEAGHPEAEHPEAJ2IHH@Z; CIme::GetCompositionStringInfo(ulong,ulong,ushort *,int,uchar *,int,long *,long *,uint,int,int)
0x180064448  mov     ecx, 0FFh
0x18006444d  cmp     eax, ecx
0x18006444f  cmovl   ecx, eax
0x180064452  movsxd  rax, ecx
0x180064455  mov     [rdi+2Ch], ecx
0x180064458  lea     rcx, [rax+rax]
0x18006445c  cmp     rcx, 200h
0x180064463  jnb     loc_1800644EE
0x180064469  xor     eax, eax
0x18006446b  mov     edx, r12d; unsigned int
0x18006446e  mov     [rbp+rcx+2F0h+var_240], ax
0x180064476  mov     rcx, rsi; struct CTextMsgFilter *
0x180064479  call    ?LocalReleaseImmContext@@YAXAEAVCTextMsgFilter@@K@Z; LocalReleaseImmContext(CTextMsgFilter &,ulong)
0x18006447e  mov     eax, [rsp+3F0h+var_388]
0x180064482  mov     r14d, [rsp+3F0h+var_380]
0x180064487  mov     dword ptr [rsp+3F0h+var_378], eax
0x18006448b  mov     dword ptr [rbp+2F0h+var_368], r14d
0x18006448f  mov     edx, [rdi+2Ch]
0x180064492  xor     r12d, r12d
0x180064495  mov     [rbp+2F0h+var_350], r12
0x180064499  test    edx, edx
0x18006449b  jz      loc_180064607
0x1800644a1  mov     rcx, [rsi+78h]
0x1800644a5  lea     r8, [rsp+3F0h+var_388]
0x1800644aa  mov     [rsp+3F0h+var_388], r12d
0x1800644af  sub     edx, r13d
0x1800644b2  mov     rax, [rcx]
0x1800644b5  mov     rax, [rax+148h]
0x1800644bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800644c1  test    eax, eax
0x1800644c3  jnz     short loc_180064535
0x1800644c5  cmp     [rsp+3F0h+var_388], r12d
0x1800644ca  jle     short loc_180064535
0x1800644cc  mov     rcx, [rsi+78h]
0x1800644d0  mov     rax, [rcx]
0x1800644d3  mov     rax, [rax+158h]
0x1800644da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800644df  mov     ecx, [rdi+2Ch]
0x1800644e2  cmp     ecx, [rsp+3F0h+var_388]
0x1800644e6  jle     short loc_1800644F4
0x1800644e8  sub     ecx, [rsp+3F0h+var_388]
0x1800644ec  jmp     short loc_1800644F7
0x1800644ee  call    __report_rangecheckfailure
0x1800644f4  mov     ecx, r12d
0x1800644f7  movsxd  rax, ecx
0x1800644fa  mov     [rdi+2Ch], ecx
0x1800644fd  lea     rdx, [rax+rax]
0x180064501  cmp     rdx, 200h
0x180064508  jnb     short loc_180064554
0x18006450a  mov     [rbp+rdx+2F0h+var_240], r12w
0x180064513  test    ecx, ecx
0x180064515  jnz     short loc_180064535
0x180064517  cmp     dword ptr [rsi+18h], 3B5h
0x18006451e  jnz     short loc_180064535
0x180064520  mov     rcx, [rsi+78h]
0x180064524  xor     edx, edx
0x180064526  mov     rax, [rcx]
0x180064529  mov     rax, [rax+0F0h]
0x180064530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064535  lea     rcx, [rbp+2F0h+var_240]; unsigned __int16 *
0x18006453c  call    ?SysAllocString@CW32System@@SAPEAGPEBG@Z; CW32System::SysAllocString(ushort const *)
0x180064541  mov     [rbp+2F0h+var_350], rax
0x180064545  test    rax, rax
0x180064548  jnz     short loc_18006455A
0x18006454a  mov     eax, 8007000Eh
0x18006454f  jmp     loc_180064B2E
0x180064554  call    __report_rangecheckfailure
0x18006455a  bt      rbx, 0Bh
0x18006455f  jnb     loc_180064607
0x180064565  mov     word ptr [rdi+0Ch], 1
0x18006456b  xor     r8d, r8d
0x18006456e  mov     rcx, [rsi+78h]
0x180064572  mov     edx, 0FF676985h
0x180064577  mov     rax, [rcx]
0x18006457a  mov     rax, [rax+0B0h]
0x180064581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064586  test    byte ptr [rsi+20h], 4
0x18006458a  jnz     short loc_1800645A1
0x18006458c  mov     rcx, [rsi+78h]
0x180064590  xor     edx, edx
0x180064592  mov     rax, [rcx]
0x180064595  mov     rax, [rax+118h]
0x18006459c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800645a1  lea     rbx, [rdi+20h]
0x1800645a5  mov     rcx, [rbx]
0x1800645a8  mov     rax, [rcx]
0x1800645ab  mov     rax, [rax+10h]
0x1800645af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800645b4  mov     rcx, [rsi+80h]
0x1800645bb  lea     rdx, [rsp+3F0h+var_380]
0x1800645c0  mov     qword ptr [rsp+3F0h+var_380], r12
0x1800645c5  mov     rax, [rcx]
0x1800645c8  mov     rax, [rax+90h]
0x1800645cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800645d4  mov     rcx, qword ptr [rsp+3F0h+var_380]
0x1800645d9  mov     rdx, rbx
0x1800645dc  mov     rax, [rcx]
0x1800645df  mov     rax, [rax+38h]
0x1800645e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800645e8  mov     rcx, qword ptr [rsp+3F0h+var_380]
0x1800645ed  mov     rax, [rcx]
0x1800645f0  mov     rax, [rax+10h]
0x1800645f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800645f9  mov     r8, [rbx]; struct ITextFont *
0x1800645fc  mov     rdx, rsi; struct CTextMsgFilter *
0x1800645ff  mov     ecx, [rdi+28h]; int
0x180064602  call    ?CheckKeyboardFontMatching@CIme@@SAXJAEAVCTextMsgFilter@@PEAUITextFont@@@Z; CIme::CheckKeyboardFontMatching(long,CTextMsgFilter &,ITextFont *)
0x180064607  xor     ebx, ebx
0x180064609  test    r13d, r13d
0x18006460c  jnz     short loc_180064640
0x18006460e  cmp     [rdi+2Ch], ebx
0x180064611  jnz     short loc_180064640
0x180064613  lea     r12, [rsi+18h]
0x180064617  cmp     dword ptr [r12], 3B5h
0x18006461f  jnz     loc_180064A1E
0x180064625  mov     rcx, [rsi+78h]
0x180064629  or      edx, 0FFFFFFFFh
0x18006462c  mov     rax, [rcx]
0x18006462f  mov     rax, [rax+160h]
0x180064636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006463b  jmp     loc_180064A10
0x180064640  test    byte ptr [rsi+20h], 4
0x180064644  jnz     short loc_18006465B
0x180064646  mov     rcx, [rsi+78h]
0x18006464a  xor     edx, edx
0x18006464c  mov     rax, [rcx]
0x18006464f  mov     rax, [rax+118h]
0x180064656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006465b  test    r13d, r13d
0x18006465e  jnz     loc_18006474D
0x180064664  cmp     dword ptr [rsi+18h], 3B5h
0x18006466b  jnz     loc_18006474D
0x180064671  test    byte ptr [rsi+20h], 10h
0x180064675  jz      loc_18006474D
0x18006467b  cmp     [rdi+10h], bx
0x18006467f  jnz     loc_18006474D
0x180064685  mov     eax, 1000h
0x18006468a  test    [rsi+20h], ax
0x18006468e  jnz     loc_18006474D
0x180064694  mov     rcx, [r15]
0x180064697  lea     r9, [rsp+3F0h+var_390]
0x18006469c  mov     [rsp+3F0h+var_380], ebx
0x1800646a0  lea     rbx, [rdi+28h]
0x1800646a4  mov     edx, [rbx]
0x1800646a6  mov     rax, [rcx]
  ... truncated ...
```
