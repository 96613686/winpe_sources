# StubNlmCacheInitialize

- ea: `0x1800164a4`
- end: `0x180016917`
- name: `StubNlmCacheInitialize`
- size: `1139`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting`

## callers

- `0x1800159b8`
- `0x18001ae2c`

## callees

- `0x180003ed0`
- `0x1800050d0`
- `0x180011f74`
- `0x180012aa0`
- `0x1800164a4`
- `0x18001bf40`
- `0x18001c470`
- `0x18001c500`
- `0x18001d09c`
- `0x18001e368`
- `0x180021cec`
- `0x18002c0d8`
- `0x18002c160`
- `0x18002c29c`
- `0x18002c494`
- `0x18002c924`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x18001685d`
- `ntdll!RtlDeleteHashTable` at `0x18001685d`
- `ntdll!RtlCreateHashTable` at `0x1800165b1`
- `ntdll!RtlCreateHashTable` at `0x1800165b1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180016604`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180016604`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016854`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016854`

## pseudocode

```c
__int64 __fastcall StubNlmCacheInitialize(
        __int64 a1,
        const wchar_t *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 *a7)
{
  void *v8; // rax
  __int64 v9; // rbx
  unsigned int v10; // edi
  __int64 v11; // r8
  const wchar_t *v12; // rax
  __int64 v13; // rcx
  unsigned int v14; // esi
  __int64 v15; // rdi
  wchar_t *v16; // rax
  __int64 v17; // r8
  HRESULT v18; // eax
  unsigned int v19; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r9
  unsigned int v23; // eax
  __int64 v25; // [rsp+80h] [rbp+8h] BYREF

  v25 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids);
  }
  v25 = 0;
  v8 = (void *)MALLOC(0xE8u);
  v9 = (__int64)v8;
  if ( !v8 )
  {
    v10 = 8;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids, 8);
    }
    goto LABEL_60;
  }
  memset_0(v8, 0, 0xE8u);
  *(_DWORD *)(v9 + 64) = 256;
  *(_QWORD *)(v9 + 40) = MALLOC;
  *(_DWORD *)(v9 + 60) = 2592000;
  *(_QWORD *)(v9 + 48) = VpnFree;
  *(_DWORD *)(v9 + 56) = 1;
  *(_QWORD *)(v9 + 80) = v9 + 72;
  *(_QWORD *)(v9 + 72) = v9 + 72;
  v25 = v9 + 88;
  if ( !(unsigned __int8)RtlCreateHashTable(&v25, 0, 0) )
  {
    v10 = 8;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids, 8);
    }
    goto LABEL_59;
  }
  InitializeCriticalSection((LPCRITICAL_SECTION)v9);
  *(_QWORD *)(v9 + 128) = 0;
  if ( a2 )
  {
    v12 = a2;
    v13 = 0x7FFFFFFF;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v13;
    }
    while ( v13 );
    v14 = v13 == 0 ? 0x80070057 : 0;
    v15 = (0x7FFFFFFF - v13) & -(__int64)(v13 != 0);
    if ( !v13 )
    {
      v10 = 87;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, v11, v14, 87);
      }
      goto LABEL_58;
    }
    v16 = (wchar_t *)MALLOC(2 * v15 + 2);
    *(_QWORD *)(v9 + 128) = v16;
    if ( !v16 )
    {
      v10 = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, v17, v14, 8);
      }
      goto LABEL_58;
    }
    v18 = StringCchCopyW(v16, v15 + 1, a2);
    if ( v18 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids,
        (unsigned int)v18);
    }
    v19 = StubNlmCacheTryPersistentStore(v9);
    v10 = v19;
    if ( v19 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_57;
      }
      v21 = 44;
      v22 = v19;
LABEL_40:
      WPP_SF_d(v20[2], v21, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids, v22);
LABEL_57:
      StubNlmCacheCleanupActiveStore(v9);
      VpnFree(*(LPVOID *)(v9 + 128));
      *(_QWORD *)(v9 + 128) = 0;
LABEL_58:
      DeleteCriticalSection((LPCRITICAL_SECTION)v9);
      RtlDeleteHashTable(v9 + 88);
LABEL_59:
      VpnFree((LPVOID)v9);
LABEL_60:
      *a7 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids, v10);
      }
      return v10;
    }
    v23 = StubNlmCacheLoadFromPersistentStore(v9);
    if ( v23
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids, v23);
    }
    if ( !(unsigned int)InitializeWorkQueue((LPCRITICAL_SECTION)(v9 + 136)) )
    {
      v22 = 8;
      v10 = 8;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_57;
      }
      v21 = 46;
      goto LABEL_40;
    }
    if ( !(unsigned int)StartWorkQueue(v9 + 136) )
    {
      v10 = 31;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids, 31);
      }
      UninitializeWorkQueue(v9 + 136);
      goto LABEL_57;
    }
    if ( *(_DWORD *)(v9 + 224) )
    {
      *(_DWORD *)(v9 + 224) = 0;
      StubNlmCacheCleanupBothStores(v9);
    }
    else
    {
      StubNlmCachePruneOldEntries(v9);
    }
  }
  *a7 = v9;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800164a4  mov     [rsp+arg_0], rcx
0x1800164a9  push    rbx
0x1800164aa  push    rbp
0x1800164ab  push    rsi
0x1800164ac  push    rdi
0x1800164ad  push    r12
0x1800164af  push    r13
0x1800164b1  push    r14
0x1800164b3  push    r15
0x1800164b5  sub     rsp, 38h
0x1800164b9  mov     rbp, rdx
0x1800164bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800164c3  lea     r13, WPP_GLOBAL_Control
0x1800164ca  mov     r12b, 4
0x1800164cd  cmp     rcx, r13
0x1800164d0  jz      short loc_1800164F3
0x1800164d2  test    [rcx+1Ch], r12b
0x1800164d6  jz      short loc_1800164F3
0x1800164d8  cmp     byte ptr [rcx+19h], 6
0x1800164dc  jb      short loc_1800164F3
0x1800164de  mov     rcx, [rcx+10h]
0x1800164e2  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x1800164e9  mov     edx, 26h ; '&'
0x1800164ee  call    WPP_SF_
0x1800164f3  mov     edi, 0E8h
0x1800164f8  xor     r15d, r15d
0x1800164fb  mov     ecx, edi; dwBytes
0x1800164fd  mov     [rsp+78h+arg_0], r15
0x180016505  call    MALLOC
0x18001650a  mov     rbx, rax
0x18001650d  test    rax, rax
0x180016510  jnz     short loc_180016555
0x180016512  lea     r9d, [r15+8]
0x180016516  mov     edi, r9d
0x180016519  mov     rcx, cs:WPP_GLOBAL_Control
0x180016520  cmp     rcx, r13
0x180016523  jz      loc_18001686B
0x180016529  test    [rcx+1Ch], r12b
0x18001652d  jz      loc_18001686B
0x180016533  cmp     byte ptr [rcx+19h], 2
0x180016537  jb      loc_18001686B
0x18001653d  mov     rcx, [rcx+10h]
0x180016541  lea     edx, [rax+27h]
0x180016544  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x18001654b  call    WPP_SF_d
0x180016550  jmp     loc_18001686B
0x180016555  mov     r8, rdi; Size
0x180016558  xor     edx, edx; Val
0x18001655a  mov     rcx, rbx; void *
0x18001655d  call    memset_0
0x180016562  mov     dword ptr [rbx+40h], 100h
0x180016569  lea     rax, MALLOC
0x180016570  mov     [rbx+28h], rax
0x180016574  lea     r14, [rbx+58h]
0x180016578  mov     dword ptr [rbx+3Ch], 278D00h
0x18001657f  lea     rax, VpnFree
0x180016586  mov     [rbx+30h], rax
0x18001658a  lea     rcx, [rsp+78h+arg_0]
0x180016592  mov     dword ptr [rbx+38h], 1
0x180016599  lea     rax, [rbx+48h]
0x18001659d  mov     [rax+8], rax
0x1800165a1  xor     r8d, r8d
0x1800165a4  mov     [rax], rax
0x1800165a7  xor     edx, edx
0x1800165a9  mov     [rsp+78h+arg_0], r14
0x1800165b1  call    cs:__imp_RtlCreateHashTable
0x1800165b7  test    al, al
0x1800165b9  jnz     short loc_180016601
0x1800165bb  mov     r9d, 8
0x1800165c1  mov     edi, r9d
0x1800165c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165cb  cmp     rcx, r13
0x1800165ce  jz      loc_180016863
0x1800165d4  test    [rcx+1Ch], r12b
0x1800165d8  jz      loc_180016863
0x1800165de  cmp     byte ptr [rcx+19h], 2
0x1800165e2  jb      loc_180016863
0x1800165e8  mov     rcx, [rcx+10h]
0x1800165ec  lea     edx, [r9+20h]
0x1800165f0  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x1800165f7  call    WPP_SF_d
0x1800165fc  jmp     loc_180016863
0x180016601  mov     rcx, rbx; lpCriticalSection
0x180016604  call    cs:__imp_InitializeCriticalSection
0x18001660a  mov     [rbx+80h], r15
0x180016611  test    rbp, rbp
0x180016614  jz      loc_1800168C9
0x18001661a  mov     edx, 7FFFFFFFh
0x18001661f  mov     rax, rbp
0x180016622  mov     ecx, edx
0x180016624  cmp     [rax], r15w
0x180016628  jz      short loc_180016634
0x18001662a  add     rax, 2
0x18001662e  sub     rcx, 1
0x180016632  jnz     short loc_180016624
0x180016634  mov     rax, rcx
0x180016637  neg     rax
0x18001663a  mov     rax, rcx
0x18001663d  sbb     esi, esi
0x18001663f  sub     rdx, rcx
0x180016642  not     esi
0x180016644  and     esi, 80070057h
0x18001664a  neg     rax
0x18001664d  sbb     rdi, rdi
0x180016650  and     rdi, rdx
0x180016653  test    rcx, rcx
0x180016656  jnz     short loc_180016697
0x180016658  lea     edi, [rcx+57h]
0x18001665b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016662  cmp     rcx, r13
0x180016665  jz      loc_180016851
0x18001666b  test    [rcx+1Ch], r12b
0x18001666f  jz      loc_180016851
0x180016675  cmp     byte ptr [rcx+19h], 2
0x180016679  jb      loc_180016851
0x18001667f  lea     edx, [rdi-2Eh]
0x180016682  mov     [rsp+78h+var_58], edi
0x180016686  mov     rcx, [rcx+10h]
0x18001668a  mov     r9d, esi
0x18001668d  call    WPP_SF_dD
0x180016692  jmp     loc_180016851
0x180016697  lea     rcx, ds:2[rdi*2]; dwBytes
0x18001669f  call    MALLOC
0x1800166a4  mov     [rbx+80h], rax
0x1800166ab  test    rax, rax
0x1800166ae  jnz     short loc_1800166E5
0x1800166b0  lea     r9d, [rax+8]
0x1800166b4  mov     edi, r9d
0x1800166b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166be  cmp     rcx, r13
0x1800166c1  jz      loc_180016851
0x1800166c7  test    [rcx+1Ch], r12b
0x1800166cb  jz      loc_180016851
0x1800166d1  cmp     byte ptr [rcx+19h], 2
0x1800166d5  jb      loc_180016851
0x1800166db  lea     edx, [rax+2Ah]
0x1800166de  mov     [rsp+78h+var_58], r9d
0x1800166e3  jmp     short loc_180016686
0x1800166e5  lea     rdx, [rdi+1]; cchDest
0x1800166e9  mov     r8, rbp; pszSrc
0x1800166ec  mov     rcx, rax; pszDest
0x1800166ef  call    StringCchCopyW
0x1800166f4  test    eax, eax
0x1800166f6  jns     short loc_180016728
0x1800166f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166ff  cmp     rcx, r13
0x180016702  jz      short loc_180016728
0x180016704  test    [rcx+1Ch], r12b
0x180016708  jz      short loc_180016728
0x18001670a  cmp     byte ptr [rcx+19h], 2
0x18001670e  jb      short loc_180016728
0x180016710  mov     rcx, [rcx+10h]
0x180016714  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x18001671b  mov     edx, 2Bh ; '+'
0x180016720  mov     r9d, eax
0x180016723  call    WPP_SF_d
0x180016728  mov     rcx, rbx
0x18001672b  call    StubNlmCacheTryPersistentStore
0x180016730  mov     edi, eax
0x180016732  test    eax, eax
0x180016734  jz      short loc_180016777
0x180016736  mov     rcx, cs:WPP_GLOBAL_Control
0x18001673d  cmp     rcx, r13
0x180016740  jz      loc_180016836
0x180016746  test    [rcx+1Ch], r12b
0x18001674a  jz      loc_180016836
0x180016750  cmp     byte ptr [rcx+19h], 2
0x180016754  jb      loc_180016836
0x18001675a  mov     edx, 2Ch ; ','
0x18001675f  mov     r9d, eax
0x180016762  mov     rcx, [rcx+10h]
0x180016766  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x18001676d  call    WPP_SF_d
0x180016772  jmp     loc_180016836
0x180016777  mov     rcx, rbx; __int64
0x18001677a  call    StubNlmCacheLoadFromPersistentStore
0x18001677f  test    eax, eax
0x180016781  jz      short loc_1800167B3
0x180016783  mov     rcx, cs:WPP_GLOBAL_Control
0x18001678a  cmp     rcx, r13
0x18001678d  jz      short loc_1800167B3
0x18001678f  test    [rcx+1Ch], r12b
0x180016793  jz      short loc_1800167B3
0x180016795  cmp     byte ptr [rcx+19h], 3
0x180016799  jb      short loc_1800167B3
0x18001679b  mov     rcx, [rcx+10h]
0x18001679f  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x1800167a6  mov     edx, 2Dh ; '-'
0x1800167ab  mov     r9d, eax
0x1800167ae  call    WPP_SF_d
0x1800167b3  lea     rsi, [rbx+88h]
0x1800167ba  mov     rcx, rsi; lpCriticalSection
0x1800167bd  call    InitializeWorkQueue
0x1800167c2  test    eax, eax
0x1800167c4  jnz     short loc_1800167ED
0x1800167c6  lea     r9d, [rax+8]
0x1800167ca  mov     edi, r9d
0x1800167cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167d4  cmp     rcx, r13
0x1800167d7  jz      short loc_180016836
0x1800167d9  test    [rcx+1Ch], r12b
0x1800167dd  jz      short loc_180016836
0x1800167df  cmp     byte ptr [rcx+19h], 2
0x1800167e3  jb      short loc_180016836
0x1800167e5  lea     edx, [rax+2Eh]
0x1800167e8  jmp     loc_180016762
0x1800167ed  mov     rcx, rsi
0x1800167f0  call    StartWorkQueue
0x1800167f5  test    eax, eax
0x1800167f7  jnz     loc_1800168AA
0x1800167fd  lea     edi, [rax+1Fh]
0x180016800  mov     rcx, cs:WPP_GLOBAL_Control
0x180016807  cmp     rcx, r13
0x18001680a  jz      short loc_18001682E
0x18001680c  test    [rcx+1Ch], r12b
0x180016810  jz      short loc_18001682E
0x180016812  cmp     byte ptr [rcx+19h], 2
0x180016816  jb      short loc_18001682E
0x180016818  mov     rcx, [rcx+10h]
0x18001681c  lea     edx, [rax+2Fh]
0x18001681f  mov     r9d, edi
0x180016822  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x180016829  call    WPP_SF_d
0x18001682e  mov     rcx, rsi
0x180016831  call    UninitializeWorkQueue
0x180016836  mov     rcx, rbx
0x180016839  call    StubNlmCacheCleanupActiveStore
0x18001683e  mov     rcx, [rbx+80h]; lpMem
0x180016845  call    VpnFree
0x18001684a  mov     [rbx+80h], r15
0x180016851  mov     rcx, rbx; lpCriticalSection
0x180016854  call    cs:__imp_DeleteCriticalSection
0x18001685a  mov     rcx, r14
0x18001685d  call    cs:__imp_RtlDeleteHashTable
0x180016863  mov     rcx, rbx; lpMem
0x180016866  call    VpnFree
0x18001686b  mov     rax, [rsp+78h+arg_30]
0x180016873  mov     [rax], r15
0x180016876  mov     rcx, cs:WPP_GLOBAL_Control
0x18001687d  cmp     rcx, r13
0x180016880  jz      short loc_1800168A6
0x180016882  test    [rcx+1Ch], r12b
0x180016886  jz      short loc_1800168A6
0x180016888  cmp     byte ptr [rcx+19h], 6
0x18001688c  jb      short loc_1800168A6
0x18001688e  mov     rcx, [rcx+10h]
0x180016892  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x180016899  mov     edx, 31h ; '1'
0x18001689e  mov     r9d, edi
0x1800168a1  call    WPP_SF_d
0x1800168a6  mov     eax, edi
0x1800168a8  jmp     short loc_180016906
0x1800168aa  mov     rcx, rbx
0x1800168ad  cmp     [rbx+0E0h], r15d
0x1800168b4  jz      short loc_1800168C4
0x1800168b6  mov     [rbx+0E0h], r15d
0x1800168bd  call    StubNlmCacheCleanupBothStores
0x1800168c2  jmp     short loc_1800168C9
0x1800168c4  call    StubNlmCachePruneOldEntries
0x1800168c9  mov     rax, [rsp+78h+arg_30]
0x1800168d1  mov     [rax], rbx
0x1800168d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168db  cmp     rcx, r13
0x1800168de  jz      short loc_180016904
0x1800168e0  test    [rcx+1Ch], r12b
0x1800168e4  jz      short loc_180016904
0x1800168e6  cmp     byte ptr [rcx+19h], 6
0x1800168ea  jb      short loc_180016904
0x1800168ec  mov     rcx, [rcx+10h]
0x1800168f0  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x1800168f7  mov     edx, 30h ; '0'
0x1800168fc  xor     r9d, r9d
0x1800168ff  call    WPP_SF_d
0x180016904  xor     eax, eax
0x180016906  add     rsp, 38h
0x18001690a  pop     r15
0x18001690c  pop     r14
0x18001690e  pop     r13
0x180016910  pop     r12
0x180016912  pop     rdi
0x180016913  pop     rsi
0x180016914  pop     rbp
0x180016915  pop     rbx
0x180016916  retn
```
