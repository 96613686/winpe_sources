# CAudioStream::SaveStreamGroupCreationParameters(StreamGroupParams *,MODE_PARAMS *)

- ea: `0x18000d6c0`
- end: `0x18000da24`
- name: `?SaveStreamGroupCreationParameters@CAudioStream@@UEAAJPEAUStreamGroupParams@@PEAUMODE_PARAMS@@@Z`
- size: `868`
- prototype: `__int64 __fastcall(CAudioStream *__hidden this, struct StreamGroupParams *, struct MODE_PARAMS *)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000cba0`
- `0x18000cc00`
- `0x18000cc30`
- `0x18000cc60`
- `0x18000d6c0`
- `0x18000da2c`
- `0x18000dbd0`
- `0x18000e284`
- `0x18000e314`
- `0x18001280c`
- `0x180032ffc`
- `0x1800cdd70`
- `0x1800cddac`
- `0x1800ce75c`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d7a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d7a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d8af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d8d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d953`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d8af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d8d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d953`

## string_xrefs

- `0x18000d89b`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x18000d90b`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x18000d93a`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x18000d97c`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x18000d9bb`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`

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
0x18000d6c0  mov     [rsp-38h+arg_8], rbx
0x18000d6c5  push    rbp
0x18000d6c6  push    rsi
0x18000d6c7  push    rdi
0x18000d6c8  push    r12
0x18000d6ca  push    r13
0x18000d6cc  push    r14
0x18000d6ce  push    r15
0x18000d6d0  mov     rbp, rsp
0x18000d6d3  sub     rsp, 40h
0x18000d6d7  mov     r15, r8
0x18000d6da  mov     rdi, rdx
0x18000d6dd  mov     r14, rcx
0x18000d6e0  lea     rax, [rcx+268h]
0x18000d6e7  mov     [rbp+var_20], rax
0x18000d6eb  xor     r13d, r13d
0x18000d6ee  mov     [rbp+var_18], r13
0x18000d6f2  mov     [rbp+var_10], 1
0x18000d6f6  lea     rdx, [rbp+var_18]; struct StreamGroupParams **
0x18000d6fa  mov     rcx, rdi; this
0x18000d6fd  call    ?Clone@StreamGroupParams@@QEBAJPEAPEAU1@@Z; StreamGroupParams::Clone(StreamGroupParams * *)
0x18000d702  mov     ebx, eax
0x18000d704  cmp     [rbp+var_10], r13b
0x18000d708  jz      short loc_18000D721
0x18000d70a  mov     r8, [rbp+var_20]
0x18000d70e  mov     rdx, [r8]
0x18000d711  mov     rcx, [rbp+var_18]
0x18000d715  mov     [r8], rcx
0x18000d718  test    rdx, rdx
0x18000d71b  jnz     loc_18000D966
0x18000d721  test    ebx, ebx
0x18000d723  js      loc_18000D970
0x18000d729  lea     rdx, [rdi+38h]; struct CProcessingModeParameters *
0x18000d72d  mov     rcx, r14; this
0x18000d730  call    ?SetProcessingModeParameters@CAudioStream@@QEAAJPEAVCProcessingModeParameters@@@Z; CAudioStream::SetProcessingModeParameters(CProcessingModeParameters *)
0x18000d735  mov     ebx, eax
0x18000d737  test    eax, eax
0x18000d739  js      loc_18000D977
0x18000d73f  test    r15, r15
0x18000d742  jz      loc_18000D875
0x18000d748  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d74f  mov     ecx, 10h; unsigned __int64
0x18000d754  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000d759  mov     rbx, rax
0x18000d75c  test    rax, rax
0x18000d75f  jz      loc_18000D8FB
0x18000d765  mov     [rax], r13
0x18000d768  mov     [rax+8], r13
0x18000d76c  mov     [rbp+arg_18], rax
0x18000d770  mov     rdi, [r15+8]
0x18000d774  test    rdi, rdi
0x18000d777  jz      loc_18000D85E
0x18000d77d  mov     rsi, r13
0x18000d780  mov     [rbp+Size], r13
0x18000d784  cmp     [rdi+18h], r13
0x18000d788  jnz     loc_18000D996
0x18000d78e  mov     r13, [rdi+10h]
0x18000d792  movzx   eax, word ptr [r13+10h]
0x18000d797  add     rax, 12h
0x18000d79b  mov     [rbp+Size], rax
0x18000d79f  mov     rcx, rax; cb
0x18000d7a2  call    cs:__imp_CoTaskMemAlloc
0x18000d7a8  mov     r12, rax
0x18000d7ab  test    rax, rax
0x18000d7ae  jz      loc_18000D92E
0x18000d7b4  mov     r8, [rbp+Size]; Size
0x18000d7b8  mov     rdx, r13; Src
0x18000d7bb  mov     rcx, rax; void *
0x18000d7be  call    memcpy_0
0x18000d7c3  mov     ecx, [rdi+40h]
0x18000d7c6  shl     rcx, 4
0x18000d7ca  add     rcx, 44h ; 'D'; unsigned __int64
0x18000d7ce  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d7d5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000d7da  mov     rcx, rax
0x18000d7dd  xor     r13d, r13d
0x18000d7e0  test    rax, rax
0x18000d7e3  jz      loc_18000D88F
0x18000d7e9  mov     eax, [rdi]
0x18000d7eb  mov     [rcx], eax
0x18000d7ed  mov     eax, [rdi+4]
0x18000d7f0  mov     [rcx+4], eax
0x18000d7f3  mov     eax, [rdi+8]
0x18000d7f6  mov     [rcx+8], eax
0x18000d7f9  mov     [rcx+10h], r12
0x18000d7fd  mov     [rcx+18h], rsi
0x18000d801  mov     eax, [rdi+20h]
0x18000d804  mov     [rcx+20h], eax
0x18000d807  movups  xmm0, xmmword ptr [rdi+24h]
0x18000d80b  movdqu  xmmword ptr [rcx+24h], xmm0
0x18000d810  mov     eax, [rdi+34h]
0x18000d813  mov     [rcx+34h], eax
0x18000d816  mov     eax, [rdi+38h]
0x18000d819  mov     [rcx+38h], eax
0x18000d81c  mov     eax, [rdi+40h]
0x18000d81f  mov     [rcx+40h], eax
0x18000d822  mov     edx, r13d
0x18000d825  cmp     [rdi+40h], r13d
0x18000d829  ja      loc_18000D8DE
0x18000d82f  mov     rax, [rbx+8]
0x18000d833  mov     [rbx+8], rcx
0x18000d837  test    rax, rax
0x18000d83a  jnz     loc_18000D9E3
0x18000d840  mov     rcx, [rbx]
0x18000d843  mov     [rbx], r13
0x18000d846  test    rcx, rcx
0x18000d849  jnz     loc_18000D9F5
0x18000d84f  mov     rcx, [r15]
0x18000d852  test    rcx, rcx
0x18000d855  jnz     loc_18000DA06
0x18000d85b  mov     [rbx], r13
0x18000d85e  mov     rdx, [r14+270h]
0x18000d865  mov     [r14+270h], rbx
0x18000d86c  test    rdx, rdx
0x18000d86f  jnz     loc_18000DA1A
0x18000d875  xor     eax, eax
0x18000d877  mov     rbx, [rsp+40h+arg_8]
0x18000d87f  add     rsp, 40h
0x18000d883  pop     r15
0x18000d885  pop     r14
0x18000d887  pop     r13
0x18000d889  pop     r12
0x18000d88b  pop     rdi
0x18000d88c  pop     rsi
0x18000d88d  pop     rbp
0x18000d88e  retn
0x18000d88f  mov     rcx, [rbp+38h]; this
0x18000d893  mov     edi, 8007000Eh
0x18000d898  mov     r9d, edi; char *
0x18000d89b  lea     r8, aAvcoreAudiocor_5; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18000d8a2  mov     edx, 82Bh; void *
0x18000d8a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d8ac  mov     rcx, r12; pv
0x18000d8af  call    cs:__imp_CoTaskMemFree
0x18000d8b5  test    rsi, rsi
0x18000d8b8  jnz     short loc_18000D8D3
0x18000d8ba  mov     rcx, rbx; this
0x18000d8bd  call    ??1MODE_PARAMS@@QEAA@XZ; MODE_PARAMS::~MODE_PARAMS(void)
0x18000d8c2  mov     edx, 10h; struct std::nothrow_t *
0x18000d8c7  mov     rcx, rbx; void *
0x18000d8ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d8cf  mov     eax, edi
0x18000d8d1  jmp     short loc_18000D877
0x18000d8d3  mov     rcx, rsi; pv
0x18000d8d6  call    cs:__imp_CoTaskMemFree
0x18000d8dc  jmp     short loc_18000D8BA
0x18000d8de  mov     eax, edx
0x18000d8e0  add     rax, rax
0x18000d8e3  movups  xmm0, xmmword ptr [rdi+rax*8+44h]
0x18000d8e8  movdqu  xmmword ptr [rcx+rax*8+44h], xmm0
0x18000d8ee  inc     edx
0x18000d8f0  cmp     edx, [rdi+40h]
0x18000d8f3  jnb     loc_18000D82F
0x18000d8f9  jmp     short loc_18000D8DE
0x18000d8fb  mov     [rbp+arg_18], r13
0x18000d8ff  mov     rcx, [rbp+38h]; this
0x18000d903  mov     edi, 8007000Eh
0x18000d908  mov     r9d, edi; char *
0x18000d90b  lea     r8, aAvcoreAudiocor_5; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18000d912  mov     edx, 81Bh; void *
0x18000d917  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d91c  mov     esi, edi
0x18000d91e  lea     rcx, [rbp+arg_18]
0x18000d922  call    ??1?$unique_ptr@UMODE_PARAMS@@U?$default_delete@UMODE_PARAMS@@@std@@@std@@QEAA@XZ; std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(void)
0x18000d927  mov     eax, esi
0x18000d929  jmp     loc_18000D877
0x18000d92e  mov     rcx, [rbp+38h]; this
0x18000d932  mov     edi, 8007000Eh
0x18000d937  mov     r9d, edi; char *
0x18000d93a  lea     r8, aAvcoreAudiocor_5; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18000d941  mov     edx, 827h; void *
0x18000d946  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d94b  test    rsi, rsi
0x18000d94e  jz      short loc_18000D959
0x18000d950  mov     rcx, rsi; pv
0x18000d953  call    cs:__imp_CoTaskMemFree
0x18000d959  mov     rdx, rbx
0x18000d95c  call    ??R?$default_delete@UMODE_PARAMS@@@std@@QEBAXPEAUMODE_PARAMS@@@Z; std::default_delete<MODE_PARAMS>::operator()(MODE_PARAMS *)
0x18000d961  jmp     loc_18000D8CF
0x18000d966  call    ??R?$default_delete@UStreamGroupParams@@@std@@QEBAXPEAUStreamGroupParams@@@Z; std::default_delete<StreamGroupParams>::operator()(StreamGroupParams *)
0x18000d96b  jmp     loc_18000D721
0x18000d970  mov     edx, 813h
0x18000d975  jmp     short loc_18000D97C
0x18000d977  mov     edx, 815h; void *
0x18000d97c  lea     r8, aAvcoreAudiocor_5; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18000d983  mov     r9d, ebx; char *
0x18000d986  mov     rcx, [rbp+38h]; this
0x18000d98a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d98f  mov     eax, ebx
0x18000d991  jmp     loc_18000D877
0x18000d996  xor     edx, edx
0x18000d998  lea     rcx, [rbp+Size]
0x18000d99c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000d9a1  lea     r9, [rbp+Size]
0x18000d9a5  mov     r8, [rdi+18h]
0x18000d9a9  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000d9ae  mov     esi, eax
0x18000d9b0  test    eax, eax
0x18000d9b2  jns     short loc_18000D9DA
0x18000d9b4  mov     rcx, [rbp+38h]; this
0x18000d9b8  mov     r9d, eax; char *
0x18000d9bb  lea     r8, aAvcoreAudiocor_5; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18000d9c2  mov     edx, 823h; void *
0x18000d9c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d9cc  lea     rcx, [rbp+Size]
0x18000d9d0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000d9d5  jmp     loc_18000D91E
0x18000d9da  mov     rsi, [rbp+Size]
0x18000d9de  jmp     loc_18000D78E
0x18000d9e3  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x18000d9e8  mov     rcx, rax; void *
0x18000d9eb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d9f0  jmp     loc_18000D840
0x18000d9f5  mov     rax, [rcx]
0x18000d9f8  mov     rax, [rax+10h]
0x18000d9fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da01  jmp     loc_18000D84F
0x18000da06  mov     [rbx], rcx
0x18000da09  mov     rax, [rcx]
0x18000da0c  mov     rax, [rax+8]
0x18000da10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da15  jmp     loc_18000D85E
0x18000da1a  call    ??R?$default_delete@UMODE_PARAMS@@@std@@QEBAXPEAUMODE_PARAMS@@@Z; std::default_delete<MODE_PARAMS>::operator()(MODE_PARAMS *)
0x18000da1f  jmp     loc_18000D875
```
