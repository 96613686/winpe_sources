# ATL::CComCreator<ATL::CComObject<CBrowserCap>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003b20`
- end: `0x180003c3f`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCBrowserCap@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800039b0`

## callees

- `0x180003b20`
- `0x180004480`
- `0x180007358`
- `0x1800099f8`
- `0x18000d010`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x180003bf4`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x180003bf4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CBrowserCap>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // ebx
  CBrowserCap *v7; // rax
  CBrowserCap *v8; // rdi
  HRESULT FreeThreadedMarshaler; // eax
  IUnknown *v10; // rax
  CBrowserCap *v13; // [rsp+78h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (CBrowserCap *)operator new(0x90u);
    v8 = v7;
    if ( v7 )
    {
      CBrowserCap::CBrowserCap(v7);
      *(_QWORD *)v8 = &ATL::CComObject<CBrowserCap>::`vftable'{for `ISupportErrorInfo'};
      *((_QWORD *)v8 + 1) = &ATL::CComObject<CBrowserCap>::`vftable'{for `ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v13 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v13;
  }
  if ( v8 )
  {
    FreeThreadedMarshaler = ATL::CComCriticalSection::Init((CBrowserCap *)((char *)v8 + 24));
    if ( FreeThreadedMarshaler >= 0 )
    {
      *((_BYTE *)v8 + 64) = 1;
      v10 = (IUnknown *)(*(__int64 (__fastcall **)(CBrowserCap *))(*(_QWORD *)v8 + 32LL))(v8);
      FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v10, (LPUNKNOWN *)v8 + 9);
    }
    v6 = 0;
    if ( FreeThreadedMarshaler < 0 )
      v6 = FreeThreadedMarshaler;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CBrowserCap *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(CBrowserCap *, __int64))(*(_QWORD *)v8 + 40LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180003b20  mov     [rsp+arg_10], r8
0x180003b25  mov     [rsp+arg_8], rdx
0x180003b2a  mov     [rsp+arg_0], rcx
0x180003b2f  push    rbx
0x180003b30  push    rsi
0x180003b31  push    rdi
0x180003b32  push    r14
0x180003b34  sub     rsp, 38h
0x180003b38  mov     rsi, r8
0x180003b3b  mov     r14, rdx
0x180003b3e  test    r8, r8
0x180003b41  jnz     short loc_180003B4D
0x180003b43  mov     eax, 80004003h
0x180003b48  jmp     loc_180003C35
0x180003b4d  mov     qword ptr [r8], 0
0x180003b54  mov     ebx, 8007000Eh
0x180003b59  mov     dword ptr [rsp+58h+arg_0], ebx
0x180003b5d  mov     [rsp+58h+arg_18], 0
0x180003b66  mov     ecx, 90h; unsigned __int64
0x180003b6b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003b70  mov     rdi, rax
0x180003b73  mov     [rsp+58h+var_38], rax
0x180003b78  test    rdi, rdi
0x180003b7b  jz      short loc_180003BAE
0x180003b7d  mov     rcx, rax; this
0x180003b80  call    ??0CBrowserCap@@QEAA@XZ; CBrowserCap::CBrowserCap(void)
0x180003b85  lea     rax, ??_7?$CComObject@VCBrowserCap@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CBrowserCap>::`vftable'{for `ISupportErrorInfo'}
0x180003b8c  mov     [rdi], rax
0x180003b8f  lea     rax, ??_7?$CComObject@VCBrowserCap@@@ATL@@6B?$IDispatchImpl@UIBrowserCap@@$1?IID_IBrowserCap@@3U_GUID@@B$1?LIBID_BrowserType@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CBrowserCap>::`vftable'{for `ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>'}
0x180003b96  mov     [rdi+8], rax
0x180003b9a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003ba1  mov     rax, [rcx]
0x180003ba4  mov     rax, [rax+8]
0x180003ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bad  nop
0x180003bae  mov     [rsp+58h+arg_18], rdi
0x180003bb3  jmp     short loc_180003BC8
0x180003bb5  mov     rsi, [rsp+58h+arg_10]
0x180003bba  mov     r14, [rsp+58h+arg_8]
0x180003bbf  mov     ebx, dword ptr [rsp+58h+arg_0]
0x180003bc3  mov     rdi, [rsp+58h+arg_18]
0x180003bc8  test    rdi, rdi
0x180003bcb  jz      short loc_180003C33
0x180003bcd  lea     rcx, [rdi+18h]; this
0x180003bd1  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003bd6  test    eax, eax
0x180003bd8  js      short loc_180003BFA
0x180003bda  mov     byte ptr [rdi+40h], 1
0x180003bde  mov     rax, [rdi]
0x180003be1  mov     rcx, rdi
0x180003be4  mov     rax, [rax+20h]
0x180003be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bed  mov     rcx, rax; punkOuter
0x180003bf0  lea     rdx, [rdi+48h]; ppunkMarshal
0x180003bf4  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180003bfa  xor     ebx, ebx
0x180003bfc  test    eax, eax
0x180003bfe  cmovs   ebx, eax
0x180003c01  test    ebx, ebx
0x180003c03  jnz     short loc_180003C1F
0x180003c05  mov     rax, [rdi]
0x180003c08  mov     r8, rsi
0x180003c0b  mov     rdx, r14
0x180003c0e  mov     rcx, rdi
0x180003c11  mov     rax, [rax]
0x180003c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c19  mov     ebx, eax
0x180003c1b  test    eax, eax
0x180003c1d  jz      short loc_180003C33
0x180003c1f  mov     r8, [rdi]
0x180003c22  mov     edx, 1
0x180003c27  mov     rcx, rdi
0x180003c2a  mov     rax, [r8+28h]
0x180003c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c33  mov     eax, ebx
0x180003c35  add     rsp, 38h
0x180003c39  pop     r14
0x180003c3b  pop     rdi
0x180003c3c  pop     rsi
0x180003c3d  pop     rbx
0x180003c3e  retn
```
