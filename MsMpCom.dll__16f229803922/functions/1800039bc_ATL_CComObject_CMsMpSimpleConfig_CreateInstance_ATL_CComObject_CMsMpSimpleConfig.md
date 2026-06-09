# ATL::CComObject<CMsMpSimpleConfig>::CreateInstance(ATL::CComObject<CMsMpSimpleConfig> * *)

- ea: `0x1800039bc`
- end: `0x180003ab3`
- name: `?CreateInstance@?$CComObject@VCMsMpSimpleConfig@@@ATL@@SAJPEAPEAV12@@Z`
- size: `247`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180002a60`

## callees

- `0x18000126c`
- `0x18000233c`
- `0x1800039bc`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMsMpSimpleConfig>::CreateInstance(_QWORD *a1)
{
  unsigned int v3; // esi
  _DWORD *v4; // rax
  _DWORD *v5; // rdi
  int v6; // ecx
  int v7; // eax

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = -2147024882;
  v4 = operator new(0x58u);
  v5 = v4;
  if ( v4 )
  {
    v4[2] = 0;
    *((_OWORD *)v4 + 1) = 0;
    *((_OWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 6) = 0;
    *((_BYTE *)v4 + 56) = 0;
    *((_QWORD *)v4 + 9) = 0;
    *((_QWORD *)v4 + 10) = 0;
    *(_QWORD *)v4 = &ATL::CComObject<CMsMpSimpleConfig>::`vftable'{for `MP_CComObjectRootEx'};
    *((_QWORD *)v4 + 8) = &ATL::CComObject<CMsMpSimpleConfig>::`vftable'{for `ATL::IDispatchImpl<IMsMpSimpleConfig,&__s_GUID const _GUID_cdfed399_7999_4309_b064_1ede04bc580d,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  if ( v5 )
  {
    v6 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v5 + 4));
    if ( v6 >= 0 )
      *((_BYTE *)v5 + 56) = 1;
    v7 = 0;
    if ( v6 < 0 )
      v7 = v6;
    v3 = 0;
    if ( v7 < 0 )
      v3 = v7;
    if ( v3 )
    {
      (**(void (__fastcall ***)(_DWORD *, __int64))v5)(v5, 1);
      v5 = 0;
    }
  }
  *a1 = v5;
  return v3;
}

```

## disassembly

```asm
0x1800039bc  mov     [rsp+arg_0], rcx
0x1800039c1  push    rsi
0x1800039c2  push    rdi
0x1800039c3  push    r14
0x1800039c5  sub     rsp, 20h
0x1800039c9  mov     r14, rcx
0x1800039cc  test    rcx, rcx
0x1800039cf  jnz     short loc_1800039DB
0x1800039d1  mov     eax, 80004003h
0x1800039d6  jmp     loc_180003AAA
0x1800039db  mov     qword ptr [rcx], 0
0x1800039e2  mov     esi, 8007000Eh
0x1800039e7  mov     [rsp+38h+arg_8], esi
0x1800039eb  mov     [rsp+38h+arg_10], 0
0x1800039f4  mov     ecx, 58h ; 'X'; Size
0x1800039f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800039fe  mov     rdi, rax
0x180003a01  test    rdi, rdi
0x180003a04  jz      short loc_180003A51
0x180003a06  mov     dword ptr [rax+8], 0
0x180003a0d  xorps   xmm0, xmm0
0x180003a10  xor     eax, eax
0x180003a12  movups  xmmword ptr [rdi+10h], xmm0
0x180003a16  movups  xmmword ptr [rdi+20h], xmm0
0x180003a1a  mov     [rdi+30h], rax
0x180003a1e  mov     [rdi+38h], al
0x180003a21  mov     [rdi+48h], rax
0x180003a25  mov     [rdi+50h], rax
0x180003a29  lea     rax, ??_7?$CComObject@VCMsMpSimpleConfig@@@ATL@@6BMP_CComObjectRootEx@@@; const ATL::CComObject<CMsMpSimpleConfig>::`vftable'{for `MP_CComObjectRootEx'}
0x180003a30  mov     [rdi], rax
0x180003a33  lea     rax, ??_7?$CComObject@VCMsMpSimpleConfig@@@ATL@@6B?$IDispatchImpl@UIMsMpSimpleConfig@@$1?_GUID_cdfed399_7999_4309_b064_1ede04bc580d@@3U__s_GUID@@B$1?LIBID_MpComExportsLib@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMsMpSimpleConfig>::`vftable'{for `ATL::IDispatchImpl<IMsMpSimpleConfig,&__s_GUID const _GUID_cdfed399_7999_4309_b064_1ede04bc580d,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>'}
0x180003a3a  mov     [rdi+40h], rax
0x180003a3e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003a45  mov     rax, [rcx]
0x180003a48  mov     rax, [rax+8]
0x180003a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a51  mov     [rsp+38h+arg_10], rdi
0x180003a56  jmp     short loc_180003A66
0x180003a58  mov     r14, [rsp+38h+arg_0]
0x180003a5d  mov     esi, [rsp+38h+arg_8]
0x180003a61  mov     rdi, [rsp+38h+arg_10]
0x180003a66  test    rdi, rdi
0x180003a69  jz      short loc_180003AA5
0x180003a6b  lea     rcx, [rdi+10h]; this
0x180003a6f  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003a74  mov     ecx, eax
0x180003a76  test    eax, eax
0x180003a78  js      short loc_180003A7E
0x180003a7a  mov     byte ptr [rdi+38h], 1
0x180003a7e  xor     eax, eax
0x180003a80  test    ecx, ecx
0x180003a82  cmovs   eax, ecx
0x180003a85  xor     esi, esi
0x180003a87  test    eax, eax
0x180003a89  cmovs   esi, eax
0x180003a8c  test    esi, esi
0x180003a8e  jz      short loc_180003AA5
0x180003a90  mov     rax, [rdi]
0x180003a93  mov     edx, 1
0x180003a98  mov     rcx, rdi
0x180003a9b  mov     rax, [rax]
0x180003a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aa3  xor     edi, edi
0x180003aa5  mov     [r14], rdi
0x180003aa8  mov     eax, esi
0x180003aaa  add     rsp, 20h
0x180003aae  pop     r14
0x180003ab0  pop     rdi
0x180003ab1  pop     rsi
0x180003ab2  retn
```
