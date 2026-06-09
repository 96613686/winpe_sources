# ATL::CComCreator<ATL::CComObject<CDfsShellAdmin>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004724`
- end: `0x1800047f9`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCDfsShellAdmin@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004430`

## callees

- `0x180001164`
- `0x180004724`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CDfsShellAdmin>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  __int64 v4; // r14
  unsigned int v6; // esi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  _DWORD *v11; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = operator new(0x10u);
    v8 = v7;
    if ( v7 )
    {
      v7[2] = 0;
      *(_QWORD *)v7 = &ATL::CComObject<CDfsShellAdmin>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v11 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v11;
  }
  if ( v8 )
  {
    v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, v4, v3);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 40LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180004724  mov     [rsp+arg_10], r8
0x180004729  mov     [rsp+arg_8], rdx
0x18000472e  mov     [rsp+arg_0], rcx
0x180004733  push    rbx
0x180004734  push    rsi
0x180004735  push    rdi
0x180004736  push    r14
0x180004738  sub     rsp, 28h
0x18000473c  mov     rdi, r8
0x18000473f  mov     r14, rdx
0x180004742  test    r8, r8
0x180004745  jnz     short loc_180004751
0x180004747  mov     eax, 80004003h
0x18000474c  jmp     loc_1800047EF
0x180004751  mov     qword ptr [r8], 0
0x180004758  mov     esi, 8007000Eh
0x18000475d  mov     dword ptr [rsp+48h+arg_0], esi
0x180004761  mov     [rsp+48h+arg_18], 0
0x18000476a  mov     ecx, 10h; Size
0x18000476f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004774  mov     rbx, rax
0x180004777  test    rbx, rbx
0x18000477a  jz      short loc_1800047A0
0x18000477c  mov     dword ptr [rax+8], 0
0x180004783  lea     rax, ??_7?$CComObject@VCDfsShellAdmin@@@ATL@@6B@; const ATL::CComObject<CDfsShellAdmin>::`vftable'
0x18000478a  mov     [rbx], rax
0x18000478d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004794  mov     rax, [rcx]
0x180004797  mov     rax, [rax+8]
0x18000479b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047a0  mov     [rsp+48h+arg_18], rbx
0x1800047a5  jmp     short loc_1800047BA
0x1800047a7  mov     rdi, [rsp+48h+arg_10]
0x1800047ac  mov     r14, [rsp+48h+arg_8]
0x1800047b1  mov     esi, dword ptr [rsp+48h+arg_0]
0x1800047b5  mov     rbx, [rsp+48h+arg_18]
0x1800047ba  test    rbx, rbx
0x1800047bd  jz      short loc_1800047ED
0x1800047bf  mov     rax, [rbx]
0x1800047c2  mov     r8, rdi
0x1800047c5  mov     rdx, r14
0x1800047c8  mov     rcx, rbx
0x1800047cb  mov     rax, [rax]
0x1800047ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047d3  mov     esi, eax
0x1800047d5  test    eax, eax
0x1800047d7  jz      short loc_1800047ED
0x1800047d9  mov     rdx, [rbx]
0x1800047dc  mov     rax, [rdx+28h]
0x1800047e0  mov     edx, 1
0x1800047e5  mov     rcx, rbx
0x1800047e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047ed  mov     eax, esi
0x1800047ef  add     rsp, 28h
0x1800047f3  pop     r14
0x1800047f5  pop     rdi
0x1800047f6  pop     rsi
0x1800047f7  pop     rbx
0x1800047f8  retn
```
