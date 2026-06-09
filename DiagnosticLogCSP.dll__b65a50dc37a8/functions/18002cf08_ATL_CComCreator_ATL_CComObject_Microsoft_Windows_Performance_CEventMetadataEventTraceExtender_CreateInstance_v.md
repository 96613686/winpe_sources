# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18002cf08`
- end: `0x18002cfdb`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001abb0`

## callees

- `0x180001bb4`
- `0x18002c520`
- `0x18002cf08`
- `0x180039010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18002cf08  mov     [rsp+arg_10], r8
0x18002cf0d  mov     [rsp+arg_8], rdx
0x18002cf12  mov     [rsp+arg_0], rcx
0x18002cf17  push    rbx
0x18002cf18  push    rsi
0x18002cf19  push    rdi
0x18002cf1a  sub     rsp, 20h
0x18002cf1e  mov     rdi, r8
0x18002cf21  test    r8, r8
0x18002cf24  jnz     short loc_18002CF30
0x18002cf26  mov     eax, 80004003h
0x18002cf2b  jmp     loc_18002CFD2
0x18002cf30  mov     qword ptr [r8], 0
0x18002cf37  mov     esi, 8007000Eh
0x18002cf3c  mov     dword ptr [rsp+38h+arg_8], esi
0x18002cf40  mov     [rsp+38h+arg_0], 0
0x18002cf49  mov     ecx, 180h; Size
0x18002cf4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002cf53  mov     rbx, rax
0x18002cf56  mov     [rsp+38h+arg_18], rax
0x18002cf5b  mov     rcx, rax; this
0x18002cf5e  call    ??0CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(void)
0x18002cf63  lea     rax, ??_7?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable'
0x18002cf6a  mov     [rbx], rax
0x18002cf6d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002cf74  mov     rax, [rcx]
0x18002cf77  mov     rax, [rax+8]
0x18002cf7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf80  nop
0x18002cf81  mov     [rsp+38h+arg_0], rbx
0x18002cf86  jmp     short loc_18002CF96
0x18002cf88  mov     rdi, [rsp+38h+arg_10]
0x18002cf8d  mov     esi, dword ptr [rsp+38h+arg_8]
0x18002cf91  mov     rbx, [rsp+38h+arg_0]
0x18002cf96  test    rbx, rbx
0x18002cf99  jz      short loc_18002CFD0
0x18002cf9b  mov     rax, [rbx]
0x18002cf9e  mov     r8, rdi
0x18002cfa1  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18002cfa8  mov     rcx, rbx
0x18002cfab  mov     rax, [rax]
0x18002cfae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cfb3  mov     esi, eax
0x18002cfb5  test    eax, eax
0x18002cfb7  jz      short loc_18002CFD0
0x18002cfb9  mov     rdx, [rbx]
0x18002cfbc  mov     rax, [rdx+88h]
0x18002cfc3  mov     edx, 1
0x18002cfc8  mov     rcx, rbx
0x18002cfcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cfd0  mov     eax, esi
0x18002cfd2  add     rsp, 20h
0x18002cfd6  pop     rdi
0x18002cfd7  pop     rsi
0x18002cfd8  pop     rbx
0x18002cfd9  retn
```
