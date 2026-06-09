# CTx::BufferTraceMsg(_GUID const * const,ulong,...)

- ea: `0x18000eb50`
- end: `0x18000ed86`
- name: `?BufferTraceMsg@CTx@@UEAAXQEBU_GUID@@KZZ`
- size: `566`
- prototype: `void(CTx *__hidden this, const struct _GUID *const, unsigned int, ...)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800703e0`
- `0x1800703f0`
- `0x180070410`
- `0x180070420`
- `0x180070430`

## callees

- `0x18000eb50`
- `0x180024b78`
- `0x180024be8`
- `0x180025104`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ec2f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ec2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ec26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ec26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ebb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ebb7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ecc0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ecc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void CTx::BufferTraceMsg(CTx *this, const struct _GUID *const a2, int a3, unsigned int a4, ...)
{
  va_list v6; // rax
  unsigned int v7; // ecx
  int v8; // edi
  unsigned int v9; // edi
  char *v10; // rbx
  _QWORD *v11; // rax
  unsigned int *v12; // rbx
  __int64 v13; // rax
  unsigned int v14; // eax
  const void **v15; // rdi
  unsigned int i; // esi
  _QWORD v17[2]; // [rsp+20h] [rbp-40h] BYREF
  _OWORD v18[3]; // [rsp+30h] [rbp-30h] BYREF
  va_list va; // [rsp+B0h] [rbp+50h] BYREF

  va_start(va, a4);
  memset((char *)v18 + 9, 0, 31);
  v17[0] = 0;
  if ( dword_1801681E4 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1801681E4);
    if ( dword_1801681E4 == -1 )
    {
      GetCurrentProcessId();
      Init_thread_footer(&dword_1801681E4);
    }
  }
  if ( HIDWORD(g_Trace) == 4 && (unsigned int)(a3 - 10) <= 0xF4 && *((_DWORD *)this + 370) )
  {
    v18[0] = *a2;
    LODWORD(v18[1]) = GetCurrentThreadId();
    *((_QWORD *)&v18[1] + 1) = GetTickCount64();
    LODWORD(v18[2]) = a3;
    va_copy(v6, va);
    v7 = a4;
    v8 = DWORD1(v18[2]);
    if ( a4 )
    {
      do
      {
        v8 += v7;
        v6 += 16;
        v7 = *((_DWORD *)v6 - 2);
      }
      while ( v7 );
      DWORD1(v18[2]) = v8;
    }
    v9 = v8 + 40;
    if ( v9 <= 0x158 )
    {
      v10 = (char *)this + 1424;
      if ( (*(unsigned int (__fastcall **)(char *))(*((_QWORD *)this + 178) + 80LL))((char *)this + 1424)
        || ((*(void (__fastcall **)(char *, _QWORD *))(*(_QWORD *)v10 + 64LL))((char *)this + 1424, v17),
            v9 + **(_DWORD **)(v17[0] + 8LL) > 0x158) )
      {
        v11 = HeapAlloc(g_MemMgrCTraceBuffer, 0, 0x190u);
        v17[1] = v11;
        if ( !v11 )
          return;
        v11[1] = &UTLink<_IOMGROVERLAP *>::`vftable';
        *((_DWORD *)v11 + 10) = 0;
        v11[6] = 0;
        *v11 = 0;
        v11[2] = v11;
        v11[4] = 0;
        v11[3] = 0;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 24LL))((char *)this + 1424);
      }
      (*(void (__fastcall **)(char *, _QWORD *))(*(_QWORD *)v10 + 64LL))((char *)this + 1424, v17);
      v12 = *(unsigned int **)(v17[0] + 8LL);
      v13 = *v12;
      *(_OWORD *)((char *)v12 + v13 + 56) = v18[0];
      *(_OWORD *)((char *)v12 + v13 + 72) = v18[1];
      *(_QWORD *)((char *)v12 + v13 + 88) = *(_QWORD *)&v18[2];
      *v12 += 40;
      v14 = *v12;
      va_copy((va_list)v15, va);
      for ( i = a4; i; i = *((_DWORD *)v15 - 2) )
      {
        memcpy_0((char *)v12 + v14 + 56, *v15, i);
        *v12 += i;
        v14 = *v12;
        v15 += 2;
      }
      ++v12[1];
    }
  }
}

```

## disassembly

```asm
0x18000eb50  mov     [rsp-28h+arg_10], r8d
0x18000eb55  mov     [rsp-28h+arg_18], r9
0x18000eb5a  push    rbp
0x18000eb5b  push    rbx
0x18000eb5c  push    rsi
0x18000eb5d  push    rdi
0x18000eb5e  push    r14
0x18000eb60  mov     rbp, rsp
0x18000eb63  sub     rsp, 60h
0x18000eb67  mov     rbx, rdx
0x18000eb6a  mov     rsi, rcx
0x18000eb6d  xor     r14d, r14d
0x18000eb70  xorps   xmm0, xmm0
0x18000eb73  movups  [rbp+var_30+9], xmm0
0x18000eb77  movups  [rbp+var_20+8], xmm0
0x18000eb7b  mov     [rbp+var_40], r14
0x18000eb7f  mov     edx, cs:_tls_index
0x18000eb85  mov     rax, gs:58h
0x18000eb8e  mov     ecx, 4
0x18000eb93  mov     rax, [rax+rdx*8]
0x18000eb97  mov     eax, [rcx+rax]
0x18000eb9a  cmp     cs:dword_1801681E4, eax
0x18000eba0  jle     short loc_18000EBCA
0x18000eba2  lea     rcx, dword_1801681E4
0x18000eba9  call    _Init_thread_header
0x18000ebae  cmp     cs:dword_1801681E4, 0FFFFFFFFh
0x18000ebb5  jnz     short loc_18000EBCA
0x18000ebb7  call    cs:__imp_GetCurrentProcessId
0x18000ebbd  nop
0x18000ebbe  lea     rcx, dword_1801681E4
0x18000ebc5  call    _Init_thread_footer
0x18000ebca  cmp     dword ptr cs:?g_Trace@@3VCTrace@@A+4, 4; CTrace g_Trace
0x18000ebd1  jnz     loc_18000ED7B
0x18000ebd7  mov     eax, [rbp+arg_10]
0x18000ebda  add     eax, 0FFFFFFF6h
0x18000ebdd  cmp     eax, 0F4h
0x18000ebe2  ja      loc_18000ED7B
0x18000ebe8  cmp     dword ptr [rsi+5C8h], 0
0x18000ebef  jz      loc_18000ED7B
0x18000ebf5  mov     eax, [rbx]
0x18000ebf7  mov     dword ptr [rbp+var_30], eax
0x18000ebfa  movzx   eax, word ptr [rbx+4]
0x18000ebfe  mov     word ptr [rbp+var_30+4], ax
0x18000ec02  movzx   eax, word ptr [rbx+6]
0x18000ec06  mov     word ptr [rbp+var_30+6], ax
0x18000ec0a  movzx   eax, byte ptr [rbx+8]
0x18000ec0e  mov     byte ptr [rbp+var_30+8], al
0x18000ec11  mov     eax, [rbx+9]
0x18000ec14  mov     dword ptr [rbp+var_30+9], eax
0x18000ec17  movzx   eax, word ptr [rbx+0Dh]
0x18000ec1b  mov     word ptr [rbp+var_30+0Dh], ax
0x18000ec1f  movzx   eax, byte ptr [rbx+0Fh]
0x18000ec23  mov     byte ptr [rbp+var_30+0Fh], al
0x18000ec26  call    cs:__imp_GetCurrentThreadId
0x18000ec2c  mov     dword ptr [rbp+var_20], eax
0x18000ec2f  call    cs:__imp_GetTickCount64
0x18000ec35  mov     qword ptr [rbp+var_20+8], rax
0x18000ec39  mov     eax, [rbp+arg_10]
0x18000ec3c  mov     dword ptr [rbp+var_10], eax
0x18000ec3f  lea     rax, [rbp+arg_18]
0x18000ec43  add     rax, 8
0x18000ec47  mov     ecx, [rax-8]
0x18000ec4a  mov     edi, dword ptr [rbp+var_10+4]
0x18000ec4d  test    ecx, ecx
0x18000ec4f  jz      short loc_18000EC61
0x18000ec51  add     edi, ecx
0x18000ec53  lea     rax, [rax+10h]
0x18000ec57  mov     ecx, [rax-8]
0x18000ec5a  test    ecx, ecx
0x18000ec5c  jnz     short loc_18000EC51
0x18000ec5e  mov     dword ptr [rbp+var_10+4], edi
0x18000ec61  add     edi, 28h ; '('
0x18000ec64  cmp     edi, 158h
0x18000ec6a  ja      loc_18000ED7B
0x18000ec70  lea     rbx, [rsi+590h]
0x18000ec77  mov     rax, [rbx]
0x18000ec7a  mov     rcx, rbx
0x18000ec7d  mov     rax, [rax+50h]
0x18000ec81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec86  test    eax, eax
0x18000ec88  jnz     short loc_18000ECB1
0x18000ec8a  mov     rax, [rbx]
0x18000ec8d  lea     rdx, [rbp+var_40]
0x18000ec91  mov     rcx, rbx
0x18000ec94  mov     rax, [rax+40h]
0x18000ec98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec9d  mov     rax, [rbp+var_40]
0x18000eca1  mov     rcx, [rax+8]
0x18000eca5  mov     ecx, [rcx]
0x18000eca7  add     ecx, edi
0x18000eca9  cmp     ecx, 158h
0x18000ecaf  jbe     short loc_18000ED07
0x18000ecb1  xor     edx, edx; dwFlags
0x18000ecb3  mov     r8d, 190h; dwBytes
0x18000ecb9  mov     rcx, cs:?g_MemMgrCTraceBuffer@@3VMemMgrSimple@@A; hHeap
0x18000ecc0  call    cs:__imp_HeapAlloc
0x18000ecc6  mov     [rbp+var_38], rax
0x18000ecca  test    rax, rax
0x18000eccd  jz      loc_18000ED7B
0x18000ecd3  lea     rdx, [rax+8]
0x18000ecd7  lea     rcx, ??_7?$UTLink@PEAU_IOMGROVERLAP@@@@6B@; const UTLink<_IOMGROVERLAP *>::`vftable'
0x18000ecde  mov     [rdx], rcx
0x18000ece1  mov     [rdx+20h], r14d
0x18000ece5  mov     [rdx+28h], r14
0x18000ece9  mov     [rax], r14
0x18000ecec  mov     [rdx+8], rax
0x18000ecf0  mov     [rdx+18h], r14
0x18000ecf4  mov     [rdx+10h], r14
0x18000ecf8  mov     rax, [rbx]
0x18000ecfb  mov     rcx, rbx
0x18000ecfe  mov     rax, [rax+18h]
0x18000ed02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed07  mov     rax, [rbx]
0x18000ed0a  lea     rdx, [rbp+var_40]
0x18000ed0e  mov     rcx, rbx
0x18000ed11  mov     rax, [rax+40h]
0x18000ed15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed1a  mov     rax, [rbp+var_40]
0x18000ed1e  mov     rbx, [rax+8]
0x18000ed22  mov     eax, [rbx]
0x18000ed24  movups  xmm0, [rbp+var_30]
0x18000ed28  movups  xmmword ptr [rax+rbx+38h], xmm0
0x18000ed2d  movups  xmm1, [rbp+var_20]
0x18000ed31  movups  xmmword ptr [rax+rbx+48h], xmm1
0x18000ed36  movsd   xmm0, [rbp+var_10]
0x18000ed3b  movsd   qword ptr [rax+rbx+58h], xmm0
0x18000ed41  add     dword ptr [rbx], 28h ; '('
0x18000ed44  mov     eax, [rbx]
0x18000ed46  lea     rdi, [rbp+arg_18]
0x18000ed4a  add     rdi, 8
0x18000ed4e  mov     esi, [rdi-8]
0x18000ed51  test    esi, esi
0x18000ed53  jz      short loc_18000ED78
0x18000ed55  lea     r14, [rbx+38h]
0x18000ed59  mov     r8d, esi; Size
0x18000ed5c  mov     ecx, eax
0x18000ed5e  add     rcx, r14; void *
0x18000ed61  mov     rdx, [rdi]; Src
0x18000ed64  call    memcpy_0
0x18000ed69  add     [rbx], esi
0x18000ed6b  mov     eax, [rbx]
0x18000ed6d  lea     rdi, [rdi+10h]
0x18000ed71  mov     esi, [rdi-8]
0x18000ed74  test    esi, esi
0x18000ed76  jnz     short loc_18000ED59
0x18000ed78  inc     dword ptr [rbx+4]
0x18000ed7b  add     rsp, 60h
0x18000ed7f  pop     r14
0x18000ed81  pop     rdi
0x18000ed82  pop     rsi
0x18000ed83  pop     rbx
0x18000ed84  pop     rbp
0x18000ed85  retn
```
