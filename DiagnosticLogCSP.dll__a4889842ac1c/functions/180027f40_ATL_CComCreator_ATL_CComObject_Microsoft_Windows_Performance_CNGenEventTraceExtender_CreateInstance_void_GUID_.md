# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180027f40`
- end: `0x180028012`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019ccc`

## callees

- `0x180001b84`
- `0x180026c3c`
- `0x180027f40`
- `0x180037010`

## pseudocode

```c
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
0x180027f40  mov     [rsp+arg_10], r8
0x180027f45  mov     [rsp+arg_8], rdx
0x180027f4a  mov     [rsp+arg_0], rcx
0x180027f4f  push    rbx
0x180027f50  push    rsi
0x180027f51  push    rdi
0x180027f52  sub     rsp, 20h
0x180027f56  mov     rdi, r8
0x180027f59  test    r8, r8
0x180027f5c  jnz     short loc_180027F68
0x180027f5e  mov     eax, 80004003h
0x180027f63  jmp     loc_18002800A
0x180027f68  mov     qword ptr [r8], 0
0x180027f6f  mov     esi, 8007000Eh
0x180027f74  mov     dword ptr [rsp+38h+arg_8], esi
0x180027f78  mov     [rsp+38h+arg_0], 0
0x180027f81  mov     ecx, 0B8h; Size
0x180027f86  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027f8b  mov     rbx, rax
0x180027f8e  mov     [rsp+38h+arg_18], rax
0x180027f93  mov     rcx, rax; this
0x180027f96  call    ??0CNGenEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CNGenEventTraceExtender::CNGenEventTraceExtender(void)
0x180027f9b  lea     rax, ??_7?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable'
0x180027fa2  mov     [rbx], rax
0x180027fa5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180027fac  mov     rax, [rcx]
0x180027faf  mov     rax, [rax+8]
0x180027fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fb8  nop
0x180027fb9  mov     [rsp+38h+arg_0], rbx
0x180027fbe  jmp     short loc_180027FCE
0x180027fc0  mov     rdi, [rsp+38h+arg_10]
0x180027fc5  mov     esi, dword ptr [rsp+38h+arg_8]
0x180027fc9  mov     rbx, [rsp+38h+arg_0]
0x180027fce  test    rbx, rbx
0x180027fd1  jz      short loc_180028008
0x180027fd3  mov     rax, [rbx]
0x180027fd6  mov     r8, rdi
0x180027fd9  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180027fe0  mov     rcx, rbx
0x180027fe3  mov     rax, [rax]
0x180027fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027feb  mov     esi, eax
0x180027fed  test    eax, eax
0x180027fef  jz      short loc_180028008
0x180027ff1  mov     rdx, [rbx]
0x180027ff4  mov     rax, [rdx+88h]
0x180027ffb  mov     edx, 1
0x180028000  mov     rcx, rbx
0x180028003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028008  mov     eax, esi
0x18002800a  add     rsp, 20h
0x18002800e  pop     rdi
0x18002800f  pop     rsi
0x180028010  pop     rbx
0x180028011  retn
```
