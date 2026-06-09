# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180031fa4`
- end: `0x180032077`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001abb0`

## callees

- `0x180001bb4`
- `0x1800319b0`
- `0x180031fa4`
- `0x180039010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180031fa4  mov     [rsp+arg_10], r8
0x180031fa9  mov     [rsp+arg_8], rdx
0x180031fae  mov     [rsp+arg_0], rcx
0x180031fb3  push    rbx
0x180031fb4  push    rsi
0x180031fb5  push    rdi
0x180031fb6  sub     rsp, 20h
0x180031fba  mov     rdi, r8
0x180031fbd  test    r8, r8
0x180031fc0  jnz     short loc_180031FCC
0x180031fc2  mov     eax, 80004003h
0x180031fc7  jmp     loc_18003206E
0x180031fcc  mov     qword ptr [r8], 0
0x180031fd3  mov     esi, 8007000Eh
0x180031fd8  mov     dword ptr [rsp+38h+arg_8], esi
0x180031fdc  mov     [rsp+38h+arg_0], 0
0x180031fe5  mov     ecx, 50h ; 'P'; Size
0x180031fea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031fef  mov     rbx, rax
0x180031ff2  mov     [rsp+38h+arg_18], rax
0x180031ff7  mov     rcx, rax; this
0x180031ffa  call    ??0CElfImageEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CElfImageEventTraceExtender::CElfImageEventTraceExtender(void)
0x180031fff  lea     rax, ??_7?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable'
0x180032006  mov     [rbx], rax
0x180032009  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180032010  mov     rax, [rcx]
0x180032013  mov     rax, [rax+8]
0x180032017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003201c  nop
0x18003201d  mov     [rsp+38h+arg_0], rbx
0x180032022  jmp     short loc_180032032
0x180032024  mov     rdi, [rsp+38h+arg_10]
0x180032029  mov     esi, dword ptr [rsp+38h+arg_8]
0x18003202d  mov     rbx, [rsp+38h+arg_0]
0x180032032  test    rbx, rbx
0x180032035  jz      short loc_18003206C
0x180032037  mov     rax, [rbx]
0x18003203a  mov     r8, rdi
0x18003203d  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180032044  mov     rcx, rbx
0x180032047  mov     rax, [rax]
0x18003204a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003204f  mov     esi, eax
0x180032051  test    eax, eax
0x180032053  jz      short loc_18003206C
0x180032055  mov     rdx, [rbx]
0x180032058  mov     rax, [rdx+0A0h]
0x18003205f  mov     edx, 1
0x180032064  mov     rcx, rbx
0x180032067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003206c  mov     eax, esi
0x18003206e  add     rsp, 20h
0x180032072  pop     rdi
0x180032073  pop     rsi
0x180032074  pop     rbx
0x180032075  retn
```
