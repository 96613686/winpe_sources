# Mso::SVG::Environment::LoadImageW(wchar_t const *,wchar_t const *)

- ea: `0x18005f7cc`
- end: `0x18005fa3c`
- name: `?LoadImageW@Environment@SVG@Mso@@QEBA?AV?$TCntPtr@$$CBUIImage@GEL@@@3@PEB_W0@Z`
- size: `624`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800bb0e8`
- `0x1800f1268`

## callees

- `0x180009068`
- `0x1800091d0`
- `0x18005ee18`
- `0x18005f7cc`
- `0x18013d650`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18005f82a`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18005f82a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18005fa17`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18005fa17`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18005f838`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18005f838`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005f9e0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005f9e0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005f9d9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005f9d9`
- `gfx!?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@PEAUIStream@@@Z` at `0x18005f88b`
- `gfx!?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@PEAUIStream@@@Z` at `0x18005f949`
- `gfx!?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@PEAUIStream@@@Z` at `0x18005f88b`
- `gfx!?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@PEAUIStream@@@Z` at `0x18005f949`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
  if ( (unsigned __int8)sub_18005EE18(a3) )
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
      std::wstring::_Construct<1,wchar_t *>(Block, a3, a4 - a3);
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
0x18005f7cc  push    rbp
0x18005f7ce  push    rbx
0x18005f7cf  push    rsi
0x18005f7d0  push    rdi
0x18005f7d1  push    r14
0x18005f7d3  push    r15
0x18005f7d5  lea     rbp, [rsp-2Fh]
0x18005f7da  sub     rsp, 88h
0x18005f7e1  mov     rax, cs:__security_cookie
0x18005f7e8  xor     rax, rsp
0x18005f7eb  mov     [rbp+57h+var_38], rax
0x18005f7ef  mov     rbx, r9
0x18005f7f2  mov     rsi, r8
0x18005f7f5  mov     rdi, rdx
0x18005f7f8  mov     r14, rcx
0x18005f7fb  mov     [rbp+57h+var_68], rdx
0x18005f7ff  xor     r15d, r15d
0x18005f802  mov     [rbp+57h+var_70], r15d
0x18005f806  mov     [rbp+57h+var_80], r15
0x18005f80a  lea     r9, [rbp+57h+var_70]
0x18005f80e  lea     r8, [rbp+57h+var_80]
0x18005f812  mov     rdx, rbx
0x18005f815  mov     rcx, rsi; String1
0x18005f818  call    sub_18005EE18
0x18005f81d  test    al, al
0x18005f81f  jz      loc_18005F8D4
0x18005f825  xor     edx, edx
0x18005f827  lea     ecx, [rdx+30h]
0x18005f82a  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x18005f830  mov     rbx, rax
0x18005f833  test    rax, rax
0x18005f836  jnz     short loc_18005F83F
0x18005f838  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x18005f83e  int     3; Trap to Debugger
0x18005f83f  mov     ecx, [rbp+57h+var_70]
0x18005f842  mov     rax, [rbp+57h+var_80]
0x18005f846  mov     [rbx+8], rax
0x18005f84a  mov     [rbx+10h], rax
0x18005f84e  add     rax, rcx
0x18005f851  mov     [rbx+18h], rax
0x18005f855  lea     rax, ??_7SimpleMemoryStream@SVG@Mso@@6B@; const Mso::SVG::SimpleMemoryStream::`vftable'
0x18005f85c  mov     [rbx], rax
0x18005f85f  mov     rax, [rbp+57h+var_80]
0x18005f863  mov     [rbp+57h+var_80], r15
0x18005f867  mov     [rbx+20h], rax
0x18005f86b  mov     [rbx+28h], r15d
0x18005f86f  mov     [rbp+57h+var_68], rbx
0x18005f873  mov     rax, [rbx]
0x18005f876  mov     rcx, rbx
0x18005f879  mov     rax, [rax+8]
0x18005f87d  call    cs:__guard_dispatch_icall_fptr
0x18005f883  nop
0x18005f884  mov     rdx, rbx
0x18005f887  lea     rcx, [rbp+57h+var_78]
0x18005f88b  call    cs:__imp_?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@PEAUIStream@@@Z; GEL::IImage::Create(IStream *)
0x18005f891  mov     rcx, [rax]
0x18005f894  mov     [rdi], rcx
0x18005f897  test    rcx, rcx
0x18005f89a  jz      short loc_18005F8A8
0x18005f89c  mov     rax, [rcx]
0x18005f89f  mov     rax, [rax]
0x18005f8a2  call    cs:__guard_dispatch_icall_fptr
0x18005f8a8  mov     rcx, [rbp+57h+var_78]
0x18005f8ac  test    rcx, rcx
0x18005f8af  jz      short loc_18005F8BF
0x18005f8b1  mov     rax, [rcx]
0x18005f8b4  mov     rax, [rax+8]
0x18005f8b8  call    cs:__guard_dispatch_icall_fptr
0x18005f8be  nop
0x18005f8bf  mov     rax, [rbx]
0x18005f8c2  mov     rcx, rbx
0x18005f8c5  mov     rax, [rax+10h]
0x18005f8c9  call    cs:__guard_dispatch_icall_fptr
0x18005f8cf  jmp     loc_18005FA0A
0x18005f8d4  xorps   xmm0, xmm0
0x18005f8d7  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18005f8db  xorps   xmm1, xmm1
0x18005f8de  movdqu  [rbp+57h+var_48], xmm1
0x18005f8e3  cmp     rsi, rbx
0x18005f8e6  jnz     short loc_18005F8FC
0x18005f8e8  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18005f8f0  movdqu  [rbp+57h+var_48], xmm0
0x18005f8f5  mov     word ptr [rbp+57h+Block], r15w
0x18005f8fa  jmp     short loc_18005F912
0x18005f8fc  sub     rbx, rsi
0x18005f8ff  sar     rbx, 1
0x18005f902  mov     r8, rbx
0x18005f905  mov     rdx, rsi
0x18005f908  lea     rcx, [rbp+57h+Block]
0x18005f90c  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x18005f911  nop
0x18005f912  mov     rcx, [r14]
0x18005f915  test    rcx, rcx
0x18005f918  jz      short loc_18005F935
0x18005f91a  mov     rax, [rcx]
0x18005f91d  lea     r8, [rbp+57h+Block]
0x18005f921  lea     rdx, [rbp+57h+var_78]
0x18005f925  mov     rax, [rax+8]
0x18005f929  call    cs:__guard_dispatch_icall_fptr
0x18005f92f  mov     rdx, [rbp+57h+var_78]
0x18005f933  jmp     short loc_18005F93C
0x18005f935  mov     rdx, r15
0x18005f938  mov     [rbp+57h+var_78], rdx
0x18005f93c  test    rdx, rdx
0x18005f93f  jz      loc_18005F9FD
0x18005f945  lea     rcx, [rbp+57h+var_68]
0x18005f949  call    cs:__imp_?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@PEAUIStream@@@Z; GEL::IImage::Create(IStream *)
0x18005f94f  mov     rcx, [rax]
0x18005f952  mov     [rdi], rcx
0x18005f955  test    rcx, rcx
0x18005f958  jz      short loc_18005F966
0x18005f95a  mov     rax, [rcx]
0x18005f95d  mov     rax, [rax]
0x18005f960  call    cs:__guard_dispatch_icall_fptr
0x18005f966  mov     rcx, [rbp+57h+var_68]
0x18005f96a  test    rcx, rcx
0x18005f96d  jz      short loc_18005F97D
0x18005f96f  mov     rax, [rcx]
0x18005f972  mov     rax, [rax+8]
0x18005f976  call    cs:__guard_dispatch_icall_fptr
0x18005f97c  nop
0x18005f97d  mov     rcx, [rbp+57h+var_78]
0x18005f981  test    rcx, rcx
0x18005f984  jz      short loc_18005F998
0x18005f986  mov     [rbp+57h+var_78], r15
0x18005f98a  mov     rax, [rcx]
0x18005f98d  mov     rax, [rax+10h]
0x18005f991  call    cs:__guard_dispatch_icall_fptr
0x18005f997  nop
0x18005f998  mov     rax, qword ptr [rbp+57h+var_48+8]
0x18005f99c  cmp     rax, 7
0x18005f9a0  jbe     short loc_18005F9E6
0x18005f9a2  mov     rcx, [rbp+57h+Block]; Block
0x18005f9a6  mov     rdx, rcx
0x18005f9a9  lea     rax, ds:2[rax*2]
0x18005f9b1  cmp     rax, 1000h
0x18005f9b7  jb      short loc_18005F9E0
0x18005f9b9  mov     rcx, [rcx-8]
0x18005f9bd  sub     rdx, rcx
0x18005f9c0  lea     rax, [rdx-8]
0x18005f9c4  cmp     rax, 1Fh
0x18005f9c8  jbe     short loc_18005F9E0
0x18005f9ca  mov     [rsp+0B0h+Reserved], r15; Reserved
0x18005f9cf  xor     r9d, r9d; LineNo
0x18005f9d2  xor     r8d, r8d; FileName
0x18005f9d5  xor     edx, edx; FunctionName
0x18005f9d7  xor     ecx, ecx; Expression
0x18005f9d9  call    cs:__imp__invoke_watson
0x18005f9e0  call    cs:__imp_free
0x18005f9e6  mov     [rbp+57h+Block], 4DE1h
0x18005f9ee  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18005f9f6  movdqu  [rbp+57h+var_48], xmm0
0x18005f9fb  jmp     short loc_18005FA0A
0x18005f9fd  mov     [rdi], r15
0x18005fa00  lea     rcx, [rbp+57h+Block]; void *
0x18005fa04  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005fa09  nop
0x18005fa0a  mov     rcx, [rbp+57h+var_80]
0x18005fa0e  test    rcx, rcx
0x18005fa11  jz      short loc_18005FA1D
0x18005fa13  mov     [rbp+57h+var_80], r15
0x18005fa17  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18005fa1d  mov     rax, rdi
0x18005fa20  mov     rcx, [rbp+57h+var_38]
0x18005fa24  xor     rcx, rsp; StackCookie
0x18005fa27  call    __security_check_cookie
0x18005fa2c  add     rsp, 88h
0x18005fa33  pop     r15
0x18005fa35  pop     r14
0x18005fa37  pop     rdi
0x18005fa38  pop     rsi
0x18005fa39  pop     rbx
0x18005fa3a  pop     rbp
0x18005fa3b  retn
```
