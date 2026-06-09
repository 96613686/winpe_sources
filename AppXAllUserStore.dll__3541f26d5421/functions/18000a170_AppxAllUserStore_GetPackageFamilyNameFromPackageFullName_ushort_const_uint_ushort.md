# AppxAllUserStore::GetPackageFamilyNameFromPackageFullName(ushort const *,uint *,ushort * *)

- ea: `0x18000a170`
- end: `0x18000a5f5`
- name: `?GetPackageFamilyNameFromPackageFullName@AppxAllUserStore@@YAJPEBGPEAIPEAPEAG@Z`
- size: `1157`
- prototype: `__int64 __fastcall(LPCWCH lpString1, const unsigned __int16 *, unsigned int *, unsigned __int16 **)`
- caller_count: `25`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004f1c`
- `0x18000b5cc`
- `0x18000b9fc`
- `0x18000bae8`
- `0x18000fed4`
- `0x180012dcc`
- `0x180015540`
- `0x180019ff8`
- `0x18001eaa8`
- `0x180020544`
- `0x180020794`
- `0x1800219d4`
- `0x18002977c`
- `0x180029fc0`
- `0x18002ae38`
- `0x18002bbf0`
- `0x18002cba0`
- `0x18002e8c0`
- `0x18002f2d0`
- `0x180031984`
- `0x180033248`
- `0x18003daf4`
- `0x18003e29c`
- `0x18003e3dc`
- `0x180043b10`

## callees

- `0x180007a10`
- `0x18000a170`
- `0x18000a600`
- `0x180016734`
- `0x180018248`
- `0x180048f08`
- `0x18004c972`
- `0x18004c98a`
- `0x18004c9d0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000a1ba`
- `ntdll!RtlAllocateHeap` at `0x18000a1ba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a2fe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a353`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a415`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a2fe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a353`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a415`

## string_xrefs

- `0x18000a57d`: `onecore\admin\appmodel\appxalluserstore\src\commonutilities.cpp`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::GetPackageFamilyNameFromPackageFullName(
        LPCWCH lpString1,
        unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int16 **a4)
{
  PVOID ProcessHeap; // rcx
  PVOID Heap; // r15
  __int64 v8; // rdx
  unsigned int v9; // eax
  signed int v10; // ebx
  const WCHAR *v11; // rsi
  int v12; // r12d
  __int64 v13; // r14
  LPCWCH v14; // rdx
  WCHAR *v15; // r8
  __int64 v16; // r9
  WCHAR v17; // cx
  unsigned __int64 v18; // rdi
  unsigned __int64 i; // rbx
  unsigned __int64 j; // rbx
  unsigned __int64 v21; // rdx
  __int64 result; // rax
  unsigned __int64 v23; // rbx
  unsigned __int64 v24; // rdi
  int v25; // r10d
  unsigned int v26; // edi
  unsigned __int16 *v27; // rbx
  unsigned int v28; // r11d
  __int64 v29; // r14
  unsigned __int16 *v30; // r9
  unsigned int v31; // eax
  int v32; // r8d
  const char *k; // rax
  int v34; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  unsigned int v36; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v37; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int *v38; // [rsp+38h] [rbp-C8h]
  _OWORD v39[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v40[16]; // [rsp+C0h] [rbp-40h] BYREF
  LPCWCH lpString1a; // [rsp+D0h] [rbp-30h]
  __int64 v42; // [rsp+D8h] [rbp-28h]
  void *Src; // [rsp+E8h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v38 = a3;
  ProcessHeap = ReservedForLocalUse::g_heap;
  if ( !ReservedForLocalUse::g_heap )
  {
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
    ReservedForLocalUse::g_heap = ProcessHeap;
  }
  Heap = RtlAllocateHeap(ProcessHeap, 0, 0x82u);
  if ( !Heap )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\commonutilities.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCase);
    return 2147942414LL;
  }
  memset_0(v40, 0, 0xF0u);
  v36 = 240;
  v9 = ARI::Identity::Convert<unsigned short,unsigned short *,unsigned short const *,PACKAGE_ID>::PackageIdBasicFromFullName(
         lpString1,
         v8,
         &v36,
         (__int64)v40);
  v10 = v9;
  if ( !v9 )
  {
    v11 = lpString1a;
    v12 = 65;
    v13 = 0;
    memset(v39, 0, sizeof(v39));
    if ( !lpString1a )
      goto LABEL_25;
    v14 = lpString1a;
    v15 = (WCHAR *)v39;
    v16 = 97;
    while ( 1 )
    {
      v17 = *v14;
      if ( !*v14 )
        break;
      if ( v9 >= 0x32 )
        goto LABEL_25;
      if ( v17 >= 0x61u )
      {
        if ( v17 > 0x7Au )
          goto LABEL_25;
      }
      else if ( v17 >= 0x41u )
      {
        if ( v17 > 0x5Au )
          goto LABEL_25;
      }
      else if ( (unsigned __int16)(v17 - 45) > 1u && (unsigned __int16)(v17 - 48) > 9u )
      {
        goto LABEL_25;
      }
      *v15 = v17;
      ++v14;
      ++v15;
      v13 = (unsigned int)(v13 + 1);
      v9 = v13;
    }
    if ( v9 < 3 )
      goto LABEL_25;
    v18 = (unsigned int)(v14 - v11);
    for ( i = 0; i < 0x18; ++i )
    {
      v15 = (WCHAR *)(2 * i);
      v16 = (unsigned int)dword_18004E190[4 * i];
      if ( v18 == v16 && CompareStringOrdinal(v11, v18, (&off_18004E198)[2 * i], v16, 1) == 2 )
        goto LABEL_25;
    }
    for ( j = 0; j < 0x17; ++j )
    {
      v15 = (WCHAR *)(2 * j);
      v21 = (unsigned int)dword_18004E020[4 * j];
      if ( v18 >= v21 && CompareStringOrdinal(v11, v21, (&off_18004E028)[2 * j], v21, 1) == 2 )
        goto LABEL_25;
    }
    if ( v18 && v11[v18 - 1] == 46 )
      goto LABEL_25;
    if ( v18 >= 5 )
    {
      v23 = 0;
      v24 = v18 - 5;
      while ( v23 <= v24 )
      {
        if ( CompareStringOrdinal(&v11[v23], 5, L".xn--", 5, 1) == 2 )
          goto LABEL_25;
        ++v23;
      }
    }
    v27 = (unsigned __int16 *)Src;
    v28 = 0;
    v37 = 0;
    *((_WORD *)v39 + v13) = 95;
    v29 = (unsigned int)(v13 + 1);
    v36 = v29;
    if ( v27 )
    {
      v30 = v27;
      v31 = 0;
LABEL_46:
      v32 = *v30;
      if ( (_WORD)v32 )
      {
        if ( v31 < 0xD )
        {
          for ( k = "1234567890abcdefghjkmnpqrstvwxyzABCDEFGHJKMNPQRSTVWXYZ"; *k; ++k )
          {
            if ( v32 == *k )
            {
              v31 = ++v28;
              ++v30;
              goto LABEL_46;
            }
          }
        }
        goto LABEL_25;
      }
      if ( v31 != 13 )
      {
LABEL_25:
        v10 = 87;
        goto LABEL_26;
      }
      v25 = v42;
    }
    else
    {
      if ( !(unsigned __int8)ReservedForLocalUse::IsPublisherValid<unsigned short,unsigned short const *>(
                               v42,
                               &v37,
                               v15,
                               v16) )
        goto LABEL_25;
      v28 = v37;
    }
    v26 = v29 + 13;
    if ( (unsigned int)(v29 + 14) > 0x41 )
    {
      v12 = v29 + 14;
      v10 = 122;
    }
    else
    {
      if ( v27 )
      {
        memcpy_0((char *)v39 + 2 * v29, v27, 2LL * v28);
LABEL_41:
        memcpy_0(Heap, v39, 2LL * v26);
        v12 = v26 + 1;
        *((_WORD *)Heap + v26) = 0;
        v10 = 0;
        goto LABEL_26;
      }
      v34 = ReservedForLocalUse::HashThePublisher<unsigned short,unsigned short const *>(
              v28,
              v25,
              v32,
              (unsigned int)&v36,
              (__int64)v39);
      v10 = v34;
      if ( v34 >= 0 )
      {
        v26 = v36;
        goto LABEL_41;
      }
      if ( (v34 & 0x1FFF0000) == 0x70000 )
        v10 = (unsigned __int16)v34;
    }
LABEL_26:
    if ( !v10 )
    {
      *(_QWORD *)v38 = Heap;
      result = 0;
      *(_DWORD *)a2 = v12;
      return result;
    }
  }
  if ( v10 > 0 )
    v10 = (unsigned __int16)v10 | 0x80070000;
  Common::GlobalHeap::Free(Heap);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000a170  push    rbp
0x18000a172  push    rbx
0x18000a173  push    r13
0x18000a175  push    r15
0x18000a177  lea     rbp, [rsp-0D8h]
0x18000a17f  sub     rsp, 1D8h
0x18000a186  mov     rax, cs:__security_cookie
0x18000a18d  xor     rax, rsp
0x18000a190  mov     [rbp+0F0h+var_40], rax
0x18000a197  mov     rbx, rcx
0x18000a19a  mov     [rsp+1F0h+var_1B8], r8
0x18000a19f  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x18000a1a6  mov     r13, rdx
0x18000a1a9  test    rcx, rcx
0x18000a1ac  jz      loc_18000A429
0x18000a1b2  xor     edx, edx; Flags
0x18000a1b4  mov     r8d, 82h; Size
0x18000a1ba  call    cs:__imp_RtlAllocateHeap
0x18000a1c0  mov     r15, rax
0x18000a1c3  test    rax, rax
0x18000a1c6  jz      loc_18000A576
0x18000a1cc  xor     edx, edx; Val
0x18000a1ce  mov     [rsp+1F0h+var_28], r12
0x18000a1d6  mov     r8d, 0F0h; Size
0x18000a1dc  lea     rcx, [rbp+0F0h+var_130]; void *
0x18000a1e0  call    memset_0
0x18000a1e5  lea     r9, [rbp+0F0h+var_130]
0x18000a1e9  mov     [rsp+1F0h+var_1C0], 0F0h
0x18000a1f1  lea     r8, [rsp+1F0h+var_1C0]
0x18000a1f6  mov     rcx, rbx; lpString1
0x18000a1f9  call    ?PackageIdBasicFromFullName@?$Convert@GPEAGPEBGUPACKAGE_ID@@@Identity@ARI@@SAJPEBGIPEAIPEAE@Z; ARI::Identity::Convert<ushort,ushort *,ushort const *,PACKAGE_ID>::PackageIdBasicFromFullName(ushort const *,uint,uint *,uchar *)
0x18000a1fe  mov     ebx, eax
0x18000a200  test    eax, eax
0x18000a202  jnz     loc_18000A5D9
0x18000a208  xorps   xmm0, xmm0
0x18000a20b  mov     [rsp+1F0h+arg_18], rsi
0x18000a213  mov     rsi, [rbp+0F0h+lpString1]
0x18000a217  mov     r12d, 41h ; 'A'
0x18000a21d  mov     [rsp+1F0h+var_30], r14
0x18000a225  xor     r14d, r14d
0x18000a228  mov     [rsp+1F0h+var_20], rdi
0x18000a230  movups  [rsp+1F0h+var_1B0], xmm0
0x18000a235  movups  [rsp+1F0h+var_1A0], xmm0
0x18000a23a  movups  [rsp+1F0h+var_190], xmm0
0x18000a23f  movups  [rsp+1F0h+var_180], xmm0
0x18000a244  movups  [rbp+0F0h+var_170], xmm0
0x18000a248  movups  [rbp+0F0h+var_160], xmm0
0x18000a24c  movups  [rbp+0F0h+var_150], xmm0
0x18000a250  movups  [rbp+0F0h+var_140], xmm0
0x18000a254  test    rsi, rsi
0x18000a257  jz      loc_18000A373
0x18000a25d  mov     rdx, rsi
0x18000a260  lea     r8, [rsp+1F0h+var_1B0]
0x18000a265  mov     r9d, 61h ; 'a'
0x18000a26b  nop     dword ptr [rax+rax+00h]
0x18000a270  movzx   ecx, word ptr [rdx]
0x18000a273  test    cx, cx
0x18000a276  jz      short loc_18000A2B6
0x18000a278  cmp     eax, 32h ; '2'
0x18000a27b  jnb     loc_18000A373
0x18000a281  cmp     r9w, cx
0x18000a285  jbe     loc_18000A59E
0x18000a28b  cmp     r12w, cx
0x18000a28f  jbe     loc_18000A4B0
0x18000a295  lea     eax, [rcx-2Dh]
0x18000a298  cmp     ax, 1
0x18000a29c  ja      loc_18000A442
0x18000a2a2  mov     [r8], cx
0x18000a2a6  add     rdx, 2
0x18000a2aa  add     r8, 2
0x18000a2ae  inc     r14d
0x18000a2b1  mov     eax, r14d
0x18000a2b4  jmp     short loc_18000A270
0x18000a2b6  cmp     eax, 3
0x18000a2b9  jb      loc_18000A373
0x18000a2bf  sub     rdx, rsi
0x18000a2c2  lea     rax, __ImageBase
0x18000a2c9  sar     rdx, 1
0x18000a2cc  mov     edi, edx
0x18000a2ce  xor     ebx, ebx
0x18000a2d0  cmp     rbx, 18h
0x18000a2d4  jnb     short loc_18000A315
0x18000a2d6  mov     r8, rbx
0x18000a2d9  add     r8, r8
0x18000a2dc  mov     r9d, ds:rva dword_18004E190[rax+r8*8]; cchCount2
0x18000a2e4  cmp     rdi, r9
0x18000a2e7  jnz     short loc_18000A310
0x18000a2e9  mov     r8, ds:rva off_18004E198[rax+r8*8]; lpString2
0x18000a2f1  mov     edx, edi; cchCount1
0x18000a2f3  mov     rcx, rsi; lpString1
0x18000a2f6  mov     [rsp+1F0h+bIgnoreCase], 1; bIgnoreCase
0x18000a2fe  call    cs:__imp_CompareStringOrdinal
0x18000a304  cmp     eax, 2
0x18000a307  jz      short loc_18000A373
0x18000a309  lea     rax, __ImageBase
0x18000a310  inc     rbx
0x18000a313  jmp     short loc_18000A2D0
0x18000a315  xor     ebx, ebx
0x18000a317  nop     word ptr [rax+rax+00000000h]
0x18000a320  cmp     rbx, 17h
0x18000a324  jnb     loc_18000A3CB
0x18000a32a  mov     r8, rbx
0x18000a32d  add     r8, r8
0x18000a330  mov     edx, ds:rva dword_18004E020[rax+r8*8]; cchCount1
0x18000a338  cmp     rdi, rdx
0x18000a33b  jb      short loc_18000A365
0x18000a33d  mov     r8, ds:rva off_18004E028[rax+r8*8]; lpString2
0x18000a345  mov     r9d, edx; cchCount2
0x18000a348  mov     rcx, rsi; lpString1
0x18000a34b  mov     [rsp+1F0h+bIgnoreCase], 1; bIgnoreCase
0x18000a353  call    cs:__imp_CompareStringOrdinal
0x18000a359  cmp     eax, 2
0x18000a35c  jz      short loc_18000A373
0x18000a35e  lea     rax, __ImageBase
0x18000a365  inc     rbx
0x18000a368  jmp     short loc_18000A320
0x18000a36a  cmp     eax, 0Dh
0x18000a36d  jz      loc_18000A454
0x18000a373  mov     ebx, 57h ; 'W'
0x18000a378  mov     r14, [rsp+1F0h+var_30]
0x18000a380  mov     rdi, [rsp+1F0h+var_20]
0x18000a388  mov     rsi, [rsp+1F0h+arg_18]
0x18000a390  test    ebx, ebx
0x18000a392  jnz     loc_18000A5D9
0x18000a398  mov     rax, [rsp+1F0h+var_1B8]
0x18000a39d  mov     [rax], r15
0x18000a3a0  xor     eax, eax
0x18000a3a2  mov     [r13+0], r12d
0x18000a3a6  mov     r12, [rsp+1F0h+var_28]
0x18000a3ae  mov     rcx, [rbp+0F0h+var_40]
0x18000a3b5  xor     rcx, rsp; StackCookie
0x18000a3b8  call    __security_check_cookie
0x18000a3bd  add     rsp, 1D8h
0x18000a3c4  pop     r15
0x18000a3c6  pop     r13
0x18000a3c8  pop     rbx
0x18000a3c9  pop     rbp
0x18000a3ca  retn
0x18000a3cb  test    rdi, rdi
0x18000a3ce  jz      short loc_18000A3D8
0x18000a3d0  cmp     word ptr [rsi+rdi*2-2], 2Eh ; '.'
0x18000a3d6  jz      short loc_18000A373
0x18000a3d8  cmp     rdi, 5
0x18000a3dc  jb      loc_18000A4BF
0x18000a3e2  xor     ebx, ebx
0x18000a3e4  add     rdi, 0FFFFFFFFFFFFFFFBh
0x18000a3e8  nop     dword ptr [rax+rax+00000000h]
0x18000a3f0  cmp     rbx, rdi
0x18000a3f3  ja      loc_18000A4BF
0x18000a3f9  mov     r9d, 5; cchCount2
0x18000a3ff  mov     [rsp+1F0h+bIgnoreCase], 1; bIgnoreCase
0x18000a407  mov     edx, r9d; cchCount1
0x18000a40a  lea     rcx, [rsi+rbx*2]; lpString1
0x18000a40e  lea     r8, String2; ".xn--"
0x18000a415  call    cs:__imp_CompareStringOrdinal
0x18000a41b  cmp     eax, 2
0x18000a41e  jz      loc_18000A373
0x18000a424  inc     rbx
0x18000a427  jmp     short loc_18000A3F0
0x18000a429  mov     rax, gs:60h
0x18000a432  mov     rcx, [rax+30h]
0x18000a436  mov     cs:?g_heap@ReservedForLocalUse@@3PEAXEA, rcx; void * ReservedForLocalUse::g_heap
0x18000a43d  jmp     loc_18000A1B2
0x18000a442  lea     eax, [rcx-30h]
0x18000a445  cmp     ax, 9
0x18000a449  jbe     loc_18000A2A2
0x18000a44f  jmp     loc_18000A373
0x18000a454  mov     r10, [rbp+0F0h+var_118]
0x18000a458  lea     edi, [r14+0Dh]
0x18000a45c  lea     eax, [rdi+1]
0x18000a45f  cmp     eax, r12d
0x18000a462  ja      loc_18000A569
0x18000a468  test    rbx, rbx
0x18000a46b  jz      loc_18000A531
0x18000a471  mov     r8d, r11d
0x18000a474  lea     rcx, [rsp+1F0h+var_1B0]
0x18000a479  add     r8, r8; Size
0x18000a47c  lea     rcx, [rcx+r14*2]; void *
0x18000a480  mov     rdx, rbx; Src
0x18000a483  call    memcpy_0
0x18000a488  mov     eax, edi
0x18000a48a  lea     rdx, [rsp+1F0h+var_1B0]; Src
0x18000a48f  mov     rcx, r15; void *
0x18000a492  lea     rbx, [rax+rax]
0x18000a496  mov     r8, rbx; Size
0x18000a499  call    memcpy_0
0x18000a49e  xor     eax, eax
0x18000a4a0  lea     r12d, [rdi+1]
0x18000a4a4  mov     [rbx+r15], ax
0x18000a4a9  xor     ebx, ebx
0x18000a4ab  jmp     loc_18000A378
0x18000a4b0  cmp     cx, 5Ah ; 'Z'
0x18000a4b4  ja      loc_18000A373
0x18000a4ba  jmp     loc_18000A2A2
0x18000a4bf  mov     rbx, [rbp+0F0h+Src]
0x18000a4c3  xor     r11d, r11d
0x18000a4c6  mov     ecx, 5Fh ; '_'
0x18000a4cb  mov     [rsp+1F0h+var_1BC], r11d
0x18000a4d0  mov     word ptr [rsp+r14*2+1F0h+var_1B0], cx
0x18000a4d6  inc     r14d
0x18000a4d9  mov     [rsp+1F0h+var_1C0], r14d
0x18000a4de  test    rbx, rbx
0x18000a4e1  jz      loc_18000A5AD
0x18000a4e7  mov     r9, rbx
0x18000a4ea  xor     eax, eax
0x18000a4ec  nop     dword ptr [rax+00h]
0x18000a4f0  movzx   r8d, word ptr [r9]
0x18000a4f4  test    r8w, r8w
0x18000a4f8  jz      loc_18000A36A
0x18000a4fe  cmp     eax, 0Dh
0x18000a501  jnb     loc_18000A373
0x18000a507  lea     rax, a1234567890abcd; "1234567890abcdefghjkmnpqrstvwxyzABCDEFG"...
0x18000a50e  xchg    ax, ax
0x18000a510  movsx   ecx, byte ptr [rax]
0x18000a513  test    cl, cl
0x18000a515  jz      loc_18000A373
0x18000a51b  cmp     r8d, ecx
0x18000a51e  jz      short loc_18000A525
0x18000a520  inc     rax
0x18000a523  jmp     short loc_18000A510
0x18000a525  inc     r11d
0x18000a528  mov     eax, r11d
0x18000a52b  add     r9, 2
0x18000a52f  jmp     short loc_18000A4F0
0x18000a531  lea     rax, [rsp+1F0h+var_1B0]
0x18000a536  mov     rdx, r10
0x18000a539  lea     r9, [rsp+1F0h+var_1C0]
0x18000a53e  mov     qword ptr [rsp+1F0h+bIgnoreCase], rax
0x18000a543  mov     ecx, r11d
0x18000a546  call    ??$HashThePublisher@GPEBG@ReservedForLocalUse@@YAJIPEBGIAEAIPEAG@Z; ReservedForLocalUse::HashThePublisher<ushort,ushort const *>(uint,ushort const *,uint,uint &,ushort *)
0x18000a54b  mov     ebx, eax
0x18000a54d  test    eax, eax
0x18000a54f  jns     short loc_18000A5D0
0x18000a551  and     eax, 1FFF0000h
0x18000a556  cmp     eax, 70000h
0x18000a55b  jnz     loc_18000A378
0x18000a561  movzx   ebx, bx
0x18000a564  jmp     loc_18000A378
0x18000a569  mov     r12d, eax
0x18000a56c  mov     ebx, 7Ah ; 'z'
0x18000a571  jmp     loc_18000A378
0x18000a576  mov     rcx, [rbp+0F8h]; this
0x18000a57d  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000a584  mov     r9d, 8007000Eh; char *
0x18000a58a  mov     edx, 1Ch; void *
0x18000a58f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a594  mov     eax, 8007000Eh
0x18000a599  jmp     loc_18000A3AE
0x18000a59e  cmp     cx, 7Ah ; 'z'
0x18000a5a2  ja      loc_18000A373
0x18000a5a8  jmp     loc_18000A2A2
0x18000a5ad  mov     r10, [rbp+0F0h+var_118]
0x18000a5b1  lea     rdx, [rsp+1F0h+var_1BC]
0x18000a5b6  mov     rcx, r10
0x18000a5b9  call    ??$IsPublisherValid@GPEBG@ReservedForLocalUse@@YA_NPEBGAEAI@Z; ReservedForLocalUse::IsPublisherValid<ushort,ushort const *>(ushort const *,uint &)
0x18000a5be  test    al, al
0x18000a5c0  jz      loc_18000A373
0x18000a5c6  mov     r11d, [rsp+1F0h+var_1BC]
0x18000a5cb  jmp     loc_18000A458
0x18000a5d0  mov     edi, [rsp+1F0h+var_1C0]
0x18000a5d4  jmp     loc_18000A488
0x18000a5d9  test    ebx, ebx
0x18000a5db  jle     short loc_18000A5E6
0x18000a5dd  movzx   ebx, bx
0x18000a5e0  or      ebx, 80070000h
0x18000a5e6  mov     rcx, r15; void *
0x18000a5e9  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18000a5ee  mov     eax, ebx
0x18000a5f0  jmp     loc_18000A3A6
```
