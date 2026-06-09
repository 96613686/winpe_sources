# Mso::SVG::Environment::LoadImageW(wchar_t const *,wchar_t const *)

- ea: `0x18005f7ec`
- end: `0x18005fa5c`
- name: `?LoadImageW@Environment@SVG@Mso@@QEBA?AV?$TCntPtr@$$CBUIImage@GEL@@@3@PEB_W0@Z`
- size: `624`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, wchar_t *, wchar_t *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800bb108`
- `0x1800f1288`

## callees

- `0x180009068`
- `0x1800091d0`
- `0x18005ee38`
- `0x18005f7ec`
- `0x18013d700`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18005f84a`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18005f84a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18005fa37`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18005fa37`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18005f858`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18005f858`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005fa00`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005fa00`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005f9f9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005f9f9`
- `gfx!?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@PEAUIStream@@@Z` at `0x18005f8ab`
- `gfx!?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@PEAUIStream@@@Z` at `0x18005f969`
- `gfx!?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@PEAUIStream@@@Z` at `0x18005f8ab`
- `gfx!?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@PEAUIStream@@@Z` at `0x18005f969`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
_QWORD *__fastcall Mso::SVG::Environment::LoadImageW(_QWORD *a1, _QWORD *a2, wchar_t *a3, wchar_t *a4)
{
  unsigned int v8; // r8d
  _QWORD *v9; // rbx
  __int64 v10; // rcx
  void (__fastcall ****v11)(_QWORD); // rax
  void (__fastcall ***v12)(_QWORD); // rcx
  __int64 v13; // rdx
  void (__fastcall ****v14)(_QWORD); // rax
  void (__fastcall ***v15)(_QWORD); // rcx
  __int64 v16; // rcx
  void *v17; // rcx
  __int64 v19; // [rsp+38h] [rbp-21h] BYREF
  unsigned int v20; // [rsp+40h] [rbp-19h]
  _QWORD *v21; // [rsp+48h] [rbp-11h] BYREF
  void *Block[2]; // [rsp+58h] [rbp-1h] BYREF
  __m128i si128; // [rsp+68h] [rbp+Fh]

  v21 = a2;
  v20 = 0;
  if ( (unsigned __int8)sub_18005EE38(a3) )
  {
    v9 = Mso::Memory::AllocateEx((Mso::Memory *)0x30, 0, v8);
    if ( !v9 )
    {
      ThrowOOM();
      __debugbreak();
    }
    v10 = v20;
    v9[1] = 0;
    v9[2] = 0;
    v9[3] = v10;
    *v9 = &Mso::SVG::SimpleMemoryStream::`vftable';
    v9[4] = 0;
    *((_DWORD *)v9 + 10) = 0;
    v21 = v9;
    (*(void (__fastcall **)(_QWORD *))(*v9 + 8LL))(v9);
    v11 = (void (__fastcall ****)(_QWORD))GEL::IImage::Create(&v19);
    v12 = *v11;
    *a2 = *v11;
    if ( v12 )
      (**v12)(v12);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
    (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
  }
  else
  {
    *(_OWORD *)Block = 0;
    si128 = 0;
    if ( a3 == a4 )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(Block[0]) = 0;
    }
    else
    {
      std::wstring::_Construct<1,wchar_t *>(Block, a3);
    }
    if ( *a1 )
    {
      (*(void (__fastcall **)(_QWORD, __int64 *, void **))(*(_QWORD *)*a1 + 8LL))(*a1, &v19, Block);
      v13 = v19;
    }
    else
    {
      v13 = 0;
      v19 = 0;
    }
    if ( v13 )
    {
      v14 = (void (__fastcall ****)(_QWORD))GEL::IImage::Create(&v21);
      v15 = *v14;
      *a2 = *v14;
      if ( v15 )
        (**v15)(v15);
      if ( v21 )
        (*(void (__fastcall **)(_QWORD *))(*v21 + 8LL))(v21);
      v16 = v19;
      if ( v19 )
      {
        v19 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      if ( si128.m128i_i64[1] > 7uLL )
      {
        v17 = Block[0];
        if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
        {
          v17 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v17 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v17);
      }
      Block[0] = (void *)19937;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
    }
    else
    {
      *a2 = 0;
      std::wstring::~wstring(Block);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18005f7ec  push    rbp
0x18005f7ee  push    rbx
0x18005f7ef  push    rsi
0x18005f7f0  push    rdi
0x18005f7f1  push    r14
0x18005f7f3  push    r15
0x18005f7f5  lea     rbp, [rsp-2Fh]
0x18005f7fa  sub     rsp, 88h
0x18005f801  mov     rax, cs:__security_cookie
0x18005f808  xor     rax, rsp
0x18005f80b  mov     [rbp+57h+var_38], rax
0x18005f80f  mov     rbx, r9
0x18005f812  mov     rsi, r8
0x18005f815  mov     rdi, rdx
0x18005f818  mov     r14, rcx
0x18005f81b  mov     [rbp+57h+var_68], rdx
0x18005f81f  xor     r15d, r15d
0x18005f822  mov     [rbp+57h+var_70], r15d
0x18005f826  mov     [rbp+57h+var_80], r15
0x18005f82a  lea     r9, [rbp+57h+var_70]
0x18005f82e  lea     r8, [rbp+57h+var_80]
0x18005f832  mov     rdx, rbx
0x18005f835  mov     rcx, rsi; String1
0x18005f838  call    sub_18005EE38
0x18005f83d  test    al, al
0x18005f83f  jz      loc_18005F8F4
0x18005f845  xor     edx, edx
0x18005f847  lea     ecx, [rdx+30h]
0x18005f84a  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x18005f850  mov     rbx, rax
0x18005f853  test    rax, rax
0x18005f856  jnz     short loc_18005F85F
0x18005f858  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x18005f85e  int     3; Trap to Debugger
0x18005f85f  mov     ecx, [rbp+57h+var_70]
0x18005f862  mov     rax, [rbp+57h+var_80]
0x18005f866  mov     [rbx+8], rax
0x18005f86a  mov     [rbx+10h], rax
0x18005f86e  add     rax, rcx
0x18005f871  mov     [rbx+18h], rax
0x18005f875  lea     rax, ??_7SimpleMemoryStream@SVG@Mso@@6B@; const Mso::SVG::SimpleMemoryStream::`vftable'
0x18005f87c  mov     [rbx], rax
0x18005f87f  mov     rax, [rbp+57h+var_80]
0x18005f883  mov     [rbp+57h+var_80], r15
0x18005f887  mov     [rbx+20h], rax
0x18005f88b  mov     [rbx+28h], r15d
0x18005f88f  mov     [rbp+57h+var_68], rbx
0x18005f893  mov     rax, [rbx]
0x18005f896  mov     rcx, rbx
0x18005f899  mov     rax, [rax+8]
0x18005f89d  call    cs:__guard_dispatch_icall_fptr
0x18005f8a3  nop
0x18005f8a4  mov     rdx, rbx
0x18005f8a7  lea     rcx, [rbp+57h+var_78]
0x18005f8ab  call    cs:__imp_?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@PEAUIStream@@@Z; GEL::IImage::Create(IStream *)
0x18005f8b1  mov     rcx, [rax]
0x18005f8b4  mov     [rdi], rcx
0x18005f8b7  test    rcx, rcx
0x18005f8ba  jz      short loc_18005F8C8
0x18005f8bc  mov     rax, [rcx]
0x18005f8bf  mov     rax, [rax]
0x18005f8c2  call    cs:__guard_dispatch_icall_fptr
0x18005f8c8  mov     rcx, [rbp+57h+var_78]
0x18005f8cc  test    rcx, rcx
0x18005f8cf  jz      short loc_18005F8DF
0x18005f8d1  mov     rax, [rcx]
0x18005f8d4  mov     rax, [rax+8]
0x18005f8d8  call    cs:__guard_dispatch_icall_fptr
0x18005f8de  nop
0x18005f8df  mov     rax, [rbx]
0x18005f8e2  mov     rcx, rbx
0x18005f8e5  mov     rax, [rax+10h]
0x18005f8e9  call    cs:__guard_dispatch_icall_fptr
0x18005f8ef  jmp     loc_18005FA2A
0x18005f8f4  xorps   xmm0, xmm0
0x18005f8f7  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18005f8fb  xorps   xmm1, xmm1
0x18005f8fe  movdqu  [rbp+57h+var_48], xmm1
0x18005f903  cmp     rsi, rbx
0x18005f906  jnz     short loc_18005F91C
0x18005f908  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18005f910  movdqu  [rbp+57h+var_48], xmm0
0x18005f915  mov     word ptr [rbp+57h+Block], r15w
0x18005f91a  jmp     short loc_18005F932
0x18005f91c  sub     rbx, rsi
0x18005f91f  sar     rbx, 1
0x18005f922  mov     r8, rbx
0x18005f925  mov     rdx, rsi
0x18005f928  lea     rcx, [rbp+57h+Block]
0x18005f92c  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x18005f931  nop
0x18005f932  mov     rcx, [r14]
0x18005f935  test    rcx, rcx
0x18005f938  jz      short loc_18005F955
0x18005f93a  mov     rax, [rcx]
0x18005f93d  lea     r8, [rbp+57h+Block]
0x18005f941  lea     rdx, [rbp+57h+var_78]
0x18005f945  mov     rax, [rax+8]
0x18005f949  call    cs:__guard_dispatch_icall_fptr
0x18005f94f  mov     rdx, [rbp+57h+var_78]
0x18005f953  jmp     short loc_18005F95C
0x18005f955  mov     rdx, r15
0x18005f958  mov     [rbp+57h+var_78], rdx
0x18005f95c  test    rdx, rdx
0x18005f95f  jz      loc_18005FA1D
0x18005f965  lea     rcx, [rbp+57h+var_68]
0x18005f969  call    cs:__imp_?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@PEAUIStream@@@Z; GEL::IImage::Create(IStream *)
0x18005f96f  mov     rcx, [rax]
0x18005f972  mov     [rdi], rcx
0x18005f975  test    rcx, rcx
0x18005f978  jz      short loc_18005F986
0x18005f97a  mov     rax, [rcx]
0x18005f97d  mov     rax, [rax]
0x18005f980  call    cs:__guard_dispatch_icall_fptr
0x18005f986  mov     rcx, [rbp+57h+var_68]
0x18005f98a  test    rcx, rcx
0x18005f98d  jz      short loc_18005F99D
0x18005f98f  mov     rax, [rcx]
0x18005f992  mov     rax, [rax+8]
0x18005f996  call    cs:__guard_dispatch_icall_fptr
0x18005f99c  nop
0x18005f99d  mov     rcx, [rbp+57h+var_78]
0x18005f9a1  test    rcx, rcx
0x18005f9a4  jz      short loc_18005F9B8
0x18005f9a6  mov     [rbp+57h+var_78], r15
0x18005f9aa  mov     rax, [rcx]
0x18005f9ad  mov     rax, [rax+10h]
0x18005f9b1  call    cs:__guard_dispatch_icall_fptr
0x18005f9b7  nop
0x18005f9b8  mov     rax, qword ptr [rbp+57h+var_48+8]
0x18005f9bc  cmp     rax, 7
0x18005f9c0  jbe     short loc_18005FA06
0x18005f9c2  mov     rcx, [rbp+57h+Block]; Block
0x18005f9c6  mov     rdx, rcx
0x18005f9c9  lea     rax, ds:2[rax*2]
0x18005f9d1  cmp     rax, 1000h
0x18005f9d7  jb      short loc_18005FA00
0x18005f9d9  mov     rcx, [rcx-8]
0x18005f9dd  sub     rdx, rcx
0x18005f9e0  lea     rax, [rdx-8]
0x18005f9e4  cmp     rax, 1Fh
0x18005f9e8  jbe     short loc_18005FA00
0x18005f9ea  mov     [rsp+0B0h+Reserved], r15; Reserved
0x18005f9ef  xor     r9d, r9d; LineNo
0x18005f9f2  xor     r8d, r8d; FileName
0x18005f9f5  xor     edx, edx; FunctionName
0x18005f9f7  xor     ecx, ecx; Expression
0x18005f9f9  call    cs:__imp__invoke_watson
0x18005fa00  call    cs:__imp_free
0x18005fa06  mov     [rbp+57h+Block], 4DE1h
0x18005fa0e  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18005fa16  movdqu  [rbp+57h+var_48], xmm0
0x18005fa1b  jmp     short loc_18005FA2A
0x18005fa1d  mov     [rdi], r15
0x18005fa20  lea     rcx, [rbp+57h+Block]; void *
0x18005fa24  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005fa29  nop
0x18005fa2a  mov     rcx, [rbp+57h+var_80]
0x18005fa2e  test    rcx, rcx
0x18005fa31  jz      short loc_18005FA3D
0x18005fa33  mov     [rbp+57h+var_80], r15
0x18005fa37  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18005fa3d  mov     rax, rdi
0x18005fa40  mov     rcx, [rbp+57h+var_38]
0x18005fa44  xor     rcx, rsp; StackCookie
0x18005fa47  call    __security_check_cookie
0x18005fa4c  add     rsp, 88h
0x18005fa53  pop     r15
0x18005fa55  pop     r14
0x18005fa57  pop     rdi
0x18005fa58  pop     rsi
0x18005fa59  pop     rbx
0x18005fa5a  pop     rbp
0x18005fa5b  retn
```
