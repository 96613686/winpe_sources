# Helpers::IsAppHostObjectBackedByExtension<IAppHostElementSchema,ATL::CComPtr<IAppHostElement>>(ATL::CComPtr<IAppHostElement> &)

- ea: `0x18000a60c`
- end: `0x18000a724`
- name: `??$IsAppHostObjectBackedByExtension@UIAppHostElementSchema@@V?$CComPtr@UIAppHostElement@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostElement@@@ATL@@@Z`
- size: `280`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b8ec`
- `0x18000bc0c`
- `0x18000c230`

## callees

- `0x1800018a0`
- `0x180001910`
- `0x180001a30`
- `0x1800021a4`
- `0x18000a60c`
- `0x1800105a0`
- `0x180012f3c`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000a6c1`
- `OLEAUT32!__imp_VariantInit` at `0x18000a6c1`
- `OLEAUT32!__imp_VariantClear` at `0x18000a707`
- `OLEAUT32!__imp_VariantClear` at `0x18000a707`

## string_xrefs

- `0x18000a677`: `extension`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall Helpers::IsAppHostObjectBackedByExtension<IAppHostElementSchema,ATL::CComPtr<IAppHostElement>>(
        _QWORD *a1)
{
  int v2; // eax
  int v3; // eax
  bool v4; // bl
  VARIANTARG pvarg; // [rsp+20h] [rbp-20h] BYREF
  int pExceptionObject; // [rsp+50h] [rbp+10h] BYREF
  __int64 v8; // [rsp+58h] [rbp+18h] BYREF

  if ( __TSS0__1____IsAppHostObjectBackedByExtension_UIAppHostElementSchema__V__CComPtr_UIAppHostElement___ATL___Helpers__SA_NAEAV__CComPtr_UIAppHostElement___ATL___Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
  {
    Init_thread_header(&__TSS0__1____IsAppHostObjectBackedByExtension_UIAppHostElementSchema__V__CComPtr_UIAppHostElement___ATL___Helpers__SA_NAEAV__CComPtr_UIAppHostElement___ATL___Z_4HA);
    if ( __TSS0__1____IsAppHostObjectBackedByExtension_UIAppHostElementSchema__V__CComPtr_UIAppHostElement___ATL___Helpers__SA_NAEAV__CComPtr_UIAppHostElement___ATL___Z_4HA == -1 )
    {
      `Helpers::IsAppHostObjectBackedByExtension<IAppHostElementSchema,ATL::CComPtr<IAppHostElement>>'::`2'::bstrExtension = 0;
      atexit(`Helpers::IsAppHostObjectBackedByExtension<IAppHostElementSchema,ATL::CComPtr<IAppHostElement>>'::`2'::`dynamic atexit destructor for 'bstrExtension'');
      Init_thread_footer(&__TSS0__1____IsAppHostObjectBackedByExtension_UIAppHostElementSchema__V__CComPtr_UIAppHostElement___ATL___Helpers__SA_NAEAV__CComPtr_UIAppHostElement___ATL___Z_4HA);
    }
  }
  Helpers::EnsureInitializedSerialized(
    (struct ScopedBSTR *)&`Helpers::IsAppHostObjectBackedByExtension<IAppHostElementSchema,ATL::CComPtr<IAppHostElement>>'::`2'::bstrExtension,
    (OLECHAR *)L"extension");
  v8 = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a1 + 72LL))(*a1, &v8);
  if ( v2 < 0 )
  {
    pExceptionObject = v2;
    throw (long *)&pExceptionObject;
  }
  VariantInit(&pvarg);
  v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v8 + 40LL))(
         v8,
         `Helpers::IsAppHostObjectBackedByExtension<IAppHostElementSchema,ATL::CComPtr<IAppHostElement>>'::`2'::bstrExtension,
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
0x18000a60c  mov     [rsp-8+arg_10], rbx
0x18000a611  push    rbp
0x18000a612  mov     rbp, rsp
0x18000a615  sub     rsp, 40h
0x18000a619  mov     rbx, rcx
0x18000a61c  mov     edx, cs:_tls_index
0x18000a622  mov     rax, gs:58h
0x18000a62b  mov     ecx, 4
0x18000a630  mov     rax, [rax+rdx*8]
0x18000a634  mov     eax, [rcx+rax]
0x18000a637  cmp     cs:?$TSS0@?1???$IsAppHostObjectBackedByExtension@UIAppHostElementSchema@@V?$CComPtr@UIAppHostElement@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostElement@@@ATL@@@Z@4HA, eax
0x18000a63d  jle     short loc_18000A677
0x18000a63f  lea     rcx, ?$TSS0@?1???$IsAppHostObjectBackedByExtension@UIAppHostElementSchema@@V?$CComPtr@UIAppHostElement@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostElement@@@ATL@@@Z@4HA
0x18000a646  call    _Init_thread_header
0x18000a64b  cmp     cs:?$TSS0@?1???$IsAppHostObjectBackedByExtension@UIAppHostElementSchema@@V?$CComPtr@UIAppHostElement@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostElement@@@ATL@@@Z@4HA, 0FFFFFFFFh
0x18000a652  jnz     short loc_18000A677
0x18000a654  mov     cs:?bstrExtension@?1???$IsAppHostObjectBackedByExtension@UIAppHostElementSchema@@V?$CComPtr@UIAppHostElement@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostElement@@@ATL@@@Z@4VScopedBSTR@@A, 0; ScopedBSTR `Helpers::IsAppHostObjectBackedByExtension<IAppHostElementSchema,ATL::CComPtr<IAppHostElement>>(ATL::CComPtr<IAppHostElement> &)'::`2'::bstrExtension
0x18000a65f  lea     rcx, ??__FbstrExtension@?1???$IsAppHostObjectBackedByExtension@UIAppHostElementSchema@@V?$CComPtr@UIAppHostElement@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostElement@@@ATL@@@Z@YAXXZ; void (__cdecl *)()
0x18000a666  call    atexit
0x18000a66b  lea     rcx, ?$TSS0@?1???$IsAppHostObjectBackedByExtension@UIAppHostElementSchema@@V?$CComPtr@UIAppHostElement@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostElement@@@ATL@@@Z@4HA
0x18000a672  call    _Init_thread_footer
0x18000a677  lea     rdx, aExtension; "extension"
0x18000a67e  lea     rcx, ?bstrExtension@?1???$IsAppHostObjectBackedByExtension@UIAppHostElementSchema@@V?$CComPtr@UIAppHostElement@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostElement@@@ATL@@@Z@4VScopedBSTR@@A; this
0x18000a685  call    ?EnsureInitializedSerialized@Helpers@@SAXAEAVScopedBSTR@@PEBG@Z; Helpers::EnsureInitializedSerialized(ScopedBSTR &,ushort const *)
0x18000a68a  mov     [rbp+arg_8], 0
0x18000a692  mov     rcx, [rbx]
0x18000a695  mov     rax, [rcx]
0x18000a698  lea     rdx, [rbp+arg_8]
0x18000a69c  mov     rax, [rax+48h]
0x18000a6a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6a5  test    eax, eax
0x18000a6a7  jns     short loc_18000A6BD
0x18000a6a9  mov     [rbp+pExceptionObject], eax
0x18000a6ac  lea     rdx, _TI1J; pThrowInfo
0x18000a6b3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000a6b7  call    _CxxThrowException_0
0x18000a6bd  lea     rcx, [rbp+pvarg]; pvarg
0x18000a6c1  call    cs:__imp_VariantInit
0x18000a6c7  nop
0x18000a6c8  mov     rcx, [rbp+arg_8]
0x18000a6cc  mov     rax, [rcx]
0x18000a6cf  lea     r8, [rbp+pvarg]
0x18000a6d3  mov     rdx, cs:?bstrExtension@?1???$IsAppHostObjectBackedByExtension@UIAppHostElementSchema@@V?$CComPtr@UIAppHostElement@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostElement@@@ATL@@@Z@4VScopedBSTR@@A; ScopedBSTR `Helpers::IsAppHostObjectBackedByExtension<IAppHostElementSchema,ATL::CComPtr<IAppHostElement>>(ATL::CComPtr<IAppHostElement> &)'::`2'::bstrExtension
0x18000a6da  mov     rax, [rax+28h]
0x18000a6de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6e3  test    eax, eax
0x18000a6e5  jns     short loc_18000A6FB
0x18000a6e7  mov     [rbp+pExceptionObject], eax
0x18000a6ea  lea     rdx, _TI1J; pThrowInfo
0x18000a6f1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000a6f5  call    _CxxThrowException_0
0x18000a6fb  cmp     word ptr [rbp+pvarg], 1
0x18000a700  setnz   bl
0x18000a703  lea     rcx, [rbp+pvarg]; pvarg
0x18000a707  call    cs:__imp_VariantClear
0x18000a70d  nop
0x18000a70e  lea     rcx, [rbp+arg_8]
0x18000a712  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000a717  mov     al, bl
0x18000a719  mov     rbx, [rsp+40h+arg_10]
0x18000a71e  add     rsp, 40h
0x18000a722  pop     rbp
0x18000a723  retn
```
