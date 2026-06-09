# ATL::CComCreator<ATL::CComObject<CMidi2SchedulerTransform>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004d44`
- end: `0x180004e77`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMidi2SchedulerTransform@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004c20`

## callees

- `0x180002050`
- `0x180004d44`
- `0x180005d08`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMidi2SchedulerTransform>>::CreateInstance(
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
    *(_QWORD *)v6 = &ATL::CComObject<CMidi2SchedulerTransform>::`vftable';
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
0x180004d44  mov     [rsp+arg_10], r8
0x180004d49  mov     [rsp+arg_8], rdx
0x180004d4e  mov     [rsp+arg_0], rcx
0x180004d53  push    rbx
0x180004d54  push    rsi
0x180004d55  push    rdi
0x180004d56  push    r12
0x180004d58  push    r14
0x180004d5a  push    r15
0x180004d5c  sub     rsp, 28h
0x180004d60  mov     rsi, r8
0x180004d63  mov     r15, rdx
0x180004d66  test    r8, r8
0x180004d69  jnz     short loc_180004D75
0x180004d6b  mov     eax, 80004003h
0x180004d70  jmp     loc_180004E69
0x180004d75  mov     qword ptr [r8], 0
0x180004d7c  mov     edi, 8007000Eh
0x180004d81  mov     dword ptr [rsp+58h+arg_0], edi
0x180004d85  mov     [rsp+58h+arg_18], 0
0x180004d8e  mov     ecx, 40h ; '@'; Size
0x180004d93  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004d98  mov     rbx, rax
0x180004d9b  mov     dword ptr [rax+8], 0
0x180004da2  xorps   xmm0, xmm0
0x180004da5  xor     eax, eax
0x180004da7  movups  xmmword ptr [rbx+10h], xmm0
0x180004dab  movups  xmmword ptr [rbx+20h], xmm0
0x180004daf  mov     [rbx+30h], rax
0x180004db3  mov     [rbx+38h], al
0x180004db6  lea     rax, ??_7?$CComObject@VCMidi2SchedulerTransform@@@ATL@@6B@; const ATL::CComObject<CMidi2SchedulerTransform>::`vftable'
0x180004dbd  mov     [rbx], rax
0x180004dc0  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004dc7  mov     rax, [rcx]
0x180004dca  mov     rax, [rax+8]
0x180004dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dd3  mov     [rsp+58h+arg_18], rbx
0x180004dd8  jmp     short loc_180004DED
0x180004dda  mov     rsi, [rsp+58h+arg_10]
0x180004ddf  mov     r15, [rsp+58h+arg_8]
0x180004de4  mov     edi, dword ptr [rsp+58h+arg_0]
0x180004de8  mov     rbx, [rsp+58h+arg_18]
0x180004ded  test    rbx, rbx
0x180004df0  jz      short loc_180004E67
0x180004df2  mov     r12d, 7FFFFFFFh
0x180004df8  jmp     short loc_180004E04
0x180004dfa  lea     ecx, [rax+1]
0x180004dfd  lock cmpxchg [rbx+8], ecx
0x180004e02  jz      short loc_180004E0C
0x180004e04  mov     eax, [rbx+8]
0x180004e07  cmp     eax, r12d
0x180004e0a  jnz     short loc_180004DFA
0x180004e0c  lea     rcx, [rbx+10h]; this
0x180004e10  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004e15  mov     edi, eax
0x180004e17  test    eax, eax
0x180004e19  js      short loc_180004E2D
0x180004e1b  mov     byte ptr [rbx+38h], 1
0x180004e1f  xor     edi, edi
0x180004e21  jmp     short loc_180004E2D
0x180004e23  lea     ecx, [rax-1]
0x180004e26  lock cmpxchg [rbx+8], ecx
0x180004e2b  jz      short loc_180004E35
0x180004e2d  mov     eax, [rbx+8]
0x180004e30  cmp     eax, r12d
0x180004e33  jnz     short loc_180004E23
0x180004e35  test    edi, edi
0x180004e37  jnz     short loc_180004E53
0x180004e39  mov     rax, [rbx]
0x180004e3c  mov     r8, rsi
0x180004e3f  mov     rdx, r15
0x180004e42  mov     rcx, rbx
0x180004e45  mov     rax, [rax]
0x180004e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e4d  mov     edi, eax
0x180004e4f  test    eax, eax
0x180004e51  jz      short loc_180004E67
0x180004e53  mov     r8, [rbx]
0x180004e56  mov     edx, 1
0x180004e5b  mov     rcx, rbx
0x180004e5e  mov     rax, [r8+20h]
0x180004e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e67  mov     eax, edi
0x180004e69  add     rsp, 28h
0x180004e6d  pop     r15
0x180004e6f  pop     r14
0x180004e71  pop     r12
0x180004e73  pop     rdi
0x180004e74  pop     rsi
0x180004e75  pop     rbx
0x180004e76  retn
```
