# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CAddMdmObj>>,ATL::CComCreator<ATL::CComAggObject<CAddMdmObj>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180005bc0`
- end: `0x180005cfd`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCAddMdmObj@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCAddMdmObj@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001194`
- `0x180005bc0`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CAddMdmObj>>,ATL::CComCreator<ATL::CComAggObject<CAddMdmObj>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // ebx
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  struct ATL::CAtlModule *v9; // rcx
  int v10; // ecx
  _DWORD *v11; // rax
  _DWORD *v12; // rdi
  struct ATL::CAtlModule *v13; // rcx

  if ( !a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      v6 = -2147024882;
      v7 = operator new(0x10u);
      v8 = v7;
      if ( v7 )
      {
        v9 = ATL::_pAtlModule;
        v7[2] = 0;
        *(_QWORD *)v7 = &ATL::CComObject<CAddMdmObj>::`vftable';
        (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
        v10 = v8[2];
        if ( v10 != 0x7FFFFFFF )
        {
          v8[2] = v10 + 1;
          if ( v10 != 2147483646 )
            v8[2] = v10;
        }
        v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, a2, a3);
        if ( v6 )
          (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 32LL))(v8, 1);
      }
      return v6;
    }
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  v6 = -2147024882;
  v11 = operator new(0x20u);
  v12 = v11;
  if ( v11 )
  {
    v13 = ATL::_pAtlModule;
    v11[2] = 0;
    *(_QWORD *)v11 = &ATL::CComAggObject<CAddMdmObj>::`vftable';
    *((_QWORD *)v11 + 2) = &ATL::CComContainedObject<CAddMdmObj>::`vftable';
    *((_QWORD *)v11 + 3) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v13 + 8LL))(v13);
    v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v12)(v12, a2, a3);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v12 + 24LL))(v12, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180005bc0  push    rbx
0x180005bc2  push    rbp
0x180005bc3  push    rsi
0x180005bc4  push    rdi
0x180005bc5  push    r14
0x180005bc7  sub     rsp, 20h
0x180005bcb  mov     rsi, r8
0x180005bce  mov     r14, rdx
0x180005bd1  mov     rbp, rcx
0x180005bd4  test    rcx, rcx
0x180005bd7  jnz     loc_180005C65
0x180005bdd  test    r8, r8
0x180005be0  jz      loc_180005C6A
0x180005be6  mov     [r8], rcx
0x180005be9  mov     ebx, 8007000Eh
0x180005bee  lea     ecx, [rbp+10h]; Size
0x180005bf1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005bf6  mov     rdi, rax
0x180005bf9  test    rax, rax
0x180005bfc  jz      loc_180005CF0
0x180005c02  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005c09  mov     [rax+8], ebp
0x180005c0c  lea     rax, ??_7?$CComObject@VCAddMdmObj@@@ATL@@6B@; const ATL::CComObject<CAddMdmObj>::`vftable'
0x180005c13  mov     [rdi], rax
0x180005c16  mov     rdx, [rcx]
0x180005c19  mov     rax, [rdx+8]
0x180005c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c22  mov     ecx, [rdi+8]
0x180005c25  cmp     ecx, 7FFFFFFFh
0x180005c2b  jz      short loc_180005C3E
0x180005c2d  lea     eax, [rcx+1]
0x180005c30  mov     [rdi+8], eax
0x180005c33  cmp     ecx, 7FFFFFFEh
0x180005c39  jz      short loc_180005C3E
0x180005c3b  mov     [rdi+8], ecx
0x180005c3e  mov     rax, [rdi]
0x180005c41  mov     r8, rsi
0x180005c44  mov     rdx, r14
0x180005c47  mov     rcx, rdi
0x180005c4a  mov     rax, [rax]
0x180005c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c52  mov     ebx, eax
0x180005c54  test    eax, eax
0x180005c56  jz      loc_180005CF0
0x180005c5c  mov     rcx, [rdi]
0x180005c5f  mov     rax, [rcx+20h]
0x180005c63  jmp     short loc_180005CE3
0x180005c65  test    rsi, rsi
0x180005c68  jnz     short loc_180005C71
0x180005c6a  mov     ebx, 80004003h
0x180005c6f  jmp     short loc_180005CF0
0x180005c71  mov     ecx, 20h ; ' '; Size
0x180005c76  mov     qword ptr [r8], 0
0x180005c7d  mov     ebx, 8007000Eh
0x180005c82  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005c87  mov     rdi, rax
0x180005c8a  test    rax, rax
0x180005c8d  jz      short loc_180005CF0
0x180005c8f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005c96  mov     dword ptr [rax+8], 0
0x180005c9d  lea     rax, ??_7?$CComAggObject@VCAddMdmObj@@@ATL@@6B@; const ATL::CComAggObject<CAddMdmObj>::`vftable'
0x180005ca4  mov     [rdi], rax
0x180005ca7  lea     rax, ??_7?$CComContainedObject@VCAddMdmObj@@@ATL@@6B@; const ATL::CComContainedObject<CAddMdmObj>::`vftable'
0x180005cae  mov     [rdi+10h], rax
0x180005cb2  mov     [rdi+18h], rbp
0x180005cb6  mov     rdx, [rcx]
0x180005cb9  mov     rax, [rdx+8]
0x180005cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cc2  mov     rax, [rdi]
0x180005cc5  mov     r8, rsi
0x180005cc8  mov     rdx, r14
0x180005ccb  mov     rcx, rdi
0x180005cce  mov     rax, [rax]
0x180005cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cd6  mov     ebx, eax
0x180005cd8  test    eax, eax
0x180005cda  jz      short loc_180005CF0
0x180005cdc  mov     rax, [rdi]
0x180005cdf  mov     rax, [rax+18h]
0x180005ce3  mov     edx, 1
0x180005ce8  mov     rcx, rdi
0x180005ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cf0  mov     eax, ebx
0x180005cf2  add     rsp, 20h
0x180005cf6  pop     r14
0x180005cf8  pop     rdi
0x180005cf9  pop     rsi
0x180005cfa  pop     rbp
0x180005cfb  pop     rbx
0x180005cfc  retn
```
