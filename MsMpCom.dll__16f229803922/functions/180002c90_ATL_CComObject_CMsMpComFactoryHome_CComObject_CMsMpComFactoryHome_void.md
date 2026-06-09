# ATL::CComObject<CMsMpComFactoryHome>::~CComObject<CMsMpComFactoryHome>(void)

- ea: `0x180002c90`
- end: `0x180002cf9`
- name: `??1?$CComObject@VCMsMpComFactoryHome@@@ATL@@UEAA@XZ`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180002e90`

## callees

- `0x180002c90`
- `0x18000a010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002ced`
- `KERNEL32!DeleteCriticalSection` at `0x180002ced`
- `mpclient!MpConfigUninitialize` at `0x180002ccf`
- `mpclient!MpConfigUninitialize` at `0x180002ccf`

## pseudocode

```c
void __fastcall ATL::CComObject<CMsMpComFactoryHome>::~CComObject<CMsMpComFactoryHome>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CMsMpComFactoryHome>::`vftable'{for `MP_CComObjectRootEx'};
  *(_QWORD *)(a1 + 64) = &ATL::CComObject<CMsMpComFactoryHome>::`vftable'{for `ATL::IDispatchImpl<IMsMpComFactory,&_GUID const IID_IMsMpComFactory,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( *(_QWORD *)(a1 + 72) )
    MpConfigUninitialize();
  *(_QWORD *)a1 = &MP_CComObjectRootEx::`vftable';
  if ( *(_BYTE *)(a1 + 56) )
  {
    *(_BYTE *)(a1 + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  }
}

```

## disassembly

```asm
0x180002c90  push    rbx
0x180002c92  sub     rsp, 20h
0x180002c96  mov     dword ptr [rcx+8], 0C0000001h
0x180002c9d  lea     rax, ??_7?$CComObject@VCMsMpComFactoryHome@@@ATL@@6BMP_CComObjectRootEx@@@; const ATL::CComObject<CMsMpComFactoryHome>::`vftable'{for `MP_CComObjectRootEx'}
0x180002ca4  mov     [rcx], rax
0x180002ca7  mov     rbx, rcx
0x180002caa  lea     rax, ??_7?$CComObject@VCMsMpComFactoryHome@@@ATL@@6B?$IDispatchImpl@UIMsMpComFactory@@$1?IID_IMsMpComFactory@@3U_GUID@@B$1?LIBID_MpComExportsLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMsMpComFactoryHome>::`vftable'{for `ATL::IDispatchImpl<IMsMpComFactory,&_GUID const IID_IMsMpComFactory,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>'}
0x180002cb1  mov     [rcx+40h], rax
0x180002cb5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002cbc  mov     rax, [rcx]
0x180002cbf  mov     rax, [rax+10h]
0x180002cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cc8  cmp     qword ptr [rbx+48h], 0
0x180002ccd  jz      short loc_180002CD5
0x180002ccf  call    cs:__imp_MpConfigUninitialize
0x180002cd5  lea     rax, ??_7MP_CComObjectRootEx@@6B@; const MP_CComObjectRootEx::`vftable'
0x180002cdc  lea     rcx, [rbx+10h]; lpCriticalSection
0x180002ce0  mov     [rbx], rax
0x180002ce3  cmp     byte ptr [rcx+28h], 0
0x180002ce7  jz      short loc_180002CF3
0x180002ce9  mov     byte ptr [rcx+28h], 0
0x180002ced  call    cs:__imp_DeleteCriticalSection
0x180002cf3  add     rsp, 20h
0x180002cf7  pop     rbx
0x180002cf8  retn
```
