# SiSelectMetadataDrives(_SC_VERSION,_SP_IDS *,_SP_FD_IDS *,_SP_IDS *,_LIST_ENTRY *)

- ea: `0x1801b16bc`
- end: `0x1801b1b13`
- name: `?SiSelectMetadataDrives@@YAHW4_SC_VERSION@@PEAU_SP_IDS@@PEAU_SP_FD_IDS@@1PEAU_LIST_ENTRY@@@Z`
- size: `1111`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801b2c40`
- `0x1801b5b44`
- `0x1801baba0`

## callees

- `0x180006290`
- `0x180006cf4`
- `0x1801b0dec`
- `0x1801b16bc`
- `0x1801bbd90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b17cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b19f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b17cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b19f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b1a6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b1a6b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801b17bb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801b17bb`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1801b19ac`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1801b1a5d`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1801b19ac`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1801b1a5d`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1801b194f`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1801b194f`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1801b19cf`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1801b1a46`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1801b19cf`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1801b1a46`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1801b18dc`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1801b18dc`
- `bcrypt!BCryptGenRandom` at `0x1801b1935`
- `bcrypt!BCryptGenRandom` at `0x1801b1935`

## pseudocode

```c
__int64 __fastcall SiSelectMetadataDrives(unsigned int a1, __int64 a2, int *a3, __int64 a4, __int64 *a5)
{
  unsigned int v9; // edx
  __int64 v10; // rcx
  int v11; // r12d
  __int64 *k; // rax
  _DWORD *v13; // rax
  __int64 v14; // r8
  __int64 v15; // rcx
  _QWORD *v16; // rax
  int v17; // r14d
  int v18; // ebx
  _QWORD **v19; // rsi
  _QWORD *v20; // rax
  unsigned int v21; // ecx
  unsigned int v22; // r15d
  struct _RTL_AVL_TABLE *v23; // r14
  struct _RTL_AVL_TABLE *Parent; // rsi
  _QWORD **v25; // r13
  _QWORD *i; // rbx
  _QWORD *v27; // rdx
  int LeftChild; // eax
  int v29; // esi
  signed int v30; // r13d
  struct _RTL_AVL_TABLE *j; // rbx
  DWORD v32; // ecx
  _QWORD *v33; // rax
  BOOLEAN v34; // al
  _QWORD **v35; // rbx
  _QWORD *v36; // rax
  __int64 v37; // rcx
  _QWORD *v38; // rdx
  _QWORD *v39; // r14
  struct _RTL_AVL_TABLE *v40; // rsi
  PVOID v41; // rax
  __int64 *v42; // rcx
  __int64 *v43; // rax
  __int64 v44; // rax
  unsigned __int8 NewElement[4]; // [rsp+30h] [rbp-A1h] BYREF
  __int64 v47; // [rsp+38h] [rbp-99h] BYREF
  __int64 *v48; // [rsp+40h] [rbp-91h]
  _QWORD *Buffer; // [rsp+48h] [rbp-89h] BYREF
  PVOID v50; // [rsp+50h] [rbp-81h] BYREF
  PVOID RestartKey; // [rsp+58h] [rbp-79h] BYREF
  __int64 v52; // [rsp+60h] [rbp-71h] BYREF
  _QWORD v53[11]; // [rsp+68h] [rbp-69h] BYREF
  _QWORD v54[2]; // [rsp+C0h] [rbp-11h] BYREF

  v52 = 0;
  memset_0(v53, 0, 0x68u);
  Buffer = 0;
  v48 = &v47;
  v9 = 0;
  RestartKey = 0;
  v47 = (__int64)&v47;
  *(_DWORD *)NewElement = 1;
  do
  {
    v10 = 2LL * (int)v9++;
    v53[v10] = &v53[v10 - 1];
    v53[v10 - 1] = &v53[v10 - 1];
  }
  while ( v9 < 7 );
  v11 = 6;
  if ( a1 > 8 )
  {
    *(_DWORD *)NewElement = SiIncludeDrivesForMetadata(a1, a2, a3, a4, a5, &v47);
    if ( *(_DWORD *)NewElement && (__int64 *)v47 != &v47 )
    {
      v13 = LocalAlloc(0x40u, 0xD8u);
      if ( v13 )
      {
        *v13 = 6;
        v15 = v54[0];
        if ( *(_QWORD **)(v54[0] + 8LL) != v54 )
          goto LABEL_63;
        v16 = v13 + 50;
        v17 = 6;
        *v16 = v54[0];
        v16[1] = v54;
        *(_QWORD *)(v15 + 8) = v16;
        v54[0] = v16;
        if ( !a3 || (v18 = *a3, v18 <= 1) )
          v18 = 5;
        while ( 1 )
        {
          v19 = (_QWORD **)&v53[2 * (unsigned int)v18 - 1];
          *(_DWORD *)NewElement = SiGetFaultDomains(&v47, (unsigned int)v18, v14, v19);
          if ( !*(_DWORD *)NewElement )
            break;
          if ( v18 != 1 )
          {
            v20 = *v19;
            v21 = 0;
            if ( *v19 == v19 )
            {
LABEL_24:
              v17 = v18;
            }
            else
            {
              v14 = *(_QWORD *)&GUID_NULL.Data1;
              while ( *(_QWORD *)((char *)v20 - 196) != *(_QWORD *)&GUID_NULL.Data1
                   || *(_QWORD *)((char *)v20 - 188) != *(_QWORD *)GUID_NULL.Data4 )
              {
                v20 = (_QWORD *)*v20;
                ++v21;
                if ( v20 == v19 )
                {
                  if ( v21 >= 5 )
                    goto LABEL_26;
                  goto LABEL_24;
                }
              }
            }
            if ( --v18 > 0 )
              continue;
          }
LABEL_26:
          v22 = 0;
          v23 = (struct _RTL_AVL_TABLE *)&v53[2 * v17 - 1];
          Parent = (struct _RTL_AVL_TABLE *)v23->BalancedRoot.Parent;
          if ( (struct _RTL_AVL_TABLE *)v23->BalancedRoot.Parent != v23 )
          {
            v25 = (_QWORD **)&v53[2 * v18 - 1];
            while ( 2 )
            {
              RtlInitializeGenericTableAvl(
                Parent - 1,
                SiFdTableCompareRoutine,
                SiTableAllocateRoutine,
                SiTableFreeRoutine,
                0);
              for ( i = *v25; i != v25; i = (_QWORD *)*i )
              {
                v27 = i - 25;
                Buffer = i - 25;
                LeftChild = (int)Parent[-2].BalancedRoot.LeftChild;
                if ( LeftChild == 6
                  || *(struct _RTL_BALANCED_LINKS **)((char *)&v27[2 * (unsigned int)(LeftChild - 2) + 2] + 4) == *(struct _RTL_BALANCED_LINKS **)((char *)&Parent[-2].BalancedRoot.LeftChild + 4)
                  && *(struct _RTL_BALANCED_LINKS **)((char *)&v27[2 * (unsigned int)(LeftChild - 2) + 3] + 4) == *(struct _RTL_BALANCED_LINKS **)((char *)&Parent[-2].BalancedRoot.RightChild + 4) )
                {
                  BCryptGenRandom(0, (PUCHAR)(v27[11] + 16LL), 4u, 2u);
                  RtlInsertElementGenericTableAvl(Parent - 1, &Buffer, 8u, NewElement);
                  if ( !*(_DWORD *)NewElement )
                  {
                    v32 = 5010;
LABEL_46:
                    SetLastError(v32);
                    goto LABEL_47;
                  }
                }
              }
              Parent = (struct _RTL_AVL_TABLE *)Parent->BalancedRoot.Parent;
              ++v22;
              if ( Parent != v23 )
                continue;
              break;
            }
          }
          v29 = 0;
          v30 = (v22 + 4 - (v22 + 4) % v22) / v22;
          if ( v30 > 0 )
          {
            while ( 2 )
            {
              for ( j = (struct _RTL_AVL_TABLE *)v23->BalancedRoot.Parent;
                    j != v23;
                    j = (struct _RTL_AVL_TABLE *)j->BalancedRoot.Parent )
              {
                RestartKey = 0;
                v33 = RtlEnumerateGenericTableWithoutSplayingAvl(j - 1, &RestartKey);
                if ( v33 )
                {
                  Buffer = (_QWORD *)*v33;
                  *(_DWORD *)(Buffer[11] + 20LL) |= 4u;
                  v34 = RtlDeleteElementGenericTableAvl(j - 1, v33);
                  *(_DWORD *)NewElement = v34;
                  if ( !v34 )
                  {
                    v32 = 1168;
                    goto LABEL_46;
                  }
                }
              }
              if ( ++v29 < v30 )
                continue;
              break;
            }
          }
          goto LABEL_47;
        }
      }
      else
      {
        SetLastError(0x5AAu);
        *(_DWORD *)NewElement = 0;
      }
    }
  }
  else
  {
    for ( k = (__int64 *)*a5; k != a5; k = (__int64 *)*k )
      *((_DWORD *)k + 5) |= 4u;
  }
  do
  {
LABEL_47:
    v35 = (_QWORD **)&v53[2 * (unsigned int)v11 - 1];
    while ( 1 )
    {
      v36 = *v35;
      if ( *v35 == v35 )
        break;
      v37 = *v36;
      if ( *(_QWORD **)(*v36 + 8LL) != v36 )
        goto LABEL_63;
      v38 = (_QWORD *)v36[1];
      if ( (_QWORD *)*v38 != v36 )
        goto LABEL_63;
      v39 = v36 - 25;
      *v38 = v37;
      v40 = (struct _RTL_AVL_TABLE *)(v36 - 13);
      *(_QWORD *)(v37 + 8) = v38;
      while ( 1 )
      {
        v50 = 0;
        v41 = RtlEnumerateGenericTableWithoutSplayingAvl(v40, &v50);
        if ( !v41 )
          break;
        RtlDeleteElementGenericTableAvl(v40, v41);
      }
      LocalFree(v39);
    }
    --v11;
  }
  while ( v11 >= 0 );
  if ( *(__int64 **)(*a5 + 8) != a5
    || (v42 = (__int64 *)a5[1], (__int64 *)*v42 != a5)
    || *(__int64 **)(v47 + 8) != &v47
    || (__int64 *)*v48 != &v47
    || (*v42 = (__int64)&v47,
        v43 = v48,
        a5[1] = (__int64)v48,
        *v43 = (__int64)a5,
        v44 = v47,
        v48 = v42,
        *(__int64 **)(v47 + 8) != &v47)
    || (__int64 *)*v42 != &v47 )
  {
LABEL_63:
    __fastfail(3u);
  }
  *v42 = v47;
  *(_QWORD *)(v44 + 8) = v42;
  return *(unsigned int *)NewElement;
}

```

## disassembly

```asm
0x1801b16bc  push    rbp
0x1801b16be  push    rbx
0x1801b16bf  push    rsi
0x1801b16c0  push    rdi
0x1801b16c1  push    r12
0x1801b16c3  push    r13
0x1801b16c5  push    r14
0x1801b16c7  push    r15
0x1801b16c9  lea     rbp, [rsp-17h]
0x1801b16ce  sub     rsp, 0E8h
0x1801b16d5  mov     rax, cs:__security_cookie
0x1801b16dc  xor     rax, rsp
0x1801b16df  mov     [rbp+4Fh+var_50], rax
0x1801b16e3  mov     rdi, [rbp+4Fh+arg_20]
0x1801b16e7  mov     r14, rdx
0x1801b16ea  xor     edx, edx; Val
0x1801b16ec  mov     [rbp+4Fh+var_C0], 0
0x1801b16f4  mov     rbx, r8
0x1801b16f7  mov     esi, ecx
0x1801b16f9  lea     rcx, [rbp+4Fh+var_B8]; void *
0x1801b16fd  mov     r15, r9
0x1801b1700  lea     r8d, [rdx+68h]; Size
0x1801b1704  call    memset_0
0x1801b1709  lea     rax, [rsp+120h+var_E8]
0x1801b170e  mov     [rsp+120h+Buffer], 0
0x1801b1717  mov     [rsp+120h+var_E0], rax
0x1801b171c  xor     edx, edx
0x1801b171e  lea     rax, [rsp+120h+var_E8]
0x1801b1723  mov     [rbp+4Fh+RestartKey], 0
0x1801b172b  mov     [rsp+120h+var_E8], rax
0x1801b1730  mov     dword ptr [rsp+120h+NewElement], 1
0x1801b1738  movsxd  rcx, edx
0x1801b173b  lea     rax, [rbp+4Fh+var_C0]
0x1801b173f  shl     rcx, 4
0x1801b1743  inc     edx
0x1801b1745  add     rax, rcx
0x1801b1748  mov     [rbp+rcx+4Fh+var_B8], rax
0x1801b174d  mov     [rax], rax
0x1801b1750  cmp     edx, 7
0x1801b1753  jb      short loc_1801B1738
0x1801b1755  mov     r12d, 6
0x1801b175b  cmp     esi, 8
0x1801b175e  ja      short loc_1801B1776
0x1801b1760  mov     rax, [rdi]
0x1801b1763  jmp     short loc_1801B176C
0x1801b1765  or      dword ptr [rax+14h], 4
0x1801b1769  mov     rax, [rax]
0x1801b176c  cmp     rax, rdi
0x1801b176f  jnz     short loc_1801B1765
0x1801b1771  jmp     loc_1801B19FC
0x1801b1776  lea     rax, [rsp+120h+var_E8]
0x1801b177b  mov     r9, r15
0x1801b177e  mov     [rsp+120h+var_F8], rax
0x1801b1783  mov     r8, rbx
0x1801b1786  mov     rdx, r14
0x1801b1789  mov     [rsp+120h+TableContext], rdi
0x1801b178e  mov     ecx, esi
0x1801b1790  call    ?SiIncludeDrivesForMetadata@@YAHW4_SC_VERSION@@PEAU_SP_IDS@@PEAU_SP_FD_IDS@@1PEAU_LIST_ENTRY@@3@Z; SiIncludeDrivesForMetadata(_SC_VERSION,_SP_IDS *,_SP_FD_IDS *,_SP_IDS *,_LIST_ENTRY *,_LIST_ENTRY *)
0x1801b1795  mov     dword ptr [rsp+120h+NewElement], eax
0x1801b1799  test    eax, eax
0x1801b179b  jz      loc_1801B19FC
0x1801b17a1  lea     rax, [rsp+120h+var_E8]
0x1801b17a6  cmp     [rsp+120h+var_E8], rax
0x1801b17ab  jz      loc_1801B19FC
0x1801b17b1  mov     edx, 0D8h; uBytes
0x1801b17b6  mov     ecx, 40h ; '@'; uFlags
0x1801b17bb  call    cs:__imp_LocalAlloc
0x1801b17c1  test    rax, rax
0x1801b17c4  jnz     short loc_1801B17DE
0x1801b17c6  mov     ecx, 5AAh; dwErrCode
0x1801b17cb  call    cs:__imp_SetLastError
0x1801b17d1  mov     dword ptr [rsp+120h+NewElement], 0
0x1801b17d9  jmp     loc_1801B19FC
0x1801b17de  mov     [rax], r12d
0x1801b17e1  lea     rdx, [rbp+4Fh+var_60]
0x1801b17e5  mov     rcx, [rbp+4Fh+var_60]
0x1801b17e9  cmp     [rcx+8], rdx
0x1801b17ed  jnz     loc_1801B1B0C
0x1801b17f3  add     rax, 0C8h
0x1801b17f9  lea     rdx, [rbp+4Fh+var_60]
0x1801b17fd  mov     r14d, r12d
0x1801b1800  mov     [rax], rcx
0x1801b1803  mov     [rax+8], rdx
0x1801b1807  mov     [rcx+8], rax
0x1801b180b  mov     [rbp+4Fh+var_60], rax
0x1801b180f  test    rbx, rbx
0x1801b1812  jz      short loc_1801B181B
0x1801b1814  mov     ebx, [rbx]
0x1801b1816  cmp     ebx, 1
0x1801b1819  jg      short loc_1801B1820
0x1801b181b  mov     ebx, 5
0x1801b1820  mov     eax, ebx
0x1801b1822  lea     rsi, [rbp+4Fh+var_C0]
0x1801b1826  shl     rax, 4
0x1801b182a  lea     rcx, [rsp+120h+var_E8]
0x1801b182f  add     rsi, rax
0x1801b1832  mov     edx, ebx
0x1801b1834  mov     r9, rsi
0x1801b1837  call    ?SiGetFaultDomains@@YAHPEAU_LIST_ENTRY@@W4_SC_FD_TYPE@@H0@Z; SiGetFaultDomains(_LIST_ENTRY *,_SC_FD_TYPE,int,_LIST_ENTRY *)
0x1801b183c  mov     dword ptr [rsp+120h+NewElement], eax
0x1801b1840  test    eax, eax
0x1801b1842  jz      loc_1801B19FC
0x1801b1848  cmp     ebx, 1
0x1801b184b  jz      short loc_1801B188F
0x1801b184d  mov     rax, [rsi]
0x1801b1850  xor     ecx, ecx
0x1801b1852  cmp     rax, rsi
0x1801b1855  jz      short loc_1801B1886
0x1801b1857  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x1801b185e  mov     r8, qword ptr cs:GUID_NULL.Data1
0x1801b1865  cmp     [rax-0C4h], r8
0x1801b186c  jnz     short loc_1801B1877
0x1801b186e  cmp     [rax-0BCh], rdx
0x1801b1875  jz      short loc_1801B1889
0x1801b1877  mov     rax, [rax]
0x1801b187a  inc     ecx
0x1801b187c  cmp     rax, rsi
0x1801b187f  jnz     short loc_1801B1865
0x1801b1881  cmp     ecx, 5
0x1801b1884  jnb     short loc_1801B188F
0x1801b1886  mov     r14d, ebx
0x1801b1889  dec     ebx
0x1801b188b  test    ebx, ebx
0x1801b188d  jg      short loc_1801B1820
0x1801b188f  movsxd  rax, r14d
0x1801b1892  xor     r15d, r15d
0x1801b1895  shl     rax, 4
0x1801b1899  lea     r14, [rbp+4Fh+var_C0]
0x1801b189d  add     r14, rax
0x1801b18a0  mov     rsi, [r14]
0x1801b18a3  cmp     rsi, r14
0x1801b18a6  jz      loc_1801B1973
0x1801b18ac  movsxd  rax, ebx
0x1801b18af  lea     r13, [rbp+4Fh+var_C0]
0x1801b18b3  shl     rax, 4
0x1801b18b7  add     r13, rax
0x1801b18ba  lea     rcx, [rsi-68h]; Table
0x1801b18be  mov     [rsp+120h+TableContext], 0; TableContext
0x1801b18c7  lea     r9, ?SiTableFreeRoutine@@YAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x1801b18ce  lea     r8, ?SiTableAllocateRoutine@@YAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x1801b18d5  lea     rdx, ?SiFdTableCompareRoutine@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x1801b18dc  call    cs:__imp_RtlInitializeGenericTableAvl
0x1801b18e2  mov     rbx, [r13+0]
0x1801b18e6  jmp     short loc_1801B195F
0x1801b18e8  lea     rdx, [rbx-0C8h]
0x1801b18ef  mov     [rsp+120h+Buffer], rdx
0x1801b18f4  mov     eax, [rsi-0C8h]
0x1801b18fa  cmp     eax, r12d
0x1801b18fd  jz      short loc_1801B1923
0x1801b18ff  add     eax, 0FFFFFFFEh
0x1801b1902  mov     ecx, eax
0x1801b1904  add     rcx, rcx
0x1801b1907  mov     rax, [rdx+rcx*8+14h]
0x1801b190c  cmp     rax, [rsi-0C4h]
0x1801b1913  jnz     short loc_1801B195C
0x1801b1915  mov     rax, [rdx+rcx*8+1Ch]
0x1801b191a  cmp     rax, [rsi-0BCh]
0x1801b1921  jnz     short loc_1801B195C
0x1801b1923  mov     rdx, [rdx+58h]
0x1801b1927  xor     ecx, ecx; hAlgorithm
0x1801b1929  add     rdx, 10h; pbBuffer
0x1801b192d  lea     r9d, [rcx+2]; dwFlags
0x1801b1931  lea     r8d, [rcx+4]; cbBuffer
0x1801b1935  call    cs:__imp_BCryptGenRandom
0x1801b193b  lea     r9, [rsp+120h+NewElement]; NewElement
0x1801b1940  mov     r8d, 8; BufferSize
0x1801b1946  lea     rdx, [rsp+120h+Buffer]; Buffer
0x1801b194b  lea     rcx, [rsi-68h]; Table
0x1801b194f  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1801b1955  cmp     dword ptr [rsp+120h+NewElement], 0
0x1801b195a  jz      short loc_1801B1995
0x1801b195c  mov     rbx, [rbx]
0x1801b195f  cmp     rbx, r13
0x1801b1962  jnz     short loc_1801B18E8
0x1801b1964  mov     rsi, [rsi]
0x1801b1967  inc     r15d
0x1801b196a  cmp     rsi, r14
0x1801b196d  jnz     loc_1801B18BA
0x1801b1973  xor     edx, edx
0x1801b1975  lea     ecx, [r15+4]
0x1801b1979  mov     eax, ecx
0x1801b197b  xor     esi, esi
0x1801b197d  div     r15d
0x1801b1980  sub     ecx, edx
0x1801b1982  xor     edx, edx
0x1801b1984  mov     eax, ecx
0x1801b1986  div     r15d
0x1801b1989  mov     r13d, eax
0x1801b198c  test    eax, eax
0x1801b198e  jle     short loc_1801B19FC
0x1801b1990  mov     rbx, [r14]
0x1801b1993  jmp     short loc_1801B19E3
0x1801b1995  mov     ecx, 1392h
0x1801b199a  jmp     short loc_1801B19F6
0x1801b199c  lea     rdx, [rbp+4Fh+RestartKey]; RestartKey
0x1801b19a0  mov     [rbp+4Fh+RestartKey], 0
0x1801b19a8  lea     rcx, [rbx-68h]; Table
0x1801b19ac  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1801b19b2  test    rax, rax
0x1801b19b5  jz      short loc_1801B19E0
0x1801b19b7  mov     rdx, [rax]
0x1801b19ba  lea     rcx, [rbx-68h]; Table
0x1801b19be  mov     [rsp+120h+Buffer], rdx
0x1801b19c3  mov     r8, [rdx+58h]
0x1801b19c7  mov     rdx, rax; Buffer
0x1801b19ca  or      dword ptr [r8+14h], 4
0x1801b19cf  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1801b19d5  movzx   eax, al
0x1801b19d8  mov     dword ptr [rsp+120h+NewElement], eax
0x1801b19dc  test    eax, eax
0x1801b19de  jz      short loc_1801B19F1
0x1801b19e0  mov     rbx, [rbx]
0x1801b19e3  cmp     rbx, r14
0x1801b19e6  jnz     short loc_1801B199C
0x1801b19e8  inc     esi
0x1801b19ea  cmp     esi, r13d
0x1801b19ed  jl      short loc_1801B1990
0x1801b19ef  jmp     short loc_1801B19FC
0x1801b19f1  mov     ecx, 490h; dwErrCode
0x1801b19f6  call    cs:__imp_SetLastError
0x1801b19fc  mov     eax, r12d
0x1801b19ff  lea     rbx, [rbp+4Fh+var_C0]
0x1801b1a03  shl     rax, 4
0x1801b1a07  add     rbx, rax
0x1801b1a0a  mov     rax, [rbx]
0x1801b1a0d  cmp     rax, rbx
0x1801b1a10  jz      short loc_1801B1A73
0x1801b1a12  mov     rcx, [rax]
0x1801b1a15  cmp     [rcx+8], rax
0x1801b1a19  jnz     loc_1801B1B0C
0x1801b1a1f  mov     rdx, [rax+8]
0x1801b1a23  cmp     [rdx], rax
0x1801b1a26  jnz     loc_1801B1B0C
0x1801b1a2c  lea     r14, [rax-0C8h]
0x1801b1a33  mov     [rdx], rcx
0x1801b1a36  lea     rsi, [r14+60h]
0x1801b1a3a  mov     [rcx+8], rdx
0x1801b1a3e  jmp     short loc_1801B1A4C
0x1801b1a40  mov     rdx, rax; Buffer
0x1801b1a43  mov     rcx, rsi; Table
0x1801b1a46  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1801b1a4c  lea     rdx, [rsp+120h+var_D0]; RestartKey
0x1801b1a51  mov     [rsp+120h+var_D0], 0
0x1801b1a5a  mov     rcx, rsi; Table
0x1801b1a5d  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1801b1a63  test    rax, rax
0x1801b1a66  jnz     short loc_1801B1A40
0x1801b1a68  mov     rcx, r14; hMem
0x1801b1a6b  call    cs:__imp_LocalFree
0x1801b1a71  jmp     short loc_1801B1A0A
0x1801b1a73  sub     r12d, 1
0x1801b1a77  jns     short loc_1801B19FC
0x1801b1a79  mov     rax, [rdi]
0x1801b1a7c  cmp     [rax+8], rdi
0x1801b1a80  jnz     loc_1801B1B0C
0x1801b1a86  mov     rcx, [rdi+8]
0x1801b1a8a  cmp     [rcx], rdi
0x1801b1a8d  jnz     short loc_1801B1B0C
0x1801b1a8f  mov     rax, [rsp+120h+var_E8]
0x1801b1a94  lea     rdx, [rsp+120h+var_E8]
0x1801b1a99  cmp     [rax+8], rdx
0x1801b1a9d  jnz     short loc_1801B1B0C
0x1801b1a9f  mov     rax, [rsp+120h+var_E0]
0x1801b1aa4  lea     rdx, [rsp+120h+var_E8]
0x1801b1aa9  cmp     [rax], rdx
0x1801b1aac  jnz     short loc_1801B1B0C
0x1801b1aae  lea     rax, [rsp+120h+var_E8]
0x1801b1ab3  mov     [rcx], rax
0x1801b1ab6  lea     rdx, [rsp+120h+var_E8]
0x1801b1abb  mov     rax, [rsp+120h+var_E0]
0x1801b1ac0  mov     [rdi+8], rax
0x1801b1ac4  mov     [rax], rdi
0x1801b1ac7  mov     rax, [rsp+120h+var_E8]
0x1801b1acc  mov     [rsp+120h+var_E0], rcx
0x1801b1ad1  cmp     [rax+8], rdx
0x1801b1ad5  jnz     short loc_1801B1B0C
0x1801b1ad7  lea     rdx, [rsp+120h+var_E8]
0x1801b1adc  cmp     [rcx], rdx
0x1801b1adf  jnz     short loc_1801B1B0C
0x1801b1ae1  mov     [rcx], rax
0x1801b1ae4  mov     [rax+8], rcx
0x1801b1ae8  mov     eax, dword ptr [rsp+120h+NewElement]
0x1801b1aec  mov     rcx, [rbp+4Fh+var_50]
0x1801b1af0  xor     rcx, rsp; StackCookie
0x1801b1af3  call    __security_check_cookie
0x1801b1af8  add     rsp, 0E8h
0x1801b1aff  pop     r15
0x1801b1b01  pop     r14
0x1801b1b03  pop     r13
0x1801b1b05  pop     r12
0x1801b1b07  pop     rdi
0x1801b1b08  pop     rsi
0x1801b1b09  pop     rbx
0x1801b1b0a  pop     rbp
0x1801b1b0b  retn
0x1801b1b0c  mov     ecx, 3
0x1801b1b11  int     29h; Win8: RtlFailFast(ecx)
```
