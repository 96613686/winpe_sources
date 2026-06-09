# Helpers::IsAppHostObjectBackedByExtension<IAppHostPropertySchema,ATL::CComPtr<IAppHostProperty>>(ATL::CComPtr<IAppHostProperty> &)

- ea: `0x18000a72c`
- end: `0x18000a844`
- name: `??$IsAppHostObjectBackedByExtension@UIAppHostPropertySchema@@V?$CComPtr@UIAppHostProperty@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostProperty@@@ATL@@@Z`
- size: `280`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b7f0`
- `0x18000bc0c`

## callees

- `0x1800018a0`
- `0x180001910`
- `0x180001a30`
- `0x1800021a4`
- `0x18000a72c`
- `0x1800105a0`
- `0x180012f3c`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000a7e1`
- `OLEAUT32!__imp_VariantInit` at `0x18000a7e1`
- `OLEAUT32!__imp_VariantClear` at `0x18000a827`
- `OLEAUT32!__imp_VariantClear` at `0x18000a827`

## string_xrefs

- `0x18000a797`: `extension`

## pseudocode

```c
bool __fastcall Helpers::IsAppHostObjectBackedByExtension<IAppHostPropertySchema,ATL::CComPtr<IAppHostProperty>>(
        _QWORD *a1)
{
  int v2; // eax
  int v3; // eax
  bool v4; // bl
  VARIANTARG pvarg; // [rsp+20h] [rbp-20h] BYREF
  int pExceptionObject; // [rsp+50h] [rbp+10h] BYREF
  __int64 v8; // [rsp+58h] [rbp+18h] BYREF

  if ( __TSS0__1____IsAppHostObjectBackedByExtension_UIAppHostPropertySchema__V__CComPtr_UIAppHostProperty___ATL___Helpers__SA_NAEAV__CComPtr_UIAppHostProperty___ATL___Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
  {
    Init_thread_header(&__TSS0__1____IsAppHostObjectBackedByExtension_UIAppHostPropertySchema__V__CComPtr_UIAppHostProperty___ATL___Helpers__SA_NAEAV__CComPtr_UIAppHostProperty___ATL___Z_4HA);
    if ( __TSS0__1____IsAppHostObjectBackedByExtension_UIAppHostPropertySchema__V__CComPtr_UIAppHostProperty___ATL___Helpers__SA_NAEAV__CComPtr_UIAppHostProperty___ATL___Z_4HA == -1 )
    {
      `Helpers::IsAppHostObjectBackedByExtension<IAppHostPropertySchema,ATL::CComPtr<IAppHostProperty>>'::`2'::bstrExtension = 0;
      atexit(`Helpers::IsAppHostObjectBackedByExtension<IAppHostPropertySchema,ATL::CComPtr<IAppHostProperty>>'::`2'::`dynamic atexit destructor for 'bstrExtension'');
      Init_thread_footer(&__TSS0__1____IsAppHostObjectBackedByExtension_UIAppHostPropertySchema__V__CComPtr_UIAppHostProperty___ATL___Helpers__SA_NAEAV__CComPtr_UIAppHostProperty___ATL___Z_4HA);
    }
  }
  Helpers::EnsureInitializedSerialized(
    (struct ScopedBSTR *)&`Helpers::IsAppHostObjectBackedByExtension<IAppHostPropertySchema,ATL::CComPtr<IAppHostProperty>>'::`2'::bstrExtension,
    (OLECHAR *)L"extension");
  v8 = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a1 + 88LL))(*a1, &v8);
  if ( v2 < 0 )
  {
    pExceptionObject = v2;
    throw (long *)&pExceptionObject;
  }
  VariantInit(&pvarg);
  v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v8 + 96LL))(
         v8,
         `Helpers::IsAppHostObjectBackedByExtension<IAppHostPropertySchema,ATL::CComPtr<IAppHostProperty>>'::`2'::bstrExtension,
         &pvarg);
  if ( v3 < 0 )
  {
    pExceptionObject = v3;
    throw (long *)&pExceptionObject;
  }
  v4 = pvarg.vt != 1;
  VariantClear(&pvarg);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
  return v4;
}

```

## disassembly

```asm
0x18000a72c  mov     [rsp-8+arg_10], rbx
0x18000a731  push    rbp
0x18000a732  mov     rbp, rsp
0x18000a735  sub     rsp, 40h
0x18000a739  mov     rbx, rcx
0x18000a73c  mov     edx, cs:_tls_index
0x18000a742  mov     rax, gs:58h
0x18000a74b  mov     ecx, 4
0x18000a750  mov     rax, [rax+rdx*8]
0x18000a754  mov     eax, [rcx+rax]
0x18000a757  cmp     cs:?$TSS0@?1???$IsAppHostObjectBackedByExtension@UIAppHostPropertySchema@@V?$CComPtr@UIAppHostProperty@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostProperty@@@ATL@@@Z@4HA, eax
0x18000a75d  jle     short loc_18000A797
0x18000a75f  lea     rcx, ?$TSS0@?1???$IsAppHostObjectBackedByExtension@UIAppHostPropertySchema@@V?$CComPtr@UIAppHostProperty@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostProperty@@@ATL@@@Z@4HA
0x18000a766  call    _Init_thread_header
0x18000a76b  cmp     cs:?$TSS0@?1???$IsAppHostObjectBackedByExtension@UIAppHostPropertySchema@@V?$CComPtr@UIAppHostProperty@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostProperty@@@ATL@@@Z@4HA, 0FFFFFFFFh
0x18000a772  jnz     short loc_18000A797
0x18000a774  mov     cs:?bstrExtension@?1???$IsAppHostObjectBackedByExtension@UIAppHostPropertySchema@@V?$CComPtr@UIAppHostProperty@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostProperty@@@ATL@@@Z@4VScopedBSTR@@A, 0; ScopedBSTR `Helpers::IsAppHostObjectBackedByExtension<IAppHostPropertySchema,ATL::CComPtr<IAppHostProperty>>(ATL::CComPtr<IAppHostProperty> &)'::`2'::bstrExtension
0x18000a77f  lea     rcx, ??__FbstrExtension@?1???$IsAppHostObjectBackedByExtension@UIAppHostPropertySchema@@V?$CComPtr@UIAppHostProperty@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostProperty@@@ATL@@@Z@YAXXZ; void (__cdecl *)()
0x18000a786  call    atexit
0x18000a78b  lea     rcx, ?$TSS0@?1???$IsAppHostObjectBackedByExtension@UIAppHostPropertySchema@@V?$CComPtr@UIAppHostProperty@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostProperty@@@ATL@@@Z@4HA
0x18000a792  call    _Init_thread_footer
0x18000a797  lea     rdx, aExtension; "extension"
0x18000a79e  lea     rcx, ?bstrExtension@?1???$IsAppHostObjectBackedByExtension@UIAppHostPropertySchema@@V?$CComPtr@UIAppHostProperty@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostProperty@@@ATL@@@Z@4VScopedBSTR@@A; this
0x18000a7a5  call    ?EnsureInitializedSerialized@Helpers@@SAXAEAVScopedBSTR@@PEBG@Z; Helpers::EnsureInitializedSerialized(ScopedBSTR &,ushort const *)
0x18000a7aa  mov     [rbp+arg_8], 0
0x18000a7b2  mov     rcx, [rbx]
0x18000a7b5  mov     rax, [rcx]
0x18000a7b8  lea     rdx, [rbp+arg_8]
0x18000a7bc  mov     rax, [rax+58h]
0x18000a7c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7c5  test    eax, eax
0x18000a7c7  jns     short loc_18000A7DD
0x18000a7c9  mov     [rbp+pExceptionObject], eax
0x18000a7cc  lea     rdx, _TI1J; pThrowInfo
0x18000a7d3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000a7d7  call    _CxxThrowException_0
0x18000a7dd  lea     rcx, [rbp+pvarg]; pvarg
0x18000a7e1  call    cs:__imp_VariantInit
0x18000a7e7  nop
0x18000a7e8  mov     rcx, [rbp+arg_8]
0x18000a7ec  mov     rax, [rcx]
0x18000a7ef  lea     r8, [rbp+pvarg]
0x18000a7f3  mov     rdx, cs:?bstrExtension@?1???$IsAppHostObjectBackedByExtension@UIAppHostPropertySchema@@V?$CComPtr@UIAppHostProperty@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostProperty@@@ATL@@@Z@4VScopedBSTR@@A; ScopedBSTR `Helpers::IsAppHostObjectBackedByExtension<IAppHostPropertySchema,ATL::CComPtr<IAppHostProperty>>(ATL::CComPtr<IAppHostProperty> &)'::`2'::bstrExtension
0x18000a7fa  mov     rax, [rax+60h]
0x18000a7fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a803  test    eax, eax
0x18000a805  jns     short loc_18000A81B
0x18000a807  mov     [rbp+pExceptionObject], eax
0x18000a80a  lea     rdx, _TI1J; pThrowInfo
0x18000a811  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000a815  call    _CxxThrowException_0
0x18000a81b  cmp     word ptr [rbp+pvarg], 1
0x18000a820  setnz   bl
0x18000a823  lea     rcx, [rbp+pvarg]; pvarg
0x18000a827  call    cs:__imp_VariantClear
0x18000a82d  nop
0x18000a82e  lea     rcx, [rbp+arg_8]
0x18000a832  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000a837  mov     al, bl
0x18000a839  mov     rbx, [rsp+40h+arg_10]
0x18000a83e  add     rsp, 40h
0x18000a842  pop     rbp
0x18000a843  retn
```
