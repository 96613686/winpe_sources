# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800048f8`
- end: `0x1800049c0`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `200`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008a88`

## callees

- `0x1800018a0`
- `0x1800048f8`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  _DWORD *v5; // rbx
  unsigned int v6; // esi
  _DWORD *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = operator new(0x10u);
    v5[2] = 0;
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vftable';
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
    v6 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_ad66cb4b_7487_4f77_84cf_cc94f549eb5e,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v5 + 32LL))(v5, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x1800048f8  mov     [rsp+arg_10], r8
0x1800048fd  mov     [rsp+arg_8], rdx
0x180004902  mov     [rsp+arg_0], rcx
0x180004907  push    rbx
0x180004908  push    rsi
0x180004909  push    rdi
0x18000490a  sub     rsp, 20h
0x18000490e  mov     rdi, r8
0x180004911  test    r8, r8
0x180004914  jnz     short loc_180004920
0x180004916  mov     eax, 80004003h
0x18000491b  jmp     loc_1800049B8
0x180004920  mov     qword ptr [r8], 0
0x180004927  mov     esi, 8007000Eh
0x18000492c  mov     dword ptr [rsp+38h+arg_8], esi
0x180004930  mov     [rsp+38h+arg_0], 0
0x180004939  mov     ecx, 10h; Size
0x18000493e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004943  mov     rbx, rax
0x180004946  mov     dword ptr [rax+8], 0
0x18000494d  lea     rax, ??_7?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vftable'
0x180004954  mov     [rbx], rax
0x180004957  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000495e  mov     rax, [rcx]
0x180004961  mov     rax, [rax+8]
0x180004965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000496a  mov     [rsp+38h+arg_0], rbx
0x18000496f  jmp     short loc_18000497F
0x180004971  mov     rdi, [rsp+38h+arg_10]
0x180004976  mov     esi, dword ptr [rsp+38h+arg_8]
0x18000497a  mov     rbx, [rsp+38h+arg_0]
0x18000497f  test    rbx, rbx
0x180004982  jz      short loc_1800049B6
0x180004984  mov     rax, [rbx]
0x180004987  mov     r8, rdi
0x18000498a  lea     rdx, _GUID_ad66cb4b_7487_4f77_84cf_cc94f549eb5e
0x180004991  mov     rcx, rbx
0x180004994  mov     rax, [rax]
0x180004997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000499c  mov     esi, eax
0x18000499e  test    eax, eax
0x1800049a0  jz      short loc_1800049B6
0x1800049a2  mov     rdx, [rbx]
0x1800049a5  mov     rax, [rdx+20h]
0x1800049a9  mov     edx, 1
0x1800049ae  mov     rcx, rbx
0x1800049b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049b6  mov     eax, esi
0x1800049b8  add     rsp, 20h
0x1800049bc  pop     rdi
0x1800049bd  pop     rsi
0x1800049be  pop     rbx
0x1800049bf  retn
```
