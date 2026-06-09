# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18002b1c4`
- end: `0x18002b2f2`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001abb0`

## callees

- `0x180001bb4`
- `0x18002b1c4`
- `0x180039010`

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
0x18002b1c4  mov     rax, rsp
0x18002b1c7  mov     [rax+20h], rbx
0x18002b1cb  mov     [rax+18h], r8
0x18002b1cf  mov     [rax+10h], rdx
0x18002b1d3  mov     [rax+8], rcx
0x18002b1d7  push    rsi
0x18002b1d8  push    rdi
0x18002b1d9  push    r14
0x18002b1db  sub     rsp, 20h
0x18002b1df  mov     rsi, r8
0x18002b1e2  xor     edi, edi
0x18002b1e4  test    r8, r8
0x18002b1e7  jnz     short loc_18002B1F3
0x18002b1e9  mov     eax, 80004003h
0x18002b1ee  jmp     loc_18002B2E3
0x18002b1f3  mov     [r8], rdi
0x18002b1f6  mov     r14d, 8007000Eh
0x18002b1fc  mov     [rsp+38h+arg_8], r14d
0x18002b201  mov     [rsp+38h+arg_0], rdi
0x18002b206  mov     ecx, 0B0h; Size
0x18002b20b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b210  mov     rbx, rax
0x18002b213  mov     [rax+18h], edi
0x18002b216  mov     [rax+8], rdi
0x18002b21a  mov     [rax+10h], rdi
0x18002b21e  mov     [rax+20h], rdi
0x18002b222  mov     [rax+28h], rdi
0x18002b226  mov     [rax+30h], rdi
0x18002b22a  mov     [rax+38h], rdi
0x18002b22e  mov     [rax+40h], rdi
0x18002b232  mov     [rax+48h], rdi
0x18002b236  xorps   xmm0, xmm0
0x18002b239  movups  xmmword ptr [rax+50h], xmm0
0x18002b23d  mov     [rax+60h], rdi
0x18002b241  mov     eax, 7
0x18002b246  mov     [rbx+68h], rax
0x18002b24a  mov     [rbx+50h], di
0x18002b24e  movups  xmmword ptr [rbx+70h], xmm0
0x18002b252  mov     [rbx+80h], rdi
0x18002b259  mov     [rbx+88h], rax
0x18002b260  mov     [rbx+70h], di
0x18002b264  mov     [rbx+90h], dil
0x18002b26b  mov     [rbx+98h], dil
0x18002b272  lea     rax, ??_7?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable'
0x18002b279  mov     [rbx], rax
0x18002b27c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002b283  mov     rax, [rcx]
0x18002b286  mov     rax, [rax+8]
0x18002b28a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b28f  mov     [rsp+38h+arg_0], rbx
0x18002b294  jmp     short loc_18002B2A5
0x18002b296  mov     rsi, [rsp+38h+arg_10]
0x18002b29b  mov     r14d, [rsp+38h+arg_8]
0x18002b2a0  mov     rbx, [rsp+38h+arg_0]
0x18002b2a5  test    rbx, rbx
0x18002b2a8  jz      short loc_18002B2E0
0x18002b2aa  mov     rax, [rbx]
0x18002b2ad  mov     r8, rsi
0x18002b2b0  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18002b2b7  mov     rcx, rbx
0x18002b2ba  mov     rax, [rax]
0x18002b2bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2c2  mov     r14d, eax
0x18002b2c5  test    eax, eax
0x18002b2c7  jz      short loc_18002B2E0
0x18002b2c9  mov     rdx, [rbx]
0x18002b2cc  mov     rax, [rdx+88h]
0x18002b2d3  mov     edx, 1
0x18002b2d8  mov     rcx, rbx
0x18002b2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2e0  mov     eax, r14d
0x18002b2e3  mov     rbx, [rsp+38h+arg_18]
0x18002b2e8  add     rsp, 20h
0x18002b2ec  pop     r14
0x18002b2ee  pop     rdi
0x18002b2ef  pop     rsi
0x18002b2f0  retn
```
