# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18001713c`
- end: `0x18001720e`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800087fc`

## callees

- `0x1800018a0`
- `0x180015e40`
- `0x18001713c`
- `0x18002a010`

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
0x18001713c  mov     [rsp+arg_10], r8
0x180017141  mov     [rsp+arg_8], rdx
0x180017146  mov     [rsp+arg_0], rcx
0x18001714b  push    rbx
0x18001714c  push    rsi
0x18001714d  push    rdi
0x18001714e  sub     rsp, 20h
0x180017152  mov     rdi, r8
0x180017155  test    r8, r8
0x180017158  jnz     short loc_180017164
0x18001715a  mov     eax, 80004003h
0x18001715f  jmp     loc_180017206
0x180017164  mov     qword ptr [r8], 0
0x18001716b  mov     esi, 8007000Eh
0x180017170  mov     dword ptr [rsp+38h+arg_8], esi
0x180017174  mov     [rsp+38h+arg_0], 0
0x18001717d  mov     ecx, 0B8h; Size
0x180017182  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017187  mov     rbx, rax
0x18001718a  mov     [rsp+38h+arg_18], rax
0x18001718f  mov     rcx, rax; this
0x180017192  call    ??0CNGenEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CNGenEventTraceExtender::CNGenEventTraceExtender(void)
0x180017197  lea     rax, ??_7?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable'
0x18001719e  mov     [rbx], rax
0x1800171a1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800171a8  mov     rax, [rcx]
0x1800171ab  mov     rax, [rax+8]
0x1800171af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171b4  nop
0x1800171b5  mov     [rsp+38h+arg_0], rbx
0x1800171ba  jmp     short loc_1800171CA
0x1800171bc  mov     rdi, [rsp+38h+arg_10]
0x1800171c1  mov     esi, dword ptr [rsp+38h+arg_8]
0x1800171c5  mov     rbx, [rsp+38h+arg_0]
0x1800171ca  test    rbx, rbx
0x1800171cd  jz      short loc_180017204
0x1800171cf  mov     rax, [rbx]
0x1800171d2  mov     r8, rdi
0x1800171d5  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x1800171dc  mov     rcx, rbx
0x1800171df  mov     rax, [rax]
0x1800171e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171e7  mov     esi, eax
0x1800171e9  test    eax, eax
0x1800171eb  jz      short loc_180017204
0x1800171ed  mov     rdx, [rbx]
0x1800171f0  mov     rax, [rdx+88h]
0x1800171f7  mov     edx, 1
0x1800171fc  mov     rcx, rbx
0x1800171ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017204  mov     eax, esi
0x180017206  add     rsp, 20h
0x18001720a  pop     rdi
0x18001720b  pop     rsi
0x18001720c  pop     rbx
0x18001720d  retn
```
