# SystemEffectDescriptor::GetSystemEffectClsidsForMode(_GUID,SED_DISCOVERYSTATE,uint *,_GUID * *,SED_RESOLVEOPT)

- ea: `0x180025890`
- end: `0x180025bb4`
- name: `?GetSystemEffectClsidsForMode@SystemEffectDescriptor@@QEAAJU_GUID@@W4SED_DISCOVERYSTATE@@PEAIPEAPEAU2@W4SED_RESOLVEOPT@@@Z`
- size: `804`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003e570`
- `0x1800994b0`

## callees

- `0x1800126bc`
- `0x180023690`
- `0x180023f44`
- `0x180025890`
- `0x1800d074c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025afe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025afe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025a31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025b7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025a31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025b7d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025b97`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025bad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025b97`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025bad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800259d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800259d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025a00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025ab3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025a00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025ab3`

## string_xrefs

- `0x180025a9f`: `avcore\audiocore\server\lib\audioserviceutil\systemeffect.cpp`

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
    JUMPOUT(0x180025BB3LL);
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
0x180025890  push    rbx
0x180025892  push    rbp
0x180025893  push    rsi
0x180025894  push    rdi
0x180025895  push    r12
0x180025897  push    r13
0x180025899  push    r14
0x18002589b  push    r15
0x18002589d  sub     rsp, 48h
0x1800258a1  mov     r13, r9
0x1800258a4  mov     r12d, r8d
0x1800258a7  mov     rdi, rcx
0x1800258aa  movaps  xmm0, xmmword ptr [rdx]
0x1800258ad  movdqa  xmmword ptr [rsp+88h+var_68], xmm0; int
0x1800258b3  movaps  xmm1, xmm0
0x1800258b6  psrldq  xmm0, 8
0x1800258bb  movq    rbp, xmm0
0x1800258c0  movq    r15, xmm1
0x1800258c5  cmp     [rsp+88h+arg_28], 0
0x1800258cd  jnz     short loc_1800258FB
0x1800258cf  xor     esi, esi
0x1800258d1  cmp     esi, [rdi+28h]
0x1800258d4  jge     short loc_1800258FB
0x1800258d6  test    esi, esi
0x1800258d8  js      loc_180025B88
0x1800258de  movsxd  r14, esi
0x1800258e1  add     r14, r14
0x1800258e4  mov     rax, [rdi+20h]
0x1800258e8  mov     r8, [rax+r14*8]
0x1800258ec  cmp     byte ptr [r8+14h], 0
0x1800258f1  jnz     loc_180025AC0
0x1800258f7  inc     esi
0x1800258f9  jmp     short loc_1800258D1
0x1800258fb  xor     edx, edx
0x1800258fd  cmp     edx, [rdi+28h]
0x180025900  jge     loc_180025A37
0x180025906  test    edx, edx
0x180025908  js      loc_180025B88
0x18002590e  movsxd  rcx, edx
0x180025911  add     rcx, rcx
0x180025914  mov     rax, [rdi+20h]
0x180025918  mov     r9, [rax+rcx*8]
0x18002591c  xor     eax, eax
0x18002591e  cmp     eax, [r9+8]
0x180025922  jge     loc_180025A27
0x180025928  movsxd  r8, eax
0x18002592b  shl     r8, 4
0x18002592f  add     r8, [r9]
0x180025932  mov     rcx, [r8]
0x180025935  sub     rcx, r15
0x180025938  jnz     short loc_180025941
0x18002593a  mov     rcx, [r8+8]
0x18002593e  sub     rcx, rbp
0x180025941  test    rcx, rcx
0x180025944  jnz     loc_180025A20
0x18002594a  cmp     eax, 0FFFFFFFFh
0x18002594d  jz      loc_180025A27
0x180025953  cmp     edx, [rdi+28h]
0x180025956  jge     loc_180025B88
0x18002595c  mov     ecx, edx
0x18002595e  add     rcx, rcx
0x180025961  mov     rax, [rdi+20h]
0x180025965  mov     rdx, [rax+rcx*8]
0x180025969  test    rdx, rdx
0x18002596c  jz      loc_180025A42
0x180025972  mov     dword ptr [r13+0], 0
0x18002597a  mov     rsi, [rsp+88h+arg_20]
0x180025982  test    rsi, rsi
0x180025985  jz      short loc_18002598E
0x180025987  mov     qword ptr [rsi], 0
0x18002598e  test    rdx, rdx
0x180025991  jz      short loc_180025A0D
0x180025993  cmp     r12d, 1
0x180025997  lea     rdi, [rdx+38h]
0x18002599b  jz      short loc_1800259A1
0x18002599d  lea     rdi, [rdx+28h]
0x1800259a1  test    rsi, rsi
0x1800259a4  jz      short loc_180025A06
0x1800259a6  cmp     dword ptr [rdi+8], 0
0x1800259aa  jle     short loc_180025A06
0x1800259ac  movsxd  rcx, dword ptr [rdi+8]
0x1800259b0  xor     edx, edx
0x1800259b2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800259b6  div     rcx
0x1800259b9  cmp     rax, 10h
0x1800259bd  jb      loc_180025A8D
0x1800259c3  shl     rcx, 4
0x1800259c7  cmp     rcx, 7FFFFFFFh
0x1800259ce  ja      loc_180025A8D
0x1800259d4  mov     ecx, ecx; cb
0x1800259d6  call    cs:__imp_CoTaskMemAlloc
0x1800259dc  mov     rbx, rax
0x1800259df  test    rax, rax
0x1800259e2  jz      loc_180025A8F
0x1800259e8  movsxd  r8, dword ptr [rdi+8]
0x1800259ec  shl     r8, 4; Size
0x1800259f0  mov     rdx, [rdi]; Src
0x1800259f3  mov     rcx, rax; void *
0x1800259f6  call    memcpy_0
0x1800259fb  mov     [rsi], rbx
0x1800259fe  xor     ecx, ecx; pv
0x180025a00  call    cs:__imp_CoTaskMemFree
0x180025a06  mov     eax, [rdi+8]
0x180025a09  mov     [r13+0], eax
0x180025a0d  xor     eax, eax
0x180025a0f  add     rsp, 48h
0x180025a13  pop     r15
0x180025a15  pop     r14
0x180025a17  pop     r13
0x180025a19  pop     r12
0x180025a1b  pop     rdi
0x180025a1c  pop     rsi
0x180025a1d  pop     rbp
0x180025a1e  pop     rbx
0x180025a1f  retn
0x180025a20  inc     eax
0x180025a22  jmp     loc_18002591E
0x180025a27  inc     edx
0x180025a29  jmp     loc_1800258FD
0x180025a2e  mov     rcx, rbx; lpCriticalSection
0x180025a31  call    cs:__imp_LeaveCriticalSection
0x180025a37  mov     rdx, [rdi+10h]
0x180025a3b  test    rdx, rdx
0x180025a3e  jnz     short loc_180025A55
0x180025a40  xor     edx, edx
0x180025a42  cmp     r12d, 1
0x180025a46  jnz     loc_180025972
0x180025a4c  mov     rdx, [rdi+10h]
0x180025a50  jmp     loc_180025972
0x180025a55  xor     eax, eax
0x180025a57  cmp     eax, [rdx+8]
0x180025a5a  jge     short loc_180025A40
0x180025a5c  movsxd  r8, eax
0x180025a5f  shl     r8, 4
0x180025a63  add     r8, [rdx]
0x180025a66  mov     rcx, [r8]
0x180025a69  sub     rcx, qword ptr [rsp+88h+var_68]
0x180025a6e  jnz     short loc_180025A79
0x180025a70  mov     rcx, [r8+8]
0x180025a74  sub     rcx, qword ptr [rsp+88h+var_68+8]
0x180025a79  test    rcx, rcx
0x180025a7c  jz      short loc_180025A82
0x180025a7e  inc     eax
0x180025a80  jmp     short loc_180025A57
0x180025a82  cmp     eax, 0FFFFFFFFh
0x180025a85  jnz     loc_180025972
0x180025a8b  jmp     short loc_180025A40
0x180025a8d  xor     ebx, ebx
0x180025a8f  mov     rcx, [rsp+88h]; this
0x180025a97  mov     edi, 8007000Eh
0x180025a9c  mov     r9d, edi; char *
0x180025a9f  lea     r8, aAvcoreAudiocor_31; "avcore\\audiocore\\server\\lib\\audiose"...
0x180025aa6  mov     edx, 270h; void *
0x180025aab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025ab0  mov     rcx, rbx; pv
0x180025ab3  call    cs:__imp_CoTaskMemFree
0x180025ab9  mov     eax, edi
0x180025abb  jmp     loc_180025A0F
0x180025ac0  xor     eax, eax
0x180025ac2  cmp     eax, [r8+8]
0x180025ac6  jge     loc_1800258F7
0x180025acc  movsxd  rdx, eax
0x180025acf  shl     rdx, 4
0x180025ad3  add     rdx, [r8]
0x180025ad6  mov     rcx, [rdx]
0x180025ad9  sub     rcx, r15
0x180025adc  jnz     short loc_180025AE5
0x180025ade  mov     rcx, [rdx+8]
0x180025ae2  sub     rcx, rbp
0x180025ae5  test    rcx, rcx
0x180025ae8  jz      short loc_180025AEE
0x180025aea  inc     eax
0x180025aec  jmp     short loc_180025AC2
0x180025aee  cmp     eax, 0FFFFFFFFh
0x180025af1  jz      loc_1800258F7
0x180025af7  lea     rbx, [rdi+38h]
0x180025afb  mov     rcx, rbx; lpCriticalSection
0x180025afe  call    cs:__imp_EnterCriticalSection
0x180025b04  mov     [rsp+88h+arg_8], rbx
0x180025b0c  cmp     esi, [rdi+28h]
0x180025b0f  jge     loc_180025B9E
0x180025b15  mov     rsi, [rdi+20h]
0x180025b19  mov     rax, [rsi+r14*8+8]
0x180025b1e  test    rax, rax
0x180025b21  jz      short loc_180025B27
0x180025b23  lock inc dword ptr [rax+8]
0x180025b27  mov     rcx, [rsi+r14*8]; this
0x180025b2b  mov     [rsp+88h+var_58], rcx
0x180025b30  mov     rsi, [rsi+r14*8+8]
0x180025b35  mov     [rsp+88h+var_50], rsi
0x180025b3a  mov     rdx, rdi; struct SystemEffectDescriptor *
0x180025b3d  call    ?Resolve@SystemEffectChainDescriptor@@IEAAJPEAVSystemEffectDescriptor@@@Z; SystemEffectChainDescriptor::Resolve(SystemEffectDescriptor *)
0x180025b42  nop
0x180025b43  test    eax, eax
0x180025b45  jns     short loc_180025B63
0x180025b47  test    rsi, rsi
0x180025b4a  jz      short loc_180025B55
0x180025b4c  mov     rcx, rsi; this
0x180025b4f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180025b54  nop
0x180025b55  test    rbx, rbx
0x180025b58  jz      loc_180025A37
0x180025b5e  jmp     loc_180025A2E
0x180025b63  test    rsi, rsi
0x180025b66  jz      short loc_180025B71
0x180025b68  mov     rcx, rsi; this
0x180025b6b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180025b70  nop
0x180025b71  test    rbx, rbx
0x180025b74  jz      loc_1800258FB
0x180025b7a  mov     rcx, rbx; lpCriticalSection
0x180025b7d  call    cs:__imp_LeaveCriticalSection
0x180025b83  jmp     loc_1800258FB
0x180025b88  xor     r9d, r9d; lpArguments
0x180025b8b  xor     r8d, r8d; nNumberOfArguments
0x180025b8e  lea     edx, [r9+1]; dwExceptionFlags
0x180025b92  mov     ecx, 0C000008Ch; dwExceptionCode
0x180025b97  call    cs:__imp_RaiseException
0x180025b9d  nop
0x180025b9e  xor     r9d, r9d; lpArguments
0x180025ba1  xor     r8d, r8d; nNumberOfArguments
0x180025ba4  lea     edx, [r9+1]; dwExceptionFlags
0x180025ba8  mov     ecx, 0C000008Ch; dwExceptionCode
0x180025bad  call    cs:__imp_RaiseException
```
