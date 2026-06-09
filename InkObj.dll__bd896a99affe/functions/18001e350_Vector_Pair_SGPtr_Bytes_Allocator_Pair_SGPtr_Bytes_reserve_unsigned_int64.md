# Vector<Pair<SGPtr,Bytes>,Allocator<Pair<SGPtr,Bytes>>>::reserve(unsigned __int64)

- ea: `0x18001e350`
- end: `0x18001e55a`
- name: `?reserve@?$Vector@V?$Pair@VSGPtr@@VBytes@@@@V?$Allocator@V?$Pair@VSGPtr@@VBytes@@@@@@@@QEAA_N_K@Z`
- size: `522`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800085d8`
- `0x180008c30`
- `0x18001f810`

## callees

- `0x1800017f4`
- `0x180002740`
- `0x18001e350`
- `0x18004451c`
- `0x1800445e8`
- `0x180044658`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e3d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e3d8`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001e452`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001e452`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e43d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e43d`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001e492`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001e530`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001e492`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001e530`

## pseudocode

```c
char __fastcall Vector<Pair<SGPtr,Bytes>,Allocator<Pair<SGPtr,Bytes>>>::reserve(
        void **a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4)
{
  void **v5; // rdi
  SIZE_T v6; // rsi
  void *v7; // rbp
  LPVOID v8; // rax
  char result; // al
  void *v10; // rsi
  void *v11; // r8

  v5 = a1;
  if ( !a2 )
  {
    v10 = *a1;
    if ( *a1 )
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
      *v5 = 0;
    }
    goto LABEL_10;
  }
  if ( a2 <= 0x7FFFFFFFFFFFFFFLL )
  {
    v6 = 32 * a2;
    if ( 32 * a2 <= 0xFFFFFFFF )
    {
      v7 = *a1;
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
      a1 = (void **)`WinHeap::GetDefault'::`2'::s_WinHeap;
      if ( `WinHeap::GetDefault'::`2'::s_WinHeap )
      {
        v8 = v7
           ? HeapReAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v7, v6)
           : HeapAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v6);
        if ( v8 )
        {
          *v5 = v8;
LABEL_10:
          v5[2] = (void *)a2;
          return 1;
        }
      }
    }
  }
  v11 = v5[1];
  if ( v11 )
    Allocator<Pair<GuidPtr,Bytes>>::Destruct(a1, *v5, v11, a4);
  if ( *v5 )
  {
    WinFree(*v5);
    *v5 = 0;
  }
  v5[1] = 0;
  result = 0;
  v5[2] = 0;
  return result;
}

```

## disassembly

```asm
0x18001e350  push    rbx
0x18001e352  push    rbp
0x18001e353  push    rsi
0x18001e354  push    rdi
0x18001e355  sub     rsp, 28h
0x18001e359  mov     rbx, rdx
0x18001e35c  mov     rdi, rcx
0x18001e35f  test    rdx, rdx
0x18001e362  jz      loc_18001E3F9
0x18001e368  mov     rax, 7FFFFFFFFFFFFFFh
0x18001e372  cmp     rdx, rax
0x18001e375  ja      loc_18001E4BC
0x18001e37b  mov     rsi, rdx
0x18001e37e  mov     eax, 0FFFFFFFFh
0x18001e383  shl     rsi, 5
0x18001e387  cmp     rsi, rax
0x18001e38a  ja      loc_18001E4BC
0x18001e390  mov     edx, cs:_tls_index
0x18001e396  mov     rax, gs:58h
0x18001e39f  mov     rbp, [rcx]
0x18001e3a2  mov     ecx, 4
0x18001e3a7  mov     rax, [rax+rdx*8]
0x18001e3ab  mov     eax, [rcx+rax]
0x18001e3ae  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x18001e3b4  jg      loc_18001E45A
0x18001e3ba  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x18001e3c1  test    rcx, rcx
0x18001e3c4  jz      loc_18001E4BC
0x18001e3ca  mov     edx, cs:dwFlags; dwFlags
0x18001e3d0  test    rbp, rbp
0x18001e3d3  jnz     short loc_18001E44C
0x18001e3d5  mov     r8, rsi; dwBytes
0x18001e3d8  call    cs:__imp_HeapAlloc
0x18001e3de  test    rax, rax
0x18001e3e1  jz      loc_18001E4BC
0x18001e3e7  mov     [rdi], rax
0x18001e3ea  mov     [rdi+10h], rbx
0x18001e3ee  mov     al, 1
0x18001e3f0  add     rsp, 28h
0x18001e3f4  pop     rdi
0x18001e3f5  pop     rsi
0x18001e3f6  pop     rbp
0x18001e3f7  pop     rbx
0x18001e3f8  retn
0x18001e3f9  mov     rsi, [rcx]
0x18001e3fc  test    rsi, rsi
0x18001e3ff  jz      short loc_18001E3EA
0x18001e401  mov     edx, cs:_tls_index
0x18001e407  mov     rax, gs:58h
0x18001e410  mov     ecx, 4
0x18001e415  mov     rax, [rax+rdx*8]
0x18001e419  mov     eax, [rcx+rax]
0x18001e41c  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x18001e422  jg      loc_18001E4F8
0x18001e428  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x18001e42f  test    rcx, rcx
0x18001e432  jz      short loc_18001E443
0x18001e434  mov     edx, cs:dwFlags; dwFlags
0x18001e43a  mov     r8, rsi; lpMem
0x18001e43d  call    cs:__imp_HeapFree
0x18001e443  mov     qword ptr [rdi], 0
0x18001e44a  jmp     short loc_18001E3EA
0x18001e44c  mov     r9, rsi; dwBytes
0x18001e44f  mov     r8, rbp; lpMem
0x18001e452  call    cs:__imp_HeapReAlloc
0x18001e458  jmp     short loc_18001E3DE
0x18001e45a  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18001e461  call    _Init_thread_header
0x18001e466  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x18001e46d  jnz     loc_18001E3BA
0x18001e473  xor     r8d, r8d; dwMaximumSize
0x18001e476  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, 0; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x18001e481  mov     edx, 10000h; dwInitialSize
0x18001e486  mov     cs:dwFlags, 0
0x18001e490  xor     ecx, ecx; flOptions
0x18001e492  call    cs:__imp_HeapCreate
0x18001e498  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x18001e49f  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x18001e4a6  call    atexit
0x18001e4ab  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18001e4b2  call    _Init_thread_footer
0x18001e4b7  jmp     loc_18001E3BA
0x18001e4bc  mov     r8, [rdi+8]
0x18001e4c0  test    r8, r8
0x18001e4c3  jz      short loc_18001E4CD
0x18001e4c5  mov     rdx, [rdi]
0x18001e4c8  call    ?Destruct@?$Allocator@V?$Pair@VGuidPtr@@VBytes@@@@@@QEAAXPEAV?$Pair@VGuidPtr@@VBytes@@@@_K@Z; Allocator<Pair<GuidPtr,Bytes>>::Destruct(Pair<GuidPtr,Bytes> *,unsigned __int64)
0x18001e4cd  mov     rcx, [rdi]; void *
0x18001e4d0  test    rcx, rcx
0x18001e4d3  jz      short loc_18001E4E1
0x18001e4d5  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x18001e4da  mov     qword ptr [rdi], 0
0x18001e4e1  mov     qword ptr [rdi+8], 0
0x18001e4e9  xor     al, al
0x18001e4eb  mov     qword ptr [rdi+10h], 0
0x18001e4f3  jmp     loc_18001E3F0
0x18001e4f8  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18001e4ff  call    _Init_thread_header
0x18001e504  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x18001e50b  jnz     loc_18001E428
0x18001e511  xor     r8d, r8d; dwMaximumSize
0x18001e514  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, 0; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x18001e51f  mov     edx, 10000h; dwInitialSize
0x18001e524  mov     cs:dwFlags, 0
0x18001e52e  xor     ecx, ecx; flOptions
0x18001e530  call    cs:__imp_HeapCreate
0x18001e536  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x18001e53d  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x18001e544  call    atexit
0x18001e549  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18001e550  call    _Init_thread_footer
0x18001e555  jmp     loc_18001E428
```
