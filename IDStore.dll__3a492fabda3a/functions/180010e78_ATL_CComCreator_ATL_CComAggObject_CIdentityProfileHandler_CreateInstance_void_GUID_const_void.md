# ATL::CComCreator<ATL::CComAggObject<CIdentityProfileHandler>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180010e78`
- end: `0x180010f9f`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCIdentityProfileHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `295`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007f40`

## callees

- `0x180006230`
- `0x180007c30`
- `0x18000f088`
- `0x180010e78`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CIdentityProfileHandler>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v7; // esi
  _DWORD *v8; // rax
  _DWORD *v9; // rdi
  int v10; // ecx
  int v11; // eax
  int v12; // ecx
  _DWORD *v13; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0x78u);
    v9 = v8;
    if ( v8 )
    {
      v8[2] = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CIdentityProfileHandler>::`vftable';
      CIdentityProfileHandler::CIdentityProfileHandler((CIdentityProfileHandler *)(v8 + 6));
      *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CIdentityProfileHandler>::`vftable';
      *((_QWORD *)v9 + 4) = a1;
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
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 10));
    if ( v10 >= 0 )
      *((_BYTE *)v9 + 80) = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v12 = 0;
    if ( v11 < 0 )
      v12 = v11;
    v7 = 0;
    if ( v12 < 0 )
      v7 = v12;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180010e78  mov     [rsp+arg_0], rbx
0x180010e7d  mov     [rsp+arg_10], r8
0x180010e82  mov     [rsp+arg_8], rdx
0x180010e87  push    rsi
0x180010e88  push    rdi
0x180010e89  push    r12
0x180010e8b  push    r14
0x180010e8d  push    r15
0x180010e8f  sub     rsp, 30h
0x180010e93  mov     r14, r8
0x180010e96  mov     r15, rdx
0x180010e99  mov     r12, rcx
0x180010e9c  test    r8, r8
0x180010e9f  jnz     short loc_180010EAB
0x180010ea1  mov     eax, 80004003h
0x180010ea6  jmp     loc_180010F8D
0x180010eab  mov     qword ptr [r8], 0
0x180010eb2  mov     esi, 8007000Eh
0x180010eb7  mov     [rsp+58h+arg_18], esi
0x180010ebb  mov     [rsp+58h+var_38], 0
0x180010ec4  mov     ecx, 78h ; 'x'; Size
0x180010ec9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010ece  mov     rdi, rax
0x180010ed1  test    rdi, rdi
0x180010ed4  jz      short loc_180010F12
0x180010ed6  mov     dword ptr [rax+8], 0
0x180010edd  lea     rax, ??_7?$CComAggObject@VCIdentityProfileHandler@@@ATL@@6B@; const ATL::CComAggObject<CIdentityProfileHandler>::`vftable'
0x180010ee4  mov     [rdi], rax
0x180010ee7  lea     rcx, [rdi+18h]; this
0x180010eeb  call    ??0CIdentityProfileHandler@@QEAA@XZ; CIdentityProfileHandler::CIdentityProfileHandler(void)
0x180010ef0  lea     rax, ??_7?$CComContainedObject@VCIdentityProfileHandler@@@ATL@@6B@; const ATL::CComContainedObject<CIdentityProfileHandler>::`vftable'
0x180010ef7  mov     [rdi+18h], rax
0x180010efb  mov     [rdi+20h], r12
0x180010eff  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180010f06  mov     rax, [rcx]
0x180010f09  mov     rax, [rax+8]
0x180010f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f12  mov     [rsp+58h+var_38], rdi
0x180010f17  jmp     short loc_180010F2C
0x180010f19  mov     r14, [rsp+58h+arg_10]
0x180010f1e  mov     r15, [rsp+58h+arg_8]
0x180010f23  mov     esi, [rsp+58h+arg_18]
0x180010f27  mov     rdi, [rsp+58h+var_38]
0x180010f2c  test    rdi, rdi
0x180010f2f  jz      short loc_180010F8B
0x180010f31  lea     rcx, [rdi+28h]; this
0x180010f35  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180010f3a  mov     ecx, eax
0x180010f3c  test    eax, eax
0x180010f3e  js      short loc_180010F44
0x180010f40  mov     byte ptr [rdi+50h], 1
0x180010f44  xor     eax, eax
0x180010f46  test    ecx, ecx
0x180010f48  cmovs   eax, ecx
0x180010f4b  xor     ecx, ecx
0x180010f4d  test    eax, eax
0x180010f4f  cmovs   ecx, eax
0x180010f52  xor     esi, esi
0x180010f54  test    ecx, ecx
0x180010f56  cmovs   esi, ecx
0x180010f59  test    esi, esi
0x180010f5b  jnz     short loc_180010F77
0x180010f5d  mov     rax, [rdi]
0x180010f60  mov     r8, r14
0x180010f63  mov     rdx, r15
0x180010f66  mov     rcx, rdi
0x180010f69  mov     rax, [rax]
0x180010f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f71  mov     esi, eax
0x180010f73  test    eax, eax
0x180010f75  jz      short loc_180010F8B
0x180010f77  mov     r8, [rdi]
0x180010f7a  mov     edx, 1
0x180010f7f  mov     rcx, rdi
0x180010f82  mov     rax, [r8+18h]
0x180010f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f8b  mov     eax, esi
0x180010f8d  mov     rbx, [rsp+58h+arg_0]
0x180010f92  add     rsp, 30h
0x180010f96  pop     r15
0x180010f98  pop     r14
0x180010f9a  pop     r12
0x180010f9c  pop     rdi
0x180010f9d  pop     rsi
0x180010f9e  retn
```
