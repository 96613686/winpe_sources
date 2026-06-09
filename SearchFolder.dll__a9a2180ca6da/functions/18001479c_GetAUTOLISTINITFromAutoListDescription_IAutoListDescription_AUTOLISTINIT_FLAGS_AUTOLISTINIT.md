# GetAUTOLISTINITFromAutoListDescription(IAutoListDescription *,AUTOLISTINIT_FLAGS,AUTOLISTINIT *)

- ea: `0x18001479c`
- end: `0x180014b71`
- name: `?GetAUTOLISTINITFromAutoListDescription@@YAJPEAUIAutoListDescription@@W4AUTOLISTINIT_FLAGS@@PEAUAUTOLISTINIT@@@Z`
- size: `981`
- prototype: `int __high(struct IAutoListDescription *, enum AUTOLISTINIT_FLAGS, struct AUTOLISTINIT *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013e0c`
- `0x18003e5d0`

## callees

- `0x1800038c0`
- `0x180006900`
- `0x1800076dc`
- `0x180009d00`
- `0x18000f718`
- `0x180010754`
- `0x180011eb8`
- `0x180013638`
- `0x18001479c`
- `0x18004a8a0`
- `0x18004a9e0`
- `0x18004aa00`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b31`

## pseudocode

```c
__int64 __fastcall GetAUTOLISTINITFromAutoListDescription(__int64 a1, char a2, __int64 a3)
{
  int v6; // r14d
  struct _DSA *v7; // rdi
  unsigned int v8; // ebx
  int inserted; // eax
  unsigned int v10; // ebx
  PVOID ItemPtr; // rax
  struct _DSA *v12; // rbx
  unsigned int v13; // r12d
  int v14; // eax
  unsigned int v15; // esi
  void *v16; // rcx
  rsize_t v17; // rsi
  int v18; // esi
  int v19; // eax
  rsize_t DestinationSize; // [rsp+38h] [rbp-48h] BYREF
  void *Source; // [rsp+40h] [rbp-40h]
  __int128 v24; // [rsp+48h] [rbp-38h] BYREF
  __int64 v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 pitem; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  memset_0((void *)a3, 0, 0xB0u);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 24LL))(a1, a3 + 8);
  if ( (a2 & 1) != 0 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 32LL))(a1, a3);
  v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 104LL))(a1, a3 + 16);
  if ( v6 < 0 )
    goto LABEL_35;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 120LL))(a1, a3 + 32);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 128LL))(a1, a3 + 36);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 136LL))(a1, a3 + 40);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 64LL))(a1, a3 + 44);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 72LL))(a1, a3 + 48);
  (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 48LL))(a1, a3 + 60, a3 + 80);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 88LL))(a1, a3 + 160);
  v7 = g_pfn_DSA_Create(20, 5);
  if ( !v7 )
  {
    v6 = -2147024882;
LABEL_35:
    ClearAutoListInit((struct AUTOLISTINIT *)a3);
    CoTaskMemFree(*(LPVOID *)(a3 + 88));
    CoTaskMemFree(*(LPVOID *)(a3 + 104));
    memset_0((void *)a3, 0, 0xB0u);
    return (unsigned int)v6;
  }
  pitem = 0;
  v27 = 0;
  v8 = 0;
  while ( (*(int (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)a1 + 40LL))(a1, v8, &pitem) >= 0 )
  {
    inserted = DSA_InsertItem(v7, 0x7FFFFFFF, &pitem);
    v6 = 0;
    if ( inserted == -1 )
      v6 = -2147024882;
    ++v8;
    if ( inserted == -1 )
      goto LABEL_32;
  }
  v10 = *(_DWORD *)v7;
  *(_DWORD *)(a3 + 84) = *(_DWORD *)v7;
  if ( !v10
    || (ItemPtr = g_pfn_DSA_GetItemPtr(v7, 0),
        v6 = SHCoDupArray<_tagpropertykey>(ItemPtr, v10, (void **)(a3 + 88)),
        v6 >= 0) )
  {
    v12 = g_pfn_DSA_Create(24, 5);
    if ( v12 )
    {
      v24 = 0;
      v25 = 0;
      v13 = 0;
      while ( (*(int (__fastcall **)(__int64, _QWORD, __int128 *, char *))(*(_QWORD *)a1 + 56LL))(
                a1,
                v13,
                &v24,
                (char *)&v25 + 4) >= 0 )
      {
        v14 = DSA_InsertItem(v12, 0x7FFFFFFF, &v24);
        v6 = 0;
        if ( v14 == -1 )
          v6 = -2147024882;
        ++v13;
        if ( v14 == -1 )
          goto LABEL_30;
      }
      v15 = *(_DWORD *)v12;
      *(_DWORD *)(a3 + 96) = *(_DWORD *)v12;
      if ( !v15 )
        goto LABEL_25;
      DestinationSize = 0;
      Source = g_pfn_DSA_GetItemPtr(v12, 0);
      *(_QWORD *)(a3 + 104) = 0;
      v6 = ULongLongMult(v15, 0x18u, &DestinationSize);
      if ( v6 >= 0 )
      {
        v17 = DestinationSize;
        v6 = CTCoAllocPolicy::Alloc(v16, 1u, DestinationSize, (void **)(a3 + 104));
        if ( v6 >= 0 )
          memcpy_s_0(*(void *const *)(a3 + 104), v17, Source, v17);
      }
      if ( v6 >= 0 )
      {
LABEL_25:
        (*(void (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)a1 + 80LL))(
          a1,
          &GUID_c92f9791_754f_4205_9d3d_3ec1e04b03f9,
          a3 + 112);
        if ( (a2 & 2) == 0
          || (v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64))(*(_QWORD *)a1 + 168LL))(
                      a1,
                      0,
                      &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798,
                      a3 + 128),
              v19 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)a1 + 176LL))(
                      a1,
                      &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
                      a3 + 136),
              v6 = v19,
              v18 >= 0)
          || v19 >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)a1 + 112LL))(
                 a1,
                 &GUID_d18f09e2_81c2_4217_a295_43b66fa4e495,
                 a3 + 120);
          if ( v6 >= 0 )
            (*(void (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)a1 + 160LL))(
              a1,
              &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
              a3 + 144);
        }
      }
LABEL_30:
      DSA_Destroy(v12);
    }
    else
    {
      v6 = -2147024882;
    }
  }
LABEL_32:
  DSA_Destroy(v7);
  if ( v6 < 0 )
    goto LABEL_35;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001479c  mov     [rsp-38h+arg_8], rbx
0x1800147a1  push    rbp
0x1800147a2  push    rsi
0x1800147a3  push    rdi
0x1800147a4  push    r12
0x1800147a6  push    r13
0x1800147a8  push    r14
0x1800147aa  push    r15
0x1800147ac  mov     rbp, rsp
0x1800147af  sub     rsp, 80h
0x1800147b6  mov     rax, cs:__security_cookie
0x1800147bd  xor     rax, rsp
0x1800147c0  mov     [rbp+var_8], rax
0x1800147c4  mov     r13, r8
0x1800147c7  mov     [rbp+var_50], edx
0x1800147ca  mov     ebx, edx
0x1800147cc  mov     r15, rcx
0x1800147cf  mov     rcx, r13; void *
0x1800147d2  xor     edx, edx; Val
0x1800147d4  mov     r8d, 0B0h; Size
0x1800147da  call    memset_0
0x1800147df  mov     rax, [r15]
0x1800147e2  lea     rdx, [r13+8]
0x1800147e6  mov     rcx, r15
0x1800147e9  mov     rax, [rax+18h]
0x1800147ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147f2  test    bl, 1
0x1800147f5  jz      short loc_180014809
0x1800147f7  mov     rax, [r15]
0x1800147fa  mov     rdx, r13
0x1800147fd  mov     rcx, r15
0x180014800  mov     rax, [rax+20h]
0x180014804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014809  mov     rax, [r15]
0x18001480c  lea     rdx, [r13+10h]
0x180014810  mov     rcx, r15
0x180014813  mov     rax, [rax+68h]
0x180014817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001481c  mov     r14d, eax
0x18001481f  test    eax, eax
0x180014821  js      loc_180014B1B
0x180014827  mov     rax, [r15]
0x18001482a  lea     rdx, [r13+20h]
0x18001482e  mov     rcx, r15
0x180014831  mov     rax, [rax+78h]
0x180014835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001483a  mov     rax, [r15]
0x18001483d  lea     rdx, [r13+24h]
0x180014841  mov     rcx, r15
0x180014844  mov     rax, [rax+80h]
0x18001484b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014850  mov     rax, [r15]
0x180014853  lea     rdx, [r13+28h]
0x180014857  mov     rcx, r15
0x18001485a  mov     rax, [rax+88h]
0x180014861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014866  mov     rax, [r15]
0x180014869  lea     rdx, [r13+2Ch]
0x18001486d  mov     rcx, r15
0x180014870  mov     rax, [rax+40h]
0x180014874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014879  mov     rax, [r15]
0x18001487c  lea     rdx, [r13+30h]
0x180014880  mov     rcx, r15
0x180014883  mov     rax, [rax+48h]
0x180014887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001488c  mov     rax, [r15]
0x18001488f  lea     r8, [r13+50h]
0x180014893  lea     rdx, [r13+3Ch]
0x180014897  mov     rcx, r15
0x18001489a  mov     rax, [rax+30h]
0x18001489e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148a3  mov     rax, [r15]
0x1800148a6  lea     rdx, [r13+0A0h]
0x1800148ad  mov     rcx, r15
0x1800148b0  mov     rax, [rax+58h]
0x1800148b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148b9  mov     r12d, 5
0x1800148bf  mov     edx, r12d; cItemGrow
0x1800148c2  lea     ecx, [r12+0Fh]; cbItem
0x1800148c7  call    cs:g_pfn_DSA_Create
0x1800148cd  mov     rdi, rax
0x1800148d0  test    rax, rax
0x1800148d3  jz      loc_180014B15
0x1800148d9  xor     eax, eax
0x1800148db  xorps   xmm0, xmm0
0x1800148de  movups  [rbp+pitem], xmm0
0x1800148e2  mov     [rbp+var_10], eax
0x1800148e5  xor     ebx, ebx
0x1800148e7  mov     esi, 8007000Eh
0x1800148ec  mov     rax, [r15]
0x1800148ef  lea     r8, [rbp+pitem]
0x1800148f3  mov     edx, ebx
0x1800148f5  mov     rcx, r15
0x1800148f8  mov     rax, [rax+28h]
0x1800148fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014901  test    eax, eax
0x180014903  js      short loc_18001492D
0x180014905  lea     r8, [rbp+pitem]; pitem
0x180014909  mov     edx, 7FFFFFFFh; i
0x18001490e  mov     rcx, rdi; hdsa
0x180014911  call    cs:__imp_DSA_InsertItem
0x180014917  xor     r14d, r14d
0x18001491a  cmp     eax, 0FFFFFFFFh
0x18001491d  cmovz   r14d, esi
0x180014921  inc     ebx
0x180014923  cmp     eax, 0FFFFFFFFh
0x180014926  jnz     short loc_1800148EC
0x180014928  jmp     loc_180014B05
0x18001492d  mov     ebx, [rdi]
0x18001492f  mov     [r13+54h], ebx
0x180014933  test    ebx, ebx
0x180014935  jz      short loc_18001495B
0x180014937  xor     edx, edx; i
0x180014939  mov     rcx, rdi; hdsa
0x18001493c  call    cs:g_pfn_DSA_GetItemPtr
0x180014942  lea     r8, [r13+58h]; void **
0x180014946  mov     edx, ebx; unsigned __int64
0x180014948  mov     rcx, rax; Source
0x18001494b  call    ??$SHCoDupArray@U_tagpropertykey@@@@YAJPEBU_tagpropertykey@@_KPEAPEAU0@@Z; SHCoDupArray<_tagpropertykey>(_tagpropertykey const *,unsigned __int64,_tagpropertykey * *)
0x180014950  mov     r14d, eax
0x180014953  test    eax, eax
0x180014955  js      loc_180014B05
0x18001495b  mov     edx, r12d; cItemGrow
0x18001495e  mov     ecx, 18h; cbItem
0x180014963  call    cs:g_pfn_DSA_Create
0x180014969  mov     rbx, rax
0x18001496c  test    rax, rax
0x18001496f  jz      loc_180014B02
0x180014975  xor     eax, eax
0x180014977  xorps   xmm0, xmm0
0x18001497a  movups  [rbp+var_38], xmm0
0x18001497e  mov     [rbp+var_28], rax
0x180014982  xor     r12d, r12d
0x180014985  mov     rax, [r15]
0x180014988  lea     r9, [rbp+var_28+4]
0x18001498c  lea     r8, [rbp+var_38]
0x180014990  mov     edx, r12d
0x180014993  mov     rcx, r15
0x180014996  mov     rax, [rax+38h]
0x18001499a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001499f  test    eax, eax
0x1800149a1  js      short loc_1800149CC
0x1800149a3  lea     r8, [rbp+var_38]; pitem
0x1800149a7  mov     edx, 7FFFFFFFh; i
0x1800149ac  mov     rcx, rbx; hdsa
0x1800149af  call    cs:__imp_DSA_InsertItem
0x1800149b5  xor     r14d, r14d
0x1800149b8  cmp     eax, 0FFFFFFFFh
0x1800149bb  cmovz   r14d, esi
0x1800149bf  inc     r12d
0x1800149c2  cmp     eax, 0FFFFFFFFh
0x1800149c5  jnz     short loc_180014985
0x1800149c7  jmp     loc_180014AF7
0x1800149cc  mov     esi, [rbx]
0x1800149ce  mov     [r13+60h], esi
0x1800149d2  test    esi, esi
0x1800149d4  jz      short loc_180014A47
0x1800149d6  xor     edx, edx; i
0x1800149d8  mov     rcx, rbx; hdsa
0x1800149db  call    cs:g_pfn_DSA_GetItemPtr
0x1800149e1  lea     r12, [r13+68h]
0x1800149e5  mov     [rbp+DestinationSize], 0
0x1800149ed  mov     ecx, esi; unsigned __int64
0x1800149ef  mov     [rbp+Source], rax
0x1800149f3  lea     r8, [rbp+DestinationSize]; unsigned __int64 *
0x1800149f7  mov     qword ptr [r12], 0
0x1800149ff  mov     edx, 18h; unsigned __int64
0x180014a04  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180014a09  mov     r14d, eax
0x180014a0c  test    eax, eax
0x180014a0e  js      short loc_180014A3E
0x180014a10  mov     rsi, [rbp+DestinationSize]
0x180014a14  mov     r9, r12; void **
0x180014a17  mov     r8, rsi; unsigned __int64
0x180014a1a  mov     edx, 1; unsigned int
0x180014a1f  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180014a24  mov     r14d, eax
0x180014a27  test    eax, eax
0x180014a29  js      short loc_180014A3E
0x180014a2b  mov     r8, [rbp+Source]; Source
0x180014a2f  mov     r9, rsi; SourceSize
0x180014a32  mov     rcx, [r12]; Destination
0x180014a36  mov     rdx, rsi; DestinationSize
0x180014a39  call    memcpy_s_0
0x180014a3e  test    r14d, r14d
0x180014a41  js      loc_180014AF7
0x180014a47  mov     rax, [r15]
0x180014a4a  lea     r8, [r13+70h]
0x180014a4e  lea     rdx, _GUID_c92f9791_754f_4205_9d3d_3ec1e04b03f9
0x180014a55  mov     rcx, r15
0x180014a58  mov     rax, [rax+50h]
0x180014a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a61  test    byte ptr [rbp+var_50], 2
0x180014a65  jz      short loc_180014AB6
0x180014a67  mov     rax, [r15]
0x180014a6a  lea     r9, [r13+80h]
0x180014a71  lea     r8, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798
0x180014a78  xor     edx, edx
0x180014a7a  mov     rcx, r15
0x180014a7d  mov     rax, [rax+0A8h]
0x180014a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a89  mov     rcx, [r15]
0x180014a8c  lea     r8, [r13+88h]
0x180014a93  mov     esi, eax
0x180014a95  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x180014a9c  mov     rax, [rcx+0B0h]
0x180014aa3  mov     rcx, r15
0x180014aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014aab  mov     r14d, eax
0x180014aae  test    esi, esi
0x180014ab0  jns     short loc_180014AB6
0x180014ab2  test    eax, eax
0x180014ab4  js      short loc_180014AF7
0x180014ab6  mov     rax, [r15]
0x180014ab9  lea     r8, [r13+78h]
0x180014abd  lea     rdx, _GUID_d18f09e2_81c2_4217_a295_43b66fa4e495
0x180014ac4  mov     rcx, r15
0x180014ac7  mov     rax, [rax+70h]
0x180014acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ad0  mov     r14d, eax
0x180014ad3  test    eax, eax
0x180014ad5  js      short loc_180014AF7
0x180014ad7  mov     rax, [r15]
0x180014ada  lea     r8, [r13+90h]
0x180014ae1  lea     rdx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x180014ae8  mov     rcx, r15
0x180014aeb  mov     rax, [rax+0A0h]
0x180014af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014af7  mov     rcx, rbx; hdsa
0x180014afa  call    cs:__imp_DSA_Destroy
0x180014b00  jmp     short loc_180014B05
0x180014b02  mov     r14d, esi
0x180014b05  mov     rcx, rdi; hdsa
0x180014b08  call    cs:__imp_DSA_Destroy
0x180014b0e  test    r14d, r14d
0x180014b11  jns     short loc_180014B47
0x180014b13  jmp     short loc_180014B1B
0x180014b15  mov     r14d, 8007000Eh
0x180014b1b  mov     rcx, r13; struct AUTOLISTINIT *
0x180014b1e  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x180014b23  mov     rcx, [r13+58h]; pv
0x180014b27  call    cs:__imp_CoTaskMemFree
0x180014b2d  mov     rcx, [r13+68h]; pv
0x180014b31  call    cs:__imp_CoTaskMemFree
0x180014b37  xor     edx, edx; Val
0x180014b39  mov     r8d, 0B0h; Size
0x180014b3f  mov     rcx, r13; void *
0x180014b42  call    memset_0
0x180014b47  mov     eax, r14d
0x180014b4a  mov     rcx, [rbp+var_8]
0x180014b4e  xor     rcx, rsp; StackCookie
0x180014b51  call    __security_check_cookie
0x180014b56  mov     rbx, [rsp+80h+arg_8]
0x180014b5e  add     rsp, 80h
0x180014b65  pop     r15
0x180014b67  pop     r14
0x180014b69  pop     r13
0x180014b6b  pop     r12
0x180014b6d  pop     rdi
0x180014b6e  pop     rsi
0x180014b6f  pop     rbp
0x180014b70  retn
```
