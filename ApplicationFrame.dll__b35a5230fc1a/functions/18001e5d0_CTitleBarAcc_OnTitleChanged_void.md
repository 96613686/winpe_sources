# CTitleBarAcc::OnTitleChanged(void)

- ea: `0x18001e5d0`
- end: `0x18001e8c8`
- name: `?OnTitleChanged@CTitleBarAcc@@UEAAXXZ`
- size: `760`
- prototype: `void __fastcall(CTitleBarAcc *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001e260`
- `0x18001e5d0`
- `0x18001feb0`
- `0x180024184`
- `0x18002e020`
- `0x1800532a8`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e63d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e63d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e718`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e718`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001e8a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001e8a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e728`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e728`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e766`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CTitleBarAcc::OnTitleChanged(RTL_SRWLOCK *this)
{
  CTitleBarElementBase *v2; // r15
  __int64 *Ptr; // rcx
  __int64 v4; // rax
  int v5; // eax
  RTL_SRWLOCK *v6; // r13
  RTL_SRWLOCK *v7; // rdi
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // r10
  __int16 *v10; // r12
  unsigned __int64 v11; // r14
  unsigned __int64 v12; // rsi
  int v13; // ebx
  const unsigned __int16 *v14; // rdx
  PVOID v15; // r14
  unsigned __int64 v16; // r15
  __int64 *v17; // rsi
  __int64 v18; // rbx
  LPVOID v19; // rdi
  unsigned int v20; // eax
  unsigned __int64 v21; // r9
  _WORD *v22; // rax
  _WORD *v23; // rdx
  unsigned __int64 v24; // rax
  __int16 v25; // cx
  _WORD *v26; // rcx
  __int64 v27; // r9
  unsigned __int64 v28; // r15
  LPVOID v29; // rax
  LPVOID pv; // [rsp+20h] [rbp-28h] BYREF
  __int64 v31; // [rsp+28h] [rbp-20h]
  __int64 v32; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  unsigned __int64 v35; // [rsp+98h] [rbp+50h] BYREF
  CTitleBarElementBase *v36; // [rsp+A0h] [rbp+58h]
  RTL_SRWLOCK *v37; // [rsp+A8h] [rbp+60h]

  pv = 0;
  v31 = 0;
  v32 = 0;
  v2 = (CTitleBarElementBase *)&this[-17];
  v36 = (CTitleBarElementBase *)&this[-17];
  Ptr = (__int64 *)this[11].Ptr;
  v4 = *Ptr;
  v31 = -1;
  v32 = -1;
  v5 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v4 + 264))(Ptr, &pv);
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x42F,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebaracc.cpp",
      (const char *)(unsigned int)v5,
      (int)pv);
  v6 = this - 1;
  AcquireSRWLockExclusive(this - 1);
  v37 = this - 1;
  v7 = this + 8;
  v8 = v31;
  v9 = 0;
  if ( v31 == -1 )
  {
    if ( pv )
    {
      v8 = -1;
      do
        ++v8;
      while ( *((_WORD *)pv + v8) );
    }
    else
    {
      v8 = 0;
    }
  }
  v10 = (__int16 *)pv;
  if ( !pv )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&this[8]);
    v9 = 0;
LABEL_16:
    v14 = &pszDefault;
    if ( v7->Ptr != (PVOID)v9 )
      v14 = (const unsigned __int16 *)v7->Ptr;
    CTitleBarElementBase::_GenerateNameAndAutomationPropertyString(v2, v14);
    v9 = 0;
    goto LABEL_19;
  }
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)pv + v11) );
  if ( v8 == -1 )
  {
    v8 = v11;
  }
  else if ( v8 < v11 )
  {
    v11 = v8;
  }
  v12 = v8 + 1;
  if ( v8 + 1 < v8 )
    goto LABEL_14;
  v21 = (unsigned __int64)this[10].Ptr;
  if ( v21 == -1 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&this[8]);
    if ( v7->Ptr == (PVOID)v9 )
      v21 = v9;
    else
      v21 = (unsigned __int64)this[9].Ptr + 1;
    this[10].Ptr = (PVOID)v21;
  }
  if ( !v21 )
  {
    if ( !is_mul_ok(v12, 2u) )
    {
LABEL_14:
      v13 = -2147024362;
      goto LABEL_15;
    }
    v22 = CoTaskMemAlloc(2 * v12);
    v9 = 0;
    if ( v22 )
    {
      this[10].Ptr = (PVOID)v12;
      v7->Ptr = v22;
      *v22 = 0;
      v13 = 0;
LABEL_33:
      if ( v12 )
      {
        v23 = v7->Ptr;
        if ( v11 > 0x7FFFFFFE || v12 > 0x7FFFFFFF )
        {
          *v23 = v9;
        }
        else
        {
          v24 = v11;
          do
          {
            if ( !v24 )
              break;
            v25 = *v10;
            if ( !*v10 )
              break;
            ++v10;
            *v23++ = v25;
            --v24;
            --v12;
          }
          while ( v12 );
          v26 = v23 - 1;
          if ( v12 )
            v26 = v23;
          *v26 = v9;
        }
      }
      v7[1].Ptr = (PVOID)v11;
LABEL_15:
      if ( v13 < 0 )
        goto LABEL_19;
      goto LABEL_16;
    }
    v13 = -2147024882;
LABEL_32:
    if ( v13 < 0 )
      goto LABEL_19;
    goto LABEL_33;
  }
  v13 = v9;
  if ( v12 <= v21 )
    goto LABEL_32;
  v35 = v9;
  v13 = ULongLongMult(v21, 2u, &v35);
  if ( v13 < 0 )
    goto LABEL_32;
  v28 = v35;
  if ( v35 - v27 > 0x800 )
    v28 = v27 + 2048;
  if ( v12 > v28 )
    v28 = v12;
  v29 = CoTaskMemRealloc(v7->Ptr, 2 * v28);
  v9 = 0;
  if ( v29 )
  {
    v7[2].Ptr = (PVOID)v28;
    v7->Ptr = v29;
    v2 = v36;
    goto LABEL_33;
  }
LABEL_19:
  v15 = this[13].Ptr;
  v16 = v9;
  if ( v15 )
  {
    do
    {
      v17 = (__int64 *)*((_QWORD *)this[12].Ptr + v16);
      v18 = *v17;
      v19 = pv;
      v20 = (*(__int64 (__fastcall **)(__int64 *))(*v17 + 48))(v17);
      (*(void (__fastcall **)(__int64 *, _QWORD, LPVOID))(v18 + 56))(v17, v20, v19);
      ++v16;
    }
    while ( v16 < (unsigned __int64)v15 );
  }
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  if ( pv )
    CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x18001e5d0  mov     [rsp-40h+arg_0], rcx
0x18001e5d5  push    rbp
0x18001e5d6  push    rbx
0x18001e5d7  push    rsi
0x18001e5d8  push    rdi
0x18001e5d9  push    r12
0x18001e5db  push    r13
0x18001e5dd  push    r14
0x18001e5df  push    r15
0x18001e5e1  mov     rbp, rsp
0x18001e5e4  sub     rsp, 48h
0x18001e5e8  mov     rbx, rcx
0x18001e5eb  xor     edi, edi
0x18001e5ed  mov     [rbp+pv], rdi
0x18001e5f1  mov     [rbp+var_20], rdi
0x18001e5f5  mov     [rbp+var_18], rdi
0x18001e5f9  lea     r15, [rcx-88h]
0x18001e600  mov     [rbp+arg_10], r15
0x18001e604  mov     rcx, [r15+0E0h]
0x18001e60b  mov     rax, [rcx]
0x18001e60e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001e612  mov     [rbp+var_20], rsi
0x18001e616  mov     [rbp+var_18], rsi
0x18001e61a  lea     rdx, [rbp+pv]
0x18001e61e  mov     rax, [rax+108h]
0x18001e625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e62a  mov     rcx, [rbp+40h]; this
0x18001e62e  test    eax, eax
0x18001e630  js      loc_18001E817
0x18001e636  lea     r13, [rbx-8]
0x18001e63a  mov     rcx, r13; SRWLock
0x18001e63d  call    cs:__imp_AcquireSRWLockExclusive
0x18001e643  mov     [rbp+arg_18], r13
0x18001e647  lea     rdi, [rbx+40h]
0x18001e64b  mov     rax, [rbp+var_20]
0x18001e64f  xor     r10d, r10d
0x18001e652  cmp     rax, rsi
0x18001e655  jnz     short loc_18001E671
0x18001e657  mov     rcx, [rbp+pv]
0x18001e65b  test    rcx, rcx
0x18001e65e  jz      loc_18001E830
0x18001e664  mov     rax, rsi
0x18001e667  inc     rax
0x18001e66a  cmp     [rcx+rax*2], r10w
0x18001e66f  jnz     short loc_18001E667
0x18001e671  mov     r12, [rbp+pv]
0x18001e675  test    r12, r12
0x18001e678  jz      loc_18001E807
0x18001e67e  mov     r14, rsi
0x18001e681  inc     r14
0x18001e684  cmp     [r12+r14*2], r10w
0x18001e689  jnz     short loc_18001E681
0x18001e68b  cmp     rax, rsi
0x18001e68e  jz      loc_18001E7F8
0x18001e694  cmp     rax, r14
0x18001e697  cmovb   r14, rax
0x18001e69b  lea     rsi, [rax+1]
0x18001e69f  cmp     rsi, rax
0x18001e6a2  jnb     loc_18001E73F
0x18001e6a8  mov     ebx, 80070216h
0x18001e6ad  test    ebx, ebx
0x18001e6af  js      short loc_18001E6CA
0x18001e6b1  lea     rdx, pszDefault
0x18001e6b8  cmp     [rdi], r10
0x18001e6bb  cmovnz  rdx, [rdi]; unsigned __int16 *
0x18001e6bf  mov     rcx, r15; this
0x18001e6c2  call    ?_GenerateNameAndAutomationPropertyString@CTitleBarElementBase@@IEAAXPEBG@Z; CTitleBarElementBase::_GenerateNameAndAutomationPropertyString(ushort const *)
0x18001e6c7  xor     r10d, r10d
0x18001e6ca  mov     r12, [rbp+arg_0]
0x18001e6ce  mov     r14, [r12+68h]
0x18001e6d3  mov     r15, r10
0x18001e6d6  test    r14, r14
0x18001e6d9  jz      short loc_18001E710
0x18001e6db  mov     rax, [r12+60h]
0x18001e6e0  mov     rsi, [rax+r15*8]
0x18001e6e4  mov     rbx, [rsi]
0x18001e6e7  mov     rdi, [rbp+pv]
0x18001e6eb  mov     rcx, rsi
0x18001e6ee  mov     rax, [rbx+30h]
0x18001e6f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6f7  mov     r8, rdi
0x18001e6fa  mov     edx, eax
0x18001e6fc  mov     rcx, rsi
0x18001e6ff  mov     rax, [rbx+38h]
0x18001e703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e708  inc     r15
0x18001e70b  cmp     r15, r14
0x18001e70e  jb      short loc_18001E6DB
0x18001e710  test    r13, r13
0x18001e713  jz      short loc_18001E71F
0x18001e715  mov     rcx, r13; SRWLock
0x18001e718  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e71e  nop
0x18001e71f  mov     rcx, [rbp+pv]; pv
0x18001e723  test    rcx, rcx
0x18001e726  jz      short loc_18001E72E
0x18001e728  call    cs:__imp_CoTaskMemFree
0x18001e72e  add     rsp, 48h
0x18001e732  pop     r15
0x18001e734  pop     r14
0x18001e736  pop     r13
0x18001e738  pop     r12
0x18001e73a  pop     rdi
0x18001e73b  pop     rsi
0x18001e73c  pop     rbx
0x18001e73d  pop     rbp
0x18001e73e  retn
0x18001e73f  mov     r9, [rdi+10h]
0x18001e743  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18001e747  jz      loc_18001E83E
0x18001e74d  mov     eax, 2
0x18001e752  test    r9, r9
0x18001e755  jnz     short loc_18001E788
0x18001e757  mul     rsi
0x18001e75a  test    rdx, rdx
0x18001e75d  jnz     loc_18001E6A8
0x18001e763  mov     rcx, rax; cb
0x18001e766  call    cs:__imp_CoTaskMemAlloc
0x18001e76c  xor     r10d, r10d
0x18001e76f  test    rax, rax
0x18001e772  jz      loc_18001E800
0x18001e778  mov     [rdi+10h], rsi
0x18001e77c  mov     [rdi], rax
0x18001e77f  mov     [rax], r10w
0x18001e783  mov     ebx, r10d
0x18001e786  jmp     short loc_18001E79C
0x18001e788  mov     ebx, r10d
0x18001e78b  cmp     rsi, r9
0x18001e78e  ja      loc_18001E860
0x18001e794  test    ebx, ebx
0x18001e796  js      loc_18001E6CA
0x18001e79c  test    rsi, rsi
0x18001e79f  jz      short loc_18001E7EF
0x18001e7a1  mov     rdx, [rdi]
0x18001e7a4  cmp     r14, 7FFFFFFEh
0x18001e7ab  ja      loc_18001E838
0x18001e7b1  cmp     rsi, 7FFFFFFFh
0x18001e7b8  ja      short loc_18001E838
0x18001e7ba  mov     rax, r14
0x18001e7bd  test    rax, rax
0x18001e7c0  jz      short loc_18001E7E0
0x18001e7c2  movzx   ecx, word ptr [r12]
0x18001e7c7  test    cx, cx
0x18001e7ca  jz      short loc_18001E7E0
0x18001e7cc  add     r12, 2
0x18001e7d0  mov     [rdx], cx
0x18001e7d3  add     rdx, 2
0x18001e7d7  dec     rax
0x18001e7da  sub     rsi, 1
0x18001e7de  jnz     short loc_18001E7BD
0x18001e7e0  lea     rcx, [rdx-2]
0x18001e7e4  test    rsi, rsi
0x18001e7e7  cmovnz  rcx, rdx
0x18001e7eb  mov     [rcx], r10w
0x18001e7ef  mov     [rdi+8], r14
0x18001e7f3  jmp     loc_18001E6AD
0x18001e7f8  mov     rax, r14
0x18001e7fb  jmp     loc_18001E69B
0x18001e800  mov     ebx, 8007000Eh
0x18001e805  jmp     short loc_18001E794
0x18001e807  mov     rcx, rdi
0x18001e80a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001e80f  xor     r10d, r10d
0x18001e812  jmp     loc_18001E6B1
0x18001e817  mov     r9d, eax; char *
0x18001e81a  lea     r8, aPcshellShellAp_6; "pcshell\\shell\\applicationframe\\frame"...
0x18001e821  mov     edx, 42Fh; void *
0x18001e826  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e82b  jmp     loc_18001E636
0x18001e830  mov     rax, r10
0x18001e833  jmp     loc_18001E671
0x18001e838  mov     [rdx], r10w
0x18001e83c  jmp     short loc_18001E7EF
0x18001e83e  mov     rcx, rdi
0x18001e841  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18001e846  cmp     [rdi], r10
0x18001e849  jz      short loc_18001E854
0x18001e84b  mov     r9, [rdi+8]
0x18001e84f  inc     r9
0x18001e852  jmp     short loc_18001E857
0x18001e854  mov     r9, r10
0x18001e857  mov     [rdi+10h], r9
0x18001e85b  jmp     loc_18001E74D
0x18001e860  mov     [rbp+arg_8], r10
0x18001e864  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x18001e868  mov     rdx, rax; unsigned __int64
0x18001e86b  mov     rcx, r9; unsigned __int64
0x18001e86e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001e873  mov     ebx, eax
0x18001e875  test    eax, eax
0x18001e877  js      loc_18001E794
0x18001e87d  mov     r15, [rbp+arg_8]
0x18001e881  mov     rcx, r15
0x18001e884  sub     rcx, r9
0x18001e887  cmp     rcx, 800h
0x18001e88e  jbe     short loc_18001E897
0x18001e890  lea     r15, [r9+800h]
0x18001e897  cmp     rsi, r15
0x18001e89a  cmova   r15, rsi
0x18001e89e  lea     rdx, [r15+r15]; cb
0x18001e8a2  mov     rcx, [rdi]; pv
0x18001e8a5  call    cs:__imp_CoTaskMemRealloc
0x18001e8ab  xor     r10d, r10d
0x18001e8ae  test    rax, rax
0x18001e8b1  jz      loc_18001E6CA
0x18001e8b7  mov     [rdi+10h], r15
0x18001e8bb  mov     [rdi], rax
0x18001e8be  mov     r15, [rbp+arg_10]
0x18001e8c2  jmp     loc_18001E79C
```
