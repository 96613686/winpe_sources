# CTx::TraceMsg(_GUID const * const,ulong,...)

- ea: `0x1800755f0`
- end: `0x1800757dc`
- name: `?TraceMsg@CTx@@UEAAXQEBU_GUID@@KZZ`
- size: `492`
- prototype: `void(CTx *__hidden this, const struct _GUID *const, unsigned int, ...)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800757f0`
- `0x180075800`
- `0x180075820`
- `0x180075830`
- `0x180075840`

## callees

- `0x18000862c`
- `0x1800240f0`
- `0x1800240fc`
- `0x180024b78`
- `0x180024be8`
- `0x180025104`
- `0x1800755f0`
- `0x1800b8420`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800756c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800756c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800756b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800756b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007567b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007567b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void CTx::TraceMsg(CTx *this, const struct _GUID *const a2, int a3, ...)
{
  char *v5; // rdi
  int v6; // ebx
  va_list v7; // r14
  unsigned int v8; // esi
  _QWORD v9[2]; // [rsp+80h] [rbp-19h] BYREF
  char v10; // [rsp+90h] [rbp-9h]
  _BYTE v11[31]; // [rsp+91h] [rbp-8h] BYREF
  va_list va; // [rsp+118h] [rbp+7Fh] BYREF

  va_start(va, a3);
  v9[0] = 0;
  v9[1] = 0;
  v10 = 0;
  memset(v11, 0, sizeof(v11));
  if ( dword_1801681DC > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1801681DC);
    if ( dword_1801681DC == -1 )
    {
      dword_1801681E0 = GetCurrentProcessId();
      Init_thread_footer(&dword_1801681DC);
    }
  }
  v9[0] = 0;
  if ( HIDWORD(g_Trace) == 4 && (unsigned int)(a3 - 10) <= 0xF4 )
  {
    *(_DWORD *)&v11[7] = GetCurrentThreadId();
    *(_QWORD *)&v11[15] = GetTickCount64();
    *(_DWORD *)&v11[23] = a3;
    v5 = (char *)operator new[](0x158u);
    if ( v5 )
    {
      v6 = 0;
      v9[0] = *((_QWORD *)this + 183) + 10000LL * (*(_QWORD *)&v11[15] - *((_QWORD *)this + 184));
      va_copy(v7, va);
      while ( 1 )
      {
        v8 = *(_DWORD *)v7;
        if ( !*(_DWORD *)v7 )
          break;
        if ( v8 > 344 - v6 )
          goto LABEL_12;
        v7 += 16;
        memcpy_0(&v5[v6], *((const void **)v7 - 1), v8);
        v6 += v8;
      }
      *(_DWORD *)&v11[27] = v6;
      CTrace::TraceEvent(
        (CTrace *)&g_Trace,
        2u,
        0,
        a2,
        *(unsigned int *)&v11[23],
        4,
        &dword_1801681E0,
        16,
        (char *)this + 524,
        4,
        &v11[7],
        8,
        v9,
        v6,
        v5,
        0);
LABEL_12:
      operator delete(v5);
    }
  }
}

```

## disassembly

```asm
0x1800755f0  mov     [rsp-8+arg_10], r8d
0x1800755f5  mov     [rsp-8+arg_18], r9
0x1800755fa  push    rbp
0x1800755fb  push    rbx
0x1800755fc  push    rsi
0x1800755fd  push    rdi
0x1800755fe  push    r12
0x180075600  push    r14
0x180075602  push    r15
0x180075604  lea     rbp, [rsp-27h]
0x180075609  sub     rsp, 0C0h
0x180075610  mov     rax, cs:__security_cookie
0x180075617  xor     rax, rsp
0x18007561a  mov     [rbp+57h+var_40], rax
0x18007561e  mov     r12, rdx
0x180075621  mov     r15, rcx
0x180075624  mov     [rbp+57h+var_70], 0
0x18007562c  mov     [rbp+57h+var_68], 0
0x180075634  mov     [rbp+57h+var_60], 0
0x180075638  xorps   xmm0, xmm0
0x18007563b  movups  [rbp+57h+var_5F], xmm0
0x18007563f  movups  [rbp+57h+var_5F+0Fh], xmm0
0x180075643  mov     ecx, cs:_tls_index
0x180075649  mov     rax, gs:58h
0x180075652  mov     edx, 4
0x180075657  mov     rax, [rax+rcx*8]
0x18007565b  mov     ecx, [rdx+rax]
0x18007565e  cmp     cs:dword_1801681DC, ecx
0x180075664  jle     short loc_180075693
0x180075666  lea     rcx, dword_1801681DC
0x18007566d  call    _Init_thread_header
0x180075672  cmp     cs:dword_1801681DC, 0FFFFFFFFh
0x180075679  jnz     short loc_180075693
0x18007567b  call    cs:__imp_GetCurrentProcessId
0x180075681  mov     cs:dword_1801681E0, eax
0x180075687  lea     rcx, dword_1801681DC
0x18007568e  call    _Init_thread_footer
0x180075693  mov     [rbp+57h+var_70], 0
0x18007569b  cmp     dword ptr cs:?g_Trace@@3VCTrace@@A+4, 4; CTrace g_Trace
0x1800756a2  jnz     loc_1800757BE
0x1800756a8  mov     eax, [rbp+57h+arg_10]
0x1800756ab  add     eax, 0FFFFFFF6h
0x1800756ae  cmp     eax, 0F4h
0x1800756b3  ja      loc_1800757BE
0x1800756b9  call    cs:__imp_GetCurrentThreadId
0x1800756bf  mov     dword ptr [rbp+57h+var_5F+7], eax
0x1800756c2  call    cs:__imp_GetTickCount64
0x1800756c8  mov     qword ptr [rbp+57h+var_5F+0Fh], rax
0x1800756cc  mov     eax, [rbp+57h+arg_10]
0x1800756cf  mov     [rbp+57h+var_48], eax
0x1800756d2  mov     ecx, 158h; unsigned __int64
0x1800756d7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800756dc  mov     rdi, rax
0x1800756df  test    rax, rax
0x1800756e2  jz      loc_1800757BE
0x1800756e8  xor     ebx, ebx
0x1800756ea  mov     rcx, qword ptr [rbp+57h+var_5F+0Fh]
0x1800756ee  sub     rcx, [r15+5C0h]
0x1800756f5  imul    rdx, rcx, 2710h
0x1800756fc  add     rdx, [r15+5B8h]
0x180075703  mov     [rbp+57h+var_70], rdx
0x180075707  lea     r14, [rbp+57h+arg_18]
0x18007570b  mov     esi, [r14]
0x18007570e  test    esi, esi
0x180075710  jz      short loc_18007573A
0x180075712  mov     eax, 158h
0x180075717  sub     eax, ebx
0x180075719  cmp     esi, eax
0x18007571b  ja      loc_1800757B6
0x180075721  add     r14, 10h
0x180075725  mov     r8d, esi; Size
0x180075728  mov     ecx, ebx
0x18007572a  add     rcx, rdi; void *
0x18007572d  mov     rdx, [r14-8]; Src
0x180075731  call    memcpy_0
0x180075736  add     ebx, esi
0x180075738  jmp     short loc_18007570B
0x18007573a  mov     [rbp+57h+var_44], ebx
0x18007573d  lea     rax, [r15+20Ch]
0x180075744  mov     [rsp+0F0h+var_78], 0
0x18007574d  mov     [rsp+0F0h+var_80], rdi
0x180075752  mov     [rsp+0F0h+var_88], ebx
0x180075756  lea     rcx, [rbp+57h+var_70]
0x18007575a  mov     [rsp+0F0h+var_90], rcx
0x18007575f  mov     [rsp+0F0h+var_98], 8
0x180075768  lea     rcx, [rbp+57h+var_5F+7]
0x18007576c  mov     [rsp+0F0h+var_A0], rcx
0x180075771  mov     ecx, 4
0x180075776  mov     [rsp+0F0h+var_A8], rcx
0x18007577b  mov     [rsp+0F0h+var_B0], rax
0x180075780  mov     [rsp+0F0h+var_B8], 10h
0x180075789  lea     rax, dword_1801681E0
0x180075790  mov     [rsp+0F0h+var_C0], rax
0x180075795  mov     [rsp+0F0h+var_C8], rcx
0x18007579a  mov     eax, [rbp+57h+var_48]
0x18007579d  mov     [rsp+0F0h+var_D0], eax; unsigned int
0x1800757a1  mov     r9, r12; struct _GUID *
0x1800757a4  xor     r8d, r8d; unsigned int
0x1800757a7  lea     edx, [rcx-2]; unsigned int
0x1800757aa  lea     rcx, ?g_Trace@@3VCTrace@@A; this
0x1800757b1  call    ?TraceEvent@CTrace@@QEAAJKKQEBU_GUID@@KZZ; CTrace::TraceEvent(ulong,ulong,_GUID const * const,ulong,...)
0x1800757b6  mov     rcx, rdi; Block
0x1800757b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800757be  mov     rcx, [rbp+57h+var_40]
0x1800757c2  xor     rcx, rsp; StackCookie
0x1800757c5  call    __security_check_cookie
0x1800757ca  add     rsp, 0C0h
0x1800757d1  pop     r15
0x1800757d3  pop     r14
0x1800757d5  pop     r12
0x1800757d7  pop     rdi
0x1800757d8  pop     rsi
0x1800757d9  pop     rbx
0x1800757da  pop     rbp
0x1800757db  retn
```
