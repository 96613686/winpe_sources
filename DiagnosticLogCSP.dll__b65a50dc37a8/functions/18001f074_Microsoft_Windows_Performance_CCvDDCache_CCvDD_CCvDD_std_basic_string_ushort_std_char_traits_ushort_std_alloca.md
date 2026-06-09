# Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)

- ea: `0x18001f074`
- end: `0x18001f285`
- name: `??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z`
- size: `529`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180020a14`
- `0x180020e38`

## callees

- `0x18000265c`
- `0x180002d25`
- `0x1800105f8`
- `0x180011648`
- `0x180015f9c`
- `0x18001618c`
- `0x18001e810`
- `0x18001f074`
- `0x180023010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        int a8,
        int a9,
        int a10,
        const void **a11,
        char a12)
{
  _QWORD *v15; // r15
  void **v16; // r14
  __int64 i; // rdi
  char *v18; // rdx
  __int64 v19; // r15
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rbx
  char *v22; // rax
  size_t v23; // rbx

  std::wstring::wstring(a1, a2);
  std::wstring::wstring(a1 + 32, a3);
  *(_DWORD *)(a1 + 64) = a4;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  v15 = (_QWORD *)(a1 + 88);
  *(_QWORD *)(a1 + 88) = 0;
  v16 = (void **)(a1 + 96);
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_BYTE *)(a1 + 124) = a12;
  *(_DWORD *)(a1 + 128) = a8;
  *(_DWORD *)(a1 + 132) = a9;
  *(_DWORD *)(a1 + 136) = a10;
  if ( *(_DWORD *)(a1 + 64) )
  {
    if ( !(unsigned __int8)ATL::CAutoVectorPtr<_CVDD>::Allocate(a1 + 72, *(unsigned int *)(a1 + 64))
      || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned long>::Allocate(a1 + 80, *(unsigned int *)(a1 + 64))
      || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned __int64>::Allocate(a1 + 88, *(unsigned int *)(a1 + 64)) )
    {
      ATL::AtlThrowImpl(-2147024882);
    }
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 64); i = (unsigned int)(i + 1) )
    {
      if ( *(_DWORD *)(a6 + 4 * i) > 0x628u )
        ATL::AtlThrowImpl(-2147418113);
      memcpy_0(
        (void *)(*(_QWORD *)(a1 + 72) + 1576LL * (unsigned int)i),
        (const void *)(1576LL * (unsigned int)i + a5),
        *(unsigned int *)(a6 + 4 * i));
      if ( a7 )
        *(_QWORD *)(*v15 + 8 * i) = *(_QWORD *)(a7 + 8 * i);
      else
        *(_QWORD *)(*v15 + 8 * i) = 0;
      *(_DWORD *)(*(_QWORD *)(a1 + 80) + 4 * i) = *(_DWORD *)(a6 + 4 * i);
    }
  }
  if ( a11 && *(_DWORD *)a11 && a11[1] )
  {
    a12 = 0;
    v18 = (char *)*v16;
    v19 = *(_QWORD *)(a1 + 104);
    v20 = v19 - *(_QWORD *)(a1 + 96);
    v21 = *(unsigned int *)a11;
    if ( v21 >= v20 )
    {
      if ( v21 <= v20 )
      {
LABEL_20:
        memcpy_0(*v16, a11[1], *(unsigned int *)a11);
        *(_WORD *)(a1 + 122) = *((_WORD *)a11 + 8);
        *(_WORD *)(a1 + 120) = *((_WORD *)a11 + 9);
        return a1;
      }
      if ( v21 > *(_QWORD *)(a1 + 112) - (_QWORD)v18 )
      {
        try
        {
          std::vector<unsigned char>::_Resize_reallocate<unsigned char>(a1 + 96, *(unsigned int *)a11, &a12);
        }
        catch ( std::bad_alloc )
        {
          ATL::AtlThrowImpl(-2147024882);
        }
        goto LABEL_20;
      }
      v23 = v21 - v20;
      memset_0(*(void **)(a1 + 104), 0, v23);
      v22 = (char *)(v23 + v19);
    }
    else
    {
      v22 = &v18[v21];
    }
    *(_QWORD *)(a1 + 104) = v22;
    goto LABEL_20;
  }
  return a1;
}

```

## disassembly

```asm
0x18001f074  mov     [rsp+arg_8], rbx
0x18001f079  mov     [rsp+arg_10], rsi
0x18001f07e  mov     [rsp+arg_0], rcx
0x18001f083  push    rdi
0x18001f084  push    r12
0x18001f086  push    r13
0x18001f088  push    r14
0x18001f08a  push    r15
0x18001f08c  sub     rsp, 20h
0x18001f090  mov     edi, r9d
0x18001f093  mov     rbx, r8
0x18001f096  mov     rsi, rcx
0x18001f099  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001f09e  nop
0x18001f09f  lea     rcx, [rsi+20h]
0x18001f0a3  mov     rdx, rbx
0x18001f0a6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001f0ab  nop
0x18001f0ac  mov     [rsi+40h], edi
0x18001f0af  lea     rcx, [rsi+48h]
0x18001f0b3  xor     r12d, r12d
0x18001f0b6  mov     [rcx], r12
0x18001f0b9  mov     [rsi+50h], r12
0x18001f0bd  lea     r15, [rsi+58h]
0x18001f0c1  mov     [r15], r12
0x18001f0c4  lea     r14, [rsi+60h]
0x18001f0c8  mov     [r14], r12
0x18001f0cb  mov     [r14+8], r12
0x18001f0cf  mov     [r14+10h], r12
0x18001f0d3  mov     al, [rsp+48h+arg_58]
0x18001f0da  mov     [rsi+7Ch], al
0x18001f0dd  mov     eax, [rsp+48h+arg_38]
0x18001f0e4  mov     [rsi+80h], eax
0x18001f0ea  mov     eax, [rsp+48h+arg_40]
0x18001f0f1  mov     [rsi+84h], eax
0x18001f0f7  mov     eax, [rsp+48h+arg_48]
0x18001f0fe  mov     [rsi+88h], eax
0x18001f104  cmp     [rsi+40h], r12d
0x18001f108  jz      loc_18001F1B6
0x18001f10e  mov     edx, [rsi+40h]
0x18001f111  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x18001f116  test    al, al
0x18001f118  jz      loc_18001F27A
0x18001f11e  mov     edx, [rsi+40h]
0x18001f121  lea     rcx, [rsi+50h]
0x18001f125  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x18001f12a  test    al, al
0x18001f12c  jz      loc_18001F27A
0x18001f132  mov     edx, [rsi+40h]
0x18001f135  mov     rcx, r15
0x18001f138  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x18001f13d  test    al, al
0x18001f13f  jz      loc_18001F27A
0x18001f145  mov     r13, [rsp+48h+arg_30]
0x18001f14d  mov     r12, [rsp+48h+arg_28]
0x18001f152  xor     edi, edi
0x18001f154  cmp     [rsi+40h], edi
0x18001f157  jbe     short loc_18001F1B3
0x18001f159  mov     ebx, edi
0x18001f15b  cmp     dword ptr [r12+rdi*4], 628h
0x18001f163  ja      loc_18001F26F
0x18001f169  imul    rcx, rbx, 628h
0x18001f170  mov     r8d, [r12+rdi*4]; Size
0x18001f174  mov     rdx, [rsp+48h+arg_20]
0x18001f179  add     rdx, rcx; Src
0x18001f17c  add     rcx, [rsi+48h]; void *
0x18001f180  call    memcpy_0
0x18001f185  test    r13, r13
0x18001f188  jz      short loc_18001F198
0x18001f18a  mov     rcx, [r15]
0x18001f18d  mov     rax, [r13+rdi*8+0]
0x18001f192  mov     [rcx+rdi*8], rax
0x18001f196  jmp     short loc_18001F1A1
0x18001f198  mov     rax, [r15]
0x18001f19b  xor     ecx, ecx
0x18001f19d  mov     [rax+rdi*8], rcx
0x18001f1a1  mov     rcx, [rsi+50h]
0x18001f1a5  mov     eax, [r12+rdi*4]
0x18001f1a9  mov     [rcx+rdi*4], eax
0x18001f1ac  inc     edi
0x18001f1ae  cmp     edi, [rsi+40h]
0x18001f1b1  jb      short loc_18001F159
0x18001f1b3  xor     r12d, r12d
0x18001f1b6  mov     rdi, [rsp+48h+arg_50]
0x18001f1be  test    rdi, rdi
0x18001f1c1  jz      loc_18001F253
0x18001f1c7  cmp     [rdi], r12d
0x18001f1ca  jz      loc_18001F253
0x18001f1d0  cmp     [rdi+8], r12
0x18001f1d4  jz      short loc_18001F253
0x18001f1d6  mov     [rsp+48h+arg_58], r12b
0x18001f1de  mov     rdx, [r14]
0x18001f1e1  mov     r15, [r14+8]
0x18001f1e5  mov     rcx, r15
0x18001f1e8  sub     rcx, rdx
0x18001f1eb  mov     ebx, [rdi]
0x18001f1ed  cmp     rbx, rcx
0x18001f1f0  jnb     short loc_18001F1F8
0x18001f1f2  lea     rax, [rbx+rdx]
0x18001f1f6  jmp     short loc_18001F22F
0x18001f1f8  jbe     short loc_18001F233
0x18001f1fa  mov     rax, [r14+10h]
0x18001f1fe  sub     rax, rdx
0x18001f201  cmp     rbx, rax
0x18001f204  jbe     short loc_18001F21B
0x18001f206  lea     r8, [rsp+48h+arg_58]
0x18001f20e  mov     rdx, rbx
0x18001f211  mov     rcx, r14
0x18001f214  call    ??$_Resize_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBE@Z; std::vector<uchar>::_Resize_reallocate<uchar>(unsigned __int64,uchar const &)
0x18001f219  jmp     short loc_18001F233
0x18001f21b  sub     rbx, rcx
0x18001f21e  mov     r8, rbx; Size
0x18001f221  xor     edx, edx; Val
0x18001f223  mov     rcx, r15; void *
0x18001f226  call    memset_0
0x18001f22b  lea     rax, [rbx+r15]
0x18001f22f  mov     [r14+8], rax
0x18001f233  mov     r8d, [rdi]; Size
0x18001f236  mov     rdx, [rdi+8]; Src
0x18001f23a  mov     rcx, [r14]; void *
0x18001f23d  call    memcpy_0
0x18001f242  nop
0x18001f243  movzx   eax, word ptr [rdi+10h]
0x18001f247  mov     [rsi+7Ah], ax
0x18001f24b  movzx   eax, word ptr [rdi+12h]
0x18001f24f  mov     [rsi+78h], ax
0x18001f253  mov     rax, rsi
0x18001f256  mov     rbx, [rsp+48h+arg_8]
0x18001f25b  mov     rsi, [rsp+48h+arg_10]
0x18001f260  add     rsp, 20h
0x18001f264  pop     r15
0x18001f266  pop     r14
0x18001f268  pop     r13
0x18001f26a  pop     r12
0x18001f26c  pop     rdi
0x18001f26d  retn
0x18001f26f  mov     ecx, 8000FFFFh; int
0x18001f274  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001f27a  mov     ecx, 8007000Eh; int
0x18001f27f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
