# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180019690`
- end: `0x18001976d`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000447c`

## callees

- `0x180017710`
- `0x180019690`
- `0x18002687c`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  unsigned int v5; // esi
  Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *v6; // rax
  Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *v7; // rbx
  Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *v8; // [rsp+50h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v5 = -2147024882;
  try
  {
    v6 = (Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *)operator new(0x190u);
    v7 = v6;
    if ( v6 )
    {
      Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(v6);
      *(_QWORD *)v7 = &ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable';
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
    v5 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *, GUID *, _QWORD *))v7)(
           v7,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v5 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *, __int64))(*(_QWORD *)v7 + 136LL))(
        v7,
        1);
  }
  return v5;
}

```

## disassembly

```asm
0x180019690  mov     rax, rsp
0x180019693  mov     [rax+18h], r8
0x180019697  mov     [rax+10h], rdx
0x18001969b  mov     [rax+8], rcx
0x18001969f  push    rbx
0x1800196a0  push    rsi
0x1800196a1  push    rdi
0x1800196a2  sub     rsp, 30h
0x1800196a6  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1800196ae  mov     rdi, r8
0x1800196b1  test    r8, r8
0x1800196b4  jnz     short loc_1800196C0
0x1800196b6  mov     eax, 80004003h
0x1800196bb  jmp     loc_180019765
0x1800196c0  and     qword ptr [r8], 0
0x1800196c4  mov     esi, 8007000Eh
0x1800196c9  mov     [rsp+48h+arg_8], esi
0x1800196cd  and     [rsp+48h+arg_0], 0
0x1800196d3  mov     ecx, 190h; Size
0x1800196d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800196dd  mov     rbx, rax
0x1800196e0  mov     [rsp+48h+arg_18], rax
0x1800196e5  test    rbx, rbx
0x1800196e8  jz      short loc_180019712
0x1800196ea  mov     rcx, rax; this
0x1800196ed  call    ??0CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(void)
0x1800196f2  nop
0x1800196f3  lea     rax, ??_7?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable'
0x1800196fa  mov     [rbx], rax
0x1800196fd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180019704  mov     rax, [rcx]
0x180019707  mov     rax, [rax+8]
0x18001970b  call    cs:__guard_dispatch_icall_fptr
0x180019711  nop
0x180019712  mov     [rsp+48h+arg_0], rbx
0x180019717  jmp     short loc_180019727
0x180019719  mov     rdi, [rsp+48h+arg_10]
0x18001971e  mov     esi, [rsp+48h+arg_8]
0x180019722  mov     rbx, [rsp+48h+arg_0]
0x180019727  test    rbx, rbx
0x18001972a  jz      short loc_180019763
0x18001972c  mov     rax, [rbx]
0x18001972f  mov     r8, rdi
0x180019732  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180019739  mov     rcx, rbx
0x18001973c  mov     rax, [rax]
0x18001973f  call    cs:__guard_dispatch_icall_fptr
0x180019745  mov     esi, eax
0x180019747  test    eax, eax
0x180019749  jz      short loc_180019763
0x18001974b  mov     rdx, [rbx]
0x18001974e  mov     rax, [rdx+88h]
0x180019755  mov     edx, 1
0x18001975a  mov     rcx, rbx
0x18001975d  call    cs:__guard_dispatch_icall_fptr
0x180019763  mov     eax, esi
0x180019765  add     rsp, 30h
0x180019769  pop     rdi
0x18001976a  pop     rsi
0x18001976b  pop     rbx
0x18001976c  retn
```
