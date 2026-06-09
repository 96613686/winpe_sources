# ATL::CComCreator<ATL::CComObject<CMidi2BS2UMPTransform>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004ba4`
- end: `0x180004cd7`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMidi2BS2UMPTransform@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004a80`

## callees

- `0x180001eb0`
- `0x180004ba4`
- `0x180005b68`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMidi2BS2UMPTransform>>::CreateInstance(
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
    *(_QWORD *)v6 = &ATL::CComObject<CMidi2BS2UMPTransform>::`vftable';
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
0x180004ba4  mov     [rsp+arg_10], r8
0x180004ba9  mov     [rsp+arg_8], rdx
0x180004bae  mov     [rsp+arg_0], rcx
0x180004bb3  push    rbx
0x180004bb4  push    rsi
0x180004bb5  push    rdi
0x180004bb6  push    r12
0x180004bb8  push    r14
0x180004bba  push    r15
0x180004bbc  sub     rsp, 28h
0x180004bc0  mov     rsi, r8
0x180004bc3  mov     r15, rdx
0x180004bc6  test    r8, r8
0x180004bc9  jnz     short loc_180004BD5
0x180004bcb  mov     eax, 80004003h
0x180004bd0  jmp     loc_180004CC9
0x180004bd5  mov     qword ptr [r8], 0
0x180004bdc  mov     edi, 8007000Eh
0x180004be1  mov     dword ptr [rsp+58h+arg_0], edi
0x180004be5  mov     [rsp+58h+arg_18], 0
0x180004bee  mov     ecx, 40h ; '@'; Size
0x180004bf3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004bf8  mov     rbx, rax
0x180004bfb  mov     dword ptr [rax+8], 0
0x180004c02  xorps   xmm0, xmm0
0x180004c05  xor     eax, eax
0x180004c07  movups  xmmword ptr [rbx+10h], xmm0
0x180004c0b  movups  xmmword ptr [rbx+20h], xmm0
0x180004c0f  mov     [rbx+30h], rax
0x180004c13  mov     [rbx+38h], al
0x180004c16  lea     rax, ??_7?$CComObject@VCMidi2BS2UMPTransform@@@ATL@@6B@; const ATL::CComObject<CMidi2BS2UMPTransform>::`vftable'
0x180004c1d  mov     [rbx], rax
0x180004c20  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004c27  mov     rax, [rcx]
0x180004c2a  mov     rax, [rax+8]
0x180004c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c33  mov     [rsp+58h+arg_18], rbx
0x180004c38  jmp     short loc_180004C4D
0x180004c3a  mov     rsi, [rsp+58h+arg_10]
0x180004c3f  mov     r15, [rsp+58h+arg_8]
0x180004c44  mov     edi, dword ptr [rsp+58h+arg_0]
0x180004c48  mov     rbx, [rsp+58h+arg_18]
0x180004c4d  test    rbx, rbx
0x180004c50  jz      short loc_180004CC7
0x180004c52  mov     r12d, 7FFFFFFFh
0x180004c58  jmp     short loc_180004C64
0x180004c5a  lea     ecx, [rax+1]
0x180004c5d  lock cmpxchg [rbx+8], ecx
0x180004c62  jz      short loc_180004C6C
0x180004c64  mov     eax, [rbx+8]
0x180004c67  cmp     eax, r12d
0x180004c6a  jnz     short loc_180004C5A
0x180004c6c  lea     rcx, [rbx+10h]; this
0x180004c70  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004c75  mov     edi, eax
0x180004c77  test    eax, eax
0x180004c79  js      short loc_180004C8D
0x180004c7b  mov     byte ptr [rbx+38h], 1
0x180004c7f  xor     edi, edi
0x180004c81  jmp     short loc_180004C8D
0x180004c83  lea     ecx, [rax-1]
0x180004c86  lock cmpxchg [rbx+8], ecx
0x180004c8b  jz      short loc_180004C95
0x180004c8d  mov     eax, [rbx+8]
0x180004c90  cmp     eax, r12d
0x180004c93  jnz     short loc_180004C83
0x180004c95  test    edi, edi
0x180004c97  jnz     short loc_180004CB3
0x180004c99  mov     rax, [rbx]
0x180004c9c  mov     r8, rsi
0x180004c9f  mov     rdx, r15
0x180004ca2  mov     rcx, rbx
0x180004ca5  mov     rax, [rax]
0x180004ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cad  mov     edi, eax
0x180004caf  test    eax, eax
0x180004cb1  jz      short loc_180004CC7
0x180004cb3  mov     r8, [rbx]
0x180004cb6  mov     edx, 1
0x180004cbb  mov     rcx, rbx
0x180004cbe  mov     rax, [r8+20h]
0x180004cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cc7  mov     eax, edi
0x180004cc9  add     rsp, 28h
0x180004ccd  pop     r15
0x180004ccf  pop     r14
0x180004cd1  pop     r12
0x180004cd3  pop     rdi
0x180004cd4  pop     rsi
0x180004cd5  pop     rbx
0x180004cd6  retn
```
