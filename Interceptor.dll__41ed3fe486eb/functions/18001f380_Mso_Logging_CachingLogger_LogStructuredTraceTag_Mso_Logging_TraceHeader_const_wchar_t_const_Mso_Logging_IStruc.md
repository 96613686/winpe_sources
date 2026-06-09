# Mso::Logging::CachingLogger::LogStructuredTraceTag(Mso::Logging::TraceHeader const &,wchar_t const *,Mso::Logging::IStructuredTrace const &)

- ea: `0x18001f380`
- end: `0x18001f64e`
- name: `?LogStructuredTraceTag@CachingLogger@Logging@Mso@@UEAAXAEBUTraceHeader@23@PEB_WAEBUIStructuredTrace@23@@Z`
- size: `718`
- prototype: `void __fastcall(Mso::Logging::CachingLogger *__hidden this, const struct Mso::Logging::TraceHeader *, const wchar_t *, const struct Mso::Logging::IStructuredTrace *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x18000410c`
- `0x18000a580`
- `0x18000dd50`
- `0x180015f68`
- `0x18001f380`
- `0x18001fb3c`
- `0x1800261c0`
- `0x1800261d0`
- `0x1800266e0`
- `0x1800282a0`
- `0x18002b3c0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001f54e`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001f54e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001f555`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001f555`

## string_xrefs

- `0x18001f62b`: `StructuredTraceCopier requires non-null IStructuredTrace to receive the copy.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Mso::Logging::CachingLogger::LogStructuredTraceTag(
        _Smtx_t *this,
        const struct Mso::Logging::TraceHeader *a2,
        const wchar_t *a3,
        const struct Mso::Logging::IStructuredTrace *a4)
{
  __int64 v8; // rbx
  __int64 v9; // rsi
  __int64 v10; // r8
  __int128 v11; // xmm6
  __int128 v12; // xmm7
  __int64 v13; // xmm8_8
  int v14; // r15d
  _QWORD *v15; // rdx
  volatile signed __int32 *v16; // rbx
  unsigned __int64 v17; // rdi
  void *v18; // rcx
  volatile signed __int32 *v19; // rbx
  __int128 v20; // [rsp+38h] [rbp-D0h] BYREF
  void **v21; // [rsp+48h] [rbp-C0h] BYREF
  __m128i si128; // [rsp+50h] [rbp-B8h]
  _OWORD pExceptionObject_8[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+88h] [rbp-80h] BYREF
  volatile signed __int32 *v25; // [rsp+90h] [rbp-78h]
  void *Block[2]; // [rsp+98h] [rbp-70h]
  __int128 v27; // [rsp+A8h] [rbp-60h]
  __int64 v28; // [rsp+B8h] [rbp-50h]
  int v29; // [rsp+C0h] [rbp-48h]
  __int128 v30; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v31; // [rsp+D8h] [rbp-30h]

  Mso::Logging::CreateStructuredTraceCollection(&v20);
  v21 = &Mso::Logging::StructuredTraceCopier::`vftable';
  si128 = 0;
  v8 = *((_QWORD *)&v20 + 1);
  if ( *((_QWORD *)&v20 + 1) )
    _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v20 + 1) + 8LL), 1u);
  v9 = v20;
  si128.m128i_i64[0] = v20;
  si128.m128i_i64[1] = v8;
  if ( !(_QWORD)v20 )
  {
    std::runtime_error::runtime_error(
      (std::runtime_error *)pExceptionObject_8,
      "StructuredTraceCopier requires non-null IStructuredTrace to receive the copy.");
    throw (std::runtime_error *)pExceptionObject_8;
  }
  (**(void (__fastcall ***)(const struct Mso::Logging::IStructuredTrace *, void ***))a4)(a4, &v21);
  if ( v8 )
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
  pExceptionObject_8[0] = v20;
  if ( !a3 )
    a3 = &Src;
  v30 = 0;
  v31 = 0;
  v10 = -1;
  do
    ++v10;
  while ( a3[v10] );
  std::wstring::_Construct<1,wchar_t const *>(&v30, a3, v10);
  v24 = v9;
  v25 = (volatile signed __int32 *)v8;
  v11 = v30;
  *(_OWORD *)Block = v30;
  v12 = v31;
  v27 = v31;
  v13 = *(_QWORD *)a2;
  v28 = *(_QWORD *)a2;
  v14 = *((_DWORD *)a2 + 2);
  v29 = v14;
  *(_QWORD *)&pExceptionObject_8[0] = this + 4;
  Smtx_lock_exclusive(this + 4);
  BYTE8(pExceptionObject_8[0]) = 1;
  v15 = this[2];
  if ( v15 == this[3] )
  {
    std::vector<std::tuple<Mso::Logging::TraceHeader,std::wstring,std::shared_ptr<Mso::Logging::IStructuredTrace>>>::_Emplace_reallocate<std::tuple<Mso::Logging::TraceHeader,std::wstring,std::shared_ptr<Mso::Logging::IStructuredTrace>>>(
      this + 1,
      v15,
      &v24);
    v17 = *((_QWORD *)&v27 + 1);
    v16 = v25;
  }
  else
  {
    *v15 = v9;
    v15[1] = v8;
    v16 = 0;
    *((_OWORD *)v15 + 1) = v11;
    *((_OWORD *)v15 + 2) = v12;
    v17 = 7;
    LOWORD(Block[0]) = 0;
    v15[6] = v13;
    *((_DWORD *)v15 + 14) = v14;
    this[2] = (char *)this[2] + 64;
  }
  Smtx_unlock_exclusive(this + 4);
  if ( v17 > 7 )
  {
    v18 = Block[0];
    if ( 2 * v17 + 2 >= 0x1000 )
    {
      v18 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v18 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v18);
  }
  if ( v16 )
  {
    if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  v19 = (volatile signed __int32 *)si128.m128i_i64[1];
  if ( si128.m128i_i64[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(si128.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
      if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
    }
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(&v20);
}

```

## disassembly

```asm
0x18001f380  mov     rax, rsp
0x18001f383  mov     [rax+10h], rbx
0x18001f387  push    rbp
0x18001f388  push    rsi
0x18001f389  push    rdi
0x18001f38a  push    r12
0x18001f38c  push    r13
0x18001f38e  push    r14
0x18001f390  push    r15
0x18001f392  lea     rbp, [rax-58h]
0x18001f396  sub     rsp, 120h
0x18001f39d  movaps  xmmword ptr [rax-48h], xmm6
0x18001f3a1  movaps  xmmword ptr [rax-58h], xmm7
0x18001f3a5  movaps  xmmword ptr [rax-68h], xmm8
0x18001f3aa  mov     rax, cs:__security_cookie
0x18001f3b1  xor     rax, rsp
0x18001f3b4  mov     [rbp+50h+var_70], rax
0x18001f3b8  mov     r14, r9
0x18001f3bb  mov     rdi, r8
0x18001f3be  mov     r15, rdx
0x18001f3c1  mov     r13, rcx
0x18001f3c4  lea     rcx, [rsp+150h+var_128+8]
0x18001f3c9  call    ?CreateStructuredTraceCollection@Logging@Mso@@YA?AV?$shared_ptr@UIStructuredTraceCollection@Logging@Mso@@@std@@XZ; Mso::Logging::CreateStructuredTraceCollection(void)
0x18001f3ce  lea     rax, ??_7StructuredTraceCopier@Logging@Mso@@6B@; const Mso::Logging::StructuredTraceCopier::`vftable'
0x18001f3d5  mov     qword ptr [rsp+150h+var_110], rax
0x18001f3da  xorps   xmm0, xmm0
0x18001f3dd  movdqu  [rsp+150h+var_110+8], xmm0
0x18001f3e3  mov     eax, 1
0x18001f3e8  mov     rbx, [rsp+150h+var_118]
0x18001f3ed  xor     r12d, r12d
0x18001f3f0  test    rbx, rbx
0x18001f3f3  jz      short loc_18001F3F9
0x18001f3f5  lock add [rbx+8], eax
0x18001f3f9  mov     rsi, qword ptr [rsp+150h+var_128+8]
0x18001f3fe  mov     qword ptr [rsp+150h+var_110+8], rsi
0x18001f403  mov     [rsp+150h+var_100], rbx
0x18001f408  test    rsi, rsi
0x18001f40b  jz      loc_18001F62B
0x18001f411  mov     rax, [r14]
0x18001f414  lea     rdx, [rsp+150h+var_110]
0x18001f419  mov     rcx, r14
0x18001f41c  mov     rax, [rax]
0x18001f41f  call    cs:__guard_dispatch_icall_fptr
0x18001f425  test    rbx, rbx
0x18001f428  jz      short loc_18001F42E
0x18001f42a  lock inc dword ptr [rbx+8]
0x18001f42e  movaps  xmm0, [rsp+150h+var_128+8]
0x18001f433  movdqa  [rsp+150h+pExceptionObject+8], xmm0
0x18001f439  lea     rax, Src
0x18001f440  test    rdi, rdi
0x18001f443  cmovz   rdi, rax
0x18001f447  xorps   xmm0, xmm0
0x18001f44a  movups  [rbp+50h+var_90], xmm0
0x18001f44e  xorps   xmm1, xmm1
0x18001f451  movdqu  [rbp+50h+var_80], xmm1
0x18001f456  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001f45a  inc     r8
0x18001f45d  cmp     [rdi+r8*2], r12w
0x18001f462  jnz     short loc_18001F45A
0x18001f464  mov     rdx, rdi
0x18001f467  lea     rcx, [rbp+50h+var_90]
0x18001f46b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001f470  mov     [rbp+50h+var_D0], rsi
0x18001f474  mov     [rbp+50h+var_C8], rbx
0x18001f478  movups  xmm6, [rbp+50h+var_90]
0x18001f47c  movaps  xmmword ptr [rbp+50h+Block], xmm6
0x18001f480  movups  xmm7, [rbp+50h+var_80]
0x18001f484  movaps  [rbp+50h+var_B0], xmm7
0x18001f488  movsd   xmm8, qword ptr [r15]
0x18001f48d  movsd   [rbp+50h+var_A0], xmm8
0x18001f493  mov     r15d, [r15+8]
0x18001f497  mov     [rbp+50h+var_98], r15d
0x18001f49b  lea     r14, [r13+20h]
0x18001f49f  mov     qword ptr [rsp+150h+pExceptionObject+8], r14
0x18001f4a4  mov     rcx, r14; _Smtx_t *
0x18001f4a7  call    _Smtx_lock_exclusive
0x18001f4ac  mov     eax, 1
0x18001f4b1  mov     [rsp+150h+var_E8], al
0x18001f4b5  lea     rcx, [r13+8]
0x18001f4b9  mov     rdx, [rcx+8]
0x18001f4bd  cmp     rdx, [rcx+10h]
0x18001f4c1  jz      short loc_18001F4EE
0x18001f4c3  mov     [rdx], rsi
0x18001f4c6  mov     [rdx+8], rbx
0x18001f4ca  mov     rbx, r12
0x18001f4cd  movups  xmmword ptr [rdx+10h], xmm6
0x18001f4d1  movups  xmmword ptr [rdx+20h], xmm7
0x18001f4d5  lea     edi, [rax+6]
0x18001f4d8  mov     word ptr [rbp+50h+Block], r12w
0x18001f4dd  movsd   qword ptr [rdx+30h], xmm8
0x18001f4e3  mov     [rdx+38h], r15d
0x18001f4e7  add     qword ptr [rcx+8], 40h ; '@'
0x18001f4ec  jmp     short loc_18001F504
0x18001f4ee  lea     r8, [rbp+50h+var_D0]
0x18001f4f2  call    ??$_Emplace_reallocate@V?$tuple@UTraceHeader@Logging@Mso@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UIStructuredTrace@Logging@Mso@@@5@@std@@@?$vector@V?$tuple@UTraceHeader@Logging@Mso@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UIStructuredTrace@Logging@Mso@@@5@@std@@V?$allocator@V?$tuple@UTraceHeader@Logging@Mso@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UIStructuredTrace@Logging@Mso@@@5@@std@@@2@@std@@AEAAPEAV?$tuple@UTraceHeader@Logging@Mso@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UIStructuredTrace@Logging@Mso@@@5@@1@QEAV21@$$QEAV21@@Z; std::vector<std::tuple<Mso::Logging::TraceHeader,std::wstring,std::shared_ptr<Mso::Logging::IStructuredTrace>>>::_Emplace_reallocate<std::tuple<Mso::Logging::TraceHeader,std::wstring,std::shared_ptr<Mso::Logging::IStructuredTrace>>>(std::tuple<Mso::Logging::TraceHeader,std::wstring,std::shared_ptr<Mso::Logging::IStructuredTrace>> * const,std::tuple<Mso::Logging::TraceHeader,std::wstring,std::shared_ptr<Mso::Logging::IStructuredTrace>> &&)
0x18001f4f7  mov     rdi, qword ptr [rbp+50h+var_B0+8]
0x18001f4fb  mov     rbx, [rbp+50h+var_C8]
0x18001f4ff  mov     eax, 1
0x18001f504  test    al, al
0x18001f506  jz      short loc_18001F511
0x18001f508  mov     rcx, r14; _Smtx_t *
0x18001f50b  call    _Smtx_unlock_exclusive
0x18001f510  nop
0x18001f511  cmp     rdi, 7
0x18001f515  jbe     short loc_18001F55B
0x18001f517  mov     rcx, [rbp+50h+Block]; Block
0x18001f51b  mov     rdx, rcx
0x18001f51e  lea     rax, ds:2[rdi*2]
0x18001f526  cmp     rax, 1000h
0x18001f52c  jb      short loc_18001F555
0x18001f52e  mov     rcx, [rcx-8]
0x18001f532  sub     rdx, rcx
0x18001f535  lea     rax, [rdx-8]
0x18001f539  cmp     rax, 1Fh
0x18001f53d  jbe     short loc_18001F555
0x18001f53f  mov     [rsp+150h+Reserved], r12; Reserved
0x18001f544  xor     r9d, r9d; LineNo
0x18001f547  xor     r8d, r8d; FileName
0x18001f54a  xor     edx, edx; FunctionName
0x18001f54c  xor     ecx, ecx; Expression
0x18001f54e  call    cs:__imp__invoke_watson
0x18001f555  call    cs:__imp_free
0x18001f55b  test    rbx, rbx
0x18001f55e  jz      short loc_18001F59A
0x18001f560  or      eax, 0FFFFFFFFh
0x18001f563  lock xadd [rbx+8], eax
0x18001f568  cmp     eax, 1
0x18001f56b  jnz     short loc_18001F59A
0x18001f56d  mov     rax, [rbx]
0x18001f570  mov     rcx, rbx
0x18001f573  mov     rax, [rax]
0x18001f576  call    cs:__guard_dispatch_icall_fptr
0x18001f57c  or      eax, 0FFFFFFFFh
0x18001f57f  lock xadd [rbx+0Ch], eax
0x18001f584  cmp     eax, 1
0x18001f587  jnz     short loc_18001F59A
0x18001f589  mov     rax, [rbx]
0x18001f58c  mov     rcx, rbx
0x18001f58f  mov     rax, [rax+8]
0x18001f593  call    cs:__guard_dispatch_icall_fptr
0x18001f599  nop
0x18001f59a  mov     rbx, [rsp+150h+var_100]
0x18001f59f  test    rbx, rbx
0x18001f5a2  jz      short loc_18001F5DD
0x18001f5a4  or      eax, 0FFFFFFFFh
0x18001f5a7  lock xadd [rbx+8], eax
0x18001f5ac  cmp     eax, 1
0x18001f5af  jnz     short loc_18001F5DD
0x18001f5b1  mov     rax, [rbx]
0x18001f5b4  mov     rcx, rbx
0x18001f5b7  mov     rax, [rax]
0x18001f5ba  call    cs:__guard_dispatch_icall_fptr
0x18001f5c0  or      eax, 0FFFFFFFFh
0x18001f5c3  lock xadd [rbx+0Ch], eax
0x18001f5c8  cmp     eax, 1
0x18001f5cb  jnz     short loc_18001F5DD
0x18001f5cd  mov     rax, [rbx]
0x18001f5d0  mov     rcx, rbx
0x18001f5d3  mov     rax, [rax+8]
0x18001f5d7  call    cs:__guard_dispatch_icall_fptr
0x18001f5dd  movdqa  xmm0, cs:__xmm@0000000000004de10000000000004de1
0x18001f5e5  movdqu  [rsp+150h+var_110+8], xmm0
0x18001f5eb  lea     rcx, [rsp+150h+var_128+8]
0x18001f5f0  call    ??1?$shared_ptr@V?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@@std@@QEAA@XZ; std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(void)
0x18001f5f5  mov     rcx, [rbp+50h+var_70]
0x18001f5f9  xor     rcx, rsp; StackCookie
0x18001f5fc  call    __security_check_cookie
0x18001f601  lea     r11, [rsp+150h+var_30]
0x18001f609  mov     rbx, [r11+48h]
0x18001f60d  movaps  xmm6, xmmword ptr [r11-10h]
0x18001f612  movaps  xmm7, xmmword ptr [r11-20h]
0x18001f617  movaps  xmm8, xmmword ptr [r11-30h]
0x18001f61c  mov     rsp, r11
0x18001f61f  pop     r15
0x18001f621  pop     r14
0x18001f623  pop     r13
0x18001f625  pop     r12
0x18001f627  pop     rdi
0x18001f628  pop     rsi
0x18001f629  pop     rbp
0x18001f62a  retn
0x18001f62b  lea     rdx, aStructuredtrac_4; "StructuredTraceCopier requires non-null"...
0x18001f632  lea     rcx, [rsp+150h+pExceptionObject+8]; this
0x18001f637  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18001f63c  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001f643  lea     rcx, [rsp+150h+pExceptionObject+8]; pExceptionObject
0x18001f648  call    _CxxThrowException
```
