# CASFIndexMaker::CompleteIndexBlocks(unsigned __int64)

- ea: `0x18002f320`
- end: `0x18002f68c`
- name: `?CompleteIndexBlocks@CASFIndexMaker@@MEAAJ_K@Z`
- size: `876`
- prototype: `__int64 __fastcall(CASFIndexMaker *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800015d0`
- `0x1800043cc`
- `0x180005948`
- `0x18002f114`
- `0x18002f320`
- `0x18002f694`
- `0x18002f704`
- `0x18002fcb0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFIndexMaker::CompleteIndexBlocks(CASFIndexMaker *this, unsigned __int64 a2)
{
  unsigned __int64 v2; // rbp
  unsigned __int64 v4; // r10
  unsigned int i; // r11d
  __int64 Ptr; // rax
  int v7; // r11d
  unsigned int v8; // r12d
  unsigned int j; // r10d
  __int64 v10; // rbx
  unsigned int v11; // r10d
  unsigned __int64 v12; // rsi
  int v13; // r13d
  unsigned int v14; // r15d
  unsigned __int64 *v15; // rsi
  __int64 NextPtr; // rax
  unsigned int v17; // r11d
  __int64 v18; // r11
  unsigned __int64 v19; // r8
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rax
  unsigned int v22; // eax
  unsigned __int64 *v23; // rax
  _QWORD *v24; // r11
  unsigned __int64 v25; // rdx
  __int64 v26; // rax
  __int64 result; // rax
  unsigned int k; // esi
  __int64 v29; // rax
  __int64 (__fastcall *v30)(CASFIndexMaker *, __int64); // rbx
  __int64 v31; // rax
  int v32; // ebx
  __int64 v33; // rax
  unsigned int v34; // [rsp+30h] [rbp-88h]
  unsigned int v35; // [rsp+34h] [rbp-84h]
  _BYTE v36[24]; // [rsp+38h] [rbp-80h] BYREF
  __int64 v37; // [rsp+50h] [rbp-68h] BYREF
  unsigned int *v38; // [rsp+58h] [rbp-60h] BYREF

  v2 = a2;
  if ( a2 == -1 )
  {
    v4 = 0;
    for ( i = 0; i < *((_DWORD *)this + 3250); i = v7 + 1 )
    {
      Ptr = CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr((char *)this + 352, i);
      if ( Ptr && *(_QWORD *)(Ptr + 24) > v4 )
        v4 = *(_QWORD *)(Ptr + 24);
    }
    v2 = v4 + *((unsigned int *)this + 16) + *((unsigned int *)this + 17);
  }
  if ( v2 >= *((unsigned int *)this + 17) )
  {
    v8 = 0;
    for ( j = 0; ; j = v11 + 1 )
    {
      v35 = j;
      if ( j >= *((_DWORD *)this + 3250) )
        break;
      v10 = CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr((char *)this + 352, j);
      if ( v10 )
      {
        while ( 1 )
        {
          v12 = *(_QWORD *)(v10 + 32);
          if ( v12 > v2 - *((unsigned int *)this + 17) )
            break;
          v34 = *(_DWORD *)(v10 + 592);
          if ( v34 && *(_QWORD *)CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::operator[](v10 + 40, v36, 0) <= v12 )
          {
            v13 = 0;
            v14 = 0;
            v37 = 0;
            v15 = 0;
            *(_QWORD *)(v10 + 576) = v10 + 40;
            *(_DWORD *)(v10 + 584) = 0;
            while ( 1 )
            {
              if ( v15 )
              {
                v18 = (__int64)v15;
                v15 = 0;
                NextPtr = v18;
              }
              else
              {
                NextPtr = CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::GetNextPtr(v10 + 40);
                if ( !NextPtr )
                {
                  if ( ++v14 >= v17 )
                    v13 = 1;
                  goto LABEL_32;
                }
                v18 = NextPtr;
              }
              v19 = *((unsigned int *)this + 17);
              v20 = *(_QWORD *)(v10 + 32);
              if ( v20 <= v19 )
              {
                v38 = (unsigned int *)(NextPtr + 8);
              }
              else
              {
                v21 = *(_QWORD *)v18 + *(unsigned int *)(v18 + 8);
                v38 = (unsigned int *)(v18 + 8);
                if ( v21 < v20 - v19 )
                {
                  CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::RemoveAt(v10 + 40, v14);
                  v22 = *(_DWORD *)(v10 + 592);
                  v34 = v22;
                  v37 = -1;
                  if ( v14 >= v22 )
                    v13 = 1;
                  goto LABEL_32;
                }
              }
              v37 = *(_QWORD *)(v18 + 16);
              if ( v14 == v34 - 1 )
                goto LABEL_35;
              v23 = (unsigned __int64 *)CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::GetNextPtr(v10 + 40);
              v25 = *(_QWORD *)(v10 + 32);
              v15 = v23;
              if ( *v23 > v25 || *v24 + (unsigned __int64)*v38 >= v25 )
                goto LABEL_35;
              ++v14;
LABEL_32:
              if ( v13 )
                goto LABEL_35;
            }
          }
          v37 = -1;
LABEL_35:
          v26 = CTDynArray<IASFIndexBlock *,20>::operator[]((char *)this + 128, *(unsigned int *)(v10 + 12));
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)v26 + 136LL))(
            v26,
            *(_QWORD *)(v10 + 32),
            *(unsigned __int16 *)(v10 + 2),
            *(unsigned __int16 *)(v10 + 4),
            v37);
          ++*(_DWORD *)(v10 + 8);
          *(_QWORD *)(v10 + 32) += *((unsigned int *)this + 16);
          if ( *(_DWORD *)(v10 + 8) >= *((_DWORD *)this + 18) )
          {
            if ( !*(_DWORD *)(v10 + 12) )
            {
              result = (*(__int64 (__fastcall **)(CASFIndexMaker *))(*(_QWORD *)this + 80LL))(this);
              if ( (int)result < 0 )
                return result;
            }
            --*(_DWORD *)(v10 + 12);
            *(_DWORD *)(v10 + 8) = 0;
          }
        }
        v11 = v35;
        if ( *(_DWORD *)(v10 + 12) > v8 )
          v8 = *(_DWORD *)(v10 + 12);
      }
    }
    for ( k = *((_DWORD *)this + 86) - 1; k > v8; --k )
    {
      v37 = 0;
      v38 = 0;
      v29 = CTDynArray<IASFIndexBlock *,20>::operator[]((char *)this + 128, k);
      (*(void (__fastcall **)(__int64, __int64 *, unsigned int **))(*(_QWORD *)v29 + 104LL))(v29, &v37, &v38);
      if ( (unsigned __int64)v38 + *((unsigned int *)this + 17) < v2 )
      {
        v30 = *(__int64 (__fastcall **)(CASFIndexMaker *, __int64))(*(_QWORD *)this + 96LL);
        v31 = CTDynArray<IASFIndexBlock *,20>::operator[]((char *)this + 128, k);
        v32 = v30(this, v31);
        v33 = CTDynArray<IASFIndexBlock *,20>::operator[]((char *)this + 128, k);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
        CTDynArray<IASFIndexBlock *,20>::RemoveAt((char *)this + 128, k);
        if ( v32 < 0 )
          return (unsigned int)v32;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002f320  push    rbx
0x18002f322  push    rbp
0x18002f323  push    rsi
0x18002f324  push    rdi
0x18002f325  push    r12
0x18002f327  push    r13
0x18002f329  push    r14
0x18002f32b  push    r15
0x18002f32d  sub     rsp, 78h
0x18002f331  mov     rax, cs:__security_cookie
0x18002f338  xor     rax, rsp
0x18002f33b  mov     [rsp+0B8h+var_58], rax
0x18002f340  mov     rbp, rdx
0x18002f343  mov     rdi, rcx
0x18002f346  mov     r14d, 1
0x18002f34c  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18002f350  jnz     short loc_18002F396
0x18002f352  xor     r10d, r10d
0x18002f355  xor     r11d, r11d
0x18002f358  cmp     [rcx+32C8h], r10d
0x18002f35f  jbe     short loc_18002F38A
0x18002f361  mov     edx, r11d
0x18002f364  lea     rcx, [rdi+160h]
0x18002f36b  call    ?GetPtr@?$CTDynArray@USTREAM_INFO@CASFBaseIndexMaker@@$0BE@@@QEAAPEAUSTREAM_INFO@CASFBaseIndexMaker@@K@Z; CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr(ulong)
0x18002f370  test    rax, rax
0x18002f373  jz      short loc_18002F37E
0x18002f375  cmp     [rax+18h], r10
0x18002f379  cmova   r10, [rax+18h]
0x18002f37e  add     r11d, r14d
0x18002f381  cmp     r11d, [rdi+32C8h]
0x18002f388  jb      short loc_18002F361
0x18002f38a  mov     eax, [rdi+40h]
0x18002f38d  mov     ebp, [rdi+44h]
0x18002f390  add     rax, r10
0x18002f393  add     rbp, rax
0x18002f396  mov     eax, [rdi+44h]
0x18002f399  cmp     rbp, rax
0x18002f39c  jb      loc_18002F66C
0x18002f3a2  xor     r12d, r12d
0x18002f3a5  xor     r10d, r10d
0x18002f3a8  lea     rax, [rdi+160h]
0x18002f3af  mov     [rsp+0B8h+var_84], r10d
0x18002f3b4  cmp     r10d, [rax+3168h]
0x18002f3bb  jnb     loc_18002F5BB
0x18002f3c1  mov     edx, r10d
0x18002f3c4  mov     rcx, rax
0x18002f3c7  call    ?GetPtr@?$CTDynArray@USTREAM_INFO@CASFBaseIndexMaker@@$0BE@@@QEAAPEAUSTREAM_INFO@CASFBaseIndexMaker@@K@Z; CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr(ulong)
0x18002f3cc  mov     rbx, rax
0x18002f3cf  test    rax, rax
0x18002f3d2  jz      loc_18002F5B3
0x18002f3d8  mov     ecx, [rdi+44h]
0x18002f3db  mov     rdx, rbp
0x18002f3de  mov     rsi, [rbx+20h]
0x18002f3e2  sub     rdx, rcx
0x18002f3e5  cmp     rsi, rdx
0x18002f3e8  ja      loc_18002F5A5
0x18002f3ee  lea     r14, [rbx+28h]
0x18002f3f2  mov     eax, [r14+228h]
0x18002f3f9  mov     [rsp+0B8h+var_88], eax
0x18002f3fd  test    eax, eax
0x18002f3ff  jz      loc_18002F517
0x18002f405  xor     r8d, r8d
0x18002f408  lea     rdx, [rsp+0B8h+var_80]
0x18002f40d  mov     rcx, r14
0x18002f410  call    ??A?$CTDynArray@USEEK_POINT@CASFBaseIndexMaker@@$0BE@@@QEBA?AUSEEK_POINT@CASFBaseIndexMaker@@K@Z; CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::operator[](ulong)
0x18002f415  cmp     [rax], rsi
0x18002f418  ja      loc_18002F517
0x18002f41e  mov     r11d, [rsp+0B8h+var_88]
0x18002f423  xor     r13d, r13d
0x18002f426  xor     r15d, r15d
0x18002f429  mov     [rsp+0B8h+var_68], 0
0x18002f432  xor     esi, esi
0x18002f434  mov     [r14+218h], r14
0x18002f43b  mov     [r14+220h], esi
0x18002f442  test    rsi, rsi
0x18002f445  jnz     short loc_18002F46B
0x18002f447  mov     rcx, r14
0x18002f44a  call    ?GetNextPtr@?$CTDynArray@USEEK_POINT@CASFBaseIndexMaker@@$0BE@@@QEAAPEAUSEEK_POINT@CASFBaseIndexMaker@@XZ; CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::GetNextPtr(void)
0x18002f44f  test    rax, rax
0x18002f452  jnz     short loc_18002F466
0x18002f454  lea     eax, [rsi+1]
0x18002f457  add     r15d, eax
0x18002f45a  cmp     r15d, r11d
0x18002f45d  cmovnb  r13d, eax
0x18002f461  jmp     loc_18002F50C
0x18002f466  mov     r11, rax
0x18002f469  jmp     short loc_18002F473
0x18002f46b  mov     r11, rsi
0x18002f46e  xor     esi, esi
0x18002f470  mov     rax, r11
0x18002f473  mov     r8d, [rdi+44h]
0x18002f477  mov     rcx, [rbx+20h]
0x18002f47b  cmp     rcx, r8
0x18002f47e  jbe     short loc_18002F4C4
0x18002f480  lea     rdx, [r11+8]
0x18002f484  sub     rcx, r8
0x18002f487  mov     eax, [rdx]
0x18002f489  add     rax, [r11]
0x18002f48c  mov     [rsp+0B8h+var_60], rdx
0x18002f491  cmp     rax, rcx
0x18002f494  jnb     short loc_18002F4CD
0x18002f496  mov     edx, r15d
0x18002f499  mov     rcx, r14
0x18002f49c  call    ?RemoveAt@?$CTDynArray@USEEK_POINT@CASFBaseIndexMaker@@$0BE@@@QEAAHKK@Z; CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::RemoveAt(ulong,ulong)
0x18002f4a1  mov     eax, [rbx+250h]
0x18002f4a7  mov     r11d, eax
0x18002f4aa  mov     [rsp+0B8h+var_88], eax
0x18002f4ae  mov     [rsp+0B8h+var_68], 0FFFFFFFFFFFFFFFFh
0x18002f4b7  cmp     r15d, eax
0x18002f4ba  jb      short loc_18002F50C
0x18002f4bc  mov     r13d, 1
0x18002f4c2  jmp     short loc_18002F50C
0x18002f4c4  add     rax, 8
0x18002f4c8  mov     [rsp+0B8h+var_60], rax
0x18002f4cd  mov     rax, [r11+10h]
0x18002f4d1  mov     [rsp+0B8h+var_68], rax
0x18002f4d6  mov     eax, [rsp+0B8h+var_88]
0x18002f4da  dec     eax
0x18002f4dc  cmp     r15d, eax
0x18002f4df  jz      short loc_18002F520
0x18002f4e1  mov     rcx, r14
0x18002f4e4  call    ?GetNextPtr@?$CTDynArray@USEEK_POINT@CASFBaseIndexMaker@@$0BE@@@QEAAPEAUSEEK_POINT@CASFBaseIndexMaker@@XZ; CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::GetNextPtr(void)
0x18002f4e9  mov     rdx, [rbx+20h]
0x18002f4ed  mov     rsi, rax
0x18002f4f0  cmp     [rax], rdx
0x18002f4f3  ja      short loc_18002F520
0x18002f4f5  mov     rax, [rsp+0B8h+var_60]
0x18002f4fa  mov     ecx, [rax]
0x18002f4fc  add     rcx, [r11]
0x18002f4ff  cmp     rcx, rdx
0x18002f502  jnb     short loc_18002F520
0x18002f504  mov     r11d, [rsp+0B8h+var_88]
0x18002f509  inc     r15d
0x18002f50c  test    r13d, r13d
0x18002f50f  jz      loc_18002F442
0x18002f515  jmp     short loc_18002F520
0x18002f517  mov     [rsp+0B8h+var_68], 0FFFFFFFFFFFFFFFFh
0x18002f520  mov     edx, [rbx+0Ch]
0x18002f523  lea     rcx, [rdi+80h]
0x18002f52a  call    ??A?$CTDynArray@PEAUIASFIndexBlock@@$0BE@@@QEBAPEAUIASFIndexBlock@@K@Z; CTDynArray<IASFIndexBlock *,20>::operator[](ulong)
0x18002f52f  movzx   r9d, word ptr [rbx+4]
0x18002f534  mov     r10, rax
0x18002f537  movzx   r8d, word ptr [rbx+2]
0x18002f53c  mov     rdx, [rbx+20h]
0x18002f540  mov     rcx, [rax]
0x18002f543  mov     rax, [rcx+88h]
0x18002f54a  mov     rcx, [rsp+0B8h+var_68]
0x18002f54f  mov     [rsp+0B8h+var_98], rcx
0x18002f554  mov     rcx, r10
0x18002f557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f55c  mov     r14d, 1
0x18002f562  add     [rbx+8], r14d
0x18002f566  mov     eax, [rdi+40h]
0x18002f569  add     [rbx+20h], rax
0x18002f56d  mov     ecx, [rbx+8]
0x18002f570  cmp     ecx, [rdi+48h]
0x18002f573  jb      loc_18002F3D8
0x18002f579  cmp     dword ptr [rbx+0Ch], 0
0x18002f57d  jnz     short loc_18002F596
0x18002f57f  mov     rax, [rdi]
0x18002f582  mov     rcx, rdi
0x18002f585  mov     rax, [rax+50h]
0x18002f589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f58e  test    eax, eax
0x18002f590  js      loc_18002F66E
0x18002f596  dec     dword ptr [rbx+0Ch]
0x18002f599  mov     dword ptr [rbx+8], 0
0x18002f5a0  jmp     loc_18002F3D8
0x18002f5a5  cmp     [rbx+0Ch], r12d
0x18002f5a9  mov     r10d, [rsp+0B8h+var_84]
0x18002f5ae  cmova   r12d, [rbx+0Ch]
0x18002f5b3  add     r10d, r14d
0x18002f5b6  jmp     loc_18002F3A8
0x18002f5bb  mov     esi, [rdi+158h]
0x18002f5c1  sub     esi, r14d
0x18002f5c4  cmp     esi, r12d
0x18002f5c7  jbe     loc_18002F66C
0x18002f5cd  lea     r14, [rdi+80h]
0x18002f5d4  mov     [rsp+0B8h+var_68], 0
0x18002f5dd  mov     rcx, r14
0x18002f5e0  mov     [rsp+0B8h+var_60], 0
0x18002f5e9  mov     edx, esi
0x18002f5eb  call    ??A?$CTDynArray@PEAUIASFIndexBlock@@$0BE@@@QEBAPEAUIASFIndexBlock@@K@Z; CTDynArray<IASFIndexBlock *,20>::operator[](ulong)
0x18002f5f0  mov     r9, rax
0x18002f5f3  lea     r8, [rsp+0B8h+var_60]
0x18002f5f8  lea     rdx, [rsp+0B8h+var_68]
0x18002f5fd  mov     rcx, [rax]
0x18002f600  mov     rax, [rcx+68h]
0x18002f604  mov     rcx, r9
0x18002f607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f60c  mov     eax, [rdi+44h]
0x18002f60f  add     rax, [rsp+0B8h+var_60]
0x18002f614  cmp     rax, rbp
0x18002f617  jnb     short loc_18002F661
0x18002f619  mov     rax, [rdi]
0x18002f61c  mov     edx, esi
0x18002f61e  mov     rcx, r14
0x18002f621  mov     rbx, [rax+60h]
0x18002f625  call    ??A?$CTDynArray@PEAUIASFIndexBlock@@$0BE@@@QEBAPEAUIASFIndexBlock@@K@Z; CTDynArray<IASFIndexBlock *,20>::operator[](ulong)
0x18002f62a  mov     rdx, rax
0x18002f62d  mov     rcx, rdi
0x18002f630  mov     rax, rbx
0x18002f633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f638  mov     edx, esi
0x18002f63a  mov     rcx, r14
0x18002f63d  mov     ebx, eax
0x18002f63f  call    ??A?$CTDynArray@PEAUIASFIndexBlock@@$0BE@@@QEBAPEAUIASFIndexBlock@@K@Z; CTDynArray<IASFIndexBlock *,20>::operator[](ulong)
0x18002f644  mov     rcx, rax
0x18002f647  mov     rdx, [rax]
0x18002f64a  mov     rax, [rdx+10h]
0x18002f64e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f653  mov     edx, esi
0x18002f655  mov     rcx, r14
0x18002f658  call    ?RemoveAt@?$CTDynArray@PEAUIASFIndexBlock@@$0BE@@@QEAAHKK@Z; CTDynArray<IASFIndexBlock *,20>::RemoveAt(ulong,ulong)
0x18002f65d  test    ebx, ebx
0x18002f65f  js      short loc_18002F668
0x18002f661  dec     esi
0x18002f663  jmp     loc_18002F5C4
0x18002f668  mov     eax, ebx
0x18002f66a  jmp     short loc_18002F66E
0x18002f66c  xor     eax, eax
0x18002f66e  mov     rcx, [rsp+0B8h+var_58]
0x18002f673  xor     rcx, rsp; StackCookie
0x18002f676  call    __security_check_cookie
0x18002f67b  add     rsp, 78h
0x18002f67f  pop     r15
0x18002f681  pop     r14
0x18002f683  pop     r13
0x18002f685  pop     r12
0x18002f687  pop     rdi
0x18002f688  pop     rsi
0x18002f689  pop     rbp
0x18002f68a  pop     rbx
0x18002f68b  retn
```
