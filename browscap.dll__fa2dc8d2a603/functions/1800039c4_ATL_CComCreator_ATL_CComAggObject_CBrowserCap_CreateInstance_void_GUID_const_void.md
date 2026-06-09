# ATL::CComCreator<ATL::CComAggObject<CBrowserCap>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800039c4`
- end: `0x180003b19`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCBrowserCap@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800039b0`

## callees

- `0x1800039c4`
- `0x180004480`
- `0x180007358`
- `0x1800099f8`
- `0x18000d010`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x180003ac6`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x180003ac6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CBrowserCap>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r15
  unsigned int v7; // ebx
  _DWORD *v8; // rax
  _DWORD *v9; // rdi
  int v10; // ecx
  HRESULT FreeThreadedMarshaler; // eax
  IUnknown *v12; // rax
  _DWORD *v13; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0xA8u);
    v9 = v8;
    if ( v8 )
    {
      v8[2] = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CBrowserCap>::`vftable';
      CBrowserCap::CBrowserCap((CBrowserCap *)(v8 + 6));
      *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CBrowserCap>::`vftable'{for `ISupportErrorInfo'};
      *((_QWORD *)v9 + 4) = &ATL::CComContainedObject<CBrowserCap>::`vftable'{for `ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)v9 + 5) = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v13 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v13;
  }
  if ( v9 )
  {
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 12));
    if ( v10 >= 0 )
      *((_BYTE *)v9 + 88) = 1;
    FreeThreadedMarshaler = 0;
    if ( v10 < 0 )
      FreeThreadedMarshaler = v10;
    if ( FreeThreadedMarshaler >= 0 )
    {
      v12 = (IUnknown *)(*(__int64 (__fastcall **)(_DWORD *))(*((_QWORD *)v9 + 3) + 32LL))(v9 + 6);
      FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v12, (LPUNKNOWN *)v9 + 12);
    }
    v7 = 0;
    if ( FreeThreadedMarshaler < 0 )
      v7 = FreeThreadedMarshaler;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x1800039c4  mov     [rsp+arg_0], rbx
0x1800039c9  mov     [rsp+arg_10], r8
0x1800039ce  mov     [rsp+arg_8], rdx
0x1800039d3  push    rsi
0x1800039d4  push    rdi
0x1800039d5  push    r12
0x1800039d7  push    r14
0x1800039d9  push    r15
0x1800039db  sub     rsp, 30h
0x1800039df  mov     rsi, r8
0x1800039e2  mov     r15, rdx
0x1800039e5  mov     r12, rcx
0x1800039e8  test    r8, r8
0x1800039eb  jnz     short loc_1800039F7
0x1800039ed  mov     eax, 80004003h
0x1800039f2  jmp     loc_180003B07
0x1800039f7  mov     qword ptr [r8], 0
0x1800039fe  mov     ebx, 8007000Eh
0x180003a03  mov     [rsp+58h+arg_18], ebx
0x180003a07  mov     [rsp+58h+var_38], 0
0x180003a10  mov     ecx, 0A8h; unsigned __int64
0x180003a15  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003a1a  mov     rdi, rax
0x180003a1d  mov     [rsp+58h+var_30], rax
0x180003a22  test    rdi, rdi
0x180003a25  jz      short loc_180003A6F
0x180003a27  mov     dword ptr [rax+8], 0
0x180003a2e  lea     rax, ??_7?$CComAggObject@VCBrowserCap@@@ATL@@6B@; const ATL::CComAggObject<CBrowserCap>::`vftable'
0x180003a35  mov     [rdi], rax
0x180003a38  lea     rcx, [rdi+18h]; this
0x180003a3c  call    ??0CBrowserCap@@QEAA@XZ; CBrowserCap::CBrowserCap(void)
0x180003a41  lea     rax, ??_7?$CComContainedObject@VCBrowserCap@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CBrowserCap>::`vftable'{for `ISupportErrorInfo'}
0x180003a48  mov     [rdi+18h], rax
0x180003a4c  lea     rax, ??_7?$CComContainedObject@VCBrowserCap@@@ATL@@6B?$IDispatchImpl@UIBrowserCap@@$1?IID_IBrowserCap@@3U_GUID@@B$1?LIBID_BrowserType@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CBrowserCap>::`vftable'{for `ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>'}
0x180003a53  mov     [rdi+20h], rax
0x180003a57  mov     [rdi+28h], r12
0x180003a5b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003a62  mov     rax, [rcx]
0x180003a65  mov     rax, [rax+8]
0x180003a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a6e  nop
0x180003a6f  mov     [rsp+58h+var_38], rdi
0x180003a74  jmp     short loc_180003A89
0x180003a76  mov     rsi, [rsp+58h+arg_10]
0x180003a7b  mov     r15, [rsp+58h+arg_8]
0x180003a80  mov     ebx, [rsp+58h+arg_18]
0x180003a84  mov     rdi, [rsp+58h+var_38]
0x180003a89  test    rdi, rdi
0x180003a8c  jz      short loc_180003B05
0x180003a8e  lea     rcx, [rdi+30h]; this
0x180003a92  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003a97  mov     ecx, eax
0x180003a99  test    eax, eax
0x180003a9b  js      short loc_180003AA1
0x180003a9d  mov     byte ptr [rdi+58h], 1
0x180003aa1  xor     eax, eax
0x180003aa3  test    ecx, ecx
0x180003aa5  cmovs   eax, ecx
0x180003aa8  test    eax, eax
0x180003aaa  js      short loc_180003ACC
0x180003aac  lea     rcx, [rdi+18h]
0x180003ab0  lea     rbx, [rcx+48h]
0x180003ab4  mov     rax, [rcx]
0x180003ab7  mov     rax, [rax+20h]
0x180003abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ac0  mov     rcx, rax; punkOuter
0x180003ac3  mov     rdx, rbx; ppunkMarshal
0x180003ac6  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180003acc  xor     ebx, ebx
0x180003ace  test    eax, eax
0x180003ad0  cmovs   ebx, eax
0x180003ad3  test    ebx, ebx
0x180003ad5  jnz     short loc_180003AF1
0x180003ad7  mov     rax, [rdi]
0x180003ada  mov     r8, rsi
0x180003add  mov     rdx, r15
0x180003ae0  mov     rcx, rdi
0x180003ae3  mov     rax, [rax]
0x180003ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aeb  mov     ebx, eax
0x180003aed  test    eax, eax
0x180003aef  jz      short loc_180003B05
0x180003af1  mov     r8, [rdi]
0x180003af4  mov     edx, 1
0x180003af9  mov     rcx, rdi
0x180003afc  mov     rax, [r8+18h]
0x180003b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b05  mov     eax, ebx
0x180003b07  mov     rbx, [rsp+58h+arg_0]
0x180003b0c  add     rsp, 30h
0x180003b10  pop     r15
0x180003b12  pop     r14
0x180003b14  pop     r12
0x180003b16  pop     rdi
0x180003b17  pop     rsi
0x180003b18  retn
```
