# Vector<Pair<GuidPtr,Bytes>,Allocator<Pair<GuidPtr,Bytes>>>::reserve(unsigned __int64)

- ea: `0x1800038a0`
- end: `0x180003b9a`
- name: `?reserve@?$Vector@V?$Pair@VGuidPtr@@VBytes@@@@V?$Allocator@V?$Pair@VGuidPtr@@VBytes@@@@@@@@QEAA_N_K@Z`
- size: `762`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002fe34`
- `0x18004392c`
- `0x18009c234`

## callees

- `0x1800038a0`
- `0x180003ba0`
- `0x18004451c`
- `0x1800445e8`
- `0x180044658`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000392b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000392b`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180003a6c`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180003a6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a58`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180003abc`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180003b16`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180003b70`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180003abc`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180003b16`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180003b70`

## pseudocode

```c
char __fastcall Vector<Pair<GuidPtr,Bytes>,Allocator<Pair<GuidPtr,Bytes>>>::reserve(__int64 a1, unsigned __int64 a2)
{
  __int64 v4; // r12
  SIZE_T v5; // rbp
  _QWORD *v6; // r15
  LPVOID v7; // rax
  char result; // al
  unsigned __int64 v9; // r15
  unsigned __int64 v10; // rbp
  _QWORD *v11; // r13
  __int64 v12; // rcx
  _QWORD *v13; // rdi
  _QWORD *v14; // rbp
  int v15; // [rsp+68h] [rbp+10h]

  if ( !a2 )
  {
    v14 = *(_QWORD **)a1;
    if ( *(_QWORD *)a1 )
    {
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
        HeapFree(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v14);
      *(_QWORD *)a1 = 0;
    }
    goto LABEL_10;
  }
  v4 = (unsigned int)tls_index;
  if ( a2 <= 0x7FFFFFFFFFFFFFFLL )
  {
    v5 = 32 * a2;
    if ( 32 * a2 <= 0xFFFFFFFF )
    {
      v6 = *(_QWORD **)a1;
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
        v7 = v6
           ? HeapReAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v6, v5)
           : HeapAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v5);
        if ( v7 )
        {
          *(_QWORD *)a1 = v7;
LABEL_10:
          *(_QWORD *)(a1 + 16) = a2;
          return 1;
        }
      }
    }
  }
  v9 = *(_QWORD *)(a1 + 8);
  if ( v9 )
  {
    v10 = 0;
    v11 = *(_QWORD **)a1;
    do
    {
      Vector<unsigned char,BasicAllocator<unsigned char>>::~Vector<unsigned char,BasicAllocator<unsigned char>>(&v11[4 * v10 + 1]);
      v12 = v11[4 * v10];
      if ( v12 )
      {
        v15 = *(_DWORD *)(v12 + 8);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v12 + 8), 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(__int64, __int64))v12)(v12, 1);
        if ( v15 == 1 )
          v11[4 * v10] = 0;
      }
      ++v10;
    }
    while ( v10 < v9 );
  }
  v13 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                     + v4)
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
      HeapFree(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v13);
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
0x1800038a0  push    rbx
0x1800038a2  push    rbp
0x1800038a3  push    rsi
0x1800038a4  push    rdi
0x1800038a5  push    r12
0x1800038a7  push    r14
0x1800038a9  push    r15
0x1800038ab  sub     rsp, 20h
0x1800038af  mov     rdi, rdx
0x1800038b2  mov     rbx, rcx
0x1800038b5  test    rdx, rdx
0x1800038b8  jz      loc_180003A0C
0x1800038be  mov     r12d, cs:_tls_index
0x1800038c5  mov     rax, 7FFFFFFFFFFFFFFh
0x1800038cf  xor     esi, esi
0x1800038d1  mov     r14d, 4
0x1800038d7  cmp     rdx, rax
0x1800038da  ja      short loc_18000394E
0x1800038dc  mov     rbp, rdx
0x1800038df  mov     eax, 0FFFFFFFFh
0x1800038e4  shl     rbp, 5
0x1800038e8  cmp     rbp, rax
0x1800038eb  ja      short loc_18000394E
0x1800038ed  mov     rax, gs:58h
0x1800038f6  mov     r15, [rcx]
0x1800038f9  mov     rax, [rax+r12*8]
0x1800038fd  mov     eax, [r14+rax]
0x180003901  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x180003907  jg      loc_180003A8C
0x18000390d  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x180003914  test    rcx, rcx
0x180003917  jz      short loc_18000394E
0x180003919  mov     edx, cs:dwFlags; dwFlags
0x18000391f  test    r15, r15
0x180003922  jnz     loc_180003A66
0x180003928  mov     r8, rbp; dwBytes
0x18000392b  call    cs:__imp_HeapAlloc
0x180003931  test    rax, rax
0x180003934  jz      short loc_18000394E
0x180003936  mov     [rbx], rax
0x180003939  mov     [rbx+10h], rdi
0x18000393d  mov     al, 1
0x18000393f  add     rsp, 20h
0x180003943  pop     r15
0x180003945  pop     r14
0x180003947  pop     r12
0x180003949  pop     rdi
0x18000394a  pop     rsi
0x18000394b  pop     rbp
0x18000394c  pop     rbx
0x18000394d  retn
0x18000394e  mov     r15, [rbx+8]
0x180003952  test    r15, r15
0x180003955  jz      short loc_1800039B0
0x180003957  mov     [rsp+58h+arg_0], r13
0x18000395c  mov     rbp, rsi
0x18000395f  mov     r13, [rbx]
0x180003962  mov     rdi, rbp
0x180003965  lea     rcx, [r13+8]
0x180003969  shl     rdi, 5
0x18000396d  add     rcx, rdi
0x180003970  call    ??1?$Vector@EV?$BasicAllocator@E@@@@QEAA@XZ; Vector<uchar,BasicAllocator<uchar>>::~Vector<uchar,BasicAllocator<uchar>>(void)
0x180003975  mov     rcx, [rdi+r13]
0x180003979  test    rcx, rcx
0x18000397c  jz      short loc_1800039A3
0x18000397e  mov     eax, [rcx+8]
0x180003981  mov     [rsp+58h+arg_8], eax
0x180003985  mov     eax, 0FFFFFFFFh
0x18000398a  lock xadd [rcx+8], eax
0x18000398f  cmp     eax, 1
0x180003992  jz      loc_180003A77
0x180003998  cmp     [rsp+58h+arg_8], 1
0x18000399d  jnz     short loc_1800039A3
0x18000399f  mov     [rdi+r13], rsi
0x1800039a3  inc     rbp
0x1800039a6  cmp     rbp, r15
0x1800039a9  jb      short loc_180003962
0x1800039ab  mov     r13, [rsp+58h+arg_0]
0x1800039b0  mov     rdi, [rbx]
0x1800039b3  test    rdi, rdi
0x1800039b6  jz      short loc_1800039F3
0x1800039b8  mov     rax, gs:58h
0x1800039c1  mov     rax, [rax+r12*8]
0x1800039c5  mov     eax, [r14+rax]
0x1800039c9  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x1800039cf  jg      loc_180003AE6
0x1800039d5  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x1800039dc  test    rcx, rcx
0x1800039df  jz      short loc_1800039F0
0x1800039e1  mov     edx, cs:dwFlags; dwFlags
0x1800039e7  mov     r8, rdi; lpMem
0x1800039ea  call    cs:__imp_HeapFree
0x1800039f0  mov     [rbx], rsi
0x1800039f3  mov     [rbx+8], rsi
0x1800039f7  xor     al, al
0x1800039f9  mov     [rbx+10h], rsi
0x1800039fd  add     rsp, 20h
0x180003a01  pop     r15
0x180003a03  pop     r14
0x180003a05  pop     r12
0x180003a07  pop     rdi
0x180003a08  pop     rsi
0x180003a09  pop     rbp
0x180003a0a  pop     rbx
0x180003a0b  retn
0x180003a0c  mov     rbp, [rcx]
0x180003a0f  test    rbp, rbp
0x180003a12  jz      loc_180003939
0x180003a18  mov     edx, cs:_tls_index
0x180003a1e  xor     esi, esi
0x180003a20  mov     rax, gs:58h
0x180003a29  mov     r14d, 4
0x180003a2f  mov     rax, [rax+rdx*8]
0x180003a33  mov     eax, [r14+rax]
0x180003a37  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x180003a3d  jg      loc_180003B40
0x180003a43  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x180003a4a  test    rcx, rcx
0x180003a4d  jz      short loc_180003A5E
0x180003a4f  mov     edx, cs:dwFlags; dwFlags
0x180003a55  mov     r8, rbp; lpMem
0x180003a58  call    cs:__imp_HeapFree
0x180003a5e  mov     [rbx], rsi
0x180003a61  jmp     loc_180003939
0x180003a66  mov     r9, rbp; dwBytes
0x180003a69  mov     r8, r15; lpMem
0x180003a6c  call    cs:__imp_HeapReAlloc
0x180003a72  jmp     loc_180003931
0x180003a77  mov     rax, [rcx]
0x180003a7a  mov     edx, 1
0x180003a7f  mov     rax, [rax]
0x180003a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a87  jmp     loc_180003998
0x180003a8c  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180003a93  call    _Init_thread_header
0x180003a98  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x180003a9f  jnz     loc_18000390D
0x180003aa5  xor     r8d, r8d; dwMaximumSize
0x180003aa8  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rsi; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180003aaf  mov     edx, 10000h; dwInitialSize
0x180003ab4  mov     cs:dwFlags, esi
0x180003aba  xor     ecx, ecx; flOptions
0x180003abc  call    cs:__imp_HeapCreate
0x180003ac2  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x180003ac9  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180003ad0  call    atexit
0x180003ad5  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180003adc  call    _Init_thread_footer
0x180003ae1  jmp     loc_18000390D
0x180003ae6  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180003aed  call    _Init_thread_header
0x180003af2  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x180003af9  jnz     loc_1800039D5
0x180003aff  xor     r8d, r8d; dwMaximumSize
0x180003b02  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rsi; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180003b09  mov     edx, 10000h; dwInitialSize
0x180003b0e  mov     cs:dwFlags, esi
0x180003b14  xor     ecx, ecx; flOptions
0x180003b16  call    cs:__imp_HeapCreate
0x180003b1c  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x180003b23  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180003b2a  call    atexit
0x180003b2f  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180003b36  call    _Init_thread_footer
0x180003b3b  jmp     loc_1800039D5
0x180003b40  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180003b47  call    _Init_thread_header
0x180003b4c  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x180003b53  jnz     loc_180003A43
0x180003b59  xor     r8d, r8d; dwMaximumSize
0x180003b5c  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rsi; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180003b63  mov     edx, 10000h; dwInitialSize
0x180003b68  mov     cs:dwFlags, esi
0x180003b6e  xor     ecx, ecx; flOptions
0x180003b70  call    cs:__imp_HeapCreate
0x180003b76  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x180003b7d  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180003b84  call    atexit
0x180003b89  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180003b90  call    _Init_thread_footer
0x180003b95  jmp     loc_180003A43
```
