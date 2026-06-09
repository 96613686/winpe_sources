# ATL::CComCreator<ATL::CComObject<CIdentityProfileHandler>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180007b20`
- end: `0x180007c29`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCIdentityProfileHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `265`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007f40`

## callees

- `0x180006230`
- `0x180007b20`
- `0x180007c30`
- `0x18000f088`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CIdentityProfileHandler>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // edi
  CIdentityProfileHandler *v6; // rax
  CIdentityProfileHandler *v7; // rbx
  int v8; // eax
  int v9; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v5 = -2147024882;
  v6 = (CIdentityProfileHandler *)operator new(0x60u);
  v7 = v6;
  if ( v6 )
  {
    CIdentityProfileHandler::CIdentityProfileHandler(v6);
    *(_QWORD *)v7 = &ATL::CComObject<CIdentityProfileHandler>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  if ( v7 )
  {
    v8 = ATL::CComCriticalSection::Init((CIdentityProfileHandler *)((char *)v7 + 16));
    if ( v8 >= 0 )
      *((_BYTE *)v7 + 56) = 1;
    v9 = 0;
    if ( v8 < 0 )
      v9 = v8;
    v5 = 0;
    if ( v9 < 0 )
      v5 = v9;
    if ( v5 || (v5 = (**(__int64 (__fastcall ***)(CIdentityProfileHandler *, __int64, _QWORD *))v7)(v7, a2, a3)) != 0 )
      (*(void (__fastcall **)(CIdentityProfileHandler *, __int64))(*(_QWORD *)v7 + 72LL))(v7, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x180007b20  mov     [rsp+arg_10], r8
0x180007b25  mov     [rsp+arg_8], rdx
0x180007b2a  mov     [rsp+arg_0], rcx
0x180007b2f  push    rbx
0x180007b30  push    rsi
0x180007b31  push    rdi
0x180007b32  push    r14
0x180007b34  sub     rsp, 28h
0x180007b38  mov     rsi, r8
0x180007b3b  mov     r14, rdx
0x180007b3e  test    r8, r8
0x180007b41  jz      loc_180007BEC
0x180007b47  mov     qword ptr [r8], 0
0x180007b4e  mov     edi, 8007000Eh
0x180007b53  mov     dword ptr [rsp+48h+arg_0], edi
0x180007b57  mov     [rsp+48h+arg_18], 0
0x180007b60  mov     ecx, 60h ; '`'; Size
0x180007b65  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007b6a  mov     rbx, rax
0x180007b6d  test    rbx, rbx
0x180007b70  jz      short loc_180007B97
0x180007b72  mov     rcx, rax; this
0x180007b75  call    ??0CIdentityProfileHandler@@QEAA@XZ; CIdentityProfileHandler::CIdentityProfileHandler(void)
0x180007b7a  lea     rax, ??_7?$CComObject@VCIdentityProfileHandler@@@ATL@@6B@; const ATL::CComObject<CIdentityProfileHandler>::`vftable'
0x180007b81  mov     [rbx], rax
0x180007b84  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007b8b  mov     rax, [rcx]
0x180007b8e  mov     rax, [rax+8]
0x180007b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b97  mov     [rsp+48h+arg_18], rbx
0x180007b9c  test    rbx, rbx
0x180007b9f  jz      short loc_180007BDE
0x180007ba1  lea     rcx, [rbx+10h]; this
0x180007ba5  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180007baa  test    eax, eax
0x180007bac  js      short loc_180007BB2
0x180007bae  mov     byte ptr [rbx+38h], 1
0x180007bb2  xor     ecx, ecx
0x180007bb4  test    eax, eax
0x180007bb6  cmovs   ecx, eax
0x180007bb9  xor     edi, edi
0x180007bbb  test    ecx, ecx
0x180007bbd  cmovs   edi, ecx
0x180007bc0  test    edi, edi
0x180007bc2  jnz     short loc_180007BFB
0x180007bc4  mov     rax, [rbx]
0x180007bc7  mov     r8, rsi
0x180007bca  mov     rdx, r14
0x180007bcd  mov     rcx, rbx
0x180007bd0  mov     rax, [rax]
0x180007bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bd8  mov     edi, eax
0x180007bda  test    eax, eax
0x180007bdc  jnz     short loc_180007BFB
0x180007bde  mov     eax, edi
0x180007be0  add     rsp, 28h
0x180007be4  pop     r14
0x180007be6  pop     rdi
0x180007be7  pop     rsi
0x180007be8  pop     rbx
0x180007be9  retn
0x180007bea  jmp     short loc_180007B97
0x180007bec  mov     eax, 80004003h
0x180007bf1  add     rsp, 28h
0x180007bf5  pop     r14
0x180007bf7  pop     rdi
0x180007bf8  pop     rsi
0x180007bf9  pop     rbx
0x180007bfa  retn
0x180007bfb  mov     rcx, [rbx]
0x180007bfe  mov     rax, [rcx+48h]
0x180007c02  mov     edx, 1
0x180007c07  mov     rcx, rbx
0x180007c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c0f  jmp     short loc_180007BDE
0x180007c11  mov     rsi, [rsp+48h+arg_10]
0x180007c16  mov     r14, [rsp+48h+arg_8]
0x180007c1b  mov     edi, dword ptr [rsp+48h+arg_0]
0x180007c1f  mov     rbx, [rsp+48h+arg_18]
0x180007c24  jmp     loc_180007B9C
```
