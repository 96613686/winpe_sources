# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRemMdmObj>>,ATL::CComCreator<ATL::CComAggObject<CRemMdmObj>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800052f0`
- end: `0x18000542d`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCRemMdmObj@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCRemMdmObj@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001194`
- `0x1800052f0`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRemMdmObj>>,ATL::CComCreator<ATL::CComAggObject<CRemMdmObj>>>::CreateInstance(
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
        *(_QWORD *)v7 = &ATL::CComObject<CRemMdmObj>::`vftable';
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
    *(_QWORD *)v11 = &ATL::CComAggObject<CRemMdmObj>::`vftable';
    *((_QWORD *)v11 + 2) = &ATL::CComContainedObject<CRemMdmObj>::`vftable';
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
0x1800052f0  push    rbx
0x1800052f2  push    rbp
0x1800052f3  push    rsi
0x1800052f4  push    rdi
0x1800052f5  push    r14
0x1800052f7  sub     rsp, 20h
0x1800052fb  mov     rsi, r8
0x1800052fe  mov     r14, rdx
0x180005301  mov     rbp, rcx
0x180005304  test    rcx, rcx
0x180005307  jnz     loc_180005395
0x18000530d  test    r8, r8
0x180005310  jz      loc_18000539A
0x180005316  mov     [r8], rcx
0x180005319  mov     ebx, 8007000Eh
0x18000531e  lea     ecx, [rbp+10h]; Size
0x180005321  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005326  mov     rdi, rax
0x180005329  test    rax, rax
0x18000532c  jz      loc_180005420
0x180005332  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005339  mov     [rax+8], ebp
0x18000533c  lea     rax, ??_7?$CComObject@VCRemMdmObj@@@ATL@@6B@; const ATL::CComObject<CRemMdmObj>::`vftable'
0x180005343  mov     [rdi], rax
0x180005346  mov     rdx, [rcx]
0x180005349  mov     rax, [rdx+8]
0x18000534d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005352  mov     ecx, [rdi+8]
0x180005355  cmp     ecx, 7FFFFFFFh
0x18000535b  jz      short loc_18000536E
0x18000535d  lea     eax, [rcx+1]
0x180005360  mov     [rdi+8], eax
0x180005363  cmp     ecx, 7FFFFFFEh
0x180005369  jz      short loc_18000536E
0x18000536b  mov     [rdi+8], ecx
0x18000536e  mov     rax, [rdi]
0x180005371  mov     r8, rsi
0x180005374  mov     rdx, r14
0x180005377  mov     rcx, rdi
0x18000537a  mov     rax, [rax]
0x18000537d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005382  mov     ebx, eax
0x180005384  test    eax, eax
0x180005386  jz      loc_180005420
0x18000538c  mov     rcx, [rdi]
0x18000538f  mov     rax, [rcx+20h]
0x180005393  jmp     short loc_180005413
0x180005395  test    rsi, rsi
0x180005398  jnz     short loc_1800053A1
0x18000539a  mov     ebx, 80004003h
0x18000539f  jmp     short loc_180005420
0x1800053a1  mov     ecx, 20h ; ' '; Size
0x1800053a6  mov     qword ptr [r8], 0
0x1800053ad  mov     ebx, 8007000Eh
0x1800053b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800053b7  mov     rdi, rax
0x1800053ba  test    rax, rax
0x1800053bd  jz      short loc_180005420
0x1800053bf  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800053c6  mov     dword ptr [rax+8], 0
0x1800053cd  lea     rax, ??_7?$CComAggObject@VCRemMdmObj@@@ATL@@6B@; const ATL::CComAggObject<CRemMdmObj>::`vftable'
0x1800053d4  mov     [rdi], rax
0x1800053d7  lea     rax, ??_7?$CComContainedObject@VCRemMdmObj@@@ATL@@6B@; const ATL::CComContainedObject<CRemMdmObj>::`vftable'
0x1800053de  mov     [rdi+10h], rax
0x1800053e2  mov     [rdi+18h], rbp
0x1800053e6  mov     rdx, [rcx]
0x1800053e9  mov     rax, [rdx+8]
0x1800053ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053f2  mov     rax, [rdi]
0x1800053f5  mov     r8, rsi
0x1800053f8  mov     rdx, r14
0x1800053fb  mov     rcx, rdi
0x1800053fe  mov     rax, [rax]
0x180005401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005406  mov     ebx, eax
0x180005408  test    eax, eax
0x18000540a  jz      short loc_180005420
0x18000540c  mov     rax, [rdi]
0x18000540f  mov     rax, [rax+18h]
0x180005413  mov     edx, 1
0x180005418  mov     rcx, rdi
0x18000541b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005420  mov     eax, ebx
0x180005422  add     rsp, 20h
0x180005426  pop     r14
0x180005428  pop     rdi
0x180005429  pop     rsi
0x18000542a  pop     rbp
0x18000542b  pop     rbx
0x18000542c  retn
```
