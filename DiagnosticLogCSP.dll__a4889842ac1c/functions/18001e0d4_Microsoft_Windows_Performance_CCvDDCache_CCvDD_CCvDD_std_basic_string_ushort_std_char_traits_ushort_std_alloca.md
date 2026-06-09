# Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)

- ea: `0x18001e0d4`
- end: `0x18001e2e4`
- name: `??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z`
- size: `528`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, __int64, __int64, __int64, int, int, int, const void **, char)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001f9e4`
- `0x18001fdf8`

## callees

- `0x18000262c`
- `0x180002cf5`
- `0x18000fde8`
- `0x180010db8`
- `0x18001543c`
- `0x18001562c`
- `0x18001d878`
- `0x18001e0d4`
- `0x1800220cc`

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
      || !ATL::CAutoVectorPtr<unsigned long>::Allocate((void **)(a1 + 80), *(unsigned int *)(a1 + 64))
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
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          std::vector<unsigned char>::_Resize_reallocate<unsigned char>(a1 + 96, *(unsigned int *)a11, &a12);
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
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
0x18001e0d4  mov     [rsp+arg_8], rbx
0x18001e0d9  mov     [rsp+arg_10], rsi
0x18001e0de  mov     [rsp+arg_0], rcx
0x18001e0e3  push    rdi
0x18001e0e4  push    r12
0x18001e0e6  push    r13
0x18001e0e8  push    r14
0x18001e0ea  push    r15
0x18001e0ec  sub     rsp, 20h
0x18001e0f0  mov     edi, r9d
0x18001e0f3  mov     rbx, r8
0x18001e0f6  mov     rsi, rcx
0x18001e0f9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001e0fe  nop
0x18001e0ff  lea     rcx, [rsi+20h]
0x18001e103  mov     rdx, rbx
0x18001e106  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001e10b  nop
0x18001e10c  mov     [rsi+40h], edi
0x18001e10f  lea     rcx, [rsi+48h]
0x18001e113  xor     r12d, r12d
0x18001e116  mov     [rcx], r12
0x18001e119  mov     [rsi+50h], r12
0x18001e11d  lea     r15, [rsi+58h]
0x18001e121  mov     [r15], r12
0x18001e124  lea     r14, [rsi+60h]
0x18001e128  mov     [r14], r12
0x18001e12b  mov     [r14+8], r12
0x18001e12f  mov     [r14+10h], r12
0x18001e133  mov     al, [rsp+48h+arg_58]
0x18001e13a  mov     [rsi+7Ch], al
0x18001e13d  mov     eax, [rsp+48h+arg_38]
0x18001e144  mov     [rsi+80h], eax
0x18001e14a  mov     eax, [rsp+48h+arg_40]
0x18001e151  mov     [rsi+84h], eax
0x18001e157  mov     eax, [rsp+48h+arg_48]
0x18001e15e  mov     [rsi+88h], eax
0x18001e164  cmp     [rsi+40h], r12d
0x18001e168  jz      loc_18001E216
0x18001e16e  mov     edx, [rsi+40h]
0x18001e171  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x18001e176  test    al, al
0x18001e178  jz      loc_18001E2D9
0x18001e17e  mov     edx, [rsi+40h]
0x18001e181  lea     rcx, [rsi+50h]
0x18001e185  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x18001e18a  test    al, al
0x18001e18c  jz      loc_18001E2D9
0x18001e192  mov     edx, [rsi+40h]
0x18001e195  mov     rcx, r15
0x18001e198  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x18001e19d  test    al, al
0x18001e19f  jz      loc_18001E2D9
0x18001e1a5  mov     r13, [rsp+48h+arg_30]
0x18001e1ad  mov     r12, [rsp+48h+arg_28]
0x18001e1b2  xor     edi, edi
0x18001e1b4  cmp     [rsi+40h], edi
0x18001e1b7  jbe     short loc_18001E213
0x18001e1b9  mov     ebx, edi
0x18001e1bb  cmp     dword ptr [r12+rdi*4], 628h
0x18001e1c3  ja      loc_18001E2CE
0x18001e1c9  imul    rcx, rbx, 628h
0x18001e1d0  mov     r8d, [r12+rdi*4]; Size
0x18001e1d4  mov     rdx, [rsp+48h+arg_20]
0x18001e1d9  add     rdx, rcx; Src
0x18001e1dc  add     rcx, [rsi+48h]; void *
0x18001e1e0  call    memcpy_0
0x18001e1e5  test    r13, r13
0x18001e1e8  jz      short loc_18001E1F8
0x18001e1ea  mov     rcx, [r15]
0x18001e1ed  mov     rax, [r13+rdi*8+0]
0x18001e1f2  mov     [rcx+rdi*8], rax
0x18001e1f6  jmp     short loc_18001E201
0x18001e1f8  mov     rax, [r15]
0x18001e1fb  xor     ecx, ecx
0x18001e1fd  mov     [rax+rdi*8], rcx
0x18001e201  mov     rcx, [rsi+50h]
0x18001e205  mov     eax, [r12+rdi*4]
0x18001e209  mov     [rcx+rdi*4], eax
0x18001e20c  inc     edi
0x18001e20e  cmp     edi, [rsi+40h]
0x18001e211  jb      short loc_18001E1B9
0x18001e213  xor     r12d, r12d
0x18001e216  mov     rdi, [rsp+48h+arg_50]
0x18001e21e  test    rdi, rdi
0x18001e221  jz      loc_18001E2B3
0x18001e227  cmp     [rdi], r12d
0x18001e22a  jz      loc_18001E2B3
0x18001e230  cmp     [rdi+8], r12
0x18001e234  jz      short loc_18001E2B3
0x18001e236  mov     [rsp+48h+arg_58], r12b
0x18001e23e  mov     rdx, [r14]
0x18001e241  mov     r15, [r14+8]
0x18001e245  mov     rcx, r15
0x18001e248  sub     rcx, rdx
0x18001e24b  mov     ebx, [rdi]
0x18001e24d  cmp     rbx, rcx
0x18001e250  jnb     short loc_18001E258
0x18001e252  lea     rax, [rbx+rdx]
0x18001e256  jmp     short loc_18001E28F
0x18001e258  jbe     short loc_18001E293
0x18001e25a  mov     rax, [r14+10h]
0x18001e25e  sub     rax, rdx
0x18001e261  cmp     rbx, rax
0x18001e264  jbe     short loc_18001E27B
0x18001e266  lea     r8, [rsp+48h+arg_58]
0x18001e26e  mov     rdx, rbx
0x18001e271  mov     rcx, r14
0x18001e274  call    ??$_Resize_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBE@Z; std::vector<uchar>::_Resize_reallocate<uchar>(unsigned __int64,uchar const &)
0x18001e279  jmp     short loc_18001E293
0x18001e27b  sub     rbx, rcx
0x18001e27e  mov     r8, rbx; Size
0x18001e281  xor     edx, edx; Val
0x18001e283  mov     rcx, r15; void *
0x18001e286  call    memset_0
0x18001e28b  lea     rax, [rbx+r15]
0x18001e28f  mov     [r14+8], rax
0x18001e293  mov     r8d, [rdi]; Size
0x18001e296  mov     rdx, [rdi+8]; Src
0x18001e29a  mov     rcx, [r14]; void *
0x18001e29d  call    memcpy_0
0x18001e2a2  nop
0x18001e2a3  movzx   eax, word ptr [rdi+10h]
0x18001e2a7  mov     [rsi+7Ah], ax
0x18001e2ab  movzx   eax, word ptr [rdi+12h]
0x18001e2af  mov     [rsi+78h], ax
0x18001e2b3  mov     rax, rsi
0x18001e2b6  mov     rbx, [rsp+48h+arg_8]
0x18001e2bb  mov     rsi, [rsp+48h+arg_10]
0x18001e2c0  add     rsp, 20h
0x18001e2c4  pop     r15
0x18001e2c6  pop     r14
0x18001e2c8  pop     r13
0x18001e2ca  pop     r12
0x18001e2cc  pop     rdi
0x18001e2cd  retn
0x18001e2ce  mov     ecx, 8000FFFFh; int
0x18001e2d3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e2d9  mov     ecx, 8007000Eh; int
0x18001e2de  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
