# Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)

- ea: `0x18000d4bc`
- end: `0x18000d6cc`
- name: `??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z`
- size: `528`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, __int64, __int64, __int64, int, int, int, unsigned int *, char)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000edc4`
- `0x18000f1d8`

## callees

- `0x180002420`
- `0x1800027b1`
- `0x180003bb8`
- `0x18000439c`
- `0x18000458c`
- `0x18000cb90`
- `0x18000d074`
- `0x18000d4bc`
- `0x1800114bc`

## pseudocode

```c
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
        unsigned int *a11,
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
  __int64 result; // rax

  ((void (*)(void))std::wstring::wstring)();
  std::wstring::wstring(a1 + 32, a3);
  try
  {
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
    if ( !a11 || !*a11 || !*((_QWORD *)a11 + 1) )
      goto LABEL_23;
    a12 = 0;
    v18 = (char *)*v16;
    v19 = *(_QWORD *)(a1 + 104);
    v20 = v19 - *(_QWORD *)(a1 + 96);
    v21 = *a11;
    if ( v21 < v20 )
    {
      v22 = &v18[v21];
LABEL_21:
      *(_QWORD *)(a1 + 104) = v22;
      goto LABEL_22;
    }
    if ( v21 > v20 )
    {
      if ( v21 <= *(_QWORD *)(a1 + 112) - (_QWORD)v18 )
      {
        v23 = v21 - v20;
        memset_0(*(void **)(a1 + 104), 0, v23);
        v22 = (char *)(v23 + v19);
        goto LABEL_21;
      }
      std::vector<unsigned char>::_Resize_reallocate<unsigned char>(a1 + 96, *a11, &a12);
    }
LABEL_22:
    memcpy_0(*v16, *((const void **)a11 + 1), *a11);
    *(_WORD *)(a1 + 122) = *((_WORD *)a11 + 8);
    *(_WORD *)(a1 + 120) = *((_WORD *)a11 + 9);
LABEL_23:
    result = a1;
  }
  catch ( std::bad_alloc )
  {
    ATL::AtlThrowImpl(-2147024882);
  }
  *(_DWORD *)(a1 + 64) = a4;
}

```

## disassembly

```asm
0x18000d4bc  mov     [rsp+arg_8], rbx
0x18000d4c1  mov     [rsp+arg_10], rsi
0x18000d4c6  mov     [rsp+arg_0], rcx
0x18000d4cb  push    rdi
0x18000d4cc  push    r12
0x18000d4ce  push    r13
0x18000d4d0  push    r14
0x18000d4d2  push    r15
0x18000d4d4  sub     rsp, 20h
0x18000d4d8  mov     edi, r9d
0x18000d4db  mov     rbx, r8
0x18000d4de  mov     rsi, rcx
0x18000d4e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d4e6  nop
0x18000d4e7  lea     rcx, [rsi+20h]
0x18000d4eb  mov     rdx, rbx
0x18000d4ee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d4f3  nop
0x18000d4f4  mov     [rsi+40h], edi
0x18000d4f7  lea     rcx, [rsi+48h]
0x18000d4fb  xor     r12d, r12d
0x18000d4fe  mov     [rcx], r12
0x18000d501  mov     [rsi+50h], r12
0x18000d505  lea     r15, [rsi+58h]
0x18000d509  mov     [r15], r12
0x18000d50c  lea     r14, [rsi+60h]
0x18000d510  mov     [r14], r12
0x18000d513  mov     [r14+8], r12
0x18000d517  mov     [r14+10h], r12
0x18000d51b  mov     al, [rsp+48h+arg_58]
0x18000d522  mov     [rsi+7Ch], al
0x18000d525  mov     eax, [rsp+48h+arg_38]
0x18000d52c  mov     [rsi+80h], eax
0x18000d532  mov     eax, [rsp+48h+arg_40]
0x18000d539  mov     [rsi+84h], eax
0x18000d53f  mov     eax, [rsp+48h+arg_48]
0x18000d546  mov     [rsi+88h], eax
0x18000d54c  cmp     [rsi+40h], r12d
0x18000d550  jz      loc_18000D5FE
0x18000d556  mov     edx, [rsi+40h]
0x18000d559  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x18000d55e  test    al, al
0x18000d560  jz      loc_18000D6C1
0x18000d566  mov     edx, [rsi+40h]
0x18000d569  lea     rcx, [rsi+50h]
0x18000d56d  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x18000d572  test    al, al
0x18000d574  jz      loc_18000D6C1
0x18000d57a  mov     edx, [rsi+40h]
0x18000d57d  mov     rcx, r15
0x18000d580  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x18000d585  test    al, al
0x18000d587  jz      loc_18000D6C1
0x18000d58d  mov     r13, [rsp+48h+arg_30]
0x18000d595  mov     r12, [rsp+48h+arg_28]
0x18000d59a  xor     edi, edi
0x18000d59c  cmp     [rsi+40h], edi
0x18000d59f  jbe     short loc_18000D5FB
0x18000d5a1  mov     ebx, edi
0x18000d5a3  cmp     dword ptr [r12+rdi*4], 628h
0x18000d5ab  ja      loc_18000D6B6
0x18000d5b1  imul    rcx, rbx, 628h
0x18000d5b8  mov     r8d, [r12+rdi*4]; Size
0x18000d5bc  mov     rdx, [rsp+48h+arg_20]
0x18000d5c1  add     rdx, rcx; Src
0x18000d5c4  add     rcx, [rsi+48h]; void *
0x18000d5c8  call    memcpy_0
0x18000d5cd  test    r13, r13
0x18000d5d0  jz      short loc_18000D5E0
0x18000d5d2  mov     rcx, [r15]
0x18000d5d5  mov     rax, [r13+rdi*8+0]
0x18000d5da  mov     [rcx+rdi*8], rax
0x18000d5de  jmp     short loc_18000D5E9
0x18000d5e0  mov     rax, [r15]
0x18000d5e3  xor     ecx, ecx
0x18000d5e5  mov     [rax+rdi*8], rcx
0x18000d5e9  mov     rcx, [rsi+50h]
0x18000d5ed  mov     eax, [r12+rdi*4]
0x18000d5f1  mov     [rcx+rdi*4], eax
0x18000d5f4  inc     edi
0x18000d5f6  cmp     edi, [rsi+40h]
0x18000d5f9  jb      short loc_18000D5A1
0x18000d5fb  xor     r12d, r12d
0x18000d5fe  mov     rdi, [rsp+48h+arg_50]
0x18000d606  test    rdi, rdi
0x18000d609  jz      loc_18000D69B
0x18000d60f  cmp     [rdi], r12d
0x18000d612  jz      loc_18000D69B
0x18000d618  cmp     [rdi+8], r12
0x18000d61c  jz      short loc_18000D69B
0x18000d61e  mov     [rsp+48h+arg_58], r12b
0x18000d626  mov     rdx, [r14]
0x18000d629  mov     r15, [r14+8]
0x18000d62d  mov     rcx, r15
0x18000d630  sub     rcx, rdx
0x18000d633  mov     ebx, [rdi]
0x18000d635  cmp     rbx, rcx
0x18000d638  jnb     short loc_18000D640
0x18000d63a  lea     rax, [rbx+rdx]
0x18000d63e  jmp     short loc_18000D677
0x18000d640  jbe     short loc_18000D67B
0x18000d642  mov     rax, [r14+10h]
0x18000d646  sub     rax, rdx
0x18000d649  cmp     rbx, rax
0x18000d64c  jbe     short loc_18000D663
0x18000d64e  lea     r8, [rsp+48h+arg_58]
0x18000d656  mov     rdx, rbx
0x18000d659  mov     rcx, r14
0x18000d65c  call    ??$_Resize_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBE@Z; std::vector<uchar>::_Resize_reallocate<uchar>(unsigned __int64,uchar const &)
0x18000d661  jmp     short loc_18000D67B
0x18000d663  sub     rbx, rcx
0x18000d666  mov     r8, rbx; Size
0x18000d669  xor     edx, edx; Val
0x18000d66b  mov     rcx, r15; void *
0x18000d66e  call    memset_0
0x18000d673  lea     rax, [rbx+r15]
0x18000d677  mov     [r14+8], rax
0x18000d67b  mov     r8d, [rdi]; Size
0x18000d67e  mov     rdx, [rdi+8]; Src
0x18000d682  mov     rcx, [r14]; void *
0x18000d685  call    memcpy_0
0x18000d68a  nop
0x18000d68b  movzx   eax, word ptr [rdi+10h]
0x18000d68f  mov     [rsi+7Ah], ax
0x18000d693  movzx   eax, word ptr [rdi+12h]
0x18000d697  mov     [rsi+78h], ax
0x18000d69b  mov     rax, rsi
0x18000d69e  mov     rbx, [rsp+48h+arg_8]
0x18000d6a3  mov     rsi, [rsp+48h+arg_10]
0x18000d6a8  add     rsp, 20h
0x18000d6ac  pop     r15
0x18000d6ae  pop     r14
0x18000d6b0  pop     r13
0x18000d6b2  pop     r12
0x18000d6b4  pop     rdi
0x18000d6b5  retn
0x18000d6b6  mov     ecx, 8000FFFFh; int
0x18000d6bb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d6c1  mov     ecx, 8007000Eh; int
0x18000d6c6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
