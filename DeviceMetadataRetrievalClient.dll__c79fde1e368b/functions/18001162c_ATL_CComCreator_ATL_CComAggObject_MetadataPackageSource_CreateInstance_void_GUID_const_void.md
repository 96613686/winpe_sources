# ATL::CComCreator<ATL::CComAggObject<MetadataPackageSource>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18001162c`
- end: `0x180011728`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VMetadataPackageSource@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `252`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180011540`

## callees

- `0x18000152c`
- `0x180003fc0`
- `0x180011288`
- `0x18001162c`
- `0x1800119c0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<MetadataPackageSource>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // ebx
  _DWORD *v8; // rax
  _DWORD *v9; // rdi
  struct ATL::CAtlModule *v10; // rcx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rcx
  int v15; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = operator new(0xF0u);
  v9 = v8;
  if ( v8 )
  {
    v8[2] = 0;
    *(_QWORD *)v8 = &ATL::CComAggObject<MetadataPackageSource>::`vftable';
    MetadataPackageSource::MetadataPackageSource((MetadataPackageSource *)(v8 + 6));
    v10 = ATL::_pAtlModule;
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<MetadataPackageSource>::`vftable';
    *((_QWORD *)v9 + 4) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v10 + 8LL))(v10);
    v11 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 10));
    v14 = (unsigned int)v11;
    if ( v11 >= 0 )
      *((_BYTE *)v9 + 80) = 1;
    v15 = 0;
    if ( (int)v14 < 0 )
      v15 = v14;
    if ( v15 >= 0 )
    {
      v15 = DMrcInit(v14, v12, v13);
      if ( v15 )
      {
        if ( v15 > 0 )
          v15 = (unsigned __int16)v15 | 0x80070000;
      }
      else
      {
        v15 = 0;
      }
    }
    v7 = 0;
    if ( v15 < 0 )
      v7 = v15;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x18001162c  push    rbx
0x18001162e  push    rbp
0x18001162f  push    rsi
0x180011630  push    rdi
0x180011631  push    r14
0x180011633  sub     rsp, 20h
0x180011637  mov     rsi, r8
0x18001163a  mov     r14, rdx
0x18001163d  mov     rbp, rcx
0x180011640  test    r8, r8
0x180011643  jnz     short loc_18001164F
0x180011645  mov     eax, 80004003h
0x18001164a  jmp     loc_18001171D
0x18001164f  mov     ecx, 0F0h; Size
0x180011654  mov     qword ptr [r8], 0
0x18001165b  mov     ebx, 8007000Eh
0x180011660  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011665  mov     rdi, rax
0x180011668  test    rax, rax
0x18001166b  jz      loc_18001171B
0x180011671  mov     dword ptr [rax+8], 0
0x180011678  lea     rcx, [rdi+18h]; this
0x18001167c  lea     rax, ??_7?$CComAggObject@VMetadataPackageSource@@@ATL@@6B@; const ATL::CComAggObject<MetadataPackageSource>::`vftable'
0x180011683  mov     [rdi], rax
0x180011686  call    ??0MetadataPackageSource@@QEAA@XZ; MetadataPackageSource::MetadataPackageSource(void)
0x18001168b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011692  lea     rax, ??_7?$CComContainedObject@VMetadataPackageSource@@@ATL@@6B@; const ATL::CComContainedObject<MetadataPackageSource>::`vftable'
0x180011699  mov     [rdi+18h], rax
0x18001169d  mov     [rdi+20h], rbp
0x1800116a1  mov     rax, [rcx]
0x1800116a4  mov     rax, [rax+8]
0x1800116a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116ad  lea     rcx, [rdi+28h]; this
0x1800116b1  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800116b6  mov     ecx, eax
0x1800116b8  test    eax, eax
0x1800116ba  js      short loc_1800116C0
0x1800116bc  mov     byte ptr [rdi+50h], 1
0x1800116c0  xor     eax, eax
0x1800116c2  test    ecx, ecx
0x1800116c4  cmovs   eax, ecx
0x1800116c7  test    eax, eax
0x1800116c9  js      short loc_1800116E2
0x1800116cb  call    ?DMrcInit@@YAKXZ; DMrcInit(void)
0x1800116d0  test    eax, eax
0x1800116d2  jz      short loc_1800116E0
0x1800116d4  jle     short loc_1800116E2
0x1800116d6  movzx   eax, ax
0x1800116d9  or      eax, 80070000h
0x1800116de  jmp     short loc_1800116E2
0x1800116e0  xor     eax, eax
0x1800116e2  xor     ebx, ebx
0x1800116e4  test    eax, eax
0x1800116e6  cmovs   ebx, eax
0x1800116e9  test    ebx, ebx
0x1800116eb  jnz     short loc_180011707
0x1800116ed  mov     rax, [rdi]
0x1800116f0  mov     r8, rsi
0x1800116f3  mov     rdx, r14
0x1800116f6  mov     rcx, rdi
0x1800116f9  mov     rax, [rax]
0x1800116fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011701  mov     ebx, eax
0x180011703  test    eax, eax
0x180011705  jz      short loc_18001171B
0x180011707  mov     rcx, [rdi]
0x18001170a  mov     edx, 1
0x18001170f  mov     rax, [rcx+18h]
0x180011713  mov     rcx, rdi
0x180011716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001171b  mov     eax, ebx
0x18001171d  add     rsp, 20h
0x180011721  pop     r14
0x180011723  pop     rdi
0x180011724  pop     rsi
0x180011725  pop     rbp
0x180011726  pop     rbx
0x180011727  retn
```
