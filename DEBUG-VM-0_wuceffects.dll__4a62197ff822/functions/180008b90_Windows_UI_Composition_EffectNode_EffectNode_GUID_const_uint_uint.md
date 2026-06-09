# Windows::UI::Composition::EffectNode::EffectNode(_GUID const &,uint,uint)

- ea: `0x180008b90`
- end: `0x180008eb3`
- name: `??0EffectNode@Composition@UI@Windows@@QEAA@AEBU_GUID@@II@Z`
- size: `803`
- prototype: `__int64 __fastcall(Windows::UI::Composition::EffectNode *__hidden this, const struct _GUID *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005ce0`
- `0x180009b3c`

## callees

- `0x180004db8`
- `0x180008b90`
- `0x180008ec0`
- `0x180008ed0`
- `0x180013a70`
- `0x18001de54`
- `0x180021060`
- `0x180021cec`
- `0x18002584c`
- `0x18002b8b0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008cae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008d2c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008db7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008cae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008d2c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008db7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008ca0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008d1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008da9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008ca0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008d1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008da9`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
Windows::UI::Composition::EffectNode *__fastcall Windows::UI::Composition::EffectNode::EffectNode(
        Windows::UI::Composition::EffectNode *this,
        const struct _GUID *a2,
        int a3,
        unsigned int a4)
{
  unsigned int i; // ebx
  void ***v9; // rsi
  _QWORD *v10; // rcx
  __int64 v11; // rax
  SIZE_T v12; // r15
  unsigned int v13; // eax
  __int64 v14; // rdi
  SIZE_T v15; // rbx
  HANDLE ProcessHeap; // rax
  Windows::UI::Composition::EffectNodeInput *v17; // rax
  Windows::UI::Composition::EffectNodeInput *v18; // rsi
  Windows::UI::Composition::EffectNodeInput *v19; // rbx
  void *v20; // rcx
  HANDLE v21; // rax
  _BYTE *v22; // rax
  _BYTE *v23; // rbx
  void *v24; // rcx
  __int64 v25; // rdi
  SIZE_T v26; // rbx
  HANDLE v27; // rax
  Windows::UI::Composition::EffectPropertyFlags *v28; // rax
  Windows::UI::Composition::EffectPropertyFlags *v29; // rbx
  Windows::UI::Composition::EffectPropertyFlags *v30; // rsi
  void *v31; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  unsigned int v35; // [rsp+20h] [rbp-50h] BYREF
  Windows::UI::Composition::EffectPropertyFlags *v36; // [rsp+28h] [rbp-48h] BYREF
  Windows::UI::Composition::EffectNodeInput *v37; // [rsp+30h] [rbp-40h]
  Windows::UI::Composition::EffectNode *v38; // [rsp+38h] [rbp-38h]
  __int128 pExceptionObject; // [rsp+40h] [rbp-30h] BYREF
  __int128 v40; // [rsp+50h] [rbp-20h]

  v38 = this;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 0x1F )
    {
      pExceptionObject = 0;
      v40 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject, L"Unsupported effect type.", 24);
      Windows::UI::Composition::OriginateException(v33, (__int64 *)&pExceptionObject);
    }
    v9 = off_18003E110[i];
    v10 = (_QWORD *)((__int64 (__fastcall *)(void ***))(*v9)[1])(v9);
    v11 = *(_QWORD *)&a2->Data1 - *v10;
    if ( !v11 )
      v11 = *(_QWORD *)a2->Data4 - v10[1];
    if ( !v11 )
      break;
  }
  *(_QWORD *)this = v9;
  *((_DWORD *)this + 4) = a3;
  *((_DWORD *)this + 5) = a4;
  if ( !((unsigned __int8 (__fastcall *)(void ***, _QWORD))(*v9)[3])(v9, a4) )
  {
    std::wstring::wstring(&pExceptionObject, L"Invalid number of sources.");
    Windows::UI::Composition::OriginateException(v34, (__int64 *)&pExceptionObject);
  }
  v12 = ((unsigned int (__fastcall *)(void ***))(*v9)[17])(v9);
  v35 = 0;
  v36 = 0;
  ((void (__fastcall *)(void ***, unsigned int *, Windows::UI::Composition::EffectPropertyFlags **))(*v9)[18])(
    v9,
    &v35,
    &v36);
  v13 = *((_DWORD *)this + 5);
  if ( v13 )
  {
    v14 = v13;
    v36 = (Windows::UI::Composition::EffectPropertyFlags *)*((unsigned int *)this + 5);
    v15 = 8LL * v13;
    if ( !is_mul_ok(v13, 8u) )
      v15 = -1;
    ProcessHeap = GetProcessHeap();
    v17 = (Windows::UI::Composition::EffectNodeInput *)HeapAlloc(ProcessHeap, 0, v15);
    v18 = v17;
    if ( !v17 )
    {
      *(_QWORD *)&v40 = 0;
      *((_QWORD *)&pExceptionObject + 1) = "bad allocation";
      *(_QWORD *)&pExceptionObject = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)&pExceptionObject;
    }
    v37 = v17;
    v19 = v17;
    do
    {
      Windows::UI::Composition::EffectNodeInput::EffectNodeInput(v19);
      v19 = (Windows::UI::Composition::EffectNodeInput *)((char *)v19 + 8);
      --v14;
    }
    while ( v14 );
    v20 = (void *)*((_QWORD *)this + 1);
    *((_QWORD *)this + 1) = v18;
    if ( v20 )
      operator delete(v20);
  }
  if ( (_DWORD)v12 )
  {
    v21 = GetProcessHeap();
    v22 = HeapAlloc(v21, 0, v12);
    v23 = v22;
    if ( !v22 )
    {
      *(_QWORD *)&v40 = 0;
      *((_QWORD *)&pExceptionObject + 1) = "bad allocation";
      *(_QWORD *)&pExceptionObject = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)&pExceptionObject;
    }
    memset_0(v22, 0, v12);
    *v23 = 0;
    v24 = (void *)*((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = v23;
    if ( v24 )
      operator delete(v24);
  }
  if ( v35 )
  {
    v25 = v35;
    v37 = (Windows::UI::Composition::EffectNodeInput *)v35;
    v26 = 2LL * v35;
    if ( !is_mul_ok(v35, 2u) )
      v26 = -1;
    v27 = GetProcessHeap();
    v28 = (Windows::UI::Composition::EffectPropertyFlags *)HeapAlloc(v27, 0, v26);
    v29 = v28;
    if ( !v28 )
    {
      *(_QWORD *)&v40 = 0;
      *((_QWORD *)&pExceptionObject + 1) = "bad allocation";
      *(_QWORD *)&pExceptionObject = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)&pExceptionObject;
    }
    v36 = v28;
    v30 = v28;
    do
    {
      Windows::UI::Composition::EffectPropertyFlags::EffectPropertyFlags(v30);
      v30 = (Windows::UI::Composition::EffectPropertyFlags *)((char *)v30 + 2);
      --v25;
    }
    while ( v25 );
    v31 = (void *)*((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = v29;
    if ( v31 )
      operator delete(v31);
  }
  return this;
}

```

## disassembly

```asm
0x180008b90  mov     [rsp-38h+arg_8], rbx
0x180008b95  push    rbp
0x180008b96  push    rsi
0x180008b97  push    rdi
0x180008b98  push    r12
0x180008b9a  push    r13
0x180008b9c  push    r14
0x180008b9e  push    r15
0x180008ba0  mov     rbp, rsp
0x180008ba3  sub     rsp, 70h
0x180008ba7  mov     rax, cs:__security_cookie
0x180008bae  xor     rax, rsp
0x180008bb1  mov     [rbp+var_10], rax
0x180008bb5  mov     r15d, r9d
0x180008bb8  mov     r12d, r8d
0x180008bbb  mov     rdi, rdx
0x180008bbe  mov     r14, rcx
0x180008bc1  mov     [rbp+var_38], rcx
0x180008bc5  xor     eax, eax
0x180008bc7  mov     [rcx+8], rax
0x180008bcb  mov     [rcx+18h], rax
0x180008bcf  mov     [rcx+20h], rax
0x180008bd3  mov     ebx, eax
0x180008bd5  lea     r13, off_18003E110
0x180008bdc  nop     dword ptr [rax+00h]
0x180008be0  cmp     ebx, 1Fh
0x180008be3  jnb     loc_180008E49
0x180008be9  mov     eax, ebx
0x180008beb  mov     rsi, [r13+rax*8+0]
0x180008bf0  mov     rax, [rsi]
0x180008bf3  mov     rcx, rsi
0x180008bf6  mov     rax, [rax+8]
0x180008bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bff  mov     rcx, rax
0x180008c02  mov     rax, [rdi]
0x180008c05  sub     rax, [rcx]
0x180008c08  jnz     short loc_180008C12
0x180008c0a  mov     rax, [rdi+8]
0x180008c0e  sub     rax, [rcx+8]
0x180008c12  test    rax, rax
0x180008c15  jz      short loc_180008C1B
0x180008c17  inc     ebx
0x180008c19  jmp     short loc_180008BE0
0x180008c1b  mov     [r14], rsi
0x180008c1e  mov     [r14+10h], r12d
0x180008c22  mov     [r14+14h], r15d
0x180008c26  mov     rax, [rsi]
0x180008c29  mov     edx, r15d
0x180008c2c  mov     rcx, rsi
0x180008c2f  mov     rax, [rax+18h]
0x180008c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c38  test    al, al
0x180008c3a  jz      loc_180008E79
0x180008c40  mov     rax, [rsi]
0x180008c43  mov     rcx, rsi
0x180008c46  mov     rax, [rax+88h]
0x180008c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c52  mov     r15d, eax
0x180008c55  xor     eax, eax
0x180008c57  mov     [rbp+var_50], eax
0x180008c5a  mov     [rbp+var_48], rax
0x180008c5e  mov     rax, [rsi]
0x180008c61  lea     r8, [rbp+var_48]
0x180008c65  lea     rdx, [rbp+var_50]
0x180008c69  mov     rcx, rsi
0x180008c6c  mov     rax, [rax+90h]
0x180008c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c78  mov     eax, [r14+14h]
0x180008c7c  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180008c83  test    eax, eax
0x180008c85  jz      loc_180008D19
0x180008c8b  mov     edi, eax
0x180008c8d  mov     [rbp+var_48], rax
0x180008c91  mov     eax, 8
0x180008c96  mul     rdi
0x180008c99  mov     rbx, rax
0x180008c9c  cmovb   rbx, r12
0x180008ca0  call    cs:__imp_GetProcessHeap
0x180008ca6  mov     rcx, rax; hHeap
0x180008ca9  mov     r8, rbx; dwBytes
0x180008cac  xor     edx, edx; dwFlags
0x180008cae  call    cs:__imp_HeapAlloc
0x180008cb4  mov     rsi, rax
0x180008cb7  test    rax, rax
0x180008cba  jnz     short loc_180008CEA
0x180008cbc  xorps   xmm0, xmm0
0x180008cbf  movups  [rbp+pExceptionObject+8], xmm0
0x180008cc3  lea     rax, aBadAllocation; "bad allocation"
0x180008cca  mov     qword ptr [rbp+pExceptionObject+8], rax
0x180008cce  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180008cd5  mov     qword ptr [rbp+pExceptionObject], rax
0x180008cd9  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180008ce0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180008ce4  call    _CxxThrowException_0
0x180008cea  mov     [rbp+var_40], rsi
0x180008cee  mov     rbx, rsi
0x180008cf1  test    rdi, rdi
0x180008cf4  jz      short loc_180008D08
0x180008cf6  mov     rcx, rbx; this
0x180008cf9  call    ??0EffectNodeInput@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::EffectNodeInput::EffectNodeInput(void)
0x180008cfe  add     rbx, 8
0x180008d02  sub     rdi, 1
0x180008d06  jnz     short loc_180008CF6
0x180008d08  mov     rcx, [r14+8]; lpMem
0x180008d0c  mov     [r14+8], rsi
0x180008d10  test    rcx, rcx
0x180008d13  jnz     loc_180008E94
0x180008d19  test    r15d, r15d
0x180008d1c  jz      short loc_180008D89
0x180008d1e  call    cs:__imp_GetProcessHeap
0x180008d24  mov     rcx, rax; hHeap
0x180008d27  mov     r8, r15; dwBytes
0x180008d2a  xor     edx, edx; dwFlags
0x180008d2c  call    cs:__imp_HeapAlloc
0x180008d32  mov     rbx, rax
0x180008d35  test    rax, rax
0x180008d38  jnz     short loc_180008D68
0x180008d3a  xorps   xmm0, xmm0
0x180008d3d  movups  [rbp+pExceptionObject+8], xmm0
0x180008d41  lea     rax, aBadAllocation; "bad allocation"
0x180008d48  mov     qword ptr [rbp+pExceptionObject+8], rax
0x180008d4c  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180008d53  mov     qword ptr [rbp+pExceptionObject], rax
0x180008d57  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180008d5e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180008d62  call    _CxxThrowException_0
0x180008d68  mov     r8, r15; Size
0x180008d6b  xor     edx, edx; Val
0x180008d6d  mov     rcx, rbx; void *
0x180008d70  call    memset_0
0x180008d75  mov     byte ptr [rbx], 0
0x180008d78  mov     rcx, [r14+18h]; lpMem
0x180008d7c  mov     [r14+18h], rbx
0x180008d80  test    rcx, rcx
0x180008d83  jnz     loc_180008E9E
0x180008d89  mov     eax, [rbp+var_50]
0x180008d8c  test    eax, eax
0x180008d8e  jz      loc_180008E22
0x180008d94  mov     edi, eax
0x180008d96  mov     [rbp+var_40], rax
0x180008d9a  mov     eax, 2
0x180008d9f  mul     rdi
0x180008da2  mov     rbx, rax
0x180008da5  cmovb   rbx, r12
0x180008da9  call    cs:__imp_GetProcessHeap
0x180008daf  mov     rcx, rax; hHeap
0x180008db2  mov     r8, rbx; dwBytes
0x180008db5  xor     edx, edx; dwFlags
0x180008db7  call    cs:__imp_HeapAlloc
0x180008dbd  mov     rbx, rax
0x180008dc0  test    rax, rax
0x180008dc3  jnz     short loc_180008DF3
0x180008dc5  xorps   xmm0, xmm0
0x180008dc8  movups  [rbp+pExceptionObject+8], xmm0
0x180008dcc  lea     rax, aBadAllocation; "bad allocation"
0x180008dd3  mov     qword ptr [rbp+pExceptionObject+8], rax
0x180008dd7  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180008dde  mov     qword ptr [rbp+pExceptionObject], rax
0x180008de2  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180008de9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180008ded  call    _CxxThrowException_0
0x180008df3  mov     [rbp+var_48], rbx
0x180008df7  mov     rsi, rbx
0x180008dfa  test    rdi, rdi
0x180008dfd  jz      short loc_180008E11
0x180008dff  mov     rcx, rsi; this
0x180008e02  call    ??0EffectPropertyFlags@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::EffectPropertyFlags::EffectPropertyFlags(void)
0x180008e07  add     rsi, 2
0x180008e0b  sub     rdi, 1
0x180008e0f  jnz     short loc_180008DFF
0x180008e11  mov     rcx, [r14+20h]; lpMem
0x180008e15  mov     [r14+20h], rbx
0x180008e19  test    rcx, rcx
0x180008e1c  jnz     loc_180008EA8
0x180008e22  mov     rax, r14
0x180008e25  mov     rcx, [rbp+var_10]
0x180008e29  xor     rcx, rsp; StackCookie
0x180008e2c  call    __security_check_cookie
0x180008e31  mov     rbx, [rsp+70h+arg_8]
0x180008e39  add     rsp, 70h
0x180008e3d  pop     r15
0x180008e3f  pop     r14
0x180008e41  pop     r13
0x180008e43  pop     r12
0x180008e45  pop     rdi
0x180008e46  pop     rsi
0x180008e47  pop     rbp
0x180008e48  retn
0x180008e49  xorps   xmm0, xmm0
0x180008e4c  movups  [rbp+pExceptionObject], xmm0
0x180008e50  xorps   xmm1, xmm1
0x180008e53  movdqu  [rbp+var_20], xmm1
0x180008e58  mov     r8d, 18h
0x180008e5e  lea     rdx, aUnsupportedEff; "Unsupported effect type."
0x180008e65  lea     rcx, [rbp+pExceptionObject]
0x180008e69  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180008e6e  nop
0x180008e6f  lea     rdx, [rbp+pExceptionObject]
0x180008e73  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x180008e79  lea     rdx, aInvalidNumberO; "Invalid number of sources."
0x180008e80  lea     rcx, [rbp+pExceptionObject]
0x180008e84  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180008e89  nop
0x180008e8a  lea     rdx, [rbp+pExceptionObject]
0x180008e8e  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x180008e94  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008e99  jmp     loc_180008D19
0x180008e9e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008ea3  jmp     loc_180008D89
0x180008ea8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008ead  jmp     loc_180008E22
```
