# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18002df44`
- end: `0x18002e016`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019ccc`

## callees

- `0x180001b84`
- `0x18002da58`
- `0x18002df44`
- `0x180037010`

## pseudocode

```c
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
0x18002df44  mov     [rsp+arg_10], r8
0x18002df49  mov     [rsp+arg_8], rdx
0x18002df4e  mov     [rsp+arg_0], rcx
0x18002df53  push    rbx
0x18002df54  push    rsi
0x18002df55  push    rdi
0x18002df56  sub     rsp, 20h
0x18002df5a  mov     rdi, r8
0x18002df5d  test    r8, r8
0x18002df60  jnz     short loc_18002DF6C
0x18002df62  mov     eax, 80004003h
0x18002df67  jmp     loc_18002E00E
0x18002df6c  mov     qword ptr [r8], 0
0x18002df73  mov     esi, 8007000Eh
0x18002df78  mov     dword ptr [rsp+38h+arg_8], esi
0x18002df7c  mov     [rsp+38h+arg_0], 0
0x18002df85  mov     ecx, 90h; Size
0x18002df8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002df8f  mov     rbx, rax
0x18002df92  mov     [rsp+38h+arg_18], rax
0x18002df97  mov     rcx, rax; this
0x18002df9a  call    ??0CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::CPerfTrackMetadataEventTraceExtender(void)
0x18002df9f  lea     rax, ??_7?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable'
0x18002dfa6  mov     [rbx], rax
0x18002dfa9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002dfb0  mov     rax, [rcx]
0x18002dfb3  mov     rax, [rax+8]
0x18002dfb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfbc  nop
0x18002dfbd  mov     [rsp+38h+arg_0], rbx
0x18002dfc2  jmp     short loc_18002DFD2
0x18002dfc4  mov     rdi, [rsp+38h+arg_10]
0x18002dfc9  mov     esi, dword ptr [rsp+38h+arg_8]
0x18002dfcd  mov     rbx, [rsp+38h+arg_0]
0x18002dfd2  test    rbx, rbx
0x18002dfd5  jz      short loc_18002E00C
0x18002dfd7  mov     rax, [rbx]
0x18002dfda  mov     r8, rdi
0x18002dfdd  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18002dfe4  mov     rcx, rbx
0x18002dfe7  mov     rax, [rax]
0x18002dfea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfef  mov     esi, eax
0x18002dff1  test    eax, eax
0x18002dff3  jz      short loc_18002E00C
0x18002dff5  mov     rdx, [rbx]
0x18002dff8  mov     rax, [rdx+88h]
0x18002dfff  mov     edx, 1
0x18002e004  mov     rcx, rbx
0x18002e007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e00c  mov     eax, esi
0x18002e00e  add     rsp, 20h
0x18002e012  pop     rdi
0x18002e013  pop     rsi
0x18002e014  pop     rbx
0x18002e015  retn
```
