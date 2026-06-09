# CNetworkItemFactory::_GetNetworkItems(_GUID const *,ushort * * *,uint *)

- ea: `0x180004524`
- end: `0x180004883`
- name: `?_GetNetworkItems@CNetworkItemFactory@@AEAAJPEBU_GUID@@PEAPEAPEAGPEAI@Z`
- size: `863`
- prototype: `__int64 __fastcall(CNetworkItemFactory *__hidden this, const struct _GUID *, unsigned __int16 ***, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800035d0`
- `0x1800035f0`

## callees

- `0x180002e74`
- `0x180003090`
- `0x180004524`
- `0x18000599c`
- `0x1800076c8`
- `0x180007f80`
- `0x180009b98`
- `0x18000a7a7`
- `0x18000b010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800045f8`
- `ole32!CoTaskMemAlloc` at `0x1800045f8`
- `SHLWAPI!SHStrDupW` at `0x18000476c`
- `SHLWAPI!SHStrDupW` at `0x18000476c`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory::_GetNetworkItems(
        CNetworkItemFactory *this,
        const struct _GUID *a2,
        unsigned __int16 ***a3,
        unsigned int *a4)
{
  CNetworkItemFactory *v5; // r13
  char v6; // r15
  HRESULT v7; // ebx
  __int64 v8; // rdi
  unsigned int i; // ebx
  __int64 v10; // r8
  volatile signed __int32 *v11; // rcx
  signed __int32 v12; // r8d
  __int64 v13; // rax
  unsigned int v14; // r8d
  unsigned int v15; // esi
  unsigned int j; // edx
  unsigned __int16 **v17; // rax
  unsigned __int16 **v18; // r14
  unsigned int v19; // edi
  __int64 v20; // rax
  unsigned __int16 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rcx
  __int64 v24; // r10
  __int64 v25; // rdx
  __int64 v27; // r8
  bool k; // zf
  signed __int32 v29; // r9d
  __int128 v30; // [rsp+28h] [rbp-59h] BYREF
  __int64 v31; // [rsp+38h] [rbp-49h]
  int v32; // [rsp+40h] [rbp-41h]
  unsigned __int16 v33; // [rsp+44h] [rbp-3Dh]
  __int16 v34; // [rsp+48h] [rbp-39h]
  __int128 v35; // [rsp+58h] [rbp-29h] BYREF
  __int64 v36; // [rsp+68h] [rbp-19h]
  int v37; // [rsp+70h] [rbp-11h]
  __int16 v38; // [rsp+74h] [rbp-Dh]
  __int16 v39; // [rsp+78h] [rbp-9h]
  _BYTE v40[8]; // [rsp+80h] [rbp-1h] BYREF
  __int64 v41; // [rsp+88h] [rbp+7h]
  __int64 v42; // [rsp+90h] [rbp+Fh]
  __int64 v43; // [rsp+9Ch] [rbp+1Bh]

  v5 = this;
  v6 = 0;
  *a3 = 0;
  *a4 = 0;
  v7 = -2147467259;
  v8 = *((_QWORD *)this + 10);
  if ( v8 )
  {
    for ( i = 0; i < *(_DWORD *)(v8 + 20); ++i )
    {
      v10 = *(_QWORD *)(*(_QWORD *)(v8 + 24) + 8LL * i);
      if ( *(_BYTE *)(v10 + 153) )
      {
        v11 = (volatile signed __int32 *)(v10 + 24);
        v12 = *(_DWORD *)(v10 + 24);
        if ( (v12 & 0xFFFF8000) != 0 || v12 != _InterlockedCompareExchange(v11, v12 + 1, v12) )
          CReaderWriterLock3::_LockSpin(v11, 2);
      }
    }
    v13 = *((_QWORD *)v5 + 10);
    v14 = *(_DWORD *)(v13 + 20);
    if ( !v14 )
      goto LABEL_44;
    v15 = 0;
    for ( j = 0; j < v14; v15 += *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 24) + 8LL * j++) + 120LL) )
      ;
    if ( v15 )
    {
      v17 = (unsigned __int16 **)CoTaskMemAlloc(8LL * v15);
      v18 = v17;
      if ( v17 )
      {
        v7 = 0;
        memset_0(v17, 0, 8LL * v15);
        v30 = 0;
        v31 = 0;
        v32 = 0;
        v33 = 0;
        v34 = 0;
        v19 = 0;
        v20 = LKRhash::CLKRHashTable::Begin(*((_QWORD *)v5 + 10), v40);
        LKRhash::CTypedHashTable<CIDToNetworkItemHashTable,IDToNetworkItemRecord const,unsigned short const *,LKRhash::CLKRHashTable>::iterator::iterator(
          &v35,
          v20);
        *(_QWORD *)&v30 = v35;
        LKRhash::CLKRLinearHashTable_Iterator::operator=((char *)&v30 + 8, (char *)&v35 + 8);
        v34 = v39;
        if ( *((_QWORD *)&v35 + 1) && v38 != -1 )
          (*(void (__fastcall **)(_QWORD, __int64))(*((_QWORD *)&v35 + 1) + 56LL))(
            *(_QWORD *)(v36 + 8LL * v38 + 24),
            0xFFFFFFFFLL);
        while ( 1 )
        {
          v35 = 0;
          v36 = 0;
          v37 = 0;
          v38 = 0;
          v39 = 0;
          LKRhash::CTypedHashTable<CIDToNetworkItemHashTable,IDToNetworkItemRecord const,unsigned short const *,LKRhash::CLKRHashTable>::iterator::iterator(
            v40,
            &v35);
          v21 = v33;
          v22 = v31;
          if ( (v31 != v42 || v33 != (_WORD)v43) && v7 >= 0 && v19 < v15 )
            v6 = 1;
          if ( v41 && (_WORD)v43 != 0xFFFF )
          {
            (*(void (__fastcall **)(_QWORD, __int64))(v41 + 56))(
              *(_QWORD *)(v42 + 8LL * (__int16)v43 + 24),
              0xFFFFFFFFLL);
            v21 = v33;
            v22 = v31;
          }
          if ( !v6 )
            break;
          v6 = 0;
          if ( !a2
            || (v23 = *(_QWORD *)(v22 + 8LL * (__int16)v21 + 24),
                *(_QWORD *)&a2->Data1 == *(_QWORD *)(*(_QWORD *)(v23 + 8) + 176LL))
            && *(_QWORD *)a2->Data4 == _mm_srli_si128(*(__m128i *)(*(_QWORD *)(v23 + 8) + 176LL), 8).m128i_u64[0] )
          {
            v7 = SHStrDupW(**(LPCWSTR **)(v22 + 8LL * (__int16)v21 + 24), &v18[v19++]);
            v21 = v33;
            v22 = v31;
          }
          if ( (_QWORD)v30 && v34 >= 0 && *((_QWORD *)&v30 + 1) && v22 && v21 <= 3u )
          {
            if ( *(_QWORD *)(v22 + 8LL * (__int16)v21 + 24) )
              LKRhash::CLKRHashTable_Iterator::_Increment((LKRhash::CLKRHashTable_Iterator *)&v30, 1);
          }
        }
        if ( v7 < 0 )
        {
          FreeStringArray(v18, v19);
          v21 = v33;
          v22 = v31;
        }
        else
        {
          *a3 = v18;
          *a4 = v19;
        }
        v5 = this;
        if ( *((_QWORD *)&v30 + 1) && v21 != 0xFFFF )
          (*(void (__fastcall **)(_QWORD))(*((_QWORD *)&v30 + 1) + 56LL))(*(_QWORD *)(v22 + 8LL * (__int16)v21 + 24));
      }
      else
      {
        v7 = -2147024882;
      }
    }
    else
    {
LABEL_44:
      v7 = 1;
    }
    v24 = *((_QWORD *)v5 + 10);
    LODWORD(v25) = *(_DWORD *)(v24 + 20);
    while ( (_DWORD)v25 )
    {
      v25 = (unsigned int)(v25 - 1);
      v27 = *(_QWORD *)(*(_QWORD *)(v24 + 24) + 8 * v25);
      for ( k = *(_BYTE *)(v27 + 153) == 0;
            !k;
            k = v29 == _InterlockedCompareExchange((volatile signed __int32 *)(v27 + 24), v29 - 1, v29) )
      {
        v29 = *(_DWORD *)(v27 + 24);
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004524  mov     rax, rsp
0x180004527  mov     [rax+10h], rbx
0x18000452b  mov     [rax+20h], r9
0x18000452f  mov     [rax+18h], r8
0x180004533  mov     [rax+8], rcx
0x180004537  push    rbp
0x180004538  push    rsi
0x180004539  push    rdi
0x18000453a  push    r12
0x18000453c  push    r13
0x18000453e  push    r14
0x180004540  push    r15
0x180004542  lea     rbp, [rax-5Fh]
0x180004546  sub     rsp, 0A0h
0x18000454d  mov     r12, rdx
0x180004550  mov     r13, rcx
0x180004553  xor     r15d, r15d
0x180004556  mov     [r8], r15
0x180004559  mov     [r9], r15d
0x18000455c  mov     ebx, 80004005h
0x180004561  mov     rdi, [rcx+50h]
0x180004565  test    rdi, rdi
0x180004568  jz      loc_18000483D
0x18000456e  mov     ebx, r15d
0x180004571  cmp     [rdi+14h], r15d
0x180004575  jbe     short loc_1800045BC
0x180004577  mov     ecx, ebx
0x180004579  mov     rax, [rdi+18h]
0x18000457d  mov     r8, [rax+rcx*8]
0x180004581  cmp     [r8+99h], r15b
0x180004588  jz      short loc_1800045B5
0x18000458a  lea     rcx, [r8+18h]
0x18000458e  mov     r8d, [r8+18h]
0x180004592  test    r8d, 0FFFF8000h
0x180004599  jnz     short loc_1800045AB
0x18000459b  lea     edx, [r8+1]
0x18000459f  mov     eax, r8d
0x1800045a2  lock cmpxchg [rcx], edx
0x1800045a6  cmp     r8d, eax
0x1800045a9  jz      short loc_1800045B5
0x1800045ab  mov     edx, 2
0x1800045b0  call    ?_LockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z; CReaderWriterLock3::_LockSpin(CReaderWriterLock3::SPIN_TYPE)
0x1800045b5  inc     ebx
0x1800045b7  cmp     ebx, [rdi+14h]
0x1800045ba  jb      short loc_180004577
0x1800045bc  mov     rax, [r13+50h]
0x1800045c0  mov     r8d, [rax+14h]
0x1800045c4  test    r8d, r8d
0x1800045c7  jz      loc_18000482C
0x1800045cd  mov     esi, r15d
0x1800045d0  mov     edx, r15d
0x1800045d3  mov     r9, [rax+18h]
0x1800045d7  mov     eax, edx
0x1800045d9  mov     rcx, [r9+rax*8]
0x1800045dd  add     esi, [rcx+78h]
0x1800045e0  inc     edx
0x1800045e2  cmp     edx, r8d
0x1800045e5  jb      short loc_1800045D7
0x1800045e7  test    esi, esi
0x1800045e9  jz      loc_18000482C
0x1800045ef  mov     edi, esi
0x1800045f1  shl     rdi, 3
0x1800045f5  mov     rcx, rdi; cb
0x1800045f8  call    cs:__imp_CoTaskMemAlloc
0x1800045fe  mov     r14, rax
0x180004601  test    rax, rax
0x180004604  jz      loc_180004825
0x18000460a  mov     ebx, r15d
0x18000460d  mov     r8, rdi; Size
0x180004610  xor     edx, edx; Val
0x180004612  mov     rcx, rax; void *
0x180004615  call    memset_0
0x18000461a  xorps   xmm0, xmm0
0x18000461d  movdqu  [rbp+57h+var_B0], xmm0
0x180004622  mov     [rbp+57h+var_A0], r15
0x180004626  mov     [rbp+57h+var_98], r15d
0x18000462a  mov     [rbp+57h+var_94], r15w
0x18000462f  mov     [rbp+57h+var_90], r15w
0x180004634  mov     edi, r15d
0x180004637  lea     rdx, [rbp+57h+var_58]
0x18000463b  mov     rcx, [r13+50h]
0x18000463f  call    ?Begin@CLKRHashTable@LKRhash@@QEAA?AVCLKRHashTable_Iterator@2@XZ; LKRhash::CLKRHashTable::Begin(void)
0x180004644  mov     rdx, rax
0x180004647  lea     rcx, [rbp+57h+var_80]
0x18000464b  call    ??0iterator@?$CTypedHashTable@VCIDToNetworkItemHashTable@@$$CBVIDToNetworkItemRecord@@PEBGVCLKRHashTable@LKRhash@@@LKRhash@@IEAA@VCLKRHashTable_Iterator@2@@Z; LKRhash::CTypedHashTable<CIDToNetworkItemHashTable,IDToNetworkItemRecord const,ushort const *,LKRhash::CLKRHashTable>::iterator::iterator(LKRhash::CLKRHashTable_Iterator)
0x180004650  nop
0x180004651  mov     rax, qword ptr [rbp+57h+var_80]
0x180004655  mov     qword ptr [rbp+57h+var_B0], rax
0x180004659  lea     rdx, [rbp+57h+var_80+8]
0x18000465d  lea     rcx, [rbp+57h+var_B0+8]
0x180004661  call    ??4CLKRLinearHashTable_Iterator@LKRhash@@QEAAAEAV01@AEBV01@@Z; LKRhash::CLKRLinearHashTable_Iterator::operator=(LKRhash::CLKRLinearHashTable_Iterator const &)
0x180004666  movzx   eax, [rbp+57h+var_60]
0x18000466a  mov     [rbp+57h+var_90], ax
0x18000466e  mov     rax, qword ptr [rbp+57h+var_80+8]
0x180004672  or      ecx, 0FFFFFFFFh
0x180004675  test    rax, rax
0x180004678  jz      short loc_18000469A
0x18000467a  cmp     [rbp+57h+var_64], cx
0x18000467e  jz      short loc_18000469A
0x180004680  movsx   r8, [rbp+57h+var_64]
0x180004685  mov     edx, ecx
0x180004687  mov     rcx, [rbp+57h+var_70]
0x18000468b  mov     rcx, [rcx+r8*8+18h]
0x180004690  mov     rax, [rax+38h]
0x180004694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004699  nop
0x18000469a  or      r13d, 0FFFFFFFFh
0x18000469e  xorps   xmm0, xmm0
0x1800046a1  movdqu  [rbp+57h+var_80], xmm0
0x1800046a6  mov     [rbp+57h+var_70], r15
0x1800046aa  mov     [rbp+57h+var_68], r15d
0x1800046ae  mov     [rbp+57h+var_64], r15w
0x1800046b3  mov     [rbp+57h+var_60], r15w
0x1800046b8  lea     rdx, [rbp+57h+var_80]
0x1800046bc  lea     rcx, [rbp+57h+var_58]
0x1800046c0  call    ??0iterator@?$CTypedHashTable@VCIDToNetworkItemHashTable@@$$CBVIDToNetworkItemRecord@@PEBGVCLKRHashTable@LKRhash@@@LKRhash@@IEAA@VCLKRHashTable_Iterator@2@@Z; LKRhash::CTypedHashTable<CIDToNetworkItemHashTable,IDToNetworkItemRecord const,ushort const *,LKRhash::CLKRHashTable>::iterator::iterator(LKRhash::CLKRHashTable_Iterator)
0x1800046c5  movzx   r8d, [rbp+57h+var_94]
0x1800046ca  mov     rax, [rbp+57h+var_3C]
0x1800046ce  mov     r9, [rbp+57h+var_A0]
0x1800046d2  mov     r11, [rbp+57h+var_48]
0x1800046d6  cmp     r9, r11
0x1800046d9  jnz     short loc_1800046E1
0x1800046db  cmp     r8w, ax
0x1800046df  jz      short loc_1800046EC
0x1800046e1  test    ebx, ebx
0x1800046e3  js      short loc_1800046EC
0x1800046e5  cmp     edi, esi
0x1800046e7  jnb     short loc_1800046EC
0x1800046e9  mov     r15b, 1
0x1800046ec  mov     r10, [rbp+57h+var_50]
0x1800046f0  test    r10, r10
0x1800046f3  jz      short loc_180004719
0x1800046f5  cmp     ax, r13w
0x1800046f9  jz      short loc_180004719
0x1800046fb  movsx   rcx, ax
0x1800046ff  mov     edx, r13d
0x180004702  mov     rcx, [r11+rcx*8+18h]
0x180004707  mov     rax, [r10+38h]
0x18000470b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004710  movzx   r8d, [rbp+57h+var_94]
0x180004715  mov     r9, [rbp+57h+var_A0]
0x180004719  test    r15b, r15b
0x18000471c  jz      loc_1800047D1
0x180004722  xor     r15d, r15d
0x180004725  test    r12, r12
0x180004728  jz      short loc_18000475A
0x18000472a  movsx   rax, r8w
0x18000472e  mov     rcx, [r9+rax*8+18h]
0x180004733  mov     rax, [rcx+8]
0x180004737  movups  xmm0, xmmword ptr [rax+0B0h]
0x18000473e  movq    rax, xmm0
0x180004743  cmp     [r12], rax
0x180004747  jnz     short loc_18000477F
0x180004749  psrldq  xmm0, 8
0x18000474e  movq    rax, xmm0
0x180004753  cmp     [r12+8], rax
0x180004758  jnz     short loc_18000477F
0x18000475a  mov     eax, edi
0x18000475c  lea     rdx, [r14+rax*8]; ppwsz
0x180004760  movsx   rax, r8w
0x180004764  mov     rcx, [r9+rax*8+18h]
0x180004769  mov     rcx, [rcx]; psz
0x18000476c  call    cs:__imp_SHStrDupW
0x180004772  mov     ebx, eax
0x180004774  inc     edi
0x180004776  movzx   r8d, [rbp+57h+var_94]
0x18000477b  mov     r9, [rbp+57h+var_A0]
0x18000477f  cmp     qword ptr [rbp+57h+var_B0], r15
0x180004783  jz      loc_18000469E
0x180004789  cmp     [rbp+57h+var_90], r15w
0x18000478e  jl      loc_18000469E
0x180004794  cmp     qword ptr [rbp+57h+var_B0+8], r15
0x180004798  jz      loc_18000469E
0x18000479e  test    r9, r9
0x1800047a1  jz      loc_18000469E
0x1800047a7  cmp     r8w, 3
0x1800047ac  ja      loc_18000469E
0x1800047b2  movsx   rax, r8w
0x1800047b6  cmp     [r9+rax*8+18h], r15
0x1800047bb  jz      loc_18000469E
0x1800047c1  mov     dl, 1; bool
0x1800047c3  lea     rcx, [rbp+57h+var_B0]; this
0x1800047c7  call    ?_Increment@CLKRHashTable_Iterator@LKRhash@@IEAA_N_N@Z; LKRhash::CLKRHashTable_Iterator::_Increment(bool)
0x1800047cc  jmp     loc_18000469E
0x1800047d1  xor     r15d, r15d
0x1800047d4  test    ebx, ebx
0x1800047d6  js      short loc_1800047E7
0x1800047d8  mov     rax, [rbp+57h+arg_10]
0x1800047dc  mov     [rax], r14
0x1800047df  mov     rax, [rbp+57h+arg_18]
0x1800047e3  mov     [rax], edi
0x1800047e5  jmp     short loc_1800047FA
0x1800047e7  mov     edx, edi; unsigned int
0x1800047e9  mov     rcx, r14; unsigned __int16 **
0x1800047ec  call    ?FreeStringArray@@YAXPEAPEAGI@Z; FreeStringArray(ushort * *,uint)
0x1800047f1  movzx   r8d, [rbp+57h+var_94]
0x1800047f6  mov     r9, [rbp+57h+var_A0]
0x1800047fa  mov     rax, qword ptr [rbp+57h+var_B0+8]
0x1800047fe  test    rax, rax
0x180004801  mov     r13, [rbp+57h+arg_0]
0x180004805  jz      short loc_180004823
0x180004807  or      edx, 0FFFFFFFFh
0x18000480a  cmp     r8w, dx
0x18000480e  jz      short loc_180004823
0x180004810  movsx   rcx, r8w
0x180004814  mov     rcx, [r9+rcx*8+18h]
0x180004819  mov     rax, [rax+38h]
0x18000481d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004822  nop
0x180004823  jmp     short loc_180004831
0x180004825  mov     ebx, 8007000Eh
0x18000482a  jmp     short loc_180004831
0x18000482c  mov     ebx, 1
0x180004831  mov     r10, [r13+50h]
0x180004835  mov     edx, [r10+14h]
0x180004839  test    edx, edx
0x18000483b  jnz     short loc_18000485A
0x18000483d  mov     eax, ebx
0x18000483f  mov     rbx, [rsp+0D0h+arg_8]
0x180004847  add     rsp, 0A0h
0x18000484e  pop     r15
0x180004850  pop     r14
0x180004852  pop     r13
0x180004854  pop     r12
0x180004856  pop     rdi
0x180004857  pop     rsi
0x180004858  pop     rbp
0x180004859  retn
0x18000485a  dec     edx
0x18000485c  mov     rax, [r10+18h]
0x180004860  mov     r8, [rax+rdx*8]
0x180004864  cmp     [r8+99h], r15b
0x18000486b  jz      short loc_180004839
0x18000486d  mov     r9d, [r8+18h]
0x180004871  lea     ecx, [r9-1]
0x180004875  mov     eax, r9d
0x180004878  lock cmpxchg [r8+18h], ecx
0x18000487e  cmp     r9d, eax
0x180004881  jmp     short loc_18000486B
```
