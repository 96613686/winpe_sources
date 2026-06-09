# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18001d5ec`
- end: `0x18001d6cf`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001abb0`

## callees

- `0x180001bb4`
- `0x18001d5ec`
- `0x180039010`

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
0x18001d5ec  mov     [rsp+arg_10], r8
0x18001d5f1  mov     [rsp+arg_8], rdx
0x18001d5f6  mov     [rsp+arg_0], rcx
0x18001d5fb  push    rsi
0x18001d5fc  push    rdi
0x18001d5fd  push    r14
0x18001d5ff  sub     rsp, 20h
0x18001d603  mov     rsi, r8
0x18001d606  test    r8, r8
0x18001d609  jnz     short loc_18001D615
0x18001d60b  mov     eax, 80004003h
0x18001d610  jmp     loc_18001D6C5
0x18001d615  mov     qword ptr [r8], 0
0x18001d61c  mov     r14d, 8007000Eh
0x18001d622  mov     dword ptr [rsp+38h+arg_8], r14d
0x18001d627  mov     [rsp+38h+arg_0], 0
0x18001d630  mov     ecx, 20h ; ' '; Size
0x18001d635  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d63a  mov     rdi, rax
0x18001d63d  mov     dword ptr [rax+18h], 0
0x18001d644  mov     qword ptr [rax+8], 0
0x18001d64c  mov     qword ptr [rax+10h], 0
0x18001d654  lea     rax, ??_7?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable'
0x18001d65b  mov     [rdi], rax
0x18001d65e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001d665  mov     rax, [rcx]
0x18001d668  mov     rax, [rax+8]
0x18001d66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d671  mov     [rsp+38h+arg_0], rdi
0x18001d676  jmp     short loc_18001D687
0x18001d678  mov     rsi, [rsp+38h+arg_10]
0x18001d67d  mov     r14d, dword ptr [rsp+38h+arg_8]
0x18001d682  mov     rdi, [rsp+38h+arg_0]
0x18001d687  test    rdi, rdi
0x18001d68a  jz      short loc_18001D6C2
0x18001d68c  mov     rax, [rdi]
0x18001d68f  mov     r8, rsi
0x18001d692  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18001d699  mov     rcx, rdi
0x18001d69c  mov     rax, [rax]
0x18001d69f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6a4  mov     r14d, eax
0x18001d6a7  test    eax, eax
0x18001d6a9  jz      short loc_18001D6C2
0x18001d6ab  mov     rdx, [rdi]
0x18001d6ae  mov     rax, [rdx+88h]
0x18001d6b5  mov     edx, 1
0x18001d6ba  mov     rcx, rdi
0x18001d6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6c2  mov     eax, r14d
0x18001d6c5  add     rsp, 20h
0x18001d6c9  pop     r14
0x18001d6cb  pop     rdi
0x18001d6cc  pop     rsi
0x18001d6cd  retn
```
