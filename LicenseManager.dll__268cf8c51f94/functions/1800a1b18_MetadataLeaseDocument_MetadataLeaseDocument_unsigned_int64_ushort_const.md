# MetadataLeaseDocument::MetadataLeaseDocument(unsigned __int64,ushort const *)

- ea: `0x1800a1b18`
- end: `0x1800a1ccf`
- name: `??0MetadataLeaseDocument@@QEAA@_KPEBG@Z`
- size: `439`
- prototype: `MetadataLeaseDocument *__fastcall(MetadataLeaseDocument *__hidden this, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800972c4`

## callees

- `0x18006a3b0`
- `0x18007b210`
- `0x1800a1af4`
- `0x1800a1b18`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800a1c9a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800a1c9a`
- `RPCRT4!UuidCreate` at `0x1800a1ca4`
- `RPCRT4!UuidCreate` at `0x1800a1ca4`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
MetadataLeaseDocument *__fastcall MetadataLeaseDocument::MetadataLeaseDocument(
        MetadataLeaseDocument *this,
        __int64 a2,
        const unsigned __int16 *a3)
{
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IStoredLicenseDocument,IStoredLeaseDocument,IClipLeaseCatalogInfo>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IStoredLicenseDocument,IStoredLeaseDocument,IClipLeaseCatalogInfo>();
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStoredLicenseDocument,IStoredLeaseDocument,IClipLeaseCatalogInfo>::`vftable';
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStoredLicenseDocument,IStoredLeaseDocument,IClipLeaseCatalogInfo>::`vftable'{for `IStoredLeaseDocument'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStoredLicenseDocument,IStoredLeaseDocument,IClipLeaseCatalogInfo>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IClipLeaseCatalogInfo>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &MetadataLeaseDocument::`vftable';
  *((_QWORD *)this + 1) = &MetadataLeaseDocument::`vftable'{for `IStoredLeaseDocument'};
  *((_QWORD *)this + 2) = &MetadataLeaseDocument::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IClipLeaseCatalogInfo>'};
  *((_OWORD *)this + 2) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 7;
  *((_WORD *)this + 16) = 0;
  *((_QWORD *)this + 8) = 0x10000;
  *(_OWORD *)((char *)this + 72) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 7;
  *((_WORD *)this + 36) = 0;
  *(_OWORD *)((char *)this + 104) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 7;
  *((_WORD *)this + 52) = 0;
  *(_OWORD *)((char *)this + 136) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 7;
  *((_WORD *)this + 68) = 0;
  *(_OWORD *)((char *)this + 168) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 7;
  *((_WORD *)this + 84) = 0;
  *(_OWORD *)((char *)this + 200) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 7;
  *((_WORD *)this + 100) = 0;
  *(_OWORD *)((char *)this + 232) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 7;
  *((_WORD *)this + 116) = 0;
  *(_OWORD *)((char *)this + 264) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 7;
  *((_WORD *)this + 132) = 0;
  web::json::value::value((MetadataLeaseDocument *)((char *)this + 296));
  *((_DWORD *)this + 76) = 0;
  *(GUID *)((char *)this + 308) = GUID_NULL;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 328), 0, 0);
  UuidCreate((UUID *)((char *)this + 308));
  std::wstring::_Assign<unsigned short>((char *)this + 32, a3, a2);
  return this;
}

```

## disassembly

```asm
0x1800a1b18  mov     [rsp+arg_8], rbx
0x1800a1b1d  mov     [rsp+arg_10], rbp
0x1800a1b22  mov     [rsp+arg_0], rcx
0x1800a1b27  push    rsi
0x1800a1b28  push    rdi
0x1800a1b29  push    r14
0x1800a1b2b  sub     rsp, 20h
0x1800a1b2f  mov     rbp, r8
0x1800a1b32  mov     r14, rdx
0x1800a1b35  mov     rsi, rcx
0x1800a1b38  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIStoredLicenseDocument@@UIStoredLeaseDocument@@UIClipLeaseCatalogInfo@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IStoredLicenseDocument,IStoredLeaseDocument,IClipLeaseCatalogInfo>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IStoredLicenseDocument,IStoredLeaseDocument,IClipLeaseCatalogInfo>(void)
0x1800a1b3d  lea     r9, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIStoredLicenseDocument@@UIStoredLeaseDocument@@UIClipLeaseCatalogInfo@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStoredLicenseDocument,IStoredLeaseDocument,IClipLeaseCatalogInfo>::`vftable'
0x1800a1b44  mov     [rsi], r9
0x1800a1b47  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIStoredLicenseDocument@@UIStoredLeaseDocument@@UIClipLeaseCatalogInfo@@@WRL@Microsoft@@6BIStoredLeaseDocument@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStoredLicenseDocument,IStoredLeaseDocument,IClipLeaseCatalogInfo>::`vftable'{for `IStoredLeaseDocument'}
0x1800a1b4e  mov     [rsi+8], rax
0x1800a1b52  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIStoredLicenseDocument@@UIStoredLeaseDocument@@UIClipLeaseCatalogInfo@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIClipLeaseCatalogInfo@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStoredLicenseDocument,IStoredLeaseDocument,IClipLeaseCatalogInfo>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IClipLeaseCatalogInfo>'}
0x1800a1b59  mov     [rsi+10h], rax
0x1800a1b5d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800a1b64  xor     ebx, ebx
0x1800a1b66  test    rcx, rcx
0x1800a1b69  jz      short loc_1800A1B78
0x1800a1b6b  mov     rax, [rcx]
0x1800a1b6e  mov     rax, [rax+8]
0x1800a1b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1b77  nop
0x1800a1b78  lea     rax, ??_7MetadataLeaseDocument@@6B@; const MetadataLeaseDocument::`vftable'
0x1800a1b7f  mov     [rsi], rax
0x1800a1b82  lea     rax, ??_7MetadataLeaseDocument@@6BIStoredLeaseDocument@@@; const MetadataLeaseDocument::`vftable'{for `IStoredLeaseDocument'}
0x1800a1b89  mov     [rsi+8], rax
0x1800a1b8d  lea     rax, ??_7MetadataLeaseDocument@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIClipLeaseCatalogInfo@@@Details@WRL@Microsoft@@@; const MetadataLeaseDocument::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IClipLeaseCatalogInfo>'}
0x1800a1b94  mov     [rsi+10h], rax
0x1800a1b98  lea     rdi, [rsi+20h]
0x1800a1b9c  xorps   xmm0, xmm0
0x1800a1b9f  movups  xmmword ptr [rdi], xmm0
0x1800a1ba2  mov     [rdi+10h], rbx
0x1800a1ba6  mov     ecx, 7
0x1800a1bab  mov     [rdi+18h], rcx
0x1800a1baf  mov     [rdi], bx
0x1800a1bb2  mov     qword ptr [rsi+40h], 10000h
0x1800a1bba  movups  xmmword ptr [rsi+48h], xmm0
0x1800a1bbe  mov     [rsi+58h], rbx
0x1800a1bc2  mov     [rsi+60h], rcx
0x1800a1bc6  mov     [rsi+48h], bx
0x1800a1bca  movups  xmmword ptr [rsi+68h], xmm0
0x1800a1bce  mov     [rsi+78h], rbx
0x1800a1bd2  mov     [rsi+80h], rcx
0x1800a1bd9  mov     [rsi+68h], bx
0x1800a1bdd  movups  xmmword ptr [rsi+88h], xmm0
0x1800a1be4  mov     [rsi+98h], rbx
0x1800a1beb  mov     [rsi+0A0h], rcx
0x1800a1bf2  mov     [rsi+88h], bx
0x1800a1bf9  movups  xmmword ptr [rsi+0A8h], xmm0
0x1800a1c00  mov     [rsi+0B8h], rbx
0x1800a1c07  mov     [rsi+0C0h], rcx
0x1800a1c0e  mov     [rsi+0A8h], bx
0x1800a1c15  movups  xmmword ptr [rsi+0C8h], xmm0
0x1800a1c1c  mov     [rsi+0D8h], rbx
0x1800a1c23  mov     [rsi+0E0h], rcx
0x1800a1c2a  mov     [rsi+0C8h], bx
0x1800a1c31  movups  xmmword ptr [rsi+0E8h], xmm0
0x1800a1c38  mov     [rsi+0F8h], rbx
0x1800a1c3f  mov     [rsi+100h], rcx
0x1800a1c46  mov     [rsi+0E8h], bx
0x1800a1c4d  movups  xmmword ptr [rsi+108h], xmm0
0x1800a1c54  mov     [rsi+118h], rbx
0x1800a1c5b  mov     [rsi+120h], rcx
0x1800a1c62  mov     [rsi+108h], bx
0x1800a1c69  lea     rcx, [rsi+128h]; this
0x1800a1c70  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x1800a1c75  nop
0x1800a1c76  mov     [rsi+130h], ebx
0x1800a1c7c  lea     rbx, [rsi+134h]
0x1800a1c83  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800a1c8a  movdqu  xmmword ptr [rbx], xmm0
0x1800a1c8e  lea     rcx, [rsi+148h]; lpCriticalSection
0x1800a1c95  xor     r8d, r8d; Flags
0x1800a1c98  xor     edx, edx; dwSpinCount
0x1800a1c9a  call    cs:__imp_InitializeCriticalSectionEx
0x1800a1ca0  nop
0x1800a1ca1  mov     rcx, rbx; Uuid
0x1800a1ca4  call    cs:__imp_UuidCreate
0x1800a1caa  mov     r8, r14
0x1800a1cad  mov     rdx, rbp
0x1800a1cb0  mov     rcx, rdi
0x1800a1cb3  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800a1cb8  nop
0x1800a1cb9  mov     rax, rsi
0x1800a1cbc  mov     rbx, [rsp+38h+arg_8]
0x1800a1cc1  mov     rbp, [rsp+38h+arg_10]
0x1800a1cc6  add     rsp, 20h
0x1800a1cca  pop     r14
0x1800a1ccc  pop     rdi
0x1800a1ccd  pop     rsi
0x1800a1cce  retn
```
