# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000b6c8`
- end: `0x18000b7aa`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `226`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800087fc`

## callees

- `0x1800018a0`
- `0x18000b6c8`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // r14d
  _DWORD *v6; // rdi

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v5 = -2147024882;
  v6 = operator new(0x20u);
  v6[6] = 0;
  *((_QWORD *)v6 + 1) = 0;
  *((_QWORD *)v6 + 2) = 0;
  *(_QWORD *)v6 = &ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  if ( v6 )
  {
    v5 = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))v6)(v6, &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33, a3);
    if ( v5 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v6 + 136LL))(v6, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x18000b6c8  mov     [rsp+arg_10], r8
0x18000b6cd  mov     [rsp+arg_8], rdx
0x18000b6d2  mov     [rsp+arg_0], rcx
0x18000b6d7  push    rsi
0x18000b6d8  push    rdi
0x18000b6d9  push    r14
0x18000b6db  sub     rsp, 20h
0x18000b6df  mov     rsi, r8
0x18000b6e2  test    r8, r8
0x18000b6e5  jnz     short loc_18000B6F1
0x18000b6e7  mov     eax, 80004003h
0x18000b6ec  jmp     loc_18000B7A1
0x18000b6f1  mov     qword ptr [r8], 0
0x18000b6f8  mov     r14d, 8007000Eh
0x18000b6fe  mov     dword ptr [rsp+38h+arg_8], r14d
0x18000b703  mov     [rsp+38h+arg_0], 0
0x18000b70c  mov     ecx, 20h ; ' '; Size
0x18000b711  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b716  mov     rdi, rax
0x18000b719  mov     dword ptr [rax+18h], 0
0x18000b720  mov     qword ptr [rax+8], 0
0x18000b728  mov     qword ptr [rax+10h], 0
0x18000b730  lea     rax, ??_7?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable'
0x18000b737  mov     [rdi], rax
0x18000b73a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b741  mov     rax, [rcx]
0x18000b744  mov     rax, [rax+8]
0x18000b748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b74d  mov     [rsp+38h+arg_0], rdi
0x18000b752  jmp     short loc_18000B763
0x18000b754  mov     rsi, [rsp+38h+arg_10]
0x18000b759  mov     r14d, dword ptr [rsp+38h+arg_8]
0x18000b75e  mov     rdi, [rsp+38h+arg_0]
0x18000b763  test    rdi, rdi
0x18000b766  jz      short loc_18000B79E
0x18000b768  mov     rax, [rdi]
0x18000b76b  mov     r8, rsi
0x18000b76e  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18000b775  mov     rcx, rdi
0x18000b778  mov     rax, [rax]
0x18000b77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b780  mov     r14d, eax
0x18000b783  test    eax, eax
0x18000b785  jz      short loc_18000B79E
0x18000b787  mov     rdx, [rdi]
0x18000b78a  mov     rax, [rdx+88h]
0x18000b791  mov     edx, 1
0x18000b796  mov     rcx, rdi
0x18000b799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b79e  mov     eax, r14d
0x18000b7a1  add     rsp, 20h
0x18000b7a5  pop     r14
0x18000b7a7  pop     rdi
0x18000b7a8  pop     rsi
0x18000b7a9  retn
```
