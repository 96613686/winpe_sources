# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18001dab4`
- end: `0x18001db91`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000447c`

## callees

- `0x18001c3dc`
- `0x18001dab4`
- `0x18002687c`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  unsigned int v5; // esi
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v6; // rax
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v7; // rbx
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v8; // [rsp+50h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v5 = -2147024882;
  try
  {
    v6 = (Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *)operator new(0xA8u);
    v7 = v6;
    if ( v6 )
    {
      Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::CPerfTrackMetadataEventTraceExtender(v6);
      *(_QWORD *)v7 = &ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v8 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v5 = -2147024882;
    v7 = v8;
  }
  if ( v7 )
  {
    v5 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *, GUID *, _QWORD *))v7)(
           v7,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v5 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *, __int64))(*(_QWORD *)v7 + 136LL))(
        v7,
        1);
  }
  return v5;
}

```

## disassembly

```asm
0x18001dab4  mov     rax, rsp
0x18001dab7  mov     [rax+18h], r8
0x18001dabb  mov     [rax+10h], rdx
0x18001dabf  mov     [rax+8], rcx
0x18001dac3  push    rbx
0x18001dac4  push    rsi
0x18001dac5  push    rdi
0x18001dac6  sub     rsp, 30h
0x18001daca  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18001dad2  mov     rdi, r8
0x18001dad5  test    r8, r8
0x18001dad8  jnz     short loc_18001DAE4
0x18001dada  mov     eax, 80004003h
0x18001dadf  jmp     loc_18001DB89
0x18001dae4  and     qword ptr [r8], 0
0x18001dae8  mov     esi, 8007000Eh
0x18001daed  mov     [rsp+48h+arg_8], esi
0x18001daf1  and     [rsp+48h+arg_0], 0
0x18001daf7  mov     ecx, 0A8h; Size
0x18001dafc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001db01  mov     rbx, rax
0x18001db04  mov     [rsp+48h+arg_18], rax
0x18001db09  test    rbx, rbx
0x18001db0c  jz      short loc_18001DB36
0x18001db0e  mov     rcx, rax; this
0x18001db11  call    ??0CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::CPerfTrackMetadataEventTraceExtender(void)
0x18001db16  nop
0x18001db17  lea     rax, ??_7?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable'
0x18001db1e  mov     [rbx], rax
0x18001db21  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001db28  mov     rax, [rcx]
0x18001db2b  mov     rax, [rax+8]
0x18001db2f  call    cs:__guard_dispatch_icall_fptr
0x18001db35  nop
0x18001db36  mov     [rsp+48h+arg_0], rbx
0x18001db3b  jmp     short loc_18001DB4B
0x18001db3d  mov     rdi, [rsp+48h+arg_10]
0x18001db42  mov     esi, [rsp+48h+arg_8]
0x18001db46  mov     rbx, [rsp+48h+arg_0]
0x18001db4b  test    rbx, rbx
0x18001db4e  jz      short loc_18001DB87
0x18001db50  mov     rax, [rbx]
0x18001db53  mov     r8, rdi
0x18001db56  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18001db5d  mov     rcx, rbx
0x18001db60  mov     rax, [rax]
0x18001db63  call    cs:__guard_dispatch_icall_fptr
0x18001db69  mov     esi, eax
0x18001db6b  test    eax, eax
0x18001db6d  jz      short loc_18001DB87
0x18001db6f  mov     rdx, [rbx]
0x18001db72  mov     rax, [rdx+88h]
0x18001db79  mov     edx, 1
0x18001db7e  mov     rcx, rbx
0x18001db81  call    cs:__guard_dispatch_icall_fptr
0x18001db87  mov     eax, esi
0x18001db89  add     rsp, 30h
0x18001db8d  pop     rdi
0x18001db8e  pop     rsi
0x18001db8f  pop     rbx
0x18001db90  retn
```
