# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180005aa8`
- end: `0x180005b7d`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `213`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004b5c`

## callees

- `0x180005aa8`
- `0x18002687c`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  unsigned int v5; // esi
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
    v6 = operator new(0x10u);
    v7 = v6;
    if ( v6 )
    {
      v6[2] = 0;
      *(_QWORD *)v6 = &ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vftable';
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
           &GUID_ad66cb4b_7487_4f77_84cf_cc94f549eb5e,
           v3);
    if ( v5 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 32LL))(v7, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x180005aa8  mov     rax, rsp
0x180005aab  mov     [rax+18h], r8
0x180005aaf  mov     [rax+10h], rdx
0x180005ab3  mov     [rax+8], rcx
0x180005ab7  push    rbx
0x180005ab8  push    rsi
0x180005ab9  push    rdi
0x180005aba  sub     rsp, 30h
0x180005abe  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180005ac6  mov     rdi, r8
0x180005ac9  test    r8, r8
0x180005acc  jnz     short loc_180005AD8
0x180005ace  mov     eax, 80004003h
0x180005ad3  jmp     loc_180005B75
0x180005ad8  and     qword ptr [r8], 0
0x180005adc  mov     esi, 8007000Eh
0x180005ae1  mov     [rsp+48h+arg_8], esi
0x180005ae5  and     [rsp+48h+arg_0], 0
0x180005aeb  mov     ecx, 10h; Size
0x180005af0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005af5  mov     rbx, rax
0x180005af8  mov     [rsp+48h+arg_18], rax
0x180005afd  test    rbx, rbx
0x180005b00  jz      short loc_180005B25
0x180005b02  and     dword ptr [rax+8], 0
0x180005b06  lea     rax, ??_7?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vftable'
0x180005b0d  mov     [rbx], rax
0x180005b10  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005b17  mov     rax, [rcx]
0x180005b1a  mov     rax, [rax+8]
0x180005b1e  call    cs:__guard_dispatch_icall_fptr
0x180005b24  nop
0x180005b25  mov     [rsp+48h+arg_0], rbx
0x180005b2a  jmp     short loc_180005B3A
0x180005b2c  mov     rdi, [rsp+48h+arg_10]
0x180005b31  mov     esi, [rsp+48h+arg_8]
0x180005b35  mov     rbx, [rsp+48h+arg_0]
0x180005b3a  test    rbx, rbx
0x180005b3d  jz      short loc_180005B73
0x180005b3f  mov     rax, [rbx]
0x180005b42  mov     r8, rdi
0x180005b45  lea     rdx, _GUID_ad66cb4b_7487_4f77_84cf_cc94f549eb5e
0x180005b4c  mov     rcx, rbx
0x180005b4f  mov     rax, [rax]
0x180005b52  call    cs:__guard_dispatch_icall_fptr
0x180005b58  mov     esi, eax
0x180005b5a  test    eax, eax
0x180005b5c  jz      short loc_180005B73
0x180005b5e  mov     rdx, [rbx]
0x180005b61  mov     rax, [rdx+20h]
0x180005b65  mov     edx, 1
0x180005b6a  mov     rcx, rbx
0x180005b6d  call    cs:__guard_dispatch_icall_fptr
0x180005b73  mov     eax, esi
0x180005b75  add     rsp, 30h
0x180005b79  pop     rdi
0x180005b7a  pop     rsi
0x180005b7b  pop     rbx
0x180005b7c  retn
```
