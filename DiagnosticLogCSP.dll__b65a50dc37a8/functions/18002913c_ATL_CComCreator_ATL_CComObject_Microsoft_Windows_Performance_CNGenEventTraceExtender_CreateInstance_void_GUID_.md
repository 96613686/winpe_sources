# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18002913c`
- end: `0x18002920f`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001abb0`

## callees

- `0x180001bb4`
- `0x180027db4`
- `0x18002913c`
- `0x180039010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v5; // rbx
  unsigned int v6; // esi
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = (Microsoft::Windows::Performance::CNGenEventTraceExtender *)operator new(0xB8u);
    Microsoft::Windows::Performance::CNGenEventTraceExtender::CNGenEventTraceExtender(v5);
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable';
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
    v6 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CNGenEventTraceExtender *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CNGenEventTraceExtender *, __int64))(*(_QWORD *)v5 + 136LL))(
        v5,
        1);
  }
  return v6;
}

```

## disassembly

```asm
0x18002913c  mov     [rsp+arg_10], r8
0x180029141  mov     [rsp+arg_8], rdx
0x180029146  mov     [rsp+arg_0], rcx
0x18002914b  push    rbx
0x18002914c  push    rsi
0x18002914d  push    rdi
0x18002914e  sub     rsp, 20h
0x180029152  mov     rdi, r8
0x180029155  test    r8, r8
0x180029158  jnz     short loc_180029164
0x18002915a  mov     eax, 80004003h
0x18002915f  jmp     loc_180029206
0x180029164  mov     qword ptr [r8], 0
0x18002916b  mov     esi, 8007000Eh
0x180029170  mov     dword ptr [rsp+38h+arg_8], esi
0x180029174  mov     [rsp+38h+arg_0], 0
0x18002917d  mov     ecx, 0B8h; Size
0x180029182  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029187  mov     rbx, rax
0x18002918a  mov     [rsp+38h+arg_18], rax
0x18002918f  mov     rcx, rax; this
0x180029192  call    ??0CNGenEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CNGenEventTraceExtender::CNGenEventTraceExtender(void)
0x180029197  lea     rax, ??_7?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable'
0x18002919e  mov     [rbx], rax
0x1800291a1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800291a8  mov     rax, [rcx]
0x1800291ab  mov     rax, [rax+8]
0x1800291af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291b4  nop
0x1800291b5  mov     [rsp+38h+arg_0], rbx
0x1800291ba  jmp     short loc_1800291CA
0x1800291bc  mov     rdi, [rsp+38h+arg_10]
0x1800291c1  mov     esi, dword ptr [rsp+38h+arg_8]
0x1800291c5  mov     rbx, [rsp+38h+arg_0]
0x1800291ca  test    rbx, rbx
0x1800291cd  jz      short loc_180029204
0x1800291cf  mov     rax, [rbx]
0x1800291d2  mov     r8, rdi
0x1800291d5  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x1800291dc  mov     rcx, rbx
0x1800291df  mov     rax, [rax]
0x1800291e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291e7  mov     esi, eax
0x1800291e9  test    eax, eax
0x1800291eb  jz      short loc_180029204
0x1800291ed  mov     rdx, [rbx]
0x1800291f0  mov     rax, [rdx+88h]
0x1800291f7  mov     edx, 1
0x1800291fc  mov     rcx, rbx
0x1800291ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029204  mov     eax, esi
0x180029206  add     rsp, 20h
0x18002920a  pop     rdi
0x18002920b  pop     rsi
0x18002920c  pop     rbx
0x18002920d  retn
```
