# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800049c8`
- end: `0x180004aaa`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `226`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800087fc`

## callees

- `0x1800018a0`
- `0x1800049c8`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  _DWORD *v5; // rdi
  unsigned int v6; // r14d
  _DWORD *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = operator new(0x20u);
    v5[6] = 0;
    *((_QWORD *)v5 + 1) = 0;
    *((_QWORD *)v5 + 2) = 0;
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable';
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
0x1800049c8  mov     [rsp+arg_10], r8
0x1800049cd  mov     [rsp+arg_8], rdx
0x1800049d2  mov     [rsp+arg_0], rcx
0x1800049d7  push    rsi
0x1800049d8  push    rdi
0x1800049d9  push    r14
0x1800049db  sub     rsp, 20h
0x1800049df  mov     rsi, r8
0x1800049e2  test    r8, r8
0x1800049e5  jnz     short loc_1800049F1
0x1800049e7  mov     eax, 80004003h
0x1800049ec  jmp     loc_180004AA1
0x1800049f1  mov     qword ptr [r8], 0
0x1800049f8  mov     r14d, 8007000Eh
0x1800049fe  mov     dword ptr [rsp+38h+arg_8], r14d
0x180004a03  mov     [rsp+38h+arg_0], 0
0x180004a0c  mov     ecx, 20h ; ' '; Size
0x180004a11  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004a16  mov     rdi, rax
0x180004a19  mov     dword ptr [rax+18h], 0
0x180004a20  mov     qword ptr [rax+8], 0
0x180004a28  mov     qword ptr [rax+10h], 0
0x180004a30  lea     rax, ??_7?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable'
0x180004a37  mov     [rdi], rax
0x180004a3a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004a41  mov     rax, [rcx]
0x180004a44  mov     rax, [rax+8]
0x180004a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a4d  mov     [rsp+38h+arg_0], rdi
0x180004a52  jmp     short loc_180004A63
0x180004a54  mov     rsi, [rsp+38h+arg_10]
0x180004a59  mov     r14d, dword ptr [rsp+38h+arg_8]
0x180004a5e  mov     rdi, [rsp+38h+arg_0]
0x180004a63  test    rdi, rdi
0x180004a66  jz      short loc_180004A9E
0x180004a68  mov     rax, [rdi]
0x180004a6b  mov     r8, rsi
0x180004a6e  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180004a75  mov     rcx, rdi
0x180004a78  mov     rax, [rax]
0x180004a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a80  mov     r14d, eax
0x180004a83  test    eax, eax
0x180004a85  jz      short loc_180004A9E
0x180004a87  mov     rdx, [rdi]
0x180004a8a  mov     rax, [rdx+88h]
0x180004a91  mov     edx, 1
0x180004a96  mov     rcx, rdi
0x180004a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a9e  mov     eax, r14d
0x180004aa1  add     rsp, 20h
0x180004aa5  pop     r14
0x180004aa7  pop     rdi
0x180004aa8  pop     rsi
0x180004aa9  retn
```
