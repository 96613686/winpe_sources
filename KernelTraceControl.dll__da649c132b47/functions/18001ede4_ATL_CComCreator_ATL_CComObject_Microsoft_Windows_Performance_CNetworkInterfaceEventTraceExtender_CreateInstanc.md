# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18001ede4`
- end: `0x18001eecd`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `233`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000447c`

## callees

- `0x18001ede4`
- `0x18002687c`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  unsigned int v5; // r14d
  _DWORD *v6; // rax
  _DWORD *v7; // rbx
  _DWORD *v8; // [rsp+50h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v5 = -2147024882;
  try
  {
    v6 = operator new(0x20u);
    v7 = v6;
    if ( v6 )
    {
      v6[6] = 0;
      *((_QWORD *)v6 + 1) = 0;
      *((_QWORD *)v6 + 2) = 0;
      *(_QWORD *)v6 = &ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v8 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v5 = -2147024882;
    v7 = v8;
  }
  if ( v7 )
  {
    v5 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, _QWORD *))v7)(
           v7,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v5 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 136LL))(v7, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x18001ede4  mov     rax, rsp
0x18001ede7  mov     [rax+18h], r8
0x18001edeb  mov     [rax+10h], rdx
0x18001edef  mov     [rax+8], rcx
0x18001edf3  push    rbx
0x18001edf4  push    rsi
0x18001edf5  push    r14
0x18001edf7  sub     rsp, 30h
0x18001edfb  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18001ee03  mov     rsi, r8
0x18001ee06  test    r8, r8
0x18001ee09  jnz     short loc_18001EE15
0x18001ee0b  mov     eax, 80004003h
0x18001ee10  jmp     loc_18001EEC4
0x18001ee15  and     qword ptr [r8], 0
0x18001ee19  mov     r14d, 8007000Eh
0x18001ee1f  mov     [rsp+48h+arg_8], r14d
0x18001ee24  and     [rsp+48h+arg_0], 0
0x18001ee2a  mov     ecx, 20h ; ' '; Size
0x18001ee2f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ee34  mov     rbx, rax
0x18001ee37  mov     [rsp+48h+arg_18], rax
0x18001ee3c  test    rbx, rbx
0x18001ee3f  jz      short loc_18001EE6E
0x18001ee41  and     dword ptr [rax+18h], 0
0x18001ee45  and     qword ptr [rax+8], 0
0x18001ee4a  and     qword ptr [rax+10h], 0
0x18001ee4f  lea     rax, ??_7?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vftable'
0x18001ee56  mov     [rbx], rax
0x18001ee59  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001ee60  mov     rax, [rcx]
0x18001ee63  mov     rax, [rax+8]
0x18001ee67  call    cs:__guard_dispatch_icall_fptr
0x18001ee6d  nop
0x18001ee6e  mov     [rsp+48h+arg_0], rbx
0x18001ee73  jmp     short loc_18001EE84
0x18001ee75  mov     rsi, [rsp+48h+arg_10]
0x18001ee7a  mov     r14d, [rsp+48h+arg_8]
0x18001ee7f  mov     rbx, [rsp+48h+arg_0]
0x18001ee84  test    rbx, rbx
0x18001ee87  jz      short loc_18001EEC1
0x18001ee89  mov     rax, [rbx]
0x18001ee8c  mov     r8, rsi
0x18001ee8f  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18001ee96  mov     rcx, rbx
0x18001ee99  mov     rax, [rax]
0x18001ee9c  call    cs:__guard_dispatch_icall_fptr
0x18001eea2  mov     r14d, eax
0x18001eea5  test    eax, eax
0x18001eea7  jz      short loc_18001EEC1
0x18001eea9  mov     rdx, [rbx]
0x18001eeac  mov     rax, [rdx+88h]
0x18001eeb3  mov     edx, 1
0x18001eeb8  mov     rcx, rbx
0x18001eebb  call    cs:__guard_dispatch_icall_fptr
0x18001eec1  mov     eax, r14d
0x18001eec4  add     rsp, 30h
0x18001eec8  pop     r14
0x18001eeca  pop     rsi
0x18001eecb  pop     rbx
0x18001eecc  retn
```
