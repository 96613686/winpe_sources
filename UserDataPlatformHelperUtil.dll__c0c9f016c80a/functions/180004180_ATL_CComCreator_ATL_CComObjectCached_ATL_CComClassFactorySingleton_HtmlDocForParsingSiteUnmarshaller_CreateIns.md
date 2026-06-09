# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactorySingleton<HtmlDocForParsingSiteUnmarshaller>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004180`
- end: `0x180004280`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@V?$CComClassFactorySingleton@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001160`
- `0x180001184`
- `0x180004180`
- `0x18000439c`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004263`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004263`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactorySingleton<HtmlDocForParsingSiteUnmarshaller>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v7; // esi
  char *v8; // rax
  char *v9; // rbx
  _BYTE *v10; // rdi
  __int64 v11; // rcx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)operator new(0x58u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *((_OWORD *)v8 + 1) = 0;
    *((_OWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 6) = 0;
    v8[56] = 0;
    *((_DWORD *)v8 + 18) = 0;
    *((_QWORD *)v8 + 10) = 0;
    *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactorySingleton<HtmlDocForParsingSiteUnmarshaller>>::`vftable';
    *((_QWORD *)v8 + 8) = a1;
    v10 = v8 + 56;
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 16));
    if ( v7 < 0 || (*v10 = 1, (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0) )
    {
      *((_DWORD *)v9 + 2) = -1073741823;
      *(_QWORD *)v9 = &ATL::CComClassFactorySingleton<HtmlDocForParsingSiteUnmarshaller>::`vftable';
      v11 = *((_QWORD *)v9 + 10);
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      *(_QWORD *)v9 = &ATL::CComClassFactory::`vftable';
      if ( *v10 )
      {
        *v10 = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
      }
      operator delete(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004180  push    rbx
0x180004182  push    rbp
0x180004183  push    rsi
0x180004184  push    rdi
0x180004185  push    r14
0x180004187  push    r15
0x180004189  sub     rsp, 28h
0x18000418d  mov     r14, r8
0x180004190  mov     r15, rdx
0x180004193  mov     rdi, rcx
0x180004196  test    r8, r8
0x180004199  jnz     short loc_1800041A5
0x18000419b  mov     eax, 80004003h
0x1800041a0  jmp     loc_180004273
0x1800041a5  mov     ecx, 58h ; 'X'; Size
0x1800041aa  mov     qword ptr [r8], 0
0x1800041b1  mov     esi, 8007000Eh
0x1800041b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800041bb  mov     rbx, rax
0x1800041be  test    rax, rax
0x1800041c1  jz      loc_180004271
0x1800041c7  mov     dword ptr [rax+8], 0
0x1800041ce  lea     rcx, [rbx+10h]; this
0x1800041d2  xor     eax, eax
0x1800041d4  xorps   xmm0, xmm0
0x1800041d7  movups  xmmword ptr [rbx+10h], xmm0
0x1800041db  movups  xmmword ptr [rbx+20h], xmm0
0x1800041df  mov     [rbx+30h], rax
0x1800041e3  mov     [rbx+38h], al
0x1800041e6  mov     [rbx+48h], eax
0x1800041e9  mov     [rbx+50h], rax
0x1800041ed  lea     rax, ??_7?$CComObjectCached@V?$CComClassFactorySingleton@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactorySingleton<HtmlDocForParsingSiteUnmarshaller>>::`vftable'
0x1800041f4  mov     [rbx], rax
0x1800041f7  mov     [rbx+40h], rdi
0x1800041fb  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004200  lea     rdi, [rbx+38h]
0x180004204  mov     esi, eax
0x180004206  test    eax, eax
0x180004208  js      short loc_180004227
0x18000420a  mov     byte ptr [rdi], 1
0x18000420d  mov     r8, r14
0x180004210  mov     rax, [rbx]
0x180004213  mov     rdx, r15
0x180004216  mov     rcx, rbx
0x180004219  mov     rax, [rax]
0x18000421c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004221  mov     esi, eax
0x180004223  test    eax, eax
0x180004225  jz      short loc_180004271
0x180004227  lea     rax, ??_7?$CComClassFactorySingleton@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@6B@; const ATL::CComClassFactorySingleton<HtmlDocForParsingSiteUnmarshaller>::`vftable'
0x18000422e  mov     dword ptr [rbx+8], 0C0000001h
0x180004235  mov     [rbx], rax
0x180004238  mov     rcx, [rbx+50h]
0x18000423c  test    rcx, rcx
0x18000423f  jz      short loc_18000424D
0x180004241  mov     rax, [rcx]
0x180004244  mov     rax, [rax+10h]
0x180004248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000424d  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180004254  mov     [rbx], rax
0x180004257  cmp     byte ptr [rdi], 0
0x18000425a  jz      short loc_180004269
0x18000425c  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004260  mov     byte ptr [rdi], 0
0x180004263  call    cs:__imp_DeleteCriticalSection
0x180004269  mov     rcx, rbx; Block
0x18000426c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004271  mov     eax, esi
0x180004273  add     rsp, 28h
0x180004277  pop     r15
0x180004279  pop     r14
0x18000427b  pop     rdi
0x18000427c  pop     rsi
0x18000427d  pop     rbp
0x18000427e  pop     rbx
0x18000427f  retn
```
