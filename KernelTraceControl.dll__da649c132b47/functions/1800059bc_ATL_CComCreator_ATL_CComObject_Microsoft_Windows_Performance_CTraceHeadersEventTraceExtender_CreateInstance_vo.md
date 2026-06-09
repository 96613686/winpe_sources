# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800059bc`
- end: `0x180005aa5`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `233`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000447c`

## callees

- `0x1800059bc`
- `0x18002687c`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(
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
      *(_QWORD *)v6 = &ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable';
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
0x1800059bc  mov     rax, rsp
0x1800059bf  mov     [rax+18h], r8
0x1800059c3  mov     [rax+10h], rdx
0x1800059c7  mov     [rax+8], rcx
0x1800059cb  push    rbx
0x1800059cc  push    rsi
0x1800059cd  push    r14
0x1800059cf  sub     rsp, 30h
0x1800059d3  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1800059db  mov     rsi, r8
0x1800059de  test    r8, r8
0x1800059e1  jnz     short loc_1800059ED
0x1800059e3  mov     eax, 80004003h
0x1800059e8  jmp     loc_180005A9C
0x1800059ed  and     qword ptr [r8], 0
0x1800059f1  mov     r14d, 8007000Eh
0x1800059f7  mov     [rsp+48h+arg_8], r14d
0x1800059fc  and     [rsp+48h+arg_0], 0
0x180005a02  mov     ecx, 20h ; ' '; Size
0x180005a07  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005a0c  mov     rbx, rax
0x180005a0f  mov     [rsp+48h+arg_18], rax
0x180005a14  test    rbx, rbx
0x180005a17  jz      short loc_180005A46
0x180005a19  and     dword ptr [rax+18h], 0
0x180005a1d  and     qword ptr [rax+8], 0
0x180005a22  and     qword ptr [rax+10h], 0
0x180005a27  lea     rax, ??_7?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable'
0x180005a2e  mov     [rbx], rax
0x180005a31  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005a38  mov     rax, [rcx]
0x180005a3b  mov     rax, [rax+8]
0x180005a3f  call    cs:__guard_dispatch_icall_fptr
0x180005a45  nop
0x180005a46  mov     [rsp+48h+arg_0], rbx
0x180005a4b  jmp     short loc_180005A5C
0x180005a4d  mov     rsi, [rsp+48h+arg_10]
0x180005a52  mov     r14d, [rsp+48h+arg_8]
0x180005a57  mov     rbx, [rsp+48h+arg_0]
0x180005a5c  test    rbx, rbx
0x180005a5f  jz      short loc_180005A99
0x180005a61  mov     rax, [rbx]
0x180005a64  mov     r8, rsi
0x180005a67  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180005a6e  mov     rcx, rbx
0x180005a71  mov     rax, [rax]
0x180005a74  call    cs:__guard_dispatch_icall_fptr
0x180005a7a  mov     r14d, eax
0x180005a7d  test    eax, eax
0x180005a7f  jz      short loc_180005A99
0x180005a81  mov     rdx, [rbx]
0x180005a84  mov     rax, [rdx+88h]
0x180005a8b  mov     edx, 1
0x180005a90  mov     rcx, rbx
0x180005a93  call    cs:__guard_dispatch_icall_fptr
0x180005a99  mov     eax, r14d
0x180005a9c  add     rsp, 30h
0x180005aa0  pop     r14
0x180005aa2  pop     rsi
0x180005aa3  pop     rbx
0x180005aa4  retn
```
