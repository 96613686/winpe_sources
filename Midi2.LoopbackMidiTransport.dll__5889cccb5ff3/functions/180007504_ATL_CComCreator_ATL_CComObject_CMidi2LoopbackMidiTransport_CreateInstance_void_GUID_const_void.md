# ATL::CComCreator<ATL::CComObject<CMidi2LoopbackMidiTransport>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180007504`
- end: `0x18000763d`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMidi2LoopbackMidiTransport@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800073d0`

## callees

- `0x1800041d0`
- `0x180007504`
- `0x1800084d8`
- `0x180032010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMidi2LoopbackMidiTransport>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r12
  char *v6; // rbx
  signed __int32 v7; // eax
  int v8; // esi
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
    v6 = (char *)operator new(0x48u);
    *((_DWORD *)v6 + 2) = 0;
    *((_OWORD *)v6 + 1) = 0;
    *((_OWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 6) = 0;
    v6[56] = 0;
    *((_QWORD *)v6 + 8) = 0;
    *(_QWORD *)v6 = &ATL::CComObject<CMidi2LoopbackMidiTransport>::`vftable';
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
0x180007504  mov     [rsp+arg_10], r8
0x180007509  mov     [rsp+arg_8], rdx
0x18000750e  mov     [rsp+arg_0], rcx
0x180007513  push    rbx
0x180007514  push    rsi
0x180007515  push    r12
0x180007517  push    r13
0x180007519  push    r14
0x18000751b  push    r15
0x18000751d  sub     rsp, 28h
0x180007521  mov     r14, r8
0x180007524  mov     r12, rdx
0x180007527  test    r8, r8
0x18000752a  jnz     short loc_180007536
0x18000752c  mov     eax, 80004003h
0x180007531  jmp     loc_18000762E
0x180007536  mov     qword ptr [r8], 0
0x18000753d  mov     esi, 8007000Eh
0x180007542  mov     dword ptr [rsp+58h+arg_0], esi
0x180007546  mov     [rsp+58h+arg_18], 0
0x18000754f  mov     ecx, 48h ; 'H'; Size
0x180007554  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007559  mov     rbx, rax
0x18000755c  mov     dword ptr [rax+8], 0
0x180007563  xorps   xmm0, xmm0
0x180007566  xor     eax, eax
0x180007568  movups  xmmword ptr [rbx+10h], xmm0
0x18000756c  movups  xmmword ptr [rbx+20h], xmm0
0x180007570  mov     [rbx+30h], rax
0x180007574  mov     [rbx+38h], al
0x180007577  mov     [rbx+40h], rax
0x18000757b  lea     rax, ??_7?$CComObject@VCMidi2LoopbackMidiTransport@@@ATL@@6B@; const ATL::CComObject<CMidi2LoopbackMidiTransport>::`vftable'
0x180007582  mov     [rbx], rax
0x180007585  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000758c  mov     rax, [rcx]
0x18000758f  mov     rax, [rax+8]
0x180007593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007598  mov     [rsp+58h+arg_18], rbx
0x18000759d  jmp     short loc_1800075B2
0x18000759f  mov     r14, [rsp+58h+arg_10]
0x1800075a4  mov     r12, [rsp+58h+arg_8]
0x1800075a9  mov     esi, dword ptr [rsp+58h+arg_0]
0x1800075ad  mov     rbx, [rsp+58h+arg_18]
0x1800075b2  test    rbx, rbx
0x1800075b5  jz      short loc_18000762C
0x1800075b7  mov     r13d, 7FFFFFFFh
0x1800075bd  jmp     short loc_1800075C9
0x1800075bf  lea     ecx, [rax+1]
0x1800075c2  lock cmpxchg [rbx+8], ecx
0x1800075c7  jz      short loc_1800075D1
0x1800075c9  mov     eax, [rbx+8]
0x1800075cc  cmp     eax, r13d
0x1800075cf  jnz     short loc_1800075BF
0x1800075d1  lea     rcx, [rbx+10h]; this
0x1800075d5  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800075da  mov     esi, eax
0x1800075dc  test    eax, eax
0x1800075de  js      short loc_1800075F2
0x1800075e0  mov     byte ptr [rbx+38h], 1
0x1800075e4  xor     esi, esi
0x1800075e6  jmp     short loc_1800075F2
0x1800075e8  lea     ecx, [rax-1]
0x1800075eb  lock cmpxchg [rbx+8], ecx
0x1800075f0  jz      short loc_1800075FA
0x1800075f2  mov     eax, [rbx+8]
0x1800075f5  cmp     eax, r13d
0x1800075f8  jnz     short loc_1800075E8
0x1800075fa  test    esi, esi
0x1800075fc  jnz     short loc_180007618
0x1800075fe  mov     rax, [rbx]
0x180007601  mov     r8, r14
0x180007604  mov     rdx, r12
0x180007607  mov     rcx, rbx
0x18000760a  mov     rax, [rax]
0x18000760d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007612  mov     esi, eax
0x180007614  test    eax, eax
0x180007616  jz      short loc_18000762C
0x180007618  mov     r8, [rbx]
0x18000761b  mov     edx, 1
0x180007620  mov     rcx, rbx
0x180007623  mov     rax, [r8+20h]
0x180007627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000762c  mov     eax, esi
0x18000762e  add     rsp, 28h
0x180007632  pop     r15
0x180007634  pop     r14
0x180007636  pop     r13
0x180007638  pop     r12
0x18000763a  pop     rsi
0x18000763b  pop     rbx
0x18000763c  retn
```
