# CreateSemanticSearchServices(void)

- ea: `0x14005d338`
- end: `0x14005d486`
- name: `?CreateSemanticSearchServices@@YA?AV?$com_ptr_t@UIIndexerSemanticSearchServices@@Uerr_exception_policy@wil@@@wil@@XZ`
- size: `334`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14005eb00`
- `0x14005f820`
- `0x14005fc34`

## callees

- `0x14000e678`
- `0x1400317a8`
- `0x14003221c`
- `0x14005d338`
- `0x14005f28c`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14005d3b7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14005d3b7`

## string_xrefs

- `0x14005d473`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x14005d458`: `onecoreuap\base\appmodel\Search\common\include\SemanticVectorHelper.h`
- `0x14005d44c`: `Total duration to cocreate wsaifabricsvc %u\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall CreateSemanticSearchServices(_QWORD *a1)
{
  _QWORD *v1; // rsi
  unsigned int v2; // ebx
  unsigned int v3; // r14d
  int v4; // ebx
  HRESULT v5; // eax
  LPVOID v6; // rax
  __int64 v7; // rcx
  _QWORD *result; // rax
  int v9; // ebx
  int ppv; // [rsp+20h] [rbp-38h]
  unsigned int v11; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  _QWORD *v13; // [rsp+60h] [rbp+8h] BYREF
  int v14; // [rsp+68h] [rbp+10h]
  LPVOID v15; // [rsp+70h] [rbp+18h] BYREF
  __int64 v16; // [rsp+78h] [rbp+20h] BYREF

  v13 = a1;
  v1 = a1;
  v11 = 0;
  std::chrono::steady_clock::now(&v16);
  *v1 = 0;
  v2 = 1;
  v3 = 1;
  v14 = 1;
  while ( 2 )
  {
    try
    {
      while ( !*v1 && v3 <= 3 )
      {
        v4 = v2 | 4;
        v15 = 0;
        v5 = CoCreateInstance(
               &GUID_879d4670_5a0c_4467_bbc4_30c943755bf8,
               0,
               4u,
               &GUID_e621e0fa_3b69_48e6_bc9f_d65ad301cb14,
               &v15);
        if ( v5 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1CBE,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
            (const char *)(unsigned int)v5,
            ppv);
        v2 = v4 & 0xFFFFFFF9 | 2;
        v11 = v2;
        v6 = v15;
        v15 = 0;
        v7 = *v1;
        *v1 = v6;
        if ( v7 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v15);
      }
      std::chrono::steady_clock::now(&v13);
      SearchIndexerDebug::Verbose(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\common\\include\\SemanticVectorHelper.h",
        (const wchar_t *)0x62,
        (unsigned int)L"Total duration to cocreate wsaifabricsvc %u\n",
        (const wchar_t *)(((__int64)v13 - v16) / 1000));
      result = v1;
    }
    catch ( ... )
    {
      v9 = v14;
      if ( v14 == 3 )
        throw;
      Sleep(10 * v14);
      v14 = v9 + 1;
      v1 = v13;
      v3 = v9 + 1;
      v2 = v11;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x14005d338  mov     rax, rsp
0x14005d33b  mov     [rax+8], rcx
0x14005d33f  push    rbx
0x14005d340  push    rsi
0x14005d341  push    r14
0x14005d343  sub     rsp, 40h
0x14005d347  mov     qword ptr [rax-20h], 0FFFFFFFFFFFFFFFEh
0x14005d34f  mov     rsi, rcx
0x14005d352  mov     dword ptr [rax-28h], 0
0x14005d359  lea     rcx, [rax+20h]
0x14005d35d  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x14005d362  mov     qword ptr [rsi], 0
0x14005d369  mov     ebx, 1
0x14005d36e  mov     r14d, ebx
0x14005d371  mov     [rsp+58h+arg_8], ebx
0x14005d375  cmp     qword ptr [rsi], 0
0x14005d379  jnz     loc_14005D41D
0x14005d37f  cmp     r14d, 3
0x14005d383  ja      loc_14005D41D
0x14005d389  or      ebx, 4
0x14005d38c  mov     [rsp+58h+var_28], ebx
0x14005d390  mov     [rsp+58h+arg_10], 0
0x14005d399  lea     rax, [rsp+58h+arg_10]
0x14005d39e  mov     qword ptr [rsp+58h+ppv], rax; int
0x14005d3a3  lea     r9, _GUID_e621e0fa_3b69_48e6_bc9f_d65ad301cb14; riid
0x14005d3aa  xor     edx, edx; pUnkOuter
0x14005d3ac  lea     r8d, [rdx+4]; dwClsContext
0x14005d3b0  lea     rcx, _GUID_879d4670_5a0c_4467_bbc4_30c943755bf8; rclsid
0x14005d3b7  call    cs:__imp_CoCreateInstance
0x14005d3bd  mov     rcx, [rsp+58h]; this
0x14005d3c2  test    eax, eax
0x14005d3c4  js      loc_14005D470
0x14005d3ca  and     ebx, 0FFFFFFFBh
0x14005d3cd  or      ebx, 2
0x14005d3d0  mov     [rsp+58h+var_28], ebx
0x14005d3d4  mov     rax, [rsp+58h+arg_10]
0x14005d3d9  mov     [rsp+58h+arg_10], 0
0x14005d3e2  mov     rcx, [rsi]
0x14005d3e5  mov     [rsi], rax
0x14005d3e8  test    rcx, rcx
0x14005d3eb  jz      short loc_14005D3FA
0x14005d3ed  mov     rax, [rcx]
0x14005d3f0  mov     rax, [rax+10h]
0x14005d3f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005d3f9  nop
0x14005d3fa  lea     rcx, [rsp+58h+arg_10]
0x14005d3ff  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x14005d404  nop
0x14005d405  jmp     loc_14005D375
0x14005d40a  mov     rsi, [rsp+58h+arg_0]
0x14005d40f  mov     r14d, [rsp+58h+arg_8]
0x14005d414  mov     ebx, [rsp+58h+var_28]
0x14005d418  jmp     loc_14005D375
0x14005d41d  lea     rcx, [rsp+58h+arg_0]
0x14005d422  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x14005d427  mov     rcx, [rsp+58h+arg_0]
0x14005d42c  sub     rcx, [rsp+58h+arg_18]
0x14005d431  mov     rax, 20C49BA5E353F7CFh
0x14005d43b  imul    rcx
0x14005d43e  sar     rdx, 7
0x14005d442  mov     r9, rdx
0x14005d445  shr     r9, 3Fh
0x14005d449  add     r9, rdx; wchar_t *
0x14005d44c  lea     r8, aTotalDurationT; "Total duration to cocreate wsaifabricsv"...
0x14005d453  mov     edx, 62h ; 'b'; wchar_t *
0x14005d458  lea     rcx, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14005d45f  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x14005d464  mov     rax, rsi
0x14005d467  add     rsp, 40h
0x14005d46b  pop     r14
0x14005d46d  pop     rsi
0x14005d46e  pop     rbx
0x14005d46f  retn
0x14005d470  mov     r9d, eax; char *
0x14005d473  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14005d47a  mov     edx, 1CBEh; void *
0x14005d47f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
