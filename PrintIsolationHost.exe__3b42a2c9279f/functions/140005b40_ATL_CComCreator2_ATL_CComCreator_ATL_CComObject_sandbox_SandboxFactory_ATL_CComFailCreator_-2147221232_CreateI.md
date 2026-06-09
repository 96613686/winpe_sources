# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<sandbox::SandboxFactory>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140005b40`
- end: `0x140005c24`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VSandboxFactory@sandbox@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `228`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000196c`
- `0x140005b40`
- `0x140008010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<sandbox::SandboxFactory>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // ebx
  volatile signed __int32 *v6; // rax
  volatile signed __int32 *v7; // rdi
  struct ATL::CAtlModule *v8; // rcx
  volatile signed __int32 *v9; // rdx
  signed __int32 v10; // eax
  signed __int32 v11; // eax

  if ( a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      return (unsigned int)-2147221232;
    }
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  v5 = -2147024882;
  v6 = (volatile signed __int32 *)operator new(0x20u);
  v7 = v6;
  if ( v6 )
  {
    v8 = ATL::_pAtlModule;
    *((_DWORD *)v6 + 2) = 0;
    *(_QWORD *)v6 = &ATL::CComObject<sandbox::SandboxFactory>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v8 + 8LL))(v8);
    v9 = v7 + 2;
    do
    {
      if ( *v9 == 0x7FFFFFFF )
        break;
      v10 = *v9;
    }
    while ( v10 != _InterlockedCompareExchange(v9, v10 + 1, v10) );
    do
    {
      if ( *v9 == 0x7FFFFFFF )
        break;
      v11 = *v9;
    }
    while ( v11 != _InterlockedCompareExchange(v9, v11 - 1, v11) );
    v5 = (**(__int64 (__fastcall ***)(volatile signed __int32 *, __int64, _QWORD *))v7)(v7, a2, a3);
    if ( v5 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v7 + 32LL))(v7, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x140005b40  push    rbx
0x140005b42  push    rbp
0x140005b43  push    rsi
0x140005b44  push    rdi
0x140005b45  sub     rsp, 28h
0x140005b49  mov     rsi, r8
0x140005b4c  mov     rbp, rdx
0x140005b4f  test    rcx, rcx
0x140005b52  jnz     loc_140005C01
0x140005b58  test    r8, r8
0x140005b5b  jz      loc_140005C06
0x140005b61  mov     [r8], rcx
0x140005b64  mov     ebx, 8007000Eh
0x140005b69  mov     ecx, 20h ; ' '; Size
0x140005b6e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005b73  mov     rdi, rax
0x140005b76  test    rax, rax
0x140005b79  jz      loc_140005C19
0x140005b7f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140005b86  mov     dword ptr [rax+8], 0
0x140005b8d  lea     rax, ??_7?$CComObject@VSandboxFactory@sandbox@@@ATL@@6B@; const ATL::CComObject<sandbox::SandboxFactory>::`vftable'
0x140005b94  mov     [rdi], rax
0x140005b97  mov     rax, [rcx]
0x140005b9a  mov     rax, [rax+8]
0x140005b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ba3  lea     rdx, [rdi+8]
0x140005ba7  mov     r8d, 7FFFFFFFh
0x140005bad  jmp     short loc_140005BB8
0x140005baf  lea     ecx, [rax+1]
0x140005bb2  lock cmpxchg [rdx], ecx
0x140005bb6  jz      short loc_140005BCA
0x140005bb8  mov     eax, [rdx]
0x140005bba  cmp     eax, r8d
0x140005bbd  jnz     short loc_140005BAF
0x140005bbf  jmp     short loc_140005BCA
0x140005bc1  lea     ecx, [rax-1]
0x140005bc4  lock cmpxchg [rdx], ecx
0x140005bc8  jz      short loc_140005BD1
0x140005bca  mov     eax, [rdx]
0x140005bcc  cmp     eax, r8d
0x140005bcf  jnz     short loc_140005BC1
0x140005bd1  mov     rax, [rdi]
0x140005bd4  mov     r8, rsi
0x140005bd7  mov     rdx, rbp
0x140005bda  mov     rcx, rdi
0x140005bdd  mov     rax, [rax]
0x140005be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005be5  mov     ebx, eax
0x140005be7  test    eax, eax
0x140005be9  jz      short loc_140005C19
0x140005beb  mov     rdx, [rdi]
0x140005bee  mov     rcx, rdi
0x140005bf1  mov     rax, [rdx+20h]
0x140005bf5  mov     edx, 1
0x140005bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005bff  jmp     short loc_140005C19
0x140005c01  test    rsi, rsi
0x140005c04  jnz     short loc_140005C0D
0x140005c06  mov     ebx, 80004003h
0x140005c0b  jmp     short loc_140005C19
0x140005c0d  mov     qword ptr [r8], 0
0x140005c14  mov     ebx, 80040110h
0x140005c19  mov     eax, ebx
0x140005c1b  add     rsp, 28h
0x140005c1f  pop     rdi
0x140005c20  pop     rsi
0x140005c21  pop     rbp
0x140005c22  pop     rbx
0x140005c23  retn
```
