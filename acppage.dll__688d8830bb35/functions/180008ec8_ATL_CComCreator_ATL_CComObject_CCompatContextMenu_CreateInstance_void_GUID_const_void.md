# ATL::CComCreator<ATL::CComObject<CCompatContextMenu>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180008ec8`
- end: `0x180008fd1`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCCompatContextMenu@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008ea0`

## callees

- `0x18000179c`
- `0x180005670`
- `0x180008ec8`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CCompatContextMenu>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  char *v7; // rax
  _BYTE *v8; // rbx
  struct ATL::CAtlModule *v9; // rcx
  int v10; // ecx
  int v11; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (char *)operator new(0x270u);
  v8 = v7;
  if ( v7 )
  {
    v9 = ATL::_pAtlModule;
    *((_DWORD *)v7 + 8) = 0;
    *(_OWORD *)(v7 + 40) = 0;
    *(_OWORD *)(v7 + 56) = 0;
    *((_QWORD *)v7 + 9) = 0;
    v7[80] = 0;
    *((_QWORD *)v7 + 76) = 0;
    *((_WORD *)v7 + 44) = 0;
    *((_QWORD *)v7 + 77) = 0;
    *(_QWORD *)v7 = &ATL::CComObject<CCompatContextMenu>::`vftable'{for `ICompatContextMenu'};
    *((_QWORD *)v7 + 1) = &ATL::CComObject<CCompatContextMenu>::`vftable'{for `IShellExtInit'};
    *((_QWORD *)v7 + 2) = &ATL::CComObject<CCompatContextMenu>::`vftable'{for `IContextMenu'};
    *((_QWORD *)v7 + 3) = &ATL::CComObject<CCompatContextMenu>::`vftable'{for `IObjectWithSite'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 40));
    if ( v10 >= 0 )
      v8[80] = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v8 + 24LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180008ec8  push    rbx
0x180008eca  push    rbp
0x180008ecb  push    rsi
0x180008ecc  push    rdi
0x180008ecd  sub     rsp, 28h
0x180008ed1  mov     rsi, r8
0x180008ed4  mov     rbp, rdx
0x180008ed7  test    r8, r8
0x180008eda  jnz     short loc_180008EE6
0x180008edc  mov     eax, 80004003h
0x180008ee1  jmp     loc_180008FC8
0x180008ee6  mov     ecx, 270h; Size
0x180008eeb  mov     qword ptr [r8], 0
0x180008ef2  mov     edi, 8007000Eh
0x180008ef7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008efc  mov     rbx, rax
0x180008eff  test    rax, rax
0x180008f02  jz      loc_180008FC6
0x180008f08  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008f0f  xorps   xmm0, xmm0
0x180008f12  mov     dword ptr [rax+20h], 0
0x180008f19  xor     eax, eax
0x180008f1b  movups  xmmword ptr [rbx+28h], xmm0
0x180008f1f  movups  xmmword ptr [rbx+38h], xmm0
0x180008f23  mov     [rbx+48h], rax
0x180008f27  mov     [rbx+50h], al
0x180008f2a  mov     [rbx+260h], rax
0x180008f31  mov     [rbx+58h], ax
0x180008f35  mov     [rbx+268h], rax
0x180008f3c  lea     rax, ??_7?$CComObject@VCCompatContextMenu@@@ATL@@6BICompatContextMenu@@@; const ATL::CComObject<CCompatContextMenu>::`vftable'{for `ICompatContextMenu'}
0x180008f43  mov     [rbx], rax
0x180008f46  lea     rax, ??_7?$CComObject@VCCompatContextMenu@@@ATL@@6BIShellExtInit@@@; const ATL::CComObject<CCompatContextMenu>::`vftable'{for `IShellExtInit'}
0x180008f4d  mov     [rbx+8], rax
0x180008f51  lea     rax, ??_7?$CComObject@VCCompatContextMenu@@@ATL@@6BIContextMenu@@@; const ATL::CComObject<CCompatContextMenu>::`vftable'{for `IContextMenu'}
0x180008f58  mov     [rbx+10h], rax
0x180008f5c  lea     rax, ??_7?$CComObject@VCCompatContextMenu@@@ATL@@6BIObjectWithSite@@@; const ATL::CComObject<CCompatContextMenu>::`vftable'{for `IObjectWithSite'}
0x180008f63  mov     [rbx+18h], rax
0x180008f67  mov     rax, [rcx]
0x180008f6a  mov     rax, [rax+8]
0x180008f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f73  lea     rcx, [rbx+28h]; this
0x180008f77  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180008f7c  mov     ecx, eax
0x180008f7e  test    eax, eax
0x180008f80  js      short loc_180008F86
0x180008f82  mov     byte ptr [rbx+50h], 1
0x180008f86  xor     eax, eax
0x180008f88  test    ecx, ecx
0x180008f8a  cmovs   eax, ecx
0x180008f8d  xor     edi, edi
0x180008f8f  test    eax, eax
0x180008f91  cmovs   edi, eax
0x180008f94  test    edi, edi
0x180008f96  jnz     short loc_180008FB2
0x180008f98  mov     rax, [rbx]
0x180008f9b  mov     r8, rsi
0x180008f9e  mov     rdx, rbp
0x180008fa1  mov     rcx, rbx
0x180008fa4  mov     rax, [rax]
0x180008fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fac  mov     edi, eax
0x180008fae  test    eax, eax
0x180008fb0  jz      short loc_180008FC6
0x180008fb2  mov     rcx, [rbx]
0x180008fb5  mov     edx, 1
0x180008fba  mov     rax, [rcx+18h]
0x180008fbe  mov     rcx, rbx
0x180008fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fc6  mov     eax, edi
0x180008fc8  add     rsp, 28h
0x180008fcc  pop     rdi
0x180008fcd  pop     rsi
0x180008fce  pop     rbp
0x180008fcf  pop     rbx
0x180008fd0  retn
```
