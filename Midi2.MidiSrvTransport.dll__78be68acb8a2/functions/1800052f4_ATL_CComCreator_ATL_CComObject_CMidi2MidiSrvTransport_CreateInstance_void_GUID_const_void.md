# ATL::CComCreator<ATL::CComObject<CMidi2MidiSrvTransport>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800052f4`
- end: `0x180005427`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMidi2MidiSrvTransport@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800051d0`

## callees

- `0x1800024c0`
- `0x1800052f4`
- `0x1800062c0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMidi2MidiSrvTransport>>::CreateInstance(
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
    *(_QWORD *)v6 = &ATL::CComObject<CMidi2MidiSrvTransport>::`vftable';
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
0x1800052f4  mov     [rsp+arg_10], r8
0x1800052f9  mov     [rsp+arg_8], rdx
0x1800052fe  mov     [rsp+arg_0], rcx
0x180005303  push    rbx
0x180005304  push    rsi
0x180005305  push    rdi
0x180005306  push    r12
0x180005308  push    r14
0x18000530a  push    r15
0x18000530c  sub     rsp, 28h
0x180005310  mov     rsi, r8
0x180005313  mov     r15, rdx
0x180005316  test    r8, r8
0x180005319  jnz     short loc_180005325
0x18000531b  mov     eax, 80004003h
0x180005320  jmp     loc_180005419
0x180005325  mov     qword ptr [r8], 0
0x18000532c  mov     edi, 8007000Eh
0x180005331  mov     dword ptr [rsp+58h+arg_0], edi
0x180005335  mov     [rsp+58h+arg_18], 0
0x18000533e  mov     ecx, 40h ; '@'; Size
0x180005343  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005348  mov     rbx, rax
0x18000534b  mov     dword ptr [rax+8], 0
0x180005352  xorps   xmm0, xmm0
0x180005355  xor     eax, eax
0x180005357  movups  xmmword ptr [rbx+10h], xmm0
0x18000535b  movups  xmmword ptr [rbx+20h], xmm0
0x18000535f  mov     [rbx+30h], rax
0x180005363  mov     [rbx+38h], al
0x180005366  lea     rax, ??_7?$CComObject@VCMidi2MidiSrvTransport@@@ATL@@6B@; const ATL::CComObject<CMidi2MidiSrvTransport>::`vftable'
0x18000536d  mov     [rbx], rax
0x180005370  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005377  mov     rax, [rcx]
0x18000537a  mov     rax, [rax+8]
0x18000537e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005383  mov     [rsp+58h+arg_18], rbx
0x180005388  jmp     short loc_18000539D
0x18000538a  mov     rsi, [rsp+58h+arg_10]
0x18000538f  mov     r15, [rsp+58h+arg_8]
0x180005394  mov     edi, dword ptr [rsp+58h+arg_0]
0x180005398  mov     rbx, [rsp+58h+arg_18]
0x18000539d  test    rbx, rbx
0x1800053a0  jz      short loc_180005417
0x1800053a2  mov     r12d, 7FFFFFFFh
0x1800053a8  jmp     short loc_1800053B4
0x1800053aa  lea     ecx, [rax+1]
0x1800053ad  lock cmpxchg [rbx+8], ecx
0x1800053b2  jz      short loc_1800053BC
0x1800053b4  mov     eax, [rbx+8]
0x1800053b7  cmp     eax, r12d
0x1800053ba  jnz     short loc_1800053AA
0x1800053bc  lea     rcx, [rbx+10h]; this
0x1800053c0  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800053c5  mov     edi, eax
0x1800053c7  test    eax, eax
0x1800053c9  js      short loc_1800053DD
0x1800053cb  mov     byte ptr [rbx+38h], 1
0x1800053cf  xor     edi, edi
0x1800053d1  jmp     short loc_1800053DD
0x1800053d3  lea     ecx, [rax-1]
0x1800053d6  lock cmpxchg [rbx+8], ecx
0x1800053db  jz      short loc_1800053E5
0x1800053dd  mov     eax, [rbx+8]
0x1800053e0  cmp     eax, r12d
0x1800053e3  jnz     short loc_1800053D3
0x1800053e5  test    edi, edi
0x1800053e7  jnz     short loc_180005403
0x1800053e9  mov     rax, [rbx]
0x1800053ec  mov     r8, rsi
0x1800053ef  mov     rdx, r15
0x1800053f2  mov     rcx, rbx
0x1800053f5  mov     rax, [rax]
0x1800053f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053fd  mov     edi, eax
0x1800053ff  test    eax, eax
0x180005401  jz      short loc_180005417
0x180005403  mov     r8, [rbx]
0x180005406  mov     edx, 1
0x18000540b  mov     rcx, rbx
0x18000540e  mov     rax, [r8+20h]
0x180005412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005417  mov     eax, edi
0x180005419  add     rsp, 28h
0x18000541d  pop     r15
0x18000541f  pop     r14
0x180005421  pop     r12
0x180005423  pop     rdi
0x180005424  pop     rsi
0x180005425  pop     rbx
0x180005426  retn
```
