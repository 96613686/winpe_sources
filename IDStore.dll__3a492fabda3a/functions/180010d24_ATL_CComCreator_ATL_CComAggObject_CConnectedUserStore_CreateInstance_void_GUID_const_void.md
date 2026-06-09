# ATL::CComCreator<ATL::CComAggObject<CConnectedUserStore>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180010d24`
- end: `0x180010e70`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCConnectedUserStore@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `332`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800042e0`

## callees

- `0x18000412c`
- `0x180006230`
- `0x18000f088`
- `0x180010d24`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CConnectedUserStore>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v7; // esi
  _BYTE *v8; // rax
  _BYTE *v9; // rdi
  int v10; // ecx
  int v11; // eax
  _BYTE *v12; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0xD8u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CConnectedUserStore>::`vftable';
      *((_OWORD *)v8 + 3) = 0;
      *((_OWORD *)v8 + 4) = 0;
      *((_QWORD *)v8 + 10) = 0;
      v8[88] = 0;
      *((_QWORD *)v8 + 26) = 0;
      *((_QWORD *)v8 + 3) = &ATL::CComContainedObject<CConnectedUserStore>::`vftable'{for `IConnectedUserStore2'};
      *((_QWORD *)v8 + 4) = &ATL::CComContainedObject<CConnectedUserStore>::`vftable'{for `IConnectedUserSite'};
      *((_QWORD *)v8 + 5) = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v12 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v12;
  }
  if ( v9 )
  {
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 48));
    if ( v10 >= 0 )
      v9[88] = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    if ( v11 >= 0 )
      v11 = CConnectedUserStore::FinalConstruct((CConnectedUserStore *)(v9 + 24));
    v7 = 0;
    if ( v11 < 0 )
      v7 = v11;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0 )
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180010d24  mov     [rsp+arg_0], rsi
0x180010d29  mov     [rsp+arg_10], r8
0x180010d2e  mov     [rsp+arg_8], rdx
0x180010d33  push    rdi
0x180010d34  push    r12
0x180010d36  push    r13
0x180010d38  push    r14
0x180010d3a  push    r15
0x180010d3c  sub     rsp, 30h
0x180010d40  mov     r14, r8
0x180010d43  mov     r15, rdx
0x180010d46  mov     r12, rcx
0x180010d49  test    r8, r8
0x180010d4c  jnz     short loc_180010D58
0x180010d4e  mov     eax, 80004003h
0x180010d53  jmp     loc_180010E5D
0x180010d58  mov     qword ptr [r8], 0
0x180010d5f  mov     esi, 8007000Eh
0x180010d64  mov     [rsp+58h+arg_18], esi
0x180010d68  mov     [rsp+58h+var_38], 0
0x180010d71  mov     ecx, 0D8h; Size
0x180010d76  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010d7b  mov     rdi, rax
0x180010d7e  test    rdi, rdi
0x180010d81  jz      short loc_180010DDC
0x180010d83  mov     dword ptr [rax+8], 0
0x180010d8a  lea     rax, ??_7?$CComAggObject@VCConnectedUserStore@@@ATL@@6B@; const ATL::CComAggObject<CConnectedUserStore>::`vftable'
0x180010d91  mov     [rdi], rax
0x180010d94  xorps   xmm0, xmm0
0x180010d97  xor     eax, eax
0x180010d99  movups  xmmword ptr [rdi+30h], xmm0
0x180010d9d  movups  xmmword ptr [rdi+40h], xmm0
0x180010da1  mov     [rdi+50h], rax
0x180010da5  mov     [rdi+58h], al
0x180010da8  mov     [rdi+0D0h], rax
0x180010daf  lea     rax, ??_7?$CComContainedObject@VCConnectedUserStore@@@ATL@@6BIConnectedUserStore2@@@; const ATL::CComContainedObject<CConnectedUserStore>::`vftable'{for `IConnectedUserStore2'}
0x180010db6  mov     [rdi+18h], rax
0x180010dba  lea     rax, ??_7?$CComContainedObject@VCConnectedUserStore@@@ATL@@6BIConnectedUserSite@@@; const ATL::CComContainedObject<CConnectedUserStore>::`vftable'{for `IConnectedUserSite'}
0x180010dc1  mov     [rdi+20h], rax
0x180010dc5  mov     [rdi+28h], r12
0x180010dc9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180010dd0  mov     rax, [rcx]
0x180010dd3  mov     rax, [rax+8]
0x180010dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ddc  mov     [rsp+58h+var_38], rdi
0x180010de1  jmp     short loc_180010DF6
0x180010de3  mov     r14, [rsp+58h+arg_10]
0x180010de8  mov     r15, [rsp+58h+arg_8]
0x180010ded  mov     esi, [rsp+58h+arg_18]
0x180010df1  mov     rdi, [rsp+58h+var_38]
0x180010df6  test    rdi, rdi
0x180010df9  jz      short loc_180010E5B
0x180010dfb  lea     rcx, [rdi+30h]; this
0x180010dff  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180010e04  mov     ecx, eax
0x180010e06  test    eax, eax
0x180010e08  js      short loc_180010E0E
0x180010e0a  mov     byte ptr [rdi+58h], 1
0x180010e0e  xor     eax, eax
0x180010e10  test    ecx, ecx
0x180010e12  cmovs   eax, ecx
0x180010e15  test    eax, eax
0x180010e17  js      short loc_180010E22
0x180010e19  lea     rcx, [rdi+18h]; this
0x180010e1d  call    ?FinalConstruct@CConnectedUserStore@@QEAAJXZ; CConnectedUserStore::FinalConstruct(void)
0x180010e22  xor     esi, esi
0x180010e24  test    eax, eax
0x180010e26  cmovs   esi, eax
0x180010e29  test    esi, esi
0x180010e2b  jnz     short loc_180010E47
0x180010e2d  mov     rax, [rdi]
0x180010e30  mov     r8, r14
0x180010e33  mov     rdx, r15
0x180010e36  mov     rcx, rdi
0x180010e39  mov     rax, [rax]
0x180010e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e41  mov     esi, eax
0x180010e43  test    eax, eax
0x180010e45  jz      short loc_180010E5B
0x180010e47  mov     r8, [rdi]
0x180010e4a  mov     edx, 1
0x180010e4f  mov     rcx, rdi
0x180010e52  mov     rax, [r8+18h]
0x180010e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e5b  mov     eax, esi
0x180010e5d  mov     rsi, [rsp+58h+arg_0]
0x180010e62  add     rsp, 30h
0x180010e66  pop     r15
0x180010e68  pop     r14
0x180010e6a  pop     r13
0x180010e6c  pop     r12
0x180010e6e  pop     rdi
0x180010e6f  retn
```
