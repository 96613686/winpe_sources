# CAudioStream::SaveStreamGroupCreationParameters(StreamGroupParams *,MODE_PARAMS *)

- ea: `0x18000d570`
- end: `0x18000d8d4`
- name: `?SaveStreamGroupCreationParameters@CAudioStream@@UEAAJPEAUStreamGroupParams@@PEAUMODE_PARAMS@@@Z`
- size: `868`
- prototype: `__int64 __fastcall(CAudioStream *__hidden this, struct StreamGroupParams *, struct MODE_PARAMS *)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000ca50`
- `0x18000cab0`
- `0x18000cae0`
- `0x18000cb10`
- `0x18000d570`
- `0x18000d8dc`
- `0x18000da80`
- `0x18000e134`
- `0x18000e1c4`
- `0x1800126bc`
- `0x180032e9c`
- `0x1800cfd60`
- `0x1800cfd9c`
- `0x1800d074c`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d652`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d652`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d75f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d786`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d803`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d75f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d786`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d803`

## string_xrefs

- `0x18000d74b`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x18000d7bb`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x18000d7ea`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x18000d82c`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x18000d86b`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAudioStream::SaveStreamGroupCreationParameters(
        CAudioStream *this,
        struct StreamGroupParams *a2,
        struct MODE_PARAMS *a3)
{
  int v6; // ebx
  struct StreamGroupParams *v7; // rdx
  MODE_PARAMS *v8; // rax
  __int64 v9; // rcx
  MODE_PARAMS *v10; // rbx
  __int64 v11; // rdi
  void *v12; // rsi
  unsigned __int16 *v13; // r13
  void *v14; // rax
  void *v15; // r12
  char *v16; // rax
  char *v17; // rcx
  __int64 i; // rdx
  void *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rdx
  unsigned int v23; // esi
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rcx
  int v28; // eax
  struct StreamGroupParams **v29; // [rsp+20h] [rbp-20h]
  struct StreamGroupParams *v30; // [rsp+28h] [rbp-18h] BYREF
  char v31; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  size_t Size; // [rsp+80h] [rbp+40h] BYREF
  MODE_PARAMS *v34; // [rsp+98h] [rbp+58h] BYREF

  v29 = (struct StreamGroupParams **)((char *)this + 616);
  v30 = 0;
  v31 = 1;
  v6 = StreamGroupParams::Clone(a2, &v30);
  if ( v31 )
  {
    v7 = *v29;
    *v29 = v30;
    if ( v7 )
      std::default_delete<StreamGroupParams>::operator()();
  }
  if ( v6 < 0 )
  {
    v25 = 2067;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiostream.cpp",
      (const char *)(unsigned int)v6,
      (int)v29);
    return (unsigned int)v6;
  }
  v6 = CAudioStream::SetProcessingModeParameters(this, (struct StreamGroupParams *)((char *)a2 + 56));
  if ( v6 < 0 )
  {
    v25 = 2069;
    goto LABEL_35;
  }
  if ( !a3 )
    return 0;
  v8 = (MODE_PARAMS *)operator new[](0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v8;
  if ( !v8 )
  {
    v34 = 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81B,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiostream.cpp",
      (const char *)0x8007000ELL,
      (int)v29);
    v23 = -2147024882;
LABEL_29:
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v34);
    return v23;
  }
  *(_QWORD *)v8 = 0;
  *((_QWORD *)v8 + 1) = 0;
  v34 = v8;
  v11 = *((_QWORD *)a3 + 1);
  if ( !v11 )
  {
LABEL_19:
    v21 = *((_QWORD *)this + 78);
    *((_QWORD *)this + 78) = v10;
    if ( v21 )
      std::default_delete<MODE_PARAMS>::operator()(v9, v21);
    return 0;
  }
  v12 = 0;
  Size = 0;
  if ( !*(_QWORD *)(v11 + 24) )
    goto LABEL_10;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &Size,
    0);
  v28 = _AllocString<CTCoAllocPolicy>(v27, v26, *(_QWORD *)(v11 + 24), &Size);
  v23 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x823,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiostream.cpp",
      (const char *)(unsigned int)v28,
      (int)v29);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Size);
    goto LABEL_29;
  }
  v12 = (void *)Size;
LABEL_10:
  v13 = *(unsigned __int16 **)(v11 + 16);
  Size = v13[8] + 18LL;
  v14 = CoTaskMemAlloc(Size);
  v15 = v14;
  if ( v14 )
  {
    memcpy_0(v14, v13, Size);
    v16 = (char *)operator new[](16LL * *(unsigned int *)(v11 + 64) + 68, (const struct std::nothrow_t *)&std::nothrow);
    v17 = v16;
    if ( v16 )
    {
      *(_DWORD *)v16 = *(_DWORD *)v11;
      *((_DWORD *)v16 + 1) = *(_DWORD *)(v11 + 4);
      *((_DWORD *)v16 + 2) = *(_DWORD *)(v11 + 8);
      *((_QWORD *)v16 + 2) = v15;
      *((_QWORD *)v16 + 3) = v12;
      *((_DWORD *)v16 + 8) = *(_DWORD *)(v11 + 32);
      *(_OWORD *)(v16 + 36) = *(_OWORD *)(v11 + 36);
      *((_DWORD *)v16 + 13) = *(_DWORD *)(v11 + 52);
      *((_DWORD *)v16 + 14) = *(_DWORD *)(v11 + 56);
      *((_DWORD *)v16 + 16) = *(_DWORD *)(v11 + 64);
      for ( i = 0; (unsigned int)i < *(_DWORD *)(v11 + 64); i = (unsigned int)(i + 1) )
        *(_OWORD *)&v16[16 * (unsigned int)i + 68] = *(_OWORD *)(v11 + 16LL * (unsigned int)i + 68);
      v19 = (void *)*((_QWORD *)v10 + 1);
      *((_QWORD *)v10 + 1) = v17;
      if ( v19 )
        operator delete(v19, (const struct std::nothrow_t *)0x58);
      v20 = *(_QWORD *)v10;
      *(_QWORD *)v10 = 0;
      if ( v20 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 16LL))(v20, i);
      v9 = *(_QWORD *)a3;
      if ( *(_QWORD *)a3 )
      {
        *(_QWORD *)v10 = v9;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 8LL))(v9, i);
      }
      else
      {
        *(_QWORD *)v10 = 0;
      }
      goto LABEL_19;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x82B,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiostream.cpp",
      (const char *)0x8007000ELL,
      (int)v29);
    CoTaskMemFree(v15);
    if ( v12 )
      CoTaskMemFree(v12);
    MODE_PARAMS::~MODE_PARAMS(v10);
    operator delete(v10, (const struct std::nothrow_t *)0x10);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x827,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiostream.cpp",
      (const char *)0x8007000ELL,
      (int)v29);
    if ( v12 )
      CoTaskMemFree(v12);
    std::default_delete<MODE_PARAMS>::operator()(v24, v10);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000d570  mov     [rsp-38h+arg_8], rbx
0x18000d575  push    rbp
0x18000d576  push    rsi
0x18000d577  push    rdi
0x18000d578  push    r12
0x18000d57a  push    r13
0x18000d57c  push    r14
0x18000d57e  push    r15
0x18000d580  mov     rbp, rsp
0x18000d583  sub     rsp, 40h
0x18000d587  mov     r15, r8
0x18000d58a  mov     rdi, rdx
0x18000d58d  mov     r14, rcx
0x18000d590  lea     rax, [rcx+268h]
0x18000d597  mov     [rbp+var_20], rax
0x18000d59b  xor     r13d, r13d
0x18000d59e  mov     [rbp+var_18], r13
0x18000d5a2  mov     [rbp+var_10], 1
0x18000d5a6  lea     rdx, [rbp+var_18]; struct StreamGroupParams **
0x18000d5aa  mov     rcx, rdi; this
0x18000d5ad  call    ?Clone@StreamGroupParams@@QEBAJPEAPEAU1@@Z; StreamGroupParams::Clone(StreamGroupParams * *)
0x18000d5b2  mov     ebx, eax
0x18000d5b4  cmp     [rbp+var_10], r13b
0x18000d5b8  jz      short loc_18000D5D1
0x18000d5ba  mov     r8, [rbp+var_20]
0x18000d5be  mov     rdx, [r8]
0x18000d5c1  mov     rcx, [rbp+var_18]
0x18000d5c5  mov     [r8], rcx
0x18000d5c8  test    rdx, rdx
0x18000d5cb  jnz     loc_18000D816
0x18000d5d1  test    ebx, ebx
0x18000d5d3  js      loc_18000D820
0x18000d5d9  lea     rdx, [rdi+38h]; struct CProcessingModeParameters *
0x18000d5dd  mov     rcx, r14; this
0x18000d5e0  call    ?SetProcessingModeParameters@CAudioStream@@QEAAJPEAVCProcessingModeParameters@@@Z; CAudioStream::SetProcessingModeParameters(CProcessingModeParameters *)
0x18000d5e5  mov     ebx, eax
0x18000d5e7  test    eax, eax
0x18000d5e9  js      loc_18000D827
0x18000d5ef  test    r15, r15
0x18000d5f2  jz      loc_18000D725
0x18000d5f8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d5ff  mov     ecx, 10h; unsigned __int64
0x18000d604  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000d609  mov     rbx, rax
0x18000d60c  test    rax, rax
0x18000d60f  jz      loc_18000D7AB
0x18000d615  mov     [rax], r13
0x18000d618  mov     [rax+8], r13
0x18000d61c  mov     [rbp+arg_18], rax
0x18000d620  mov     rdi, [r15+8]
0x18000d624  test    rdi, rdi
0x18000d627  jz      loc_18000D70E
0x18000d62d  mov     rsi, r13
0x18000d630  mov     [rbp+Size], r13
0x18000d634  cmp     [rdi+18h], r13
0x18000d638  jnz     loc_18000D846
0x18000d63e  mov     r13, [rdi+10h]
0x18000d642  movzx   eax, word ptr [r13+10h]
0x18000d647  add     rax, 12h
0x18000d64b  mov     [rbp+Size], rax
0x18000d64f  mov     rcx, rax; cb
0x18000d652  call    cs:__imp_CoTaskMemAlloc
0x18000d658  mov     r12, rax
0x18000d65b  test    rax, rax
0x18000d65e  jz      loc_18000D7DE
0x18000d664  mov     r8, [rbp+Size]; Size
0x18000d668  mov     rdx, r13; Src
0x18000d66b  mov     rcx, rax; void *
0x18000d66e  call    memcpy_0
0x18000d673  mov     ecx, [rdi+40h]
0x18000d676  shl     rcx, 4
0x18000d67a  add     rcx, 44h ; 'D'; unsigned __int64
0x18000d67e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d685  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000d68a  mov     rcx, rax
0x18000d68d  xor     r13d, r13d
0x18000d690  test    rax, rax
0x18000d693  jz      loc_18000D73F
0x18000d699  mov     eax, [rdi]
0x18000d69b  mov     [rcx], eax
0x18000d69d  mov     eax, [rdi+4]
0x18000d6a0  mov     [rcx+4], eax
0x18000d6a3  mov     eax, [rdi+8]
0x18000d6a6  mov     [rcx+8], eax
0x18000d6a9  mov     [rcx+10h], r12
0x18000d6ad  mov     [rcx+18h], rsi
0x18000d6b1  mov     eax, [rdi+20h]
0x18000d6b4  mov     [rcx+20h], eax
0x18000d6b7  movups  xmm0, xmmword ptr [rdi+24h]
0x18000d6bb  movdqu  xmmword ptr [rcx+24h], xmm0
0x18000d6c0  mov     eax, [rdi+34h]
0x18000d6c3  mov     [rcx+34h], eax
0x18000d6c6  mov     eax, [rdi+38h]
0x18000d6c9  mov     [rcx+38h], eax
0x18000d6cc  mov     eax, [rdi+40h]
0x18000d6cf  mov     [rcx+40h], eax
0x18000d6d2  mov     edx, r13d
0x18000d6d5  cmp     [rdi+40h], r13d
0x18000d6d9  ja      loc_18000D78E
0x18000d6df  mov     rax, [rbx+8]
0x18000d6e3  mov     [rbx+8], rcx
0x18000d6e7  test    rax, rax
0x18000d6ea  jnz     loc_18000D893
0x18000d6f0  mov     rcx, [rbx]
0x18000d6f3  mov     [rbx], r13
0x18000d6f6  test    rcx, rcx
0x18000d6f9  jnz     loc_18000D8A5
0x18000d6ff  mov     rcx, [r15]
0x18000d702  test    rcx, rcx
0x18000d705  jnz     loc_18000D8B6
0x18000d70b  mov     [rbx], r13
0x18000d70e  mov     rdx, [r14+270h]
0x18000d715  mov     [r14+270h], rbx
0x18000d71c  test    rdx, rdx
0x18000d71f  jnz     loc_18000D8CA
0x18000d725  xor     eax, eax
0x18000d727  mov     rbx, [rsp+40h+arg_8]
0x18000d72f  add     rsp, 40h
0x18000d733  pop     r15
0x18000d735  pop     r14
0x18000d737  pop     r13
0x18000d739  pop     r12
0x18000d73b  pop     rdi
0x18000d73c  pop     rsi
0x18000d73d  pop     rbp
0x18000d73e  retn
0x18000d73f  mov     rcx, [rbp+38h]; this
0x18000d743  mov     edi, 8007000Eh
0x18000d748  mov     r9d, edi; char *
0x18000d74b  lea     r8, aAvcoreAudiocor_5; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18000d752  mov     edx, 82Bh; void *
0x18000d757  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d75c  mov     rcx, r12; pv
0x18000d75f  call    cs:__imp_CoTaskMemFree
0x18000d765  test    rsi, rsi
0x18000d768  jnz     short loc_18000D783
0x18000d76a  mov     rcx, rbx; this
0x18000d76d  call    ??1MODE_PARAMS@@QEAA@XZ; MODE_PARAMS::~MODE_PARAMS(void)
0x18000d772  mov     edx, 10h; struct std::nothrow_t *
0x18000d777  mov     rcx, rbx; void *
0x18000d77a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d77f  mov     eax, edi
0x18000d781  jmp     short loc_18000D727
0x18000d783  mov     rcx, rsi; pv
0x18000d786  call    cs:__imp_CoTaskMemFree
0x18000d78c  jmp     short loc_18000D76A
0x18000d78e  mov     eax, edx
0x18000d790  add     rax, rax
0x18000d793  movups  xmm0, xmmword ptr [rdi+rax*8+44h]
0x18000d798  movdqu  xmmword ptr [rcx+rax*8+44h], xmm0
0x18000d79e  inc     edx
0x18000d7a0  cmp     edx, [rdi+40h]
0x18000d7a3  jnb     loc_18000D6DF
0x18000d7a9  jmp     short loc_18000D78E
0x18000d7ab  mov     [rbp+arg_18], r13
0x18000d7af  mov     rcx, [rbp+38h]; this
0x18000d7b3  mov     edi, 8007000Eh
0x18000d7b8  mov     r9d, edi; char *
0x18000d7bb  lea     r8, aAvcoreAudiocor_5; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18000d7c2  mov     edx, 81Bh; void *
0x18000d7c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d7cc  mov     esi, edi
0x18000d7ce  lea     rcx, [rbp+arg_18]
0x18000d7d2  call    ??1?$unique_ptr@UMODE_PARAMS@@U?$default_delete@UMODE_PARAMS@@@std@@@std@@QEAA@XZ; std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(void)
0x18000d7d7  mov     eax, esi
0x18000d7d9  jmp     loc_18000D727
0x18000d7de  mov     rcx, [rbp+38h]; this
0x18000d7e2  mov     edi, 8007000Eh
0x18000d7e7  mov     r9d, edi; char *
0x18000d7ea  lea     r8, aAvcoreAudiocor_5; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18000d7f1  mov     edx, 827h; void *
0x18000d7f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d7fb  test    rsi, rsi
0x18000d7fe  jz      short loc_18000D809
0x18000d800  mov     rcx, rsi; pv
0x18000d803  call    cs:__imp_CoTaskMemFree
0x18000d809  mov     rdx, rbx
0x18000d80c  call    ??R?$default_delete@UMODE_PARAMS@@@std@@QEBAXPEAUMODE_PARAMS@@@Z; std::default_delete<MODE_PARAMS>::operator()(MODE_PARAMS *)
0x18000d811  jmp     loc_18000D77F
0x18000d816  call    ??R?$default_delete@UStreamGroupParams@@@std@@QEBAXPEAUStreamGroupParams@@@Z; std::default_delete<StreamGroupParams>::operator()(StreamGroupParams *)
0x18000d81b  jmp     loc_18000D5D1
0x18000d820  mov     edx, 813h
0x18000d825  jmp     short loc_18000D82C
0x18000d827  mov     edx, 815h; void *
0x18000d82c  lea     r8, aAvcoreAudiocor_5; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18000d833  mov     r9d, ebx; char *
0x18000d836  mov     rcx, [rbp+38h]; this
0x18000d83a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d83f  mov     eax, ebx
0x18000d841  jmp     loc_18000D727
0x18000d846  xor     edx, edx
0x18000d848  lea     rcx, [rbp+Size]
0x18000d84c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000d851  lea     r9, [rbp+Size]
0x18000d855  mov     r8, [rdi+18h]
0x18000d859  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000d85e  mov     esi, eax
0x18000d860  test    eax, eax
0x18000d862  jns     short loc_18000D88A
0x18000d864  mov     rcx, [rbp+38h]; this
0x18000d868  mov     r9d, eax; char *
0x18000d86b  lea     r8, aAvcoreAudiocor_5; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18000d872  mov     edx, 823h; void *
0x18000d877  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d87c  lea     rcx, [rbp+Size]
0x18000d880  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000d885  jmp     loc_18000D7CE
0x18000d88a  mov     rsi, [rbp+Size]
0x18000d88e  jmp     loc_18000D63E
0x18000d893  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x18000d898  mov     rcx, rax; void *
0x18000d89b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d8a0  jmp     loc_18000D6F0
0x18000d8a5  mov     rax, [rcx]
0x18000d8a8  mov     rax, [rax+10h]
0x18000d8ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8b1  jmp     loc_18000D6FF
0x18000d8b6  mov     [rbx], rcx
0x18000d8b9  mov     rax, [rcx]
0x18000d8bc  mov     rax, [rax+8]
0x18000d8c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8c5  jmp     loc_18000D70E
0x18000d8ca  call    ??R?$default_delete@UMODE_PARAMS@@@std@@QEBAXPEAUMODE_PARAMS@@@Z; std::default_delete<MODE_PARAMS>::operator()(MODE_PARAMS *)
0x18000d8cf  jmp     loc_18000D725
```
