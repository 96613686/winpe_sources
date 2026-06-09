# ATL::CComCreator<ATL::CComAggObject<CMidi2DiagnosticsTransport>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006344`
- end: `0x18000644c`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMidi2DiagnosticsTransport@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006330`

## callees

- `0x180003420`
- `0x180006344`
- `0x180007418`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMidi2DiagnosticsTransport>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  char *v7; // rbx
  int v8; // edi
  char *v9; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v7 = (char *)operator new(0x58u);
    *((_DWORD *)v7 + 2) = 0;
    *(_QWORD *)v7 = &ATL::CComAggObject<CMidi2DiagnosticsTransport>::`vftable';
    *(_OWORD *)(v7 + 40) = 0;
    *(_OWORD *)(v7 + 56) = 0;
    *((_QWORD *)v7 + 9) = 0;
    v7[80] = 0;
    *((_QWORD *)v7 + 3) = &ATL::CComContainedObject<CMidi2DiagnosticsTransport>::`vftable';
    *((_QWORD *)v7 + 4) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v9 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v8 = -2147024882;
    v7 = v9;
  }
  if ( v7 )
  {
    v8 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)v7 + 1);
    if ( v8 < 0 || (v7[80] = 1, (v8 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v7)(v7, v4, v3)) != 0) )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v7 + 24LL))(v7, 1);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006344  mov     [rsp+arg_10], r8
0x180006349  mov     [rsp+arg_8], rdx
0x18000634e  push    rbx
0x18000634f  push    rsi
0x180006350  push    rdi
0x180006351  push    r14
0x180006353  push    r15
0x180006355  sub     rsp, 30h
0x180006359  mov     rsi, r8
0x18000635c  mov     r14, rdx
0x18000635f  mov     r15, rcx
0x180006362  test    r8, r8
0x180006365  jnz     short loc_180006371
0x180006367  mov     eax, 80004003h
0x18000636c  jmp     loc_180006440
0x180006371  mov     qword ptr [r8], 0
0x180006378  mov     edi, 8007000Eh
0x18000637d  mov     [rsp+58h+arg_18], edi
0x180006381  mov     [rsp+58h+var_38], 0
0x18000638a  mov     ecx, 58h ; 'X'; Size
0x18000638f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006394  mov     rbx, rax
0x180006397  mov     dword ptr [rax+8], 0
0x18000639e  lea     rax, ??_7?$CComAggObject@VCMidi2DiagnosticsTransport@@@ATL@@6B@; const ATL::CComAggObject<CMidi2DiagnosticsTransport>::`vftable'
0x1800063a5  mov     [rbx], rax
0x1800063a8  xorps   xmm0, xmm0
0x1800063ab  xor     eax, eax
0x1800063ad  movups  xmmword ptr [rbx+28h], xmm0
0x1800063b1  movups  xmmword ptr [rbx+38h], xmm0
0x1800063b5  mov     [rbx+48h], rax
0x1800063b9  mov     [rbx+50h], al
0x1800063bc  lea     rax, ??_7?$CComContainedObject@VCMidi2DiagnosticsTransport@@@ATL@@6B@; const ATL::CComContainedObject<CMidi2DiagnosticsTransport>::`vftable'
0x1800063c3  mov     [rbx+18h], rax
0x1800063c7  mov     [rbx+20h], r15
0x1800063cb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800063d2  mov     rax, [rcx]
0x1800063d5  mov     rax, [rax+8]
0x1800063d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063de  mov     [rsp+58h+var_38], rbx
0x1800063e3  jmp     short loc_1800063F8
0x1800063e5  mov     rsi, [rsp+58h+arg_10]
0x1800063ea  mov     r14, [rsp+58h+arg_8]
0x1800063ef  mov     edi, [rsp+58h+arg_18]
0x1800063f3  mov     rbx, [rsp+58h+var_38]
0x1800063f8  test    rbx, rbx
0x1800063fb  jz      short loc_18000643E
0x1800063fd  lea     rcx, [rbx+28h]; this
0x180006401  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006406  mov     edi, eax
0x180006408  test    eax, eax
0x18000640a  js      short loc_18000642A
0x18000640c  mov     byte ptr [rbx+50h], 1
0x180006410  mov     rax, [rbx]
0x180006413  mov     r8, rsi
0x180006416  mov     rdx, r14
0x180006419  mov     rcx, rbx
0x18000641c  mov     rax, [rax]
0x18000641f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006424  mov     edi, eax
0x180006426  test    eax, eax
0x180006428  jz      short loc_18000643E
0x18000642a  mov     rax, [rbx]
0x18000642d  mov     edx, 1
0x180006432  mov     rcx, rbx
0x180006435  mov     rax, [rax+18h]
0x180006439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000643e  mov     eax, edi
0x180006440  add     rsp, 30h
0x180006444  pop     r15
0x180006446  pop     r14
0x180006448  pop     rdi
0x180006449  pop     rsi
0x18000644a  pop     rbx
0x18000644b  retn
```
