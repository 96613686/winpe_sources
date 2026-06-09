# ipx::mtf::InputTypeAttributesFactory::_CreateIUnknownInstance(IUnknown *,IUnknown * *)

- ea: `0x180007fa0`
- end: `0x1800080a3`
- name: `?_CreateIUnknownInstance@InputTypeAttributesFactory@mtf@ipx@@UEAAJPEAUIUnknown@@PEAPEAU4@@Z`
- size: `259`
- prototype: `__int64 __fastcall(ipx::mtf::InputTypeAttributesFactory *__hidden this, struct IUnknown *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001fc4`
- `0x180007fa0`

## pseudocode

```c
__int64 __fastcall ipx::mtf::InputTypeAttributesFactory::_CreateIUnknownInstance(
        ipx::mtf::InputTypeAttributesFactory *this,
        struct IUnknown *a2,
        struct IUnknown **a3)
{
  char *v5; // rax

  if ( a2 )
    return 2147746064LL;
  v5 = (char *)operator new(0xE0u);
  if ( v5 )
  {
    *(_QWORD *)v5 = &ipx::mtf::CMtfInputTypeAttributes::`vftable';
    *((_QWORD *)v5 + 1) = &ipx::mtf::CFuzzyTable::`vftable';
    *((_QWORD *)v5 + 2) = 0;
    *((_DWORD *)v5 + 6) = 20;
    *((_QWORD *)v5 + 4) = 0;
    *((_DWORD *)v5 + 10) = 0;
    *((_QWORD *)v5 + 6) = &ipx::mtf::CFuzzyTable::`vftable';
    *((_QWORD *)v5 + 7) = 0;
    *((_DWORD *)v5 + 16) = 20;
    *((_QWORD *)v5 + 9) = 0;
    *((_DWORD *)v5 + 20) = 0;
    *((_QWORD *)v5 + 11) = &ipx::mtf::CFuzzyHiraganaTable::`vftable';
    *((_QWORD *)v5 + 12) = 0;
    *((_DWORD *)v5 + 26) = 20;
    *((_QWORD *)v5 + 14) = 0;
    *((_QWORD *)v5 + 15) = 0;
    *((_QWORD *)v5 + 17) = 0;
    *((_DWORD *)v5 + 36) = 20;
    *((_QWORD *)v5 + 19) = 0;
    *((_QWORD *)v5 + 16) = &ipx::mtf::CFuzzyHiraganaTable::`vftable';
    *((_QWORD *)v5 + 20) = 0;
    *((_QWORD *)v5 + 21) = 0;
    *(_QWORD *)(v5 + 196) = 0;
    *(_QWORD *)(v5 + 204) = 0;
    *((GUID *)v5 + 11) = GUID_NULL;
    *(_QWORD *)(v5 + 212) = 0;
    *((_DWORD *)v5 + 55) = 0;
    *((_DWORD *)v5 + 48) = 1;
    _InterlockedIncrement(&g_cRefDll);
  }
  else
  {
    v5 = 0;
  }
  *a3 = (struct IUnknown *)v5;
  return 0;
}

```

## disassembly

```asm
0x180007fa0  mov     [rsp+arg_0], rbx
0x180007fa5  push    rdi
0x180007fa6  sub     rsp, 20h
0x180007faa  xor     edi, edi
0x180007fac  mov     rbx, r8
0x180007faf  test    rdx, rdx
0x180007fb2  jz      short loc_180007FBE
0x180007fb4  mov     eax, 80040110h
0x180007fb9  jmp     loc_180008098
0x180007fbe  mov     ecx, 0E0h; Size
0x180007fc3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007fc8  mov     [rsp+28h+arg_8], rax
0x180007fcd  test    rax, rax
0x180007fd0  jz      loc_180008090
0x180007fd6  mov     edx, 14h
0x180007fdb  lea     rcx, ??_7CMtfInputTypeAttributes@mtf@ipx@@6B@; const ipx::mtf::CMtfInputTypeAttributes::`vftable'
0x180007fe2  mov     [rax], rcx
0x180007fe5  lea     rcx, ??_7CFuzzyTable@mtf@ipx@@6B@; const ipx::mtf::CFuzzyTable::`vftable'
0x180007fec  mov     [rax+8], rcx
0x180007ff0  mov     [rax+10h], rdi
0x180007ff4  mov     [rax+18h], edx
0x180007ff7  mov     [rax+20h], rdi
0x180007ffb  mov     [rax+28h], edi
0x180007ffe  mov     [rax+30h], rcx
0x180008002  lea     rcx, ??_7CFuzzyHiraganaTable@mtf@ipx@@6B@; const ipx::mtf::CFuzzyHiraganaTable::`vftable'
0x180008009  mov     [rax+38h], rdi
0x18000800d  mov     [rax+40h], edx
0x180008010  mov     [rax+48h], rdi
0x180008014  mov     [rax+50h], edi
0x180008017  mov     [rax+58h], rcx
0x18000801b  mov     [rax+60h], rdi
0x18000801f  mov     [rax+68h], edx
0x180008022  mov     [rax+70h], rdi
0x180008026  mov     [rax+78h], rdi
0x18000802a  mov     [rax+88h], rdi
0x180008031  mov     [rax+90h], edx
0x180008037  mov     [rax+98h], rdi
0x18000803e  mov     [rax+80h], rcx
0x180008045  mov     [rax+0A0h], rdi
0x18000804c  mov     [rax+0A8h], rdi
0x180008053  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000805a  mov     [rax+0C4h], rdi
0x180008061  mov     [rax+0CCh], rdi
0x180008068  movdqu  xmmword ptr [rax+0B0h], xmm0
0x180008070  mov     [rax+0D4h], rdi
0x180008077  mov     [rax+0DCh], edi
0x18000807d  mov     dword ptr [rax+0C0h], 1
0x180008087  lock inc cs:?g_cRefDll@@3JA; long g_cRefDll
0x18000808e  jmp     short loc_180008093
0x180008090  mov     rax, rdi
0x180008093  mov     [rbx], rax
0x180008096  xor     eax, eax
0x180008098  mov     rbx, [rsp+28h+arg_0]
0x18000809d  add     rsp, 20h
0x1800080a1  pop     rdi
0x1800080a2  retn
```
