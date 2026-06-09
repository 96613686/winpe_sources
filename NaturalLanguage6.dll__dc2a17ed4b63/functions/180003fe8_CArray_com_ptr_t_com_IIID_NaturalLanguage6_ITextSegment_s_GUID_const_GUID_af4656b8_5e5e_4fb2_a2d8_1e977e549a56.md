# CArray<_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>,CArrayAllocator_malloc>::SetArraySize(__int64)

- ea: `0x180003fe8`
- end: `0x18000418a`
- name: `?SetArraySize@?$CArray@V?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@VCArrayAllocator_malloc@@@@QEAAX_J@Z`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180004220`

## callees

- `0x180002778`
- `0x180002a50`
- `0x180003460`
- `0x180003fe8`
- `0x180005160`
- `0x180035640`
- `0x18003ed6c`

## import_xrefs

- `msvcrt!free` at `0x1800040fe`
- `msvcrt!free` at `0x1800040fe`

## pseudocode

```c
void __fastcall CArray<_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>,CArrayAllocator_malloc>::SetArraySize(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 *v6; // r14
  __int64 i; // rbx
  __int64 *j; // rsi
  _QWORD *v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rcx
  _QWORD *v12; // r8
  __int64 v13; // rdx
  _QWORD *v14; // rax
  __int64 v15; // rcx
  signed __int64 v16; // rax
  unsigned __int64 v17; // rbx
  size_t v18; // rax
  CArrayAllocator_malloc *v19; // rcx
  _BYTE pExceptionObject[104]; // [rsp+20h] [rbp-68h] BYREF
  const void *retaddr; // [rsp+88h] [rbp+0h]

  if ( a2 < 0 )
  {
    CNLException::CNLException((CNLException *)pExceptionObject, 2147942487LL, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  v4 = *(_QWORD *)(a1 + 8);
  if ( a2 )
  {
    v5 = *(_QWORD *)(a1 + 16);
    if ( a2 > v5 )
    {
      if ( *(_QWORD *)a1 )
      {
        CArray<NLG::ITrieIter *,CArrayAllocator_malloc>::ReallocWorker(a1);
        v11 = *(_QWORD *)(a1 + 8);
        v12 = (_QWORD *)(*(_QWORD *)a1 + 8 * v11);
        v13 = a2 - v11;
        if ( a2 != v11 )
        {
          do
          {
            *v12++ = 0;
            --v13;
          }
          while ( v13 );
        }
      }
      else
      {
        if ( v4 < 8 )
          v4 = 8;
        v16 = v4 + v5;
        v17 = a2;
        if ( a2 < v16 )
          v17 = v16;
        v18 = ULongLongMultRtlAsserted(8u, v17);
        v14 = CArrayAllocator_malloc::Alloc(v19, v18);
        *(_QWORD *)a1 = v14;
        v15 = a2;
        *(_QWORD *)(a1 + 16) = v17;
        do
        {
          *v14++ = 0;
          --v15;
        }
        while ( v15 );
      }
    }
    else if ( a2 > v4 )
    {
      v9 = (_QWORD *)(*(_QWORD *)a1 + 8 * v4);
      v10 = a2 - v4;
      if ( a2 != v4 )
      {
        do
        {
          *v9++ = 0;
          --v10;
        }
        while ( v10 );
      }
    }
    else if ( a2 < v4 )
    {
      v6 = (__int64 *)(*(_QWORD *)a1 + 8 * a2);
      for ( i = v4 - a2; i; --i )
        _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(v6++);
    }
    *(_QWORD *)(a1 + 8) = a2;
  }
  else
  {
    for ( j = *(__int64 **)a1; v4; --v4 )
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(j++);
    if ( !*(_BYTE *)(a1 + 24) )
    {
      if ( *(_QWORD *)a1 )
        free(*(void **)a1);
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 16) = 0;
    }
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180003fe8  push    rbx
0x180003fea  push    rbp
0x180003feb  push    rsi
0x180003fec  push    rdi
0x180003fed  push    r14
0x180003fef  sub     rsp, 60h
0x180003ff3  mov     rsi, rdx
0x180003ff6  mov     rdi, rcx
0x180003ff9  test    rdx, rdx
0x180003ffc  js      loc_18000412E
0x180004002  mov     rbx, [rcx+8]
0x180004006  test    rdx, rdx
0x180004009  jz      short loc_180004047
0x18000400b  mov     rax, [rcx+10h]
0x18000400f  cmp     rdx, rax
0x180004012  jg      loc_1800040AC
0x180004018  cmp     rdx, rbx
0x18000401b  jg      short loc_180004082
0x18000401d  jge     loc_1800040A6
0x180004023  mov     rax, [rcx]
0x180004026  lea     r14, [rax+rdx*8]
0x18000402a  sub     rbx, rdx
0x18000402d  jz      short loc_1800040A6
0x18000402f  mov     ebp, 8
0x180004034  mov     rcx, r14
0x180004037  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18000403c  add     r14, rbp
0x18000403f  sub     rbx, 1
0x180004043  jnz     short loc_180004034
0x180004045  jmp     short loc_1800040A6
0x180004047  mov     rsi, [rcx]
0x18000404a  test    rbx, rbx
0x18000404d  jz      short loc_180004065
0x18000404f  mov     ebp, 8
0x180004054  mov     rcx, rsi
0x180004057  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18000405c  add     rsi, rbp
0x18000405f  sub     rbx, 1
0x180004063  jnz     short loc_180004054
0x180004065  cmp     byte ptr [rdi+18h], 0
0x180004069  jz      loc_1800040F6
0x18000406f  mov     qword ptr [rdi+8], 0
0x180004077  add     rsp, 60h
0x18000407b  pop     r14
0x18000407d  pop     rdi
0x18000407e  pop     rsi
0x18000407f  pop     rbp
0x180004080  pop     rbx
0x180004081  retn
0x180004082  mov     rax, [rdi]
0x180004085  mov     rcx, rsi
0x180004088  lea     rdx, [rax+rbx*8]
0x18000408c  sub     rcx, rbx
0x18000408f  jz      short loc_1800040A6
0x180004091  mov     ebp, 8
0x180004096  mov     qword ptr [rdx], 0
0x18000409d  add     rdx, rbp
0x1800040a0  sub     rcx, 1
0x1800040a4  jnz     short loc_180004096
0x1800040a6  mov     [rdi+8], rsi
0x1800040aa  jmp     short loc_180004077
0x1800040ac  cmp     qword ptr [rcx], 0
0x1800040b0  mov     ebp, 8
0x1800040b5  jz      loc_180004157
0x1800040bb  cmp     rbx, rbp
0x1800040be  cmovl   rbx, rbp
0x1800040c2  add     rax, rbx
0x1800040c5  cmp     rsi, rax
0x1800040c8  cmovl   rdx, rax
0x1800040cc  call    ?ReallocWorker@?$CArray@PEAVITrieIter@NLG@@VCArrayAllocator_malloc@@@@AEAAX_J@Z; CArray<NLG::ITrieIter *,CArrayAllocator_malloc>::ReallocWorker(__int64)
0x1800040d1  mov     rcx, [rdi+8]
0x1800040d5  mov     rdx, rsi
0x1800040d8  mov     rax, [rdi]
0x1800040db  lea     r8, [rax+rcx*8]
0x1800040df  sub     rdx, rcx
0x1800040e2  jz      short loc_1800040A6
0x1800040e4  mov     qword ptr [r8], 0
0x1800040eb  add     r8, rbp
0x1800040ee  sub     rdx, 1
0x1800040f2  jz      short loc_1800040A6
0x1800040f4  jmp     short loc_1800040E4
0x1800040f6  mov     rcx, [rdi]; Block
0x1800040f9  test    rcx, rcx
0x1800040fc  jz      short loc_180004104
0x1800040fe  call    cs:__imp_free
0x180004104  mov     qword ptr [rdi], 0
0x18000410b  mov     qword ptr [rdi+10h], 0
0x180004113  jmp     loc_18000406F
0x180004118  mov     qword ptr [rax], 0
0x18000411f  add     rax, rbp
0x180004122  sub     rcx, 1
0x180004126  jz      loc_1800040A6
0x18000412c  jmp     short loc_180004118
0x18000412e  mov     r8, [rsp+88h]; void *
0x180004136  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18000413b  mov     edx, 80070057h; int
0x180004140  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180004145  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18000414c  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180004151  call    _CxxThrowException_0
0x180004157  cmp     rbx, rbp
0x18000415a  mov     rcx, rbp; unsigned __int64
0x18000415d  cmovl   rbx, rbp
0x180004161  add     rax, rbx
0x180004164  mov     rbx, rsi
0x180004167  cmp     rsi, rax
0x18000416a  cmovl   rbx, rax
0x18000416e  mov     rdx, rbx; unsigned __int64
0x180004171  call    ?ULongLongMultRtlAsserted@@YA_K_K0@Z; ULongLongMultRtlAsserted(unsigned __int64,unsigned __int64)
0x180004176  mov     rdx, rax; unsigned __int64
0x180004179  call    ?Alloc@CArrayAllocator_malloc@@QEAAPEAX_K@Z; CArrayAllocator_malloc::Alloc(unsigned __int64)
0x18000417e  mov     [rdi], rax
0x180004181  mov     rcx, rsi
0x180004184  mov     [rdi+10h], rbx
0x180004188  jmp     short loc_180004118
```
