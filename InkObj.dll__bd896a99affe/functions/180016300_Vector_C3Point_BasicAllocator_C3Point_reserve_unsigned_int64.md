# Vector<C3Point,BasicAllocator<C3Point>>::reserve(unsigned __int64)

- ea: `0x180016300`
- end: `0x18001657f`
- name: `?reserve@?$Vector@VC3Point@@V?$BasicAllocator@VC3Point@@@@@@QEAA_N_K@Z`
- size: `639`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014aa0`
- `0x180093c70`

## callees

- `0x180016300`
- `0x18004451c`
- `0x1800445e8`
- `0x180044658`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001638b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001638b`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180016466`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180016466`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800163e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016452`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800163e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016452`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800164a1`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800164fb`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180016555`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800164a1`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800164fb`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180016555`

## pseudocode

```c
char __fastcall Vector<C3Point,BasicAllocator<C3Point>>::reserve(__int64 a1, unsigned __int64 a2)
{
  __int64 v4; // r15
  SIZE_T v5; // rbp
  void *v6; // r12
  LPVOID v7; // rax
  char result; // al
  void *v9; // rdi
  void *v10; // rbp

  if ( !a2 )
  {
    v10 = *(void **)a1;
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
        HeapFree(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v10);
      *(_QWORD *)a1 = 0;
    }
    goto LABEL_10;
  }
  v4 = (unsigned int)tls_index;
  if ( a2 <= 0xFFFFFFFFFFFFFFFLL )
  {
    v5 = 16 * a2;
    if ( 16 * a2 <= 0xFFFFFFFF )
    {
      v6 = *(void **)a1;
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
  v9 = *(void **)a1;
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
      HeapFree(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v9);
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
0x180016300  push    rbx
0x180016302  push    rbp
0x180016303  push    rsi
0x180016304  push    rdi
0x180016305  push    r12
0x180016307  push    r14
0x180016309  push    r15
0x18001630b  sub     rsp, 20h
0x18001630f  mov     rdi, rdx
0x180016312  mov     rbx, rcx
0x180016315  test    rdx, rdx
0x180016318  jz      loc_18001640A
0x18001631e  mov     r15d, cs:_tls_index
0x180016325  mov     rax, 0FFFFFFFFFFFFFFFh
0x18001632f  xor     esi, esi
0x180016331  mov     r14d, 4
0x180016337  cmp     rdx, rax
0x18001633a  ja      short loc_1800163AE
0x18001633c  mov     rbp, rdx
0x18001633f  mov     eax, 0FFFFFFFFh
0x180016344  shl     rbp, 4
0x180016348  cmp     rbp, rax
0x18001634b  ja      short loc_1800163AE
0x18001634d  mov     rax, gs:58h
0x180016356  mov     r12, [rcx]
0x180016359  mov     rax, [rax+r15*8]
0x18001635d  mov     eax, [r14+rax]
0x180016361  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x180016367  jg      loc_180016471
0x18001636d  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x180016374  test    rcx, rcx
0x180016377  jz      short loc_1800163AE
0x180016379  mov     edx, cs:dwFlags; dwFlags
0x18001637f  test    r12, r12
0x180016382  jnz     loc_180016460
0x180016388  mov     r8, rbp; dwBytes
0x18001638b  call    cs:__imp_HeapAlloc
0x180016391  test    rax, rax
0x180016394  jz      short loc_1800163AE
0x180016396  mov     [rbx], rax
0x180016399  mov     [rbx+10h], rdi
0x18001639d  mov     al, 1
0x18001639f  add     rsp, 20h
0x1800163a3  pop     r15
0x1800163a5  pop     r14
0x1800163a7  pop     r12
0x1800163a9  pop     rdi
0x1800163aa  pop     rsi
0x1800163ab  pop     rbp
0x1800163ac  pop     rbx
0x1800163ad  retn
0x1800163ae  mov     rdi, [rbx]
0x1800163b1  test    rdi, rdi
0x1800163b4  jz      short loc_1800163F1
0x1800163b6  mov     rax, gs:58h
0x1800163bf  mov     rax, [rax+r15*8]
0x1800163c3  mov     eax, [r14+rax]
0x1800163c7  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x1800163cd  jg      loc_1800164CB
0x1800163d3  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x1800163da  test    rcx, rcx
0x1800163dd  jz      short loc_1800163EE
0x1800163df  mov     edx, cs:dwFlags; dwFlags
0x1800163e5  mov     r8, rdi; lpMem
0x1800163e8  call    cs:__imp_HeapFree
0x1800163ee  mov     [rbx], rsi
0x1800163f1  mov     [rbx+8], rsi
0x1800163f5  xor     al, al
0x1800163f7  mov     [rbx+10h], rsi
0x1800163fb  add     rsp, 20h
0x1800163ff  pop     r15
0x180016401  pop     r14
0x180016403  pop     r12
0x180016405  pop     rdi
0x180016406  pop     rsi
0x180016407  pop     rbp
0x180016408  pop     rbx
0x180016409  retn
0x18001640a  mov     rbp, [rcx]
0x18001640d  test    rbp, rbp
0x180016410  jz      short loc_180016399
0x180016412  mov     edx, cs:_tls_index
0x180016418  xor     esi, esi
0x18001641a  mov     rax, gs:58h
0x180016423  mov     r14d, 4
0x180016429  mov     rax, [rax+rdx*8]
0x18001642d  mov     eax, [r14+rax]
0x180016431  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x180016437  jg      loc_180016525
0x18001643d  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x180016444  test    rcx, rcx
0x180016447  jz      short loc_180016458
0x180016449  mov     edx, cs:dwFlags; dwFlags
0x18001644f  mov     r8, rbp; lpMem
0x180016452  call    cs:__imp_HeapFree
0x180016458  mov     [rbx], rsi
0x18001645b  jmp     loc_180016399
0x180016460  mov     r9, rbp; dwBytes
0x180016463  mov     r8, r12; lpMem
0x180016466  call    cs:__imp_HeapReAlloc
0x18001646c  jmp     loc_180016391
0x180016471  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180016478  call    _Init_thread_header
0x18001647d  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x180016484  jnz     loc_18001636D
0x18001648a  xor     r8d, r8d; dwMaximumSize
0x18001648d  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rsi; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180016494  mov     edx, 10000h; dwInitialSize
0x180016499  mov     cs:dwFlags, esi
0x18001649f  xor     ecx, ecx; flOptions
0x1800164a1  call    cs:__imp_HeapCreate
0x1800164a7  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x1800164ae  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x1800164b5  call    atexit
0x1800164ba  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x1800164c1  call    _Init_thread_footer
0x1800164c6  jmp     loc_18001636D
0x1800164cb  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x1800164d2  call    _Init_thread_header
0x1800164d7  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x1800164de  jnz     loc_1800163D3
0x1800164e4  xor     r8d, r8d; dwMaximumSize
0x1800164e7  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rsi; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x1800164ee  mov     edx, 10000h; dwInitialSize
0x1800164f3  mov     cs:dwFlags, esi
0x1800164f9  xor     ecx, ecx; flOptions
0x1800164fb  call    cs:__imp_HeapCreate
0x180016501  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x180016508  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x18001650f  call    atexit
0x180016514  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18001651b  call    _Init_thread_footer
0x180016520  jmp     loc_1800163D3
0x180016525  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18001652c  call    _Init_thread_header
0x180016531  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x180016538  jnz     loc_18001643D
0x18001653e  xor     r8d, r8d; dwMaximumSize
0x180016541  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rsi; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180016548  mov     edx, 10000h; dwInitialSize
0x18001654d  mov     cs:dwFlags, esi
0x180016553  xor     ecx, ecx; flOptions
0x180016555  call    cs:__imp_HeapCreate
0x18001655b  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x180016562  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180016569  call    atexit
0x18001656e  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180016575  call    _Init_thread_footer
0x18001657a  jmp     loc_18001643D
```
