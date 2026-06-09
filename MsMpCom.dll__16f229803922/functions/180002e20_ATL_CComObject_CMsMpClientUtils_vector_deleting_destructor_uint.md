# ATL::CComObject<CMsMpClientUtils>::`vector deleting destructor'(uint)

- ea: `0x180002e20`
- end: `0x180002e82`
- name: `??_E?$CComObject@VCMsMpClientUtils@@@ATL@@UEAAPEAXI@Z`
- size: `98`
- prototype: `__int64 __fastcall(CMsMpClientUtils *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180002e20`
- `0x180004f60`
- `0x18000a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002e6e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002e6e`

## pseudocode

```c
CMsMpClientUtils *__fastcall ATL::CComObject<CMsMpClientUtils>::`vector deleting destructor'(
        CMsMpClientUtils *this,
        char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CMsMpClientUtils>::`vftable'{for `MP_CComObjectRootEx'};
  *((_QWORD *)this + 8) = &ATL::CComObject<CMsMpClientUtils>::`vftable'{for `ATL::IDispatchImpl<IMsMpClientUtils,&__s_GUID const _GUID_e2d74550_8e41_460e_bb51_52e1f9522134,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CMsMpClientUtils::~CMsMpClientUtils(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002e20  mov     [rsp+arg_0], rbx
0x180002e25  push    rdi
0x180002e26  sub     rsp, 20h
0x180002e2a  mov     dword ptr [rcx+8], 0C0000001h
0x180002e31  lea     rax, ??_7?$CComObject@VCMsMpClientUtils@@@ATL@@6BMP_CComObjectRootEx@@@; const ATL::CComObject<CMsMpClientUtils>::`vftable'{for `MP_CComObjectRootEx'}
0x180002e38  mov     [rcx], rax
0x180002e3b  mov     rdi, rcx
0x180002e3e  lea     rax, ??_7?$CComObject@VCMsMpClientUtils@@@ATL@@6B?$IDispatchImpl@UIMsMpClientUtils@@$1?_GUID_e2d74550_8e41_460e_bb51_52e1f9522134@@3U__s_GUID@@B$1?LIBID_MpComExportsLib@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMsMpClientUtils>::`vftable'{for `ATL::IDispatchImpl<IMsMpClientUtils,&__s_GUID const _GUID_e2d74550_8e41_460e_bb51_52e1f9522134,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>'}
0x180002e45  mov     ebx, edx
0x180002e47  mov     [rcx+40h], rax
0x180002e4b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002e52  mov     rax, [rcx]
0x180002e55  mov     rax, [rax+10h]
0x180002e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e5e  mov     rcx, rdi; this
0x180002e61  call    ??1CMsMpClientUtils@@UEAA@XZ; CMsMpClientUtils::~CMsMpClientUtils(void)
0x180002e66  test    bl, 1
0x180002e69  jz      short loc_180002E74
0x180002e6b  mov     rcx, rdi
0x180002e6e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002e74  mov     rbx, [rsp+28h+arg_0]
0x180002e79  mov     rax, rdi
0x180002e7c  add     rsp, 20h
0x180002e80  pop     rdi
0x180002e81  retn
```
