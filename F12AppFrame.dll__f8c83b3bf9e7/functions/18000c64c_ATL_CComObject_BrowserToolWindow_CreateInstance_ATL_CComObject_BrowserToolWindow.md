# ATL::CComObject<BrowserToolWindow>::CreateInstance(ATL::CComObject<BrowserToolWindow> * *)

- ea: `0x18000c64c`
- end: `0x18000c79c`
- name: `?CreateInstance@?$CComObject@UBrowserToolWindow@@@ATL@@SAJPEAPEAV12@@Z`
- size: `336`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000bddc`

## callees

- `0x18000193c`
- `0x18000c64c`
- `0x18000e1e4`
- `0x180011e34`
- `0x180035010`

## import_xrefs

- `USER32!DefWindowProcW` at `0x18000c6bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ATL::CComObject<BrowserToolWindow>::CreateInstance(char **a1)
{
  char **v1; // r14
  int v3; // esi
  char *v4; // rdi
  char *v6; // [rsp+60h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = (char *)operator new(0xD8u);
    *((_DWORD *)v4 + 20) = 0;
    *(_OWORD *)(v4 + 88) = 0;
    *(_OWORD *)(v4 + 104) = 0;
    *((_QWORD *)v4 + 15) = 0;
    v4[128] = 0;
    *((_QWORD *)v4 + 1) = 0;
    AtlAxWinInit();
    *((_QWORD *)v4 + 5) = 0;
    *((_QWORD *)v4 + 6) = 0;
    *((_DWORD *)v4 + 14) = 0;
    *((_QWORD *)v4 + 8) = DefWindowProcW;
    *((_QWORD *)v4 + 17) = 0;
    *((_QWORD *)v4 + 18) = 0;
    *((_QWORD *)v4 + 19) = 0;
    *((_QWORD *)v4 + 20) = 0;
    *((_QWORD *)v4 + 21) = 0;
    *((_QWORD *)v4 + 22) = 0;
    *((_DWORD *)v4 + 46) = -1;
    *((_QWORD *)v4 + 24) = 0;
    *((_WORD *)v4 + 100) = 0;
    v4[202] = 0;
    *(_QWORD *)(v4 + 204) = 0;
    *(_QWORD *)v4 = &ATL::CComObject<BrowserToolWindow>::`vftable'{for `ATL::CWindowImpl<BrowserToolWindow,ATL::CAxWindow2T<ATL::CWindow>,ATL::CWinTraits<1442840576,0>>'};
    *((_QWORD *)v4 + 9) = &ATL::CComObject<BrowserToolWindow>::`vftable'{for `IWPCEvents'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v6 = v4;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v4 = v6;
  }
  if ( v4 )
  {
    v3 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v4 + 88));
    if ( v3 < 0 )
    {
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v4 + 8LL))(v4, 1);
      v4 = 0;
    }
    else
    {
      v4[128] = 1;
      v3 = 0;
    }
  }
  *v1 = v4;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000c64c  mov     [rsp+arg_0], rcx
0x18000c651  push    rbx
0x18000c652  push    rsi
0x18000c653  push    rdi
0x18000c654  push    r14
0x18000c656  push    r15
0x18000c658  sub     rsp, 20h
0x18000c65c  mov     r14, rcx
0x18000c65f  xor     ebx, ebx
0x18000c661  test    rcx, rcx
0x18000c664  jnz     short loc_18000C670
0x18000c666  mov     eax, 80004003h
0x18000c66b  jmp     loc_18000C790
0x18000c670  mov     [rcx], rbx
0x18000c673  mov     esi, 8007000Eh
0x18000c678  mov     [rsp+48h+arg_8], esi
0x18000c67c  mov     [rsp+48h+arg_10], rbx
0x18000c681  mov     ecx, 0D8h; Size
0x18000c686  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c68b  mov     rdi, rax
0x18000c68e  mov     [rax+50h], ebx
0x18000c691  xorps   xmm0, xmm0
0x18000c694  xor     eax, eax
0x18000c696  movups  xmmword ptr [rdi+58h], xmm0
0x18000c69a  movups  xmmword ptr [rdi+68h], xmm0
0x18000c69e  mov     [rdi+78h], rax
0x18000c6a2  mov     [rdi+80h], bl
0x18000c6a8  mov     [rdi+8], rbx
0x18000c6ac  call    AtlAxWinInit
0x18000c6b1  mov     [rdi+28h], rbx
0x18000c6b5  mov     [rdi+30h], rbx
0x18000c6b9  mov     [rdi+38h], ebx
0x18000c6bc  mov     rax, cs:__imp_DefWindowProcW
0x18000c6c3  mov     [rdi+40h], rax
0x18000c6c7  mov     [rdi+88h], rbx
0x18000c6ce  mov     [rdi+90h], rbx
0x18000c6d5  mov     [rdi+98h], rbx
0x18000c6dc  mov     [rdi+0A0h], rbx
0x18000c6e3  mov     [rdi+0A8h], rbx
0x18000c6ea  mov     [rdi+0B0h], rbx
0x18000c6f1  mov     dword ptr [rdi+0B8h], 0FFFFFFFFh
0x18000c6fb  mov     [rdi+0C0h], rbx
0x18000c702  mov     [rdi+0C8h], bx
0x18000c709  mov     [rdi+0CAh], bl
0x18000c70f  mov     [rdi+0CCh], rbx
0x18000c716  lea     rax, ??_7?$CComObject@UBrowserToolWindow@@@ATL@@6B?$CWindowImpl@UBrowserToolWindow@@V?$CAxWindow2T@VCWindow@ATL@@@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@3@@1@@; const ATL::CComObject<BrowserToolWindow>::`vftable'{for `ATL::CWindowImpl<BrowserToolWindow,ATL::CAxWindow2T<ATL::CWindow>,ATL::CWinTraits<1442840576,0>>'}
0x18000c71d  mov     [rdi], rax
0x18000c720  lea     rax, ??_7?$CComObject@UBrowserToolWindow@@@ATL@@6BIWPCEvents@@@; const ATL::CComObject<BrowserToolWindow>::`vftable'{for `IWPCEvents'}
0x18000c727  mov     [rdi+48h], rax
0x18000c72b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c732  mov     rax, [rcx]
0x18000c735  mov     rax, [rax+8]
0x18000c739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c73e  mov     [rsp+48h+arg_10], rdi
0x18000c743  jmp     short loc_18000C755
0x18000c745  xor     ebx, ebx
0x18000c747  mov     r14, [rsp+48h+arg_0]
0x18000c74c  mov     esi, [rsp+48h+arg_8]
0x18000c750  mov     rdi, [rsp+48h+arg_10]
0x18000c755  test    rdi, rdi
0x18000c758  jz      short loc_18000C78B
0x18000c75a  lea     rcx, [rdi+58h]; this
0x18000c75e  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000c763  mov     esi, eax
0x18000c765  test    eax, eax
0x18000c767  js      short loc_18000C774
0x18000c769  mov     byte ptr [rdi+80h], 1
0x18000c770  mov     esi, ebx
0x18000c772  jmp     short loc_18000C78B
0x18000c774  mov     rdx, [rdi]
0x18000c777  mov     rax, [rdx+8]
0x18000c77b  mov     edx, 1
0x18000c780  mov     rcx, rdi
0x18000c783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c788  mov     rdi, rbx
0x18000c78b  mov     [r14], rdi
0x18000c78e  mov     eax, esi
0x18000c790  add     rsp, 20h
0x18000c794  pop     r15
0x18000c796  pop     r14
0x18000c798  pop     rdi
0x18000c799  pop     rsi
0x18000c79a  pop     rbx
0x18000c79b  retn
```
