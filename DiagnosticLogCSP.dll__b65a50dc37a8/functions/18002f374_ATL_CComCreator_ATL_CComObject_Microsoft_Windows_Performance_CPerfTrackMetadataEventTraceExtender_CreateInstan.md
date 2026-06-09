# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18002f374`
- end: `0x18002f447`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001abb0`

## callees

- `0x180001bb4`
- `0x18002edd0`
- `0x18002f374`
- `0x180039010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v5; // rbx
  unsigned int v6; // esi
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = (Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *)operator new(0x90u);
    Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::CPerfTrackMetadataEventTraceExtender(v5);
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable';
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
    v6 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *, __int64))(*(_QWORD *)v5 + 136LL))(
        v5,
        1);
  }
  return v6;
}

```

## disassembly

```asm
0x18002f374  mov     [rsp+arg_10], r8
0x18002f379  mov     [rsp+arg_8], rdx
0x18002f37e  mov     [rsp+arg_0], rcx
0x18002f383  push    rbx
0x18002f384  push    rsi
0x18002f385  push    rdi
0x18002f386  sub     rsp, 20h
0x18002f38a  mov     rdi, r8
0x18002f38d  test    r8, r8
0x18002f390  jnz     short loc_18002F39C
0x18002f392  mov     eax, 80004003h
0x18002f397  jmp     loc_18002F43E
0x18002f39c  mov     qword ptr [r8], 0
0x18002f3a3  mov     esi, 8007000Eh
0x18002f3a8  mov     dword ptr [rsp+38h+arg_8], esi
0x18002f3ac  mov     [rsp+38h+arg_0], 0
0x18002f3b5  mov     ecx, 90h; Size
0x18002f3ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f3bf  mov     rbx, rax
0x18002f3c2  mov     [rsp+38h+arg_18], rax
0x18002f3c7  mov     rcx, rax; this
0x18002f3ca  call    ??0CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::CPerfTrackMetadataEventTraceExtender(void)
0x18002f3cf  lea     rax, ??_7?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable'
0x18002f3d6  mov     [rbx], rax
0x18002f3d9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002f3e0  mov     rax, [rcx]
0x18002f3e3  mov     rax, [rax+8]
0x18002f3e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3ec  nop
0x18002f3ed  mov     [rsp+38h+arg_0], rbx
0x18002f3f2  jmp     short loc_18002F402
0x18002f3f4  mov     rdi, [rsp+38h+arg_10]
0x18002f3f9  mov     esi, dword ptr [rsp+38h+arg_8]
0x18002f3fd  mov     rbx, [rsp+38h+arg_0]
0x18002f402  test    rbx, rbx
0x18002f405  jz      short loc_18002F43C
0x18002f407  mov     rax, [rbx]
0x18002f40a  mov     r8, rdi
0x18002f40d  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18002f414  mov     rcx, rbx
0x18002f417  mov     rax, [rax]
0x18002f41a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f41f  mov     esi, eax
0x18002f421  test    eax, eax
0x18002f423  jz      short loc_18002F43C
0x18002f425  mov     rdx, [rbx]
0x18002f428  mov     rax, [rdx+88h]
0x18002f42f  mov     edx, 1
0x18002f434  mov     rcx, rbx
0x18002f437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f43c  mov     eax, esi
0x18002f43e  add     rsp, 20h
0x18002f442  pop     rdi
0x18002f443  pop     rsi
0x18002f444  pop     rbx
0x18002f445  retn
```
