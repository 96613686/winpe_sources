# CScriptAutoDetection::HasSpecialScript(ushort const *,SPECIAL_SCRIPTS_FOUND_FLAGS *,ulong *,ulong *)

- ea: `0x1800758e0`
- end: `0x180075ade`
- name: `?HasSpecialScript@CScriptAutoDetection@@QEAAJPEBGPEAW4SPECIAL_SCRIPTS_FOUND_FLAGS@@PEAK2@Z`
- size: `510`
- prototype: `int(CScriptAutoDetection *__hidden this, const unsigned __int16 *, enum SPECIAL_SCRIPTS_FOUND_FLAGS *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007565c`

## callees

- `0x1800030b6`
- `0x180046dec`
- `0x1800758e0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180075a16`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180075a16`
- `elscore!MappingRecognizeText` at `0x180075986`
- `elscore!MappingRecognizeText` at `0x180075986`
- `elscore!MappingFreePropertyBag` at `0x180075abb`
- `elscore!MappingFreePropertyBag` at `0x180075abb`

## pseudocode

```c
__int64 __fastcall CScriptAutoDetection::HasSpecialScript(
        PMAPPING_SERVICE_INFO *this,
        const unsigned __int16 *a2,
        enum SPECIAL_SCRIPTS_FOUND_FLAGS *a3,
        unsigned int *a4,
        unsigned int *a5)
{
  unsigned int v5; // r12d
  unsigned int *v6; // rbp
  HRESULT v10; // ebx
  __int64 v11; // r8
  int v12; // edi
  unsigned int v13; // esi
  DWORD v14; // r13d
  __int64 v15; // r10
  _WORD *pData; // rcx
  int v17; // eax
  unsigned int v18; // eax
  struct _GUID v20; // [rsp+30h] [rbp-88h] BYREF
  struct _MAPPING_PROPERTY_BAG pBag; // [rsp+40h] [rbp-78h] BYREF
  __int64 v22; // [rsp+D0h] [rbp+18h]

  v5 = 0;
  v6 = a4;
  *(_DWORD *)a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  v20 = (struct _GUID)xmmword_18008EE48;
  v10 = CElsServiceInstance::Initialize(this, &v20);
  if ( v10 >= 0 )
  {
    memset_0(&pBag, 0, sizeof(pBag));
    v11 = -1;
    pBag.Size = 64;
    do
      ++v11;
    while ( a2[v11] );
    v10 = MappingRecognizeText(*this, a2, v11, 0, 0, &pBag);
    if ( v10 >= 0 )
    {
      v12 = 0;
      v13 = 0;
      v14 = 0;
      if ( pBag.dwRangesCount )
      {
        do
        {
          v15 = v14;
          pData = pBag.prgResultRanges[v14].pData;
          if ( pData && *pData )
          {
            while ( v5 < 0x22 )
            {
              v22 = 3LL * (int)v5;
              if ( CompareStringOrdinal(
                     (LPCWCH)pBag.prgResultRanges[v15].pData,
                     -1,
                     (&off_180084310)[3 * (int)v5],
                     -1,
                     1) == 2 )
              {
                v5 = 0;
                v17 = *((_DWORD *)&off_180084310 + 2 * v22 + 2);
                if ( (v17 & *(_DWORD *)a3) == 0 )
                {
                  ++v12;
                  *(_DWORD *)a3 |= v17;
                  v18 = (unsigned int)(&off_180084310)[v22 + 1];
                  if ( v18 )
                  {
                    v13 = (unsigned int)(&off_180084310)[v22 + 1];
                    if ( *((_BYTE *)&off_180084310 + 8 * v22 + 12) )
                    {
                      if ( a5 && !*a5 )
                        *a5 = v18;
                    }
                  }
                }
                goto LABEL_24;
              }
              v15 = v14;
              ++v5;
            }
            if ( (*(_DWORD *)a3 & 0x2000000) == 0 )
            {
              *(_DWORD *)a3 |= 0x2000000u;
              ++v12;
            }
            v5 = 0;
          }
LABEL_24:
          ++v14;
        }
        while ( v14 < pBag.dwRangesCount );
        v6 = a4;
      }
      if ( v6 && v12 == 1 )
        *v6 = v13;
      if ( !*(_DWORD *)a3 )
        v10 = 1;
      MappingFreePropertyBag(&pBag);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800758e0  mov     [rsp+arg_0], rbx
0x1800758e5  mov     [rsp+arg_18], r9
0x1800758ea  push    rbp
0x1800758eb  push    rsi
0x1800758ec  push    rdi
0x1800758ed  push    r12
0x1800758ef  push    r13
0x1800758f1  push    r14
0x1800758f3  push    r15
0x1800758f5  sub     rsp, 80h
0x1800758fc  xor     r12d, r12d
0x1800758ff  mov     rbp, r9
0x180075902  mov     [r8], r12d
0x180075905  mov     r15, r8
0x180075908  mov     rdi, rdx
0x18007590b  mov     rsi, rcx
0x18007590e  test    r9, r9
0x180075911  jz      short loc_180075916
0x180075913  mov     [r9], r12d
0x180075916  mov     r14, [rsp+0B8h+arg_20]
0x18007591e  test    r14, r14
0x180075921  jz      short loc_180075926
0x180075923  mov     [r14], r12d
0x180075926  movups  xmm0, cs:xmmword_18008EE48
0x18007592d  lea     rdx, [rsp+0B8h+var_88]; struct _GUID
0x180075932  movdqu  xmmword ptr [rsp+0B8h+var_88.Data1], xmm0
0x180075938  call    ?Initialize@CElsServiceInstance@@IEAAJU_GUID@@@Z; CElsServiceInstance::Initialize(_GUID)
0x18007593d  mov     ebx, eax
0x18007593f  test    eax, eax
0x180075941  js      loc_180075AC1
0x180075947  mov     ebx, 40h ; '@'
0x18007594c  lea     rcx, [rsp+0B8h+pBag]; void *
0x180075951  mov     r8d, ebx; Size
0x180075954  xor     edx, edx; Val
0x180075956  call    memset_0
0x18007595b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007595f  mov     [rsp+0B8h+pBag.Size], rbx
0x180075964  inc     r8; dwLength
0x180075967  cmp     [rdi+r8*2], r12w
0x18007596c  jnz     short loc_180075964
0x18007596e  mov     rcx, [rsi]; pServiceInfo
0x180075971  lea     rax, [rsp+0B8h+pBag]
0x180075976  mov     [rsp+0B8h+pbag], rax; pbag
0x18007597b  xor     r9d, r9d; dwIndex
0x18007597e  mov     rdx, rdi; pszText
0x180075981  mov     [rsp+0B8h+pOptions], r12; pOptions
0x180075986  call    cs:__imp_MappingRecognizeText
0x18007598c  mov     ebx, eax
0x18007598e  test    eax, eax
0x180075990  js      loc_180075AC1
0x180075996  mov     edi, r12d
0x180075999  mov     esi, r12d
0x18007599c  mov     r13d, r12d
0x18007599f  mov     eax, 1
0x1800759a4  cmp     [rsp+0B8h+pBag.dwRangesCount], r12d
0x1800759a9  jbe     loc_180075AA4
0x1800759af  lea     r8, off_180084310; "Hira"
0x1800759b6  mov     ebp, eax
0x1800759b8  mov     eax, r13d
0x1800759bb  lea     r10, [rax+rax*8]
0x1800759bf  mov     rax, [rsp+0B8h+pBag.prgResultRanges]
0x1800759c4  mov     [rsp+0B8h+arg_20], r10
0x1800759cc  mov     rcx, [rax+r10*8+18h]
0x1800759d1  test    rcx, rcx
0x1800759d4  jz      loc_180075A89
0x1800759da  cmp     [rcx], r12w
0x1800759de  jz      loc_180075A89
0x1800759e4  cmp     r12d, 22h ; '"'
0x1800759e8  jnb     loc_180075A74
0x1800759ee  mov     rcx, [rsp+0B8h+pBag.prgResultRanges]
0x1800759f3  or      r9d, 0FFFFFFFFh; cchCount2
0x1800759f7  movsxd  rax, r12d
0x1800759fa  or      edx, r9d; cchCount1
0x1800759fd  mov     dword ptr [rsp+0B8h+pOptions], ebp; bIgnoreCase
0x180075a01  mov     rcx, [rcx+r10*8+18h]; lpString1
0x180075a06  lea     rax, [rax+rax*2]
0x180075a0a  mov     r8, [r8+rax*8]; lpString2
0x180075a0e  mov     [rsp+0B8h+arg_10], rax
0x180075a16  call    cs:__imp_CompareStringOrdinal
0x180075a1c  lea     r8, off_180084310; "Hira"
0x180075a23  cmp     eax, 2
0x180075a26  jz      short loc_180075A35
0x180075a28  mov     r10, [rsp+0B8h+arg_20]
0x180075a30  add     r12d, ebp
0x180075a33  jmp     short loc_1800759E4
0x180075a35  mov     rcx, [rsp+0B8h+arg_10]
0x180075a3d  xor     r12d, r12d
0x180075a40  mov     edx, [r15]
0x180075a43  mov     eax, [r8+rcx*8+8]
0x180075a48  test    edx, eax
0x180075a4a  jnz     short loc_180075A89
0x180075a4c  or      eax, edx
0x180075a4e  add     edi, ebp
0x180075a50  mov     [r15], eax
0x180075a53  mov     eax, [r8+rcx*8+10h]
0x180075a58  test    eax, eax
0x180075a5a  jz      short loc_180075A89
0x180075a5c  mov     esi, eax
0x180075a5e  cmp     [r8+rcx*8+0Ch], r12b
0x180075a63  jz      short loc_180075A89
0x180075a65  test    r14, r14
0x180075a68  jz      short loc_180075A89
0x180075a6a  cmp     [r14], r12d
0x180075a6d  jnz     short loc_180075A89
0x180075a6f  mov     [r14], eax
0x180075a72  jmp     short loc_180075A89
0x180075a74  mov     eax, [r15]
0x180075a77  bt      eax, 19h
0x180075a7b  jb      short loc_180075A86
0x180075a7d  bts     eax, 19h
0x180075a81  mov     [r15], eax
0x180075a84  inc     edi
0x180075a86  xor     r12d, r12d
0x180075a89  add     r13d, ebp
0x180075a8c  cmp     r13d, [rsp+0B8h+pBag.dwRangesCount]
0x180075a91  jb      loc_1800759B8
0x180075a97  mov     rbp, [rsp+0B8h+arg_18]
0x180075a9f  mov     eax, 1
0x180075aa4  test    rbp, rbp
0x180075aa7  jz      short loc_180075AB0
0x180075aa9  cmp     edi, eax
0x180075aab  jnz     short loc_180075AB0
0x180075aad  mov     [rbp+0], esi
0x180075ab0  cmp     [r15], r12d
0x180075ab3  lea     rcx, [rsp+0B8h+pBag]; pBag
0x180075ab8  cmovz   ebx, eax
0x180075abb  call    cs:__imp_MappingFreePropertyBag
0x180075ac1  mov     eax, ebx
0x180075ac3  mov     rbx, [rsp+0B8h+arg_0]
0x180075acb  add     rsp, 80h
0x180075ad2  pop     r15
0x180075ad4  pop     r14
0x180075ad6  pop     r13
0x180075ad8  pop     r12
0x180075ada  pop     rdi
0x180075adb  pop     rsi
0x180075adc  pop     rbp
0x180075add  retn
```
