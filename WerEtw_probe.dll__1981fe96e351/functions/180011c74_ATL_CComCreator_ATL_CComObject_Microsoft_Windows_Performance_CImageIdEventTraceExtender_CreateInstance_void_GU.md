# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180011c74`
- end: `0x180011d46`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800087fc`

## callees

- `0x1800018a0`
- `0x18000d770`
- `0x180011c74`
- `0x18002a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v5; // rbx
  unsigned int v6; // esi
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)operator new(0x1A8u);
    Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(v5);
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable';
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
    v6 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CImageIdEventTraceExtender *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CImageIdEventTraceExtender *, __int64))(*(_QWORD *)v5 + 136LL))(
        v5,
        1);
  }
  return v6;
}

```

## disassembly

```asm
0x180011c74  mov     [rsp+arg_10], r8
0x180011c79  mov     [rsp+arg_8], rdx
0x180011c7e  mov     [rsp+arg_0], rcx
0x180011c83  push    rbx
0x180011c84  push    rsi
0x180011c85  push    rdi
0x180011c86  sub     rsp, 20h
0x180011c8a  mov     rdi, r8
0x180011c8d  test    r8, r8
0x180011c90  jnz     short loc_180011C9C
0x180011c92  mov     eax, 80004003h
0x180011c97  jmp     loc_180011D3E
0x180011c9c  mov     qword ptr [r8], 0
0x180011ca3  mov     esi, 8007000Eh
0x180011ca8  mov     dword ptr [rsp+38h+arg_8], esi
0x180011cac  mov     [rsp+38h+arg_0], 0
0x180011cb5  mov     ecx, 1A8h; Size
0x180011cba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011cbf  mov     rbx, rax
0x180011cc2  mov     [rsp+38h+arg_18], rax
0x180011cc7  mov     rcx, rax; this
0x180011cca  call    ??0CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(void)
0x180011ccf  lea     rax, ??_7?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable'
0x180011cd6  mov     [rbx], rax
0x180011cd9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011ce0  mov     rax, [rcx]
0x180011ce3  mov     rax, [rax+8]
0x180011ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cec  nop
0x180011ced  mov     [rsp+38h+arg_0], rbx
0x180011cf2  jmp     short loc_180011D02
0x180011cf4  mov     rdi, [rsp+38h+arg_10]
0x180011cf9  mov     esi, dword ptr [rsp+38h+arg_8]
0x180011cfd  mov     rbx, [rsp+38h+arg_0]
0x180011d02  test    rbx, rbx
0x180011d05  jz      short loc_180011D3C
0x180011d07  mov     rax, [rbx]
0x180011d0a  mov     r8, rdi
0x180011d0d  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180011d14  mov     rcx, rbx
0x180011d17  mov     rax, [rax]
0x180011d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d1f  mov     esi, eax
0x180011d21  test    eax, eax
0x180011d23  jz      short loc_180011D3C
0x180011d25  mov     rdx, [rbx]
0x180011d28  mov     rax, [rdx+88h]
0x180011d2f  mov     edx, 1
0x180011d34  mov     rcx, rbx
0x180011d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d3c  mov     eax, esi
0x180011d3e  add     rsp, 20h
0x180011d42  pop     rdi
0x180011d43  pop     rsi
0x180011d44  pop     rbx
0x180011d45  retn
```
