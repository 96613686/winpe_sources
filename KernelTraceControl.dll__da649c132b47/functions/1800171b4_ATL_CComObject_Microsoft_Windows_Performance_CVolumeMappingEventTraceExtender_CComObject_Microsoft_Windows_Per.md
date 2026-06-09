# ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>(void)

- ea: `0x1800171b4`
- end: `0x18001722b`
- name: `??1?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017230`

## callees

- `0x1800134a8`
- `0x1800171b4`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>(
        __int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable';
  *(_DWORD *)(a1 + 24) = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::~CNtImagePathDecoderBase((void **)(a1 + 32));
  v2 = *(_QWORD *)(a1 + 16);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *(_QWORD *)(a1 + 8);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
}

```

## disassembly

```asm
0x1800171b4  mov     [rsp+arg_0], rcx
0x1800171b9  push    rbx
0x1800171ba  sub     rsp, 30h
0x1800171be  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800171c7  mov     rbx, rcx
0x1800171ca  lea     rax, ??_7?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable'
0x1800171d1  mov     [rcx], rax
0x1800171d4  mov     dword ptr [rcx+18h], 0C0000001h
0x1800171db  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800171e2  mov     rax, [rcx]
0x1800171e5  mov     rax, [rax+10h]
0x1800171e9  call    cs:__guard_dispatch_icall_fptr
0x1800171ef  nop
0x1800171f0  lea     rcx, [rbx+20h]; this
0x1800171f4  call    ??1CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAA@XZ; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::~CNtImagePathDecoderBase(void)
0x1800171f9  mov     rcx, [rbx+10h]
0x1800171fd  test    rcx, rcx
0x180017200  jz      short loc_18001720F
0x180017202  mov     rax, [rcx]
0x180017205  mov     rax, [rax+10h]
0x180017209  call    cs:__guard_dispatch_icall_fptr
0x18001720f  mov     rcx, [rbx+8]
0x180017213  test    rcx, rcx
0x180017216  jz      short loc_180017225
0x180017218  mov     rax, [rcx]
0x18001721b  mov     rax, [rax+10h]
0x18001721f  call    cs:__guard_dispatch_icall_fptr
0x180017225  add     rsp, 30h
0x180017229  pop     rbx
0x18001722a  retn
```
