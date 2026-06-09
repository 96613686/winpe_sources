# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180021d44`
- end: `0x180021e16`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800087fc`

## callees

- `0x1800018a0`
- `0x180021a7c`
- `0x180021d44`
- `0x18002a010`

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
0x180021d44  mov     [rsp+arg_10], r8
0x180021d49  mov     [rsp+arg_8], rdx
0x180021d4e  mov     [rsp+arg_0], rcx
0x180021d53  push    rbx
0x180021d54  push    rsi
0x180021d55  push    rdi
0x180021d56  sub     rsp, 20h
0x180021d5a  mov     rdi, r8
0x180021d5d  test    r8, r8
0x180021d60  jnz     short loc_180021D6C
0x180021d62  mov     eax, 80004003h
0x180021d67  jmp     loc_180021E0E
0x180021d6c  mov     qword ptr [r8], 0
0x180021d73  mov     esi, 8007000Eh
0x180021d78  mov     dword ptr [rsp+38h+arg_8], esi
0x180021d7c  mov     [rsp+38h+arg_0], 0
0x180021d85  mov     ecx, 68h ; 'h'; Size
0x180021d8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021d8f  mov     rbx, rax
0x180021d92  mov     [rsp+38h+arg_18], rax
0x180021d97  mov     rcx, rax; this
0x180021d9a  call    ??0CWinSATEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CWinSATEventTraceExtender::CWinSATEventTraceExtender(void)
0x180021d9f  lea     rax, ??_7?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable'
0x180021da6  mov     [rbx], rax
0x180021da9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180021db0  mov     rax, [rcx]
0x180021db3  mov     rax, [rax+8]
0x180021db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dbc  nop
0x180021dbd  mov     [rsp+38h+arg_0], rbx
0x180021dc2  jmp     short loc_180021DD2
0x180021dc4  mov     rdi, [rsp+38h+arg_10]
0x180021dc9  mov     esi, dword ptr [rsp+38h+arg_8]
0x180021dcd  mov     rbx, [rsp+38h+arg_0]
0x180021dd2  test    rbx, rbx
0x180021dd5  jz      short loc_180021E0C
0x180021dd7  mov     rax, [rbx]
0x180021dda  mov     r8, rdi
0x180021ddd  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180021de4  mov     rcx, rbx
0x180021de7  mov     rax, [rax]
0x180021dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021def  mov     esi, eax
0x180021df1  test    eax, eax
0x180021df3  jz      short loc_180021E0C
0x180021df5  mov     rdx, [rbx]
0x180021df8  mov     rax, [rdx+88h]
0x180021dff  mov     edx, 1
0x180021e04  mov     rcx, rbx
0x180021e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e0c  mov     eax, esi
0x180021e0e  add     rsp, 20h
0x180021e12  pop     rdi
0x180021e13  pop     rsi
0x180021e14  pop     rbx
0x180021e15  retn
```
