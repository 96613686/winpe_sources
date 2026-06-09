# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180015b98`
- end: `0x180015c75`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000447c`

## callees

- `0x180013f50`
- `0x180015b98`
- `0x18002687c`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  unsigned int v5; // esi
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v6; // rax
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v7; // rbx
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v8; // [rsp+50h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v5 = -2147024882;
  try
  {
    v6 = (Microsoft::Windows::Performance::CNGenEventTraceExtender *)operator new(0xD0u);
    v7 = v6;
    if ( v6 )
    {
      Microsoft::Windows::Performance::CNGenEventTraceExtender::CNGenEventTraceExtender(v6);
      *(_QWORD *)v7 = &ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable';
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
    v5 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CNGenEventTraceExtender *, GUID *, _QWORD *))v7)(
           v7,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v5 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CNGenEventTraceExtender *, __int64))(*(_QWORD *)v7 + 136LL))(
        v7,
        1);
  }
  return v5;
}

```

## disassembly

```asm
0x180015b98  mov     rax, rsp
0x180015b9b  mov     [rax+18h], r8
0x180015b9f  mov     [rax+10h], rdx
0x180015ba3  mov     [rax+8], rcx
0x180015ba7  push    rbx
0x180015ba8  push    rsi
0x180015ba9  push    rdi
0x180015baa  sub     rsp, 30h
0x180015bae  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180015bb6  mov     rdi, r8
0x180015bb9  test    r8, r8
0x180015bbc  jnz     short loc_180015BC8
0x180015bbe  mov     eax, 80004003h
0x180015bc3  jmp     loc_180015C6D
0x180015bc8  and     qword ptr [r8], 0
0x180015bcc  mov     esi, 8007000Eh
0x180015bd1  mov     [rsp+48h+arg_8], esi
0x180015bd5  and     [rsp+48h+arg_0], 0
0x180015bdb  mov     ecx, 0D0h; Size
0x180015be0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015be5  mov     rbx, rax
0x180015be8  mov     [rsp+48h+arg_18], rax
0x180015bed  test    rbx, rbx
0x180015bf0  jz      short loc_180015C1A
0x180015bf2  mov     rcx, rax; this
0x180015bf5  call    ??0CNGenEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CNGenEventTraceExtender::CNGenEventTraceExtender(void)
0x180015bfa  nop
0x180015bfb  lea     rax, ??_7?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable'
0x180015c02  mov     [rbx], rax
0x180015c05  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180015c0c  mov     rax, [rcx]
0x180015c0f  mov     rax, [rax+8]
0x180015c13  call    cs:__guard_dispatch_icall_fptr
0x180015c19  nop
0x180015c1a  mov     [rsp+48h+arg_0], rbx
0x180015c1f  jmp     short loc_180015C2F
0x180015c21  mov     rdi, [rsp+48h+arg_10]
0x180015c26  mov     esi, [rsp+48h+arg_8]
0x180015c2a  mov     rbx, [rsp+48h+arg_0]
0x180015c2f  test    rbx, rbx
0x180015c32  jz      short loc_180015C6B
0x180015c34  mov     rax, [rbx]
0x180015c37  mov     r8, rdi
0x180015c3a  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180015c41  mov     rcx, rbx
0x180015c44  mov     rax, [rax]
0x180015c47  call    cs:__guard_dispatch_icall_fptr
0x180015c4d  mov     esi, eax
0x180015c4f  test    eax, eax
0x180015c51  jz      short loc_180015C6B
0x180015c53  mov     rdx, [rbx]
0x180015c56  mov     rax, [rdx+88h]
0x180015c5d  mov     edx, 1
0x180015c62  mov     rcx, rbx
0x180015c65  call    cs:__guard_dispatch_icall_fptr
0x180015c6b  mov     eax, esi
0x180015c6d  add     rsp, 30h
0x180015c71  pop     rdi
0x180015c72  pop     rsi
0x180015c73  pop     rbx
0x180015c74  retn
```
