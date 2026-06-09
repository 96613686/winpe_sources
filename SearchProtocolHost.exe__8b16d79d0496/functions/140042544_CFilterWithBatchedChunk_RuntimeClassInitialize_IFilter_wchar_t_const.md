# CFilterWithBatchedChunk::RuntimeClassInitialize(IFilter *,wchar_t const *)

- ea: `0x140042544`
- end: `0x1400426e6`
- name: `?RuntimeClassInitialize@CFilterWithBatchedChunk@@QEAAJPEAUIFilter@@PEB_W@Z`
- size: `418`
- prototype: `__int64 __fastcall(CFilterWithBatchedChunk *__hidden this, struct IFilter *, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14003e94c`

## callees

- `0x140009d6c`
- `0x140028044`
- `0x140033530`
- `0x140036570`
- `0x140041500`
- `0x140042544`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140042683`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140042683`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140042696`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140042696`

## string_xrefs

- `0x1400425d1`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrbatch.hxx`
- `0x140042622`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrbatch.hxx`
- `0x14004266a`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrbatch.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CFilterWithBatchedChunk::RuntimeClassInitialize(
        CFilterWithBatchedChunk *this,
        struct IFilter *a2,
        const wchar_t *a3)
{
  __int64 (__fastcall ***v6)(_QWORD, GUID *, char *); // rdi
  __int64 (__fastcall *v7)(_QWORD, GUID *, char *); // rbx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 result; // rax
  __int64 (__fastcall ***v11)(_QWORD, GUID *, char *); // rdi
  __int64 (__fastcall *v12)(_QWORD, GUID *, char *); // rbx
  int v13; // eax
  __int64 (__fastcall ***v14)(_QWORD, GUID *, char *); // rdi
  __int64 (__fastcall *v15)(_QWORD, GUID *, char *); // rbx
  int v16; // eax
  LPVOID v17; // rax
  void *v18; // rcx
  int v19; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v21; // [rsp+50h] [rbp+8h] BYREF

  v19 = -2;
  if ( *((struct IFilter **)this + 4) != a2 )
  {
    if ( a2 )
      ((void (__fastcall *)(struct IFilter *))a2->lpVtbl->AddRef)(a2);
    v21 = *((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = a2;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v21);
  }
  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 4);
  v7 = **v6;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease((char *)this + 40);
  v8 = v7(v6, &GUID_7e4a4a60_9c7b_459a_b4fc_7685e9864d7e, (char *)this + 40);
  if ( v8 < 0 )
  {
    v9 = 33;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrbatch.hxx",
      (const char *)(unsigned int)v8,
      v19);
    return (unsigned int)v8;
  }
  v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 4);
  v12 = **v11;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease((char *)this + 48);
  v13 = v12(v11, &GUID_00000109_0000_0000_c000_000000000046, (char *)this + 48);
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrbatch.hxx",
      (const char *)(unsigned int)v13,
      -2);
  v14 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 4);
  v15 = **v14;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease((char *)this + 56);
  v16 = v15(v14, &GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f, (char *)this + 56);
  if ( v16 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrbatch.hxx",
      (const char *)(unsigned int)v16,
      v19);
  v17 = CoTaskMemAlloc(104LL * *((unsigned int *)this + 16));
  v18 = (void *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = v17;
  if ( v18 )
    CoTaskMemFree(v18);
  if ( !*((_QWORD *)this + 11) )
  {
    v8 = -2147024882;
    v9 = 40;
    goto LABEL_7;
  }
  std::_WChar_traits<wchar_t>::length(a3);
  try
  {
    std::wstring::_Assign<wchar_t>();
    result = 0;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      46,
      "onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrbatch.hxx");
  }
  return result;
}

```

## disassembly

```asm
0x140042544  push    rdi
0x140042546  push    r14
0x140042548  push    r15
0x14004254a  sub     rsp, 30h
0x14004254e  mov     qword ptr [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh; int
0x140042557  mov     [rsp+48h+arg_8], rbx
0x14004255c  mov     [rsp+48h+arg_10], rsi
0x140042561  mov     r15, r8
0x140042564  mov     rbx, rdx
0x140042567  mov     r14, rcx
0x14004256a  cmp     [rcx+20h], rdx
0x14004256e  jz      short loc_14004259D
0x140042570  test    rdx, rdx
0x140042573  jz      short loc_140042585
0x140042575  mov     rax, [rdx]
0x140042578  mov     rcx, rdx
0x14004257b  mov     rax, [rax+8]
0x14004257f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042584  nop
0x140042585  mov     rax, [r14+20h]
0x140042589  mov     [rsp+48h+arg_0], rax
0x14004258e  mov     [r14+20h], rbx
0x140042592  lea     rcx, [rsp+48h+arg_0]
0x140042597  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x14004259c  nop
0x14004259d  mov     rdi, [r14+20h]
0x1400425a1  mov     rax, [rdi]
0x1400425a4  mov     rbx, [rax]
0x1400425a7  lea     rcx, [r14+28h]
0x1400425ab  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x1400425b0  lea     r8, [r14+28h]
0x1400425b4  lea     rdx, _GUID_7e4a4a60_9c7b_459a_b4fc_7685e9864d7e
0x1400425bb  mov     rcx, rdi
0x1400425be  mov     rax, rbx
0x1400425c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400425c6  mov     ebx, eax
0x1400425c8  test    eax, eax
0x1400425ca  jns     short loc_1400425EC
0x1400425cc  mov     edx, 21h ; '!'; void *
0x1400425d1  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\appmodel\\search\\sea"...
0x1400425d8  mov     r9d, ebx; char *
0x1400425db  mov     rcx, [rsp+48h]; this
0x1400425e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400425e5  mov     eax, ebx
0x1400425e7  jmp     loc_1400426D2
0x1400425ec  mov     rdi, [r14+20h]
0x1400425f0  mov     rax, [rdi]
0x1400425f3  mov     rbx, [rax]
0x1400425f6  lea     rcx, [r14+30h]
0x1400425fa  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x1400425ff  lea     r8, [r14+30h]
0x140042603  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x14004260a  mov     rcx, rdi
0x14004260d  mov     rax, rbx
0x140042610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042615  nop
0x140042616  mov     rcx, [rsp+48h]; this
0x14004261b  test    eax, eax
0x14004261d  jns     short loc_140042634
0x14004261f  mov     r9d, eax; char *
0x140042622  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\appmodel\\search\\sea"...
0x140042629  mov     edx, 24h ; '$'; void *
0x14004262e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140042633  nop
0x140042634  mov     rdi, [r14+20h]
0x140042638  mov     rax, [rdi]
0x14004263b  mov     rbx, [rax]
0x14004263e  lea     rcx, [r14+38h]
0x140042642  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x140042647  lea     r8, [r14+38h]
0x14004264b  lea     rdx, _GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f
0x140042652  mov     rcx, rdi
0x140042655  mov     rax, rbx
0x140042658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004265d  nop
0x14004265e  mov     rcx, [rsp+48h]; this
0x140042663  test    eax, eax
0x140042665  jns     short loc_14004267B
0x140042667  mov     r9d, eax; char *
0x14004266a  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\appmodel\\search\\sea"...
0x140042671  mov     edx, 25h ; '%'; void *
0x140042676  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14004267b  mov     eax, [r14+40h]
0x14004267f  imul    rcx, rax, 68h ; 'h'; cb
0x140042683  call    cs:__imp_CoTaskMemAlloc
0x140042689  mov     rcx, [r14+58h]; pv
0x14004268d  mov     [r14+58h], rax
0x140042691  test    rcx, rcx
0x140042694  jz      short loc_14004269C
0x140042696  call    cs:__imp_CoTaskMemFree
0x14004269c  cmp     qword ptr [r14+58h], 0
0x1400426a1  jnz     short loc_1400426B2
0x1400426a3  mov     ebx, 8007000Eh
0x1400426a8  mov     edx, 28h ; '('
0x1400426ad  jmp     loc_1400425D1
0x1400426b2  mov     rcx, r15
0x1400426b5  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1400426ba  lea     rcx, [r14+60h]
0x1400426be  mov     r8, rax
0x1400426c1  mov     rdx, r15
0x1400426c4  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1400426c9  nop
0x1400426ca  xor     eax, eax
0x1400426cc  jmp     short loc_1400426D2
0x1400426ce  mov     eax, dword ptr [rsp+48h+arg_0]
0x1400426d2  mov     rbx, [rsp+48h+arg_8]
0x1400426d7  mov     rsi, [rsp+48h+arg_10]
0x1400426dc  add     rsp, 30h
0x1400426e0  pop     r15
0x1400426e2  pop     r14
0x1400426e4  pop     rdi
0x1400426e5  retn
```
