# StructuredQuery1::ParseKeywords(wchar_t const *,StructuredQuery1::Tokenizer *,wchar_t * * *,ulong *)

- ea: `0x18001ebc4`
- end: `0x18001ee5a`
- name: `?ParseKeywords@StructuredQuery1@@YAJPEB_WPEAVTokenizer@1@PEAPEAPEA_WPEAK@Z`
- size: `662`
- prototype: `__int64 __fastcall(wchar_t *this, const wchar_t *, struct StructuredQuery1::Tokenizer *, wchar_t ***, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001e940`

## callees

- `0x18000bec0`
- `0x180015a40`
- `0x18001ebc4`
- `0x18001ee60`
- `0x18001efa4`
- `0x1800204f4`
- `0x180059920`
- `0x18005db14`
- `0x18005e048`
- `0x18005e740`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!GetStringTypeW` at `0x18001ec47`
- `api-ms-win-core-string-l1-1-0!GetStringTypeW` at `0x18001ec47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001eca8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001eca8`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::ParseKeywords(
        wchar_t *this,
        wchar_t *a2,
        struct StructuredQuery1::Tokenizer *a3,
        wchar_t ***a4)
{
  wchar_t ***v4; // r13
  __int64 v6; // rsi
  void *v8; // rdi
  unsigned int v9; // ebp
  unsigned __int64 v10; // rax
  WORD *v11; // rax
  WORD *v12; // r12
  const struct std::nothrow_t *v13; // rdx
  unsigned __int128 v14; // rax
  int Error; // ebx
  struct SemanticsUM::TokenCollectionUM *v16; // r14
  size_t v17; // rax
  unsigned int v18; // r15d
  __int64 v19; // rsi
  __int64 v20; // rax
  __int64 v21; // rdx
  int v22; // eax
  wchar_t *v23; // rcx
  __int64 v24; // rdx
  unsigned int v25; // ebx
  int v26; // eax
  __int64 v27; // rdx
  wchar_t **v28; // r8
  __int64 result; // rax
  const size_t *v30; // r8
  int v31; // [rsp+20h] [rbp-58h]
  struct SemanticsUM::TokenCollectionUM *v32; // [rsp+30h] [rbp-48h] BYREF

  v4 = a4;
  v6 = -1;
  v8 = 0;
  v9 = 0;
  do
    ++v6;
  while ( this[v6] );
  v10 = 2LL * (unsigned int)(v6 + 1);
  if ( !is_mul_ok((unsigned int)(v6 + 1), 2u) )
    v10 = -1;
  v11 = (WORD *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  if ( !v11 )
  {
    Error = -2147024882;
    goto LABEL_25;
  }
  if ( (_DWORD)v6 == -1 )
  {
    Error = 0;
    goto LABEL_30;
  }
  if ( !GetStringTypeW(1u, this, v6 + 1, v11) )
  {
    operator delete(v12, v13);
    v12 = 0;
    Error = ResultFromKnownLastError();
LABEL_30:
    if ( Error < 0 )
      goto LABEL_25;
  }
  v32 = 0;
  Error = StructuredQuery1::Tokenizer::TokenizeWorker((StructuredQuery1::Tokenizer *)a2, this, v12, v6, &v32);
  if ( Error >= 0 )
  {
    v16 = v32;
    v9 = (**(__int64 (__fastcall ***)(struct SemanticsUM::TokenCollectionUM *))v32)(v32);
    v14 = v9 * (unsigned __int128)8u;
    if ( !is_mul_ok(v9, 8u) )
    {
      Error = -2147024362;
      goto LABEL_22;
    }
    *(_QWORD *)&v14 = CoTaskMemAlloc(8LL * v9);
    v8 = (void *)v14;
    if ( (_QWORD)v14 )
    {
      v17 = CTCoAllocPolicy::_CoTaskMemSize((void *)v14);
      memset_0(v8, 0, v17);
      Error = 0;
    }
    else
    {
      Error = -2147024882;
    }
    if ( Error >= 0 )
    {
      v18 = 0;
      while ( 1 )
      {
        if ( v18 >= v9 )
        {
LABEL_21:
          v4 = a4;
          goto LABEL_22;
        }
        v19 = *((_QWORD *)v16 + 2) + 40LL * v18;
        v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 32LL))(v19);
        v21 = *(_QWORD *)v19;
        if ( v20 )
          break;
        if ( (*(unsigned int (__fastcall **)(__int64))(v21 + 16))(v19) == 1 )
        {
          v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
          v23 = this;
          v24 = 8211;
          if ( this[v22] == 8211 )
          {
            v30 = (const size_t *)L"-";
LABEL_28:
            LODWORD(v14) = _AllocString<CTCoAllocPolicy>((__int64)v23, v24, v30, (_QWORD *)v8 + v18);
            goto LABEL_19;
          }
        }
        v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
        LODWORD(v14) = _AllocStringWorker<CTCoAllocPolicy>(
                         (__int64)this,
                         v27,
                         (const size_t *)&this[v26],
                         v25,
                         v31,
                         (_QWORD *)v8 + v18);
LABEL_19:
        ++v18;
        Error = v14;
        if ( (v14 & 0x80000000) != 0LL )
        {
          StructuredQuery1::ClearStringArray((StructuredQuery1 *)v9, (LPVOID *)v8, v28);
          v9 = 0;
          v8 = 0;
          goto LABEL_21;
        }
      }
      v30 = (const size_t *)(*(__int64 (__fastcall **)(__int64))(v21 + 32))(v19);
      goto LABEL_28;
    }
LABEL_22:
    if ( v16 )
      (*(void (__fastcall **)(struct SemanticsUM::TokenCollectionUM *, __int64))(*(_QWORD *)v16 + 16LL))(v16, 1);
  }
  operator delete(v12, *((const struct std::nothrow_t **)&v14 + 1));
LABEL_25:
  *(_QWORD *)a3 = v8;
  result = (unsigned int)Error;
  *(_DWORD *)v4 = v9;
  return result;
}

```

## disassembly

```asm
0x18001ebc4  mov     rax, rsp
0x18001ebc7  mov     [rax+10h], rbx
0x18001ebcb  mov     [rax+20h], r9
0x18001ebcf  mov     [rax+18h], r8
0x18001ebd3  mov     [rax+8], rcx
0x18001ebd7  push    rbp
0x18001ebd8  push    rsi
0x18001ebd9  push    rdi
0x18001ebda  push    r12
0x18001ebdc  push    r13
0x18001ebde  push    r14
0x18001ebe0  push    r15
0x18001ebe2  sub     rsp, 40h
0x18001ebe6  xor     eax, eax
0x18001ebe8  mov     r13, r9
0x18001ebeb  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001ebef  mov     r15, rdx
0x18001ebf2  mov     rsi, r8
0x18001ebf5  mov     r14, rcx
0x18001ebf8  mov     edi, eax
0x18001ebfa  mov     ebp, eax
0x18001ebfc  inc     rsi
0x18001ebff  cmp     [rcx+rsi*2], ax
0x18001ec03  jnz     short loc_18001EBFC
0x18001ec05  lea     ebx, [rsi+1]
0x18001ec08  mov     eax, 2
0x18001ec0d  mov     ecx, ebx
0x18001ec0f  mul     rcx
0x18001ec12  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ec19  cmovb   rax, r8
0x18001ec1d  mov     rcx, rax; unsigned __int64
0x18001ec20  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001ec25  mov     r12, rax
0x18001ec28  test    rax, rax
0x18001ec2b  jz      loc_18001EDFD
0x18001ec31  test    ebx, ebx
0x18001ec33  jz      loc_18001EE19
0x18001ec39  mov     r9, rax; lpCharType
0x18001ec3c  mov     r8d, ebx; cchSrc
0x18001ec3f  mov     rdx, r14; lpSrcStr
0x18001ec42  mov     ecx, 1; dwInfoType
0x18001ec47  call    cs:__imp_GetStringTypeW
0x18001ec4d  test    eax, eax
0x18001ec4f  jz      loc_18001EE24
0x18001ec55  lea     rax, [rsp+78h+var_48]
0x18001ec5a  mov     [rsp+78h+var_48], rdi
0x18001ec5f  mov     r9d, esi; unsigned int
0x18001ec62  mov     [rsp+78h+var_58], rax; struct SemanticsUM::TokenCollectionUM **
0x18001ec67  mov     r8, r12; unsigned __int16 *
0x18001ec6a  mov     rdx, r14; wchar_t *
0x18001ec6d  mov     rcx, r15; this
0x18001ec70  call    ?TokenizeWorker@Tokenizer@StructuredQuery1@@AEAAJPEB_WPEBGKPEAPEAVTokenCollectionUM@SemanticsUM@@_N@Z; StructuredQuery1::Tokenizer::TokenizeWorker(wchar_t const *,ushort const *,ulong,SemanticsUM::TokenCollectionUM * *,bool)
0x18001ec75  xor     esi, esi
0x18001ec77  mov     ebx, eax
0x18001ec79  test    eax, eax
0x18001ec7b  js      loc_18001EDCC
0x18001ec81  mov     r14, [rsp+78h+var_48]
0x18001ec86  mov     rcx, r14
0x18001ec89  mov     rax, [r14]
0x18001ec8c  mov     rax, [rax]
0x18001ec8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec94  mov     ebp, eax
0x18001ec96  lea     eax, [rsi+8]
0x18001ec99  mul     rbp
0x18001ec9c  test    rdx, rdx
0x18001ec9f  jnz     loc_18001EE50
0x18001eca5  mov     rcx, rax; cb
0x18001eca8  call    cs:__imp_CoTaskMemAlloc
0x18001ecae  mov     rdi, rax
0x18001ecb1  test    rax, rax
0x18001ecb4  jz      loc_18001EE38
0x18001ecba  mov     rcx, rax; void *
0x18001ecbd  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18001ecc2  mov     r8, rax; Size
0x18001ecc5  xor     edx, edx; Val
0x18001ecc7  mov     rcx, rdi; void *
0x18001ecca  call    memset_0
0x18001eccf  mov     ebx, esi
0x18001ecd1  test    ebx, ebx
0x18001ecd3  js      loc_18001EDB3
0x18001ecd9  mov     r15d, esi
0x18001ecdc  cmp     r15d, ebp
0x18001ecdf  jnb     loc_18001EDAB
0x18001ece5  mov     rax, [r14+10h]
0x18001ece9  mov     r13d, r15d
0x18001ecec  lea     rcx, ds:0[r13*4]
0x18001ecf4  add     rcx, r13
0x18001ecf7  lea     rsi, [rax+rcx*8]
0x18001ecfb  mov     rax, [rsi]
0x18001ecfe  mov     rcx, rsi
0x18001ed01  mov     rax, [rax+20h]
0x18001ed05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed0a  mov     rdx, [rsi]
0x18001ed0d  mov     rcx, rsi
0x18001ed10  test    rax, rax
0x18001ed13  jnz     loc_18001EE42
0x18001ed19  mov     rax, [rdx+10h]
0x18001ed1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed22  cmp     eax, 1
0x18001ed25  jnz     short loc_18001ED4F
0x18001ed27  mov     rax, [rsi]
0x18001ed2a  mov     rcx, rsi
0x18001ed2d  mov     rax, [rax+8]
0x18001ed31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed36  mov     rcx, [rsp+78h+arg_0]
0x18001ed3e  mov     edx, 2013h
0x18001ed43  mov     eax, eax
0x18001ed45  cmp     [rcx+rax*2], dx
0x18001ed49  jz      loc_18001EE04
0x18001ed4f  mov     rax, [rsi]
0x18001ed52  mov     rcx, rsi
0x18001ed55  mov     rax, [rax+10h]
0x18001ed59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed5e  mov     ebx, eax
0x18001ed60  mov     rcx, rsi
0x18001ed63  mov     rax, [rsi]
0x18001ed66  mov     rax, [rax+8]
0x18001ed6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed6f  mov     rcx, [rsp+78h+arg_0]
0x18001ed77  mov     r9d, ebx
0x18001ed7a  mov     eax, eax
0x18001ed7c  lea     r8, [rcx+rax*2]
0x18001ed80  lea     rax, [rdi+r13*8]
0x18001ed84  mov     [rsp+78h+var_50], rax
0x18001ed89  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEB_W_K2PEAPEA_W@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,wchar_t const *,unsigned __int64,unsigned __int64,wchar_t * *)
0x18001ed8e  inc     r15d
0x18001ed91  xor     esi, esi
0x18001ed93  mov     ebx, eax
0x18001ed95  test    eax, eax
0x18001ed97  jns     loc_18001ECDC
0x18001ed9d  mov     rdx, rdi; unsigned int
0x18001eda0  mov     ecx, ebp; this
0x18001eda2  call    ?ClearStringArray@StructuredQuery1@@YAXKPEAPEA_W@Z; StructuredQuery1::ClearStringArray(ulong,wchar_t * *)
0x18001eda7  mov     ebp, esi
0x18001eda9  mov     edi, esi
0x18001edab  mov     r13, [rsp+78h+arg_18]
0x18001edb3  test    r14, r14
0x18001edb6  jz      short loc_18001EDCC
0x18001edb8  mov     rax, [r14]
0x18001edbb  mov     edx, 1
0x18001edc0  mov     rcx, r14
0x18001edc3  mov     rax, [rax+10h]
0x18001edc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edcc  mov     rcx, r12; void *
0x18001edcf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001edd4  mov     rax, [rsp+78h+arg_10]
0x18001eddc  mov     [rax], rdi
0x18001eddf  mov     eax, ebx
0x18001ede1  mov     rbx, [rsp+78h+arg_8]
0x18001ede9  mov     [r13+0], ebp
0x18001eded  add     rsp, 40h
0x18001edf1  pop     r15
0x18001edf3  pop     r14
0x18001edf5  pop     r13
0x18001edf7  pop     r12
0x18001edf9  pop     rdi
0x18001edfa  pop     rsi
0x18001edfb  pop     rbp
0x18001edfc  retn
0x18001edfd  mov     ebx, 8007000Eh
0x18001ee02  jmp     short loc_18001EDD4
0x18001ee04  lea     r8, asc_18009AAB8; "-"
0x18001ee0b  lea     r9, [rdi+r13*8]
0x18001ee0f  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x18001ee14  jmp     loc_18001ED8E
0x18001ee19  xor     ebx, ebx
0x18001ee1b  test    ebx, ebx
0x18001ee1d  js      short loc_18001EDD4
0x18001ee1f  jmp     loc_18001EC55
0x18001ee24  mov     rcx, r12; void *
0x18001ee27  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ee2c  xor     r12d, r12d
0x18001ee2f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001ee34  mov     ebx, eax
0x18001ee36  jmp     short loc_18001EE1B
0x18001ee38  mov     ebx, 8007000Eh
0x18001ee3d  jmp     loc_18001ECD1
0x18001ee42  mov     rax, [rdx+20h]
0x18001ee46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee4b  mov     r8, rax
0x18001ee4e  jmp     short loc_18001EE0B
0x18001ee50  mov     ebx, 80070216h
0x18001ee55  jmp     loc_18001EDB3
```
