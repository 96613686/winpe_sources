# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<MetadataPackageSource>>,ATL::CComCreator<ATL::CComAggObject<MetadataPackageSource>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180011540`
- end: `0x180011623`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VMetadataPackageSource@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VMetadataPackageSource@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `227`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000152c`
- `0x180003fc0`
- `0x180011288`
- `0x180011540`
- `0x18001162c`
- `0x1800119c0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<MetadataPackageSource>>,ATL::CComCreator<ATL::CComAggObject<MetadataPackageSource>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // ebx
  MetadataPackageSource *v6; // rax
  MetadataPackageSource *v7; // rdi
  struct ATL::CAtlModule *v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8

  if ( a1 )
  {
    return (unsigned int)ATL::CComCreator<ATL::CComAggObject<MetadataPackageSource>>::CreateInstance();
  }
  else if ( a3 )
  {
    *a3 = 0;
    v5 = -2147024882;
    v6 = (MetadataPackageSource *)operator new(0xD8u);
    v7 = v6;
    if ( v6 )
    {
      MetadataPackageSource::MetadataPackageSource(v6);
      v8 = ATL::_pAtlModule;
      *(_QWORD *)v7 = &ATL::CComObject<MetadataPackageSource>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v8 + 8LL))(v8);
      v9 = ATL::CComCriticalSection::Init((MetadataPackageSource *)((char *)v7 + 16));
      if ( v9 >= 0 )
      {
        *((_BYTE *)v7 + 56) = 1;
        v9 = DMrcInit(v11, v10, v12);
        if ( v9 )
        {
          if ( v9 > 0 )
            v9 = (unsigned __int16)v9 | 0x80070000;
        }
        else
        {
          v9 = 0;
        }
      }
      v5 = 0;
      if ( v9 < 0 )
        v5 = v9;
      if ( v5 || (v5 = (**(__int64 (__fastcall ***)(MetadataPackageSource *, __int64, _QWORD *))v7)(v7, a2, a3)) != 0 )
        (*(void (__fastcall **)(MetadataPackageSource *, __int64))(*(_QWORD *)v7 + 88LL))(v7, 1);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v5;
}

```

## disassembly

```asm
0x180011540  push    rbx
0x180011542  push    rbp
0x180011543  push    rsi
0x180011544  push    rdi
0x180011545  sub     rsp, 28h
0x180011549  mov     rsi, r8
0x18001154c  mov     rbp, rdx
0x18001154f  test    rcx, rcx
0x180011552  jnz     loc_180011611
0x180011558  test    r8, r8
0x18001155b  jnz     short loc_180011567
0x18001155d  mov     ebx, 80004003h
0x180011562  jmp     loc_180011618
0x180011567  mov     ecx, 0D8h; Size
0x18001156c  mov     qword ptr [r8], 0
0x180011573  mov     ebx, 8007000Eh
0x180011578  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001157d  mov     rdi, rax
0x180011580  test    rax, rax
0x180011583  jz      loc_180011618
0x180011589  mov     rcx, rax; this
0x18001158c  call    ??0MetadataPackageSource@@QEAA@XZ; MetadataPackageSource::MetadataPackageSource(void)
0x180011591  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011598  lea     rax, ??_7?$CComObject@VMetadataPackageSource@@@ATL@@6B@; const ATL::CComObject<MetadataPackageSource>::`vftable'
0x18001159f  mov     [rdi], rax
0x1800115a2  mov     rax, [rcx]
0x1800115a5  mov     rax, [rax+8]
0x1800115a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115ae  lea     rcx, [rdi+10h]; this
0x1800115b2  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800115b7  test    eax, eax
0x1800115b9  js      short loc_1800115D6
0x1800115bb  mov     byte ptr [rdi+38h], 1
0x1800115bf  call    ?DMrcInit@@YAKXZ; DMrcInit(void)
0x1800115c4  test    eax, eax
0x1800115c6  jz      short loc_1800115D4
0x1800115c8  jle     short loc_1800115D6
0x1800115ca  movzx   eax, ax
0x1800115cd  or      eax, 80070000h
0x1800115d2  jmp     short loc_1800115D6
0x1800115d4  xor     eax, eax
0x1800115d6  xor     ebx, ebx
0x1800115d8  test    eax, eax
0x1800115da  cmovs   ebx, eax
0x1800115dd  test    ebx, ebx
0x1800115df  jnz     short loc_1800115FB
0x1800115e1  mov     rax, [rdi]
0x1800115e4  mov     r8, rsi
0x1800115e7  mov     rdx, rbp
0x1800115ea  mov     rcx, rdi
0x1800115ed  mov     rax, [rax]
0x1800115f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115f5  mov     ebx, eax
0x1800115f7  test    eax, eax
0x1800115f9  jz      short loc_180011618
0x1800115fb  mov     rax, [rdi]
0x1800115fe  mov     edx, 1
0x180011603  mov     rcx, rdi
0x180011606  mov     rax, [rax+58h]
0x18001160a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001160f  jmp     short loc_180011618
0x180011611  call    ?CreateInstance@?$CComCreator@V?$CComAggObject@VMetadataPackageSource@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<MetadataPackageSource>>::CreateInstance(void *,_GUID const &,void * *)
0x180011616  mov     ebx, eax
0x180011618  mov     eax, ebx
0x18001161a  add     rsp, 28h
0x18001161e  pop     rdi
0x18001161f  pop     rsi
0x180011620  pop     rbp
0x180011621  pop     rbx
0x180011622  retn
```
