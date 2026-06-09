# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180029f44`
- end: `0x18002a071`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019ccc`

## callees

- `0x180001b84`
- `0x180029f44`
- `0x180037010`

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
0x180029f44  mov     rax, rsp
0x180029f47  mov     [rax+20h], rbx
0x180029f4b  mov     [rax+18h], r8
0x180029f4f  mov     [rax+10h], rdx
0x180029f53  mov     [rax+8], rcx
0x180029f57  push    rsi
0x180029f58  push    rdi
0x180029f59  push    r14
0x180029f5b  sub     rsp, 20h
0x180029f5f  mov     rsi, r8
0x180029f62  xor     edi, edi
0x180029f64  test    r8, r8
0x180029f67  jnz     short loc_180029F73
0x180029f69  mov     eax, 80004003h
0x180029f6e  jmp     loc_18002A063
0x180029f73  mov     [r8], rdi
0x180029f76  mov     r14d, 8007000Eh
0x180029f7c  mov     [rsp+38h+arg_8], r14d
0x180029f81  mov     [rsp+38h+arg_0], rdi
0x180029f86  mov     ecx, 0B0h; Size
0x180029f8b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029f90  mov     rbx, rax
0x180029f93  mov     [rax+18h], edi
0x180029f96  mov     [rax+8], rdi
0x180029f9a  mov     [rax+10h], rdi
0x180029f9e  mov     [rax+20h], rdi
0x180029fa2  mov     [rax+28h], rdi
0x180029fa6  mov     [rax+30h], rdi
0x180029faa  mov     [rax+38h], rdi
0x180029fae  mov     [rax+40h], rdi
0x180029fb2  mov     [rax+48h], rdi
0x180029fb6  xorps   xmm0, xmm0
0x180029fb9  movups  xmmword ptr [rax+50h], xmm0
0x180029fbd  mov     [rax+60h], rdi
0x180029fc1  mov     eax, 7
0x180029fc6  mov     [rbx+68h], rax
0x180029fca  mov     [rbx+50h], di
0x180029fce  movups  xmmword ptr [rbx+70h], xmm0
0x180029fd2  mov     [rbx+80h], rdi
0x180029fd9  mov     [rbx+88h], rax
0x180029fe0  mov     [rbx+70h], di
0x180029fe4  mov     [rbx+90h], dil
0x180029feb  mov     [rbx+98h], dil
0x180029ff2  lea     rax, ??_7?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable'
0x180029ff9  mov     [rbx], rax
0x180029ffc  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002a003  mov     rax, [rcx]
0x18002a006  mov     rax, [rax+8]
0x18002a00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a00f  mov     [rsp+38h+arg_0], rbx
0x18002a014  jmp     short loc_18002A025
0x18002a016  mov     rsi, [rsp+38h+arg_10]
0x18002a01b  mov     r14d, [rsp+38h+arg_8]
0x18002a020  mov     rbx, [rsp+38h+arg_0]
0x18002a025  test    rbx, rbx
0x18002a028  jz      short loc_18002A060
0x18002a02a  mov     rax, [rbx]
0x18002a02d  mov     r8, rsi
0x18002a030  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18002a037  mov     rcx, rbx
0x18002a03a  mov     rax, [rax]
0x18002a03d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a042  mov     r14d, eax
0x18002a045  test    eax, eax
0x18002a047  jz      short loc_18002A060
0x18002a049  mov     rdx, [rbx]
0x18002a04c  mov     rax, [rdx+88h]
0x18002a053  mov     edx, 1
0x18002a058  mov     rcx, rbx
0x18002a05b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a060  mov     eax, r14d
0x18002a063  mov     rbx, [rsp+38h+arg_18]
0x18002a068  add     rsp, 20h
0x18002a06c  pop     r14
0x18002a06e  pop     rdi
0x18002a06f  pop     rsi
0x18002a070  retn
```
