# ATL::CComCreator<ATL::CComAggObject<CMidi2LoopbackMidiTransport>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800073e4`
- end: `0x1800074fe`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMidi2LoopbackMidiTransport@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800073d0`

## callees

- `0x1800041d0`
- `0x1800073e4`
- `0x1800084d8`
- `0x180032010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMidi2LoopbackMidiTransport>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  char *v7; // rbx
  int v8; // esi
  char *v9; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v7 = (char *)operator new(0x60u);
    *((_DWORD *)v7 + 2) = 0;
    *(_QWORD *)v7 = &ATL::CComAggObject<CMidi2LoopbackMidiTransport>::`vftable';
    *(_OWORD *)(v7 + 40) = 0;
    *(_OWORD *)(v7 + 56) = 0;
    *((_QWORD *)v7 + 9) = 0;
    v7[80] = 0;
    *((_QWORD *)v7 + 11) = 0;
    *((_QWORD *)v7 + 3) = &ATL::CComContainedObject<CMidi2LoopbackMidiTransport>::`vftable';
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
0x1800073e4  mov     [rsp+arg_0], rbx
0x1800073e9  mov     [rsp+arg_10], r8
0x1800073ee  mov     [rsp+arg_8], rdx
0x1800073f3  push    rsi
0x1800073f4  push    r12
0x1800073f6  push    r13
0x1800073f8  push    r14
0x1800073fa  push    r15
0x1800073fc  sub     rsp, 30h
0x180007400  mov     r14, r8
0x180007403  mov     r15, rdx
0x180007406  mov     r12, rcx
0x180007409  test    r8, r8
0x18000740c  jnz     short loc_180007418
0x18000740e  mov     eax, 80004003h
0x180007413  jmp     loc_1800074EB
0x180007418  mov     qword ptr [r8], 0
0x18000741f  mov     esi, 8007000Eh
0x180007424  mov     [rsp+58h+arg_18], esi
0x180007428  mov     [rsp+58h+var_38], 0
0x180007431  mov     ecx, 60h ; '`'; Size
0x180007436  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000743b  mov     rbx, rax
0x18000743e  mov     dword ptr [rax+8], 0
0x180007445  lea     rax, ??_7?$CComAggObject@VCMidi2LoopbackMidiTransport@@@ATL@@6B@; const ATL::CComAggObject<CMidi2LoopbackMidiTransport>::`vftable'
0x18000744c  mov     [rbx], rax
0x18000744f  xorps   xmm0, xmm0
0x180007452  xor     eax, eax
0x180007454  movups  xmmword ptr [rbx+28h], xmm0
0x180007458  movups  xmmword ptr [rbx+38h], xmm0
0x18000745c  mov     [rbx+48h], rax
0x180007460  mov     [rbx+50h], al
0x180007463  mov     [rbx+58h], rax
0x180007467  lea     rax, ??_7?$CComContainedObject@VCMidi2LoopbackMidiTransport@@@ATL@@6B@; const ATL::CComContainedObject<CMidi2LoopbackMidiTransport>::`vftable'
0x18000746e  mov     [rbx+18h], rax
0x180007472  mov     [rbx+20h], r12
0x180007476  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000747d  mov     rax, [rcx]
0x180007480  mov     rax, [rax+8]
0x180007484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007489  mov     [rsp+58h+var_38], rbx
0x18000748e  jmp     short loc_1800074A3
0x180007490  mov     r14, [rsp+58h+arg_10]
0x180007495  mov     r15, [rsp+58h+arg_8]
0x18000749a  mov     esi, [rsp+58h+arg_18]
0x18000749e  mov     rbx, [rsp+58h+var_38]
0x1800074a3  test    rbx, rbx
0x1800074a6  jz      short loc_1800074E9
0x1800074a8  lea     rcx, [rbx+28h]; this
0x1800074ac  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800074b1  mov     esi, eax
0x1800074b3  test    eax, eax
0x1800074b5  js      short loc_1800074D5
0x1800074b7  mov     byte ptr [rbx+50h], 1
0x1800074bb  mov     rax, [rbx]
0x1800074be  mov     r8, r14
0x1800074c1  mov     rdx, r15
0x1800074c4  mov     rcx, rbx
0x1800074c7  mov     rax, [rax]
0x1800074ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074cf  mov     esi, eax
0x1800074d1  test    eax, eax
0x1800074d3  jz      short loc_1800074E9
0x1800074d5  mov     rax, [rbx]
0x1800074d8  mov     edx, 1
0x1800074dd  mov     rcx, rbx
0x1800074e0  mov     rax, [rax+18h]
0x1800074e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074e9  mov     eax, esi
0x1800074eb  mov     rbx, [rsp+58h+arg_0]
0x1800074f0  add     rsp, 30h
0x1800074f4  pop     r15
0x1800074f6  pop     r14
0x1800074f8  pop     r13
0x1800074fa  pop     r12
0x1800074fc  pop     rsi
0x1800074fd  retn
```
