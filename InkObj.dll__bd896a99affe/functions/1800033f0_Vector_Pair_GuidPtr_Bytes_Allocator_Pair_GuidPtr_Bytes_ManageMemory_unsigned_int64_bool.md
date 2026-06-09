# Vector<Pair<GuidPtr,Bytes>,Allocator<Pair<GuidPtr,Bytes>>>::ManageMemory(unsigned __int64,bool)

- ea: `0x1800033f0`
- end: `0x18000388b`
- name: `?ManageMemory@?$Vector@V?$Pair@VGuidPtr@@VBytes@@@@V?$Allocator@V?$Pair@VGuidPtr@@VBytes@@@@@@@@IEAA_N_K_N@Z`
- size: `1179`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18009c0ac`

## callees

- `0x180002740`
- `0x1800033f0`
- `0x180003ba0`
- `0x18004451c`
- `0x1800445e8`
- `0x180044658`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003664`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000371e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003664`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000371e`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800036ba`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000374b`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800036ba`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000374b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035f9`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800037ad`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180003807`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180003861`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800037ad`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180003807`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180003861`

## pseudocode

```c
char __fastcall Vector<Pair<GuidPtr,Bytes>,Allocator<Pair<GuidPtr,Bytes>>>::ManageMemory(
        __int64 a1,
        unsigned __int64 a2,
        char a3)
{
  unsigned __int64 v4; // rbx
  SIZE_T v5; // rbp
  unsigned __int64 v6; // rbp
  unsigned __int64 v7; // r14
  _QWORD *v8; // r15
  unsigned __int64 i; // rbp
  __int64 v10; // rcx
  int v11; // r12d
  char result; // al
  unsigned int v13; // r12d
  unsigned __int64 v14; // r14
  unsigned __int64 v15; // rbp
  _QWORD *v16; // r13
  __int64 v17; // rcx
  _QWORD *v18; // rbx
  _QWORD *v19; // r14
  LPVOID v20; // rax
  _QWORD *v21; // rcx
  _QWORD *v22; // r14
  LPVOID v23; // rax
  int v24; // [rsp+60h] [rbp+8h]

  if ( a2 > *(_QWORD *)(a1 + 16) )
  {
    if ( a2 >= 0x20 )
    {
      v4 = a2 | 0xF;
    }
    else
    {
      if ( a2 < 2 )
      {
        v4 = 1;
        v5 = 32;
        goto LABEL_45;
      }
      if ( a2 < 4 )
      {
        v4 = 3;
        v5 = 96;
        goto LABEL_45;
      }
      if ( a2 < 8 )
      {
        v4 = 7;
        v5 = 224;
        goto LABEL_45;
      }
      if ( a2 < 0x10 )
      {
        v4 = 15;
        v5 = 480;
        goto LABEL_45;
      }
      v4 = 31;
    }
    if ( v4 > 0x7FFFFFFFFFFFFFFLL || (v5 = 32 * v4, 32 * v4 > 0xFFFFFFFF) )
    {
      v13 = tls_index;
      goto LABEL_30;
    }
LABEL_45:
    v13 = tls_index;
    v19 = *(_QWORD **)a1;
    if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                     + (unsigned int)tls_index)
                                                                   + 4LL) )
    {
      Init_thread_header(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
      if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA == -1 )
      {
        `WinHeap::GetDefault'::`2'::s_WinHeap = 0;
        dwFlags = 0;
        `WinHeap::GetDefault'::`2'::s_WinHeap = HeapCreate(0, 0x10000u, 0);
        atexit(`WinHeap::GetDefault'::`2'::`dynamic atexit destructor for 's_WinHeap'');
        Init_thread_footer(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
      }
    }
    if ( `WinHeap::GetDefault'::`2'::s_WinHeap )
    {
      v20 = v19
          ? HeapReAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v19, v5)
          : HeapAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v5);
      if ( v20 )
      {
        *(_QWORD *)a1 = v20;
        result = 1;
LABEL_51:
        *(_QWORD *)(a1 + 16) = v4;
        return result;
      }
    }
LABEL_30:
    v14 = *(_QWORD *)(a1 + 8);
    if ( v14 )
    {
      v15 = 0;
      v16 = *(_QWORD **)a1;
      do
      {
        Vector<unsigned char,BasicAllocator<unsigned char>>::~Vector<unsigned char,BasicAllocator<unsigned char>>(&v16[4 * v15 + 1]);
        v17 = v16[4 * v15];
        if ( v17 )
        {
          v24 = *(_DWORD *)(v17 + 8);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v17 + 8), 0xFFFFFFFF) == 1 )
            (**(void (__fastcall ***)(__int64, __int64))v17)(v17, 1);
          if ( v24 == 1 )
            v16[4 * v15] = 0;
        }
        ++v15;
      }
      while ( v15 < v14 );
    }
    v18 = *(_QWORD **)a1;
    if ( *(_QWORD *)a1 )
    {
      if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                       + v13)
                                                                     + 4LL) )
      {
        Init_thread_header(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
        if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA == -1 )
        {
          `WinHeap::GetDefault'::`2'::s_WinHeap = 0;
          dwFlags = 0;
          `WinHeap::GetDefault'::`2'::s_WinHeap = HeapCreate(0, 0x10000u, 0);
          atexit(`WinHeap::GetDefault'::`2'::`dynamic atexit destructor for 's_WinHeap'');
          Init_thread_footer(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
        }
      }
      if ( `WinHeap::GetDefault'::`2'::s_WinHeap )
        HeapFree(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v18);
      *(_QWORD *)a1 = 0;
    }
    *(_QWORD *)(a1 + 8) = 0;
    result = 0;
    v4 = 0;
    goto LABEL_51;
  }
  if ( !a3 || a2 >= *(_QWORD *)(a1 + 8) >> 2 )
    return 1;
  v6 = a2 | 0xF;
  if ( !a2 )
    v6 = 0;
  if ( !v6 )
  {
    v21 = *(_QWORD **)a1;
    if ( v21 )
    {
      WinFree(v21);
      *(_QWORD *)a1 = 0;
    }
    goto LABEL_65;
  }
  if ( v6 <= 0x7FFFFFFFFFFFFFFLL && 32 * v6 <= 0xFFFFFFFF )
  {
    v22 = *(_QWORD **)a1;
    if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                     + (unsigned int)tls_index)
                                                                   + 4LL) )
    {
      Init_thread_header(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
      if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA == -1 )
      {
        `WinHeap::GetDefault'::`2'::s_WinHeap = 0;
        dwFlags = 0;
        `WinHeap::GetDefault'::`2'::s_WinHeap = HeapCreate(0, 0x10000u, 0);
        atexit(`WinHeap::GetDefault'::`2'::`dynamic atexit destructor for 's_WinHeap'');
        Init_thread_footer(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
      }
    }
    if ( `WinHeap::GetDefault'::`2'::s_WinHeap )
    {
      v23 = v22
          ? HeapReAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v22, 32 * v6)
          : HeapAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, 32 * v6);
      if ( v23 )
      {
        *(_QWORD *)a1 = v23;
LABEL_65:
        result = 1;
        *(_QWORD *)(a1 + 16) = v6;
        return result;
      }
    }
  }
  v7 = *(_QWORD *)(a1 + 8);
  if ( v7 )
  {
    v8 = *(_QWORD **)a1;
    for ( i = 0; i < v7; ++i )
    {
      Vector<unsigned char,BasicAllocator<unsigned char>>::~Vector<unsigned char,BasicAllocator<unsigned char>>(&v8[4 * i + 1]);
      v10 = v8[4 * i];
      if ( v10 )
      {
        v11 = *(_DWORD *)(v10 + 8);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v10 + 8), 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(__int64, __int64))v10)(v10, 1);
        if ( v11 == 1 )
          v8[4 * i] = 0;
      }
    }
  }
  if ( *(_QWORD *)a1 )
  {
    WinFree(*(void **)a1);
    *(_QWORD *)a1 = 0;
  }
  *(_QWORD *)(a1 + 8) = 0;
  result = 0;
  *(_QWORD *)(a1 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x1800033f0  push    rbx
0x1800033f2  push    rbp
0x1800033f3  push    rsi
0x1800033f4  push    rdi
0x1800033f5  push    r12
0x1800033f7  push    r14
0x1800033f9  push    r15
0x1800033fb  sub     rsp, 20h
0x1800033ff  mov     rbx, rdx
0x180003402  mov     rdi, rcx
0x180003405  cmp     rdx, [rcx+10h]
0x180003409  jbe     short loc_18000344C
0x18000340b  cmp     rdx, 20h ; ' '
0x18000340f  jnb     loc_180003520
0x180003415  cmp     rdx, 2
0x180003419  jb      loc_18000368B
0x18000341f  cmp     rdx, 4
0x180003423  jb      loc_180003697
0x180003429  cmp     rdx, 8
0x18000342d  jb      loc_18000360D
0x180003433  cmp     rdx, 10h
0x180003437  jnb     loc_1800036AA
0x18000343d  mov     ebx, 0Fh
0x180003442  mov     ebp, 1E0h
0x180003447  jmp     loc_180003617
0x18000344c  test    r8b, r8b
0x18000344f  jz      loc_1800036A6
0x180003455  mov     rax, [rcx+8]
0x180003459  shr     rax, 2
0x18000345d  cmp     rbx, rax
0x180003460  jnb     loc_1800036A6
0x180003466  xor     esi, esi
0x180003468  mov     rbp, rbx
0x18000346b  or      rbp, 0Fh
0x18000346f  test    rbx, rbx
0x180003472  cmovz   rbp, rsi
0x180003476  test    rbp, rbp
0x180003479  jz      loc_1800036C2
0x18000347f  mov     rax, 7FFFFFFFFFFFFFFh
0x180003489  cmp     rbp, rax
0x18000348c  ja      short loc_1800034A3
0x18000348e  mov     rbx, rbp
0x180003491  mov     eax, 0FFFFFFFFh
0x180003496  shl     rbx, 5
0x18000349a  cmp     rbx, rax
0x18000349d  jbe     loc_1800036D4
0x1800034a3  mov     r14, [rdi+8]
0x1800034a7  test    r14, r14
0x1800034aa  jz      short loc_1800034F7
0x1800034ac  mov     r15, [rdi]
0x1800034af  mov     rbp, rsi
0x1800034b2  mov     rbx, rbp
0x1800034b5  lea     rcx, [r15+8]
0x1800034b9  shl     rbx, 5
0x1800034bd  add     rcx, rbx
0x1800034c0  call    ??1?$Vector@EV?$BasicAllocator@E@@@@QEAA@XZ; Vector<uchar,BasicAllocator<uchar>>::~Vector<uchar,BasicAllocator<uchar>>(void)
0x1800034c5  mov     rcx, [rbx+r15]
0x1800034c9  test    rcx, rcx
0x1800034cc  jz      short loc_1800034EF
0x1800034ce  mov     r12d, [rcx+8]
0x1800034d2  mov     eax, 0FFFFFFFFh
0x1800034d7  lock xadd [rcx+8], eax
0x1800034dc  cmp     eax, 1
0x1800034df  jz      loc_180003768
0x1800034e5  cmp     r12d, 1
0x1800034e9  jnz     short loc_1800034EF
0x1800034eb  mov     [rbx+r15], rsi
0x1800034ef  inc     rbp
0x1800034f2  cmp     rbp, r14
0x1800034f5  jb      short loc_1800034B2
0x1800034f7  mov     rcx, [rdi]; void *
0x1800034fa  test    rcx, rcx
0x1800034fd  jz      short loc_180003507
0x1800034ff  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x180003504  mov     [rdi], rsi
0x180003507  mov     [rdi+8], rsi
0x18000350b  xor     al, al
0x18000350d  mov     [rdi+10h], rsi
0x180003511  add     rsp, 20h
0x180003515  pop     r15
0x180003517  pop     r14
0x180003519  pop     r12
0x18000351b  pop     rdi
0x18000351c  pop     rsi
0x18000351d  pop     rbp
0x18000351e  pop     rbx
0x18000351f  retn
0x180003520  or      rbx, 0Fh
0x180003524  mov     rax, 7FFFFFFFFFFFFFFh
0x18000352e  cmp     rbx, rax
0x180003531  ja      short loc_180003548
0x180003533  mov     rbp, rbx
0x180003536  mov     eax, 0FFFFFFFFh
0x18000353b  shl     rbp, 5
0x18000353f  cmp     rbp, rax
0x180003542  jbe     loc_180003617
0x180003548  mov     r12d, cs:_tls_index
0x18000354f  xor     esi, esi
0x180003551  mov     r15d, 4
0x180003557  mov     r14, [rdi+8]
0x18000355b  test    r14, r14
0x18000355e  jz      short loc_1800035B9
0x180003560  mov     [rsp+58h+arg_10], r13
0x180003565  mov     rbp, rsi
0x180003568  mov     r13, [rdi]
0x18000356b  mov     rbx, rbp
0x18000356e  lea     rcx, [r13+8]
0x180003572  shl     rbx, 5
0x180003576  add     rcx, rbx
0x180003579  call    ??1?$Vector@EV?$BasicAllocator@E@@@@QEAA@XZ; Vector<uchar,BasicAllocator<uchar>>::~Vector<uchar,BasicAllocator<uchar>>(void)
0x18000357e  mov     rcx, [rbx+r13]
0x180003582  test    rcx, rcx
0x180003585  jz      short loc_1800035AC
0x180003587  mov     eax, [rcx+8]
0x18000358a  mov     [rsp+58h+arg_0], eax
0x18000358e  mov     eax, 0FFFFFFFFh
0x180003593  lock xadd [rcx+8], eax
0x180003598  cmp     eax, 1
0x18000359b  jz      loc_180003753
0x1800035a1  cmp     [rsp+58h+arg_0], 1
0x1800035a6  jnz     short loc_1800035AC
0x1800035a8  mov     [rbx+r13], rsi
0x1800035ac  inc     rbp
0x1800035af  cmp     rbp, r14
0x1800035b2  jb      short loc_18000356B
0x1800035b4  mov     r13, [rsp+58h+arg_10]
0x1800035b9  mov     rbx, [rdi]
0x1800035bc  test    rbx, rbx
0x1800035bf  jz      short loc_180003602
0x1800035c1  mov     rax, gs:58h
0x1800035ca  mov     ecx, r12d
0x1800035cd  mov     r8d, r15d
0x1800035d0  mov     rax, [rax+rcx*8]
0x1800035d4  mov     eax, [r8+rax]
0x1800035d8  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x1800035de  jg      loc_1800037D7
0x1800035e4  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x1800035eb  test    rcx, rcx
0x1800035ee  jz      short loc_1800035FF
0x1800035f0  mov     edx, cs:dwFlags; dwFlags
0x1800035f6  mov     r8, rbx; lpMem
0x1800035f9  call    cs:__imp_HeapFree
0x1800035ff  mov     [rdi], rsi
0x180003602  mov     [rdi+8], rsi
0x180003606  xor     al, al
0x180003608  mov     rbx, rsi
0x18000360b  jmp     short loc_180003678
0x18000360d  mov     ebx, 7
0x180003612  mov     ebp, 0E0h
0x180003617  mov     r12d, cs:_tls_index
0x18000361e  xor     esi, esi
0x180003620  mov     rax, gs:58h
0x180003629  mov     r14, [rcx]
0x18000362c  mov     r15d, 4
0x180003632  mov     rax, [rax+r12*8]
0x180003636  mov     eax, [r15+rax]
0x18000363a  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x180003640  jg      loc_18000377D
0x180003646  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x18000364d  test    rcx, rcx
0x180003650  jz      loc_180003557
0x180003656  mov     edx, cs:dwFlags; dwFlags
0x18000365c  test    r14, r14
0x18000365f  jnz     short loc_1800036B4
0x180003661  mov     r8, rbp; dwBytes
0x180003664  call    cs:__imp_HeapAlloc
0x18000366a  test    rax, rax
0x18000366d  jz      loc_180003557
0x180003673  mov     [rdi], rax
0x180003676  mov     al, 1
0x180003678  mov     [rdi+10h], rbx
0x18000367c  add     rsp, 20h
0x180003680  pop     r15
0x180003682  pop     r14
0x180003684  pop     r12
0x180003686  pop     rdi
0x180003687  pop     rsi
0x180003688  pop     rbp
0x180003689  pop     rbx
0x18000368a  retn
0x18000368b  mov     ebx, 1
0x180003690  mov     ebp, 20h ; ' '
0x180003695  jmp     short loc_180003617
0x180003697  mov     ebx, 3
0x18000369c  mov     ebp, 60h ; '`'
0x1800036a1  jmp     loc_180003617
0x1800036a6  mov     al, 1
0x1800036a8  jmp     short loc_18000367C
0x1800036aa  mov     ebx, 1Fh
0x1800036af  jmp     loc_180003524
0x1800036b4  mov     r9, rbp; dwBytes
0x1800036b7  mov     r8, r14; lpMem
0x1800036ba  call    cs:__imp_HeapReAlloc
0x1800036c0  jmp     short loc_18000366A
0x1800036c2  mov     rcx, [rcx]; void *
0x1800036c5  test    rcx, rcx
0x1800036c8  jz      short loc_180003730
0x1800036ca  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x1800036cf  mov     [rdi], rsi
0x1800036d2  jmp     short loc_180003730
0x1800036d4  mov     edx, cs:_tls_index
0x1800036da  mov     rax, gs:58h
0x1800036e3  mov     r14, [rcx]
0x1800036e6  mov     r15d, 4
0x1800036ec  mov     rax, [rax+rdx*8]
0x1800036f0  mov     eax, [r15+rax]
0x1800036f4  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x1800036fa  jg      loc_180003831
0x180003700  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x180003707  test    rcx, rcx
0x18000370a  jz      loc_1800034A3
0x180003710  mov     edx, cs:dwFlags; dwFlags
0x180003716  test    r14, r14
0x180003719  jnz     short loc_180003745
0x18000371b  mov     r8, rbx; dwBytes
0x18000371e  call    cs:__imp_HeapAlloc
0x180003724  test    rax, rax
0x180003727  jz      loc_1800034A3
0x18000372d  mov     [rdi], rax
0x180003730  mov     al, 1
0x180003732  mov     [rdi+10h], rbp
0x180003736  add     rsp, 20h
0x18000373a  pop     r15
0x18000373c  pop     r14
0x18000373e  pop     r12
0x180003740  pop     rdi
0x180003741  pop     rsi
0x180003742  pop     rbp
0x180003743  pop     rbx
0x180003744  retn
0x180003745  mov     r9, rbx; dwBytes
0x180003748  mov     r8, r14; lpMem
0x18000374b  call    cs:__imp_HeapReAlloc
0x180003751  jmp     short loc_180003724
0x180003753  mov     rax, [rcx]
0x180003756  mov     edx, 1
0x18000375b  mov     rax, [rax]
0x18000375e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003763  jmp     loc_1800035A1
0x180003768  mov     rax, [rcx]
0x18000376b  mov     edx, 1
0x180003770  mov     rax, [rax]
0x180003773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003778  jmp     loc_1800034E5
0x18000377d  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180003784  call    _Init_thread_header
0x180003789  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x180003790  jnz     loc_180003646
0x180003796  xor     r8d, r8d; dwMaximumSize
0x180003799  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rsi; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x1800037a0  mov     edx, 10000h; dwInitialSize
0x1800037a5  mov     cs:dwFlags, esi
0x1800037ab  xor     ecx, ecx; flOptions
0x1800037ad  call    cs:__imp_HeapCreate
0x1800037b3  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x1800037ba  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x1800037c1  call    atexit
0x1800037c6  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x1800037cd  call    _Init_thread_footer
0x1800037d2  jmp     loc_180003646
0x1800037d7  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x1800037de  call    _Init_thread_header
0x1800037e3  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x1800037ea  jnz     loc_1800035E4
0x1800037f0  xor     r8d, r8d; dwMaximumSize
0x1800037f3  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rsi; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x1800037fa  mov     edx, 10000h; dwInitialSize
0x1800037ff  mov     cs:dwFlags, esi
0x180003805  xor     ecx, ecx; flOptions
0x180003807  call    cs:__imp_HeapCreate
0x18000380d  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x180003814  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x18000381b  call    atexit
0x180003820  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180003827  call    _Init_thread_footer
0x18000382c  jmp     loc_1800035E4
0x180003831  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180003838  call    _Init_thread_header
0x18000383d  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x180003844  jnz     loc_180003700
0x18000384a  xor     r8d, r8d; dwMaximumSize
0x18000384d  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rsi; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180003854  mov     edx, 10000h; dwInitialSize
0x180003859  mov     cs:dwFlags, esi
0x18000385f  xor     ecx, ecx; flOptions
0x180003861  call    cs:__imp_HeapCreate
0x180003867  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x18000386e  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180003875  call    atexit
0x18000387a  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180003881  call    _Init_thread_footer
0x180003886  jmp     loc_180003700
```
