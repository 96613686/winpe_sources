# Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70> const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)

- ea: `0x180008d5c`
- end: `0x180009016`
- name: `??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z`
- size: `698`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, __int64, __int64, __int64, int, int, int, const void **, char)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800093c0`
- `0x180009704`

## callees

- `0x18000139c`
- `0x1800056c8`
- `0x1800061c8`
- `0x180008d5c`
- `0x18000d6e0`
- `0x18000e50c`
- `0x180013934`
- `0x1800278f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  __int64 v15; // rsi
  _QWORD *v16; // r12
  unsigned int i; // r15d
  unsigned __int64 v18; // r8
  __int64 v19; // rax
  unsigned __int64 v20; // rcx
  __int64 v22; // [rsp+20h] [rbp-38h]

  *(_QWORD *)(a1 + 32) = 7;
  v15 = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_WORD *)(a1 + 8) = 0;
  ((void (__fastcall *)(__int64, __int64, _QWORD, __int64, __int64))std::wstring::assign)(a1, a2, 0, -1, -2);
  *(_QWORD *)(a1 + 72) = 7;
  *(_QWORD *)(a1 + 64) = 0;
  *(_WORD *)(a1 + 48) = 0;
  ((void (__fastcall *)(__int64, __int64, _QWORD, __int64, __int64))std::wstring::assign)(a1 + 40, a3, 0, -1, v22);
  *(_DWORD *)(a1 + 80) = a4;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  v16 = (_QWORD *)(a1 + 104);
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_BYTE *)(a1 + 148) = a12;
  *(_DWORD *)(a1 + 152) = a8;
  *(_DWORD *)(a1 + 156) = a9;
  *(_DWORD *)(a1 + 160) = a10;
  if ( *(_DWORD *)(a1 + 80) )
  {
    if ( !ATL::CAutoVectorPtr<_CVDD>::Allocate((_QWORD *)(a1 + 88), *(unsigned int *)(a1 + 80))
      || !ATL::CAutoVectorPtr<unsigned long>::Allocate((_QWORD *)(a1 + 96), *(unsigned int *)(a1 + 80))
      || !ATL::CAutoVectorPtr<unsigned __int64>::Allocate((_QWORD *)(a1 + 104), *(unsigned int *)(a1 + 80)) )
    {
      ATL::AtlThrowImpl(-2147024882);
    }
    for ( i = 0; i < *(_DWORD *)(a1 + 80); ++i )
    {
      if ( *(_DWORD *)(a6 + 4LL * i) > 0x628u )
        ATL::AtlThrowImpl(-2147418113);
      memcpy_0(
        (void *)(1576LL * i + *(_QWORD *)(a1 + 88)),
        (const void *)(1576LL * i + a5),
        *(unsigned int *)(a6 + 4LL * i));
      if ( a7 )
        *(_QWORD *)(*v16 + 8LL * i) = *(_QWORD *)(a7 + 8LL * i);
      else
        *(_QWORD *)(*v16 + 8LL * i) = 0;
      *(_DWORD *)(*(_QWORD *)(a1 + 96) + 4LL * i) = *(_DWORD *)(a6 + 4LL * i);
    }
  }
  if ( a11 && *(_DWORD *)a11 && a11[1] )
  {
    try
    {
      a12 = 0;
      v18 = *(unsigned int *)a11;
      v19 = *(_QWORD *)(a1 + 120);
      if ( v19 )
        v20 = *(_QWORD *)(a1 + 128) - v19;
      else
        v20 = 0;
      if ( v20 >= v18 )
      {
        if ( v19 && v18 < *(_QWORD *)(a1 + 128) - v19 && v19 + v18 != *(_QWORD *)(a1 + 128) )
          *(_QWORD *)(a1 + 128) = v19 + v18;
      }
      else
      {
        if ( v19 )
          v15 = *(_QWORD *)(a1 + 128) - v19;
        std::vector<unsigned char>::_Insert_n(a1 + 112, *(char **)(a1 + 128), v18 - v15, &a12);
      }
      memcpy_0(*(void **)(a1 + 120), a11[1], *(unsigned int *)a11);
    }
    catch ( std::bad_alloc )
    {
      ATL::AtlThrowImpl(-2147024882);
    }
    *(_WORD *)(a1 + 146) = *((_WORD *)a11 + 8);
    *(_WORD *)(a1 + 144) = *((_WORD *)a11 + 9);
  }
  return a1;
}

```

## disassembly

```asm
0x180008d5c  mov     rax, rsp
0x180008d5f  mov     [rax+8], rcx
0x180008d63  push    rdi
0x180008d64  push    r12
0x180008d66  push    r13
0x180008d68  push    r14
0x180008d6a  push    r15
0x180008d6c  sub     rsp, 30h
0x180008d70  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180008d78  mov     [rax+10h], rbx
0x180008d7c  mov     [rax+18h], rsi
0x180008d80  mov     edi, r9d
0x180008d83  mov     rbx, r8
0x180008d86  mov     r14, rcx
0x180008d89  mov     r12d, 7
0x180008d8f  mov     [rcx+20h], r12
0x180008d93  xor     esi, esi
0x180008d95  mov     [rcx+18h], rsi
0x180008d99  mov     [rcx+8], si
0x180008d9d  or      r15, 0FFFFFFFFFFFFFFFFh
0x180008da1  mov     r9, r15
0x180008da4  xor     r8d, r8d
0x180008da7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180008dac  nop
0x180008dad  lea     rcx, [r14+28h]
0x180008db1  mov     [rcx+20h], r12
0x180008db5  mov     [rcx+18h], rsi
0x180008db9  mov     [rcx+8], si
0x180008dbd  mov     r9, r15
0x180008dc0  xor     r8d, r8d
0x180008dc3  mov     rdx, rbx
0x180008dc6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180008dcb  nop
0x180008dcc  mov     [r14+50h], edi
0x180008dd0  lea     rcx, [r14+58h]
0x180008dd4  mov     [rcx], rsi
0x180008dd7  mov     [r14+60h], rsi
0x180008ddb  lea     r12, [r14+68h]
0x180008ddf  mov     [r12], rsi
0x180008de3  mov     [r14+78h], rsi
0x180008de7  mov     [r14+80h], rsi
0x180008dee  mov     [r14+88h], rsi
0x180008df5  mov     al, [rsp+58h+arg_58]
0x180008dfc  mov     [r14+94h], al
0x180008e03  mov     eax, [rsp+58h+arg_38]
0x180008e0a  mov     [r14+98h], eax
0x180008e11  mov     eax, [rsp+58h+arg_40]
0x180008e18  mov     [r14+9Ch], eax
0x180008e1f  mov     eax, [rsp+58h+arg_48]
0x180008e26  mov     [r14+0A0h], eax
0x180008e2d  cmp     [r14+50h], esi
0x180008e31  jz      loc_180008F09
0x180008e37  mov     edx, [r14+50h]
0x180008e3b  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x180008e40  test    al, al
0x180008e42  jz      loc_180008EFE
0x180008e48  mov     edx, [r14+50h]
0x180008e4c  lea     rcx, [r14+60h]
0x180008e50  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x180008e55  test    al, al
0x180008e57  jz      loc_180008EFE
0x180008e5d  mov     edx, [r14+50h]
0x180008e61  mov     rcx, r12
0x180008e64  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x180008e69  test    al, al
0x180008e6b  jz      loc_180008EFE
0x180008e71  mov     r15d, esi
0x180008e74  cmp     [r14+50h], esi
0x180008e78  jbe     loc_180008F09
0x180008e7e  mov     r13, [rsp+58h+arg_28]
0x180008e86  mov     ebx, r15d
0x180008e89  cmp     dword ptr [r13+rbx*4+0], 628h
0x180008e92  ja      short loc_180008EF3
0x180008e94  mov     rcx, [r14+58h]
0x180008e98  imul    rax, rbx, 628h
0x180008e9f  mov     r8d, [r13+rbx*4+0]; Size
0x180008ea4  mov     rdx, [rsp+58h+arg_20]
0x180008eac  add     rdx, rax; Src
0x180008eaf  add     rcx, rax; void *
0x180008eb2  call    memcpy_0
0x180008eb7  mov     rax, [rsp+58h+arg_30]
0x180008ebf  test    rax, rax
0x180008ec2  jz      short loc_180008ED2
0x180008ec4  mov     rcx, [r12]
0x180008ec8  mov     rax, [rax+rbx*8]
0x180008ecc  mov     [rcx+rbx*8], rax
0x180008ed0  jmp     short loc_180008EDC
0x180008ed2  mov     rax, [r12]
0x180008ed6  xor     ecx, ecx
0x180008ed8  mov     [rax+rbx*8], rcx
0x180008edc  mov     rcx, [r14+60h]
0x180008ee0  mov     eax, [r13+rbx*4+0]
0x180008ee5  mov     [rcx+rbx*4], eax
0x180008ee8  inc     r15d
0x180008eeb  cmp     r15d, [r14+50h]
0x180008eef  jb      short loc_180008E86
0x180008ef1  jmp     short loc_180008F09
0x180008ef3  mov     ecx, 8000FFFFh; int
0x180008ef8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008efe  mov     ecx, 8007000Eh; int
0x180008f03  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008f09  mov     rbx, [rsp+58h+arg_50]
0x180008f11  test    rbx, rbx
0x180008f14  jz      loc_180008FFB
0x180008f1a  cmp     [rbx], esi
0x180008f1c  jz      loc_180008FFB
0x180008f22  cmp     [rbx+8], rsi
0x180008f26  jz      loc_180008FFB
0x180008f2c  mov     [rsp+58h+arg_58], sil
0x180008f34  mov     r8d, [rbx]
0x180008f37  mov     rax, [r14+78h]
0x180008f3b  test    rax, rax
0x180008f3e  jnz     short loc_180008F45
0x180008f40  mov     rcx, rsi
0x180008f43  jmp     short loc_180008F4F
0x180008f45  mov     rcx, [r14+80h]
0x180008f4c  sub     rcx, rax
0x180008f4f  cmp     rcx, r8
0x180008f52  jnb     short loc_180008F80
0x180008f54  test    rax, rax
0x180008f57  jz      short loc_180008F63
0x180008f59  mov     rsi, [r14+80h]
0x180008f60  sub     rsi, rax
0x180008f63  sub     r8, rsi
0x180008f66  lea     r9, [rsp+58h+arg_58]
0x180008f6e  mov     rdx, [r14+80h]
0x180008f75  lea     rcx, [r14+70h]
0x180008f79  call    ?_Insert_n@?$vector@EV?$allocator@E@std@@@std@@IEAAXV?$_Vector_iterator@EV?$allocator@E@std@@@2@_KAEBE@Z; std::vector<uchar>::_Insert_n(std::_Vector_iterator<uchar>,unsigned __int64,uchar const &)
0x180008f7e  jmp     short loc_180008FD2
0x180008f80  test    rax, rax
0x180008f83  jz      short loc_180008FD2
0x180008f85  mov     rdx, [r14+80h]
0x180008f8c  mov     rcx, rdx
0x180008f8f  sub     rcx, rax
0x180008f92  cmp     r8, rcx
0x180008f95  jnb     short loc_180008FD2
0x180008f97  lea     rcx, [rax+r8]
0x180008f9b  cmp     rcx, rdx
0x180008f9e  jz      short loc_180008FD2
0x180008fa0  mov     r8, rdx
0x180008fa3  sub     r8, rdx
0x180008fa6  cmp     rdx, rdx
0x180008fa9  cmova   r8, rsi
0x180008fad  test    r8, r8
0x180008fb0  jz      short loc_180008FCB
0x180008fb2  mov     r9, rdx
0x180008fb5  neg     r9
0x180008fb8  mov     al, [rdx]
0x180008fba  mov     [rcx], al
0x180008fbc  inc     rcx
0x180008fbf  inc     rdx
0x180008fc2  lea     rax, [r9+rdx]
0x180008fc6  cmp     rax, r8
0x180008fc9  jnz     short loc_180008FB8
0x180008fcb  mov     [r14+80h], rcx
0x180008fd2  mov     r8d, [rbx]; Size
0x180008fd5  mov     rdx, [rbx+8]; Src
0x180008fd9  mov     rcx, [r14+78h]; void *
0x180008fdd  call    memcpy_0
0x180008fe2  nop
0x180008fe3  movzx   eax, word ptr [rbx+10h]
0x180008fe7  mov     [r14+92h], ax
0x180008fef  movzx   eax, word ptr [rbx+12h]
0x180008ff3  mov     [r14+90h], ax
0x180008ffb  mov     rax, r14
0x180008ffe  mov     rbx, [rsp+58h+arg_8]
0x180009003  mov     rsi, [rsp+58h+arg_10]
0x180009008  add     rsp, 30h
0x18000900c  pop     r15
0x18000900e  pop     r14
0x180009010  pop     r13
0x180009012  pop     r12
0x180009014  pop     rdi
0x180009015  retn
```
