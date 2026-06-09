# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180023844`
- end: `0x180023917`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001abb0`

## callees

- `0x180001bb4`
- `0x18001f32c`
- `0x180023844`
- `0x180039010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v5; // rbx
  unsigned int v6; // esi
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)operator new(0x1A8u);
    Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(v5);
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v7 = v5;
  }
  catch ( ... )
  {
    v3 = a3;
    v6 = -2147024882;
    v5 = v7;
  }
  if ( v5 )
  {
    v6 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CImageIdEventTraceExtender *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CImageIdEventTraceExtender *, __int64))(*(_QWORD *)v5 + 136LL))(
        v5,
        1);
  }
  return v6;
}

```

## disassembly

```asm
0x180023844  mov     [rsp+arg_10], r8
0x180023849  mov     [rsp+arg_8], rdx
0x18002384e  mov     [rsp+arg_0], rcx
0x180023853  push    rbx
0x180023854  push    rsi
0x180023855  push    rdi
0x180023856  sub     rsp, 20h
0x18002385a  mov     rdi, r8
0x18002385d  test    r8, r8
0x180023860  jnz     short loc_18002386C
0x180023862  mov     eax, 80004003h
0x180023867  jmp     loc_18002390E
0x18002386c  mov     qword ptr [r8], 0
0x180023873  mov     esi, 8007000Eh
0x180023878  mov     dword ptr [rsp+38h+arg_8], esi
0x18002387c  mov     [rsp+38h+arg_0], 0
0x180023885  mov     ecx, 1A8h; Size
0x18002388a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002388f  mov     rbx, rax
0x180023892  mov     [rsp+38h+arg_18], rax
0x180023897  mov     rcx, rax; this
0x18002389a  call    ??0CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(void)
0x18002389f  lea     rax, ??_7?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable'
0x1800238a6  mov     [rbx], rax
0x1800238a9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800238b0  mov     rax, [rcx]
0x1800238b3  mov     rax, [rax+8]
0x1800238b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238bc  nop
0x1800238bd  mov     [rsp+38h+arg_0], rbx
0x1800238c2  jmp     short loc_1800238D2
0x1800238c4  mov     rdi, [rsp+38h+arg_10]
0x1800238c9  mov     esi, dword ptr [rsp+38h+arg_8]
0x1800238cd  mov     rbx, [rsp+38h+arg_0]
0x1800238d2  test    rbx, rbx
0x1800238d5  jz      short loc_18002390C
0x1800238d7  mov     rax, [rbx]
0x1800238da  mov     r8, rdi
0x1800238dd  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x1800238e4  mov     rcx, rbx
0x1800238e7  mov     rax, [rax]
0x1800238ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238ef  mov     esi, eax
0x1800238f1  test    eax, eax
0x1800238f3  jz      short loc_18002390C
0x1800238f5  mov     rdx, [rbx]
0x1800238f8  mov     rax, [rdx+88h]
0x1800238ff  mov     edx, 1
0x180023904  mov     rcx, rbx
0x180023907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002390c  mov     eax, esi
0x18002390e  add     rsp, 20h
0x180023912  pop     rdi
0x180023913  pop     rsi
0x180023914  pop     rbx
0x180023915  retn
```
