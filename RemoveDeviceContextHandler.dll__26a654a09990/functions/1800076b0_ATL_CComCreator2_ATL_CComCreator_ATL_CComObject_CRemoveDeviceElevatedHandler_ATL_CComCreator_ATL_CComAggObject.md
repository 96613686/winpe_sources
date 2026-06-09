# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRemoveDeviceElevatedHandler>>,ATL::CComCreator<ATL::CComAggObject<CRemoveDeviceElevatedHandler>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800076b0`
- end: `0x1800077ed`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCRemoveDeviceElevatedHandler@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCRemoveDeviceElevatedHandler@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c04`
- `0x1800076b0`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRemoveDeviceElevatedHandler>>,ATL::CComCreator<ATL::CComAggObject<CRemoveDeviceElevatedHandler>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // ebx
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  struct ATL::CAtlModule *v9; // rcx
  int v10; // ecx
  _DWORD *v11; // rax
  _DWORD *v12; // rdi
  struct ATL::CAtlModule *v13; // rcx

  if ( !a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      v6 = -2147024882;
      v7 = operator new(0x10u);
      v8 = v7;
      if ( v7 )
      {
        v9 = ATL::_pAtlModule;
        v7[2] = 0;
        *(_QWORD *)v7 = &ATL::CComObject<CRemoveDeviceElevatedHandler>::`vftable';
        (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
        v10 = v8[2];
        if ( v10 != 0x7FFFFFFF )
        {
          v8[2] = v10 + 1;
          if ( v10 != 2147483646 )
            v8[2] = v10;
        }
        v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, a2, a3);
        if ( v6 )
          (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 32LL))(v8, 1);
      }
      return v6;
    }
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  v6 = -2147024882;
  v11 = operator new(0x20u);
  v12 = v11;
  if ( v11 )
  {
    v13 = ATL::_pAtlModule;
    v11[2] = 0;
    *(_QWORD *)v11 = &ATL::CComAggObject<CRemoveDeviceElevatedHandler>::`vftable';
    *((_QWORD *)v11 + 2) = &ATL::CComContainedObject<CRemoveDeviceElevatedHandler>::`vftable';
    *((_QWORD *)v11 + 3) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v13 + 8LL))(v13);
    v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v12)(v12, a2, a3);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v12 + 24LL))(v12, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x1800076b0  push    rbx
0x1800076b2  push    rbp
0x1800076b3  push    rsi
0x1800076b4  push    rdi
0x1800076b5  push    r14
0x1800076b7  sub     rsp, 20h
0x1800076bb  mov     rsi, r8
0x1800076be  mov     r14, rdx
0x1800076c1  mov     rbp, rcx
0x1800076c4  test    rcx, rcx
0x1800076c7  jnz     loc_180007755
0x1800076cd  test    r8, r8
0x1800076d0  jz      loc_18000775A
0x1800076d6  mov     [r8], rcx
0x1800076d9  mov     ebx, 8007000Eh
0x1800076de  lea     ecx, [rbp+10h]; Size
0x1800076e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800076e6  mov     rdi, rax
0x1800076e9  test    rax, rax
0x1800076ec  jz      loc_1800077E0
0x1800076f2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800076f9  mov     [rax+8], ebp
0x1800076fc  lea     rax, ??_7?$CComObject@VCRemoveDeviceElevatedHandler@@@ATL@@6B@; const ATL::CComObject<CRemoveDeviceElevatedHandler>::`vftable'
0x180007703  mov     [rdi], rax
0x180007706  mov     rdx, [rcx]
0x180007709  mov     rax, [rdx+8]
0x18000770d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007712  mov     ecx, [rdi+8]
0x180007715  cmp     ecx, 7FFFFFFFh
0x18000771b  jz      short loc_18000772E
0x18000771d  lea     eax, [rcx+1]
0x180007720  mov     [rdi+8], eax
0x180007723  cmp     ecx, 7FFFFFFEh
0x180007729  jz      short loc_18000772E
0x18000772b  mov     [rdi+8], ecx
0x18000772e  mov     rax, [rdi]
0x180007731  mov     r8, rsi
0x180007734  mov     rdx, r14
0x180007737  mov     rcx, rdi
0x18000773a  mov     rax, [rax]
0x18000773d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007742  mov     ebx, eax
0x180007744  test    eax, eax
0x180007746  jz      loc_1800077E0
0x18000774c  mov     rcx, [rdi]
0x18000774f  mov     rax, [rcx+20h]
0x180007753  jmp     short loc_1800077D3
0x180007755  test    rsi, rsi
0x180007758  jnz     short loc_180007761
0x18000775a  mov     ebx, 80004003h
0x18000775f  jmp     short loc_1800077E0
0x180007761  mov     ecx, 20h ; ' '; Size
0x180007766  mov     qword ptr [r8], 0
0x18000776d  mov     ebx, 8007000Eh
0x180007772  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007777  mov     rdi, rax
0x18000777a  test    rax, rax
0x18000777d  jz      short loc_1800077E0
0x18000777f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007786  mov     dword ptr [rax+8], 0
0x18000778d  lea     rax, ??_7?$CComAggObject@VCRemoveDeviceElevatedHandler@@@ATL@@6B@; const ATL::CComAggObject<CRemoveDeviceElevatedHandler>::`vftable'
0x180007794  mov     [rdi], rax
0x180007797  lea     rax, ??_7?$CComContainedObject@VCRemoveDeviceElevatedHandler@@@ATL@@6B@; const ATL::CComContainedObject<CRemoveDeviceElevatedHandler>::`vftable'
0x18000779e  mov     [rdi+10h], rax
0x1800077a2  mov     [rdi+18h], rbp
0x1800077a6  mov     rdx, [rcx]
0x1800077a9  mov     rax, [rdx+8]
0x1800077ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077b2  mov     rax, [rdi]
0x1800077b5  mov     r8, rsi
0x1800077b8  mov     rdx, r14
0x1800077bb  mov     rcx, rdi
0x1800077be  mov     rax, [rax]
0x1800077c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077c6  mov     ebx, eax
0x1800077c8  test    eax, eax
0x1800077ca  jz      short loc_1800077E0
0x1800077cc  mov     rax, [rdi]
0x1800077cf  mov     rax, [rax+18h]
0x1800077d3  mov     edx, 1
0x1800077d8  mov     rcx, rdi
0x1800077db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077e0  mov     eax, ebx
0x1800077e2  add     rsp, 20h
0x1800077e6  pop     r14
0x1800077e8  pop     rdi
0x1800077e9  pop     rsi
0x1800077ea  pop     rbp
0x1800077eb  pop     rbx
0x1800077ec  retn
```
