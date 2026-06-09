# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180017074`
- end: `0x1800171b1`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `317`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000447c`

## callees

- `0x180017074`
- `0x18002687c`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  unsigned int v5; // r14d
  _DWORD *v6; // rax
  _DWORD *v7; // rdi
  _DWORD *v8; // [rsp+60h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v5 = -2147024882;
  try
  {
    v6 = operator new(0xD0u);
    v7 = v6;
    if ( v6 )
    {
      v6[6] = 0;
      *((_QWORD *)v6 + 1) = 0;
      *((_QWORD *)v6 + 2) = 0;
      *((_QWORD *)v6 + 5) = 0;
      *((_QWORD *)v6 + 6) = 0;
      *((_QWORD *)v6 + 7) = 0;
      *((_QWORD *)v6 + 9) = 0;
      *((_QWORD *)v6 + 10) = 0;
      *((_QWORD *)v6 + 11) = 0;
      *((_QWORD *)v6 + 16) = 7;
      *((_QWORD *)v6 + 15) = 0;
      *((_WORD *)v6 + 52) = 0;
      *((_QWORD *)v6 + 21) = 7;
      *((_QWORD *)v6 + 20) = 0;
      *((_WORD *)v6 + 72) = 0;
      *((_BYTE *)v6 + 176) = 0;
      *((_BYTE *)v6 + 184) = 0;
      *(_QWORD *)v6 = &ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v7 = 0;
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
0x180017074  mov     rax, rsp
0x180017077  mov     [rax+18h], r8
0x18001707b  mov     [rax+10h], rdx
0x18001707f  mov     [rax+8], rcx
0x180017083  push    rbx
0x180017084  push    rsi
0x180017085  push    rdi
0x180017086  push    r14
0x180017088  sub     rsp, 38h
0x18001708c  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180017094  mov     rsi, r8
0x180017097  xor     ebx, ebx
0x180017099  test    r8, r8
0x18001709c  jnz     short loc_1800170A8
0x18001709e  mov     eax, 80004003h
0x1800170a3  jmp     loc_1800171A7
0x1800170a8  mov     [r8], rbx
0x1800170ab  mov     r14d, 8007000Eh
0x1800170b1  mov     [rsp+58h+arg_8], r14d
0x1800170b6  mov     [rsp+58h+arg_0], rbx
0x1800170bb  mov     ecx, 0D0h; Size
0x1800170c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800170c5  mov     rdi, rax
0x1800170c8  mov     [rsp+58h+arg_18], rax
0x1800170cd  test    rax, rax
0x1800170d0  jz      short loc_18001714E
0x1800170d2  mov     [rax+18h], ebx
0x1800170d5  mov     [rax+8], rbx
0x1800170d9  mov     [rax+10h], rbx
0x1800170dd  add     rax, 20h ; ' '
0x1800170e1  mov     [rsp+58h+var_30], rax
0x1800170e6  mov     [rax+8], rbx
0x1800170ea  mov     [rax+10h], rbx
0x1800170ee  mov     [rax+18h], rbx
0x1800170f2  mov     [rax+28h], rbx
0x1800170f6  mov     [rax+30h], rbx
0x1800170fa  mov     [rax+38h], rbx
0x1800170fe  mov     ecx, 7
0x180017103  mov     [rax+60h], rcx
0x180017107  mov     [rax+58h], rbx
0x18001710b  mov     [rax+48h], bx
0x18001710f  mov     [rax+88h], rcx
0x180017116  mov     [rax+80h], rbx
0x18001711d  mov     [rax+70h], bx
0x180017121  mov     [rax+90h], bl
0x180017127  mov     [rdi+0B8h], bl
0x18001712d  lea     rax, ??_7?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable'
0x180017134  mov     [rdi], rax
0x180017137  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001713e  mov     rax, [rcx]
0x180017141  mov     rax, [rax+8]
0x180017145  call    cs:__guard_dispatch_icall_fptr
0x18001714b  nop
0x18001714c  jmp     short loc_180017151
0x18001714e  mov     rdi, rbx
0x180017151  mov     [rsp+58h+arg_0], rdi
0x180017156  jmp     short loc_180017167
0x180017158  mov     rsi, [rsp+58h+arg_10]
0x18001715d  mov     r14d, [rsp+58h+arg_8]
0x180017162  mov     rdi, [rsp+58h+arg_0]
0x180017167  test    rdi, rdi
0x18001716a  jz      short loc_1800171A4
0x18001716c  mov     rax, [rdi]
0x18001716f  mov     r8, rsi
0x180017172  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180017179  mov     rcx, rdi
0x18001717c  mov     rax, [rax]
0x18001717f  call    cs:__guard_dispatch_icall_fptr
0x180017185  mov     r14d, eax
0x180017188  test    eax, eax
0x18001718a  jz      short loc_1800171A4
0x18001718c  mov     rdx, [rdi]
0x18001718f  mov     rax, [rdx+88h]
0x180017196  mov     edx, 1
0x18001719b  mov     rcx, rdi
0x18001719e  call    cs:__guard_dispatch_icall_fptr
0x1800171a4  mov     eax, r14d
0x1800171a7  add     rsp, 38h
0x1800171ab  pop     r14
0x1800171ad  pop     rdi
0x1800171ae  pop     rsi
0x1800171af  pop     rbx
0x1800171b0  retn
```
