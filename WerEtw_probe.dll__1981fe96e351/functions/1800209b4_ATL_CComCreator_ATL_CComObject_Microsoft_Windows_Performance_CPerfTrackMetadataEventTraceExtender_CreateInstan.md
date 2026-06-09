# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800209b4`
- end: `0x180020a86`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800087fc`

## callees

- `0x1800018a0`
- `0x180020508`
- `0x1800209b4`
- `0x18002a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  unsigned int (__fastcall **v5)(__int64, size_t *, int *); // rbx
  unsigned int v6; // esi
  unsigned int (__fastcall **v7)(__int64, size_t *, int *); // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = (unsigned int (__fastcall **)(__int64, size_t *, int *))operator new(0x90u);
    Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::CPerfTrackMetadataEventTraceExtender(v5);
    *v5 = (unsigned int (__fastcall *)(__int64, size_t *, int *))&ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable';
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
    v6 = (*(__int64 (__fastcall **)(_QWORD, GUID *, _QWORD *))*v5)(v5, &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33, v3);
    if ( v6 )
      (*((void (__fastcall **)(unsigned int (__fastcall **)(__int64, size_t *, int *), __int64))*v5 + 17))(v5, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x1800209b4  mov     [rsp+arg_10], r8
0x1800209b9  mov     [rsp+arg_8], rdx
0x1800209be  mov     [rsp+arg_0], rcx
0x1800209c3  push    rbx
0x1800209c4  push    rsi
0x1800209c5  push    rdi
0x1800209c6  sub     rsp, 20h
0x1800209ca  mov     rdi, r8
0x1800209cd  test    r8, r8
0x1800209d0  jnz     short loc_1800209DC
0x1800209d2  mov     eax, 80004003h
0x1800209d7  jmp     loc_180020A7E
0x1800209dc  mov     qword ptr [r8], 0
0x1800209e3  mov     esi, 8007000Eh
0x1800209e8  mov     dword ptr [rsp+38h+arg_8], esi
0x1800209ec  mov     [rsp+38h+arg_0], 0
0x1800209f5  mov     ecx, 90h; Size
0x1800209fa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800209ff  mov     rbx, rax
0x180020a02  mov     [rsp+38h+arg_18], rax
0x180020a07  mov     rcx, rax; this
0x180020a0a  call    ??0CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::CPerfTrackMetadataEventTraceExtender(void)
0x180020a0f  lea     rax, ??_7?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable'
0x180020a16  mov     [rbx], rax
0x180020a19  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180020a20  mov     rax, [rcx]
0x180020a23  mov     rax, [rax+8]
0x180020a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a2c  nop
0x180020a2d  mov     [rsp+38h+arg_0], rbx
0x180020a32  jmp     short loc_180020A42
0x180020a34  mov     rdi, [rsp+38h+arg_10]
0x180020a39  mov     esi, dword ptr [rsp+38h+arg_8]
0x180020a3d  mov     rbx, [rsp+38h+arg_0]
0x180020a42  test    rbx, rbx
0x180020a45  jz      short loc_180020A7C
0x180020a47  mov     rax, [rbx]
0x180020a4a  mov     r8, rdi
0x180020a4d  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180020a54  mov     rcx, rbx
0x180020a57  mov     rax, [rax]
0x180020a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a5f  mov     esi, eax
0x180020a61  test    eax, eax
0x180020a63  jz      short loc_180020A7C
0x180020a65  mov     rdx, [rbx]
0x180020a68  mov     rax, [rdx+88h]
0x180020a6f  mov     edx, 1
0x180020a74  mov     rcx, rbx
0x180020a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a7c  mov     eax, esi
0x180020a7e  add     rsp, 20h
0x180020a82  pop     rdi
0x180020a83  pop     rsi
0x180020a84  pop     rbx
0x180020a85  retn
```
