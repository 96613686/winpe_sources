# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800228a4`
- end: `0x180022976`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019ccc`

## callees

- `0x180001b84`
- `0x18001e388`
- `0x1800228a4`
- `0x180037010`

## pseudocode

```c
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
0x1800228a4  mov     [rsp+arg_10], r8
0x1800228a9  mov     [rsp+arg_8], rdx
0x1800228ae  mov     [rsp+arg_0], rcx
0x1800228b3  push    rbx
0x1800228b4  push    rsi
0x1800228b5  push    rdi
0x1800228b6  sub     rsp, 20h
0x1800228ba  mov     rdi, r8
0x1800228bd  test    r8, r8
0x1800228c0  jnz     short loc_1800228CC
0x1800228c2  mov     eax, 80004003h
0x1800228c7  jmp     loc_18002296E
0x1800228cc  mov     qword ptr [r8], 0
0x1800228d3  mov     esi, 8007000Eh
0x1800228d8  mov     dword ptr [rsp+38h+arg_8], esi
0x1800228dc  mov     [rsp+38h+arg_0], 0
0x1800228e5  mov     ecx, 1A8h; Size
0x1800228ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800228ef  mov     rbx, rax
0x1800228f2  mov     [rsp+38h+arg_18], rax
0x1800228f7  mov     rcx, rax; this
0x1800228fa  call    ??0CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(void)
0x1800228ff  lea     rax, ??_7?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable'
0x180022906  mov     [rbx], rax
0x180022909  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180022910  mov     rax, [rcx]
0x180022913  mov     rax, [rax+8]
0x180022917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002291c  nop
0x18002291d  mov     [rsp+38h+arg_0], rbx
0x180022922  jmp     short loc_180022932
0x180022924  mov     rdi, [rsp+38h+arg_10]
0x180022929  mov     esi, dword ptr [rsp+38h+arg_8]
0x18002292d  mov     rbx, [rsp+38h+arg_0]
0x180022932  test    rbx, rbx
0x180022935  jz      short loc_18002296C
0x180022937  mov     rax, [rbx]
0x18002293a  mov     r8, rdi
0x18002293d  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180022944  mov     rcx, rbx
0x180022947  mov     rax, [rax]
0x18002294a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002294f  mov     esi, eax
0x180022951  test    eax, eax
0x180022953  jz      short loc_18002296C
0x180022955  mov     rdx, [rbx]
0x180022958  mov     rax, [rdx+88h]
0x18002295f  mov     edx, 1
0x180022964  mov     rcx, rbx
0x180022967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002296c  mov     eax, esi
0x18002296e  add     rsp, 20h
0x180022972  pop     rdi
0x180022973  pop     rsi
0x180022974  pop     rbx
0x180022975  retn
```
