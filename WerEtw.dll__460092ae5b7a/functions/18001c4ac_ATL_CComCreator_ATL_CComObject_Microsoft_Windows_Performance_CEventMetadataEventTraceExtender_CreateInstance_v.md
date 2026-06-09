# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18001c4ac`
- end: `0x18001c57e`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800087fc`

## callees

- `0x1800018a0`
- `0x18001af8c`
- `0x18001c4ac`
- `0x18002a010`

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
0x18001c4ac  mov     [rsp+arg_10], r8
0x18001c4b1  mov     [rsp+arg_8], rdx
0x18001c4b6  mov     [rsp+arg_0], rcx
0x18001c4bb  push    rbx
0x18001c4bc  push    rsi
0x18001c4bd  push    rdi
0x18001c4be  sub     rsp, 20h
0x18001c4c2  mov     rdi, r8
0x18001c4c5  test    r8, r8
0x18001c4c8  jnz     short loc_18001C4D4
0x18001c4ca  mov     eax, 80004003h
0x18001c4cf  jmp     loc_18001C576
0x18001c4d4  mov     qword ptr [r8], 0
0x18001c4db  mov     esi, 8007000Eh
0x18001c4e0  mov     dword ptr [rsp+38h+arg_8], esi
0x18001c4e4  mov     [rsp+38h+arg_0], 0
0x18001c4ed  mov     ecx, 180h; Size
0x18001c4f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c4f7  mov     rbx, rax
0x18001c4fa  mov     [rsp+38h+arg_18], rax
0x18001c4ff  mov     rcx, rax; this
0x18001c502  call    ??0CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(void)
0x18001c507  lea     rax, ??_7?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable'
0x18001c50e  mov     [rbx], rax
0x18001c511  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001c518  mov     rax, [rcx]
0x18001c51b  mov     rax, [rax+8]
0x18001c51f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c524  nop
0x18001c525  mov     [rsp+38h+arg_0], rbx
0x18001c52a  jmp     short loc_18001C53A
0x18001c52c  mov     rdi, [rsp+38h+arg_10]
0x18001c531  mov     esi, dword ptr [rsp+38h+arg_8]
0x18001c535  mov     rbx, [rsp+38h+arg_0]
0x18001c53a  test    rbx, rbx
0x18001c53d  jz      short loc_18001C574
0x18001c53f  mov     rax, [rbx]
0x18001c542  mov     r8, rdi
0x18001c545  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18001c54c  mov     rcx, rbx
0x18001c54f  mov     rax, [rax]
0x18001c552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c557  mov     esi, eax
0x18001c559  test    eax, eax
0x18001c55b  jz      short loc_18001C574
0x18001c55d  mov     rdx, [rbx]
0x18001c560  mov     rax, [rdx+88h]
0x18001c567  mov     edx, 1
0x18001c56c  mov     rcx, rbx
0x18001c56f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c574  mov     eax, esi
0x18001c576  add     rsp, 20h
0x18001c57a  pop     rdi
0x18001c57b  pop     rsi
0x18001c57c  pop     rbx
0x18001c57d  retn
```
