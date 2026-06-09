# Vector<CWaitProcThread *,Allocator<CWaitProcThread *>>::reserve(unsigned __int64)

- ea: `0x180014130`
- end: `0x1800143aa`
- name: `?reserve@?$Vector@PEAVCWaitProcThread@@V?$Allocator@PEAVCWaitProcThread@@@@@@QEAA_N_K@Z`
- size: `634`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013148`
- `0x18002fe34`
- `0x18003280c`
- `0x180038268`
- `0x18003b9c0`
- `0x180049818`
- `0x180066028`
- `0x1800884ac`
- `0x18008ab4c`
- `0x18008c214`
- `0x180090930`
- `0x1800916f4`
- `0x180091e38`
- `0x1800947a0`
- `0x1800fd820`
- `0x1800fe2e0`
- `0x1800ff090`

## callees

- `0x180014130`
- `0x18004451c`
- `0x1800445e8`
- `0x180044658`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001427e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001427e`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180014298`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180014298`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800141bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014226`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800141bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014226`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800142cc`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180014326`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180014380`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800142cc`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180014326`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180014380`

## pseudocode

```c
char __fastcall Vector<CWaitProcThread *,Allocator<CWaitProcThread *>>::reserve(__int64 a1, unsigned __int64 a2)
{
  __int64 v4; // r15
  SIZE_T v5; // rbp
  void *v6; // rdi
  char result; // al
  void *v8; // rbp
  void *v9; // r12
  LPVOID v10; // rax

  if ( !a2 )
  {
    v8 = *(void **)a1;
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
        HeapFree(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v8);
      *(_QWORD *)a1 = 0;
    }
    goto LABEL_15;
  }
  v4 = (unsigned int)tls_index;
  if ( a2 <= 0x1FFFFFFFFFFFFFFFLL )
  {
    v5 = 8 * a2;
    if ( 8 * a2 <= 0xFFFFFFFF )
    {
      v9 = *(void **)a1;
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
        v10 = v9
            ? HeapReAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v9, v5)
            : HeapAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v5);
        if ( v10 )
        {
          *(_QWORD *)a1 = v10;
LABEL_15:
          *(_QWORD *)(a1 + 16) = a2;
          return 1;
        }
      }
    }
  }
  v6 = *(void **)a1;
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
      HeapFree(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v6);
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
0x180014130  push    rbx
0x180014132  push    rbp
0x180014133  push    rsi
0x180014134  push    rdi
0x180014135  push    r12
0x180014137  push    r14
0x180014139  push    r15
0x18001413b  sub     rsp, 20h
0x18001413f  mov     rdi, rdx
0x180014142  mov     rbx, rcx
0x180014145  test    rdx, rdx
0x180014148  jz      loc_1800141DE
0x18001414e  mov     r15d, cs:_tls_index
0x180014155  mov     rax, 1FFFFFFFFFFFFFFFh
0x18001415f  xor     esi, esi
0x180014161  mov     r14d, 4
0x180014167  cmp     rdx, rax
0x18001416a  ja      short loc_180014182
0x18001416c  lea     rbp, ds:0[rdx*8]
0x180014174  mov     eax, 0FFFFFFFFh
0x180014179  cmp     rbp, rax
0x18001417c  jbe     loc_180014244
0x180014182  mov     rdi, [rbx]
0x180014185  test    rdi, rdi
0x180014188  jz      short loc_1800141C5
0x18001418a  mov     rax, gs:58h
0x180014193  mov     rax, [rax+r15*8]
0x180014197  mov     eax, [r14+rax]
0x18001419b  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x1800141a1  jg      loc_1800142F6
0x1800141a7  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x1800141ae  test    rcx, rcx
0x1800141b1  jz      short loc_1800141C2
0x1800141b3  mov     edx, cs:dwFlags; dwFlags
0x1800141b9  mov     r8, rdi; lpMem
0x1800141bc  call    cs:__imp_HeapFree
0x1800141c2  mov     [rbx], rsi
0x1800141c5  mov     [rbx+8], rsi
0x1800141c9  xor     al, al
0x1800141cb  mov     [rbx+10h], rsi
0x1800141cf  add     rsp, 20h
0x1800141d3  pop     r15
0x1800141d5  pop     r14
0x1800141d7  pop     r12
0x1800141d9  pop     rdi
0x1800141da  pop     rsi
0x1800141db  pop     rbp
0x1800141dc  pop     rbx
0x1800141dd  retn
0x1800141de  mov     rbp, [rcx]
0x1800141e1  test    rbp, rbp
0x1800141e4  jz      short loc_18001422F
0x1800141e6  mov     edx, cs:_tls_index
0x1800141ec  xor     esi, esi
0x1800141ee  mov     rax, gs:58h
0x1800141f7  mov     r14d, 4
0x1800141fd  mov     rax, [rax+rdx*8]
0x180014201  mov     eax, [r14+rax]
0x180014205  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x18001420b  jg      loc_180014350
0x180014211  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x180014218  test    rcx, rcx
0x18001421b  jz      short loc_18001422C
0x18001421d  mov     edx, cs:dwFlags; dwFlags
0x180014223  mov     r8, rbp; lpMem
0x180014226  call    cs:__imp_HeapFree
0x18001422c  mov     [rbx], rsi
0x18001422f  mov     [rbx+10h], rdi
0x180014233  mov     al, 1
0x180014235  add     rsp, 20h
0x180014239  pop     r15
0x18001423b  pop     r14
0x18001423d  pop     r12
0x18001423f  pop     rdi
0x180014240  pop     rsi
0x180014241  pop     rbp
0x180014242  pop     rbx
0x180014243  retn
0x180014244  mov     rax, gs:58h
0x18001424d  mov     r12, [rcx]
0x180014250  mov     rax, [rax+r15*8]
0x180014254  mov     eax, [r14+rax]
0x180014258  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x18001425e  jg      short loc_1800142A0
0x180014260  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x180014267  test    rcx, rcx
0x18001426a  jz      loc_180014182
0x180014270  mov     edx, cs:dwFlags; dwFlags
0x180014276  test    r12, r12
0x180014279  jnz     short loc_180014292
0x18001427b  mov     r8, rbp; dwBytes
0x18001427e  call    cs:__imp_HeapAlloc
0x180014284  test    rax, rax
0x180014287  jz      loc_180014182
0x18001428d  mov     [rbx], rax
0x180014290  jmp     short loc_18001422F
0x180014292  mov     r9, rbp; dwBytes
0x180014295  mov     r8, r12; lpMem
0x180014298  call    cs:__imp_HeapReAlloc
0x18001429e  jmp     short loc_180014284
0x1800142a0  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x1800142a7  call    _Init_thread_header
0x1800142ac  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x1800142b3  jnz     short loc_180014260
0x1800142b5  xor     r8d, r8d; dwMaximumSize
0x1800142b8  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rsi; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x1800142bf  mov     edx, 10000h; dwInitialSize
0x1800142c4  mov     cs:dwFlags, esi
0x1800142ca  xor     ecx, ecx; flOptions
0x1800142cc  call    cs:__imp_HeapCreate
0x1800142d2  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x1800142d9  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x1800142e0  call    atexit
0x1800142e5  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x1800142ec  call    _Init_thread_footer
0x1800142f1  jmp     loc_180014260
0x1800142f6  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x1800142fd  call    _Init_thread_header
0x180014302  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x180014309  jnz     loc_1800141A7
0x18001430f  xor     r8d, r8d; dwMaximumSize
0x180014312  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rsi; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180014319  mov     edx, 10000h; dwInitialSize
0x18001431e  mov     cs:dwFlags, esi
0x180014324  xor     ecx, ecx; flOptions
0x180014326  call    cs:__imp_HeapCreate
0x18001432c  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x180014333  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x18001433a  call    atexit
0x18001433f  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180014346  call    _Init_thread_footer
0x18001434b  jmp     loc_1800141A7
0x180014350  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180014357  call    _Init_thread_header
0x18001435c  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x180014363  jnz     loc_180014211
0x180014369  xor     r8d, r8d; dwMaximumSize
0x18001436c  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rsi; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180014373  mov     edx, 10000h; dwInitialSize
0x180014378  mov     cs:dwFlags, esi
0x18001437e  xor     ecx, ecx; flOptions
0x180014380  call    cs:__imp_HeapCreate
0x180014386  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x18001438d  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180014394  call    atexit
0x180014399  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x1800143a0  call    _Init_thread_footer
0x1800143a5  jmp     loc_180014211
```
