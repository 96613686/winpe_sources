# Mso::Logging::ReentrantLoggerDecorator::FlushDeferredTraces(void)

- ea: `0x180014e40`
- end: `0x18001543d`
- name: `?FlushDeferredTraces@ReentrantLoggerDecorator@Logging@Mso@@AEAAXXZ`
- size: `1533`
- prototype: `void __fastcall(Mso::Logging::ReentrantLoggerDecorator *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800146c0`
- `0x180015518`
- `0x180015c90`

## callees

- `0x180004544`
- `0x1800045ec`
- `0x18000dd50`
- `0x180014e40`
- `0x180015440`
- `0x1800266e0`
- `0x18002b3c0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800153f0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001540a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180015420`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180015436`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800153f0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001540a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180015420`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180015436`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001514c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001520c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001529c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001514c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001520c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001529c`

## string_xrefs

- `0x180014f38`: `The following traces were triggered while servicing this thread's previous trace.`
- `0x180015388`: `Traces triggered while servicing this thread's previous deferred traces were discarded.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Mso::Logging::ReentrantLoggerDecorator::FlushDeferredTraces(
        Mso::Logging::ReentrantLoggerDecorator *this)
{
  __int64 v2; // r15
  __int64 v3; // rax
  char v4; // bl
  __int64 v5; // rax
  __int64 *v6; // rcx
  __int64 v7; // rax
  _QWORD *v8; // rax
  __m128i si128; // xmm6
  __m128i v10; // xmm7
  __int64 v11; // rbx
  __int64 v12; // rax
  _QWORD *v13; // rdx
  _QWORD *v14; // rsi
  _QWORD *v15; // rdi
  volatile signed __int32 *v17; // rdi
  __int64 v18; // rbx
  __int64 *v19; // rsi
  __int64 v20; // rax
  void (__fastcall *v21)(__int64 *, __int64 *, __int128 *); // rbx
  __int128 *v22; // rdx
  __int128 *v23; // r8
  void *v24; // rcx
  void (__fastcall *v25)(__int64 *, __int64 *, __int128 *, __int64); // r12
  __int64 v26; // rbx
  __int128 *v27; // rdx
  __int128 *v28; // r8
  void *v29; // rcx
  void *v30; // rcx
  volatile signed __int32 *v31; // rbx
  __int64 v32; // rax
  __int64 *v33; // rcx
  __int64 v34; // rax
  char v35; // [rsp+38h] [rbp-D0h]
  __int128 *v36; // [rsp+40h] [rbp-C8h] BYREF
  int v37; // [rsp+48h] [rbp-C0h] BYREF
  int v38; // [rsp+4Ch] [rbp-BCh]
  char v39; // [rsp+50h] [rbp-B8h]
  __int16 v40; // [rsp+52h] [rbp-B6h]
  __m128i v41; // [rsp+58h] [rbp-B0h] BYREF
  int *v42; // [rsp+68h] [rbp-A0h]
  __int64 v43; // [rsp+70h] [rbp-98h] BYREF
  int v44; // [rsp+78h] [rbp-90h]
  __int64 v45; // [rsp+7Ch] [rbp-8Ch] BYREF
  int v46; // [rsp+84h] [rbp-84h]
  __int64 v47; // [rsp+88h] [rbp-80h]
  char v48; // [rsp+90h] [rbp-78h]
  __int128 v49; // [rsp+98h] [rbp-70h] BYREF
  __m128i v50; // [rsp+A8h] [rbp-60h]
  __int64 v51; // [rsp+B8h] [rbp-50h]
  volatile signed __int32 *v52; // [rsp+C0h] [rbp-48h]
  __int128 v53; // [rsp+C8h] [rbp-40h] BYREF
  __m128i v54; // [rsp+D8h] [rbp-30h]
  __int64 v55; // [rsp+E8h] [rbp-20h]
  int v56; // [rsp+F0h] [rbp-18h]

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v3 = *(_QWORD *)(v2 + 320);
  if ( v3 )
  {
    v47 = v2 + 330;
    v4 = *(_BYTE *)(v2 + 330);
    v35 = v4;
    v48 = v4;
    *(_BYTE *)(v2 + 330) = 1;
    v5 = *(_QWORD *)(v3 + 32);
    *(_QWORD *)&v49 = &Mso::Logging::StructuredObject<unsigned __int64,1>::`vftable';
    *((_QWORD *)&v49 + 1) = L"cTracesDeferred";
    v50.m128i_i64[0] = v5;
    v50.m128i_i16[4] = 0;
    v36 = &v49;
    v41.m128i_i64[0] = (__int64)&Mso::Logging::CompositeStructuredTrace::`vftable';
    v41.m128i_i64[1] = (__int64)&v36;
    v42 = &v37;
    v6 = (__int64 *)*((_QWORD *)this + 2);
    v7 = *v6;
    v37 = 7463960;
    v38 = 138;
    v39 = 100;
    v40 = 2;
    (*(void (__fastcall **)(__int64 *, int *, const wchar_t *, __m128i *))(v7 + 16))(
      v6,
      &v37,
      L"The following traces were triggered while servicing this thread's previous trace.",
      &v41);
    v8 = *(_QWORD **)(v2 + 320);
    if ( v8[4] )
    {
      v36 = &v53;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v10 = _mm_load_si128((const __m128i *)&_xmm);
      do
      {
        v11 = *(_QWORD *)(v8[1] + 8 * (v8[3] & (v8[2] - 1LL)));
        v51 = 0;
        v52 = 0;
        v12 = *(_QWORD *)(v11 + 8);
        if ( v12 )
          _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
        v51 = *(_QWORD *)v11;
        v52 = *(volatile signed __int32 **)(v11 + 8);
        v53 = 0;
        v54 = 0u;
        v13 = (_QWORD *)(v11 + 16);
        if ( *(_QWORD *)(v11 + 40) > 7u )
          v13 = (_QWORD *)*v13;
        std::wstring::_Construct<2,wchar_t const *>(&v53, v13, *(_QWORD *)(v11 + 32));
        v55 = *(_QWORD *)(v11 + 48);
        v56 = *(_DWORD *)(v11 + 56);
        v14 = *(_QWORD **)(v2 + 320);
        if ( !v14[4] )
          _invoke_watson(0, 0, 0, 0, 0);
        v15 = *(_QWORD **)(v14[1] + 8 * (v14[3] & (v14[2] - 1LL)));
        std::wstring::_Tidy_deallocate(v15 + 2);
        v15[2] = 19937;
        v15[4] = 0;
        v15[5] = 15;
        std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v15);
        if ( v14[4]-- == 1 )
          v14[3] = 0;
        else
          ++v14[3];
        v17 = v52;
        if ( v52 )
        {
          _InterlockedIncrement(v52 + 2);
          v17 = v52;
        }
        v18 = v51;
        if ( v17 )
        {
          if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
            if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
          }
          v17 = v52;
        }
        v19 = (__int64 *)*((_QWORD *)this + 2);
        v20 = *v19;
        if ( v18 )
        {
          v25 = *(void (__fastcall **)(__int64 *, __int64 *, __int128 *, __int64))(v20 + 16);
          if ( v17 )
          {
            _InterlockedIncrement(v17 + 2);
            v17 = v52;
          }
          v26 = v51;
          v41.m128i_i64[0] = v51;
          v41.m128i_i64[1] = (__int64)v17;
          v49 = 0;
          v50 = 0;
          v27 = &v53;
          if ( v54.m128i_i64[1] > 7uLL )
            v27 = (__int128 *)v53;
          std::wstring::_Construct<2,wchar_t const *>(&v49, v27, v54.m128i_i64[0]);
          v28 = &v49;
          if ( v50.m128i_i64[1] > 7uLL )
            v28 = (__int128 *)v49;
          v45 = v55;
          v46 = v56;
          v25(v19, &v45, v28, v26);
          if ( v50.m128i_i64[1] > 7uLL )
          {
            v29 = (void *)v49;
            if ( (unsigned __int64)(2 * v50.m128i_i64[1] + 2) >= 0x1000 )
            {
              v29 = *(void **)(v49 - 8);
              if ( (unsigned __int64)(v49 - (_QWORD)v29 - 8) > 0x1F )
                _invoke_watson(0, 0, 0, 0, 0);
            }
            free(v29);
          }
          *(_QWORD *)&v49 = 19937;
          v50 = si128;
          if ( v17 )
          {
            if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
              if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
            }
          }
          v41 = v10;
        }
        else
        {
          v21 = *(void (__fastcall **)(__int64 *, __int64 *, __int128 *))(v20 + 8);
          v49 = 0;
          v50 = 0;
          v22 = &v53;
          if ( v54.m128i_i64[1] > 7uLL )
            v22 = (__int128 *)v53;
          std::wstring::_Construct<2,wchar_t const *>(&v49, v22, v54.m128i_i64[0]);
          v23 = &v49;
          if ( v50.m128i_i64[1] > 7uLL )
            v23 = (__int128 *)v49;
          v43 = v55;
          v44 = v56;
          v21(v19, &v43, v23);
          if ( v50.m128i_i64[1] > 7uLL )
          {
            v24 = (void *)v49;
            if ( (unsigned __int64)(2 * v50.m128i_i64[1] + 2) >= 0x1000 )
            {
              v24 = *(void **)(v49 - 8);
              if ( (unsigned __int64)(v49 - (_QWORD)v24 - 8) > 0x1F )
                _invoke_watson(0, 0, 0, 0, 0);
            }
            free(v24);
          }
        }
        if ( v54.m128i_i64[1] > 7uLL )
        {
          v30 = (void *)v53;
          if ( (unsigned __int64)(2 * v54.m128i_i64[1] + 2) >= 0x1000 )
          {
            v30 = *(void **)(v53 - 8);
            if ( (unsigned __int64)(v53 - (_QWORD)v30 - 8) > 0x1F )
              _invoke_watson(0, 0, 0, 0, 0);
          }
          free(v30);
        }
        *(_QWORD *)&v53 = 19937;
        v54 = si128;
        v31 = v52;
        if ( v52 )
        {
          if ( _InterlockedExchangeAdd(v52 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
            if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
          }
        }
        v8 = *(_QWORD **)(v2 + 320);
      }
      while ( v8[4] );
      v4 = v35;
    }
    v32 = *((_QWORD *)this + 5);
    if ( v32 )
    {
      *(_QWORD *)&v49 = &Mso::Logging::StructuredObject<unsigned __int64,1>::`vftable';
      *((_QWORD *)&v49 + 1) = L"cTracesDiscarded";
      v50.m128i_i64[0] = v32;
      v50.m128i_i16[4] = 0;
      v36 = &v49;
      v41.m128i_i64[0] = (__int64)&Mso::Logging::CompositeStructuredTrace::`vftable';
      v41.m128i_i64[1] = (__int64)&v36;
      v42 = &v37;
      v33 = (__int64 *)*((_QWORD *)this + 2);
      v34 = *v33;
      v37 = 7463961;
      v38 = 138;
      v39 = 50;
      v40 = 2;
      (*(void (__fastcall **)(__int64 *, int *, const wchar_t *, __m128i *))(v34 + 16))(
        v33,
        &v37,
        L"Traces triggered while servicing this thread's previous deferred traces were discarded.",
        &v41);
    }
    Mso::Logging::ReentrantLoggerDecorator::ResetThreadLocals(this);
    *(_BYTE *)(v2 + 330) = v4;
  }
}

```

## disassembly

```asm
0x180014e40  mov     rax, rsp
0x180014e43  mov     [rax+10h], rbx
0x180014e47  mov     [rax+18h], rsi
0x180014e4b  mov     [rax+20h], rdi
0x180014e4f  push    rbp
0x180014e50  push    r12
0x180014e52  push    r13
0x180014e54  push    r14
0x180014e56  push    r15
0x180014e58  lea     rbp, [rax-48h]
0x180014e5c  sub     rsp, 120h
0x180014e63  movaps  xmmword ptr [rax-38h], xmm6
0x180014e67  movaps  xmmword ptr [rax-48h], xmm7
0x180014e6b  mov     rax, cs:__security_cookie
0x180014e72  xor     rax, rsp
0x180014e75  mov     [rbp+40h+var_50], rax
0x180014e79  mov     r14, rcx
0x180014e7c  xor     r12d, r12d
0x180014e7f  mov     edi, 140h
0x180014e84  mov     ecx, cs:_tls_index
0x180014e8a  mov     rax, gs:58h
0x180014e93  mov     r15, [rax+rcx*8]
0x180014e97  mov     rax, [r15+rdi]
0x180014e9b  test    rax, rax
0x180014e9e  jz      loc_1800153AA
0x180014ea4  mov     r13d, 14Ah
0x180014eaa  add     r13, r15
0x180014ead  mov     [rbp+40h+var_C0], r13
0x180014eb1  mov     bl, [r13+0]
0x180014eb5  mov     byte ptr [rsp+140h+var_110], bl
0x180014eb9  mov     [rbp+40h+var_B8], bl
0x180014ebc  mov     byte ptr [r13+0], 1
0x180014ec1  mov     rax, [rax+20h]
0x180014ec5  lea     rsi, ??_7?$StructuredObject@_K$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<unsigned __int64,1>::`vftable'
0x180014ecc  mov     qword ptr [rbp+40h+var_B0], rsi
0x180014ed0  lea     rcx, aCtracesdeferre; "cTracesDeferred"
0x180014ed7  mov     qword ptr [rbp+40h+var_B0+8], rcx
0x180014edb  mov     qword ptr [rbp+40h+var_A0], rax
0x180014edf  mov     word ptr [rbp+40h+var_A0+8], r12w
0x180014ee4  lea     rax, [rbp+40h+var_B0]
0x180014ee8  mov     [rsp+140h+var_108], rax
0x180014eed  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x180014ef4  mov     qword ptr [rsp+140h+var_F8+8], rax
0x180014ef9  lea     rax, [rsp+140h+var_108]
0x180014efe  mov     [rsp+140h+var_E8], rax
0x180014f03  lea     rax, [rsp+140h+var_100]
0x180014f08  mov     [rsp+140h+var_E0], rax
0x180014f0d  mov     rcx, [r14+10h]
0x180014f11  mov     rax, [rcx]
0x180014f14  mov     [rsp+140h+var_100], 71E418h
0x180014f1c  mov     [rsp+140h+var_FC], 8Ah
0x180014f24  mov     byte ptr [rsp+140h+var_F8], 64h ; 'd'
0x180014f29  lea     edx, [r12+2]
0x180014f2e  mov     word ptr [rsp+140h+var_F8+2], dx
0x180014f33  lea     r9, [rsp+140h+var_F8+8]
0x180014f38  lea     r8, aTheFollowingTr; "The following traces were triggered whi"...
0x180014f3f  lea     rdx, [rsp+140h+var_100]
0x180014f44  mov     rax, [rax+10h]
0x180014f48  call    cs:__guard_dispatch_icall_fptr
0x180014f4e  mov     rax, [r15+rdi]
0x180014f52  cmp     [rax+20h], r12
0x180014f56  jz      loc_18001530F
0x180014f5c  lea     rcx, [rbp+40h+var_80]
0x180014f60  mov     [rsp+140h+var_108], rcx
0x180014f65  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x180014f6d  movdqa  xmm7, cs:__xmm@0000000000004de10000000000004de1
0x180014f75  mov     rcx, [rax+10h]
0x180014f79  dec     rcx
0x180014f7c  and     rcx, [rax+18h]
0x180014f80  mov     rax, [rax+8]
0x180014f84  mov     rbx, [rax+rcx*8]
0x180014f88  mov     [rbp+40h+var_90], r12
0x180014f8c  mov     [rbp+40h+var_88], r12
0x180014f90  mov     rax, [rbx+8]
0x180014f94  test    rax, rax
0x180014f97  jz      short loc_180014F9D
0x180014f99  lock inc dword ptr [rax+8]
0x180014f9d  mov     rax, [rbx]
0x180014fa0  mov     [rbp+40h+var_90], rax
0x180014fa4  mov     rax, [rbx+8]
0x180014fa8  mov     [rbp+40h+var_88], rax
0x180014fac  xorps   xmm0, xmm0
0x180014faf  movups  [rbp+40h+var_80], xmm0
0x180014fb3  mov     qword ptr [rbp+40h+var_70], r12
0x180014fb7  mov     qword ptr [rbp+40h+var_70+8], r12
0x180014fbb  lea     rdx, [rbx+10h]
0x180014fbf  cmp     qword ptr [rdx+18h], 7
0x180014fc4  jbe     short loc_180014FC9
0x180014fc6  mov     rdx, [rdx]
0x180014fc9  mov     r8, [rbx+20h]
0x180014fcd  lea     rcx, [rbp+40h+var_80]
0x180014fd1  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180014fd6  movsd   xmm0, qword ptr [rbx+30h]
0x180014fdb  movsd   [rbp+40h+var_60], xmm0
0x180014fe0  mov     eax, [rbx+38h]
0x180014fe3  mov     [rbp+40h+var_58], eax
0x180014fe6  mov     rsi, [r15+rdi]
0x180014fea  cmp     [rsi+20h], r12
0x180014fee  jz      loc_180015427
0x180014ff4  mov     rcx, [rsi+10h]
0x180014ff8  dec     rcx
0x180014ffb  and     rcx, [rsi+18h]
0x180014fff  mov     rax, [rsi+8]
0x180015003  mov     rdi, [rax+rcx*8]
0x180015007  lea     rcx, [rdi+10h]
0x18001500b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015010  mov     qword ptr [rdi+10h], 4DE1h
0x180015018  mov     [rdi+20h], r12
0x18001501c  mov     qword ptr [rdi+28h], 0Fh
0x180015024  mov     rcx, rdi
0x180015027  call    ??1?$shared_ptr@V?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@@std@@QEAA@XZ; std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(void)
0x18001502c  sub     qword ptr [rsi+20h], 1
0x180015031  jnz     short loc_180015039
0x180015033  mov     [rsi+18h], r12
0x180015037  jmp     short loc_18001503D
0x180015039  inc     qword ptr [rsi+18h]
0x18001503d  mov     rdi, [rbp+40h+var_88]
0x180015041  test    rdi, rdi
0x180015044  jz      short loc_18001504E
0x180015046  lock inc dword ptr [rdi+8]
0x18001504a  mov     rdi, [rbp+40h+var_88]
0x18001504e  mov     rbx, [rbp+40h+var_90]
0x180015052  test    rdi, rdi
0x180015055  jz      short loc_180015094
0x180015057  or      eax, 0FFFFFFFFh
0x18001505a  lock xadd [rdi+8], eax
0x18001505f  cmp     eax, 1
0x180015062  jnz     short loc_180015090
0x180015064  mov     rax, [rdi]
0x180015067  mov     rcx, rdi
0x18001506a  mov     rax, [rax]
0x18001506d  call    cs:__guard_dispatch_icall_fptr
0x180015073  or      eax, 0FFFFFFFFh
0x180015076  lock xadd [rdi+0Ch], eax
0x18001507b  cmp     eax, 1
0x18001507e  jnz     short loc_180015090
0x180015080  mov     rax, [rdi]
0x180015083  mov     rcx, rdi
0x180015086  mov     rax, [rax+8]
0x18001508a  call    cs:__guard_dispatch_icall_fptr
0x180015090  mov     rdi, [rbp+40h+var_88]
0x180015094  mov     rsi, [r14+10h]
0x180015098  mov     rax, [rsi]
0x18001509b  test    rbx, rbx
0x18001509e  jnz     loc_180015157
0x1800150a4  mov     rbx, [rax+8]
0x1800150a8  xorps   xmm0, xmm0
0x1800150ab  movups  [rbp+40h+var_B0], xmm0
0x1800150af  xorps   xmm1, xmm1
0x1800150b2  movdqu  [rbp+40h+var_A0], xmm1
0x1800150b7  lea     rdx, [rbp+40h+var_80]
0x1800150bb  cmp     qword ptr [rbp+40h+var_70+8], 7
0x1800150c0  cmova   rdx, qword ptr [rbp+40h+var_80]
0x1800150c5  mov     r8, qword ptr [rbp+40h+var_70]
0x1800150c9  lea     rcx, [rbp+40h+var_B0]
0x1800150cd  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800150d2  lea     r8, [rbp+40h+var_B0]
0x1800150d6  cmp     qword ptr [rbp+40h+var_A0+8], 7
0x1800150db  cmova   r8, qword ptr [rbp+40h+var_B0]
0x1800150e0  movsd   xmm0, [rbp+40h+var_60]
0x1800150e5  movsd   qword ptr [rsp+140h+var_D8], xmm0
0x1800150eb  mov     ecx, [rbp+40h+var_58]
0x1800150ee  mov     dword ptr [rsp+140h+var_D4+4], ecx
0x1800150f2  lea     rdx, [rsp+140h+var_D8]
0x1800150f7  mov     rcx, rsi
0x1800150fa  mov     rax, rbx
0x1800150fd  call    cs:__guard_dispatch_icall_fptr
0x180015103  mov     rax, qword ptr [rbp+40h+var_A0+8]
0x180015107  cmp     rax, 7
0x18001510b  jbe     loc_180015266
0x180015111  nop     dword ptr [rax+00h]
0x180015115  nop     word ptr [rax+rax+00000000h]
0x180015120  mov     rcx, qword ptr [rbp+40h+var_B0]
0x180015124  mov     rdx, rcx
0x180015127  lea     rax, ds:2[rax*2]
0x18001512f  cmp     rax, 1000h
0x180015135  jb      short loc_18001514C
0x180015137  mov     rcx, [rcx-8]; Block
0x18001513b  sub     rdx, rcx
0x18001513e  lea     rax, [rdx-8]
0x180015142  cmp     rax, 1Fh
0x180015146  ja      loc_1800153E1
0x18001514c  call    cs:__imp_free
0x180015152  jmp     loc_180015266
0x180015157  mov     r12, [rax+10h]
0x18001515b  test    rdi, rdi
0x18001515e  jz      short loc_180015168
0x180015160  lock inc dword ptr [rdi+8]
0x180015164  mov     rdi, [rbp+40h+var_88]
0x180015168  mov     rbx, [rbp+40h+var_90]
0x18001516c  mov     qword ptr [rsp+140h+var_F8+8], rbx
0x180015171  mov     [rsp+140h+var_E8], rdi
0x180015176  xorps   xmm0, xmm0
0x180015179  movups  [rbp+40h+var_B0], xmm0
0x18001517d  xorps   xmm1, xmm1
0x180015180  movdqu  [rbp+40h+var_A0], xmm1
0x180015185  lea     rdx, [rbp+40h+var_80]
0x180015189  cmp     qword ptr [rbp+40h+var_70+8], 7
0x18001518e  cmova   rdx, qword ptr [rbp+40h+var_80]
0x180015193  mov     r8, qword ptr [rbp+40h+var_70]
0x180015197  lea     rcx, [rbp+40h+var_B0]
0x18001519b  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800151a0  lea     r8, [rbp+40h+var_B0]
0x1800151a4  cmp     qword ptr [rbp+40h+var_A0+8], 7
0x1800151a9  cmova   r8, qword ptr [rbp+40h+var_B0]
0x1800151ae  movsd   xmm0, [rbp+40h+var_60]
0x1800151b3  movsd   [rsp+140h+var_CC], xmm0
0x1800151b9  mov     ecx, [rbp+40h+var_58]
0x1800151bc  mov     [rsp+140h+var_C4], ecx
0x1800151c0  mov     r9, rbx
0x1800151c3  lea     rdx, [rsp+140h+var_CC]
0x1800151c8  mov     rcx, rsi
0x1800151cb  mov     rax, r12
0x1800151ce  call    cs:__guard_dispatch_icall_fptr
0x1800151d4  mov     rax, qword ptr [rbp+40h+var_A0+8]
0x1800151d8  cmp     rax, 7
0x1800151dc  jbe     short loc_180015212
0x1800151de  xchg    ax, ax
0x1800151e0  mov     rcx, qword ptr [rbp+40h+var_B0]
0x1800151e4  mov     rdx, rcx
0x1800151e7  lea     rax, ds:2[rax*2]
0x1800151ef  cmp     rax, 1000h
0x1800151f5  jb      short loc_18001520C
0x1800151f7  mov     rcx, [rcx-8]; Block
0x1800151fb  sub     rdx, rcx
0x1800151fe  lea     rax, [rdx-8]
0x180015202  cmp     rax, 1Fh
0x180015206  ja      loc_1800153F7
0x18001520c  call    cs:__imp_free
0x180015212  mov     qword ptr [rbp+40h+var_B0], 4DE1h
0x18001521a  movdqu  [rbp+40h+var_A0], xmm6
0x18001521f  xor     r12d, r12d
0x180015222  test    rdi, rdi
0x180015225  jz      short loc_180015260
0x180015227  or      eax, 0FFFFFFFFh
0x18001522a  lock xadd [rdi+8], eax
0x18001522f  cmp     eax, 1
0x180015232  jnz     short loc_180015260
0x180015234  mov     rax, [rdi]
0x180015237  mov     rcx, rdi
0x18001523a  mov     rax, [rax]
0x18001523d  call    cs:__guard_dispatch_icall_fptr
0x180015243  or      eax, 0FFFFFFFFh
0x180015246  lock xadd [rdi+0Ch], eax
0x18001524b  cmp     eax, 1
0x18001524e  jnz     short loc_180015260
0x180015250  mov     rax, [rdi]
0x180015253  mov     rcx, rdi
0x180015256  mov     rax, [rax+8]
0x18001525a  call    cs:__guard_dispatch_icall_fptr
0x180015260  movdqu  [rsp+140h+var_F8+8], xmm7
0x180015266  mov     rax, qword ptr [rbp+40h+var_70+8]
0x18001526a  cmp     rax, 7
0x18001526e  jbe     short loc_1800152A2
0x180015270  mov     rcx, qword ptr [rbp+40h+var_80]
0x180015274  mov     rdx, rcx
0x180015277  lea     rax, ds:2[rax*2]
0x18001527f  cmp     rax, 1000h
0x180015285  jb      short loc_18001529C
0x180015287  mov     rcx, [rcx-8]; Block
0x18001528b  sub     rdx, rcx
0x18001528e  lea     rax, [rdx-8]
0x180015292  cmp     rax, 1Fh
0x180015296  ja      loc_180015411
0x18001529c  call    cs:__imp_free
0x1800152a2  mov     qword ptr [rbp+40h+var_80], 4DE1h
0x1800152aa  movdqa  [rbp+40h+var_70], xmm6
0x1800152af  mov     rbx, [rbp+40h+var_88]
0x1800152b3  test    rbx, rbx
0x1800152b6  jz      short loc_1800152F1
0x1800152b8  or      eax, 0FFFFFFFFh
0x1800152bb  lock xadd [rbx+8], eax
0x1800152c0  cmp     eax, 1
0x1800152c3  jnz     short loc_1800152F1
0x1800152c5  mov     rax, [rbx]
0x1800152c8  mov     rcx, rbx
0x1800152cb  mov     rax, [rax]
0x1800152ce  call    cs:__guard_dispatch_icall_fptr
0x1800152d4  or      eax, 0FFFFFFFFh
0x1800152d7  lock xadd [rbx+0Ch], eax
0x1800152dc  cmp     eax, 1
0x1800152df  jnz     short loc_1800152F1
0x1800152e1  mov     rax, [rbx]
0x1800152e4  mov     rcx, rbx
0x1800152e7  mov     rax, [rax+8]
0x1800152eb  call    cs:__guard_dispatch_icall_fptr
0x1800152f1  mov     edi, 140h
0x1800152f6  mov     rax, [r15+rdi]
0x1800152fa  cmp     [rax+20h], r12
0x1800152fe  jnz     loc_180014F75
0x180015304  mov     bl, byte ptr [rsp+140h+var_110]
0x180015308  lea     rsi, ??_7?$StructuredObject@_K$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<unsigned __int64,1>::`vftable'
0x18001530f  mov     rax, [r14+28h]
0x180015313  test    rax, rax
0x180015316  jz      loc_18001539E
0x18001531c  mov     qword ptr [rbp+40h+var_B0], rsi
0x180015320  lea     rcx, aCtracesdiscard; "cTracesDiscarded"
0x180015327  mov     qword ptr [rbp+40h+var_B0+8], rcx
0x18001532b  mov     qword ptr [rbp+40h+var_A0], rax
0x18001532f  mov     word ptr [rbp+40h+var_A0+8], r12w
  ... truncated ...
```
