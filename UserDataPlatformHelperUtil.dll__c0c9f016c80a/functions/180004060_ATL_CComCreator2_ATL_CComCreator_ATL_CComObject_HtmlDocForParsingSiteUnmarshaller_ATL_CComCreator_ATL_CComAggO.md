# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<HtmlDocForParsingSiteUnmarshaller>>,ATL::CComCreator<ATL::CComAggObject<HtmlDocForParsingSiteUnmarshaller>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004060`
- end: `0x180004179`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `281`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001184`
- `0x180004060`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<HtmlDocForParsingSiteUnmarshaller>>,ATL::CComCreator<ATL::CComAggObject<HtmlDocForParsingSiteUnmarshaller>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // ebx
  _DWORD *v7; // rax
  _DWORD *v8; // rsi
  struct ATL::CAtlModule *v9; // rcx
  _DWORD *v10; // rax
  _DWORD *v11; // rsi
  struct ATL::CAtlModule *v12; // rcx

  if ( !a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      v6 = -2147024882;
      v7 = operator new(0x20u);
      v8 = v7;
      if ( v7 )
      {
        v9 = ATL::_pAtlModule;
        v7[2] = 0;
        *(_QWORD *)v7 = &ATL::CComObject<HtmlDocForParsingSiteUnmarshaller>::`vftable';
        (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
        v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, a2, a3);
        if ( v6 )
          (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 72LL))(v8, 1);
      }
      return v6;
    }
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  v6 = -2147024882;
  v10 = operator new(0x38u);
  v11 = v10;
  if ( v10 )
  {
    v12 = ATL::_pAtlModule;
    v10[2] = 0;
    *(_QWORD *)v10 = &ATL::CComAggObject<HtmlDocForParsingSiteUnmarshaller>::`vftable';
    *((_QWORD *)v10 + 3) = &ATL::CComContainedObject<HtmlDocForParsingSiteUnmarshaller>::`vftable';
    *((_QWORD *)v10 + 4) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v12 + 8LL))(v12);
    v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v11)(v11, a2, a3);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v11 + 24LL))(v11, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180004060  push    rbx
0x180004062  push    rbp
0x180004063  push    rsi
0x180004064  push    rdi
0x180004065  push    r14
0x180004067  sub     rsp, 20h
0x18000406b  mov     rdi, r8
0x18000406e  mov     r14, rdx
0x180004071  mov     rbp, rcx
0x180004074  test    rcx, rcx
0x180004077  jnz     short loc_1800040E1
0x180004079  test    r8, r8
0x18000407c  jz      short loc_1800040E6
0x18000407e  mov     [r8], rcx
0x180004081  mov     ebx, 8007000Eh
0x180004086  lea     ecx, [rbp+20h]; Size
0x180004089  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000408e  mov     rsi, rax
0x180004091  test    rax, rax
0x180004094  jz      loc_18000416C
0x18000409a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800040a1  mov     [rax+8], ebp
0x1800040a4  lea     rax, ??_7?$CComObject@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@6B@; const ATL::CComObject<HtmlDocForParsingSiteUnmarshaller>::`vftable'
0x1800040ab  mov     [rsi], rax
0x1800040ae  mov     rdx, [rcx]
0x1800040b1  mov     rax, [rdx+8]
0x1800040b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040ba  mov     rcx, [rsi]
0x1800040bd  mov     r8, rdi
0x1800040c0  mov     rdx, r14
0x1800040c3  mov     rax, [rcx]
0x1800040c6  mov     rcx, rsi
0x1800040c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040ce  mov     ebx, eax
0x1800040d0  test    eax, eax
0x1800040d2  jz      loc_18000416C
0x1800040d8  mov     rcx, [rsi]
0x1800040db  mov     rax, [rcx+48h]
0x1800040df  jmp     short loc_18000415F
0x1800040e1  test    rdi, rdi
0x1800040e4  jnz     short loc_1800040ED
0x1800040e6  mov     ebx, 80004003h
0x1800040eb  jmp     short loc_18000416C
0x1800040ed  mov     ecx, 38h ; '8'; Size
0x1800040f2  mov     qword ptr [r8], 0
0x1800040f9  mov     ebx, 8007000Eh
0x1800040fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004103  mov     rsi, rax
0x180004106  test    rax, rax
0x180004109  jz      short loc_18000416C
0x18000410b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004112  mov     dword ptr [rax+8], 0
0x180004119  lea     rax, ??_7?$CComAggObject@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@6B@; const ATL::CComAggObject<HtmlDocForParsingSiteUnmarshaller>::`vftable'
0x180004120  mov     [rsi], rax
0x180004123  lea     rax, ??_7?$CComContainedObject@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@6B@; const ATL::CComContainedObject<HtmlDocForParsingSiteUnmarshaller>::`vftable'
0x18000412a  mov     [rsi+18h], rax
0x18000412e  mov     [rsi+20h], rbp
0x180004132  mov     rdx, [rcx]
0x180004135  mov     rax, [rdx+8]
0x180004139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000413e  mov     rax, [rsi]
0x180004141  mov     r8, rdi
0x180004144  mov     rdx, r14
0x180004147  mov     rcx, rsi
0x18000414a  mov     rax, [rax]
0x18000414d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004152  mov     ebx, eax
0x180004154  test    eax, eax
0x180004156  jz      short loc_18000416C
0x180004158  mov     rax, [rsi]
0x18000415b  mov     rax, [rax+18h]
0x18000415f  mov     edx, 1
0x180004164  mov     rcx, rsi
0x180004167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000416c  mov     eax, ebx
0x18000416e  add     rsp, 20h
0x180004172  pop     r14
0x180004174  pop     rdi
0x180004175  pop     rsi
0x180004176  pop     rbp
0x180004177  pop     rbx
0x180004178  retn
```
