# ATL::CComCreator<ATL::CComObject<CMidi2DiagnosticsTransport>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006454`
- end: `0x180006587`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMidi2DiagnosticsTransport@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006330`

## callees

- `0x180003420`
- `0x180006454`
- `0x180007418`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMidi2DiagnosticsTransport>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r15
  char *v6; // rbx
  signed __int32 v7; // eax
  int v8; // edi
  signed __int32 v9; // eax
  char *v12; // [rsp+78h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v6 = (char *)operator new(0x40u);
    *((_DWORD *)v6 + 2) = 0;
    *((_OWORD *)v6 + 1) = 0;
    *((_OWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 6) = 0;
    v6[56] = 0;
    *(_QWORD *)v6 = &ATL::CComObject<CMidi2DiagnosticsTransport>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v12 = v6;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v8 = -2147024882;
    v6 = v12;
  }
  if ( v6 )
  {
    do
      v7 = *((_DWORD *)v6 + 2);
    while ( v7 != 0x7FFFFFFF && v7 != _InterlockedCompareExchange((volatile signed __int32 *)v6 + 2, v7 + 1, v7) );
    v8 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v6 + 16));
    if ( v8 >= 0 )
    {
      v6[56] = 1;
      v8 = 0;
    }
    do
      v9 = *((_DWORD *)v6 + 2);
    while ( v9 != 0x7FFFFFFF && v9 != _InterlockedCompareExchange((volatile signed __int32 *)v6 + 2, v9 - 1, v9) );
    if ( v8 || (v8 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v6)(v6, v4, v3)) != 0 )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v6 + 32LL))(v6, 1);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006454  mov     [rsp+arg_10], r8
0x180006459  mov     [rsp+arg_8], rdx
0x18000645e  mov     [rsp+arg_0], rcx
0x180006463  push    rbx
0x180006464  push    rsi
0x180006465  push    rdi
0x180006466  push    r12
0x180006468  push    r14
0x18000646a  push    r15
0x18000646c  sub     rsp, 28h
0x180006470  mov     rsi, r8
0x180006473  mov     r15, rdx
0x180006476  test    r8, r8
0x180006479  jnz     short loc_180006485
0x18000647b  mov     eax, 80004003h
0x180006480  jmp     loc_180006579
0x180006485  mov     qword ptr [r8], 0
0x18000648c  mov     edi, 8007000Eh
0x180006491  mov     dword ptr [rsp+58h+arg_0], edi
0x180006495  mov     [rsp+58h+arg_18], 0
0x18000649e  mov     ecx, 40h ; '@'; Size
0x1800064a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800064a8  mov     rbx, rax
0x1800064ab  mov     dword ptr [rax+8], 0
0x1800064b2  xorps   xmm0, xmm0
0x1800064b5  xor     eax, eax
0x1800064b7  movups  xmmword ptr [rbx+10h], xmm0
0x1800064bb  movups  xmmword ptr [rbx+20h], xmm0
0x1800064bf  mov     [rbx+30h], rax
0x1800064c3  mov     [rbx+38h], al
0x1800064c6  lea     rax, ??_7?$CComObject@VCMidi2DiagnosticsTransport@@@ATL@@6B@; const ATL::CComObject<CMidi2DiagnosticsTransport>::`vftable'
0x1800064cd  mov     [rbx], rax
0x1800064d0  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800064d7  mov     rax, [rcx]
0x1800064da  mov     rax, [rax+8]
0x1800064de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e3  mov     [rsp+58h+arg_18], rbx
0x1800064e8  jmp     short loc_1800064FD
0x1800064ea  mov     rsi, [rsp+58h+arg_10]
0x1800064ef  mov     r15, [rsp+58h+arg_8]
0x1800064f4  mov     edi, dword ptr [rsp+58h+arg_0]
0x1800064f8  mov     rbx, [rsp+58h+arg_18]
0x1800064fd  test    rbx, rbx
0x180006500  jz      short loc_180006577
0x180006502  mov     r12d, 7FFFFFFFh
0x180006508  jmp     short loc_180006514
0x18000650a  lea     ecx, [rax+1]
0x18000650d  lock cmpxchg [rbx+8], ecx
0x180006512  jz      short loc_18000651C
0x180006514  mov     eax, [rbx+8]
0x180006517  cmp     eax, r12d
0x18000651a  jnz     short loc_18000650A
0x18000651c  lea     rcx, [rbx+10h]; this
0x180006520  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006525  mov     edi, eax
0x180006527  test    eax, eax
0x180006529  js      short loc_18000653D
0x18000652b  mov     byte ptr [rbx+38h], 1
0x18000652f  xor     edi, edi
0x180006531  jmp     short loc_18000653D
0x180006533  lea     ecx, [rax-1]
0x180006536  lock cmpxchg [rbx+8], ecx
0x18000653b  jz      short loc_180006545
0x18000653d  mov     eax, [rbx+8]
0x180006540  cmp     eax, r12d
0x180006543  jnz     short loc_180006533
0x180006545  test    edi, edi
0x180006547  jnz     short loc_180006563
0x180006549  mov     rax, [rbx]
0x18000654c  mov     r8, rsi
0x18000654f  mov     rdx, r15
0x180006552  mov     rcx, rbx
0x180006555  mov     rax, [rax]
0x180006558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000655d  mov     edi, eax
0x18000655f  test    eax, eax
0x180006561  jz      short loc_180006577
0x180006563  mov     r8, [rbx]
0x180006566  mov     edx, 1
0x18000656b  mov     rcx, rbx
0x18000656e  mov     rax, [r8+20h]
0x180006572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006577  mov     eax, edi
0x180006579  add     rsp, 28h
0x18000657d  pop     r15
0x18000657f  pop     r14
0x180006581  pop     r12
0x180006583  pop     rdi
0x180006584  pop     rsi
0x180006585  pop     rbx
0x180006586  retn
```
