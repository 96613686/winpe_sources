# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180008a18`
- end: `0x180008b01`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `233`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000447c`

## callees

- `0x180008a18`
- `0x18002687c`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(
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
      *(_QWORD *)v6 = &ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable';
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
0x180008a18  mov     rax, rsp
0x180008a1b  mov     [rax+18h], r8
0x180008a1f  mov     [rax+10h], rdx
0x180008a23  mov     [rax+8], rcx
0x180008a27  push    rbx
0x180008a28  push    rsi
0x180008a29  push    r14
0x180008a2b  sub     rsp, 30h
0x180008a2f  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180008a37  mov     rsi, r8
0x180008a3a  test    r8, r8
0x180008a3d  jnz     short loc_180008A49
0x180008a3f  mov     eax, 80004003h
0x180008a44  jmp     loc_180008AF8
0x180008a49  and     qword ptr [r8], 0
0x180008a4d  mov     r14d, 8007000Eh
0x180008a53  mov     [rsp+48h+arg_8], r14d
0x180008a58  and     [rsp+48h+arg_0], 0
0x180008a5e  mov     ecx, 20h ; ' '; Size
0x180008a63  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008a68  mov     rbx, rax
0x180008a6b  mov     [rsp+48h+arg_18], rax
0x180008a70  test    rbx, rbx
0x180008a73  jz      short loc_180008AA2
0x180008a75  and     dword ptr [rax+18h], 0
0x180008a79  and     qword ptr [rax+8], 0
0x180008a7e  and     qword ptr [rax+10h], 0
0x180008a83  lea     rax, ??_7?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable'
0x180008a8a  mov     [rbx], rax
0x180008a8d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008a94  mov     rax, [rcx]
0x180008a97  mov     rax, [rax+8]
0x180008a9b  call    cs:__guard_dispatch_icall_fptr
0x180008aa1  nop
0x180008aa2  mov     [rsp+48h+arg_0], rbx
0x180008aa7  jmp     short loc_180008AB8
0x180008aa9  mov     rsi, [rsp+48h+arg_10]
0x180008aae  mov     r14d, [rsp+48h+arg_8]
0x180008ab3  mov     rbx, [rsp+48h+arg_0]
0x180008ab8  test    rbx, rbx
0x180008abb  jz      short loc_180008AF5
0x180008abd  mov     rax, [rbx]
0x180008ac0  mov     r8, rsi
0x180008ac3  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180008aca  mov     rcx, rbx
0x180008acd  mov     rax, [rax]
0x180008ad0  call    cs:__guard_dispatch_icall_fptr
0x180008ad6  mov     r14d, eax
0x180008ad9  test    eax, eax
0x180008adb  jz      short loc_180008AF5
0x180008add  mov     rdx, [rbx]
0x180008ae0  mov     rax, [rdx+88h]
0x180008ae7  mov     edx, 1
0x180008aec  mov     rcx, rbx
0x180008aef  call    cs:__guard_dispatch_icall_fptr
0x180008af5  mov     eax, r14d
0x180008af8  add     rsp, 30h
0x180008afc  pop     r14
0x180008afe  pop     rsi
0x180008aff  pop     rbx
0x180008b00  retn
```
