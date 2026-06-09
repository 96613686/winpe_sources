# Mso::Logging::CreateCachingLogger(void)

- ea: `0x18001ff28`
- end: `0x1800200cd`
- name: `?CreateCachingLogger@Logging@Mso@@YA?AV?$unique_ptr@UICachingLogger@Logging@Mso@@U?$default_delete@UICachingLogger@Logging@Mso@@@std@@@std@@XZ`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800143f0`

## callees

- `0x1800045ec`
- `0x180005224`
- `0x18000ab0c`
- `0x18000dd50`
- `0x18001ff28`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800200c0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800200c0`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001ff4d`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001ff4d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180020073`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180020073`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Mso::Logging::CreateCachingLogger(_QWORD *a1)
{
  _QWORD *v2; // rdi
  __int64 v3; // rax
  __int64 v4; // rbp
  __int64 v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rdx
  _QWORD *v8; // rsi
  _QWORD *v9; // r14
  _QWORD *v10; // rcx

  v2 = malloc(0x30u);
  if ( !v2 )
    std::_Xbad_alloc();
  *v2 = &Mso::Logging::CachingLogger::`vftable';
  v2[1] = 0;
  v2[2] = 0;
  v2[3] = 0;
  v2[4] = 0;
  *((_WORD *)v2 + 20) = 0;
  v3 = std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(32000);
  v4 = v3;
  v5 = v2[2];
  v6 = v2[1];
  if ( v6 != v5 )
  {
    v7 = v3 + 8;
    do
    {
      *(_QWORD *)(v7 - 8) = 0;
      *(_QWORD *)v7 = 0;
      *(_QWORD *)(v7 - 8) = *(_QWORD *)v6;
      *(_QWORD *)v7 = *(_QWORD *)(v6 + 8);
      *(_QWORD *)v6 = 0;
      *(_QWORD *)(v6 + 8) = 0;
      *(_OWORD *)(v7 + 8) = 0;
      *(_QWORD *)(v7 + 24) = 0;
      *(_QWORD *)(v7 + 32) = 0;
      *(_OWORD *)(v7 + 8) = *(_OWORD *)(v6 + 16);
      *(_OWORD *)(v7 + 24) = *(_OWORD *)(v6 + 32);
      *(_WORD *)(v6 + 16) = 0;
      *(_QWORD *)(v6 + 32) = 0;
      *(_QWORD *)(v6 + 40) = 7;
      *(_QWORD *)(v7 + 40) = *(_QWORD *)(v6 + 48);
      *(_DWORD *)(v7 + 48) = *(_DWORD *)(v6 + 56);
      v7 += 64;
      v6 += 64;
    }
    while ( v6 != v5 );
  }
  v8 = (_QWORD *)v2[1];
  if ( v8 )
  {
    v9 = (_QWORD *)v2[2];
    while ( v8 != v9 )
    {
      std::wstring::_Tidy_deallocate(v8 + 2);
      v8[2] = 19937;
      v8[4] = 0;
      v8[5] = 15;
      std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v8);
      v8 += 8;
    }
    v10 = (_QWORD *)v2[1];
    if ( ((v2[3] - (_QWORD)v10) & 0xFFFFFFFFFFFFFFC0uLL) >= 0x1000 )
    {
      _mm_lfence();
      if ( (unsigned __int64)v10 - *(v10 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v10 = (_QWORD *)*(v10 - 1);
    }
    free(v10);
  }
  v2[1] = v4;
  v2[2] = v4;
  v2[3] = v4 + 32000;
  *a1 = v2;
  return a1;
}

```

## disassembly

```asm
0x18001ff28  mov     rax, rsp
0x18001ff2b  mov     [rax+8], rbx
0x18001ff2f  mov     [rax+10h], rbp
0x18001ff33  mov     [rax+18h], rsi
0x18001ff37  mov     [rax+20h], rdi
0x18001ff3b  push    r12
0x18001ff3d  push    r14
0x18001ff3f  push    r15
0x18001ff41  sub     rsp, 30h
0x18001ff45  mov     r15, rcx
0x18001ff48  mov     ecx, 30h ; '0'; Size
0x18001ff4d  call    cs:__imp_malloc
0x18001ff53  mov     rdi, rax
0x18001ff56  xor     r12d, r12d
0x18001ff59  test    rax, rax
0x18001ff5c  jz      loc_1800200C7
0x18001ff62  lea     rax, ??_7CachingLogger@Logging@Mso@@6B@; const Mso::Logging::CachingLogger::`vftable'
0x18001ff69  mov     [rdi], rax
0x18001ff6c  mov     [rdi+8], r12
0x18001ff70  mov     [rdi+10h], r12
0x18001ff74  mov     [rdi+18h], r12
0x18001ff78  mov     [rdi+20h], r12
0x18001ff7c  mov     [rdi+28h], r12w
0x18001ff81  mov     ecx, 7D00h
0x18001ff86  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x18001ff8b  mov     rbp, rax
0x18001ff8e  mov     r8, [rdi+10h]
0x18001ff92  mov     rcx, [rdi+8]
0x18001ff96  cmp     rcx, r8
0x18001ff99  jz      short loc_180020008
0x18001ff9b  lea     rdx, [rax+8]
0x18001ff9f  mov     [rdx-8], r12
0x18001ffa3  mov     [rdx], r12
0x18001ffa6  mov     rax, [rcx]
0x18001ffa9  mov     [rdx-8], rax
0x18001ffad  mov     rax, [rcx+8]
0x18001ffb1  mov     [rdx], rax
0x18001ffb4  mov     [rcx], r12
0x18001ffb7  mov     [rcx+8], r12
0x18001ffbb  xorps   xmm0, xmm0
0x18001ffbe  movups  xmmword ptr [rdx+8], xmm0
0x18001ffc2  mov     [rdx+18h], r12
0x18001ffc6  mov     [rdx+20h], r12
0x18001ffca  movups  xmm0, xmmword ptr [rcx+10h]
0x18001ffce  movups  xmmword ptr [rdx+8], xmm0
0x18001ffd2  movups  xmm1, xmmword ptr [rcx+20h]
0x18001ffd6  movups  xmmword ptr [rdx+18h], xmm1
0x18001ffda  mov     [rcx+10h], r12w
0x18001ffdf  mov     [rcx+20h], r12
0x18001ffe3  mov     qword ptr [rcx+28h], 7
0x18001ffeb  movsd   xmm0, qword ptr [rcx+30h]
0x18001fff0  movsd   qword ptr [rdx+28h], xmm0
0x18001fff5  mov     eax, [rcx+38h]
0x18001fff8  mov     [rdx+30h], eax
0x18001fffb  lea     rdx, [rdx+40h]
0x18001ffff  add     rcx, 40h ; '@'
0x180020003  cmp     rcx, r8
0x180020006  jnz     short loc_18001FF9F
0x180020008  mov     rsi, [rdi+8]
0x18002000c  test    rsi, rsi
0x18002000f  jz      short loc_180020079
0x180020011  mov     r14, [rdi+10h]
0x180020015  jmp     short loc_180020040
0x180020017  lea     rcx, [rsi+10h]
0x18002001b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020020  mov     qword ptr [rsi+10h], 4DE1h
0x180020028  mov     [rsi+20h], r12
0x18002002c  mov     qword ptr [rsi+28h], 0Fh
0x180020034  mov     rcx, rsi
0x180020037  call    ??1?$shared_ptr@V?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@@std@@QEAA@XZ; std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(void)
0x18002003c  add     rsi, 40h ; '@'
0x180020040  cmp     rsi, r14
0x180020043  jnz     short loc_180020017
0x180020045  mov     rcx, [rdi+8]
0x180020049  mov     rax, [rdi+18h]
0x18002004d  sub     rax, rcx
0x180020050  and     rax, 0FFFFFFFFFFFFFFC0h
0x180020054  cmp     rax, 1000h
0x18002005a  jb      short loc_180020073
0x18002005c  lfence
0x18002005f  mov     rdx, [rcx-8]
0x180020063  sub     rcx, rdx
0x180020066  lea     rax, [rcx-8]
0x18002006a  cmp     rax, 1Fh
0x18002006e  ja      short loc_1800200B1
0x180020070  mov     rcx, rdx; Block
0x180020073  call    cs:__imp_free
0x180020079  mov     [rdi+8], rbp
0x18002007d  mov     [rdi+10h], rbp
0x180020081  lea     rax, [rbp+7D00h]
0x180020088  mov     [rdi+18h], rax
0x18002008c  mov     [r15], rdi
0x18002008f  mov     rax, r15
0x180020092  mov     rbx, [rsp+48h+arg_0]
0x180020097  mov     rbp, [rsp+48h+arg_8]
0x18002009c  mov     rsi, [rsp+48h+arg_10]
0x1800200a1  mov     rdi, [rsp+48h+arg_18]
0x1800200a6  add     rsp, 30h
0x1800200aa  pop     r15
0x1800200ac  pop     r14
0x1800200ae  pop     r12
0x1800200b0  retn
0x1800200b1  mov     [rsp+48h+Reserved], r12; Reserved
0x1800200b6  xor     r9d, r9d; LineNo
0x1800200b9  xor     r8d, r8d; FileName
0x1800200bc  xor     edx, edx; FunctionName
0x1800200be  xor     ecx, ecx; Expression
0x1800200c0  call    cs:__imp__invoke_watson
0x1800200c7  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
