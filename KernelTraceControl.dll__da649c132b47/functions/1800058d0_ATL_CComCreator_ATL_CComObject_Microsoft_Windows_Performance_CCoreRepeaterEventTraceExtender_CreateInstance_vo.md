# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800058d0`
- end: `0x1800059b9`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `233`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000447c`

## callees

- `0x1800058d0`
- `0x18002687c`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  unsigned int v5; // r14d
  _DWORD *v6; // rax
  _DWORD *v7; // rbx
  _DWORD *v8; // [rsp+50h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v5 = -2147024882;
  try
  {
    v6 = operator new(0x20u);
    v7 = v6;
    if ( v6 )
    {
      v6[6] = 0;
      *((_QWORD *)v6 + 1) = 0;
      *((_QWORD *)v6 + 2) = 0;
      *(_QWORD *)v6 = &ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable';
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
    v5 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, _QWORD *))v7)(
           v7,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v5 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 136LL))(v7, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x1800058d0  mov     rax, rsp
0x1800058d3  mov     [rax+18h], r8
0x1800058d7  mov     [rax+10h], rdx
0x1800058db  mov     [rax+8], rcx
0x1800058df  push    rbx
0x1800058e0  push    rsi
0x1800058e1  push    r14
0x1800058e3  sub     rsp, 30h
0x1800058e7  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1800058ef  mov     rsi, r8
0x1800058f2  test    r8, r8
0x1800058f5  jnz     short loc_180005901
0x1800058f7  mov     eax, 80004003h
0x1800058fc  jmp     loc_1800059B0
0x180005901  and     qword ptr [r8], 0
0x180005905  mov     r14d, 8007000Eh
0x18000590b  mov     [rsp+48h+arg_8], r14d
0x180005910  and     [rsp+48h+arg_0], 0
0x180005916  mov     ecx, 20h ; ' '; Size
0x18000591b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005920  mov     rbx, rax
0x180005923  mov     [rsp+48h+arg_18], rax
0x180005928  test    rbx, rbx
0x18000592b  jz      short loc_18000595A
0x18000592d  and     dword ptr [rax+18h], 0
0x180005931  and     qword ptr [rax+8], 0
0x180005936  and     qword ptr [rax+10h], 0
0x18000593b  lea     rax, ??_7?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable'
0x180005942  mov     [rbx], rax
0x180005945  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000594c  mov     rax, [rcx]
0x18000594f  mov     rax, [rax+8]
0x180005953  call    cs:__guard_dispatch_icall_fptr
0x180005959  nop
0x18000595a  mov     [rsp+48h+arg_0], rbx
0x18000595f  jmp     short loc_180005970
0x180005961  mov     rsi, [rsp+48h+arg_10]
0x180005966  mov     r14d, [rsp+48h+arg_8]
0x18000596b  mov     rbx, [rsp+48h+arg_0]
0x180005970  test    rbx, rbx
0x180005973  jz      short loc_1800059AD
0x180005975  mov     rax, [rbx]
0x180005978  mov     r8, rsi
0x18000597b  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180005982  mov     rcx, rbx
0x180005985  mov     rax, [rax]
0x180005988  call    cs:__guard_dispatch_icall_fptr
0x18000598e  mov     r14d, eax
0x180005991  test    eax, eax
0x180005993  jz      short loc_1800059AD
0x180005995  mov     rdx, [rbx]
0x180005998  mov     rax, [rdx+88h]
0x18000599f  mov     edx, 1
0x1800059a4  mov     rcx, rbx
0x1800059a7  call    cs:__guard_dispatch_icall_fptr
0x1800059ad  mov     eax, r14d
0x1800059b0  add     rsp, 30h
0x1800059b4  pop     r14
0x1800059b6  pop     rsi
0x1800059b7  pop     rbx
0x1800059b8  retn
```
