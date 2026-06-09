# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180019140`
- end: `0x18001926d`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800087fc`

## callees

- `0x1800018a0`
- `0x180019140`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  _DWORD *v5; // rbx
  unsigned int v6; // r14d
  _DWORD *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = operator new(0xB0u);
    v5[6] = 0;
    *((_QWORD *)v5 + 1) = 0;
    *((_QWORD *)v5 + 2) = 0;
    *((_QWORD *)v5 + 4) = 0;
    *((_QWORD *)v5 + 5) = 0;
    *((_QWORD *)v5 + 6) = 0;
    *((_QWORD *)v5 + 7) = 0;
    *((_QWORD *)v5 + 8) = 0;
    *((_QWORD *)v5 + 9) = 0;
    *((_OWORD *)v5 + 5) = 0;
    *((_QWORD *)v5 + 12) = 0;
    *((_QWORD *)v5 + 13) = 7;
    *((_WORD *)v5 + 40) = 0;
    *((_OWORD *)v5 + 7) = 0;
    *((_QWORD *)v5 + 16) = 0;
    *((_QWORD *)v5 + 17) = 7;
    *((_WORD *)v5 + 56) = 0;
    *((_BYTE *)v5 + 144) = 0;
    *((_BYTE *)v5 + 152) = 0;
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable';
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
    v6 = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))v5)(v5, &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33, v3);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v5 + 136LL))(v5, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180019140  mov     rax, rsp
0x180019143  mov     [rax+20h], rbx
0x180019147  mov     [rax+18h], r8
0x18001914b  mov     [rax+10h], rdx
0x18001914f  mov     [rax+8], rcx
0x180019153  push    rsi
0x180019154  push    rdi
0x180019155  push    r14
0x180019157  sub     rsp, 20h
0x18001915b  mov     rsi, r8
0x18001915e  xor     edi, edi
0x180019160  test    r8, r8
0x180019163  jnz     short loc_18001916F
0x180019165  mov     eax, 80004003h
0x18001916a  jmp     loc_18001925F
0x18001916f  mov     [r8], rdi
0x180019172  mov     r14d, 8007000Eh
0x180019178  mov     [rsp+38h+arg_8], r14d
0x18001917d  mov     [rsp+38h+arg_0], rdi
0x180019182  mov     ecx, 0B0h; Size
0x180019187  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001918c  mov     rbx, rax
0x18001918f  mov     [rax+18h], edi
0x180019192  mov     [rax+8], rdi
0x180019196  mov     [rax+10h], rdi
0x18001919a  mov     [rax+20h], rdi
0x18001919e  mov     [rax+28h], rdi
0x1800191a2  mov     [rax+30h], rdi
0x1800191a6  mov     [rax+38h], rdi
0x1800191aa  mov     [rax+40h], rdi
0x1800191ae  mov     [rax+48h], rdi
0x1800191b2  xorps   xmm0, xmm0
0x1800191b5  movups  xmmword ptr [rax+50h], xmm0
0x1800191b9  mov     [rax+60h], rdi
0x1800191bd  mov     eax, 7
0x1800191c2  mov     [rbx+68h], rax
0x1800191c6  mov     [rbx+50h], di
0x1800191ca  movups  xmmword ptr [rbx+70h], xmm0
0x1800191ce  mov     [rbx+80h], rdi
0x1800191d5  mov     [rbx+88h], rax
0x1800191dc  mov     [rbx+70h], di
0x1800191e0  mov     [rbx+90h], dil
0x1800191e7  mov     [rbx+98h], dil
0x1800191ee  lea     rax, ??_7?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable'
0x1800191f5  mov     [rbx], rax
0x1800191f8  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800191ff  mov     rax, [rcx]
0x180019202  mov     rax, [rax+8]
0x180019206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001920b  mov     [rsp+38h+arg_0], rbx
0x180019210  jmp     short loc_180019221
0x180019212  mov     rsi, [rsp+38h+arg_10]
0x180019217  mov     r14d, [rsp+38h+arg_8]
0x18001921c  mov     rbx, [rsp+38h+arg_0]
0x180019221  test    rbx, rbx
0x180019224  jz      short loc_18001925C
0x180019226  mov     rax, [rbx]
0x180019229  mov     r8, rsi
0x18001922c  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180019233  mov     rcx, rbx
0x180019236  mov     rax, [rax]
0x180019239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001923e  mov     r14d, eax
0x180019241  test    eax, eax
0x180019243  jz      short loc_18001925C
0x180019245  mov     rdx, [rbx]
0x180019248  mov     rax, [rdx+88h]
0x18001924f  mov     edx, 1
0x180019254  mov     rcx, rbx
0x180019257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001925c  mov     eax, r14d
0x18001925f  mov     rbx, [rsp+38h+arg_18]
0x180019264  add     rsp, 20h
0x180019268  pop     r14
0x18001926a  pop     rdi
0x18001926b  pop     rsi
0x18001926c  retn
```
