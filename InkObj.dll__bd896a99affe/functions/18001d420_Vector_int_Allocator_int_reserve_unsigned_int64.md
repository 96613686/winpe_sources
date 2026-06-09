# Vector<int,Allocator<int>>::reserve(unsigned __int64)

- ea: `0x18001d420`
- end: `0x18001d69a`
- name: `?reserve@?$Vector@HV?$Allocator@H@@@@QEAA_N_K@Z`
- size: `634`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014aa0`
- `0x1800294b8`

## callees

- `0x18001d420`
- `0x18004451c`
- `0x1800445e8`
- `0x180044658`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d56e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d56e`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001d588`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001d588`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d4ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d516`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d4ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d516`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001d5bc`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001d616`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001d670`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001d5bc`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001d616`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001d670`

## pseudocode

```c
char __fastcall Vector<int,Allocator<int>>::reserve(__int64 a1, unsigned __int64 a2)
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
  if ( a2 <= 0x3FFFFFFFFFFFFFFFLL )
  {
    v5 = 4 * a2;
    if ( 4 * a2 <= 0xFFFFFFFF )
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
0x18001d420  push    rbx
0x18001d422  push    rbp
0x18001d423  push    rsi
0x18001d424  push    rdi
0x18001d425  push    r12
0x18001d427  push    r14
0x18001d429  push    r15
0x18001d42b  sub     rsp, 20h
0x18001d42f  mov     rdi, rdx
0x18001d432  mov     rbx, rcx
0x18001d435  test    rdx, rdx
0x18001d438  jz      loc_18001D4CE
0x18001d43e  mov     r15d, cs:_tls_index
0x18001d445  mov     rax, 3FFFFFFFFFFFFFFFh
0x18001d44f  xor     esi, esi
0x18001d451  mov     r14d, 4
0x18001d457  cmp     rdx, rax
0x18001d45a  ja      short loc_18001D472
0x18001d45c  lea     rbp, ds:0[rdx*4]
0x18001d464  mov     eax, 0FFFFFFFFh
0x18001d469  cmp     rbp, rax
0x18001d46c  jbe     loc_18001D534
0x18001d472  mov     rdi, [rbx]
0x18001d475  test    rdi, rdi
0x18001d478  jz      short loc_18001D4B5
0x18001d47a  mov     rax, gs:58h
0x18001d483  mov     rax, [rax+r15*8]
0x18001d487  mov     eax, [r14+rax]
0x18001d48b  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x18001d491  jg      loc_18001D5E6
0x18001d497  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x18001d49e  test    rcx, rcx
0x18001d4a1  jz      short loc_18001D4B2
0x18001d4a3  mov     edx, cs:dwFlags; dwFlags
0x18001d4a9  mov     r8, rdi; lpMem
0x18001d4ac  call    cs:__imp_HeapFree
0x18001d4b2  mov     [rbx], rsi
0x18001d4b5  mov     [rbx+8], rsi
0x18001d4b9  xor     al, al
0x18001d4bb  mov     [rbx+10h], rsi
0x18001d4bf  add     rsp, 20h
0x18001d4c3  pop     r15
0x18001d4c5  pop     r14
0x18001d4c7  pop     r12
0x18001d4c9  pop     rdi
0x18001d4ca  pop     rsi
0x18001d4cb  pop     rbp
0x18001d4cc  pop     rbx
0x18001d4cd  retn
0x18001d4ce  mov     rbp, [rcx]
0x18001d4d1  test    rbp, rbp
0x18001d4d4  jz      short loc_18001D51F
0x18001d4d6  mov     edx, cs:_tls_index
0x18001d4dc  xor     esi, esi
0x18001d4de  mov     rax, gs:58h
0x18001d4e7  mov     r14d, 4
0x18001d4ed  mov     rax, [rax+rdx*8]
0x18001d4f1  mov     eax, [r14+rax]
0x18001d4f5  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x18001d4fb  jg      loc_18001D640
0x18001d501  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x18001d508  test    rcx, rcx
0x18001d50b  jz      short loc_18001D51C
0x18001d50d  mov     edx, cs:dwFlags; dwFlags
0x18001d513  mov     r8, rbp; lpMem
0x18001d516  call    cs:__imp_HeapFree
0x18001d51c  mov     [rbx], rsi
0x18001d51f  mov     [rbx+10h], rdi
0x18001d523  mov     al, 1
0x18001d525  add     rsp, 20h
0x18001d529  pop     r15
0x18001d52b  pop     r14
0x18001d52d  pop     r12
0x18001d52f  pop     rdi
0x18001d530  pop     rsi
0x18001d531  pop     rbp
0x18001d532  pop     rbx
0x18001d533  retn
0x18001d534  mov     rax, gs:58h
0x18001d53d  mov     r12, [rcx]
0x18001d540  mov     rax, [rax+r15*8]
0x18001d544  mov     eax, [r14+rax]
0x18001d548  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x18001d54e  jg      short loc_18001D590
0x18001d550  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x18001d557  test    rcx, rcx
0x18001d55a  jz      loc_18001D472
0x18001d560  mov     edx, cs:dwFlags; dwFlags
0x18001d566  test    r12, r12
0x18001d569  jnz     short loc_18001D582
0x18001d56b  mov     r8, rbp; dwBytes
0x18001d56e  call    cs:__imp_HeapAlloc
0x18001d574  test    rax, rax
0x18001d577  jz      loc_18001D472
0x18001d57d  mov     [rbx], rax
0x18001d580  jmp     short loc_18001D51F
0x18001d582  mov     r9, rbp; dwBytes
0x18001d585  mov     r8, r12; lpMem
0x18001d588  call    cs:__imp_HeapReAlloc
0x18001d58e  jmp     short loc_18001D574
0x18001d590  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18001d597  call    _Init_thread_header
0x18001d59c  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x18001d5a3  jnz     short loc_18001D550
0x18001d5a5  xor     r8d, r8d; dwMaximumSize
0x18001d5a8  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rsi; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x18001d5af  mov     edx, 10000h; dwInitialSize
0x18001d5b4  mov     cs:dwFlags, esi
0x18001d5ba  xor     ecx, ecx; flOptions
0x18001d5bc  call    cs:__imp_HeapCreate
0x18001d5c2  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x18001d5c9  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x18001d5d0  call    atexit
0x18001d5d5  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18001d5dc  call    _Init_thread_footer
0x18001d5e1  jmp     loc_18001D550
0x18001d5e6  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18001d5ed  call    _Init_thread_header
0x18001d5f2  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x18001d5f9  jnz     loc_18001D497
0x18001d5ff  xor     r8d, r8d; dwMaximumSize
0x18001d602  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rsi; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x18001d609  mov     edx, 10000h; dwInitialSize
0x18001d60e  mov     cs:dwFlags, esi
0x18001d614  xor     ecx, ecx; flOptions
0x18001d616  call    cs:__imp_HeapCreate
0x18001d61c  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x18001d623  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x18001d62a  call    atexit
0x18001d62f  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18001d636  call    _Init_thread_footer
0x18001d63b  jmp     loc_18001D497
0x18001d640  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18001d647  call    _Init_thread_header
0x18001d64c  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x18001d653  jnz     loc_18001D501
0x18001d659  xor     r8d, r8d; dwMaximumSize
0x18001d65c  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rsi; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x18001d663  mov     edx, 10000h; dwInitialSize
0x18001d668  mov     cs:dwFlags, esi
0x18001d66e  xor     ecx, ecx; flOptions
0x18001d670  call    cs:__imp_HeapCreate
0x18001d676  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x18001d67d  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x18001d684  call    atexit
0x18001d689  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18001d690  call    _Init_thread_footer
0x18001d695  jmp     loc_18001D501
```
