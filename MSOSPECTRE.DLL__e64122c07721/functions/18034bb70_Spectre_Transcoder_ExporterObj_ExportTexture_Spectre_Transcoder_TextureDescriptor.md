# Spectre::Transcoder::ExporterObj::ExportTexture(Spectre::Transcoder::TextureDescriptor &)

- ea: `0x18034bb70`
- end: `0x18034be24`
- name: `?ExportTexture@ExporterObj@Transcoder@Spectre@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAVTextureDescriptor@23@@Z`
- size: `692`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18034ab30`

## callees

- `0x18003eb90`
- `0x1800eb2a0`
- `0x18034bb70`
- `0x18034be70`
- `0x18039e5b0`
- `0x18039ebb0`
- `0x180490f10`
- `0x1804f99e0`

## import_xrefs

- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x18034bd17`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x18034bd17`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18034bc63`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18034bdb1`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18034bdfb`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18034bc63`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18034bdb1`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18034bdfb`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_OWORD *__fastcall Spectre::Transcoder::ExporterObj::ExportTexture(__int64 a1, _OWORD *a2, _DWORD *a3)
{
  _QWORD *UniqueName; // r10
  __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  char *v9; // rax
  void *v10; // rcx
  volatile signed __int32 *v11; // rdi
  void *v12; // rcx
  void *v13; // rcx
  _OWORD *v15; // [rsp+30h] [rbp-59h] BYREF
  void *Block[3]; // [rsp+38h] [rbp-51h] BYREF
  unsigned __int64 v17; // [rsp+50h] [rbp-39h]
  _BYTE v18[16]; // [rsp+58h] [rbp-31h] BYREF
  void *v19[2]; // [rsp+68h] [rbp-21h] BYREF
  __int128 v20; // [rsp+78h] [rbp-11h]
  void *v21[2]; // [rsp+88h] [rbp-1h] BYREF
  __int64 v22; // [rsp+98h] [rbp+Fh]
  __int128 v23; // [rsp+A0h] [rbp+17h] BYREF

  v15 = a2;
  UniqueName = (_QWORD *)Spectre::Transcoder::ExporterObj::GetUniqueName(a1, Block);
  v7 = UniqueName[2];
  v8 = UniqueName[3];
  if ( v8 - v7 < 4 )
  {
    UniqueName = (_QWORD *)std::string::_Reallocate_grow_by<_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64>(
                             UniqueName,
                             4u);
  }
  else
  {
    UniqueName[2] = v7 + 4;
    v9 = (char *)UniqueName;
    if ( v8 >= 0x10 )
      v9 = (char *)*UniqueName;
    strcpy(&v9[v7], ".png");
  }
  v19[0] = 0;
  v20 = 0u;
  *(_OWORD *)v19 = *(_OWORD *)UniqueName;
  v20 = *((_OWORD *)UniqueName + 1);
  UniqueName[2] = 0;
  UniqueName[3] = 15;
  *(_BYTE *)UniqueName = 0;
  if ( v17 >= 0x10 )
  {
    v10 = Block[0];
    if ( v17 + 1 >= 0x1000 )
    {
      v10 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v10 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v10);
  }
  Block[2] = 0;
  v17 = 15;
  LOBYTE(Block[0]) = 0;
  LODWORD(v15) = a3[2];
  std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::emplace<unsigned int const &>(
    a1 + 264,
    v18,
    &v15);
  if ( v18[8] )
  {
    *(_OWORD *)v21 = 0;
    v22 = 0;
    Spectre::Transcoder::TextureDescriptor::EncodeTo((__int64)a3, (__int64)v21, 1u, 4, a3[28], a3[27]);
    v23 = 0;
    (*(void (__fastcall **)(_QWORD, __int128 *, void **))(**(_QWORD **)(a1 + 144) + 8LL))(
      *(_QWORD *)(a1 + 144),
      &v23,
      v19);
    std::ostream::write(v23, v21[0], (char *)v21[1] - (char *)v21[0]);
    *a2 = *(_OWORD *)v19;
    a2[1] = v20;
    *(_QWORD *)&v20 = 0;
    *((_QWORD *)&v20 + 1) = 15;
    LOBYTE(v19[0]) = 0;
    v11 = (volatile signed __int32 *)*((_QWORD *)&v23 + 1);
    if ( *((_QWORD *)&v23 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v23 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
    v12 = v21[0];
    if ( v21[0] )
    {
      if ( v22 - (unsigned __int64)v21[0] >= 0x1000 )
      {
        v12 = (void *)*((_QWORD *)v21[0] - 1);
        if ( (unsigned __int64)((char *)v21[0] - (char *)v12 - 8) > 0x1F )
          _invalid_parameter_noinfo_noreturn();
      }
      operator delete(v12);
      *(_OWORD *)v21 = 0;
      v22 = 0;
    }
    if ( *((_QWORD *)&v20 + 1) >= 0x10u )
    {
      v13 = v19[0];
      if ( (unsigned __int64)(*((_QWORD *)&v20 + 1) + 1LL) >= 0x1000 )
      {
        v13 = (void *)*((_QWORD *)v19[0] - 1);
        if ( (unsigned __int64)((char *)v19[0] - (char *)v13 - 8) > 0x1F )
          _invalid_parameter_noinfo_noreturn();
      }
      operator delete(v13);
    }
  }
  else
  {
    *a2 = *(_OWORD *)v19;
    a2[1] = v20;
  }
  return a2;
}

```

## disassembly

```asm
0x18034bb70  push    rbp
0x18034bb72  push    rbx
0x18034bb73  push    rsi
0x18034bb74  push    rdi
0x18034bb75  push    r14
0x18034bb77  lea     rbp, [rsp-37h]
0x18034bb7c  sub     rsp, 0C0h
0x18034bb83  mov     rax, cs:__security_cookie
0x18034bb8a  xor     rax, rsp
0x18034bb8d  mov     [rbp+57h+var_30], rax
0x18034bb91  mov     rdi, r8
0x18034bb94  mov     rbx, rdx
0x18034bb97  mov     rsi, rcx
0x18034bb9a  mov     [rbp+57h+var_B0], rdx
0x18034bb9e  lea     rdx, [rbp+57h+Block]
0x18034bba2  call    ?GetUniqueName@ExporterObj@Transcoder@Spectre@@IEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVITraversableWithName@23@@Z; Spectre::Transcoder::ExporterObj::GetUniqueName(Spectre::Transcoder::ITraversableWithName const &)
0x18034bba7  mov     r10, rax
0x18034bbaa  mov     rcx, [rax+10h]
0x18034bbae  mov     rdx, [rax+18h]
0x18034bbb2  mov     rax, rdx
0x18034bbb5  sub     rax, rcx
0x18034bbb8  cmp     rax, 4
0x18034bbbc  jb      short loc_18034BBE0
0x18034bbbe  lea     rax, [rcx+4]
0x18034bbc2  mov     [r10+10h], rax
0x18034bbc6  mov     rax, r10
0x18034bbc9  cmp     rdx, 10h
0x18034bbcd  jb      short loc_18034BBD2
0x18034bbcf  mov     rax, [r10]
0x18034bbd2  mov     dword ptr [rax+rcx], 676E702Eh
0x18034bbd9  mov     byte ptr [rax+rcx+4], 0
0x18034bbde  jmp     short loc_18034BC02
0x18034bbe0  mov     [rsp+0E0h+Size], 4; Size
0x18034bbe9  lea     r9, aPng_0; ".png"
0x18034bbf0  xor     r8d, r8d
0x18034bbf3  lea     edx, [r8+4]
0x18034bbf7  mov     rcx, r10; Src
0x18034bbfa  call    ??$_Reallocate_grow_by@V_lambda_65e615be2a453ca0576c979606f46740_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_65e615be2a453ca0576c979606f46740_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64>(unsigned __int64,_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64)
0x18034bbff  mov     r10, rax
0x18034bc02  xor     r14d, r14d
0x18034bc05  mov     [rbp+57h+var_78], r14
0x18034bc09  mov     qword ptr [rbp+57h+var_68], r14
0x18034bc0d  mov     qword ptr [rbp+57h+var_68+8], r14
0x18034bc11  movups  xmm0, xmmword ptr [r10]
0x18034bc15  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x18034bc19  movups  xmm1, xmmword ptr [r10+10h]
0x18034bc1e  movups  [rbp+57h+var_68], xmm1
0x18034bc22  mov     [r10+10h], r14
0x18034bc26  mov     qword ptr [r10+18h], 0Fh
0x18034bc2e  mov     [r10], r14b
0x18034bc31  mov     rdx, [rbp+57h+var_90]
0x18034bc35  cmp     rdx, 10h
0x18034bc39  jb      short loc_18034BC6F
0x18034bc3b  inc     rdx
0x18034bc3e  mov     rcx, [rbp+57h+Block]; Block
0x18034bc42  mov     rax, rcx
0x18034bc45  cmp     rdx, 1000h
0x18034bc4c  jb      short loc_18034BC6A
0x18034bc4e  add     rdx, 27h ; '''
0x18034bc52  mov     rcx, [rcx-8]
0x18034bc56  sub     rax, rcx
0x18034bc59  add     rax, 0FFFFFFFFFFFFFFF8h
0x18034bc5d  cmp     rax, 1Fh
0x18034bc61  jbe     short loc_18034BC6A
0x18034bc63  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18034bc6a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18034bc6f  mov     [rbp+57h+var_98], r14
0x18034bc73  mov     [rbp+57h+var_90], 0Fh
0x18034bc7b  mov     byte ptr [rbp+57h+Block], 0
0x18034bc7f  mov     eax, [rdi+8]
0x18034bc82  mov     dword ptr [rbp+57h+var_B0], eax
0x18034bc85  lea     rcx, [rsi+108h]
0x18034bc8c  lea     r8, [rbp+57h+var_B0]
0x18034bc90  lea     rdx, [rbp+57h+var_88]
0x18034bc94  call    ??$emplace@AEBI@?$_Hash@V?$_Uset_traits@IV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@I@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@I@std@@@std@@@std@@_N@1@AEBI@Z; std::_Hash<std::_Uset_traits<uint,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<uint>,0>>::emplace<uint const &>(uint const &)
0x18034bc99  cmp     [rbp+57h+var_80], 0
0x18034bc9d  jnz     short loc_18034BCB3
0x18034bc9f  movups  xmm0, xmmword ptr [rbp+57h+var_78]
0x18034bca3  movups  xmmword ptr [rbx], xmm0
0x18034bca6  movups  xmm1, [rbp+57h+var_68]
0x18034bcaa  movups  xmmword ptr [rbx+10h], xmm1
0x18034bcae  jmp     loc_18034BE07
0x18034bcb3  xorps   xmm0, xmm0
0x18034bcb6  xor     eax, eax
0x18034bcb8  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x18034bcbc  mov     [rbp+57h+var_48], rax
0x18034bcc0  mov     eax, [rdi+6Ch]
0x18034bcc3  mov     edx, [rdi+70h]
0x18034bcc6  mov     [rsp+0E0h+var_B8], eax
0x18034bcca  mov     dword ptr [rsp+0E0h+Size], edx
0x18034bcce  mov     r9d, 4
0x18034bcd4  mov     r8b, 1
0x18034bcd7  lea     rdx, [rbp+57h+var_58]
0x18034bcdb  mov     rcx, rdi
0x18034bcde  call    ?EncodeTo@TextureDescriptor@Transcoder@Spectre@@QEBA?AV?$vector@EV?$allocator@E@std@@@std@@W4TextureContainer@23@W4EFormat@TextureSegment@Framework@3@II@Z; Spectre::Transcoder::TextureDescriptor::EncodeTo(Spectre::Transcoder::TextureContainer,Spectre::Framework::TextureSegment::EFormat,uint,uint)
0x18034bce3  nop
0x18034bce4  xorps   xmm0, xmm0
0x18034bce7  movups  [rbp+57h+var_40], xmm0
0x18034bceb  mov     rcx, [rsi+90h]
0x18034bcf2  mov     rax, [rcx]
0x18034bcf5  lea     r8, [rbp+57h+var_78]
0x18034bcf9  lea     rdx, [rbp+57h+var_40]
0x18034bcfd  mov     rax, [rax+8]
0x18034bd01  call    cs:__guard_dispatch_icall_fptr
0x18034bd07  nop
0x18034bd08  mov     r8, [rbp+57h+var_58+8]
0x18034bd0c  mov     rdx, [rbp+57h+var_58]
0x18034bd10  sub     r8, rdx
0x18034bd13  mov     rcx, qword ptr [rbp+57h+var_40]
0x18034bd17  call    cs:__imp_?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z; std::ostream::write(char const *,__int64)
0x18034bd1d  movups  xmm0, xmmword ptr [rbp+57h+var_78]
0x18034bd21  movups  xmmword ptr [rbx], xmm0
0x18034bd24  movups  xmm1, [rbp+57h+var_68]
0x18034bd28  movups  xmmword ptr [rbx+10h], xmm1
0x18034bd2c  mov     qword ptr [rbp+57h+var_68], r14
0x18034bd30  mov     qword ptr [rbp+57h+var_68+8], 0Fh
0x18034bd38  mov     byte ptr [rbp+57h+var_78], 0
0x18034bd3c  mov     rdi, qword ptr [rbp+57h+var_40+8]
0x18034bd40  test    rdi, rdi
0x18034bd43  jz      short loc_18034BD80
0x18034bd45  mov     esi, 0FFFFFFFFh
0x18034bd4a  mov     eax, esi
0x18034bd4c  lock xadd [rdi+8], eax
0x18034bd51  cmp     eax, 1
0x18034bd54  jnz     short loc_18034BD80
0x18034bd56  mov     rax, [rdi]
0x18034bd59  mov     rcx, rdi
0x18034bd5c  mov     rax, [rax]
0x18034bd5f  call    cs:__guard_dispatch_icall_fptr
0x18034bd65  lock xadd [rdi+0Ch], esi
0x18034bd6a  cmp     esi, 1
0x18034bd6d  jnz     short loc_18034BD80
0x18034bd6f  mov     rax, [rdi]
0x18034bd72  mov     rcx, rdi
0x18034bd75  mov     rax, [rax+8]
0x18034bd79  call    cs:__guard_dispatch_icall_fptr
0x18034bd7f  nop
0x18034bd80  mov     rcx, [rbp+57h+var_58]; Block
0x18034bd84  test    rcx, rcx
0x18034bd87  jz      short loc_18034BDC9
0x18034bd89  mov     rdx, [rbp+57h+var_48]
0x18034bd8d  sub     rdx, rcx
0x18034bd90  mov     rax, rcx
0x18034bd93  cmp     rdx, 1000h
0x18034bd9a  jb      short loc_18034BDB8
0x18034bd9c  add     rdx, 27h ; '''
0x18034bda0  mov     rcx, [rcx-8]
0x18034bda4  sub     rax, rcx
0x18034bda7  add     rax, 0FFFFFFFFFFFFFFF8h
0x18034bdab  cmp     rax, 1Fh
0x18034bdaf  jbe     short loc_18034BDB8
0x18034bdb1  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18034bdb8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18034bdbd  xorps   xmm0, xmm0
0x18034bdc0  movdqu  xmmword ptr [rbp+57h+var_58], xmm0
0x18034bdc5  mov     [rbp+57h+var_48], r14
0x18034bdc9  mov     rdx, qword ptr [rbp+57h+var_68+8]
0x18034bdcd  cmp     rdx, 10h
0x18034bdd1  jb      short loc_18034BE07
0x18034bdd3  inc     rdx
0x18034bdd6  mov     rcx, [rbp+57h+var_78]; Block
0x18034bdda  mov     rax, rcx
0x18034bddd  cmp     rdx, 1000h
0x18034bde4  jb      short loc_18034BE02
0x18034bde6  add     rdx, 27h ; '''
0x18034bdea  mov     rcx, [rcx-8]
0x18034bdee  sub     rax, rcx
0x18034bdf1  add     rax, 0FFFFFFFFFFFFFFF8h
0x18034bdf5  cmp     rax, 1Fh
0x18034bdf9  jbe     short loc_18034BE02
0x18034bdfb  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18034be02  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18034be07  mov     rax, rbx
0x18034be0a  mov     rcx, [rbp+57h+var_30]
0x18034be0e  xor     rcx, rsp; StackCookie
0x18034be11  call    __security_check_cookie
0x18034be16  add     rsp, 0C0h
0x18034be1d  pop     r14
0x18034be1f  pop     rdi
0x18034be20  pop     rsi
0x18034be21  pop     rbx
0x18034be22  pop     rbp
0x18034be23  retn
```
