# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800306f4`
- end: `0x1800307c7`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001abb0`

## callees

- `0x180001bb4`
- `0x1800304d0`
- `0x1800306f4`
- `0x180039010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  Microsoft::Windows::Performance::CWinSATEventTraceExtender *v5; // rbx
  unsigned int v6; // esi
  Microsoft::Windows::Performance::CWinSATEventTraceExtender *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = (Microsoft::Windows::Performance::CWinSATEventTraceExtender *)operator new(0x68u);
    Microsoft::Windows::Performance::CWinSATEventTraceExtender::CWinSATEventTraceExtender(v5);
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable';
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
    v6 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CWinSATEventTraceExtender *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CWinSATEventTraceExtender *, __int64))(*(_QWORD *)v5 + 136LL))(
        v5,
        1);
  }
  return v6;
}

```

## disassembly

```asm
0x1800306f4  mov     [rsp+arg_10], r8
0x1800306f9  mov     [rsp+arg_8], rdx
0x1800306fe  mov     [rsp+arg_0], rcx
0x180030703  push    rbx
0x180030704  push    rsi
0x180030705  push    rdi
0x180030706  sub     rsp, 20h
0x18003070a  mov     rdi, r8
0x18003070d  test    r8, r8
0x180030710  jnz     short loc_18003071C
0x180030712  mov     eax, 80004003h
0x180030717  jmp     loc_1800307BE
0x18003071c  mov     qword ptr [r8], 0
0x180030723  mov     esi, 8007000Eh
0x180030728  mov     dword ptr [rsp+38h+arg_8], esi
0x18003072c  mov     [rsp+38h+arg_0], 0
0x180030735  mov     ecx, 68h ; 'h'; Size
0x18003073a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003073f  mov     rbx, rax
0x180030742  mov     [rsp+38h+arg_18], rax
0x180030747  mov     rcx, rax; this
0x18003074a  call    ??0CWinSATEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CWinSATEventTraceExtender::CWinSATEventTraceExtender(void)
0x18003074f  lea     rax, ??_7?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable'
0x180030756  mov     [rbx], rax
0x180030759  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180030760  mov     rax, [rcx]
0x180030763  mov     rax, [rax+8]
0x180030767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003076c  nop
0x18003076d  mov     [rsp+38h+arg_0], rbx
0x180030772  jmp     short loc_180030782
0x180030774  mov     rdi, [rsp+38h+arg_10]
0x180030779  mov     esi, dword ptr [rsp+38h+arg_8]
0x18003077d  mov     rbx, [rsp+38h+arg_0]
0x180030782  test    rbx, rbx
0x180030785  jz      short loc_1800307BC
0x180030787  mov     rax, [rbx]
0x18003078a  mov     r8, rdi
0x18003078d  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180030794  mov     rcx, rbx
0x180030797  mov     rax, [rax]
0x18003079a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003079f  mov     esi, eax
0x1800307a1  test    eax, eax
0x1800307a3  jz      short loc_1800307BC
0x1800307a5  mov     rdx, [rbx]
0x1800307a8  mov     rax, [rdx+88h]
0x1800307af  mov     edx, 1
0x1800307b4  mov     rcx, rbx
0x1800307b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307bc  mov     eax, esi
0x1800307be  add     rsp, 20h
0x1800307c2  pop     rdi
0x1800307c3  pop     rsi
0x1800307c4  pop     rbx
0x1800307c5  retn
```
