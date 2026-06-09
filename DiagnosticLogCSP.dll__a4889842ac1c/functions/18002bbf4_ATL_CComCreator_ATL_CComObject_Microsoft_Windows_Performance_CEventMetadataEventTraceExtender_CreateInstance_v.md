# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18002bbf4`
- end: `0x18002bcc6`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019ccc`

## callees

- `0x180001b84`
- `0x18002b24c`
- `0x18002bbf4`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *v5; // rbx
  unsigned int v6; // esi
  Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = (Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *)operator new(0x180u);
    Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(v5);
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable';
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
    v6 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *, __int64))(*(_QWORD *)v5 + 136LL))(
        v5,
        1);
  }
  return v6;
}

```

## disassembly

```asm
0x18002bbf4  mov     [rsp+arg_10], r8
0x18002bbf9  mov     [rsp+arg_8], rdx
0x18002bbfe  mov     [rsp+arg_0], rcx
0x18002bc03  push    rbx
0x18002bc04  push    rsi
0x18002bc05  push    rdi
0x18002bc06  sub     rsp, 20h
0x18002bc0a  mov     rdi, r8
0x18002bc0d  test    r8, r8
0x18002bc10  jnz     short loc_18002BC1C
0x18002bc12  mov     eax, 80004003h
0x18002bc17  jmp     loc_18002BCBE
0x18002bc1c  mov     qword ptr [r8], 0
0x18002bc23  mov     esi, 8007000Eh
0x18002bc28  mov     dword ptr [rsp+38h+arg_8], esi
0x18002bc2c  mov     [rsp+38h+arg_0], 0
0x18002bc35  mov     ecx, 180h; Size
0x18002bc3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bc3f  mov     rbx, rax
0x18002bc42  mov     [rsp+38h+arg_18], rax
0x18002bc47  mov     rcx, rax; this
0x18002bc4a  call    ??0CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(void)
0x18002bc4f  lea     rax, ??_7?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable'
0x18002bc56  mov     [rbx], rax
0x18002bc59  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002bc60  mov     rax, [rcx]
0x18002bc63  mov     rax, [rax+8]
0x18002bc67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc6c  nop
0x18002bc6d  mov     [rsp+38h+arg_0], rbx
0x18002bc72  jmp     short loc_18002BC82
0x18002bc74  mov     rdi, [rsp+38h+arg_10]
0x18002bc79  mov     esi, dword ptr [rsp+38h+arg_8]
0x18002bc7d  mov     rbx, [rsp+38h+arg_0]
0x18002bc82  test    rbx, rbx
0x18002bc85  jz      short loc_18002BCBC
0x18002bc87  mov     rax, [rbx]
0x18002bc8a  mov     r8, rdi
0x18002bc8d  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18002bc94  mov     rcx, rbx
0x18002bc97  mov     rax, [rax]
0x18002bc9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc9f  mov     esi, eax
0x18002bca1  test    eax, eax
0x18002bca3  jz      short loc_18002BCBC
0x18002bca5  mov     rdx, [rbx]
0x18002bca8  mov     rax, [rdx+88h]
0x18002bcaf  mov     edx, 1
0x18002bcb4  mov     rcx, rbx
0x18002bcb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcbc  mov     eax, esi
0x18002bcbe  add     rsp, 20h
0x18002bcc2  pop     rdi
0x18002bcc3  pop     rsi
0x18002bcc4  pop     rbx
0x18002bcc5  retn
```
