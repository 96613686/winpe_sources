# ATL::CComObject<CMsMpSimpleConfig>::`scalar deleting destructor'(uint)

- ea: `0x180002ed0`
- end: `0x180002f32`
- name: `??_G?$CComObject@VCMsMpSimpleConfig@@@ATL@@UEAAPEAXI@Z`
- size: `98`
- prototype: `__int64 __fastcall(CMsMpSimpleConfig *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x180002ed0`
- `0x180004bbc`
- `0x18000a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002f1e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002f1e`

## pseudocode

```c
CMsMpSimpleConfig *__fastcall ATL::CComObject<CMsMpSimpleConfig>::`scalar deleting destructor'(
        CMsMpSimpleConfig *this,
        char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CMsMpSimpleConfig>::`vftable'{for `MP_CComObjectRootEx'};
  *((_QWORD *)this + 8) = &ATL::CComObject<CMsMpSimpleConfig>::`vftable'{for `ATL::IDispatchImpl<IMsMpSimpleConfig,&__s_GUID const _GUID_cdfed399_7999_4309_b064_1ede04bc580d,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CMsMpSimpleConfig::~CMsMpSimpleConfig(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002ed0  mov     [rsp+arg_0], rbx
0x180002ed5  push    rdi
0x180002ed6  sub     rsp, 20h
0x180002eda  mov     dword ptr [rcx+8], 0C0000001h
0x180002ee1  lea     rax, ??_7?$CComObject@VCMsMpSimpleConfig@@@ATL@@6BMP_CComObjectRootEx@@@; const ATL::CComObject<CMsMpSimpleConfig>::`vftable'{for `MP_CComObjectRootEx'}
0x180002ee8  mov     [rcx], rax
0x180002eeb  mov     rdi, rcx
0x180002eee  lea     rax, ??_7?$CComObject@VCMsMpSimpleConfig@@@ATL@@6B?$IDispatchImpl@UIMsMpSimpleConfig@@$1?_GUID_cdfed399_7999_4309_b064_1ede04bc580d@@3U__s_GUID@@B$1?LIBID_MpComExportsLib@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMsMpSimpleConfig>::`vftable'{for `ATL::IDispatchImpl<IMsMpSimpleConfig,&__s_GUID const _GUID_cdfed399_7999_4309_b064_1ede04bc580d,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>'}
0x180002ef5  mov     ebx, edx
0x180002ef7  mov     [rcx+40h], rax
0x180002efb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002f02  mov     rax, [rcx]
0x180002f05  mov     rax, [rax+10h]
0x180002f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f0e  mov     rcx, rdi; this
0x180002f11  call    ??1CMsMpSimpleConfig@@UEAA@XZ; CMsMpSimpleConfig::~CMsMpSimpleConfig(void)
0x180002f16  test    bl, 1
0x180002f19  jz      short loc_180002F24
0x180002f1b  mov     rcx, rdi
0x180002f1e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002f24  mov     rbx, [rsp+28h+arg_0]
0x180002f29  mov     rax, rdi
0x180002f2c  add     rsp, 20h
0x180002f30  pop     rdi
0x180002f31  retn
```
