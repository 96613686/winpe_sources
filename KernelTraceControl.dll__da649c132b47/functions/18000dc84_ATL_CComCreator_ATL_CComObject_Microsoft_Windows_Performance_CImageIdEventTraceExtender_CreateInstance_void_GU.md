# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000dc84`
- end: `0x18000dd61`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000447c`

## callees

- `0x1800098d0`
- `0x18000dc84`
- `0x18002687c`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  unsigned int v5; // esi
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v6; // rax
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v7; // rbx
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v8; // [rsp+50h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v5 = -2147024882;
  try
  {
    v6 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)operator new(0x1B0u);
    v7 = v6;
    if ( v6 )
    {
      Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(v6);
      *(_QWORD *)v7 = &ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable';
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
    v5 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CImageIdEventTraceExtender *, GUID *, _QWORD *))v7)(
           v7,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v5 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CImageIdEventTraceExtender *, __int64))(*(_QWORD *)v7 + 136LL))(
        v7,
        1);
  }
  return v5;
}

```

## disassembly

```asm
0x18000dc84  mov     rax, rsp
0x18000dc87  mov     [rax+18h], r8
0x18000dc8b  mov     [rax+10h], rdx
0x18000dc8f  mov     [rax+8], rcx
0x18000dc93  push    rbx
0x18000dc94  push    rsi
0x18000dc95  push    rdi
0x18000dc96  sub     rsp, 30h
0x18000dc9a  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18000dca2  mov     rdi, r8
0x18000dca5  test    r8, r8
0x18000dca8  jnz     short loc_18000DCB4
0x18000dcaa  mov     eax, 80004003h
0x18000dcaf  jmp     loc_18000DD59
0x18000dcb4  and     qword ptr [r8], 0
0x18000dcb8  mov     esi, 8007000Eh
0x18000dcbd  mov     [rsp+48h+arg_8], esi
0x18000dcc1  and     [rsp+48h+arg_0], 0
0x18000dcc7  mov     ecx, 1B0h; Size
0x18000dccc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dcd1  mov     rbx, rax
0x18000dcd4  mov     [rsp+48h+arg_18], rax
0x18000dcd9  test    rbx, rbx
0x18000dcdc  jz      short loc_18000DD06
0x18000dcde  mov     rcx, rax; this
0x18000dce1  call    ??0CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(void)
0x18000dce6  nop
0x18000dce7  lea     rax, ??_7?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable'
0x18000dcee  mov     [rbx], rax
0x18000dcf1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000dcf8  mov     rax, [rcx]
0x18000dcfb  mov     rax, [rax+8]
0x18000dcff  call    cs:__guard_dispatch_icall_fptr
0x18000dd05  nop
0x18000dd06  mov     [rsp+48h+arg_0], rbx
0x18000dd0b  jmp     short loc_18000DD1B
0x18000dd0d  mov     rdi, [rsp+48h+arg_10]
0x18000dd12  mov     esi, [rsp+48h+arg_8]
0x18000dd16  mov     rbx, [rsp+48h+arg_0]
0x18000dd1b  test    rbx, rbx
0x18000dd1e  jz      short loc_18000DD57
0x18000dd20  mov     rax, [rbx]
0x18000dd23  mov     r8, rdi
0x18000dd26  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18000dd2d  mov     rcx, rbx
0x18000dd30  mov     rax, [rax]
0x18000dd33  call    cs:__guard_dispatch_icall_fptr
0x18000dd39  mov     esi, eax
0x18000dd3b  test    eax, eax
0x18000dd3d  jz      short loc_18000DD57
0x18000dd3f  mov     rdx, [rbx]
0x18000dd42  mov     rax, [rdx+88h]
0x18000dd49  mov     edx, 1
0x18000dd4e  mov     rcx, rbx
0x18000dd51  call    cs:__guard_dispatch_icall_fptr
0x18000dd57  mov     eax, esi
0x18000dd59  add     rsp, 30h
0x18000dd5d  pop     rdi
0x18000dd5e  pop     rsi
0x18000dd5f  pop     rbx
0x18000dd60  retn
```
