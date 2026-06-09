# ATL::CComCreator<ATL::CComObject<CMidi2UMP2BSTransform>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004c34`
- end: `0x180004d67`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMidi2UMP2BSTransform@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004b10`

## callees

- `0x180001f40`
- `0x180004c34`
- `0x180005bf8`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMidi2UMP2BSTransform>>::CreateInstance(
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
    *(_QWORD *)v6 = &ATL::CComObject<CMidi2UMP2BSTransform>::`vftable';
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
0x180004c34  mov     [rsp+arg_10], r8
0x180004c39  mov     [rsp+arg_8], rdx
0x180004c3e  mov     [rsp+arg_0], rcx
0x180004c43  push    rbx
0x180004c44  push    rsi
0x180004c45  push    rdi
0x180004c46  push    r12
0x180004c48  push    r14
0x180004c4a  push    r15
0x180004c4c  sub     rsp, 28h
0x180004c50  mov     rsi, r8
0x180004c53  mov     r15, rdx
0x180004c56  test    r8, r8
0x180004c59  jnz     short loc_180004C65
0x180004c5b  mov     eax, 80004003h
0x180004c60  jmp     loc_180004D59
0x180004c65  mov     qword ptr [r8], 0
0x180004c6c  mov     edi, 8007000Eh
0x180004c71  mov     dword ptr [rsp+58h+arg_0], edi
0x180004c75  mov     [rsp+58h+arg_18], 0
0x180004c7e  mov     ecx, 40h ; '@'; Size
0x180004c83  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004c88  mov     rbx, rax
0x180004c8b  mov     dword ptr [rax+8], 0
0x180004c92  xorps   xmm0, xmm0
0x180004c95  xor     eax, eax
0x180004c97  movups  xmmword ptr [rbx+10h], xmm0
0x180004c9b  movups  xmmword ptr [rbx+20h], xmm0
0x180004c9f  mov     [rbx+30h], rax
0x180004ca3  mov     [rbx+38h], al
0x180004ca6  lea     rax, ??_7?$CComObject@VCMidi2UMP2BSTransform@@@ATL@@6B@; const ATL::CComObject<CMidi2UMP2BSTransform>::`vftable'
0x180004cad  mov     [rbx], rax
0x180004cb0  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004cb7  mov     rax, [rcx]
0x180004cba  mov     rax, [rax+8]
0x180004cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cc3  mov     [rsp+58h+arg_18], rbx
0x180004cc8  jmp     short loc_180004CDD
0x180004cca  mov     rsi, [rsp+58h+arg_10]
0x180004ccf  mov     r15, [rsp+58h+arg_8]
0x180004cd4  mov     edi, dword ptr [rsp+58h+arg_0]
0x180004cd8  mov     rbx, [rsp+58h+arg_18]
0x180004cdd  test    rbx, rbx
0x180004ce0  jz      short loc_180004D57
0x180004ce2  mov     r12d, 7FFFFFFFh
0x180004ce8  jmp     short loc_180004CF4
0x180004cea  lea     ecx, [rax+1]
0x180004ced  lock cmpxchg [rbx+8], ecx
0x180004cf2  jz      short loc_180004CFC
0x180004cf4  mov     eax, [rbx+8]
0x180004cf7  cmp     eax, r12d
0x180004cfa  jnz     short loc_180004CEA
0x180004cfc  lea     rcx, [rbx+10h]; this
0x180004d00  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004d05  mov     edi, eax
0x180004d07  test    eax, eax
0x180004d09  js      short loc_180004D1D
0x180004d0b  mov     byte ptr [rbx+38h], 1
0x180004d0f  xor     edi, edi
0x180004d11  jmp     short loc_180004D1D
0x180004d13  lea     ecx, [rax-1]
0x180004d16  lock cmpxchg [rbx+8], ecx
0x180004d1b  jz      short loc_180004D25
0x180004d1d  mov     eax, [rbx+8]
0x180004d20  cmp     eax, r12d
0x180004d23  jnz     short loc_180004D13
0x180004d25  test    edi, edi
0x180004d27  jnz     short loc_180004D43
0x180004d29  mov     rax, [rbx]
0x180004d2c  mov     r8, rsi
0x180004d2f  mov     rdx, r15
0x180004d32  mov     rcx, rbx
0x180004d35  mov     rax, [rax]
0x180004d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d3d  mov     edi, eax
0x180004d3f  test    eax, eax
0x180004d41  jz      short loc_180004D57
0x180004d43  mov     r8, [rbx]
0x180004d46  mov     edx, 1
0x180004d4b  mov     rcx, rbx
0x180004d4e  mov     rax, [r8+20h]
0x180004d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d57  mov     eax, edi
0x180004d59  add     rsp, 28h
0x180004d5d  pop     r15
0x180004d5f  pop     r14
0x180004d61  pop     r12
0x180004d63  pop     rdi
0x180004d64  pop     rsi
0x180004d65  pop     rbx
0x180004d66  retn
```
