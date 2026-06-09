# ATL::CComCreator<ATL::CComObject<Windows::Globalization::Spelling::CSpellCheckHost>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140010358`
- end: `0x14001042d`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCSpellCheckHost@Spelling@Globalization@Windows@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `213`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140010330`

## callees

- `0x1400014fc`
- `0x140010358`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Windows::Globalization::Spelling::CSpellCheckHost>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  __int64 v4; // r14
  unsigned int v6; // esi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  _DWORD *v11; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = operator new(0x20u);
    v8 = v7;
    if ( v7 )
    {
      v7[2] = 0;
      *(_QWORD *)v7 = &ATL::CComObject<Windows::Globalization::Spelling::CSpellCheckHost>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v11 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v11;
  }
  if ( v8 )
  {
    v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, v4, v3);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 32LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x140010358  mov     [rsp+arg_10], r8
0x14001035d  mov     [rsp+arg_8], rdx
0x140010362  mov     [rsp+arg_0], rcx
0x140010367  push    rbx
0x140010368  push    rsi
0x140010369  push    rdi
0x14001036a  push    r14
0x14001036c  sub     rsp, 28h
0x140010370  mov     rdi, r8
0x140010373  mov     r14, rdx
0x140010376  test    r8, r8
0x140010379  jnz     short loc_140010385
0x14001037b  mov     eax, 80004003h
0x140010380  jmp     loc_140010423
0x140010385  mov     qword ptr [r8], 0
0x14001038c  mov     esi, 8007000Eh
0x140010391  mov     dword ptr [rsp+48h+arg_0], esi
0x140010395  mov     [rsp+48h+arg_18], 0
0x14001039e  mov     ecx, 20h ; ' '; Size
0x1400103a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400103a8  mov     rbx, rax
0x1400103ab  test    rbx, rbx
0x1400103ae  jz      short loc_1400103D4
0x1400103b0  mov     dword ptr [rax+8], 0
0x1400103b7  lea     rax, ??_7?$CComObject@VCSpellCheckHost@Spelling@Globalization@Windows@@@ATL@@6B@; const ATL::CComObject<Windows::Globalization::Spelling::CSpellCheckHost>::`vftable'
0x1400103be  mov     [rbx], rax
0x1400103c1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400103c8  mov     rax, [rcx]
0x1400103cb  mov     rax, [rax+8]
0x1400103cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400103d4  mov     [rsp+48h+arg_18], rbx
0x1400103d9  jmp     short loc_1400103EE
0x1400103db  mov     rdi, [rsp+48h+arg_10]
0x1400103e0  mov     r14, [rsp+48h+arg_8]
0x1400103e5  mov     esi, dword ptr [rsp+48h+arg_0]
0x1400103e9  mov     rbx, [rsp+48h+arg_18]
0x1400103ee  test    rbx, rbx
0x1400103f1  jz      short loc_140010421
0x1400103f3  mov     rax, [rbx]
0x1400103f6  mov     r8, rdi
0x1400103f9  mov     rdx, r14
0x1400103fc  mov     rcx, rbx
0x1400103ff  mov     rax, [rax]
0x140010402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010407  mov     esi, eax
0x140010409  test    eax, eax
0x14001040b  jz      short loc_140010421
0x14001040d  mov     rdx, [rbx]
0x140010410  mov     rax, [rdx+20h]
0x140010414  mov     edx, 1
0x140010419  mov     rcx, rbx
0x14001041c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010421  mov     eax, esi
0x140010423  add     rsp, 28h
0x140010427  pop     r14
0x140010429  pop     rdi
0x14001042a  pop     rsi
0x14001042b  pop     rbx
0x14001042c  retn
```
