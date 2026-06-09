# CBatchedFilter::RuntimeClassInitialize(IGenericFilter *,wchar_t const *)

- ea: `0x140042394`
- end: `0x14004253d`
- name: `?RuntimeClassInitialize@CBatchedFilter@@QEAAJPEAUIGenericFilter@@PEB_W@Z`
- size: `425`
- prototype: `__int64 __fastcall(CBatchedFilter *__hidden this, struct IGenericFilter *, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14003e884`

## callees

- `0x140009d6c`
- `0x140028044`
- `0x140033530`
- `0x140036570`
- `0x140041500`
- `0x140042394`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400424d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400424d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400424ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400424ea`

## string_xrefs

- `0x140042421`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrbatch.hxx`
- `0x140042472`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrbatch.hxx`
- `0x1400424ba`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrbatch.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CBatchedFilter::RuntimeClassInitialize(
        CBatchedFilter *this,
        struct IGenericFilter *a2,
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
  if ( *((struct IGenericFilter **)this + 8) != a2 )
  {
    if ( a2 )
      (*(void (__fastcall **)(struct IGenericFilter *))(*(_QWORD *)a2 + 8LL))(a2);
    v21 = *((_QWORD *)this + 8);
    *((_QWORD *)this + 8) = a2;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v21);
  }
  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 8);
  v7 = **v6;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease((char *)this + 72);
  v8 = v7(v6, &GUID_243202cc_8184_468f_a8d4_28a5c990acc5, (char *)this + 72);
  if ( v8 < 0 )
  {
    v9 = 222;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrbatch.hxx",
      (const char *)(unsigned int)v8,
      v19);
    return (unsigned int)v8;
  }
  v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 8);
  v12 = **v11;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease((char *)this + 80);
  v13 = v12(v11, &GUID_00000109_0000_0000_c000_000000000046, (char *)this + 80);
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrbatch.hxx",
      (const char *)(unsigned int)v13,
      -2);
  v14 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 8);
  v15 = **v14;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease((char *)this + 88);
  v16 = v15(v14, &GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f, (char *)this + 88);
  if ( v16 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xE2,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrbatch.hxx",
      (const char *)(unsigned int)v16,
      v19);
  v17 = CoTaskMemAlloc(72LL * *((unsigned int *)this + 24));
  v18 = (void *)*((_QWORD *)this + 15);
  *((_QWORD *)this + 15) = v17;
  if ( v18 )
    CoTaskMemFree(v18);
  if ( !*((_QWORD *)this + 15) )
  {
    v8 = -2147024882;
    v9 = 229;
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
      235,
      "onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrbatch.hxx");
  }
  return result;
}

```

## disassembly

```asm
0x140042394  push    rdi
0x140042396  push    r14
0x140042398  push    r15
0x14004239a  sub     rsp, 30h
0x14004239e  mov     qword ptr [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh; int
0x1400423a7  mov     [rsp+48h+arg_8], rbx
0x1400423ac  mov     [rsp+48h+arg_10], rsi
0x1400423b1  mov     r15, r8
0x1400423b4  mov     rbx, rdx
0x1400423b7  mov     r14, rcx
0x1400423ba  cmp     [rcx+40h], rdx
0x1400423be  jz      short loc_1400423ED
0x1400423c0  test    rdx, rdx
0x1400423c3  jz      short loc_1400423D5
0x1400423c5  mov     rax, [rdx]
0x1400423c8  mov     rcx, rdx
0x1400423cb  mov     rax, [rax+8]
0x1400423cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400423d4  nop
0x1400423d5  mov     rax, [r14+40h]
0x1400423d9  mov     [rsp+48h+arg_0], rax
0x1400423de  mov     [r14+40h], rbx
0x1400423e2  lea     rcx, [rsp+48h+arg_0]
0x1400423e7  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x1400423ec  nop
0x1400423ed  mov     rdi, [r14+40h]
0x1400423f1  mov     rax, [rdi]
0x1400423f4  mov     rbx, [rax]
0x1400423f7  lea     rcx, [r14+48h]
0x1400423fb  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x140042400  lea     r8, [r14+48h]
0x140042404  lea     rdx, _GUID_243202cc_8184_468f_a8d4_28a5c990acc5
0x14004240b  mov     rcx, rdi
0x14004240e  mov     rax, rbx
0x140042411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042416  mov     ebx, eax
0x140042418  test    eax, eax
0x14004241a  jns     short loc_14004243C
0x14004241c  mov     edx, 0DEh; void *
0x140042421  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\appmodel\\search\\sea"...
0x140042428  mov     r9d, ebx; char *
0x14004242b  mov     rcx, [rsp+48h]; this
0x140042430  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140042435  mov     eax, ebx
0x140042437  jmp     loc_140042529
0x14004243c  mov     rdi, [r14+40h]
0x140042440  mov     rax, [rdi]
0x140042443  mov     rbx, [rax]
0x140042446  lea     rcx, [r14+50h]
0x14004244a  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x14004244f  lea     r8, [r14+50h]
0x140042453  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x14004245a  mov     rcx, rdi
0x14004245d  mov     rax, rbx
0x140042460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042465  nop
0x140042466  mov     rcx, [rsp+48h]; this
0x14004246b  test    eax, eax
0x14004246d  jns     short loc_140042484
0x14004246f  mov     r9d, eax; char *
0x140042472  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\appmodel\\search\\sea"...
0x140042479  mov     edx, 0E1h; void *
0x14004247e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140042483  nop
0x140042484  mov     rdi, [r14+40h]
0x140042488  mov     rax, [rdi]
0x14004248b  mov     rbx, [rax]
0x14004248e  lea     rcx, [r14+58h]
0x140042492  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x140042497  lea     r8, [r14+58h]
0x14004249b  lea     rdx, _GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f
0x1400424a2  mov     rcx, rdi
0x1400424a5  mov     rax, rbx
0x1400424a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400424ad  nop
0x1400424ae  mov     rcx, [rsp+48h]; this
0x1400424b3  test    eax, eax
0x1400424b5  jns     short loc_1400424CB
0x1400424b7  mov     r9d, eax; char *
0x1400424ba  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\appmodel\\search\\sea"...
0x1400424c1  mov     edx, 0E2h; void *
0x1400424c6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400424cb  mov     eax, [r14+60h]
0x1400424cf  lea     rcx, [rax+rax*8]
0x1400424d3  shl     rcx, 3; cb
0x1400424d7  call    cs:__imp_CoTaskMemAlloc
0x1400424dd  mov     rcx, [r14+78h]; pv
0x1400424e1  mov     [r14+78h], rax
0x1400424e5  test    rcx, rcx
0x1400424e8  jz      short loc_1400424F0
0x1400424ea  call    cs:__imp_CoTaskMemFree
0x1400424f0  cmp     qword ptr [r14+78h], 0
0x1400424f5  jnz     short loc_140042506
0x1400424f7  mov     ebx, 8007000Eh
0x1400424fc  mov     edx, 0E5h
0x140042501  jmp     loc_140042421
0x140042506  mov     rcx, r15
0x140042509  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x14004250e  lea     rcx, [r14+80h]
0x140042515  mov     r8, rax
0x140042518  mov     rdx, r15
0x14004251b  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x140042520  nop
0x140042521  xor     eax, eax
0x140042523  jmp     short loc_140042529
0x140042525  mov     eax, dword ptr [rsp+48h+arg_0]
0x140042529  mov     rbx, [rsp+48h+arg_8]
0x14004252e  mov     rsi, [rsp+48h+arg_10]
0x140042533  add     rsp, 30h
0x140042537  pop     r15
0x140042539  pop     r14
0x14004253b  pop     rdi
0x14004253c  retn
```
