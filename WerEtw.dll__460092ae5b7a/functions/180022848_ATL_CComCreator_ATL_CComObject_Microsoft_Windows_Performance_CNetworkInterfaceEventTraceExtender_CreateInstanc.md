# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180022848`
- end: `0x18002292a`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `226`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800087fc`

## callees

- `0x1800018a0`
- `0x180022848`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(
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
  *(_QWORD *)v6 = &ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vftable';
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
0x180022848  mov     [rsp+arg_10], r8
0x18002284d  mov     [rsp+arg_8], rdx
0x180022852  mov     [rsp+arg_0], rcx
0x180022857  push    rsi
0x180022858  push    rdi
0x180022859  push    r14
0x18002285b  sub     rsp, 20h
0x18002285f  mov     rsi, r8
0x180022862  test    r8, r8
0x180022865  jnz     short loc_180022871
0x180022867  mov     eax, 80004003h
0x18002286c  jmp     loc_180022921
0x180022871  mov     qword ptr [r8], 0
0x180022878  mov     r14d, 8007000Eh
0x18002287e  mov     dword ptr [rsp+38h+arg_8], r14d
0x180022883  mov     [rsp+38h+arg_0], 0
0x18002288c  mov     ecx, 20h ; ' '; Size
0x180022891  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022896  mov     rdi, rax
0x180022899  mov     dword ptr [rax+18h], 0
0x1800228a0  mov     qword ptr [rax+8], 0
0x1800228a8  mov     qword ptr [rax+10h], 0
0x1800228b0  lea     rax, ??_7?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vftable'
0x1800228b7  mov     [rdi], rax
0x1800228ba  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800228c1  mov     rax, [rcx]
0x1800228c4  mov     rax, [rax+8]
0x1800228c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228cd  mov     [rsp+38h+arg_0], rdi
0x1800228d2  jmp     short loc_1800228E3
0x1800228d4  mov     rsi, [rsp+38h+arg_10]
0x1800228d9  mov     r14d, dword ptr [rsp+38h+arg_8]
0x1800228de  mov     rdi, [rsp+38h+arg_0]
0x1800228e3  test    rdi, rdi
0x1800228e6  jz      short loc_18002291E
0x1800228e8  mov     rax, [rdi]
0x1800228eb  mov     r8, rsi
0x1800228ee  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x1800228f5  mov     rcx, rdi
0x1800228f8  mov     rax, [rax]
0x1800228fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022900  mov     r14d, eax
0x180022903  test    eax, eax
0x180022905  jz      short loc_18002291E
0x180022907  mov     rdx, [rdi]
0x18002290a  mov     rax, [rdx+88h]
0x180022911  mov     edx, 1
0x180022916  mov     rcx, rdi
0x180022919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002291e  mov     eax, r14d
0x180022921  add     rsp, 20h
0x180022925  pop     r14
0x180022927  pop     rdi
0x180022928  pop     rsi
0x180022929  retn
```
