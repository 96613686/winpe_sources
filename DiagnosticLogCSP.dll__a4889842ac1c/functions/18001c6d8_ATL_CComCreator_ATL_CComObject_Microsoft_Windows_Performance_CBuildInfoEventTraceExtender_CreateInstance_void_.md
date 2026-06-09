# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18001c6d8`
- end: `0x18001c7ba`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `226`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019ccc`

## callees

- `0x180001b84`
- `0x18001c6d8`
- `0x180037010`

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
0x18001c6d8  mov     [rsp+arg_10], r8
0x18001c6dd  mov     [rsp+arg_8], rdx
0x18001c6e2  mov     [rsp+arg_0], rcx
0x18001c6e7  push    rsi
0x18001c6e8  push    rdi
0x18001c6e9  push    r14
0x18001c6eb  sub     rsp, 20h
0x18001c6ef  mov     rsi, r8
0x18001c6f2  test    r8, r8
0x18001c6f5  jnz     short loc_18001C701
0x18001c6f7  mov     eax, 80004003h
0x18001c6fc  jmp     loc_18001C7B1
0x18001c701  mov     qword ptr [r8], 0
0x18001c708  mov     r14d, 8007000Eh
0x18001c70e  mov     dword ptr [rsp+38h+arg_8], r14d
0x18001c713  mov     [rsp+38h+arg_0], 0
0x18001c71c  mov     ecx, 20h ; ' '; Size
0x18001c721  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c726  mov     rdi, rax
0x18001c729  mov     dword ptr [rax+18h], 0
0x18001c730  mov     qword ptr [rax+8], 0
0x18001c738  mov     qword ptr [rax+10h], 0
0x18001c740  lea     rax, ??_7?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable'
0x18001c747  mov     [rdi], rax
0x18001c74a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001c751  mov     rax, [rcx]
0x18001c754  mov     rax, [rax+8]
0x18001c758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c75d  mov     [rsp+38h+arg_0], rdi
0x18001c762  jmp     short loc_18001C773
0x18001c764  mov     rsi, [rsp+38h+arg_10]
0x18001c769  mov     r14d, dword ptr [rsp+38h+arg_8]
0x18001c76e  mov     rdi, [rsp+38h+arg_0]
0x18001c773  test    rdi, rdi
0x18001c776  jz      short loc_18001C7AE
0x18001c778  mov     rax, [rdi]
0x18001c77b  mov     r8, rsi
0x18001c77e  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18001c785  mov     rcx, rdi
0x18001c788  mov     rax, [rax]
0x18001c78b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c790  mov     r14d, eax
0x18001c793  test    eax, eax
0x18001c795  jz      short loc_18001C7AE
0x18001c797  mov     rdx, [rdi]
0x18001c79a  mov     rax, [rdx+88h]
0x18001c7a1  mov     edx, 1
0x18001c7a6  mov     rcx, rdi
0x18001c7a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7ae  mov     eax, r14d
0x18001c7b1  add     rsp, 20h
0x18001c7b5  pop     r14
0x18001c7b7  pop     rdi
0x18001c7b8  pop     rsi
0x18001c7b9  retn
```
