# NetSetupPropertyBag::Get(_NETSETUPPROPKEY const &)

- ea: `0x180008280`
- end: `0x1800086a6`
- name: `?Get@NetSetupPropertyBag@@AEBA?AV?$shared_ptr@VProperty@NetSetup2@@@std@@AEBU_NETSETUPPROPKEY@@@Z`
- size: `1062`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180006070`
- `0x180008a10`
- `0x18000f670`
- `0x180041334`

## callees

- `0x180006070`
- `0x1800076c0`
- `0x180008280`
- `0x1800086b0`
- `0x180009440`
- `0x180020898`
- `0x1800646b8`
- `0x1800647e0`
- `0x1800810d0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000854e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000854e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008419`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008419`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800082d5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800082d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800083ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800083de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800083ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800083de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000841f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000841f`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 *__fastcall NetSetupPropertyBag::Get(RTL_SRWLOCK *a1, __int64 *a2, __int128 *a3)
{
  RTL_SRWLOCK *v6; // r13
  RTL_SRWLOCK *v7; // r14
  _QWORD *Ptr; // rdx
  _QWORD *v9; // rax
  bool v10; // zf
  _QWORD *v11; // rdi
  __int64 v12; // r8
  _DWORD *v13; // rax
  _DWORD *v14; // rbx
  int v16; // ecx
  __int64 v17; // rbx
  _BYTE *v18; // rdx
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  __int64 v21; // r8
  _BYTE *v22; // r8
  _DWORD *v23; // rcx
  volatile signed __int32 *v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rax
  _QWORD *v27; // rdx
  __int128 i; // [rsp+30h] [rbp-69h]
  _QWORD *v29; // [rsp+50h] [rbp-49h]
  __int128 v30; // [rsp+60h] [rbp-39h]
  __int64 v31; // [rsp+A0h] [rbp+7h] BYREF
  volatile signed __int32 *v32; // [rsp+A8h] [rbp+Fh]

  v6 = a1 + 6;
  AcquireSRWLockShared(a1 + 6);
  v7 = a1 + 8;
  Ptr = a1[9].Ptr;
  v9 = a1[8].Ptr;
  v30 = *a3;
  v10 = v9 == Ptr;
  if ( v9 == Ptr )
    goto LABEL_10;
  do
  {
    if ( *((_DWORD *)v9 + 4) == *((_DWORD *)a3 + 4) )
    {
      v12 = *v9 - v30;
      if ( *v9 == (_QWORD)v30 )
        v12 = v9[1] - *((_QWORD *)&v30 + 1);
      if ( !v12 )
        break;
    }
    v9 += 6;
  }
  while ( v9 != Ptr );
  v10 = v9 == Ptr;
  if ( v9 == Ptr )
LABEL_10:
    v11 = v29;
  else
    v11 = v9;
  if ( v10 )
  {
    ReleaseSRWLockShared(v6);
    NetSetupPropertyBag::GetUncached(a1, &v31, a3);
    v16 = *((_DWORD *)a3 + 4);
    if ( v16 != 8 )
      goto LABEL_50;
    v25 = *(_QWORD *)a3 - NETSETUPPKEY_Interface_NetLuidIndex;
    if ( *(_QWORD *)a3 == (_QWORD)NETSETUPPKEY_Interface_NetLuidIndex )
      v25 = *((_QWORD *)a3 + 1) - *((_QWORD *)&NETSETUPPKEY_Interface_NetLuidIndex + 1);
    if ( v25 )
    {
LABEL_50:
      if ( v16 != 6 )
        goto LABEL_18;
      v26 = *(_QWORD *)a3 - NETSETUPPKEY_INF_Characteristics;
      if ( *(_QWORD *)a3 == NETSETUPPKEY_INF_Characteristics )
        v26 = *((_QWORD *)a3 + 1) - 0x17957FBBAD0689ALL;
      if ( v26 )
      {
LABEL_18:
        v17 = v31;
        AcquireSRWLockExclusive(v6);
        LODWORD(v6[1].Ptr) = GetCurrentThreadId();
        v18 = v7[1].Ptr;
        v19 = v7->Ptr;
        for ( i = *a3; v19 != (_QWORD *)v18; v19 += 6 )
        {
          if ( *((_DWORD *)v19 + 4) == *((_DWORD *)a3 + 4) )
          {
            v21 = *v19 - i;
            if ( *v19 == (_QWORD)i )
              v21 = v19[1] - *((_QWORD *)&i + 1);
            if ( !v21 )
              break;
          }
        }
        if ( v19 == (_QWORD *)v18 )
          v20 = *(_QWORD **)a3;
        else
          v20 = v19;
        if ( v19 == (_QWORD *)v18 )
        {
          if ( v17 )
          {
            v22 = v7[2].Ptr;
            if ( v18 == v22 && !(0xAAAAAAAAAAAAAAABuLL * ((v22 - v18) >> 4)) )
            {
              if ( 0xAAAAAAAAAAAAAAABuLL * ((v18 - (char *)v7->Ptr) >> 4) == 0x555555555555555LL )
                std::_Xlength_error("vector<T> too long");
              std::vector<NetSetup2::Property>::_Reallocate(v7);
            }
            v23 = v7[1].Ptr;
            *(_OWORD *)v23 = *(_OWORD *)v17;
            v23[4] = *(_DWORD *)(v17 + 16);
            v23[5] = *(_DWORD *)(v17 + 20);
            std::vector<unsigned char>::vector<unsigned char>(v23 + 6, v17 + 24);
          }
          else
          {
            if ( v18 == v7[2].Ptr )
              std::vector<NetSetup2::Property>::_Reserve(v7);
            v27 = v7[1].Ptr;
            *(_OWORD *)v27 = *a3;
            v27[2] = *((unsigned int *)a3 + 4);
            v27[3] = 0;
            v27[4] = 0;
            v27[5] = 0;
          }
          v7[1].Ptr = (char *)v7[1].Ptr + 48;
        }
        else if ( v17 )
        {
          *(_OWORD *)v20 = *(_OWORD *)v17;
          *((_DWORD *)v20 + 4) = *(_DWORD *)(v17 + 16);
          *((_DWORD *)v20 + 5) = *(_DWORD *)(v17 + 20);
          std::vector<unsigned char>::operator=(v20 + 3, v17 + 24);
        }
        else
        {
          *((_DWORD *)v20 + 5) = 0;
          v20[4] = v20[3];
        }
        LODWORD(v6[1].Ptr) = 0;
        ReleaseSRWLockExclusive(v6);
      }
    }
    *a2 = 0;
    a2[1] = 0;
    if ( a2 == &v31 )
    {
      v24 = v32;
    }
    else
    {
      a2[1] = (__int64)v32;
      v24 = 0;
      v32 = 0;
      *a2 = v31;
      v31 = 0;
    }
    if ( v24 )
    {
      if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
        if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
      }
    }
  }
  else
  {
    v13 = operator new(0x40u);
    v14 = v13;
    if ( v13 )
    {
      v13[2] = 1;
      v13[3] = 1;
      *(_QWORD *)v13 = &std::_Ref_count_obj<NetSetup2::Property>::`vftable';
      *((_OWORD *)v13 + 1) = *(_OWORD *)v11;
      v13[8] = *((_DWORD *)v11 + 4);
      v13[9] = *((_DWORD *)v11 + 5);
      std::vector<unsigned char>::vector<unsigned char>(v13 + 10, v11 + 3);
    }
    else
    {
      v14 = 0;
    }
    a2[1] = (__int64)v14;
    *a2 = (__int64)(v14 + 4);
    ReleaseSRWLockShared(v6);
  }
  return a2;
}

```

## disassembly

```asm
0x180008280  push    rbp
0x180008282  push    rsi
0x180008283  push    rdi
0x180008284  push    r12
0x180008286  push    r13
0x180008288  push    r14
0x18000828a  push    r15
0x18000828c  lea     rbp, [rsp-27h]
0x180008291  sub     rsp, 0C0h
0x180008298  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFEh
0x1800082a0  mov     [rsp+0F0h+arg_18], rbx
0x1800082a8  mov     rax, cs:__security_cookie
0x1800082af  xor     rax, rsp
0x1800082b2  mov     [rbp+57h+var_40], rax
0x1800082b6  mov     r15, r8
0x1800082b9  mov     rsi, rdx
0x1800082bc  mov     rbx, rcx
0x1800082bf  mov     [rbp+57h+var_58], rdx
0x1800082c3  xor     r12d, r12d
0x1800082c6  mov     [rbp+57h+var_D0], r12d
0x1800082ca  lea     r13, [rcx+30h]
0x1800082ce  mov     [rbp+57h+var_68], r13
0x1800082d2  mov     rcx, r13; SRWLock
0x1800082d5  call    cs:__imp_AcquireSRWLockShared
0x1800082db  mov     [rbp+57h+var_70], 1
0x1800082e2  lea     r14, [rbx+40h]
0x1800082e6  mov     rdx, [r14+8]
0x1800082ea  mov     rax, [r14]
0x1800082ed  movups  xmm0, xmmword ptr [r15]
0x1800082f1  movaps  [rbp+57h+var_90], xmm0
0x1800082f5  mov     ecx, [r15+10h]
0x1800082f9  cmp     rax, rdx
0x1800082fc  jz      short loc_18000833C
0x1800082fe  mov     r9, qword ptr [rbp+57h+var_90+8]
0x180008302  mov     r10, qword ptr [rbp+57h+var_90]
0x180008306  cmp     [rax+10h], ecx
0x180008309  jz      short loc_180008326
0x18000830b  add     rax, 30h ; '0'
0x18000830f  cmp     rax, rdx
0x180008312  jnz     short loc_180008306
0x180008314  cmp     rax, rdx
0x180008317  jz      short loc_18000833C
0x180008319  mov     [rbp+57h+var_98], 1
0x18000831d  mov     rdi, rax
0x180008320  mov     [rbp+57h+var_A0], rax
0x180008324  jmp     short loc_180008344
0x180008326  mov     r8, [rax]
0x180008329  sub     r8, r10
0x18000832c  jnz     short loc_180008335
0x18000832e  mov     r8, [rax+8]
0x180008332  sub     r8, r9
0x180008335  test    r8, r8
0x180008338  jnz     short loc_18000830B
0x18000833a  jmp     short loc_180008314
0x18000833c  mov     [rbp+57h+var_98], 0
0x180008340  mov     rdi, [rbp+57h+var_A0]
0x180008344  jz      loc_1800083DB
0x18000834a  mov     ecx, 40h ; '@'; Size
0x18000834f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008354  mov     rbx, rax
0x180008357  mov     qword ptr [rbp+57h+var_C0], rax
0x18000835b  test    rax, rax
0x18000835e  jz      loc_180008616
0x180008364  mov     dword ptr [rax+8], 1
0x18000836b  mov     dword ptr [rax+0Ch], 1
0x180008372  lea     rax, ??_7?$_Ref_count_obj@VProperty@NetSetup2@@@std@@6B@; const std::_Ref_count_obj<NetSetup2::Property>::`vftable'
0x180008379  mov     [rbx], rax
0x18000837c  movups  xmm0, xmmword ptr [rdi]
0x18000837f  movups  xmmword ptr [rbx+10h], xmm0
0x180008383  mov     eax, [rdi+10h]
0x180008386  mov     [rbx+20h], eax
0x180008389  mov     eax, [rdi+14h]
0x18000838c  mov     [rbx+24h], eax
0x18000838f  lea     rdx, [rdi+18h]
0x180008393  lea     rcx, [rbx+28h]
0x180008397  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x18000839c  nop
0x18000839d  mov     [rsi+8], rbx
0x1800083a1  lea     rcx, [rbx+10h]
0x1800083a5  mov     [rsi], rcx
0x1800083a8  mov     rcx, r13; SRWLock
0x1800083ab  call    cs:__imp_ReleaseSRWLockShared
0x1800083b1  mov     rax, rsi
0x1800083b4  mov     rcx, [rbp+57h+var_40]
0x1800083b8  xor     rcx, rsp; StackCookie
0x1800083bb  call    __security_check_cookie
0x1800083c0  mov     rbx, [rsp+0F0h+arg_18]
0x1800083c8  add     rsp, 0C0h
0x1800083cf  pop     r15
0x1800083d1  pop     r14
0x1800083d3  pop     r13
0x1800083d5  pop     r12
0x1800083d7  pop     rdi
0x1800083d8  pop     rsi
0x1800083d9  pop     rbp
0x1800083da  retn
0x1800083db  mov     rcx, r13; SRWLock
0x1800083de  call    cs:__imp_ReleaseSRWLockShared
0x1800083e4  mov     [rbp+57h+var_70], r12d
0x1800083e8  mov     r8, r15
0x1800083eb  lea     rdx, [rbp+57h+var_50]
0x1800083ef  mov     rcx, rbx
0x1800083f2  call    ?GetUncached@NetSetupPropertyBag@@AEBA?AV?$shared_ptr@VProperty@NetSetup2@@@std@@AEBU_NETSETUPPROPKEY@@@Z; NetSetupPropertyBag::GetUncached(_NETSETUPPROPKEY const &)
0x1800083f7  nop
0x1800083f8  mov     ecx, [r15+10h]
0x1800083fc  cmp     ecx, 8
0x1800083ff  jz      loc_1800085CC
0x180008405  cmp     ecx, 6
0x180008408  jz      loc_1800085F1
0x18000840e  mov     rbx, [rbp+57h+var_50]
0x180008412  mov     qword ptr [rbp+57h+var_90+8], r13
0x180008416  mov     rcx, r13; SRWLock
0x180008419  call    cs:__imp_AcquireSRWLockExclusive
0x18000841f  call    cs:__imp_GetCurrentThreadId
0x180008425  mov     [r13+8], eax
0x180008429  mov     dword ptr [rbp+57h+var_90], 2
0x180008430  mov     rdx, [r14+8]
0x180008434  mov     r11, [r14]
0x180008437  mov     rax, r11
0x18000843a  movups  xmm0, xmmword ptr [r15]
0x18000843e  movaps  [rbp+57h+var_C0], xmm0
0x180008442  mov     ecx, [r15+10h]
0x180008446  cmp     r11, rdx
0x180008449  jz      short loc_180008461
0x18000844b  mov     r9, qword ptr [rbp+57h+var_C0+8]
0x18000844f  mov     r10, qword ptr [rbp+57h+var_C0]
0x180008453  cmp     [rax+10h], ecx
0x180008456  jz      short loc_180008473
0x180008458  add     rax, 30h ; '0'
0x18000845c  cmp     rax, rdx
0x18000845f  jnz     short loc_180008453
0x180008461  cmp     rax, rdx
0x180008464  jz      short loc_180008489
0x180008466  mov     byte ptr [rbp+57h+var_C0+8], 1
0x18000846a  mov     rcx, rax
0x18000846d  mov     qword ptr [rbp+57h+var_C0], rax
0x180008471  jmp     short loc_180008491
0x180008473  mov     r8, [rax]
0x180008476  sub     r8, r10
0x180008479  jnz     short loc_180008482
0x18000847b  mov     r8, [rax+8]
0x18000847f  sub     r8, r9
0x180008482  test    r8, r8
0x180008485  jz      short loc_180008461
0x180008487  jmp     short loc_180008458
0x180008489  mov     byte ptr [rbp+57h+var_C0+8], 0
0x18000848d  mov     rcx, qword ptr [rbp+57h+var_C0]
0x180008491  jnz     loc_180008655
0x180008497  test    rbx, rbx
0x18000849a  jz      loc_18000861E
0x1800084a0  mov     r8, [r14+10h]
0x1800084a4  cmp     rdx, r8
0x1800084a7  jnz     short loc_18000851F
0x1800084a9  mov     rax, r8
0x1800084ac  sub     rax, rdx
0x1800084af  sar     rax, 4
0x1800084b3  mov     rcx, 0AAAAAAAAAAAAAAABh
0x1800084bd  imul    rax, rcx
0x1800084c1  cmp     rax, 1
0x1800084c5  jnb     short loc_18000851F
0x1800084c7  sub     rdx, r11
0x1800084ca  sar     rdx, 4
0x1800084ce  imul    rdx, rcx
0x1800084d2  mov     r9, 555555555555555h
0x1800084dc  mov     rax, r9
0x1800084df  sub     rax, rdx
0x1800084e2  cmp     rax, 1
0x1800084e6  jb      loc_18000868F
0x1800084ec  inc     rdx
0x1800084ef  sub     r8, r11
0x1800084f2  sar     r8, 4
0x1800084f6  imul    r8, rcx
0x1800084fa  mov     rax, r8
0x1800084fd  shr     rax, 1
0x180008500  sub     r9, rax
0x180008503  add     rax, r8
0x180008506  mov     rcx, r12
0x180008509  cmp     r9, r8
0x18000850c  cmovnb  rcx, rax
0x180008510  cmp     rcx, rdx
0x180008513  cmovnb  rdx, rcx
0x180008517  mov     rcx, r14
0x18000851a  call    ?_Reallocate@?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@IEAAX_K@Z; std::vector<NetSetup2::Property>::_Reallocate(unsigned __int64)
0x18000851f  mov     rcx, [r14+8]
0x180008523  movups  xmm0, xmmword ptr [rbx]
0x180008526  movups  xmmword ptr [rcx], xmm0
0x180008529  mov     eax, [rbx+10h]
0x18000852c  mov     [rcx+10h], eax
0x18000852f  mov     eax, [rbx+14h]
0x180008532  mov     [rcx+14h], eax
0x180008535  lea     rdx, [rbx+18h]
0x180008539  add     rcx, 18h
0x18000853d  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180008542  add     qword ptr [r14+8], 30h ; '0'
0x180008547  mov     [r13+8], r12d
0x18000854b  mov     rcx, r13; SRWLock
0x18000854e  call    cs:__imp_ReleaseSRWLockExclusive
0x180008554  mov     [rsi], r12
0x180008557  mov     [rsi+8], r12
0x18000855b  lea     rax, [rbp+57h+var_50]
0x18000855f  cmp     rsi, rax
0x180008562  jz      loc_18000869C
0x180008568  mov     rax, [rbp+57h+var_48]
0x18000856c  mov     [rsi+8], rax
0x180008570  mov     rbx, r12
0x180008573  mov     [rbp+57h+var_48], rbx
0x180008577  mov     rax, [rbp+57h+var_50]
0x18000857b  mov     [rsi], rax
0x18000857e  mov     [rbp+57h+var_50], r12
0x180008582  mov     [rbp+57h+var_D0], 1
0x180008589  test    rbx, rbx
0x18000858c  jz      short loc_1800085C7
0x18000858e  mov     edi, 0FFFFFFFFh
0x180008593  mov     eax, edi
0x180008595  lock xadd [rbx+8], eax
0x18000859a  cmp     eax, 1
0x18000859d  jnz     short loc_1800085C7
0x18000859f  mov     rax, [rbx]
0x1800085a2  mov     rcx, rbx
0x1800085a5  mov     rax, [rax]
0x1800085a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085ad  lock xadd [rbx+0Ch], edi
0x1800085b2  cmp     edi, 1
0x1800085b5  jnz     short loc_1800085C7
0x1800085b7  mov     rax, [rbx]
0x1800085ba  mov     rcx, rbx
0x1800085bd  mov     rax, [rax+8]
0x1800085c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085c6  nop
0x1800085c7  jmp     loc_1800083B1
0x1800085cc  mov     rax, [r15]
0x1800085cf  sub     rax, qword ptr cs:NETSETUPPKEY_Interface_NetLuidIndex
0x1800085d6  jnz     short loc_1800085E3
0x1800085d8  mov     rax, [r15+8]
0x1800085dc  sub     rax, qword ptr cs:NETSETUPPKEY_Interface_NetLuidIndex+8
0x1800085e3  test    rax, rax
0x1800085e6  jz      loc_180008554
0x1800085ec  jmp     loc_180008405
0x1800085f1  mov     rax, [r15]
0x1800085f4  sub     rax, cs:NETSETUPPKEY_INF_Characteristics
0x1800085fb  jnz     short loc_180008608
0x1800085fd  mov     rax, [r15+8]
0x180008601  sub     rax, cs:qword_1800999D8
0x180008608  test    rax, rax
0x18000860b  jz      loc_180008554
0x180008611  jmp     loc_18000840E
0x180008616  mov     rbx, r12
0x180008619  jmp     loc_18000839D
0x18000861e  cmp     rdx, [r14+10h]
0x180008622  jz      short loc_18000864B
0x180008624  mov     rdx, [r14+8]
0x180008628  movups  xmm0, xmmword ptr [r15]
0x18000862c  movups  xmmword ptr [rdx], xmm0
0x18000862f  mov     eax, [r15+10h]
0x180008633  mov     [rdx+10h], eax
0x180008636  mov     [rdx+14h], r12d
0x18000863a  mov     [rdx+18h], r12
0x18000863e  mov     [rdx+20h], r12
0x180008642  mov     [rdx+28h], r12
0x180008646  jmp     loc_180008542
0x18000864b  mov     rcx, r14
0x18000864e  call    ?_Reserve@?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@IEAAX_K@Z; std::vector<NetSetup2::Property>::_Reserve(unsigned __int64)
0x180008653  jmp     short loc_180008624
0x180008655  test    rbx, rbx
0x180008658  jz      short loc_18000867E
0x18000865a  movups  xmm0, xmmword ptr [rbx]
0x18000865d  movups  xmmword ptr [rcx], xmm0
0x180008660  mov     eax, [rbx+10h]
0x180008663  mov     [rcx+10h], eax
0x180008666  mov     eax, [rbx+14h]
0x180008669  mov     [rcx+14h], eax
0x18000866c  lea     rdx, [rbx+18h]
0x180008670  add     rcx, 18h
0x180008674  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x180008679  jmp     loc_180008547
0x18000867e  mov     [rcx+14h], r12d
0x180008682  mov     rax, [rcx+18h]
0x180008686  mov     [rcx+20h], rax
0x18000868a  jmp     loc_180008547
0x18000868f  lea     rcx, aVectorTTooLong; "vector<T> too long"
0x180008696  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000869c  mov     rbx, [rbp+57h+var_48]
0x1800086a0  jmp     loc_180008582
```
