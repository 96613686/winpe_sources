# KerbInitSearchForests(_KERB_MESSAGE_BUFFER *,_KERB_FSO_COMMON_FUNCTION_TABLE const *,ulong *)

- ea: `0x18007a5cc`
- end: `0x18007a925`
- name: `?KerbInitSearchForests@@YAJPEAU_KERB_MESSAGE_BUFFER@@PEBU_KERB_FSO_COMMON_FUNCTION_TABLE@@PEAK@Z`
- size: `857`
- prototype: `__int64 __fastcall(struct _KERB_MESSAGE_BUFFER *, const struct _KERB_FSO_COMMON_FUNCTION_TABLE *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800391e4`

## callees

- `0x1800101c4`
- `0x18007a5cc`
- `0x18007b790`
- `0x18007b7d8`
- `0x18007b868`
- `0x18007b948`
- `0x18007ba6c`
- `0x18007bb04`
- `0x18007bb5c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18007a6c7`
- `ntdll!RtlInitUnicodeString` at `0x18007a6c7`
- `ntdll!RtlInitializeCriticalSection` at `0x18007a632`
- `ntdll!RtlInitializeCriticalSection` at `0x18007a632`
- `ntdll!RtlLeaveCriticalSection` at `0x18007a73e`
- `ntdll!RtlLeaveCriticalSection` at `0x18007a778`
- `ntdll!RtlLeaveCriticalSection` at `0x18007a7c5`
- `ntdll!RtlLeaveCriticalSection` at `0x18007a7d4`
- `ntdll!RtlLeaveCriticalSection` at `0x18007a896`
- `ntdll!RtlLeaveCriticalSection` at `0x18007a908`
- `ntdll!RtlLeaveCriticalSection` at `0x18007a73e`
- `ntdll!RtlLeaveCriticalSection` at `0x18007a778`
- `ntdll!RtlLeaveCriticalSection` at `0x18007a7c5`
- `ntdll!RtlLeaveCriticalSection` at `0x18007a7d4`
- `ntdll!RtlLeaveCriticalSection` at `0x18007a896`
- `ntdll!RtlLeaveCriticalSection` at `0x18007a908`
- `ntdll!RtlEnterCriticalSection` at `0x18007a674`
- `ntdll!RtlEnterCriticalSection` at `0x18007a72a`
- `ntdll!RtlEnterCriticalSection` at `0x18007a78f`
- `ntdll!RtlEnterCriticalSection` at `0x18007a674`
- `ntdll!RtlEnterCriticalSection` at `0x18007a72a`
- `ntdll!RtlEnterCriticalSection` at `0x18007a78f`

## pseudocode

```c
__int64 __fastcall KerbInitSearchForests(
        struct _KERB_MESSAGE_BUFFER *a1,
        const struct _KERB_FSO_COMMON_FUNCTION_TABLE *a2,
        unsigned int *a3)
{
  _WORD *v3; // rbx
  int v5; // r12d
  struct _KERBEROS_LIST *v6; // rcx
  NTSTATUS inited; // esi
  const WCHAR *v8; // rbp
  __int64 v9; // r14
  struct _KERB_FSO_CACHE_ENTRY *FsoCacheEntry; // rax
  struct _KERB_FSO_CACHE_ENTRY *v11; // rbx
  struct _KERB_FSO_CACHE_ENTRY *v12; // rcx
  struct _KERB_FSO_CACHE_ENTRY *v13; // rdi
  struct _KERB_FSO_CACHE_ENTRY **v14; // rcx
  __int64 v15; // rax
  struct _KERB_FSO_CACHE_ENTRY **v16; // rdi
  struct _KERB_FSO_CACHE_ENTRY *i; // rax
  struct _KERB_FSO_CACHE_ENTRY **v18; // rbx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF
  struct _KERB_FSO_CACHE_ENTRY *v21; // [rsp+78h] [rbp+10h] BYREF
  unsigned int *v22; // [rsp+80h] [rbp+18h]

  v22 = a3;
  v21 = a2;
  v3 = (_WORD *)*((_QWORD *)a1 + 1);
  v5 = 0;
  DestinationString = 0;
  if ( !KerbSearchForestsInitialized )
  {
    qword_1800B2CE0 = (__int64)&KerbFsoCache;
    KerbFsoCache = (struct _KERB_FSO_CACHE_ENTRY *)&KerbFsoCache;
    FsoFunctions = (const struct _KERB_FSO_COMMON_FUNCTION_TABLE *const)&KerbFunctions;
    inited = RtlInitializeCriticalSection(&stru_1800B2CE8);
    if ( inited < 0 )
    {
      KerbFreeList(v6);
      goto LABEL_58;
    }
    KerbSearchForestsInitialized = 1;
  }
  for ( ; v3; ++v3 )
  {
    if ( !*v3 )
      break;
    if ( *v3 == 59 || *v3 == 32 )
      *v3 = 0;
  }
  inited = RtlEnterCriticalSection(&stru_1800B2CE8);
  if ( inited >= 0 )
  {
    v5 = 1;
    KerbNumSearchForests = 0;
    v8 = (const WCHAR *)*((_QWORD *)a1 + 1);
    v9 = 0;
    while ( 1 )
    {
      if ( !v8 || (unsigned __int64)v8 >= *((_QWORD *)a1 + 1) + (unsigned __int64)*(unsigned int *)a1 )
      {
        if ( v9 )
        {
          v16 = *(struct _KERB_FSO_CACHE_ENTRY ***)v9;
          if ( *(struct _KERB_FSO_CACHE_ENTRY ***)v9 == &KerbFsoCache )
          {
            v16 = 0;
          }
          else
          {
            v16[1] = 0;
            *(_QWORD *)qword_1800B2CE0 = 0;
            *(_QWORD *)v9 = &KerbFsoCache;
            qword_1800B2CE0 = v9;
          }
          for ( i = KerbFirstFsoCacheEntry(); i; i = KerbNextFsoCacheEntry(i) )
            ++KerbNumSearchForests;
          RtlLeaveCriticalSection(&stru_1800B2CE8);
          v5 = 0;
          if ( v16 )
          {
            do
            {
              v18 = (struct _KERB_FSO_CACHE_ENTRY **)*v16;
              *v16 = 0;
              v16[1] = 0;
              KerbDereferenceFsoCacheEntry((struct _KERB_FSO_CACHE_ENTRY *)v16);
              v16 = v18;
            }
            while ( v18 );
          }
        }
        else
        {
          inited = 0;
        }
        goto LABEL_58;
      }
      if ( *v8 )
      {
        RtlInitUnicodeString(&DestinationString, v8);
        FsoCacheEntry = KerbFindFsoCacheEntry(&DestinationString);
        v21 = FsoCacheEntry;
        v11 = FsoCacheEntry;
        if ( FsoCacheEntry )
        {
          if ( FsoCacheEntry == (struct _KERB_FSO_CACHE_ENTRY *)v9 )
          {
            KerbDereferenceFsoCacheEntry(FsoCacheEntry);
            goto LABEL_40;
          }
          KerbUnlinkFso(FsoCacheEntry);
        }
        else
        {
          inited = KerbInitFsoEntry(&DestinationString, &v21);
          if ( inited < 0 )
            goto LABEL_58;
          v11 = v21;
        }
        if ( v9 )
        {
          v13 = v11;
          RtlEnterCriticalSection(&stru_1800B2CE8);
          inited = 0;
          if ( *(_QWORD *)v11 && *((_QWORD *)v11 + 1)
            || (v14 = *(struct _KERB_FSO_CACHE_ENTRY ***)v9) == 0
            || !*(_QWORD *)(v9 + 8) )
          {
            RtlLeaveCriticalSection(&stru_1800B2CE8);
            inited = -1073741811;
          }
          else
          {
            *(_QWORD *)v11 = v14;
            v14[1] = v11;
            *((_QWORD *)v11 + 1) = v9;
            *(_QWORD *)v9 = v11;
            RtlLeaveCriticalSection(&stru_1800B2CE8);
          }
        }
        else
        {
          RtlEnterCriticalSection(&stru_1800B2CE8);
          if ( *(_QWORD *)v11 && *((_QWORD *)v11 + 1) )
          {
            RtlLeaveCriticalSection(&stru_1800B2CE8);
            inited = -1073741811;
          }
          else
          {
            v12 = KerbFsoCache;
            if ( *((struct _KERB_FSO_CACHE_ENTRY ***)KerbFsoCache + 1) != &KerbFsoCache )
              __fastfail(3u);
            *(_QWORD *)v11 = KerbFsoCache;
            *((_QWORD *)v11 + 1) = &KerbFsoCache;
            *((_QWORD *)v12 + 1) = v11;
            KerbFsoCache = v11;
            RtlLeaveCriticalSection(&stru_1800B2CE8);
            inited = 0;
          }
          v13 = v11;
        }
        KerbDereferenceFsoCacheEntry(v11);
        if ( inited < 0 )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_0117c3251e483c44e322262836b1158e_Traceguids);
          }
        }
        else
        {
          v9 = (__int64)v13;
        }
      }
LABEL_40:
      v15 = -1;
      do
        ++v15;
      while ( v8[v15] );
      v8 += v15 + 1;
    }
  }
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_0117c3251e483c44e322262836b1158e_Traceguids);
LABEL_58:
  if ( v22 )
    *v22 = KerbNumSearchForests;
  if ( v5 )
    RtlLeaveCriticalSection(&stru_1800B2CE8);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18007a5cc  mov     rax, rsp
0x18007a5cf  mov     [rax+8], rbx
0x18007a5d3  mov     [rax+18h], r8
0x18007a5d7  mov     [rax+10h], rdx
0x18007a5db  push    rbp
0x18007a5dc  push    rsi
0x18007a5dd  push    rdi
0x18007a5de  push    r12
0x18007a5e0  push    r13
0x18007a5e2  push    r14
0x18007a5e4  push    r15
0x18007a5e6  sub     rsp, 30h
0x18007a5ea  mov     rbx, [rcx+8]
0x18007a5ee  xor     edi, edi
0x18007a5f0  cmp     cs:?KerbSearchForestsInitialized@@3HA, edi; int KerbSearchForestsInitialized
0x18007a5f6  xorps   xmm0, xmm0
0x18007a5f9  mov     r13, rcx
0x18007a5fc  mov     r12d, edi
0x18007a5ff  movups  xmmword ptr [rax-48h], xmm0
0x18007a603  lea     ebp, [rdi+1]
0x18007a606  lea     rcx, ?KerbFsoCache@@3U_KERBEROS_LIST@@A; _KERBEROS_LIST KerbFsoCache
0x18007a60d  jnz     short loc_18007A64E
0x18007a60f  lea     rax, ?KerbFunctions@@3U_KERB_FSO_COMMON_FUNCTION_TABLE@@A; _KERB_FSO_COMMON_FUNCTION_TABLE KerbFunctions
0x18007a616  mov     cs:qword_1800B2CE0, rcx
0x18007a61d  mov     cs:?KerbFsoCache@@3U_KERBEROS_LIST@@A, rcx; _KERBEROS_LIST KerbFsoCache
0x18007a624  lea     rcx, stru_1800B2CE8; CriticalSection
0x18007a62b  mov     cs:?FsoFunctions@@3PEBU_KERB_FSO_COMMON_FUNCTION_TABLE@@EB, rax; _KERB_FSO_COMMON_FUNCTION_TABLE const * const FsoFunctions
0x18007a632  call    cs:__imp_RtlInitializeCriticalSection
0x18007a638  mov     esi, eax
0x18007a63a  test    eax, eax
0x18007a63c  jns     short loc_18007A648
0x18007a63e  call    ?KerbFreeList@@YAXPEAU_KERBEROS_LIST@@@Z; KerbFreeList(_KERBEROS_LIST *)
0x18007a643  jmp     loc_18007A8E7
0x18007a648  mov     cs:?KerbSearchForestsInitialized@@3HA, ebp; int KerbSearchForestsInitialized
0x18007a64e  test    rbx, rbx
0x18007a651  jz      short loc_18007A66D
0x18007a653  cmp     [rbx], di
0x18007a656  jz      short loc_18007A66D
0x18007a658  cmp     word ptr [rbx], 3Bh ; ';'
0x18007a65c  jz      short loc_18007A664
0x18007a65e  cmp     word ptr [rbx], 20h ; ' '
0x18007a662  jnz     short loc_18007A667
0x18007a664  mov     [rbx], di
0x18007a667  add     rbx, 2
0x18007a66b  jnz     short loc_18007A653
0x18007a66d  lea     rcx, stru_1800B2CE8; CriticalSection
0x18007a674  call    cs:__imp_RtlEnterCriticalSection
0x18007a67a  lea     r15, WPP_GLOBAL_Control
0x18007a681  mov     esi, eax
0x18007a683  test    eax, eax
0x18007a685  js      loc_18007A8C0
0x18007a68b  mov     r12d, ebp
0x18007a68e  mov     cs:?KerbNumSearchForests@@3KA, edi; ulong KerbNumSearchForests
0x18007a694  mov     rbp, [r13+8]
0x18007a698  mov     r14, rdi
0x18007a69b  test    rbp, rbp
0x18007a69e  jz      loc_18007A83C
0x18007a6a4  mov     eax, [r13+0]
0x18007a6a8  add     rax, [r13+8]
0x18007a6ac  cmp     rbp, rax
0x18007a6af  jnb     loc_18007A83C
0x18007a6b5  cmp     [rbp+0], di
0x18007a6b9  jz      loc_18007A819
0x18007a6bf  mov     rdx, rbp; SourceString
0x18007a6c2  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18007a6c7  call    cs:__imp_RtlInitUnicodeString
0x18007a6cd  lea     rcx, [rsp+68h+DestinationString]; String1
0x18007a6d2  call    ?KerbFindFsoCacheEntry@@YAPEAU_KERB_FSO_CACHE_ENTRY@@PEAU_UNICODE_STRING@@@Z; KerbFindFsoCacheEntry(_UNICODE_STRING *)
0x18007a6d7  mov     [rsp+68h+arg_8], rax
0x18007a6dc  mov     rbx, rax
0x18007a6df  test    rax, rax
0x18007a6e2  jnz     short loc_18007A704
0x18007a6e4  lea     rdx, [rsp+68h+arg_8]; struct _KERB_FSO_CACHE_ENTRY **
0x18007a6e9  lea     rcx, [rsp+68h+DestinationString]; struct _UNICODE_STRING *
0x18007a6ee  call    ?KerbInitFsoEntry@@YAJPEAU_UNICODE_STRING@@PEAPEAU_KERB_FSO_CACHE_ENTRY@@@Z; KerbInitFsoEntry(_UNICODE_STRING *,_KERB_FSO_CACHE_ENTRY * *)
0x18007a6f3  mov     esi, eax
0x18007a6f5  test    eax, eax
0x18007a6f7  js      loc_18007A8E7
0x18007a6fd  mov     rbx, [rsp+68h+arg_8]
0x18007a702  jmp     short loc_18007A71B
0x18007a704  mov     rcx, rax; struct _KERB_FSO_CACHE_ENTRY *
0x18007a707  cmp     rax, r14
0x18007a70a  jnz     short loc_18007A716
0x18007a70c  call    ?KerbDereferenceFsoCacheEntry@@YAXPEAU_KERB_FSO_CACHE_ENTRY@@@Z; KerbDereferenceFsoCacheEntry(_KERB_FSO_CACHE_ENTRY *)
0x18007a711  jmp     loc_18007A819
0x18007a716  call    ?KerbUnlinkFso@@YAJPEAU_KERB_FSO_CACHE_ENTRY@@@Z; KerbUnlinkFso(_KERB_FSO_CACHE_ENTRY *)
0x18007a71b  test    r14, r14
0x18007a71e  jnz     short loc_18007A785
0x18007a720  lea     rsi, stru_1800B2CE8
0x18007a727  mov     rcx, rsi; CriticalSection
0x18007a72a  call    cs:__imp_RtlEnterCriticalSection
0x18007a730  cmp     [rbx], rdi
0x18007a733  jz      short loc_18007A74B
0x18007a735  cmp     [rbx+8], rdi
0x18007a739  jz      short loc_18007A74B
0x18007a73b  mov     rcx, rsi; CriticalSection
0x18007a73e  call    cs:__imp_RtlLeaveCriticalSection
0x18007a744  mov     esi, 0C000000Dh
0x18007a749  jmp     short loc_18007A780
0x18007a74b  mov     rcx, cs:?KerbFsoCache@@3U_KERBEROS_LIST@@A; _KERBEROS_LIST KerbFsoCache
0x18007a752  lea     rdx, ?KerbFsoCache@@3U_KERBEROS_LIST@@A; _KERBEROS_LIST KerbFsoCache
0x18007a759  cmp     [rcx+8], rdx
0x18007a75d  jnz     loc_18007A835
0x18007a763  mov     [rbx], rcx
0x18007a766  mov     [rbx+8], rdx
0x18007a76a  mov     [rcx+8], rbx
0x18007a76e  mov     rcx, rsi; CriticalSection
0x18007a771  mov     cs:?KerbFsoCache@@3U_KERBEROS_LIST@@A, rbx; _KERBEROS_LIST KerbFsoCache
0x18007a778  call    cs:__imp_RtlLeaveCriticalSection
0x18007a77e  mov     esi, edi
0x18007a780  mov     rdi, rbx
0x18007a783  jmp     short loc_18007A7DF
0x18007a785  lea     rcx, stru_1800B2CE8; CriticalSection
0x18007a78c  mov     rdi, rbx
0x18007a78f  call    cs:__imp_RtlEnterCriticalSection
0x18007a795  xor     esi, esi
0x18007a797  cmp     [rbx], rsi
0x18007a79a  jz      short loc_18007A7A2
0x18007a79c  cmp     [rbx+8], rsi
0x18007a7a0  jnz     short loc_18007A7CD
0x18007a7a2  mov     rcx, [r14]
0x18007a7a5  test    rcx, rcx
0x18007a7a8  jz      short loc_18007A7CD
0x18007a7aa  cmp     [r14+8], rsi
0x18007a7ae  jz      short loc_18007A7CD
0x18007a7b0  mov     [rbx], rcx
0x18007a7b3  mov     [rcx+8], rbx
0x18007a7b7  lea     rcx, stru_1800B2CE8; CriticalSection
0x18007a7be  mov     [rbx+8], r14
0x18007a7c2  mov     [r14], rbx
0x18007a7c5  call    cs:__imp_RtlLeaveCriticalSection
0x18007a7cb  jmp     short loc_18007A7DF
0x18007a7cd  lea     rcx, stru_1800B2CE8; CriticalSection
0x18007a7d4  call    cs:__imp_RtlLeaveCriticalSection
0x18007a7da  mov     esi, 0C000000Dh
0x18007a7df  mov     rcx, rbx; struct _KERB_FSO_CACHE_ENTRY *
0x18007a7e2  call    ?KerbDereferenceFsoCacheEntry@@YAXPEAU_KERB_FSO_CACHE_ENTRY@@@Z; KerbDereferenceFsoCacheEntry(_KERB_FSO_CACHE_ENTRY *)
0x18007a7e7  test    esi, esi
0x18007a7e9  js      short loc_18007A7F0
0x18007a7eb  mov     r14, rdi
0x18007a7ee  jmp     short loc_18007A817
0x18007a7f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a7f7  cmp     rcx, r15
0x18007a7fa  jz      short loc_18007A817
0x18007a7fc  test    [rcx+1Ch], r12b
0x18007a800  jz      short loc_18007A817
0x18007a802  mov     rcx, [rcx+10h]
0x18007a806  lea     r8, WPP_0117c3251e483c44e322262836b1158e_Traceguids
0x18007a80d  mov     edx, 0Bh
0x18007a812  call    WPP_SF_
0x18007a817  xor     edi, edi
0x18007a819  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007a81d  inc     rax
0x18007a820  cmp     [rbp+rax*2+0], di
0x18007a825  jnz     short loc_18007A81D
0x18007a827  lea     rbp, [rbp+rax*2+0]
0x18007a82c  add     rbp, 2
0x18007a830  jmp     loc_18007A69B
0x18007a835  mov     ecx, 3
0x18007a83a  int     29h; Win8: RtlFailFast(ecx)
0x18007a83c  test    r14, r14
0x18007a83f  jnz     short loc_18007A848
0x18007a841  mov     esi, edi
0x18007a843  jmp     loc_18007A8E7
0x18007a848  mov     rdi, [r14]
0x18007a84b  lea     rcx, ?KerbFsoCache@@3U_KERBEROS_LIST@@A; _KERBEROS_LIST KerbFsoCache
0x18007a852  xor     ebp, ebp
0x18007a854  cmp     rdi, rcx
0x18007a857  jnz     short loc_18007A85D
0x18007a859  mov     edi, ebp
0x18007a85b  jmp     short loc_18007A875
0x18007a85d  mov     [rdi+8], rbp
0x18007a861  mov     rax, cs:qword_1800B2CE0
0x18007a868  mov     [rax], rbp
0x18007a86b  mov     [r14], rcx
0x18007a86e  mov     cs:qword_1800B2CE0, r14
0x18007a875  call    ?KerbFirstFsoCacheEntry@@YAPEAU_KERB_FSO_CACHE_ENTRY@@XZ; KerbFirstFsoCacheEntry(void)
0x18007a87a  jmp     short loc_18007A88A
0x18007a87c  inc     cs:?KerbNumSearchForests@@3KA; ulong KerbNumSearchForests
0x18007a882  mov     rcx, rax; struct _KERB_FSO_CACHE_ENTRY *
0x18007a885  call    ?KerbNextFsoCacheEntry@@YAPEAU_KERB_FSO_CACHE_ENTRY@@PEAU1@@Z; KerbNextFsoCacheEntry(_KERB_FSO_CACHE_ENTRY *)
0x18007a88a  test    rax, rax
0x18007a88d  jnz     short loc_18007A87C
0x18007a88f  lea     rcx, stru_1800B2CE8; CriticalSection
0x18007a896  call    cs:__imp_RtlLeaveCriticalSection
0x18007a89c  mov     r12d, ebp
0x18007a89f  test    rdi, rdi
0x18007a8a2  jz      short loc_18007A8E7
0x18007a8a4  mov     rbx, [rdi]
0x18007a8a7  mov     rcx, rdi; struct _KERB_FSO_CACHE_ENTRY *
0x18007a8aa  mov     [rdi], rbp
0x18007a8ad  mov     [rdi+8], rbp
0x18007a8b1  call    ?KerbDereferenceFsoCacheEntry@@YAXPEAU_KERB_FSO_CACHE_ENTRY@@@Z; KerbDereferenceFsoCacheEntry(_KERB_FSO_CACHE_ENTRY *)
0x18007a8b6  mov     rdi, rbx
0x18007a8b9  test    rbx, rbx
0x18007a8bc  jnz     short loc_18007A8A4
0x18007a8be  jmp     short loc_18007A8E7
0x18007a8c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a8c7  cmp     rcx, r15
0x18007a8ca  jz      short loc_18007A8E7
0x18007a8cc  test    [rcx+1Ch], bpl
0x18007a8d0  jz      short loc_18007A8E7
0x18007a8d2  mov     rcx, [rcx+10h]
0x18007a8d6  lea     r8, WPP_0117c3251e483c44e322262836b1158e_Traceguids
0x18007a8dd  mov     edx, 0Ah
0x18007a8e2  call    WPP_SF_
0x18007a8e7  mov     rdx, [rsp+68h+arg_10]
0x18007a8ef  test    rdx, rdx
0x18007a8f2  jz      short loc_18007A8FC
0x18007a8f4  mov     eax, cs:?KerbNumSearchForests@@3KA; ulong KerbNumSearchForests
0x18007a8fa  mov     [rdx], eax
0x18007a8fc  test    r12d, r12d
0x18007a8ff  jz      short loc_18007A90E
0x18007a901  lea     rcx, stru_1800B2CE8; CriticalSection
0x18007a908  call    cs:__imp_RtlLeaveCriticalSection
0x18007a90e  mov     rbx, [rsp+68h+arg_0]
0x18007a913  mov     eax, esi
0x18007a915  add     rsp, 30h
0x18007a919  pop     r15
0x18007a91b  pop     r14
0x18007a91d  pop     r13
0x18007a91f  pop     r12
0x18007a921  pop     rdi
0x18007a922  pop     rsi
0x18007a923  pop     rbp
0x18007a924  retn
```
