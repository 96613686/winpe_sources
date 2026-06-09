# SystemEffectDescriptor::GetSystemEffectClsidsForMode(_GUID,SED_DISCOVERYSTATE,uint *,_GUID * *,SED_RESOLVEOPT)

- ea: `0x1800259e0`
- end: `0x180025d04`
- name: `?GetSystemEffectClsidsForMode@SystemEffectDescriptor@@QEAAJU_GUID@@W4SED_DISCOVERYSTATE@@PEAIPEAPEAU2@W4SED_RESOLVEOPT@@@Z`
- size: `804`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003e6d0`
- `0x180098c54`

## callees

- `0x18001280c`
- `0x1800237e0`
- `0x180024094`
- `0x1800259e0`
- `0x1800ce75c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025c4e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025c4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025b81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025ccd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025b81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025ccd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025ce7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025cfd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025ce7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025cfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025b26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025b26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025c03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025c03`

## string_xrefs

- `0x180025bef`: `avcore\audiocore\server\lib\audioserviceutil\systemeffect.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemEffectDescriptor::GetSystemEffectClsidsForMode(
        __int64 a1,
        __m128i *a2,
        int a3,
        _DWORD *a4,
        _QWORD *a5,
        int a6)
{
  unsigned __int64 v9; // xmm0_8
  __int64 v10; // r15
  int i; // esi
  __int64 v12; // r14
  __int64 v13; // r8
  int k; // edx
  __int64 v15; // r9
  int m; // eax
  _QWORD *v17; // r8
  unsigned __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdi
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  void *v23; // rax
  void *v24; // rbx
  int n; // eax
  _QWORD *v27; // r8
  __int64 v28; // rcx
  int j; // eax
  _QWORD *v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rsi
  __int64 v33; // rax
  SystemEffectChainDescriptor *v34; // rcx
  std::_Ref_count_base *v35; // rsi
  __m128i v36; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v36 = *a2;
  v9 = _mm_srli_si128(*a2, 8).m128i_u64[0];
  v10 = a2->m128i_i64[0];
  if ( a6 )
    goto LABEL_7;
  for ( i = 0; ; ++i )
  {
    if ( i >= *(_DWORD *)(a1 + 40) )
      goto LABEL_7;
    if ( i < 0 )
      goto LABEL_66;
    v12 = 2LL * i;
    v13 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 16LL * i);
    if ( *(_BYTE *)(v13 + 20) )
    {
      for ( j = 0; ; ++j )
      {
        if ( j >= *(_DWORD *)(v13 + 8) )
          goto LABEL_6;
        v30 = (_QWORD *)(*(_QWORD *)v13 + 16LL * j);
        v31 = *v30 - v36.m128i_i64[0];
        if ( *v30 == v36.m128i_i64[0] )
          v31 = v30[1] - v9;
        if ( !v31 )
          break;
      }
      if ( j != -1 )
        break;
    }
LABEL_6:
    ;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  if ( i >= *(_DWORD *)(a1 + 40) )
    goto LABEL_67;
  v32 = *(_QWORD *)(a1 + 32);
  v33 = *(_QWORD *)(v32 + 8 * v12 + 8);
  if ( v33 )
    _InterlockedIncrement((volatile signed __int32 *)(v33 + 8));
  v34 = *(SystemEffectChainDescriptor **)(v32 + 8 * v12);
  v35 = *(std::_Ref_count_base **)(v32 + 8 * v12 + 8);
  if ( (int)SystemEffectChainDescriptor::Resolve(v34, (struct SystemEffectDescriptor *)a1) >= 0 )
  {
    if ( v35 )
      std::_Ref_count_base::_Decref(v35);
    if ( a1 != -56 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
LABEL_7:
    for ( k = 0; ; ++k )
    {
      if ( k >= *(_DWORD *)(a1 + 40) )
        goto LABEL_33;
      if ( k < 0 )
        goto LABEL_66;
      v15 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 16LL * k);
      for ( m = 0; ; ++m )
      {
        if ( m >= *(_DWORD *)(v15 + 8) )
          goto LABEL_32;
        v17 = (_QWORD *)(*(_QWORD *)v15 + 16LL * m);
        v18 = *v17 - v10;
        if ( *v17 == v10 )
          v18 = v17[1] - v9;
        if ( !v18 )
          break;
      }
      if ( m != -1 )
        break;
LABEL_32:
      ;
    }
    if ( k < *(_DWORD *)(a1 + 40) )
    {
      v19 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 16LL * (unsigned int)k);
      if ( v19 )
        goto LABEL_18;
      goto LABEL_35;
    }
LABEL_66:
    RaiseException(0xC000008C, 1u, 0, 0);
LABEL_67:
    RaiseException(0xC000008C, 1u, 0, 0);
    JUMPOUT(0x180025D03LL);
  }
  if ( v35 )
    std::_Ref_count_base::_Decref(v35);
  if ( a1 != -56 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
LABEL_33:
  v19 = *(_QWORD *)(a1 + 16);
  if ( v19 )
  {
    for ( n = 0; n < *(_DWORD *)(v19 + 8); ++n )
    {
      v27 = (_QWORD *)(*(_QWORD *)v19 + 16LL * n);
      v28 = *v27 - v36.m128i_i64[0];
      if ( *v27 == v36.m128i_i64[0] )
        v28 = v27[1] - v36.m128i_i64[1];
      if ( !v28 )
      {
        if ( n != -1 )
          goto LABEL_18;
        break;
      }
    }
  }
  v19 = 0;
LABEL_35:
  if ( a3 == 1 )
    v19 = *(_QWORD *)(a1 + 16);
LABEL_18:
  *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( !v19 )
    return 0;
  v20 = v19 + 56;
  if ( a3 != 1 )
    v20 = v19 + 40;
  if ( !a5 || *(int *)(v20 + 8) <= 0 )
  {
LABEL_29:
    *a4 = *(_DWORD *)(v20 + 8);
    return 0;
  }
  v21 = *(int *)(v20 + 8);
  if ( 0xFFFFFFFFFFFFFFFFuLL / v21 < 0x10 || (v22 = 16 * v21, v22 > 0x7FFFFFFF) )
  {
    v24 = 0;
  }
  else
  {
    v23 = CoTaskMemAlloc((unsigned int)v22);
    v24 = v23;
    if ( v23 )
    {
      memcpy_0(v23, *(const void **)v20, 16LL * *(int *)(v20 + 8));
      *a5 = v24;
      CoTaskMemFree(0);
      goto LABEL_29;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x270,
    (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\systemeffect.cpp",
    (const char *)0x8007000ELL,
    v36.m128i_i32[0]);
  CoTaskMemFree(v24);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800259e0  push    rbx
0x1800259e2  push    rbp
0x1800259e3  push    rsi
0x1800259e4  push    rdi
0x1800259e5  push    r12
0x1800259e7  push    r13
0x1800259e9  push    r14
0x1800259eb  push    r15
0x1800259ed  sub     rsp, 48h
0x1800259f1  mov     r13, r9
0x1800259f4  mov     r12d, r8d
0x1800259f7  mov     rdi, rcx
0x1800259fa  movaps  xmm0, xmmword ptr [rdx]
0x1800259fd  movdqa  xmmword ptr [rsp+88h+var_68], xmm0; int
0x180025a03  movaps  xmm1, xmm0
0x180025a06  psrldq  xmm0, 8
0x180025a0b  movq    rbp, xmm0
0x180025a10  movq    r15, xmm1
0x180025a15  cmp     [rsp+88h+arg_28], 0
0x180025a1d  jnz     short loc_180025A4B
0x180025a1f  xor     esi, esi
0x180025a21  cmp     esi, [rdi+28h]
0x180025a24  jge     short loc_180025A4B
0x180025a26  test    esi, esi
0x180025a28  js      loc_180025CD8
0x180025a2e  movsxd  r14, esi
0x180025a31  add     r14, r14
0x180025a34  mov     rax, [rdi+20h]
0x180025a38  mov     r8, [rax+r14*8]
0x180025a3c  cmp     byte ptr [r8+14h], 0
0x180025a41  jnz     loc_180025C10
0x180025a47  inc     esi
0x180025a49  jmp     short loc_180025A21
0x180025a4b  xor     edx, edx
0x180025a4d  cmp     edx, [rdi+28h]
0x180025a50  jge     loc_180025B87
0x180025a56  test    edx, edx
0x180025a58  js      loc_180025CD8
0x180025a5e  movsxd  rcx, edx
0x180025a61  add     rcx, rcx
0x180025a64  mov     rax, [rdi+20h]
0x180025a68  mov     r9, [rax+rcx*8]
0x180025a6c  xor     eax, eax
0x180025a6e  cmp     eax, [r9+8]
0x180025a72  jge     loc_180025B77
0x180025a78  movsxd  r8, eax
0x180025a7b  shl     r8, 4
0x180025a7f  add     r8, [r9]
0x180025a82  mov     rcx, [r8]
0x180025a85  sub     rcx, r15
0x180025a88  jnz     short loc_180025A91
0x180025a8a  mov     rcx, [r8+8]
0x180025a8e  sub     rcx, rbp
0x180025a91  test    rcx, rcx
0x180025a94  jnz     loc_180025B70
0x180025a9a  cmp     eax, 0FFFFFFFFh
0x180025a9d  jz      loc_180025B77
0x180025aa3  cmp     edx, [rdi+28h]
0x180025aa6  jge     loc_180025CD8
0x180025aac  mov     ecx, edx
0x180025aae  add     rcx, rcx
0x180025ab1  mov     rax, [rdi+20h]
0x180025ab5  mov     rdx, [rax+rcx*8]
0x180025ab9  test    rdx, rdx
0x180025abc  jz      loc_180025B92
0x180025ac2  mov     dword ptr [r13+0], 0
0x180025aca  mov     rsi, [rsp+88h+arg_20]
0x180025ad2  test    rsi, rsi
0x180025ad5  jz      short loc_180025ADE
0x180025ad7  mov     qword ptr [rsi], 0
0x180025ade  test    rdx, rdx
0x180025ae1  jz      short loc_180025B5D
0x180025ae3  cmp     r12d, 1
0x180025ae7  lea     rdi, [rdx+38h]
0x180025aeb  jz      short loc_180025AF1
0x180025aed  lea     rdi, [rdx+28h]
0x180025af1  test    rsi, rsi
0x180025af4  jz      short loc_180025B56
0x180025af6  cmp     dword ptr [rdi+8], 0
0x180025afa  jle     short loc_180025B56
0x180025afc  movsxd  rcx, dword ptr [rdi+8]
0x180025b00  xor     edx, edx
0x180025b02  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025b06  div     rcx
0x180025b09  cmp     rax, 10h
0x180025b0d  jb      loc_180025BDD
0x180025b13  shl     rcx, 4
0x180025b17  cmp     rcx, 7FFFFFFFh
0x180025b1e  ja      loc_180025BDD
0x180025b24  mov     ecx, ecx; cb
0x180025b26  call    cs:__imp_CoTaskMemAlloc
0x180025b2c  mov     rbx, rax
0x180025b2f  test    rax, rax
0x180025b32  jz      loc_180025BDF
0x180025b38  movsxd  r8, dword ptr [rdi+8]
0x180025b3c  shl     r8, 4; Size
0x180025b40  mov     rdx, [rdi]; Src
0x180025b43  mov     rcx, rax; void *
0x180025b46  call    memcpy_0
0x180025b4b  mov     [rsi], rbx
0x180025b4e  xor     ecx, ecx; pv
0x180025b50  call    cs:__imp_CoTaskMemFree
0x180025b56  mov     eax, [rdi+8]
0x180025b59  mov     [r13+0], eax
0x180025b5d  xor     eax, eax
0x180025b5f  add     rsp, 48h
0x180025b63  pop     r15
0x180025b65  pop     r14
0x180025b67  pop     r13
0x180025b69  pop     r12
0x180025b6b  pop     rdi
0x180025b6c  pop     rsi
0x180025b6d  pop     rbp
0x180025b6e  pop     rbx
0x180025b6f  retn
0x180025b70  inc     eax
0x180025b72  jmp     loc_180025A6E
0x180025b77  inc     edx
0x180025b79  jmp     loc_180025A4D
0x180025b7e  mov     rcx, rbx; lpCriticalSection
0x180025b81  call    cs:__imp_LeaveCriticalSection
0x180025b87  mov     rdx, [rdi+10h]
0x180025b8b  test    rdx, rdx
0x180025b8e  jnz     short loc_180025BA5
0x180025b90  xor     edx, edx
0x180025b92  cmp     r12d, 1
0x180025b96  jnz     loc_180025AC2
0x180025b9c  mov     rdx, [rdi+10h]
0x180025ba0  jmp     loc_180025AC2
0x180025ba5  xor     eax, eax
0x180025ba7  cmp     eax, [rdx+8]
0x180025baa  jge     short loc_180025B90
0x180025bac  movsxd  r8, eax
0x180025baf  shl     r8, 4
0x180025bb3  add     r8, [rdx]
0x180025bb6  mov     rcx, [r8]
0x180025bb9  sub     rcx, qword ptr [rsp+88h+var_68]
0x180025bbe  jnz     short loc_180025BC9
0x180025bc0  mov     rcx, [r8+8]
0x180025bc4  sub     rcx, qword ptr [rsp+88h+var_68+8]
0x180025bc9  test    rcx, rcx
0x180025bcc  jz      short loc_180025BD2
0x180025bce  inc     eax
0x180025bd0  jmp     short loc_180025BA7
0x180025bd2  cmp     eax, 0FFFFFFFFh
0x180025bd5  jnz     loc_180025AC2
0x180025bdb  jmp     short loc_180025B90
0x180025bdd  xor     ebx, ebx
0x180025bdf  mov     rcx, [rsp+88h]; this
0x180025be7  mov     edi, 8007000Eh
0x180025bec  mov     r9d, edi; char *
0x180025bef  lea     r8, aAvcoreAudiocor_31; "avcore\\audiocore\\server\\lib\\audiose"...
0x180025bf6  mov     edx, 270h; void *
0x180025bfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025c00  mov     rcx, rbx; pv
0x180025c03  call    cs:__imp_CoTaskMemFree
0x180025c09  mov     eax, edi
0x180025c0b  jmp     loc_180025B5F
0x180025c10  xor     eax, eax
0x180025c12  cmp     eax, [r8+8]
0x180025c16  jge     loc_180025A47
0x180025c1c  movsxd  rdx, eax
0x180025c1f  shl     rdx, 4
0x180025c23  add     rdx, [r8]
0x180025c26  mov     rcx, [rdx]
0x180025c29  sub     rcx, r15
0x180025c2c  jnz     short loc_180025C35
0x180025c2e  mov     rcx, [rdx+8]
0x180025c32  sub     rcx, rbp
0x180025c35  test    rcx, rcx
0x180025c38  jz      short loc_180025C3E
0x180025c3a  inc     eax
0x180025c3c  jmp     short loc_180025C12
0x180025c3e  cmp     eax, 0FFFFFFFFh
0x180025c41  jz      loc_180025A47
0x180025c47  lea     rbx, [rdi+38h]
0x180025c4b  mov     rcx, rbx; lpCriticalSection
0x180025c4e  call    cs:__imp_EnterCriticalSection
0x180025c54  mov     [rsp+88h+arg_8], rbx
0x180025c5c  cmp     esi, [rdi+28h]
0x180025c5f  jge     loc_180025CEE
0x180025c65  mov     rsi, [rdi+20h]
0x180025c69  mov     rax, [rsi+r14*8+8]
0x180025c6e  test    rax, rax
0x180025c71  jz      short loc_180025C77
0x180025c73  lock inc dword ptr [rax+8]
0x180025c77  mov     rcx, [rsi+r14*8]; this
0x180025c7b  mov     [rsp+88h+var_58], rcx
0x180025c80  mov     rsi, [rsi+r14*8+8]
0x180025c85  mov     [rsp+88h+var_50], rsi
0x180025c8a  mov     rdx, rdi; struct SystemEffectDescriptor *
0x180025c8d  call    ?Resolve@SystemEffectChainDescriptor@@IEAAJPEAVSystemEffectDescriptor@@@Z; SystemEffectChainDescriptor::Resolve(SystemEffectDescriptor *)
0x180025c92  nop
0x180025c93  test    eax, eax
0x180025c95  jns     short loc_180025CB3
0x180025c97  test    rsi, rsi
0x180025c9a  jz      short loc_180025CA5
0x180025c9c  mov     rcx, rsi; this
0x180025c9f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180025ca4  nop
0x180025ca5  test    rbx, rbx
0x180025ca8  jz      loc_180025B87
0x180025cae  jmp     loc_180025B7E
0x180025cb3  test    rsi, rsi
0x180025cb6  jz      short loc_180025CC1
0x180025cb8  mov     rcx, rsi; this
0x180025cbb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180025cc0  nop
0x180025cc1  test    rbx, rbx
0x180025cc4  jz      loc_180025A4B
0x180025cca  mov     rcx, rbx; lpCriticalSection
0x180025ccd  call    cs:__imp_LeaveCriticalSection
0x180025cd3  jmp     loc_180025A4B
0x180025cd8  xor     r9d, r9d; lpArguments
0x180025cdb  xor     r8d, r8d; nNumberOfArguments
0x180025cde  lea     edx, [r9+1]; dwExceptionFlags
0x180025ce2  mov     ecx, 0C000008Ch; dwExceptionCode
0x180025ce7  call    cs:__imp_RaiseException
0x180025ced  nop
0x180025cee  xor     r9d, r9d; lpArguments
0x180025cf1  xor     r8d, r8d; nNumberOfArguments
0x180025cf4  lea     edx, [r9+1]; dwExceptionFlags
0x180025cf8  mov     ecx, 0C000008Ch; dwExceptionCode
0x180025cfd  call    cs:__imp_RaiseException
```
