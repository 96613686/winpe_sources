# ATL::CComObject<CMsMpClientUtils>::CreateInstance(ATL::CComObject<CMsMpClientUtils> * *)

- ea: `0x1800038bc`
- end: `0x1800039b3`
- name: `?CreateInstance@?$CComObject@VCMsMpClientUtils@@@ATL@@SAJPEAPEAV12@@Z`
- size: `247`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002920`

## callees

- `0x18000126c`
- `0x18000233c`
- `0x1800038bc`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMsMpClientUtils>::CreateInstance(_QWORD *a1)
{
  _QWORD *v1; // r14
  unsigned int v3; // esi
  _DWORD *v4; // rax
  _DWORD *v5; // rdi
  int v6; // ecx
  int v7; // eax
  _DWORD *v9; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
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
      *(_QWORD *)v4 = &ATL::CComObject<CMsMpClientUtils>::`vftable'{for `MP_CComObjectRootEx'};
      *((_QWORD *)v4 + 8) = &ATL::CComObject<CMsMpClientUtils>::`vftable'{for `ATL::IDispatchImpl<IMsMpClientUtils,&__s_GUID const _GUID_e2d74550_8e41_460e_bb51_52e1f9522134,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v9 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v9;
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
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x1800038bc  mov     [rsp+arg_0], rcx
0x1800038c1  push    rsi
0x1800038c2  push    rdi
0x1800038c3  push    r14
0x1800038c5  sub     rsp, 20h
0x1800038c9  mov     r14, rcx
0x1800038cc  test    rcx, rcx
0x1800038cf  jnz     short loc_1800038DB
0x1800038d1  mov     eax, 80004003h
0x1800038d6  jmp     loc_1800039AA
0x1800038db  mov     qword ptr [rcx], 0
0x1800038e2  mov     esi, 8007000Eh
0x1800038e7  mov     [rsp+38h+arg_8], esi
0x1800038eb  mov     [rsp+38h+arg_10], 0
0x1800038f4  mov     ecx, 58h ; 'X'; Size
0x1800038f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800038fe  mov     rdi, rax
0x180003901  test    rdi, rdi
0x180003904  jz      short loc_180003951
0x180003906  mov     dword ptr [rax+8], 0
0x18000390d  xorps   xmm0, xmm0
0x180003910  xor     eax, eax
0x180003912  movups  xmmword ptr [rdi+10h], xmm0
0x180003916  movups  xmmword ptr [rdi+20h], xmm0
0x18000391a  mov     [rdi+30h], rax
0x18000391e  mov     [rdi+38h], al
0x180003921  mov     [rdi+48h], rax
0x180003925  mov     [rdi+50h], rax
0x180003929  lea     rax, ??_7?$CComObject@VCMsMpClientUtils@@@ATL@@6BMP_CComObjectRootEx@@@; const ATL::CComObject<CMsMpClientUtils>::`vftable'{for `MP_CComObjectRootEx'}
0x180003930  mov     [rdi], rax
0x180003933  lea     rax, ??_7?$CComObject@VCMsMpClientUtils@@@ATL@@6B?$IDispatchImpl@UIMsMpClientUtils@@$1?_GUID_e2d74550_8e41_460e_bb51_52e1f9522134@@3U__s_GUID@@B$1?LIBID_MpComExportsLib@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMsMpClientUtils>::`vftable'{for `ATL::IDispatchImpl<IMsMpClientUtils,&__s_GUID const _GUID_e2d74550_8e41_460e_bb51_52e1f9522134,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>'}
0x18000393a  mov     [rdi+40h], rax
0x18000393e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003945  mov     rax, [rcx]
0x180003948  mov     rax, [rax+8]
0x18000394c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003951  mov     [rsp+38h+arg_10], rdi
0x180003956  jmp     short loc_180003966
0x180003958  mov     r14, [rsp+38h+arg_0]
0x18000395d  mov     esi, [rsp+38h+arg_8]
0x180003961  mov     rdi, [rsp+38h+arg_10]
0x180003966  test    rdi, rdi
0x180003969  jz      short loc_1800039A5
0x18000396b  lea     rcx, [rdi+10h]; this
0x18000396f  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003974  mov     ecx, eax
0x180003976  test    eax, eax
0x180003978  js      short loc_18000397E
0x18000397a  mov     byte ptr [rdi+38h], 1
0x18000397e  xor     eax, eax
0x180003980  test    ecx, ecx
0x180003982  cmovs   eax, ecx
0x180003985  xor     esi, esi
0x180003987  test    eax, eax
0x180003989  cmovs   esi, eax
0x18000398c  test    esi, esi
0x18000398e  jz      short loc_1800039A5
0x180003990  mov     rax, [rdi]
0x180003993  mov     edx, 1
0x180003998  mov     rcx, rdi
0x18000399b  mov     rax, [rax]
0x18000399e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039a3  xor     edi, edi
0x1800039a5  mov     [r14], rdi
0x1800039a8  mov     eax, esi
0x1800039aa  add     rsp, 20h
0x1800039ae  pop     r14
0x1800039b0  pop     rdi
0x1800039b1  pop     rsi
0x1800039b2  retn
```
