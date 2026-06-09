# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::MergeSchematizedFilter(uint,uchar *,Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal &)

- ea: `0x180023d04`
- end: `0x180023f74`
- name: `?MergeSchematizedFilter@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@CAJIPEAEAEAVEtwProviderConfigInternal@1234@@Z`
- size: `624`
- prototype: `__int64 __fastcall(size_t Size, unsigned __int8 *Src, struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023f74`

## callees

- `0x180009e14`
- `0x180023d04`
- `0x180025080`
- `0x1800253cc`
- `0x1800267e8`
- `0x180026fec`
- `0x180049bac`
- `0x180049c18`
- `0x18004a024`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x180023d57`
- `VCRUNTIME140!memcpy` at `0x180023f0a`
- `VCRUNTIME140!memcpy` at `0x180023d57`
- `VCRUNTIME140!memcpy` at `0x180023f0a`
- `VCRUNTIME140!memset` at `0x180023f21`
- `VCRUNTIME140!memset` at `0x180023f21`
- `VCRUNTIME140!memmove` at `0x180023e16`
- `VCRUNTIME140!memmove` at `0x180023e16`
- `VCRUNTIME140!memcmp` at `0x180023e78`
- `VCRUNTIME140!memcmp` at `0x180023e78`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180023f27`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180023f27`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180023f33`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180023f33`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::MergeSchematizedFilter(
        size_t Size,
        unsigned __int8 *Src,
        struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal *a3)
{
  size_t v5; // rbx
  void *v6; // rcx
  size_t v7; // r8
  __int64 v8; // rdx
  char *v9; // rbx
  char *v10; // rdi
  size_t v11; // rbx
  size_t v12; // r8
  __int64 v13; // rax
  __int64 v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rsi
  __int64; // rax
  unsigned int v18; // ebx
  _DWORD Srca[6]; // [rsp+20h] [rbp-68h] BYREF
  void *Buf2[2]; // [rsp+38h] [rbp-50h] BYREF
  __int64 v21; // [rsp+48h] [rbp-40h]
  _QWORD v22[7]; // [rsp+50h] [rbp-38h] BYREF

  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    *(_OWORD *)Buf2 = 0;
    v21 = 0;
    v5 = (unsigned int)Size;
    std::vector<unsigned char>::resize(Buf2, (unsigned int)Size);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180023F53);
      std::vector<unsigned char>::~vector<unsigned char>(Buf2);
       = 2147942414LL;
LABEL_36:
      ;
    }
  }
  if ( v5 )
  {
    v6 = Buf2[0];
    if ( !Buf2[0] )
      goto LABEL_20;
    v7 = v5;
    if ( !Src )
    {
LABEL_19:
      memset(v6, 0, v7);
      goto LABEL_20;
    }
    memcpy(Buf2[0], Src, v5);
  }
  v8 = 4;
  if ( dword_180077A08 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180077A08);
    if ( dword_180077A08 == -1 )
    {
      strcpy((char *)Srca, "FilterAndPayloadSpecs");
      *(_OWORD *)&Buf1 = 0;
      qword_180077A20 = 0;
      _mm_lfence();
      Buf1 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(22);
      *(&Buf1 + 1) = Buf1;
      v9 = (char *)Buf1 + 22;
      qword_180077A20 = (__int64)Buf1 + 22;
      memmove(Buf1, Srca, 0x16u);
      *(&Buf1 + 1) = v9;
      v22[0] = 0;
      std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(v22);
      atexit(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::MergeSchematizedFilter_::_2_::_dynamic_atexit_destructor_for__filterHeader__);
      Init_thread_footer(&dword_180077A08);
    }
  }
  v10 = (char *)Buf2[0];
  v11 = (char *)Buf2[1] - (char *)Buf2[0];
  v12 = (_BYTE *)*(&Buf1 + 1) - (_BYTE *)Buf1;
  if ( (void *)((char *)Buf2[1] - (char *)Buf2[0]) > (void *)((_BYTE *)*(&Buf1 + 1) - (_BYTE *)Buf1) )
  {
    _mm_lfence();
    if ( !memcmp(Buf1, Buf2[0], v12) )
    {
      v10 += (_BYTE *)*(&Buf1 + 1) - (_BYTE *)Buf1;
      v11 -= (_BYTE *)*(&Buf1 + 1) - (_BYTE *)Buf1;
    }
  }
  v13 = *((_QWORD *)a3 + 8);
  v14 = *((_QWORD *)a3 + 9) - v13;
  v15 = v14 - 1;
  if ( *((_QWORD *)a3 + 9) == v13 )
    std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xrange(v15, v8, v12);
  if ( __eh34_try(-1, 2) )
  {
    __eh34_scope_strut(2);
    _mm_lfence();
    v16 = (*(_BYTE *)(v13 + v15) != 0) + 1LL;
    std::vector<unsigned char>::resize((char *)a3 + 64, v11 + v14 + v16);
  }
  if ( __eh34_catch(2) )
  {
    if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v18 = -2147024882;
      __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_180023F40);
      goto LABEL_21;
    }
  }
  *(_BYTE *)(v14 + *((_QWORD *)a3 + 8) + v16 - 2) = 13;
  *(_BYTE *)(v14 + *((_QWORD *)a3 + 8) + v16 - 1) = 10;
  v6 = (void *)(v16 + v14 + *((_QWORD *)a3 + 8));
  if ( !v11 )
  {
LABEL_18:
    std::vector<unsigned char>::~vector<unsigned char>(Buf2);
     = 0;
    goto LABEL_36;
  }
  if ( v6 )
  {
    _mm_lfence();
    v7 = v11;
    if ( v10 )
    {
      memcpy(v6, v10, v11);
      goto LABEL_18;
    }
    goto LABEL_19;
  }
LABEL_20:
  *_errno() = 22;
  _invalid_parameter_noinfo();
  v18 = -2147418113;
LABEL_21:
  std::vector<unsigned char>::~vector<unsigned char>(Buf2);
   = v18;
  goto LABEL_36;
}

```

## disassembly

```asm
0x180023d04  push    rbx
0x180023d06  push    rsi
0x180023d07  push    rdi
0x180023d08  push    r14
0x180023d0a  push    r15
0x180023d0c  sub     rsp, 60h
0x180023d10  mov     r15, r8
0x180023d13  mov     rdi, rdx
0x180023d16  xor     eax, eax
0x180023d18  xorps   xmm1, xmm1
0x180023d1b  movdqu  xmmword ptr [rsp+88h+Buf2], xmm1
0x180023d21  mov     [rsp+88h+var_40], rax
0x180023d26  mov     ebx, ecx
0x180023d28  mov     edx, ecx
0x180023d2a  lea     rcx, [rsp+88h+Buf2]
0x180023d2f  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180023d34  nop
0x180023d35  test    rbx, rbx
0x180023d38  jz      short loc_180023D5D
0x180023d3a  mov     rcx, [rsp+88h+Buf2]; void *
0x180023d3f  test    rcx, rcx
0x180023d42  jz      loc_180023F27
0x180023d48  mov     r8, rbx; Size
0x180023d4b  test    rdi, rdi
0x180023d4e  jz      loc_180023F1F
0x180023d54  mov     rdx, rdi; Src
0x180023d57  call    cs:__imp_memcpy
0x180023d5d  mov     ecx, cs:_tls_index
0x180023d63  mov     rax, gs:58h
0x180023d6c  mov     edx, 4
0x180023d71  mov     rax, [rax+rcx*8]
0x180023d75  mov     ecx, [rdx+rax]
0x180023d78  cmp     cs:dword_180077A08, ecx
0x180023d7e  jle     loc_180023E4F
0x180023d84  lea     rcx, dword_180077A08
0x180023d8b  call    _Init_thread_header
0x180023d90  cmp     cs:dword_180077A08, 0FFFFFFFFh
0x180023d97  jnz     loc_180023E4F
0x180023d9d  mov     [rsp+88h+Src], 746C6946h
0x180023da5  mov     [rsp+88h+var_64], 6E417265h
0x180023dad  mov     [rsp+88h+var_60], 79615064h
0x180023db5  mov     [rsp+88h+var_5C], 64616F6Ch
0x180023dbd  mov     [rsp+88h+var_58], 63657053h
0x180023dc5  mov     [rsp+88h+var_54], 73h ; 's'
0x180023dcc  xorps   xmm0, xmm0
0x180023dcf  movdqu  cs:Buf1, xmm0
0x180023dd7  mov     cs:qword_180077A20, 0
0x180023de2  lfence
0x180023de5  mov     ecx, 16h
0x180023dea  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180023def  mov     qword ptr cs:Buf1, rax
0x180023df6  mov     qword ptr cs:Buf1+8, rax
0x180023dfd  lea     rbx, [rax+16h]
0x180023e01  mov     cs:qword_180077A20, rbx
0x180023e08  mov     r8d, 16h; Size
0x180023e0e  lea     rdx, [rsp+88h+Src]; Src
0x180023e13  mov     rcx, rax; void *
0x180023e16  call    cs:__imp_memmove
0x180023e1c  mov     qword ptr cs:Buf1+8, rbx
0x180023e23  mov     [rsp+88h+var_38], 0
0x180023e2c  lea     rcx, [rsp+88h+var_38]
0x180023e31  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x180023e36  lea     rcx, _Microsoft__DiagnosticsHub__StandardCollector__EtwCollectionSessionController__MergeSchematizedFilter____2____dynamic_atexit_destructor_for__filterHeader__; void (__cdecl *)()
0x180023e3d  call    atexit
0x180023e42  nop
0x180023e43  lea     rcx, dword_180077A08
0x180023e4a  call    _Init_thread_footer
0x180023e4f  mov     rdi, [rsp+88h+Buf2]
0x180023e54  mov     rbx, [rsp+88h+Buf2+8]
0x180023e59  sub     rbx, rdi
0x180023e5c  mov     r8, qword ptr cs:Buf1+8
0x180023e63  mov     rcx, qword ptr cs:Buf1; Buf1
0x180023e6a  sub     r8, rcx; Size
0x180023e6d  cmp     rbx, r8
0x180023e70  jbe     short loc_180023E96
0x180023e72  lfence
0x180023e75  mov     rdx, rdi; Buf2
0x180023e78  call    cs:__imp_memcmp
0x180023e7e  test    eax, eax
0x180023e80  jnz     short loc_180023E96
0x180023e82  mov     rax, qword ptr cs:Buf1+8
0x180023e89  sub     rax, qword ptr cs:Buf1
0x180023e90  add     rdi, rax
0x180023e93  sub     rbx, rax
0x180023e96  mov     rax, [r15+40h]
0x180023e9a  mov     r14, [r15+48h]
0x180023e9e  sub     r14, rax
0x180023ea1  lea     rcx, [r14-1]
0x180023ea5  cmp     r14, rcx
0x180023ea8  jbe     loc_180023F6E
0x180023eae  lfence
0x180023eb1  mov     al, [rax+rcx]
0x180023eb4  neg     al
0x180023eb6  sbb     rsi, rsi
0x180023eb9  neg     rsi
0x180023ebc  inc     rsi
0x180023ebf  lea     rdx, [r14+rsi]
0x180023ec3  add     rdx, rbx
0x180023ec6  lea     rcx, [r15+40h]
0x180023eca  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180023ecf  nop
0x180023ed0  mov     rcx, [r15+40h]
0x180023ed4  add     rcx, r14
0x180023ed7  mov     byte ptr [rcx+rsi-2], 0Dh
0x180023edc  mov     rcx, [r15+40h]
0x180023ee0  add     rcx, r14
0x180023ee3  mov     byte ptr [rcx+rsi-1], 0Ah
0x180023ee8  mov     rcx, [r15+40h]
0x180023eec  add     rcx, r14
0x180023eef  add     rcx, rsi; void *
0x180023ef2  test    rbx, rbx
0x180023ef5  jz      short loc_180023F11
0x180023ef7  test    rcx, rcx
0x180023efa  jz      short loc_180023F27
0x180023efc  lfence
0x180023eff  mov     r8, rbx; Size
0x180023f02  test    rdi, rdi
0x180023f05  jz      short loc_180023F1F
0x180023f07  mov     rdx, rdi; Src
0x180023f0a  call    cs:__imp_memcpy
0x180023f10  nop
0x180023f11  lea     rcx, [rsp+88h+Buf2]
0x180023f16  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180023f1b  xor     eax, eax
0x180023f1d  jmp     short loc_180023F62
0x180023f1f  xor     edx, edx; Val
0x180023f21  call    cs:__imp_memset
0x180023f27  call    cs:__imp__errno
0x180023f2d  mov     dword ptr [rax], 16h
0x180023f33  call    cs:__imp__invalid_parameter_noinfo
0x180023f39  mov     ebx, 8000FFFFh
0x180023f3e  jmp     short loc_180023F45
0x180023f40  mov     ebx, 8007000Eh
0x180023f45  lea     rcx, [rsp+88h+Buf2]
0x180023f4a  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180023f4f  mov     eax, ebx
0x180023f51  jmp     short loc_180023F62
0x180023f53  lea     rcx, [rsp+88h+Buf2]
0x180023f58  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180023f5d  mov     eax, 8007000Eh
0x180023f62  add     rsp, 60h
0x180023f66  pop     r15
0x180023f68  pop     r14
0x180023f6a  pop     rdi
0x180023f6b  pop     rsi
0x180023f6c  pop     rbx
0x180023f6d  retn
0x180023f6e  call    ?_Xrange@?$vector@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@CAXXZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xrange(void)
```
