# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180030a94`
- end: `0x180030b66`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019ccc`

## callees

- `0x180001b84`
- `0x18003050c`
- `0x180030a94`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  Microsoft::Windows::Performance::CElfImageEventTraceExtender *v5; // rbx
  unsigned int v6; // esi
  Microsoft::Windows::Performance::CElfImageEventTraceExtender *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = (Microsoft::Windows::Performance::CElfImageEventTraceExtender *)operator new(0x50u);
    Microsoft::Windows::Performance::CElfImageEventTraceExtender::CElfImageEventTraceExtender(v5);
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable';
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
    v6 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CElfImageEventTraceExtender *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CElfImageEventTraceExtender *, __int64))(*(_QWORD *)v5 + 160LL))(
        v5,
        1);
  }
  return v6;
}

```

## disassembly

```asm
0x180030a94  mov     [rsp+arg_10], r8
0x180030a99  mov     [rsp+arg_8], rdx
0x180030a9e  mov     [rsp+arg_0], rcx
0x180030aa3  push    rbx
0x180030aa4  push    rsi
0x180030aa5  push    rdi
0x180030aa6  sub     rsp, 20h
0x180030aaa  mov     rdi, r8
0x180030aad  test    r8, r8
0x180030ab0  jnz     short loc_180030ABC
0x180030ab2  mov     eax, 80004003h
0x180030ab7  jmp     loc_180030B5E
0x180030abc  mov     qword ptr [r8], 0
0x180030ac3  mov     esi, 8007000Eh
0x180030ac8  mov     dword ptr [rsp+38h+arg_8], esi
0x180030acc  mov     [rsp+38h+arg_0], 0
0x180030ad5  mov     ecx, 50h ; 'P'; Size
0x180030ada  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030adf  mov     rbx, rax
0x180030ae2  mov     [rsp+38h+arg_18], rax
0x180030ae7  mov     rcx, rax; this
0x180030aea  call    ??0CElfImageEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CElfImageEventTraceExtender::CElfImageEventTraceExtender(void)
0x180030aef  lea     rax, ??_7?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable'
0x180030af6  mov     [rbx], rax
0x180030af9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180030b00  mov     rax, [rcx]
0x180030b03  mov     rax, [rax+8]
0x180030b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b0c  nop
0x180030b0d  mov     [rsp+38h+arg_0], rbx
0x180030b12  jmp     short loc_180030B22
0x180030b14  mov     rdi, [rsp+38h+arg_10]
0x180030b19  mov     esi, dword ptr [rsp+38h+arg_8]
0x180030b1d  mov     rbx, [rsp+38h+arg_0]
0x180030b22  test    rbx, rbx
0x180030b25  jz      short loc_180030B5C
0x180030b27  mov     rax, [rbx]
0x180030b2a  mov     r8, rdi
0x180030b2d  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180030b34  mov     rcx, rbx
0x180030b37  mov     rax, [rax]
0x180030b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b3f  mov     esi, eax
0x180030b41  test    eax, eax
0x180030b43  jz      short loc_180030B5C
0x180030b45  mov     rdx, [rbx]
0x180030b48  mov     rax, [rdx+0A0h]
0x180030b4f  mov     edx, 1
0x180030b54  mov     rcx, rbx
0x180030b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b5c  mov     eax, esi
0x180030b5e  add     rsp, 20h
0x180030b62  pop     rdi
0x180030b63  pop     rsi
0x180030b64  pop     rbx
0x180030b65  retn
```
