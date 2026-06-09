# ATL::CComCreator<ATL::CComObject<CMidi2VirtualMidiTransport>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006ae4`
- end: `0x180006c17`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMidi2VirtualMidiTransport@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800069c0`

## callees

- `0x180003940`
- `0x180006ae4`
- `0x180007aa8`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMidi2VirtualMidiTransport>>::CreateInstance(
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
    *(_QWORD *)v6 = &ATL::CComObject<CMidi2VirtualMidiTransport>::`vftable';
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
0x180006ae4  mov     [rsp+arg_10], r8
0x180006ae9  mov     [rsp+arg_8], rdx
0x180006aee  mov     [rsp+arg_0], rcx
0x180006af3  push    rbx
0x180006af4  push    rsi
0x180006af5  push    rdi
0x180006af6  push    r12
0x180006af8  push    r14
0x180006afa  push    r15
0x180006afc  sub     rsp, 28h
0x180006b00  mov     rsi, r8
0x180006b03  mov     r15, rdx
0x180006b06  test    r8, r8
0x180006b09  jnz     short loc_180006B15
0x180006b0b  mov     eax, 80004003h
0x180006b10  jmp     loc_180006C09
0x180006b15  mov     qword ptr [r8], 0
0x180006b1c  mov     edi, 8007000Eh
0x180006b21  mov     dword ptr [rsp+58h+arg_0], edi
0x180006b25  mov     [rsp+58h+arg_18], 0
0x180006b2e  mov     ecx, 40h ; '@'; Size
0x180006b33  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006b38  mov     rbx, rax
0x180006b3b  mov     dword ptr [rax+8], 0
0x180006b42  xorps   xmm0, xmm0
0x180006b45  xor     eax, eax
0x180006b47  movups  xmmword ptr [rbx+10h], xmm0
0x180006b4b  movups  xmmword ptr [rbx+20h], xmm0
0x180006b4f  mov     [rbx+30h], rax
0x180006b53  mov     [rbx+38h], al
0x180006b56  lea     rax, ??_7?$CComObject@VCMidi2VirtualMidiTransport@@@ATL@@6B@; const ATL::CComObject<CMidi2VirtualMidiTransport>::`vftable'
0x180006b5d  mov     [rbx], rax
0x180006b60  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006b67  mov     rax, [rcx]
0x180006b6a  mov     rax, [rax+8]
0x180006b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b73  mov     [rsp+58h+arg_18], rbx
0x180006b78  jmp     short loc_180006B8D
0x180006b7a  mov     rsi, [rsp+58h+arg_10]
0x180006b7f  mov     r15, [rsp+58h+arg_8]
0x180006b84  mov     edi, dword ptr [rsp+58h+arg_0]
0x180006b88  mov     rbx, [rsp+58h+arg_18]
0x180006b8d  test    rbx, rbx
0x180006b90  jz      short loc_180006C07
0x180006b92  mov     r12d, 7FFFFFFFh
0x180006b98  jmp     short loc_180006BA4
0x180006b9a  lea     ecx, [rax+1]
0x180006b9d  lock cmpxchg [rbx+8], ecx
0x180006ba2  jz      short loc_180006BAC
0x180006ba4  mov     eax, [rbx+8]
0x180006ba7  cmp     eax, r12d
0x180006baa  jnz     short loc_180006B9A
0x180006bac  lea     rcx, [rbx+10h]; this
0x180006bb0  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006bb5  mov     edi, eax
0x180006bb7  test    eax, eax
0x180006bb9  js      short loc_180006BCD
0x180006bbb  mov     byte ptr [rbx+38h], 1
0x180006bbf  xor     edi, edi
0x180006bc1  jmp     short loc_180006BCD
0x180006bc3  lea     ecx, [rax-1]
0x180006bc6  lock cmpxchg [rbx+8], ecx
0x180006bcb  jz      short loc_180006BD5
0x180006bcd  mov     eax, [rbx+8]
0x180006bd0  cmp     eax, r12d
0x180006bd3  jnz     short loc_180006BC3
0x180006bd5  test    edi, edi
0x180006bd7  jnz     short loc_180006BF3
0x180006bd9  mov     rax, [rbx]
0x180006bdc  mov     r8, rsi
0x180006bdf  mov     rdx, r15
0x180006be2  mov     rcx, rbx
0x180006be5  mov     rax, [rax]
0x180006be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bed  mov     edi, eax
0x180006bef  test    eax, eax
0x180006bf1  jz      short loc_180006C07
0x180006bf3  mov     r8, [rbx]
0x180006bf6  mov     edx, 1
0x180006bfb  mov     rcx, rbx
0x180006bfe  mov     rax, [r8+20h]
0x180006c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c07  mov     eax, edi
0x180006c09  add     rsp, 28h
0x180006c0d  pop     r15
0x180006c0f  pop     r14
0x180006c11  pop     r12
0x180006c13  pop     rdi
0x180006c14  pop     rsi
0x180006c15  pop     rbx
0x180006c16  retn
```
